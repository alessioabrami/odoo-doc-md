# Valuation by lots/serial numbers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../warehouses_storage.html "Warehouses and storage") |
  * [precedente](landed_costs.html "Landed costs") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Valuation by lots/serial numbers



# Valuation by lots/serial numbers¶

Track [inventory valuation](using_inventory_valuation.html) by [lots or serial numbers](../product_tracking.html) to:

  1. Compare and differentiate purchasing cost, based on lot or serial numbers.

  2. Track the actual cost of manufactured products, based on the real cost of each tracked component used.

  3. Depreciate specific lot or serial numbers when they [sit in stock for too long](../../warehouses_storage/reporting/aging.html).




Importante

Please read this [introduction to inventory valuation](inventory_valuation_config.html) before setting up valuation by lot/serial numbers.

## Configurazione¶

To enable valuation by lots or serial numbers, begin by enabling the [Lots and Serial Numbers feature](../product_tracking.html). After that, go to Inventory app ‣ Products ‣ Products, and select the desired product, or create a new product, by clicking New.

On the product form, in the Category field, choose a product category. Ensure the product category’s [Costing Method](inventory_valuation_config.html#inventory-warehouses-storage-costing-methods) is set to _First In First Out (FIFO)_ or _Average Cost (AVCO)_.

Suggerimento

To check the costing method set on the product category, hover over the Category field, and click the __(Internal Link) icon.

Vedi anche

[Costing methods](inventory_valuation_config.html#inventory-warehouses-storage-costing-methods)

Next, activate the product to be tracked by lots or serial numbers by ticking the Track Inventory checkbox. Then, click the adjacent field that appears, and choose either By Lots or By Unique Serial Number from the resulting drop-down menu.

Doing so makes the Valuation by Lot/Serial number checkbox appear below it. Tick that checkbox, and the configuration to track valuation by lot or serial numbers is complete.

Product form showing the Valuation by Lot or Serial Number feature¶

## Valuation layers¶

To understand how valuation by lots and serial numbers works, consider these scenarios:

  1. Purchase and sell products: cost is calculated based on the _product category’s_ costing method.

  2. Create new lot/serial numbers using an inventory adjustment: value of the new lot/serial number is assigned to the cost from the product form.

  3. Inventory adjustment to update quantities for an existing lot/serial number: value is assigned based on the most recent cost for that lot/serial number.




For both AVCO and FIFO methods, the _Cost_ field on the product form is calculated using this formula:

\\(Avg~Cost = \frac{Total~Value}{Total~Qty}\\)

### Acquistare i prodotti¶

Consider how purchasing products affect the inventory valuation, in the table below.

| Quantità | Lot number | Matematica | Average cost on product form  
---|---|---|---|---  
Empty stock | 0.00 |  |  | 0 $  
Day 1: Receive one product at $10/unit | 1,00 | LOT 1 | \\(\frac{10}{1}\\) | 10 $  
Day 2: Receive another product at $20/unit | 1,00 | LOT 2 | \\(\frac{10+20}{2}\\) | $15  
  
As a result, the product form displays an average cost of $15 in the **Cost** field.¶

### Create new lot/serial number¶

Creating a new lot/serial number through an [inventory adjustment](../../warehouses_storage/inventory_management/count_products.html) assigns the same value as the cost on the product form.

To make an inventory adjustment, and assign a lot number, go to Inventory app ‣ Operations ‣ Physical Inventory. Then, click New.

In the new inventory adjustment line that appears, set the Product, create the Lot/Serial Number, set the Counted Quantity, and click __ Apply.

To view the valuation layer, go to Inventory app ‣ Reporting ‣ Valuation. The Total Value per unit matches the _Cost_ on the product form.

Example

Continuing the example in the table above, when the product cost is `$15`, the valuation for a newly-created `LOT3` is also be `$15`.

### Existing lot/serial number¶

When adjusting the quantity of an existing lot/serial number, the value is based on the most recent valuation layer for that specific lot/serial number.

Example

Continuing the example in the table above, the value for `LOT 1` is `$10`.

So, when the quantity is updated from `1.00` to `2.00`, the additional quantity is also valued at `$10`, reflecting the latest valuation layer for `LOT 1`.

The inventory adjustment (top line) is valued the same as LOT 1 (bottom line).¶

## View valuation¶

To find the average cost of a specific lot/serial number, go to Inventory app ‣ Products ‣ Lots/Serial Numbers, and select the desired record.

Both the Cost and Average Cost fields show a unit’s average cost. The Total Value reflects the total on-hand value for that lot/serial number.

Importante

Ensure the costing method is set to _First In First Out (FIFO)_ or _Average Cost (AVCO)_ to display the cost on this page.

Lot form, displaying **Cost** field. The **Valuation** smart button is in the top-right.¶

Valuation layers of a lot/serial number can be viewed through the valuation report, or by clicking the lot/serial number’s Valuation smart button. These detailed, line-by-line records can help determine how each inventory move of the specific lot/serial number affects its valuation.

### Valuation report¶

Display the valuation of lots and serial numbers in the database by going to Inventory app ‣ Reporting ‣ Valuation.

On the resulting Stock Valuation report, click the search bar, and in the __ Group By section of the resulting drop-down menu, select Lot/Serial number.

Suggerimento

Click the __(plus) icon to the right of a collapsed lot number line to [manually modify the cost](using_inventory_valuation.html#inventory-product-management-update-unit-price).

This is useful for adjusting individual lot prices when a purchase order or bill includes multiple lots/serial numbers, as initial prices are identical upon reception.

### Valuation smart button¶

To access a filtered part of the _Stock Valuation_ report, specific to a lot or serial number, go to Inventory app ‣ Products ‣ Lots/Serial Numbers, and select the desired item.

On the Lot/Serial Numbers page, click the Valuation smart button.

All stock moves that affect the valuation of `LOT 1`.¶

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/inventory_valuation/valuation_by_lots.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../warehouses_storage.html "Warehouses and storage") |
  * [precedente](landed_costs.html "Landed costs") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Valuation by lots/serial numbers


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
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
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
  *[AVCO]: Average Cost
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In First Out
  *[FEFO]: First Expired, First Out
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