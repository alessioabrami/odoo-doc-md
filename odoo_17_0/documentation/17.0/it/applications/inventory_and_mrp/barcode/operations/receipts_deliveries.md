# Process receipts and deliveries with barcodes — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](transfers_scratch.html "Create and process transfers with barcodes") |
  * [precedente](adjustments.html "Apply inventory adjustments with barcodes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Process receipts and deliveries with barcodes



# Process receipts and deliveries with barcodes¶

The _Barcode_ app can be used to process receipts, deliveries, and other types of operations in real time using a barcode scanner or the Odoo mobile app.

This makes it possible to process operations on the warehouse floor when they happen, instead of having to wait to validate transfers from a computer. Processing operations this way can help to properly attribute barcodes to the appropriate products, pickings, locations, and more.

## Enable Barcode app¶

To use the _Barcode_ app to process transfers, it must be installed by enabling the feature from the settings of the _Inventory_ app.

To do so, go to the Inventory app ‣ Configuration ‣ Settings. Then, scroll down to the Barcode section, and click the checkbox next to the Barcode Scanner feature.

Once the checkbox is ticked, click Save at the top of the page to save changes.

Once the page has refreshed, new options will be displayed under the Barcode Scanner feature: Barcode Nomenclature (with a corresponding drop-down menu), where either Default Nomenclature or Default GS1 Nomenclature can be selected.

There is also a Configure Product Barcodes internal link arrow, and a set of Print buttons for printing barcode commands and a barcode demo sheet.

For more on setting up and configuring the Barcode app, refer to the [Set up your barcode scanner](../setup/hardware.html) and [Activate the Barcodes in Odoo](../setup/software.html) documentation pages.

## Scan barcodes for receipts¶

To process warehouse receipts for incoming products, there first needs to be a purchase order (PO) created, and a receipt operation to process.

To create a PO, navigate to the Purchase app ‣ Create to create a new request for quotation (RFQ).

From the blank RFQ form, click the drop-down menu next to the Vendor field to add a vendor. Then, on the Product line under the Products tab, click Add a product, and select the desired product(s) to add to the quotation.

Once ready, click Save at the top of the form, then click Confirm Order to confirm the RFQ to a PO.

To process and scan barcodes for warehouse receipts, navigate to the Barcode app.

Once inside the Barcode app, a Barcode Scanning screen displaying different options is presented. To process receipts, click on the Operations button at the bottom of the screen. This navigates to an Operations overview page.

From this page, locate the Receipts card, and click the # To Process button to view all outstanding receipts. Then, select the desired receipt operation to process. This navigates to the barcode transfer screen.

Nota

If _only_ using a barcode scanner or the Odoo mobile app, the barcodes for each transfer of a corresponding operation type can be scanned to be processed easily. Once scanned, the products that are part of an existing transfer can be scanned, and new products can be added to the transfer, as well. Once all products have been scanned, validate the transfer to proceed with the stock moves.

From this screen, an overview of all receipts to process within that transfer (**WH/IN/000XX**) is shown. At the bottom of the screen, there are options to Add Product or Validate, depending on if products need to be added to the operation, or if the whole operation should be validated at once.

To process and scan each product individually, choose a specific product line. The +# button (in this case, +10) can be clicked to indicate receipt of that product, or the pencil icon can be clicked to open a new screen to edit that product line.

From this screen, the product that’s being received is listed. Under the product name, the Quantity line can be edited. Either change the `0` in the line to the desired quantity, or click the /# Units button (in this case, /10 Units) to automatically fill the quantity ordered from the PO.

Example

In the reception operation `WH/IN/00019`, `10 Units` of the `Barcode Product` is expected to be received. `[BARCODE_PROD]` is the Internal Reference set on the product form. Scan the barcode of the `Barcode Product` to receive one unit. Afterwards, click the pencil icon to manually enter the received quantities.

Additionally, the +1 and -1 buttons can be clicked to add or subtract quantity of the product, and the number keys can be used to add quantity, as well.

Below the number keys is the location line, which reads `WH/Stock` by default, unless another _location_ is listed on the product itself. Click this line to reveal a drop-down menu of additional locations to choose from.

Once ready, click Confirm to confirm the changes made to the product line.

Then, from the overview page with all receipts to process within that transfer (**WH/IN/000XX**), click the +# button on the product line for the products being received, and click Validate. The receipt has now been processed, and the Barcode app can be closed out.

## Scan barcodes for delivery orders¶

To process warehouse deliveries for outgoing products, there first needs to be a sales order (SO) created, and a delivery operation to process.

To create a SO, navigate to the Sales app ‣ Create to create a new quotation.

From the blank quotation form, click the drop-down menu next to the Customer field to add a customer. Then, on the Product line under the Order Lines tab, click Add a product, and select the desired product(s) to add to the quotation.

Once ready, click Save at the top of the form, and click Confirm Order to confirm the quotation to a SO.

To process and scan barcodes for warehouse deliveries, navigate to the Barcode app.

Once inside the Barcode app, a Barcode Scanning screen displaying different options is presented. To process deliveries, click on the Operations button at the bottom of the screen. This navigates to an Operations overview page.

From this page, locate the Delivery Orders card, and click the # To Process button to view all outstanding deliveries. Then, select the desired delivery order to process. This navigates to the barcode transfer screen.

From this screen, an overview of all deliveries to process within that transfer (**WH/OUT/000XX**) is shown. At the bottom of the screen, there are options to Add Product or Validate, depending on if products need to be added to the operation, or if the whole operation should be validated at once.

To process and scan each product individually, choose a specific product line. The +1 button can be clicked to indicate delivery of that product, or the pencil icon can be clicked to open a new screen to edit that product line.

From this screen, the product that’s being delivered is listed. Under the product name, the Quantity line can be edited. Either change the `0` in the line to the desired quantity, or click the /# Units button (in this case, /10 Units) to automatically fill the quantity ordered from the SO.

Additionally, the +1 and -1 buttons can be clicked to add or subtract quantity of the product, and the number keys can be used to add quantity, as well.

Below the number keys is the location line, which reads `WH/Stock` by default, unless another location is listed on the product itself.

This is the location that the product is being pulled from for delivery. Click this line to reveal a drop-down menu of additional locations to choose from (if this product is stored in multiple locations in the warehouse).

Suggerimento

For warehouses that have multiple different storage locations, putaway rules, and removal strategies, additional steps can be added for various operation types, while using the _Barcode_ app.

Once ready, click Confirm to confirm the changes made to the product line.

Then, from the overview page with all receipts to process within that transfer (**WH/OUT/000XX**), click the +# button on the product line for the products being received, and click Validate. The delivery has now been processed, and the _Barcode_ app can be closed out.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/barcode/operations/receipts_deliveries.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](transfers_scratch.html "Create and process transfers with barcodes") |
  * [precedente](adjustments.html "Apply inventory adjustments with barcodes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Process receipts and deliveries with barcodes


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
  *[PO]: purchase order
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