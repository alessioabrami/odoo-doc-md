# Price management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_upselling.html "Cross-selling and upselling") |
  * [precedente](catalog.html "Catalogo") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [E-commerce](../../ecommerce.html) »
  * [Prodotti](../products.html) »
  * Price management



# Price management¶

Odoo offers multiple options to select the prices displayed on a website, as well as condition-specific prices based on set criteria.

## Imposte¶

### Tax configuration¶

To add a tax on a product, you can either set a tax in the Customer Taxes field of the **product template** or use [fiscal positions](../../../finance/accounting/taxes/fiscal_positions.html).

Vedi anche

  * [Imposte](../../../finance/accounting/taxes.html)

  * [Integrazione AvaTax](../../../finance/accounting/taxes/avatax.html)

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../../../finance/accounting/taxes/fiscal_positions.html)




### Tax display¶

Choosing the displayed price tax usually depends on a country’s regulations or the type of customers **(B2B vs. B2C)**. To select the type of price displayed, go to Website ‣ Configuration ‣ Settings, scroll down to the Shop - Products category, and select Tax Excluded or Tax Included.

  * Tax Excluded: the price displayed on the website is **tax-excluded** , and the tax is computed at the cart-review step;

  * Tax Included: the price displayed on the website is **tax-included**.




Nota

This setting is website specific, and therefore can be altered for each website within a database.

To display the type of pricing next to the product price, navigate to Website ‣ Site ‣ Homepage ‣ Shop, select a product, then click Edit and, in the Customize tab, enable Tax Indication.

Vedi anche

[Tariffe B2B (imposte escluse) e B2C (imposte incluse)](../../../finance/accounting/taxes/B2B_B2C.html)

## Price per unit¶

It is possible to display a [price per unit](../../../inventory_and_mrp/inventory/product_management/configure/uom.html) on the product page. To do that, go to Website ‣ Configuration ‣ Settings and enable Product Reference Price under the Shop - Products section. When enabled, ensure an amount is set in the Base Unit Count field of the product template, and in the Sales Price field.

The price per unit of measure can be found above the Add to Cart button on the product page.

Nota

Pay attention that having the price per unit may be **mandatory** in some countries.

Vedi anche

[Unità di misura](../../../inventory_and_mrp/inventory/product_management/configure/uom.html)

## Listini prezzi¶

Pricelists are the primary tool to manage prices on an eCommerce website. They make it possible to define website-specific prices - different from the price on the product template - based on the country group, currency, minimum quantity, period, or variant.

Vedi anche

[Listini prezzi](../../../sales/sales/products_prices/prices/pricing.html)

### Understanding default pricelists¶

The concept of a default pricelist in Odoo depends on the application being used. In the **Sales** app, a customer’s default pricelist is determined by their contact profile. If a pricelist is manually assigned to a contact, the pricelist becomes their default. If no pricelist is assigned, the default is the first pricelist listed.

In the **eCommerce** app,the default pricelist is assigned at the website level. However, it is influenced by the user’s login status and country group settings.

### How pricelists are applied in eCommerce¶

If a portal user has a specific pricelist assigned to their contact profile, that pricelist is applied to their purchase. However, if that pricelist is **not** assigned to the website they are visiting, the user sees the website’s default pricelist.

Nota

The default website pricelist is the first available pricelist assigned to a website, without the country group setting configured.

Public, non-logged in users, see the website’s default pricelist.

If a pricelist includes a country group, Odoo checks the visitor’s IP address and applies the corresponding pricelist. If a visitor has a pricelist assigned in their contact profile, that pricelist takes precedence over the country-based pricelist, unless the assigned pricelist has a different country group.

Example

A customer from the United States visits the website. They do not have a portal account. The United States pricelist is applied.

A different visitor, also from the United States, has the Loyal Customer Discount pricelist assigned in their contact record. This assignment takes precedence over the country group assignation, so the Loyal Customer Discount is applied.

### Pricelist configuration¶

To activate pricelists, navigate to Website ‣ Configuration ‣ Settings, scroll down to the Shop - Products section, enable the Pricelist feature, then click Save. Once pricelists have been activated, go to Website ‣ eCommerce ‣ Pricelists to configure them.

#### Preventing sales if price is zero¶

The Prevent Sale of Zero Priced Product feature prevents customers from purchasing a product if the sales price is listed as `0`. When this feature is enabled, instead of seeing Add to Cart when attempting to purchase a product, they see Contact Us. This feature is useful for companies that want to hide the prices of their products.

To utilize this feature, first navigate to Website ‣ Configuration ‣ Settings and tick the Prevent Sale of Zero Priced Product checkbox, then click Save.

Next, create a pricelist that sets all product prices to `0`. Ensure the pricelist is assigned to the correct website and is listed first among the website’s pricelists.

#### Selectable pricelists¶

_Selectable pricelists_ appear in the shop page’s pricelist drop-down menu. When a pricelist is designated as Selectable, it allows the customer to choose between available pricelists.

Importante

If a pricelist is designated as Selectable, and is not assigned to a specific website, then the pricelist is selectable on **all** websites.

If a pricelist is designated as Selectable, it appears in the drop-down menu next to the search bar. However, if a pricelist does _not_ appear in the drop-down menu, it may be for one of the following reasons:

  * If there is only one selectable pricelist, and the contact is assigned a pricelist, the drop-down may not appear.

  * If multiple selectable pricelists exist and match a visitor’s country group, only those pricelists are shown in the drop-down.




### Foreign currency¶

If you are selling in **multiple currencies** and have pricelists in foreign currencies, customers can select their corresponding pricelist anywhere on the Shop page from the drop-down menu next to the search bar.

Vedi anche

  * [Listini prezzi](../../../sales/sales/products_prices/prices/pricing.html)

  * [Foreign currencies](../../../sales/sales/products_prices/prices/currencies.html)




## Permanent discount¶

If you have permanently reduced the price of a product, a popular means to attract customers is the **strikethrough** strategy. The strategy consists in displaying the previous price crossed out and the **new discounted price** next to it.

To display a “striked” price, enable the Comparison Price option under Website ‣ Configuration ‣ Settings ‣ Shop - Products category. Then, head to the product’s template (Website ‣ eCommerce ‣ Products), and in the Compare to Price field, enter the **new** price.

Nota

If a pricelist contains a [Discount](../../../sales/sales/products_prices/prices/pricing.html#sales-products-price-rules) price type, the striked price is visible to applicable customers. This is true even if the Comparison Price feature has not been enabled.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/ecommerce/products/price_management.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_upselling.html "Cross-selling and upselling") |
  * [precedente](catalog.html "Catalogo") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [E-commerce](../../ecommerce.html) »
  * [Prodotti](../products.html) »
  * Price management


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