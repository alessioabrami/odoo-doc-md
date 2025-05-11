# Odoo Editor — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../user_interface.html "User interface") |
  * [precedente](qweb.html "QWeb Templates") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Odoo Editor



# Odoo Editor¶

Odoo Editor is Odoo’s own rich text editor. Its sources can be found in the [odoo-editor directory](https://github.com/odoo/odoo/blob/18.0/addons/web_editor/static/src/js/editor/odoo-editor).

## Powerbox¶

The Powerbox is a piece of user interface that contains commands organized into categories. It appears when typing `/` in the editor. The commands can be filtered when the user inputs text, and navigated with the arrow keys.

### Modifying the Powerbox¶

Only one Powerbox should be instantiated at the time, and that job is done by the editor itself. Its Powerbox instance can be found in its `powerbox` instance variable. To change the Powerbox’s contents and options, change the options passed to the editor before it gets instantiated.

Importante

Never instantiate the Powerbox yourself. Always use the current editor’s own instance instead.

Example

Say we want to add a new command `Document` to the Powerbox, just for the `mass_mailing` module. We want to add it to a new category called `Documentation` and we want it all the way at the top of the Powerbox.

`mass_mailing` [extends](https://github.com/odoo/odoo/blob/18.0/addons/mass_mailing/static/src/js/wysiwyg.js) `web_editor`’s [Wysiwyg class](https://github.com/odoo/odoo/blob/18.0/addons/web_editor/static/src/js/wysiwyg/wysiwyg.js), which instantiates the editor in its `start` method. Before doing so, it calls its own `_getPowerboxOptions` method, which can conveniently be overridden to add our new commands.

Since `mass_mailing` already overrides `_getPowerboxOptions`, let’s just add our new command to it:
    
    
    _getPowerboxOptions: function () {
        const options = this._super();
        // (existing code before the return statement)
        options.categories.push({
            name: _t('Documentation'),
            priority: 300,
        });
        options.commands.push({
            name: _t('Document'),
            category: _t('Documentation'),
            description: _t("Add this text to your mailing's documentation"),
            fontawesome: 'fa-book',
            priority: 1, // This is the only command in its category anyway.
        });
        return options;
    }
    

Importante

In order to allow the names and descriptions of your commands and categories to be translated, make sure to wrap them in the `_t` function.

Suggerimento

To avoid out-of-control escalations, don’t use random numbers for your priorities: look at which other priorities already exist and choose your value accordingly (like you would do for a `z-index`).

### Opening a custom Powerbox¶

It is possible to open the Powerbox with a custom set of categories and commands, bypassing all pre-existing ones. To do that, call the `open` method of the Powerbox and pass it your custom commands and categories.

Example

We need the current instance of the Powerbox, which can be found in the current editor. In the [Wysiwyg class](https://github.com/odoo/odoo/blob/18.0/addons/web_editor/static/src/js/wysiwyg/wysiwyg.js), you will find it as `this.odooEditor.powerbox`.

Now to open it with our custom «Document» command in a custom «Documentation» category:
    
    
    this.odooEditor.powerbox.open(
        [{
            name: _t('Document'),
            category: _t('Documentation'),
            description: _t("Add this text to your mailing's documentation"),
            fontawesome: 'fa-book',
            priority: 1, // This is the only command in its category anyway.
        }],
        [{
            name: _t('Documentation'),
            priority: 300,
        }]
    );
    

### Filtering commands¶

There are three ways to filter commands:

  1. Via the `powerboxFilters` Powerbox option.

  2. Via a given command’s `isDisabled` entry.

  3. The user can filter commands by simply typing text after opening the Powerbox. It will fuzzy-match that text with the names of the categories and commands.




### Reference¶

#### Category¶

Name | Type | Description  
---|---|---  
`name` | `string` | the name of the category  
`priority` | `number` | used to order the category: a category with a higher priority is displayed higher into the Powerbox (categories with the same priority are ordered alphabetically)  
  
Nota

If several categories exist with the same name, they will be grouped into one. Its priority will be that defined in the version of the category that was declared last.

#### Command¶

Name | Type | Description  
---|---|---  
`name` | `string` | the name of the command  
`category` | `string` | the name of the category the command belongs to  
`description` | `string` | a short text to describe the command  
`fontawesome` | `string` | the name of a _Font Awesome_ that will serve as the command’s icon  
`priority` | `number` | used to order the command: a command with a higher priority is displayed higher into the Powerbox (commands with the same priority are ordered alphabetically)  
`callback` | `function` (`() => void`) | the function to execute when the command is picked (can be asynchronous)  
`isDisabled` (optional) | `function` (`() => void`) | a function used to disable the command under certain conditions (when it returns `true`, the command will be disabled)  
  
Nota

If the command points to a category that doesn’t exist yet, that category will be created and appended at the end of the Powerbox.

#### Options¶

The following options can be passed to OdooEditor, that will then be passed to the instance of the Powerbox:

Name | Type | Description  
---|---|---  
`commands` | `array of commands` | commands to add to the default defined by the editor  
`categories` | `array of categories` | categories to add to the default defined by the editor  
`powerboxFilters` | `array of functions` (`commands => commands`) | functions used to filter commands displayed in the Powerbox  
`getContextFromParentRect` | `function` (`() => DOMRect`) | a function that returns the `DOMRect` of an ancestor of the editor (can be useful when the editor is in an iframe)  
  
[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/frontend/odoo_editor.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../user_interface.html "User interface") |
  * [precedente](qweb.html "QWeb Templates") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Odoo Editor


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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