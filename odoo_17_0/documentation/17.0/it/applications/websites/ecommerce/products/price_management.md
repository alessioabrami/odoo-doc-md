# Price management — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_upselling.html "Cross-selling and upselling") |
  * [precedente](catalog.html "Catalogo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [E-commerce](../../ecommerce.html) »
  * [Prodotti](../products.html) »
  * Price management



# Price management¶

Odoo offers multiple options to select the price displayed on your website, as well as condition-specific prices based on set criteria.

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

This setting is **global** , and the tax-display type is the same for (all of) your website(s). It is, therefore, not possible to select different tax displays for different websites. This may be a significant point of consideration when implementing a database with multiple ecommerce websites aimed at varying customer types (i.e., B2B and B2C).

You can choose to display the type of pricing next to the product price by going to Website ‣ Site ‣ Homepage ‣ Shop, selecting a product, and then Edit ‣ Customize tab and enabling Tax Indication.

Vedi anche

[Tariffe B2B (imposte escluse) e B2C (imposte incluse)](../../../finance/accounting/taxes/B2B_B2C.html)

## Price per unit¶

It is possible to display a [price per unit](../../../inventory_and_mrp/inventory/product_management/configure/uom.html) on the product page. To do that, go to Website ‣ Configuration ‣ Settings and enable Product Reference Price under the Shop - Products section. When enabled, ensure an amount is set in the Base Unit Count field of the **product template** , and in the Sales Price.

The price per unit of measure can be found above the Add to Cart button on the product page.

Nota

Pay attention that having the price per unit may be **mandatory** in some countries.

Vedi anche

[Unità di misura](../../../inventory_and_mrp/inventory/product_management/configure/uom.html)

### Price configuration: pricelists¶

Pricelists are the primary tool to manage prices on your eCommerce. They allow you to define website-specific prices - different from the price on the product template - based on the **country group** , **currency** , **minimum quantity** , **period** , or **variant**. You can create as many pricelists as needed, but it is mandatory to have at least one pricelist configured per website. If no custom pricelists are added, Odoo defaults to the **Public Pricelist** for all websites.

Vedi anche

[Pricelists, discounts, and formulas](../../../sales/sales/products_prices/prices/pricing.html)

#### Configurazione¶

Pricelists can be found under Website ‣ eCommerce ‣ Pricelists, but must first be activated. For that, head to Website ‣ Configuration ‣ Settings and scroll down to the Shop - Products section. There, you can find two options:

  * Multiple prices per product;

  * Advanced price rules (discounts, formulas).




The **first** option allows you to set different prices per customer _segment_ , i.e., registered customers, gold customers, regular customers, etc. The **second** option allows you to set _price change_ rules such as **discounts** , **margins** , **roundings** , etc.

#### Foreign currency¶

If you are selling in **multiple currencies** and have pricelists in foreign currencies, customers can select their corresponding pricelist anywhere on the Shop page from the drop-down menu next to the **search bar**.

Vedi anche

  * [Pricelists, discounts, and formulas](../../../sales/sales/products_prices/prices/pricing.html)

  * [Foreign currencies](../../../sales/sales/products_prices/prices/currencies.html)




### Permanent discount¶

If you have permanently reduced the price of a product, a popular means to attract customers is the **strikethrough** strategy. The strategy consists in displaying the previous price crossed out and the **new discounted price** next to it.

To display a “striked” price, enable the Comparison Price option under Website ‣ Configuration ‣ Settings ‣ Shop - Products category. Then, head to the product’s template (Website ‣ eCommerce ‣ Products), and in the Compare to Price field, enter the **new** price.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/ecommerce/products/price_management.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_upselling.html "Cross-selling and upselling") |
  * [precedente](catalog.html "Catalogo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
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
  *[CSV]: Valori separati da virgola
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement