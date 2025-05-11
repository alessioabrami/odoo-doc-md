# Product images with Google Images — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../prices.html "Manage your pricing") |
  * [precedente](variants.html "Varianti prodotto") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your products](../products.html) »
  * Product images with Google Images



# Product images with Google Images¶

Having appropriate product images in Odoo is useful for a number of reasons. However, if a lot of products need images, assigning them can become incredibly time-consuming.

Fortunately, by configuring the _Google Custom Search_ API within an Odoo database, finding product images for products (based on their barcode) is extremely efficient.

## Configurazione¶

In order to utilize _Google Custom Search_ within an Odoo database, both the database and the Google API must be properly configured.

Nota

Free Google accounts allow users to select up to 100 free images per day. If a higher amount is needed, a billing upgrade is required.

### Google API dashboard¶

  1. Go to the [Google Cloud Platform API & Services](https://console.developers.google.com/) page to generate Google Custom Search API credentials. Then, log in with a Google account. Next, agree to their Terms of Service by checking the box, and clicking Agree and Continue.

  2. From here, select (or create) an API project to store the credentials. Start by giving it a memorable Project Name, select a Location (if any), then click Create.

  3. With the Credentials option selected in the left sidebar, click Create Credentials, and select API key from the drop-down menu.

  4. Doing so reveals an API key created pop-up window, containing a custom API key. Copy and save Your API key in the pop-up window – it will be used later. Once the key is copied (and saved for later use), click Close to remove the pop-up window.

  5. On this page, search for `Custom Search API`, and select it.

  6. From the Custom Search API page, enable the API by clicking Enable.




### Google Programmable Search dashboard¶

  1. Next, go to [Google Programmable Search Engine](https://programmablesearchengine.google.com/), and click either of the Get started buttons. Log in with a Google account, if not already logged in.

  2. On the Create a new search engine form, fill out the name of the search engine, along with what the engine should search, and be sure to enable Image Search and SafeSearch.

  3. Validate the form by clicking Create.

  4. Doing so reveals a new page with the heading: Your new search engine has been created.

  5. From this page, click Customize to open the Overview ‣ Basic page. Then, copy the ID in the Search engine ID field. This ID is needed for the Odoo configuration.




### Odoo¶

  1. In the Odoo database, go to the Settings app and scroll to the Integrations section. From here, check the box beside Google Images. Then, click Save.

  2. Next, return to the Settings app, and scroll to the Integrations section. Then, enter the API Key and Search Engine ID in the fields beneath the Google Images feature.

  3. fai clic su Salva.




## Product images in Odoo with Google Custom Search API¶

Adding images to products in Odoo can be done on any product or product variant. This process can be completed in any Odoo application that provides access to product pages (e.g. _Sales_ app, _Inventory_ app, etc.).

Below is a step-by-step guide detailing how to utilize the _Google Custom Search API_ to assign images to products in Odoo using the Odoo _Sales_ application:

  1. Navigate to the Products page in the _Sales_ app (Sales app ‣ Products ‣ Products). Or, navigate to the Product Variants page in the _Sales_ app (Sales app ‣ Products ‣ Product Variants).

  2. Select the desired product that needs an image.

Nota

Only products (or product variants) that have a barcode, but **not** an image, are processed.

If a product with one or more variants is selected, each variant that matches the aforementioned criteria is processed.

  3. Click the Action ⚙️ (gear) icon on the product page, and select Get Pictures from Google Images from the menu that pops up.

  4. On the pop-up window that appears, click Get Pictures.

  5. Once clicked, the image(s) will appear incrementally.

Nota

Only the first 10 images are fetched immediately. If you selected more than 10, the rest are fetched as a background job.

The background job processes about 100 images in a minute. If the quota authorized by Google (either with a free or a paid plan) is reached, the background job puts itself on hold for 24 hours. Then, it will continue where it stopped the day before.




Vedi anche

[Create, modify, or close your Google Cloud Billing account](https://cloud.google.com/billing/docs/how-to/manage-billing-account)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/products_prices/products/product_images.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../prices.html "Manage your pricing") |
  * [precedente](variants.html "Varianti prodotto") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your products](../products.html) »
  * Product images with Google Images


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
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
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
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