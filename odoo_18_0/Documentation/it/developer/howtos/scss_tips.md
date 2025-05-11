# Write lean easy-to-maintain CSS — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](javascript_field.html "Customize a field") |
  * [precedente](../howtos.html "How-to guides") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Write lean easy-to-maintain CSS



# Write lean easy-to-maintain CSS¶

There are many ways to lean and simplify SCSS. The first step is to establish if custom code is needed at all.

Odoo’s webclient has been designed to be modular, meaning that (potentially all) classes can be shared across views. Check the code before creating a new class. Chances are that there is already a class or an HTML tag doing exactly what you’re looking for.

On top of that, Odoo relies on [Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction/) (BS), one of the most complete CSS frameworks available. The framework has been customized in order to match Odoo’s design (both community and enterprise versions), meaning that you can use any BS class directly in Odoo and achieve a visual result that is consistent with our UI.

Avvertimento

  * The fact that a class achieves the desired visual result doesn’t necessarily mean that it’s the right one for the job. Be aware of classes triggering JS behaviors, for example.

  * Be careful about class semantics. Applying a **button class** to a **title** is not only semantically wrong, it may also lead to migration issues and visual inconsistencies.




The following sections describe tips to strip-down SCSS lines **when custom-code is the only way to go**.

## Browser defaults¶

By default, each browser renders content using a _user agent stylesheet_. To overcome inconsistencies between browsers, some of these rules are overridden by [Bootstrap Reboot](https://getbootstrap.com/docs/5.1/content/reboot/).

At this stage all «browser-specific-decoration» rules have been stripped away, but a big chunk of rules defining basic layout information is maintained (or reinforced by _Reboot_ for consistency reasons).

You can rely on these rules.

Example

Applying `display: block;` to a `<div/>` is normally not necessary.
    
    
    div.element {
       display: block;
       /* not needed 99% of the time */
    }
    

Example

In this instance, you may opt to switching the HTML tag rather than adding a new CSS rule.
    
    
    span.element {
       display: block;
       /* replace <span> with <div> instead
          to get 'display: block' by default */
    }
    

Here’s a non-comprehensive list of default rules:

Tag / Attribute | Defaults  
---|---  
`<div/>`, `<section/>`, `<header/>`, `<footer/>`… | `display: block`  
`<span/>`, `<a/>`, `<em/>`, `<b/>`… | `display: inline`  
`<button/>`, `<label/>`, `<output/>`… | `display: inline-block`  
`<img/>`, `<svg/>` | `vertical-align: middle`  
`<summary/>`, `[role="button"]` | `cursor: pointer;`  
`<q/>` |  `:before {content: open-quote}` `:after {content: close-quote}`  
… | …  
  
Vedi anche

[Bootstrap Reboot on GitHub](https://github.com/twbs/bootstrap/blob/1a6fdfae6b/scss/_reboot.scss)

## HTML tags¶

It may seem obvious, but the simplest and most **consistent** way of making text look like a title is to use a header tag (`<h1>`, `<h2>`, …). Besides reboot rules, mostly all tags carry decorative styles defined by Odoo.

Example

Don’t

XMLSCSS
    
    
    <span class="o_module_custom_title">
       Hello There!
    </span>
    
    <span class="o_module_custom_subtitle">
       I'm a subtitle.
    </span>
    
    
    
    .o_module_custom_title {
       display: block;
       font-size: 120%;
       font-weight: bold;
       animation: 1s linear 1s mycustomAnimation;
    }
    
    .o_module_custom_subtitle {
       display: block;
       font-size: 12px;
       font-weight: bold;
       animation: 2s linear 1s mycustomAnimation;
    }
    

Do

XMLSCSS
    
    
    <h5 class="o_module_custom_title">
       Hello There!
    </h5>
    
    <div class="o_module_custom_subtitle">
       <b><small>I'm a subtitle.</small></b>
    </div>
    
    
    
    .o_module_custom_title {
       animation: 1s linear 1s mycustomAnimation;
    }
    
    .o_module_custom_subtitle {
       animation: 2s linear 1s mycustomAnimation;
    }
    

Nota

Besides reducing the amount of code, a modular-design approach (use classes, tags, mixins…) keeps the visual result consistent and easily **maintainable**.

Following the last example, if Odoo titles” design changes, these changes will be applied in the `o_module_custom_title` element too since it’s using an `<h5>` tag.

## Utility classes¶

Our framework defines a multitude of utility classes designed to cover almost all layout/design/interaction needs. The simple fact that a class already exists justifies its use over custom CSS whenever possible.

Take the example of `position-relative`.
    
    
    position-relative {
       position: relative !important;
    }
    

Since a utility-class is defined, any CSS line with the declaration `position: relative` is **potentially** redundant.

Odoo relies on the default [Bootstrap utility-classes](https://getbootstrap.com/docs/5.1/utilities/background/) stack and defines its own using [Bootstrap API](https://getbootstrap.com/docs/5.1/utilities/api/).

Vedi anche

  * [Bootstrap utility classes](https://getbootstrap.com/docs/5.1/utilities/api/)

  * [Odoo custom utilities on github](https://github.com/odoo/odoo/blob/18.0/addons/web/static/src/scss/utilities_custom.scss)




### Handling utility-classes verbosity¶

The downside of utility-classes is the potential lack of readability.

Example
    
    
    <myComponent t-attf-class="d-flex border px-lg-2 card
    {{props.readonly ? 'o_myComponent_disabled' : ''}}
    card d-lg-block position-absolute {{props.active ?
    'o_myComponent_active' : ''}}  myComponent px-3"/>
    

To overcome the issue you may combine different approaches:

  * in Qweb attributes, only use classes to be toggled _on-the-fly_ ;

  * use new lines for each attribute;

  * order classes using the convention `[odoo component] [bootstrap component] [css declaration order]`.




Example
    
    
    <myComponent
       t-att-class="{
          o_myComponent_disabled: props.readonly,
          o_myComponent_active: props.active
       }"
       class="myComponent card position-absolute d-flex d-lg-block border px-3 px-lg-2"
    />
    

Vedi anche

[Odoo CSS properties order](../../contributing/development/coding_guidelines.html#contributing-coding-guidelines-scss-properties-order)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/scss_tips.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](javascript_field.html "Customize a field") |
  * [precedente](../howtos.html "How-to guides") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Write lean easy-to-maintain CSS


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