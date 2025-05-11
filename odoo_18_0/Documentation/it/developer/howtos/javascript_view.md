# Customize a view type — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](javascript_client_action.html "Create a client action") |
  * [precedente](javascript_field.html "Customize a field") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Customize a view type



# Customize a view type¶

## Subclass an existing view¶

Assume we need to create a custom version of a generic view. For example, a kanban view with some extra ribbon-like widget on top (to display some specific custom information). In that case, this can be done in a few steps:

  1. Extend the kanban controller/renderer/model and register it in the view registry.

`custom_kanban_controller.js`¶
         
         import { KanbanController } from "@web/views/kanban/kanban_controller";
         import { kanbanView } from "@web/views/kanban/kanban_view";
         import { registry } from "@web/core/registry";
         
         // the controller usually contains the Layout and the renderer.
         class CustomKanbanController extends KanbanController {
             static template = "my_module.CustomKanbanView";
         
             // Your logic here, override or insert new methods...
             // if you override setup(), don't forget to call super.setup()
         }
         
         export const customKanbanView = {
             ...kanbanView, // contains the default Renderer/Controller/Model
             Controller: CustomKanbanController,
         };
         
         // Register it to the views registry
         registry.category("views").add("custom_kanban", customKanbanView);
         

In our custom kanban, we defined a new template. We can either inherit the kanban controller template and add our template pieces or we can define a completely new template.

`custom_kanban_controller.xml`¶
         
         <?xml version="1.0" encoding="UTF-8" ?>
         <templates>
             <t t-name="my_module.CustomKanbanView" t-inherit="web.KanbanView">
                 <xpath expr="//Layout" position="before">
                     <div>
                         Hello world !
                     </div>
                 </xpath>
             </t>
         </templates>
         

  2. Use the view with the `js_class` attribute in arch.
         
         <kanban js_class="custom_kanban">
             <templates>
                 <t t-name="kanban-box">
                     <!--Your comment-->
                 </t>
             </templates>
         </kanban>
         




The possibilities for extending views are endless. While we have only extended the controller here, you can also extend the renderer to add new buttons, modify how records are presented, or customize the dropdown, as well as extend other components such as the model and `buttonTemplate`.

## Create a new view from scratch¶

Creating a new view is an advanced topic. This guide highlight only the essential steps.

  1. Create the controller.

> The primary role of a controller is to facilitate the coordination between various components of a view, such as the Renderer, Model, and Layout.

`beautiful_controller.js`¶
         
         import { Layout } from "@web/search/layout";
         import { useService } from "@web/core/utils/hooks";
         import { Component, onWillStart, useState} from "@odoo/owl";
         
         export class BeautifulController extends Component {
             static template = "my_module.View";
             static components = { Layout };
         
             setup() {
                 this.orm = useService("orm");
         
                 // The controller create the model and make it reactive so whenever this.model is
                 // accessed and edited then it'll cause a rerendering
                 this.model = useState(
                     new this.props.Model(
                         this.orm,
                         this.props.resModel,
                         this.props.fields,
                         this.props.archInfo,
                         this.props.domain
                     )
                 );
         
                 onWillStart(async () => {
                     await this.model.load();
                 });
             }
         }
         

The template of the Controller displays the control panel with Layout and also the renderer.

`beautiful_controller.xml`¶
         
         <?xml version="1.0" encoding="UTF-8"?>
         <templates xml:space="preserve">
             <t t-name="my_module.View">
                 <Layout display="props.display" className="'h-100 overflow-auto'">
                     <t t-component="props.Renderer" records="model.records" propsYouWant="'Hello world'"/>
                 </Layout>
             </t>
         </templates>
         

  2. Create the renderer.

> The primary function of a renderer is to generate a visual representation of data by rendering the view that includes records.

`beautiful_renderer.js`¶
         
         import { Component } from "@odoo/owl";
         export class BeautifulRenderer extends Component {
             static template = "my_module.Renderer";
         }
         

`beautiful_renderer.xml`¶
         
         <?xml version="1.0" encoding="UTF-8"?>
         <templates xml:space="preserve">
             <t t-name="my_module.Renderer">
                 <t t-esc="props.propsYouWant"/>
                 <t t-foreach="props.records" t-as="record" t-key="record.id">
                     // Show records
                 </t>
             </t>
         </templates>
         

  3. Create the model.

The role of the model is to retrieve and manage all the necessary data in the view.

`beautiful_model.js`¶
         
         import { KeepLast } from "@web/core/utils/concurrency";
         
         export class BeautifulModel {
             constructor(orm, resModel, fields, archInfo, domain) {
                 this.orm = orm;
                 this.resModel = resModel;
                 // We can access arch information parsed by the beautiful arch parser
                 const { fieldFromTheArch } = archInfo;
                 this.fieldFromTheArch = fieldFromTheArch;
                 this.fields = fields;
                 this.domain = domain;
                 this.keepLast = new KeepLast();
             }
         
             async load() {
                 // The keeplast protect against concurrency call
                 const { length, records } = await this.keepLast.add(
                     this.orm.webSearchRead(this.resModel, this.domain, [this.fieldsFromTheArch], {})
                 );
                 this.records = records;
                 this.recordsLength = length;
             }
         }
         

Nota

For advanced cases, instead of creating a model from scratch, it is also possible to use `RelationalModel`, which is used by other views.

  4. Create the arch parser.

The role of the arch parser is to parse the arch view so the view has access to the information.

`beautiful_arch_parser.js`¶
         
         import { XMLParser } from "@web/core/utils/xml";
         
         export class BeautifulArchParser extends XMLParser {
             parse(arch) {
                 const xmlDoc = this.parseXML(arch);
                 const fieldFromTheArch = xmlDoc.getAttribute("fieldFromTheArch");
                 return {
                     fieldFromTheArch,
                 };
             }
         }
         

  5. Create the view and combine all the pieces together, then register the view in the views registry.

`beautiful_view.js`¶
         
         import { registry } from "@web/core/registry";
         import { BeautifulController } from "./beautiful_controller";
         import { BeautifulArchParser } from "./beautiful_arch_parser";
         import { BeautifylModel } from "./beautiful_model";
         import { BeautifulRenderer } from "./beautiful_renderer";
         
         export const beautifulView = {
             type: "beautiful",
             display_name: "Beautiful",
             icon: "fa fa-picture-o", // the icon that will be displayed in the Layout panel
             multiRecord: true,
             Controller: BeautifulController,
             ArchParser: BeautifulArchParser,
             Model: BeautifulModel,
             Renderer: BeautifulRenderer,
         
             props(genericProps, view) {
                 const { ArchParser } = view;
                 const { arch } = genericProps;
                 const archInfo = new ArchParser().parse(arch);
         
                 return {
                     ...genericProps,
                     Model: view.Model,
                     Renderer: view.Renderer,
                     archInfo,
                 };
             },
         };
         
         registry.category("views").add("beautifulView", beautifulView);
         

  6. Declare the [view](../reference/user_interface/view_records.html#reference-view-records-structure) in the arch.
         
         ...
         <record id="my_beautiful_view" model="ir.ui.view">
           <field name="name">my_view</field>
           <field name="model">my_model</field>
           <field name="arch" type="xml">
               <beautiful fieldFromTheArch="res.partner"/>
           </field>
         </record>
         ...
         




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/javascript_view.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](javascript_client_action.html "Create a client action") |
  * [precedente](javascript_field.html "Customize a field") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Customize a view type


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Point of Sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format