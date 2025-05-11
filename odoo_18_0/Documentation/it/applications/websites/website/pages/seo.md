# Search Engine Optimization (SEO) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../configuration.html "Configurazione") |
  * [precedente](menus.html "Menù") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Pagine](../pages.html) »
  * Search Engine Optimization (SEO)



# Search Engine Optimization (SEO)¶

Search Engine Optimization, often abbreviated as SEO, is a digital marketing strategy to improve a website’s visibility and ranking in search engine results (e.g., in Google). It involves optimizing various elements on your website, including its content, social sharing, URLs, images, and page speed.

Nota

  * Odoo provides several modules to help you build your website content, such as [eCommerce](../../ecommerce.html), [Blog](../../blog.html), [eLearning](../../elearning.html), and [Forum](../../forum.html).

  * All Odoo [themes](../web_design/themes.html) rely on the CSS Framework [Bootstrap](https://getbootstrap.com/) to render efficiently according to the device: desktop, tablet, or mobile, which positively impacts ranking in search engines.




## Content optimization¶

To optimize a webpage’s SEO, access the page, then go to Website ‣ Site ‣ Optimize SEO.

### Meta tags¶

Meta tags are HTML elements that provide information about a webpage to search engines and website visitors. They play a crucial role in SEO by helping search engines understand the content and context of a webpage and attract visitors with appealing content. There are two types of meta tags in Odoo:

  * Title tags specify a webpage’s title and are displayed as a clickable link in search engine results. They should be concise, descriptive, and relevant to the page’s content. You can update the title tag of your webpage or keep it empty to use the default value based on the page’s content.

  * Description tags summarize the webpage’s content, often displayed in search engine results below the title. They are used to encourage the user to visit the page. You can update the description tag of your webpage or keep it empty to use the default value based on the page’s content.




Nota

The Preview card displays how the title and description tags should appear in search results. It also includes the URL of your page.

### Parole chiave¶

Keywords are one of the main elements of SEO. A website that is well optimized for search engines speaks the same language as potential visitors, with keywords for SEO helping them to connect to your site.

You can enter the keywords you consider essential in the Keyword field and click ADD to see how they are used at different levels in your content (H1, H2, page title, page description, page content) and the related searches in Google. The tool also suggests relevant keywords to drive your web traffic. The more keywords are present on your webpage, the better.

Suggerimento

It is strongly recommended to only use one H1 title per page for SEO.

### Image for social share¶

When you share your page on social media, your logo image is selected, but you can upload any other image by clicking the upward arrow.

Nota

  * The Social Preview card displays how the page’s information would appear when shared.

  * If you change the title of a blog post or the name of a product, the changes apply automatically everywhere on your website. The old link still functions when external websites use a [301 redirect](../pages.html#website-url-redirection), maintaining the SEO link juice.




## Immagini¶

The size of images has a significant impact on page speed, which is an essential criterion for search engines to optimize SEO ranking.

Suggerimento

Compare how your website ranks using [Google Page Speed](https://pagespeed.web.dev/?utm_source=psi&utm_medium=redirect) or [Pingdom Website Speed Test](https://tools.pingdom.com/).

Odoo automatically compresses uploaded images and converts them to `Webp`. With this file format, photos are smaller, which increases the page loading speed and, therefore, gives a better ranking in SEO. All images used in Odoo official [themes](../web_design/themes.html) are also compressed by default. If you are using a third-party theme, it may provide images that are not compressed efficiently.

**To modify an image** from your website, select the image, click Edit, then go to the Customize tab, and adapt the Format in the Image section.

Importante

Alt tags are used to provide context to what an image is displaying, informing search engine crawlers and allowing them to index an image correctly. Adding alt tags keywords in the Description field is essential from an SEO perspective. This description is added to the HTML code of your image, and it is shown when the image cannot be displayed.

## Advanced features¶

### Structured data markup¶

Structured data markup is used to generate rich snippets in search engine results. It is a way for websites to send structured data to search engine robots, helping them understand your content and create well-presented search results.

By default, Google supports many [rich snippets](https://developers.google.com/search/blog/2009/05/introducing-rich-snippets) for content types, including Reviews, People, Products, Businesses, Events, and Organizations.

Microdata is a set of tags, introduced with HTML5, that help search engines better understand your content and display it in a relevant way. Odoo implements microdata as defined in the schema.org [specification](https://schema.org/docs/gs.html) for events, eCommerce products, forum posts, and contact addresses. This allows your product pages to be displayed in Google using extra information like the price and rating of a product:

### robots.txt¶

A robots.txt file tells search engine crawlers which URLs the crawler can access on your site, to index its content. This is used mainly to avoid overloading your site with requests.

When indexing your website, search engines take a first look at the robots.txt file. Odoo automatically creates one robot.txt file available on `mydatabase.odoo.com/robots.txt`.

By editing a robots.txt file, you can control which site pages are accessible to search engine crawlers. To add custom instructions to the file, go to Website ‣ Configuration ‣ Settings, scroll down to the SEO section, and click Edit robots.txt.

Example

If you do not want the robots to crawl the `/about-us` page of your site, you can edit the robots.txt file to add `Disallow: /about-us`.

### Mappa del sito¶

The sitemap points out website pages and their relation to each other to search engine robots. Odoo generates a `/sitemap.xml` file, including all URLs. For performance reasons, this file is cached and updated every 12 hours.

Nota

If your website has a lot of pages, Odoo automatically creates a Sitemap Index file, respecting the [sitemaps.org protocol](http://www.sitemaps.org/protocol.html), grouping sitemap URLs in 45000 chunks per file.

Every sitemap entry has three attributes that are computed automatically:

  * `<loc>`: the URL of a page.

  * `<lastmod>`: last modification date of the resource, computed automatically based on the related object. For a page related to a product, this could be the last modification date of the product or the page.

  * `<priority>`: modules may implement their priority algorithm based on their content (for example, a forum might assign a priority based on the number of votes on a specific post). The priority of a static page is defined by its priority field, which is normalized (16 is the default).




Suggerimento

To prevent pages from appearing in a sitemap, go to Site ‣ Properties, click the Publish tab, and turn off the Indexed feature.

> ### Hreflang HTML tags¶

Odoo automatically includes `hreflang` and `x-default` tags in the code of your website’s multilingual pages. These HTML attributes are crucial in informing search engines about a specific page’s language and geographical targeting.

Vedi anche

[Traduzioni](../configuration/translate.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/website/pages/seo.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../configuration.html "Configurazione") |
  * [precedente](menus.html "Menù") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Pagine](../pages.html) »
  * Search Engine Optimization (SEO)


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
  *[URL]: Uniform Resource Locators
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