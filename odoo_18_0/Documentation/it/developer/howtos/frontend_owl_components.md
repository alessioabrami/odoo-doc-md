# Use Owl components on the portal and website — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_themes.html "Website themes") |
  * [precedente](standalone_owl_application.html "Create a standalone Owl application") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Use Owl components on the portal and website



# Use Owl components on the portal and website¶

In this article, you will learn how you can leverage Owl components on the portal and website.

## Overview¶

To use Owl components on the website or portal, you will need to do a few things:

  * Create your Owl component and register it in the `public_components` registry

  * Add that component to the `web.assets_frontend` bundle

  * Add an `<owl-component>` tag to a website or portal page to use the component




## 1\. Creating the Owl component¶

To keep things simple, let’s start with a very straightforward component that just renders «Hello, World!». This will let us know at a glance if our setup is working.

First, create the template in `/your_module/static/src/portal_component/your_component.xml`.
    
    
    <?xml version="1.0" encoding="UTF-8"?>
    <templates xml:space="preserve">
        <t t-name="your_module.YourComponent">
            Hello, World!
        </t>
    </templates>
    

Then create the JavaScript file for that component in `/your_module/static/src/portal_component/your_component.js`, and add it to the `public_components` registry:
    
    
    import { Component } from "@odoo/owl";
    import { registry } from "@web/core/registry"
    
    export class YourComponent extends Component {
        static template = "your_module.YourComponent";
        static props = {};
    }
    
    registry.category("public_components").add("your_module.YourComponent", YourComponent);
    

Vedi anche

[Owl components reference](../reference/frontend/owl_components.html#frontend-components).

## 2\. Adding your component to the `web.assets_frontend` bundle¶

The `web.assets_frontend` bundle is the assets bundle that is used by the portal and website, you’ll want to add your component’s code to that bundle so that the public components service can find your component and mount it. In your module’s manifest, in the assets section, add an entry for `web.assets_frontend` and add your component’s files:
    
    
    {
        # ...
        'assets': {
            'web.assets_frontend': [
                'your_module/static/src/portal_component/**/*',
            ],
        }
    }
    

Vedi anche

[Module manifest reference](../reference/backend/module.html#reference-module-manifest).

## 3\. Adding an `<owl-component>` tag to a page¶

Now we need add an `<owl-component>` tag that will serve as the target for the component to be mounted. For the sake of this example, we’ll add it directly to the portal’s home page with an xpath in `/your_module/views/templates.xml`.
    
    
    <?xml version="1.0" encoding="utf-8"?>
    <odoo>
        <template id="your_module.portal_my_home" inherit_id="portal.portal_my_home">
            <xpath expr="//*[hasclass('o_portal_my_home')]" position="before">
                <owl-component name="your_module.YourComponent" />
            </xpath>
        </template>
    </odoo>
    

Don’t forget to add this file to the data section of your assets bundle:
    
    
    {
        # ...
        'data': [
            'views/templates.xml',
        ]
    }
    

And that’s it! If you open the home page of the portal you should see the message «Hello, World!» at the top of the page.

## Points of caution¶

Owl components are rendered entirely in JavaScript by the browser. This can cause some issues:

  * Layout shift

  * Poorer indexing by search engines




For these reasons, you should only use Owl components on the portal and website for specific use cases described below.

### Layout shift¶

When a page initially renders content, and that content subsequently moves («shifts») within the page, this is referred to as a layout shift. When using Owl components in the portal or website, all of the HTML that surrounds the Owl component is rendered by the server and is the first thing that will be displayed to the user. When JavaScript starts running, Owl will mount your component, which will likely cause the surrounding elements to move around on the page. This can cause poor user experience: the user sees an element on the page that was initially rendered and with which they want to interact, so they move their cursor or finger above that element. Just as they’re about to click, the Owl component is mounted, and the element they want to interact with is moved. They click and interact with the Owl app instead.

This can be a frustrating experience, so you should be careful when designing your page that the Owl component will not move elements around. This can be achieved in various ways, e.g. by positioning it below all other existing elements, not having other interactive elements around, or reserving a fixed space for the Owl component using CSS.

Vedi anche

[Cumulative Layout Shift on web.dev](https://web.dev/articles/cls)

### Poorer indexing by search engines¶

When search engines build their index of the content of the web, they use web crawlers to find pages and analyze their content to show these pages in their search results. While modern search engines are generally capable of executing JavaScript code and should generally be able to view and index content rendered in JavaScript, they may not index the content as fast and penalize the page in search results.

Because most search engines do not reveal the exact way that they crawl and index web pages, it’s not always easy to know the extent of the impact that client-side rendering can have on your search engine scores. While it’s unlikely to make or break your SEO strategy, you should still only use Owl components when they are adding real value over server-side rendering.

## When to use Owl components on the portal and website¶

As explained in the previous sections, using Owl component can slightly degrade user experience if you’re not careful and may also hinder your SEO. So when should you choose to use Owl components in these places? Here are some general guidelines.

### When you don’t care about SEO¶

If a page cannot be indexed by search engines because it’s not available to the public, e.g. anything in the user portal, SEO performance is not a concern, as web crawlers cannot access these pages anyway. There are also some things that you do not want or care about indexing, e.g. if you want to have a page where the user can choose a date and time for an appointment, you probably don’t want search engines to index the dates on which an appointment is possible at a specific moment in time.

### When you need strong interactivity¶

The decision to use Owl is a trade-off between the previously mentioned disadvantages and the effort that Owl saves you by making it easy to build richly interactive user experiences. The main reason to use Owl is when you want to build an interface that can react in real time to user inputs without requiring the page to reload. If you mainly want to show static content to the user, you probably shouldn’t use an Owl component.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/howtos/frontend_owl_components.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_themes.html "Website themes") |
  * [precedente](standalone_owl_application.html "Create a standalone Owl application") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Use Owl components on the portal and website


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