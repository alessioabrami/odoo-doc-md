# Chapter 1 - Theming — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](02_build_website.html "Chapter 2 - Build your website") |
  * [precedente](../website_theme.html "Build a website theme") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 1 - Theming



# Chapter 1 - Theming¶

Now that you have Odoo installed and your server is running locally, it’s time to create your own theme module for your website.

## Setup¶

The first step is to ensure that Odoo is running correctly locally. To do this, use a Shell script to run the server.

In this script, define the database name and install only the `website` module.

Vedi anche

See reference documentation on how to [run Odoo](../../howtos/website_themes/setup.html#website-themes-setup-getting-started).

## Build your module structure¶

Now that we know everything is working properly, let’s start building our module.

Based on the following structure, start creating your module that will be used as a theme. This is where you are going to add your XML pages, SCSS, JS, …

Vedi anche

See reference documentation on how to structure your [Theme module](../../howtos/website_themes/theming.html#theming-module).

Start with the basics : `/data`, `/img`, `/scss`, `/js`.

Don’t forget to add the `__init__.py` and `__manifest__.py` files.

In your `__manifest__.py` file, you can declare your module with the following information:

  * name (required)

  * description

  * category

  * version

  * author

  * license

  * depends




## Declare Odoo variables¶

In the `primary_variables.scss` file, you can override the default Odoo SCSS variables to match your design.

Based on the Airproof design, create your `primary_variables.scss` file and define the following elements:

  * Headings font family : Space Grotesk

  * Content font family : Lato

  * The color palette name and the 5 main colors that compose it: `#000000`, `#BBE1FA`, `#CEF8A1`, `#FFFFFF`, `#0B8EE6`

  * Header & Footer : Use one of the default templates for the moment, we will create a custom header later.




Vedi anche

See reference documentation on how to use [primary variables](../../howtos/website_themes/theming.html#theming-module-variables), as well as a list of all [primary variables](https://github.com/odoo/odoo/blob/18.0/addons/website/static/src/scss/primary_variables.scss) available.

Restart your script to immediately see the application of your changes.

Don’t forget to add the path to your manifest in the script and set your module as the app to install.

To ensure your changes are applied correctly, log in to your website and check that your color palette includes your specified colors.

Suggerimento

You will need to override more variables to replicate the Airproof design. Remember to add them throughout the creation of your website.

Nota

The font families are from [Google fonts](https://fonts.google.com/).

Solutions

To complete this exercise, you need to:

  1. Create your `primary_variables.scss` file. You can find all the necessary information in the [primary_variables.scss](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/scss/primary_variables.scss) file from our example module.

  2. Declare your file in the `__manifest__.py` as indicated in the documentation.

  3. Install your module via your script. In our example, it looks like this:



    
    
    ./odoo-bin --addons-path=../enterprise,addons,../myprojects --db-filter=theming -d theming
    --without-demo=all -i website_airproof --dev=xml
    

## Declare Bootstrap variables¶

On top of the default Odoo variables, you can also redefine the Bootstrap variables. Bootstrap is a front-end framework which is included by default in Odoo.

Based on the Airproof design, define the following elements:

  * Headings font sizes :

    * h1 : 3.125rem

    * h2 : 2.5rem

    * h3 : 2rem

    * h4 : 1.75rem

    * h5 : 1.5rem

    * h6 : 1.25rem

  * Inputs border radius : 10px

  * Inputs border color : black

  * Inputs border width : 1px

  * Large buttons border radius : 0px 10px 10px 10px




Vedi anche

  * See reference documentation on how to use [Bootstrap variables](../../howtos/website_themes/theming.html#theming-module-bootstrap).

  * A list of all [Bootstrap variables](https://github.com/odoo/odoo/blob/18.0/addons/web/static/lib/bootstrap/scss/_variables.scss) used by Odoo.

  * And [Bootstrap framework](https://getbootstrap.com/docs/4.6/getting-started/introduction/) official documentation.




Suggerimento

  * You will need to override more variables to replicate the Airproof design. Remember to add them throughout the creation of your website.

  * Make it a habit to regularly check locally that your changes have been successfully applied and have not caused any errors.




Solutions

To complete this exercise, you need to:

  1. Create your `bootstrap_overridden.scss` file. You can find all the necessary information in the [bootstrap_overridden.scss](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/scss/bootstrap_overridden.scss) file from our example module.

  2. Declare your file in the `__manifest__.py` as indicated in the documentation.




## Define presets¶

In addition to the variables we have just covered, you can also activate specific views to modify the design.

Add your `presets.xml` file and based on the Airproof design, activate the appropriate views to meet the following client requests:

  * Deactivate the Call-to-action in the header.

  * Deactivate the wishlist feature in the shop but activate it on the product page.

  * On the shop page, activate the filtering by categories only on the left side.




Vedi anche

See how you can define your [presets](../../howtos/website_themes/theming.html#theming-module-views-presets).

To start writing your file, follow the instructions for any Odoo XML page described in [Layout](../../howtos/website_themes/layout.html).

Suggerimento

  * To complete the exercise, you need to install the **eCommerce** (`website_sale`) and **wishlist** (`website_sale_whishlist`) applications. **Be careful!** Referencing an application in your code that hasn’t been installed will result in an error.

  * In order to find the templates to activate or not, go to the source code: `odoo/addons/website/views/**`.

For example, you can find all the templates for the header in [website_templates.xml](https://github.com/odoo/odoo/blob/18.0/addons/website/views/website_templates.xml).

  * To see the effect of your presets, add some **products** (_Airproof Mini_ , _Airproof Robin_ , _Warranty_ , _Charger cable_) and create **eCommerce categories** (_Warranties_ , _Accessories_ , and _Drones_ with _Camera drones_ and _Waterproof drones_) in the database. You will find the [product images here](https://github.com/odoo/tutorials/blob/18.0/website_airproof/static/src/img/content).

  * You will need to activate more views to replicate the Airproof design. Remember to add them throughout the creation of your website.




Solutions

To deactivate the Call-to-action:

  1. The view you have to find is in `odoo/addons/website/views/website_templates.xml l:2113`

  2. Create your `presets.xml` file with the right records

`/website_airproof/data/presets.xml`¶
         
         <?xml version="1.0" encoding="utf-8"?>
         <odoo>
            <!-- Disable Call-to-action in header -->
            <record id="website.header_call_to_action" model="ir.ui.view">
               <field name="active" eval="False"/>
            </record>
         </odoo>
         

  3. In the manifest, add the 2 apps and declare your file.

`/website_airproof/__manifest__.py`¶
         
         'depends': ['website_sale', 'website_sale_wishlist'],
         'data': [
            # Options
            'data/presets.xml',
         ]
         




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/tutorials/website_theme/01_theming.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](02_build_website.html "Chapter 2 - Build your website") |
  * [precedente](../website_theme.html "Build a website theme") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 1 - Theming


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