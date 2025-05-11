# Apply inventory adjustments with barcodes — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_deliveries.html "Process receipts and deliveries with barcodes") |
  * [precedente](../operations.html "Daily operations") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Apply inventory adjustments with barcodes



# Apply inventory adjustments with barcodes¶

In a warehouse, the recorded inventory counts in the database might not always match the actual, real inventory counts. In such cases, inventory adjustments can be made to reconcile the differences, and ensure that the recorded counts in the database match the actual counts in the warehouse. In Odoo, the _Barcode_ app can be used to make these adjustments.

These adjustments can be done in real time using an Odoo-compatible barcode scanner or the Odoo mobile app.

Nota

For a list of Odoo-compatible barcode mobile scanners, and other hardware for the _Inventory_ and _Barcode_ apps, refer to the [Odoo Inventory • Hardware page](https://www.odoo.com/app/inventory-hardware).

Vedi anche

[Inventory adjustments](../../inventory/warehouses_storage/inventory_management/count_products.html)

## Enable Barcode app¶

To use the _Barcode_ app to create and apply inventory adjustments, it **must** be installed by enabling the feature from the settings of the _Inventory_ app.

To do so, go to the Inventory app ‣ Configuration ‣ Settings. Then, scroll down to the Barcode section, and click the checkbox next to the Barcode Scanner option.

Once the checkbox is ticked, click Save at the top of the page to save changes.

After saving, a new drop-down menu appears under the Barcode Scanner option, labeled Barcode Nomenclature, where either Default Nomenclature or Default GS1 Nomenclature can be selected. Each nomenclature option determines how scanners interpret barcodes in Odoo.

There is also a Configure Product Barcodes internal link arrow, along with a set of Print buttons for printing barcode commands and a barcode demo sheet.

Vedi anche

For more information on setting up and configuring the Barcode app, refer to the [Set up your barcode scanner](../setup/hardware.html) and [Activate the Barcodes in Odoo](../setup/software.html) docs.

## Perform an inventory adjustment¶

Begin by navigating to the Barcode app ‣ Barcode Scanning dashboard, where different options will be displayed, including Operations, Inventory Adjustments, and Batch Transfers.

To create and apply inventory adjustments, click on the Inventory Adjustments button at the bottom of the screen.

Doing so navigates to the _Barcode Inventory Client Action_ page, labeled as Inventory Adjustment in the top header section.

To begin the adjustment, first scan the _source location_ , which is the current location in the warehouse of the product whose count should be adjusted. Then, scan the product barcode(s).

The barcode of a specific product can be scanned multiple times to increase the quantity of that product in the adjustment.

Suggerimento

If the warehouse _multi-location_ feature is **not** enabled in the database, a source location does not need to be scanned. Instead, simply scan the product barcode to start the inventory adjustment.

Alternatively, the quantity can be changed by clicking the ✏️ (pencil) icon on the far right of the product line.

Doing so opens a separate window with a keypad. Edit the number in the Quantity line to change the quantity. Additionally, the +1 and -1 buttons can be clicked to add or subtract quantity of the product, and the number keys can be used to add quantity, as well.

Example

In the below inventory adjustment, the source location `WH/Stock/Shelf/2` was scanned, assigning the location. Then, the barcode for the product `[FURN_7888] Desk Stand with Screen` was scanned 3 times, increasing the units in the adjustment. Additional products can be added to this adjustment by scanning the barcodes for those specific products.

To complete the inventory adjustment, click the green ✅ Apply button with the check mark at the bottom of the page.

Once applied, Odoo navigates back to the Barcode Scanning screen. A small green banner appears in the top right corner, confirming validation of the adjustment.

Did you know?

Odoo’s _Barcode_ application provides demo data with barcodes to explore the features of the app. These can be used for testing purposes, and can be printed from the home screen of the app.

To access this demo data, navigate to the Barcode app and click stock barcodes sheet and commands for Inventory (bolded and highlighted in blue) in the information pop-up window above the scanner.

## Manually add products to inventory adjustment¶

When the barcodes for the location or product are not available, Odoo _Barcode_ can still be used to perform inventory adjustments.

To do this, navigate to the Barcode app ‣ Barcode Scanning ‣ Inventory Adjustments.

Doing so navigates to the _Barcode Inventory Client Action_ page, labeled as Inventory Adjustment in the top header section.

To manually add products to this adjustment, click the white ➕ Add Product button at the bottom of the screen.

This navigates to a new, blank page where the desired product, quantity, and source location must be chosen.

> First, click the Product line, and choose the product whose stock count should be adjusted. Then, manually enter the quantity of that product, either by changing the `1` in the Quantity line, or by clicking the +1 and -1 buttons to add or subtract quantity of the product. The number pad can be used to add quantity, as well.

Below the number pad is the location line, which should read `WH/Stock` by default. Click this line to reveal a drop-down menu of locations to choose from, and choose the source location for this inventory adjustment.

Once ready, click Confirm to confirm the changes.

To apply the inventory adjustment, click the green ✅ Apply button with the check mark, at the bottom of the page.

Once applied, Odoo navigates back to the Barcode Scanning screen. A small green banner appears in the top right corner, confirming validation of the adjustment.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/barcode/operations/adjustments.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_deliveries.html "Process receipts and deliveries with barcodes") |
  * [precedente](../operations.html "Daily operations") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Apply inventory adjustments with barcodes


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