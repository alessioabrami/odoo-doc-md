# GS1 barcode usage — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../quality.html "Qualità") |
  * [precedente](gs1_nomenclature.html "GS1 barcode nomenclature") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * GS1 barcode usage



# GS1 barcode usage¶

GS1 barcodes provide a standardized format that barcode scanners can interpret. They encode information in a [specific structure recognized globally](gs1_nomenclature.html#barcode-operations-gs1), allowing scanners to understand and process supply chain data consistently.

Odoo _Barcode_ interprets and prints GS1 barcodes, automating product identification and tracking in warehouse operations such as receiving, picking, and shipping.

The following sections contain examples of how Odoo uses GS1 barcodes provided by the business to identify common warehouse items and automate certain warehouse workflows.

Importante

Odoo **does not** create GS1 barcodes. Businesses must purchase a unique Global Trade Item Number (GTIN) from GS1. Then, they can combine their existing GS1 barcodes with product and supply chain information (also provided by GS1) to create barcodes in Odoo.

Vedi anche

  * [Purchase GTINs](https://www.gs1.org/standards/get-barcodes)

  * [GS1 nomenclature](gs1_nomenclature.html#barcode-operations-gs1)




## Configure barcodes for product, quantity, and lots¶

To build a GS1 barcode that contains information about a product, its quantities, and the lot number, the following barcode patterns and Application Identifiers (A.I.) are used:

Nome | Nome regola | A.I. | Modello codice | Field in Odoo  
---|---|---|---|---  
Prodotto | Global Trade Item Number (GTIN) | 01 | (01)(\d{14}) | Barcode field on product form  
Quantità | Variable count of items | 30 | (30)(\d{0,8}) | Units field on transfer form  
Numero lotto | Batch or lot number | 10 | (10)([!»%-/0-9:-?A-Z_a-z]{0,20}) | Lot on Detailed Operations pop-up  
  
### Configurazione¶

First, [enable product tracking using lots](../../inventory/product_management/product_tracking/lots.html#inventory-management-track-products-by-lots) by navigating to Inventory app ‣ Configuration ‣ Settings, and checking the box for Lots & Serial Numbers under the Traceability heading.

Then, set up the product barcode by navigating to the intended product form in Inventory app ‣ Products ‣ Products and selecting the product. On the product form, click Edit. Then, in the General Information tab, fill in the Barcode field with the unique 14-digit [Global Trade Item Number (GTIN)](https://www.gs1.org/standards/get-barcodes), which is a universally recognized identifying number that is provided by GS1.

Importante

On the product form, omit the A.I. `01` for GTIN product barcode pattern, as it is only used to encode multiple barcodes into a single barcode that contains detailed information about the package contents.

Example

To record the GS1 barcode for the product, `Fuji Apple`, enter the 14-digit GTIN `20611628936004` in the Barcode field on the product form.

Suggerimento

To view a list of _all_ products and their corresponding barcodes in the Odoo database, navigate to Inventory app ‣ Configuration ‣ Settings. Under the Barcode heading, click on the Configure Product Barcodes button under the Barcode Scanner section. Enter the 14-digit GTIN into the Barcode column, then click Save.

After activating tracking by lots and serial numbers from the settings page, specify that this feature is to be applied on each product by navigating to the Inventory tab on the product form. Under Tracking, choose the By Lots radio button.

### Scan barcode on receipt¶

To ensure accurate lot interpretation in Odoo on product barcodes scanned during a receipt operation, navigate to the Barcode app to manage the [receipt picking process](receipts_deliveries.html#barcode-operations-scan-received-products).

From the Barcode Scanning dashboard, click the Operations button, then the Receipts button to view the list of vendor receipts to process. Receipts generated from POs are listed, but new receipt operations can also be created directly through the Barcode app using the Create button.

On the list of receipts, click on the warehouse operation (`WH/IN`) and scan product barcodes and lot numbers with a barcode scanner. The scanned product then appears on the list. Use the ✏️ (pencil) button to open a window and manually enter quantities for specific lot numbers.

Example

After placing a PO for fifty apples, navigate to the associated receipt in the _Barcode_ app.

Scan the barcode containing the GTIN, quantity, and lot number. For testing with a barcode scanner, below is an example barcode for the fifty Fuji apples in Lot 2.

50 Fuji apples in Lot0002 |   
---|---  
2D Matrix |   
A.I. (product) | 01  
GS1 Barcode (product) | 20611628936004  
A.I. (quantity) | 30  
GS1 Barcode (quantity) | 00000050  
A.I. (lot) | 10  
GS1 Barcode (lot #) | LOT0002  
Full GS1 barcode | 0120611628936004 3000000050 10LOT0002  
  
[If the configuration is correct](gs1_nomenclature.html#barcode-operations-troubleshooting), `50/50` Units processed will be displayed and the Validate button turns green. Click the Validate button to complete the reception.

## Configure barcode for product and non-unit quantity¶

To build a GS1 barcode that contains products measured in a non-unit quantity, like kilograms, for example, the following barcode patterns are used:

Nome | Nome regola | A.I. | Modello codice | Field in Odoo  
---|---|---|---|---  
Prodotto | Global Trade Item Number (GTIN) | 01 | (01)(\d{14}) | Barcode field on product form  
Quantity in kilograms | Variable count of items | 310[0-5] | (310[0-5])(\d{6}) | Units field on transfer form  
  
### Scan barcode on receipt¶

To confirm that quantities are correctly interpreted in Odoo, place an order in the _Purchase_ app using the appropriate unit of measure (UoM) for the quantity of products to be purchased.

Vedi anche

[Simplify vendor unit conversions with UoMs](../../inventory/product_management/configure/uom.html#inventory-product-replenishment-unit-conversion)

After the order is placed, navigate to the Barcode app to [receive the vendor shipment](receipts_deliveries.html#barcode-operations-scan-received-products).

Example

On the receipt in the _Barcode_ app, receive an order for `52.1 kg` of peaches by scanning the barcode containing the GTIN and quantity of peaches in kilograms.

52.1 kg of Peaches |   
---|---  
2D Matrix |   
A.I. (product) | 01  
GS1 Barcode (product) | 00614141000012  
A.I. (kg, 1 decimal point) | 3101  
GS1 Barcode (quantity) | 000521  
Full GS1 barcode | 0100614141000012 3101000521  
  
[If the configuration is correct](gs1_nomenclature.html#barcode-operations-troubleshooting), `52.1 / 52.1` kg will be displayed and the Validate button turns green. Finally, press Validate to complete the validation.

## Verify product moves¶

For additional verification, the quantities of received products are also recorded on the Product Moves report, accessible by navigating to Inventory app ‣ Reporting ‣ Product Moves.

The items on the Product Moves report are grouped by product by default. To confirm the received quantities, click on a product line to open its collapsible drop-down menu, which displays a list of _stock move lines_ for the product. The latest stock move matches the warehouse reception reference number (e.g. `WH/IN/00013`) and quantity processed in the barcode scan, demonstrating that the records processed in the _Barcode_ app were properly stored in _Inventory_.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/barcode/operations/gs1_usage.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../quality.html "Qualità") |
  * [precedente](gs1_nomenclature.html "GS1 barcode nomenclature") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * GS1 barcode usage


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