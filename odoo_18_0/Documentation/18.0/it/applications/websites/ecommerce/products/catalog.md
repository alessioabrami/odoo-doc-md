# Catalogo — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](price_management.html "Price management") |
  * [precedente](../products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [E-commerce](../../ecommerce.html) »
  * [Prodotti](../products.html) »
  * Catalogo



# Catalogo¶

The eCommerce catalog is the equivalent of your physical store shelves: it allows customers to see what you have to offer. Clear categories, available options, sorting, and navigation threads help you structure it efficiently.

Suggerimento

Go to Website ‣ Configuration ‣ Settings, scroll down to the Privacy section to restrict Ecommerce Access to logged-in users and/or enable Shared Customer Accounts to allow access to all websites with a single account.

## Categorize the product catalog¶

In Odoo, there is a **specific category model** for your eCommerce. Using eCommerce categories for your products allows you to add a navigation menu on your eCommerce page. Visitors can then use it to view all products under the category they select.

To do so, go to Website ‣ eCommerce ‣ Products, select the product you wish to modify, click on the Sales tab, and select the Categories you want under eCommerce Shop.

Nota

A single product can appear under multiple eCommerce categories.

When your product’s categories are configured, go to your **main shop page** and click on Edit ‣ Customize tab. In the Categories option, you can either enable a menu on the Left, on the Top, or both. If you select the Left category, the option Collapsable Category Recursive appears and allows to render the Left category menu collapsable.

Vedi anche

[Prodotti](../products.html)

### Browsing¶

The eCommerce category is the first tool to organize and split your products. However, if you need an extra level of categorization in your catalog, you can activate various **filters** such as attributes or sort-by search.

#### Caratteristiche¶

Attributes refer to **characteristics** of a product, such as **color** or **material** , whereas variants are the different combinations of attributes. Attributes and Variants can be found under Website ‣ eCommerce ‣ Products, select your product, and Attributes & Variants tab.

Vedi anche

  * [Varianti prodotto](../../../sales/sales/products_prices/products/variants.html)




To enable **attribute filtering** , go to your **main shop page** , click on Edit ‣ Customize tab and select either Left, Top, or both. Additionally, you can also enable Price Filtering to enable price filters.

Nota

Price Filter works independently from **attributes** and, therefore, can be enabled on its own if desired.

Suggerimento

You can use **attribute filters** even if you do not work with product variants. When adding attributes to your products, make sure only to specify _one_ value per attribute. Odoo does not create variants if no combination is possible.

#### Sort-by search¶

It is possible to allow the user to manually **sort the catalog** using the search bar. From your **main shop page** , click on Edit ‣ Customize tab; you can enable or disable the Sort-By option as well as the Layout button. You can also select the Default Sort of the Sort-By button. The default sort applies to _all_ categories.

The **sorting** options are:

  * In evidenza

  * Nuovi arrivi

  * Nome (A-Z)

  * Prezzo - Basso verso Alto

  * Prezzo - alto a basso




In addition, you can **manually edit** the catalog’s order of a product by going to **the main shop page** and clicking on the product. Under the Product section of the Customize section, you can rearrange the order by clicking on the arrows. `<<` `>>` move the product to the **extreme** right or left, and `<` `>` move the product by **one** row to the right or left. It is also possible to change the catalog’s order of products in Website ‣ eCommerce ‣ Products and drag-and-dropping the products within the list.

## Page design¶

### Category page¶

You can customize the layout of the category page using the website builder.

Importante

Editing the layout of the category page is global; editing one category layout affects _all_ category pages.

To do so, go on to your Category page ‣ Edit ‣ Customize. Here, you can choose the layout, the number of columns to display the products, etc. The Product Description button makes the product description visible from the category page, underneath the product picture.

Suggerimento

You can choose the size of the grid, but be aware that displaying too many products may affect performance and page loading speed.

### Prodotto in evidenza¶

You can highlight products to make them more visible on the category or product page. On the page of your choice, go to Edit ‣ Customize and click on the product to highlight. In the Product section, you can choose the size of the product image by clicking on the grid, and you can also add a **ribbon** or Badge. This displays a banner across the product’s image, such as:

  * Sale;

  * Sold out;

  * Out of stock;

  * New.




Alternatively, you can activate the [developer mode](../../../general/developer_mode.html) on the **product’s template** , and under the Sales tab, change or create the ribbon from the Ribbon field.

Nota

The [developer mode](../../../general/developer_mode.html) is only intended for experienced users who wish to have access to advanced tools. Using the **developer mode** is _not_ recommended for regular users.

## Additional features¶

You can access and enable additional feature buttons such as **add to cart** , **comparison list** , or a **wishlist**. To do so, go to your **main shop page** , and at the end of the Products Page category, click on the feature buttons you wish to use. All three buttons appear when hovering the mouse over a product’s image.

  * Add to Cart: adds a button to [add the product to the cart](../cart.html);

  * Comparison List: adds a button to **compare** products based on their price, variant, etc.;

  * Wishlist Button: adds a button to **wishlist** the product.




## Add content¶

You can use **building blocks** to add content on the category page, with a variety of blocks ranging from Structure to Dynamic Content. Specific areas are defined to use blocks are defined and highlighted on the page when **dragging-and-dropping** a block.

  * If you drop a building block **on top** of the product list, it creates a new category header specific to _that_ category.

  * If you drop a building **on the top** or **bottom** of the page, it becomes visible on _all_ category pages.




Suggerimento

Adding content to an eCommerce category page is beneficial in terms of **SEO** strategy. Using **keywords** linked to the products or the eCommerce categories improves organic traffic. Additionally, each category has its own specific URL that can be pointed to and is indexed by search engines.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/ecommerce/products/catalog.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](price_management.html "Price management") |
  * [precedente](../products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [E-commerce](../../ecommerce.html) »
  * [Prodotti](../products.html) »
  * Catalogo


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
  *[EDI]: Electronic Data Exchange
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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions