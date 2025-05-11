# Prodotti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products/catalog.html "Catalogo") |
  * [precedente](../ecommerce.html "E-commerce") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Prodotti



# Prodotti¶

**Odoo eCommerce** allows you to add products and manage your product pages directly from the Website app. It also allows you to add product variants and digital files, translating the product page content, managing stock, and enabling product comparisons.

## Add products¶

### Create products¶

To create a product from the frontend, click \+ New in the top-right corner, then Product. Enter the Product Name, Sales Price, the default Customer Taxes for local transactions, and Save. You can then update the product’s details, add an image, and customize the product page. When you Save, the product page is automatically published.

Suggerimento

  * You can also create a product from the backend by going to Website ‣ eCommerce ‣ Products and clicking New.

  * Products created from the frontend are automatically [published](../website/pages.html#website-un-publish-page), while products created from the backend are not. To publish a product, click the Go to Website smart button to access the product page, then toggle the switch from Unpublished to Published.




Vedi anche

[Create new products using the Barcode Lookup database](../../general/integrations/barcodelookup.html).

### Import products¶

To [import product data](../../essentials/export_import_data.html#essentials-export-import-data-import-data) using XLSX or CSV files, go to Website ‣ eCommerce ‣ Products, click the __( gear) icon, then [Import records](../../essentials/export_import_data.html#essentials-export-import-data-import-data).

Suggerimento

To publish **large batches** of products, follow these steps:

  1. Go to Website ‣ eCommerce ‣ Products.

  2. Remove the Published filter and switch to the List view.

  3. Click the __( dropdown toggle) icon and enable Is published.

  4. Click the Is Published column to re-order it by **published** or **unpublished** products.

  5. Select the products to publish by ticking their box.

  6. In the Is Published column, tick the box for any of the selected products, then Confirm to publish them.




## Shop page¶

To customize the layout of the main Shop page or modify its content, click Edit. Go to the Blocks tab to add [building blocks](../website/web_design/building_blocks.html) or to the Customize tab to change the page layout or add features:

  * Layout: Select Grid or List.

>     * Size: Set the number of products displayed per page and line.
> 
>     * Style: Select Default, Cards, Thumbnails, or Grid.
> 
>     * Image Size: Choose the aspect ratio for the product images: Landscape (4/3), Default (1/1), Portrait (4/5), or Vertical (2/3). You can also adjust the display by changing the Fill options to best fit your design preferences.

  * Search Bar: Toggle the switch to display a search bar at the top of the products
    

page.

  * Prod. Desc.: Toggle the switch to display the product description below the product’s name.

  * Categories: display product categories on the Left, on the Top, or both. If Left is selected, you can enable Collapse Categories to make the category menu collapsible.

  * Datepicker: Toggle the switch to display a date range calendar to check the availability of rental products over a specific period. The [Rental app](../../sales/rental.html) must be installed to use this feature.

  * Attributes: Show product attributes on the Left and/or display a __( dropdown toggle) icon at the Top allowing customers to filter products based on their attributes.

    * Price Filter: Toggle the switch to display a Price Range bar, which allows customers to filter products according to a specific price range by dragging adjustable handles.

    * Product Tags: Toggle the switch to display the Product Template Tags on the product page and allow customers to filter products using those tags by going to the Tags section in the left column.

  * Top Bar: Select Sort By to display a dropdown list in the top bar for sorting products and/or Layout to allow customers to switch to the grid or list view using the related icons.

  * Default Sort: Choose how products are sorted by default: Featured, Newest Arrivals, Name (A-Z), Price - Low to High, or Price - High to Low.

  * Buttons:

    * Select the __( Shopping cart) option to display an __( Add to cart) icon on each product’s image, which takes the customer to the checkout page.




>   * Select the __( Wishlist) option to display an __( Add to wishlist) icon on each product’s image allowing logged-in customers to save products to a wishlist.
> 
>   * Select the __( Compare) option to display the __( Compare) icon on each product’s image allowing customers to compare products based on their attributes.
> 
> 


Suggerimento

To feature a product, go to the product form and click the __( Favorite) icon next to the product’s name.

## Product page¶

To access a product’s page, go to the Shop and click on the product. Click Edit to customize the page or edit its images.

To access the backend **product form** , click the __ Product button in the top-right corner of the product page. Alternatively, navigate to Website ‣ eCommerce ‣ Products and select the product. You can configure the product page from the form by adding variants, digital documents, or translating content.

Suggerimento

Click the Go to Website smart button to return to the frontend product’s page.

### Personalizzazione¶

To customize a product page, click Edit. Go to the Blocks tab to add [building blocks](../website/web_design/building_blocks.html).

Suggerimento

  * When dragging and dropping a building block on the product page, placing it above or below the top or bottom blue lines makes it visible on all product pages.

  * You can edit any text on your website simply by clicking on it while in Edit mode.




Go to the Customize tab to modify the page layout or add features:

  * Terms and Conditions: Toggle the switch to display a link to your [terms and conditions](../../finance/accounting/customer_invoices/terms_conditions.html) on the product page.

  * Customers:

>     * Rating: Allow logged-in portal users to submit product reviews by clicking the stars below the product’s name and sharing their experience in the Customer Reviews section at the bottom. Reviews are visible from the product page using the __( plus) icon next to the Customer Reviews heading or from the product form’s chatter. To restrict visibility to internal employees, toggle the Public switch next to the review comment.
> 
>     * Share: Add social media and email icon buttons allowing customers to share the product through those channels.

  * Select Quantity: Toggle the switch to allow customers to select the product quantity they want to purchase.

  * Tax indication: Toggle the switch to indicate if the price is [VAT included or excluded](products/price_management.html#ecommerce-price-management-tax-display).

  * Variants: Show all possible product variants vertically as a Products List or horizontally as selectable Options to compose the variant yourself.

  * Product Tags: Toggle the switch to display the Product Template Tags on the product page and allow customers to filter products using those tags.

  * Cart:

>     * Buy Now: Add a __ Buy Now option to take the customer to the checkout page.
> 
>     * Wishlist: Add an __ Add to wishlist option allowing logged-in customers to save products in a wishlist.
> 
>     * Compare: Add a __ Compare option, allowing customers to compare products based on their attributes.

  * Specification: Select Bottom of Page to display a detailed list of the attributes and their values available for the product. This option only works for products with variants if the Product comparison tool is enabled in the Website Settings.




Nota

  * Variants, __ Wishlist, and __ Compare options must be enabled by going to Website ‣ Configuration ‣ Settings, in the Shop - Products section.

  * Enabled functions apply to all product pages.

  * Products with single values for their attributes do not generate variants but are still displayed in the Product Specifications.




### Image customization¶

To customize the images available on the product page, go to the Customize tab:

  * Images Width: Changes the width of the product images displayed on the page.

  * Layout: The Carousel layout allows customers to navigate from one image to the next using the __( left arrow) or __( right arrow); whereas the Grid displays four images in a square layout.

  * Image Zoom: Select the zoom effect for product images: Magnifier on hover Pop-up on Click, Both, or None.

  * Thumbnails: Align thumbnails on the __( Left) or
    

at the __( Bottom).

  * Main Image: Click Replace to change the product’s main image.

  * Extra Images: Add extra images or videos (including via URL) or Remove all product images.




Nota

Images must be in PNG or JPG format and with a minimum size of 1024x1024 to trigger the zoom.

## Varianti prodotto¶

[Product variants](../../sales/sales/products_prices/products/variants.html) are different versions of the same product, such as various colors or materials, with potential differences in price and availability.

To configure product variants for a product:

  1. Go to Website ‣ Configuration ‣ Settings.

  2. Scroll down to the Shop - Products section and enable the Product Variants feature.

  3. Access the product forms and go to the Attributes & Variants tab, where you can add attributes and values, allowing customers to configure and select product variants on the product page. For multiple attributes, you can combine them to create specific variants.




To display or hide an attribute on the Shop page and allow visitors to filter them, go to Website ‣ eCommerce ‣ Attributes, click on the attribute, and select Visible or Hidden in the eCommerce Filter Visibility field.

Suggerimento

  * To display the product attributes on the main Shop page, set the Attributes feature to Left using the website editor.

  * To group attributes under the same section when comparing products, go to the eCommerce Category field and either select an existing category or create a new one.




Nota

Two attribute values are needed to make the filter visible.

Vedi anche

[Product variants](../../sales/sales/products_prices/products/variants.html)

## Digital files¶

You can link digital files like certificates, eBooks, or user manuals to the products. These documents are available before payment on the product page or in the customer portal after checkout.

To link a digital file to a product, go to the product form and click the Documents smart button. Then, click Upload to upload a file directly, or for additional options, click New, then Upload your file.

Suggerimento

  * You can link a URL instead of a digital file. To do so, click New, go to the Type field, and select URL.

  * To edit an existing file, click the __( dropdown menu) in the top-right corner of the document card and click Edit.




### Digital files available before payment¶

To make the file available on the product page (before payment), leave the Visibility field blank and toggle the Show on product page switch.

### Digital files available after payment¶

To make the file available (after payment), set the Visibility field to Confirmed order and turn off the Show on product page switch.

## Translation¶

If multiple languages are available on your website, you can translate a product’s information directly on the product form. Fields that support multiple languages are identifiable by their abbreviation language (e.g., EN) next to their field.

The eCommerce-related fields to translate are:

  * Product name.

  * Out-of-Stock Message (under the Sales tab).

  * Sales Description (under the Sales tab).




Nota

  * Having untranslated content on a web page may be detrimental to the user experience and [SEO](../website/pages/seo.html). You can use the [Translate](../website/configuration/translate.html) feature to translate the page’s content.

  * To check the language(s) of your website, go to Website ‣ Configuration ‣ Settings and go to the Website Info section.




### Website availability¶

To set the product’s website availability, navigate to the product form, go to the Sales tab, and in the eCommerce shop section, select the Website you wish the product to be available on. Leave the field blank to make the product available on _all_ websites.

Nota

You can make a product available on either _one_ website or _all_ websites, but selecting only _some_ websites is not possible.

## Stock management¶

To enable and configure inventory management options, go to Website ‣ Configuration ‣ Settings, scroll down to the Shop - Products section and the Inventory Defaults sub-section.

Importante

  * The **Inventory** app must be installed to see the inventory management options.

  * To display the stock level on the product page, the Product Type field must be set to Storable in the product form.




### Magazzino¶

In the Inventory Defaults sub-section, fill in those fields:

  * [Warehouse](../../inventory_and_mrp/inventory/warehouses_storage/inventory_management/warehouses.html).

  * Out-of-Stock: Enable Continue Selling to allow customers to place orders even when the product is **out of stock**. Leave the box unchecked to **prevent orders**.

  * Show Available Qty: Displays the available quantity left under a specified threshold on the product page. The available quantity is calculated based on the On hand quantity minus the quantity already reserved for outgoing transfers.




## Product comparison¶

To allow website visitors to compare products based on their attributes, go to Website ‣ Configuration ‣ Settings, scroll down to the Shop - Products section, and enable Product Comparison Tool.

The __( Compare) icon is now available on each product card on the main shop page when customers hover their mouse over it. To compare products, customers can click the __( Compare) option on the products they want to compare, then click __ Compare in the pop-up window at the bottom of the page to reach the comparison summary.

Nota

  * The Product Comparison Tool is only available for products with attributes.

  * Selecting the __( Compare) option from a product page is also possible.




  * [Catalogo](products/catalog.html)
  * [Price management](products/price_management.html)
  * [Cross-selling and upselling](products/cross_upselling.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/ecommerce/products.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products/catalog.html "Catalogo") |
  * [precedente](../ecommerce.html "E-commerce") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Prodotti


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