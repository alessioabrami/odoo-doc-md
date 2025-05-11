# Two-step receipt and delivery — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_three_steps.html "Three-step receipt") |
  * [precedente](receipts_delivery_one_step.html "One-step receipt and delivery") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Two-step receipt and delivery



# Two-step receipt and delivery¶

Depending on a company’s needs, receiving and shipping products in and out of the warehouse might require multi-step operations. In Odoo _Inventory_ , this can be done using _Multi-Step Routes_.

In the two-step receipt process, products are received in an input area, then transferred to stock. This kind of process for incoming shipments might be beneficial for warehouses with specific storage locations, such as freezers and refrigerators, secured locked areas, or special aisles and shelves.

Products can be sorted according to where they are going to be stored, and employees can stock all the products going to a specific location. The products are _not_ available for further processing, until they are transferred into stock.

In the two-step delivery process, products are first picked from their respective location in the warehouse, then transferred to an output location before being shipped to the customer.

This might be beneficial for companies using a First In, First Out (FIFO), Last In, First Out (LIFO), or First Expired, First Out (FEFO) removal strategy.

Suggerimento

Incoming and outgoing shipments do **not** need to be configured with the same amount of steps.

For example, a warehouse’s settings can be configured so products can be received in two steps (input + stock), and delivered in three steps (pick + pack + ship).

## Configurazione¶

In Odoo _Inventory_ , both incoming and outgoing shipments are configured to process in one step, by default. To change these settings, the _Multi-Step Routes_ feature must be enabled.

To enable _Multi-Step Routes_ , navigate to Inventory app ‣ Configuration ‣ Settings. Under the Warehouse section, tick the checkbox next to Multi-Step Routes, and click Save. Doing so also activates the Storage Locations feature.

Next, configure a warehouse for two-step receipts and deliveries. Navigate to Inventory app ‣ Configuration ‣ Warehouses, and select a warehouse to edit.

Under the Warehouse Configuration tab, set Incoming Shipments to Receive goods in input and then stock (2 steps), and set Outgoing Shipments to Send goods in output and then deliver (2 steps).

Nota

Selecting two-step receipts and deliveries automatically creates new _Input_ and _Output_ warehouse locations in the database, named `WH/Input` and `WH/Output`, respectively.

To rename or edit these locations, navigate to Inventory app ‣ Configuration ‣ Locations, and select the desired location.

On the location’s form, change the Location Name, and make any other necessary changes.

## Process receipt in two steps (input + stock)¶

When products are received in two steps, they first move from the vendor location to an input location. Then, they move from the input location to warehouse stock in the database, upon validation of a purchase order (PO), and a subsequent internal transfer.

### Create purchase order¶

To create a PO, navigate to the Purchase app, and click New. This opens a blank Request for Quotation (RfQ) form.

Add a vendor in the Vendor field. Then, fill out the various fields on the RfQ, as necessary.

Under the Products tab, click Add a product, and select a product to add to the RfQ.

Once ready, click Confirm Order. This moves the RfQ to the Purchase Order stage.

Once the PO is confirmed, a Receipt smart button appears at the top of the form. Clicking the smart button opens the warehouse receipt (WH/IN) form.

Suggerimento

For businesses with multiple warehouses that have different step configurations, the Deliver To field on the PO form **must** be specified as the correct _input location_ connected to the two-step warehouse.

This can be done by selecting the warehouse from the drop-down menu that includes the `Receipts` label at the end of the name.

### Process receipt¶

From the warehouse receipt form, the products ordered can be received into the warehouse. To receive the products, click Validate. Once validated, the receipt moves to the Done stage, and the products move to the WH/Input location.

Click back to the PO (via the breadcrumbs, at the top of the form) to view the PO form. On the product line, the quantity in the Received column now matches the ordered Quantity.

### Process internal transfer¶

Once the receipt is validated, an internal transfer is created and ready to process.

To view the internal transfer, navigate to the Inventory app, and locate the Internal Transfers task card.

Click the # To Process button on the task card to reveal a list of all internal transfers to process, and select the transfer associated with the previously validated receipt.

Once ready, click Validate to complete the transfer, and move the product from WH/Input to WH/Stock.

Once the transfer is validated, the products enter inventory, and are available for customer deliveries or manufacturing orders.

## Process delivery order in two steps (pick + ship)¶

When products are delivered in two steps, they move from warehouse stock to an output location. Then, they move from the output location to a customer location in the database, upon validation of a picking order, and a subsequent delivery order (DO).

### Create sales order¶

To create a SO, navigate to the Sales app, and click New. This opens a blank sales quotation form.

Add a customer in the Customer field. Then, fill out the various fields on the sales quotation form, as necessary.

Under the Order Lines tab, click Add a product, and select a product to add to the sales order quotation.

Once ready, click Confirm. This moves the quotation to the Sales Order stage.

Once the SO is confirmed, a Delivery smart button appears at the top of the form. Clicking the smart button opens the warehouse delivery (WH/OUT) form.

### Process picking¶

Once the sales order is confirmed, a picking order is generated and ready to process.

To complete the picking, navigate to the Inventory app, and locate the Pick task card on the Inventory Overview dashboard. Alternatively, the picking order can also be accessed via the Delivery smart button at the top of the sales order form.

From the Inventory Overview page, click the # To Process button on the Pick task card. This reveals a list of all pickings to process.

Click on the picking (WH/PICK) operation associated with the sales order to reveal the picking order.

Manually set the quantity by changing the value in the Quantity column, to match the value in the Demand column.

Once ready, click Validate to complete the picking, and move the product from WH/Stock to WH/Output.

### Process delivery¶

Once the picking is validated, a delivery order is created, and ready to process. Clicking the Delivery smart button on the sales order form reveals the newly created delivery order.

Alternatively, to view the delivery order, navigate back to the Inventory Overview page, via the breadcrumbs, and locate the Delivery Orders task card.

Click the # To Process button on the task card to reveal a list of all delivery orders to process, and select the order associated with the previously validated picking.

To deliver the products, change the value in the Quantity field to match the ordered quantity in the Demand field.

Once ready, click Validate. Once validated, the delivery order moves to the Done stage.

Vedi anche

[Inbound and outbound flows](../daily_operations.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations/receipts_delivery_two_steps.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_three_steps.html "Three-step receipt") |
  * [precedente](receipts_delivery_one_step.html "One-step receipt and delivery") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Two-step receipt and delivery


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
  *[UoM]: Units of Measure
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders