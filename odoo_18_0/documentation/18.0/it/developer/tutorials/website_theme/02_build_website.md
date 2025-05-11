# Chapter 2 - Build your website — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [precedente](01_theming.html "Chapter 1 - Theming") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 2 - Build your website



# Chapter 2 - Build your website¶

## Create a page¶

Now that the theme has been set up, let’s move on to creating the content.

First of all, start by creating your first theme page: the home page. For now, only indicate “Hello” as content in the page.

Suggerimento

You will need to deactivate the default homepage.

Vedi anche

See reference documentation on how to [desactivate a default page](../../howtos/website_themes/pages.html#website-themes-pages-default) and how to [start a new page](../../howtos/website_themes/pages.html#website-themes-pages-theme-pages).

Solutions

`/website_airproof/__manifest__.py`¶
    
    
    'data': [
       # Pages
       'data/pages/home.xml',
    ]
    

`/website_airproof/data/pages/home.xml`¶
    
    
    <?xml version="1.0" encoding="utf-8"?>
    <odoo>
       <data noupdate="1">
          <!-- Deactivate default homepage -->
          <record id="website.homepage" model="ir.ui.view">
             <field name="active" eval="False"/>
          </record>
          <!-- Home -->
          <record id="page_home" model="website.page">
             <field name="name">Home</field>
             <field name="is_published" eval="True"/>
             <field name="key">website_airproof.page_home</field>
             <field name="url">/</field>
             <field name="type">qweb</field>
             <field name="arch" type="xml">
                <t t-name="website_airproof.page_home">
                   <t t-call="website.layout">
                      <!-- Title -->
                      <t t-set="additional_title">One step beyond the horizon | Airproof</t>
                      <!-- Content -->
                      <div id="wrap" class="oe_structure">
                         <p>Hello</p>
                      </div>
                   </t>
                </t>
             </field>
          </record>
       </data>
    </odoo>
    

## Add a media¶

If you want the client to be able to reuse certain pictures that you are going to add on the website, they must be added to the image library.

To do the test, declare the drone image to add it to the library. You will find the [drone picture here](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/img/content/drone-robin.png).

Vedi anche

See reference documentation on how to [add a media](../../howtos/website_themes/media.html#website-themes-media-images).

Go to the Website Builder, double-click on the logo, and you will see the drone image in the library.

Solutions

To complete this exercise, you need to:

  1. Put your PNG in the right image folder.

  2. Create your `images.xml` file. You can find all the necessary information in the [images.xml](https://github.com/odoo/tutorials/blob/18.0/website_airproof/data/images.xml) file from our example module.

  3. Declare your file in the `__manifest__.py`.




## Add building blocks¶

Now, let’s get into the real work. Start adding content to the pages.

In an Odoo website, we create the content of a page using building blocks. These can be compared to snippets editable by the user in the Website Builder. The standard main container for any snippet is a `section`.

Based on the Airproof design, add the following elements to the homepage :

  * Create a section with the 3 boxes using the Big boxes building block.

    * For this section, you don’t want the future user to be able to edit it via the Website Builder.

    * Put an opacity filter on the background image of the 3 boxes.

  * Create another section containing the title and icons.




You can use these [images](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/img/content) and [icons](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/img/content/icons).

Vedi anche

See reference documentation on how to [write standard snippets](../../howtos/website_themes/building_blocks.html#website-themes-building-blocks-layout).

Suggerimento

To determine the code needed to create your building blocks :

  * Create a test page via the website builder.

Drag & drop the building block that interests you and apply the right design.

Use the code generated via Editor HTML/SCSS in the menu.

  * You can also find the original building block code in Odoo : `odoo/addons/website/views/snippets/**.xml`.




Solutions

Find the solution in our Airproof example on [home.xml](https://github.com/odoo/tutorials/blob/18.0/website_airproof/data/pages/home.xml).

## Navigation¶

For now, the client is fine with the default header but has requested some navigation adjustments.

The client has requested the following changes:

  * Remove the link to the homepage and the shop.

  * Add a link to the future “About us” page.

  * Replace the default blog item with a dropdown to display the different blogs: “Our latest news” and “Tutorials”.

  * Add a mega-menu “Waterproof drones” to display the different products.




Vedi anche

  * You can find the original mega-menu templates code in Odoo : [odoo/addons/website/views/snippets/s_mega_menu_**.xml](https://github.com/odoo/odoo/blob/18.0/addons/website/views/snippets)

  * See reference documentation on how to modifiy the [Navigation](../../howtos/website_themes/navigation.html).




Suggerimento

  * Make sure the Blog app is installed and create the two different blogs in the backend.

  * Create the different products via the backend. You can use these [product pictures](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/img/content).




Solutions

Find the solution in our Airproof example on [menu.xml](https://github.com/odoo/tutorials/blob/18.0/website_airproof/data/menu.xml).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/tutorials/website_theme/02_build_website.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [precedente](01_theming.html "Chapter 1 - Theming") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 2 - Build your website


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