# Purchase Analysis report — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_costs_report.html "Vendor costs report") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Avanzato](../advanced.html) »
  * Purchase Analysis report



# Purchase Analysis report¶

The _Purchase Analysis_ report provides statistics about products purchased using Odoo’s **Purchase** app. This data is useful for gaining a deeper understanding of key metrics related to purchase orders (POs), including the quantity of products ordered and received, the amount of time it takes to receive purchased products, and more.

To open the Purchase Analysis report, navigate to Purchase app ‣ Reporting ‣ Purchase.

Importante

The Purchase Analysis report is one of many reports available across the Odoo app suite. This documentation only covers the measures specific to the Purchase Analysis report, along with a few use case examples.

For a full overview of the basic features available in most Odoo reports, see the documentation on [reporting essentials](../../../essentials/reporting.html).

## Misure¶

_Measures_ refer to the various datasets that can be displayed on the Purchase Analysis report, with each dataset representing a key statistic about POs or products. To choose a measure, click the Measures __button, and select one of the options from the drop-down menu:

  * # of Lines: The number of PO order lines, across all POs.

  * Average Cost: The average cost of POs.

  * Days to Confirm: The number of days it takes to confirm a PO.

  * Days to Receive: The number of days it takes to receive the products in a PO.

  * Gross Weight: The total weight of purchased products.

  * Qty Billed: The quantity of a product (or products) for which the vendor has already been billed.

  * Qty Ordered: The quantity of a product (or products) ordered.

  * Qty Received: The quantity of an ordered product (or products) received.

  * Qty to be Billed: The quantity of an ordered product (or products) for which the vendor has yet to be billed.

  * Total: The total amount spent, including tax.

  * Untaxed Total: The total amount spent, excluding tax. This measure is selected by default.

  * Volume: The total volume of ordered products, for products which are measured by volume.

  * Count: The total count of POs.




Suggerimento

Only one measure can be selected at a time when one of the __(graph view) options is enabled. However, multiple measures, and varying group-by criteria (on the x and y axes), can be selected when using the __(pivot table).

## Use case: determine days to receive products from each vendor¶

One possible use case for the Purchase Analysis report is determining how long each vendor takes to deliver purchased items. This allows companies to make better informed decisions about which vendors they want to purchase from.

Example

A local bike shop, _Bike Haus_ , sells high-quality unicycles, bicycles, tricycles, and all the accessories needed to ride and maintain them. They purchase their inventory from a few different vendors, and then sell those products on to customers through their storefront.

Recently, Bike Haus has decided to have their purchasing manager, David, look into how long it has taken each of their vendors to deliver the items they’ve purchased during the current year, 2024.

David starts by navigating to Purchase app ‣ Reporting ‣ Purchase, and selecting the __(bar chart) graph type at the top of the report.

Next, he clicks the __(toggle) button on the right of the search bar to open its drop-down menu. In the Confirmation Date filter section, he makes sure that **only** the 2024 filter is enabled. Then, he selects the Vendor option in the Group By section, before clicking away from the drop-down menu to close it.

Finally, David clicks on the Measures __drop-down menu, and selects the Days to Receive option.

With all of these options enabled, the Purchase Analysis report shows a bar chart, with one bar for each vendor, representing the average number of days it takes to receive products purchased from the vendor.

Using this data, David can see that it takes Bike Friends over 4.5 days, on average, to deliver purchased products. This is more than four times the amount of time it takes any other vendor.

Based on these findings, David makes the decision to reduce the quantity of products purchased from Bike Friends.

## Use case: compare vendor POs for two time periods¶

Another use for the Purchase Analysis report is to compare key statistics about POs for two different time periods, for a specific vendor. By doing so, it is easy to understand how purchases from the vendor have increased or decreased.

Example

Following the previous example, it has been one month since Bike Haus decided to reduce the quantity of products purchased from Bike Friends, one of their retailers. Bike Haus” purchasing manager, David, wants to understand the impact this decision has had on the amount of money they have spent on Bike Friends products.

David starts by navigating to Purchase app ‣ Reporting ‣ Purchase. Then, he selects the __(pivot table) option at the top of the screen.

In the search bar, he types `Bike Friends`, and clicks Enter, so the report only shows data for purchases from Bike Friends.

Then, David clicks the __(toggle) button on the right of the search bar to open its drop-down menu. In the Confirmation Date field, he leaves the June and 2024 filters enabled. He also selects Confirmation Date: Previous Period in the Comparison section, before clicking away from the drop-down menu to close it.

Next, David clicks on the Measures __drop-down menu. He leaves the Total and Untaxed Total datasets enabled, and disables the Order and Count datasets.

Finally, David clicks the __ Total button above the rows on the pivot table, and selects the Product option.

With all of these options configured, the Purchase Analysis report shows a pivot table comparing purchase data for the current month, June, with the previous month, May.

The pivot table is broken down into two main columns: one for the untaxed total spent, and one for the taxed total spent. These columns are further broken down into three smaller columns: the amount spent in May, the amount spent in June, and the variation between the two months, represented as a percentage.

On the left side of the pivot table, one row is shown for each product purchased from Bike Friends during June. Using this report, David is able to see that Bike Haus has spent much less money on products purchased from Bike Friends, compared to the previous month.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/purchase/advanced/analyze.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_costs_report.html "Vendor costs report") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Avanzato](../advanced.html) »
  * Purchase Analysis report


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: manufacturing order
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
  *[SO]: Sales Order
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
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: purchase order
  *[MTO]: Make to Order
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
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