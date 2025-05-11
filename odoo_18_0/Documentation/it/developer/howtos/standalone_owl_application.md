# Create a standalone Owl application — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](frontend_owl_components.html "Use Owl components on the portal and website") |
  * [precedente](javascript_client_action.html "Create a client action") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Create a standalone Owl application



# Create a standalone Owl application¶

For any number of reasons, you may want to have a standalone Owl application that isn’t a part of the web client. One example in Odoo is the self-ordering application, that lets customers order food from their phone. In this chapter we will go into what’s required to achieve something like this.

## Overview¶

To have a standalone Owl app, a few things are required:

  * a root component for the application

  * an assets bundle that contains the setup code

  * a QWeb view that calls the assets bundle

  * a controller that renders the view




## 1\. Root component¶

To keep things simple, let’s start with a very straightforward component that just renders «Hello, World!». This will let us know at a glance if our setup is working.

First, create the template in `/your_module/static/src/standalone_app/root.xml`.
    
    
    <?xml version="1.0" encoding="UTF-8"?>
    <templates xml:space="preserve">
        <t t-name="your_module.Root">
            Hello, World!
        </t>
    </templates>
    

Then create the JavaScript file for that component in `/your_module/static/src/standalone_app/root.js`.
    
    
    import { Component } from "@odoo/owl";
    
    export class Root extends Component {
        static template = "your_module.Root";
        static props = {};
    }
    

It’s generally a good idea to have the application setup code that mounts the component in a separate file. Create the JavaScript file that will mount the app in `/your_module/static/src/standalone_app/app.js`.
    
    
    import { whenReady } from "@odoo/owl";
    import { mountComponent } from "@web/env";
    import { Root } from "./root";
    
    whenReady(() => mountComponent(Root, document.body));
    

The `mountComponent` utility function will take care of creating the Owl application and configuring it correctly: it will create an environment, start the [services](../reference/frontend/services.html#frontend-services), make sure the app is translated and give the app access to the templates from your assets bundle, among other things.

Vedi anche

[Owl components reference](../reference/frontend/owl_components.html#frontend-components).

## 2\. Creating an assets bundle containing our code¶

In the manifest of your module, create a new [assets bundle](../reference/frontend/assets.html#reference-assets-bundle). It should include the `web._assets_core` bundle, which contains the Odoo JavaScript framework and the core libraries it needs (e.g. Owl and luxon), after which you can have a glob that adds all the files for your application in the bundle.
    
    
    {
        # ...
        'assets': {
            'your_module.assets_standalone_app': [
                ('include', 'web._assets_helpers'),
                'web/static/src/scss/pre_variables.scss',
                'web/static/lib/bootstrap/scss/_variables.scss',
                ('include', 'web._assets_bootstrap'),
                ('include', 'web._assets_core'),
                'your_module/static/src/standalone_app/**/*',
            ],
        }
    }
    

The other lines are bundles and scss files that are required to make Bootstrap work. They are mandatory, as the components of the web framework use bootstrap classes for their styling and layout.

Attenzione

Make sure that the files for your standalone app are only added to this bundle, if you already have a definition for `web.assets_backend` or `web.assets_frontend` and they have globs, make sure these globs don’t match the files for your standalone app, otherwise the startup code for your app will conflict with the existing startup code in those bundles.

Vedi anche

[Module manifest reference](../reference/backend/module.html#reference-module-manifest).

## 3\. XML view that calls the assets bundle¶

Now that we have created our assets bundle, we need to create a [QWeb view](../reference/user_interface/view_architectures.html#reference-view-architectures-qweb) that uses that assets bundle.
    
    
    <?xml version="1.0" encoding="utf-8"?>
    <odoo>
        <template id="your_module.standalone_app">&lt;!DOCTYPE html&gt;
            <html>
                <head>
                    <script type="text/javascript">
                        var odoo = {
                            csrf_token: "<t t-nocache="The csrf token must always be up to date." t-esc="request.csrf_token(None)"/>",
                            debug: "<t t-out="debug"/>",
                            __session_info__: <t t-esc="json.dumps(session_info)"/>,
                        };
                    </script>
                    <t t-call-assets="your_module.assets_standalone_app" />
                </head>
                <body/>
            </html>
        </template>
    </odoo>
    

This template only does two things: it initializes the `odoo` global variable, then calls the assets bundle we just defined. Initializing the `odoo` global variable is a necessary step. This variable should be an object that contains the following:

  * The CSRF token, which is required to interact with HTTP controllers in many cases.

  * The debug value, which is used in many places to add additional logging or developer-friendly checks.

  * `__session_info__`, that contains information from the server that is always needed and for which we don’t want to perform an additional request. More on this in the next section.




## 4\. Controller that renders the view¶

Now that we have the view, we need to make it accessible to the user. For that purpose, we will create an [HTTP controller](../reference/backend/http.html#reference-controllers) that renders that view and returns it to the user.
    
    
    from odoo.http import request, route, Controller
    
    class YourController(Controller):
        @route("/your_module/standalone_app", auth="public")
        def standalone_app(self):
            return request.render(
                'your_module.standalone_app',
                {
                    'session_info': request.env['ir.http'].get_frontend_session_info(),
                }
            )
    

Notice how we’re giving the template `session_info`. We get it from the `get_frontend_session_info` method, and it will end up containing information used by the web framework, such as the current user’s ID if they are logged in, the server version, the Odoo edition, etc.

At this point, if you open the url `/your_module/standalone_app` in your brower, you should see a blank page with the text «Hello, World!». At this point, you can start actually writing the code for your app.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/standalone_owl_application.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](frontend_owl_components.html "Use Owl components on the portal and website") |
  * [precedente](javascript_client_action.html "Create a client action") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Create a standalone Owl application


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