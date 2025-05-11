# Numeri lotto — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reassign.html "Reassign lot/serial numbers") |
  * [precedente](create_sn.html "Assign serial numbers") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Numeri lotto



# Numeri lotto¶

_Lots_ are one of the two ways to identify and track products in Odoo. They typically represent a specific batch of products that were received, stored, shipped, or manufactured in-house.

Manufacturers assign lot numbers to groups of products sharing common properties, facilitating end-to-end traceability through their lifecycles.

Lots are useful for managing large quantities of manufactured or received products, aiding in tracing items back to their group, particularly for product recalls or [expiration dates](expiration_dates.html).

Vedi anche

[Use serial numbers to track products](serial_numbers.html)

## Enable lots & serial numbers¶

To track products using lots, enable the _Lots & Serial Numbers_ feature. Go to the Inventory app ‣ Configuration ‣ Settings, scroll down to the Traceability section, and tick the checkbox next to Lots & Serial Numbers. Then, click Save.

Vedi anche

  * [Tracking expiration dates](expiration_dates.html)

  * [Print GS1 barcodes for lots and serial numbers](../../../barcode/operations/gs1_usage.html#barcode-operations-gs1-lots)




## Track by lots¶

Once the Lots & Serial Numbers feature is activated, configure individual products to be tracked using lots. To do this, go to Inventory app ‣ Products ‣ Products, and choose a product to configure.

On the product form, go to the Inventory tab. In the Traceability section, select the By Lots option in the Tracking field. Now, new or existing lot numbers can be assigned to newly-received or manufactured batches of this product.

Vedi anche

[Expiration dates](expiration_dates.html)

Importante

If a product has stock on-hand prior to activating tracking by lots or serial numbers, a warning message appears. Use an [inventory adjustment](reassign.html) to assign lot numbers to existing products in stock.

## Assign lots for shipping and receiving¶

Assign new lot numbers to incoming goods on the receipt form. When shipping outgoing goods, select products with specific lot numbers on the delivery order form.

### On receipts¶

Assigning new or existing lot numbers to incoming goods can be done directly on receipts.

To begin, go to the Purchase app to [create and confirm](https://www.youtube.com/watch?v=o_uI718P1Dc) a PO for products tracked by lot numbers. Then, click the Receipt smart button that appears at the top of the page to navigate to the warehouse receipt form.

Nota

Alternatively, navigate to an existing receipt by going to the Inventory app, clicking the Receipts Kanban card, and choosing the desired receipt.

Importante

Clicking Validate before assigning a lot number triggers an error, indicating that a lot number **must** be assigned before validating the receipt.

On the receipt form, on the product line in the Operations tab, select the __(list) icon to the right of the product that is tracked by lot numbers.

Doing so opens the Open: Stock move pop-up window, where the Lot/Serial Number and Quantity are assigned.

The two ways to assign lot numbers: **manually** and **importing**.

#### Manual assignment¶

To manually assign lot numbers, click Add a line. Input the Lot/Serial Number, Store To location for the lot, Quantity, and Destination Package, if any.

Nota

To assign multiple lot numbers, or store to multiple locations, click Add a line, and type a new Lot/Serial Number for additional quantities. Repeat until the total in the Quantity column matches the Demand at the top.

#### Import lots¶

In the Open: Stock move pop-up window, click Import Serials/Lots, then paste the bulk lot numbers, in the Lots/Serial numbers field.

List of lot numbers copied on _Google_ spreadsheets.¶

Lot numbers pasted to the «Lots/Serial numbers» field, in the **Import Lots** pop-up window.¶

Tick the Keep current lines checkbox to generate _additional_ lot numbers in the Open: Stock move pop-up window. To replace the lot numbers in the list, leave the Keep current lines option unticked.

Finally, click Generate.

Once all product quantities have been assigned a lot number, click Save to close the pop-up window. Then, click Validate on the receipt form.

Vedi anche

Traceability report for lot numbers

### On delivery orders¶

Odoo makes it possible to specify which lot numbers for a product are chosen for outgoing shipment on a delivery order form.

To begin, create or select an existing quotation from the Sales app. After confirming the SO, the Delivery smart button becomes available. Click the Delivery smart button to view the warehouse receipt form for that specific SO.

Nota

Alternatively, navigate to delivery orders by going to the Inventory app, and clicking the Delivery Orders kanban card.

Clicking the Delivery smart button opens the the delivery order form, where lot numbers are picked for delivery. In the Operations tab, click the __(list) icon to the right of the product that is tracked by lot numbers. Clicking that icon reveals a Open: Stock move pop-up window.

In the pop-up window, the chosen lot number and its storage location is displayed in the Pick From column, with the with the full Quantity taken from that specific lot (if there is enough stock in that particular lot).

If there is insufficient stock in that lot, or if partial quantities of the Demand should be taken from multiple lots, change the Quantity directly.

Nota

The lot automatically chosen for delivery orders varies, depending on the selected removal strategy (FIFO, LIFO, or FEFO). It also depends on the ordered quantity, and whether the lot’s on-hand quantity is enough to fulfill the order.

Vedi anche

[Removal strategies](../../shipping_receiving/removal_strategies.html)

Repeat the above steps to select enough lots to fulfill the Demand, and click Save to close the pop-up window. Lastly, click the Validate button on the DO to deliver the products.

Vedi anche

Traceability report for lot numbers

## Lot management¶

Manage and view existing lot numbers for products in the Lot/Serial Numbers dashboard by going to Inventory app ‣ Products ‣ Lots/Serial Numbers.

By default, lot numbers are grouped by product, and selecting the drop-down menu for each product displays the existing lot numbers. Select a lot number to modify or add details linked to the lot. Lot numbers can also be created from this page, by clicking the New button.

Display lot numbers, grouped by products, on the **Lot/Serial Number** dashboard.¶

### Modify lot¶

Clicking a lot from the Lot/Serial Number dashboard reveals a separate page where additional information can be provided about the lot.

Suggerimento

Odoo automatically generates a new Lot/Serial Number to follow the most recent number. However, it can be edited, by clicking the line under the Lot/Serial Number field, and changing the generated number to any desired one.

On the lot number form, the following fields can be modified:

  * Lot/Serial Number: change the lot number linked to the Product

  * Internal Reference: records an alternative lot/serial number used within the warehouse that differs from the one used by the supplier manufacturer.

  * Company: specify the company where the lot number is available.

  * Description: add extra details about the lot or serial number in this text field.




Importante

On existing lots, the Product and On Hand Quantity fields **cannot** be modified, as the lot numbers are linked with existing stock moves.

Vedi anche

[Set expiration dates for lots](expiration_dates.html)

#### Add property¶

To add custom fields to lots for enhanced traceability, there are two methods of adding properties on a lot number form:

  1. Click the __(cog) icon at the top-left of the page, then select __ Add Properties from the drop-down menu.

  2. Click the __ Add a Property button, located below the existing fields.




Name and [configure the new field](../../../../productivity/knowledge/properties.html). Once finished, enter the property value in the new field.

Example

The new property, `Wood type`, is added. The value is recorded as `Cherry wood`.

Vedi anche

[Configuring custom properties](../../../../productivity/knowledge/properties.html)

### Reserve lot number for a product¶

To create a lot number for a product, begin by going to Inventory app ‣ Products ‣ Lot/Serial Numbers, and click New.

Importante

Creating a lot number reserves it for a product but **does not** assign it. To assign lot numbers, refer to the section on assigning lot numbers on receipts.

Suggerimento

While Odoo automatically generates a new Lot/Serial Number to follow the most recent number, it can be edited and changed to any desired number, by clicking the line under the Lot/Serial Number field on the lot form, and changing the generated number.

Once the new Lot/Serial Number is generated, click the blank field next to Product to reveal a drop-down menu. From this menu, select the product to which this new number will be assigned.

Example

The lot number, `000001`, is created for the product, `Drawer Black`.

After a new lot number has been created, saved, and assigned to the desired product, the lot number is saved as an existing lot number linked to the product, and can be selected when assigning lot numbers to products on a receipt, or when making an inventory adjustment.

Example

After creating the lot number, `000001` appears as an option for `Drawer Black` when assigning lot numbers on the Inventory Adjustment page.

## Manage lots for different operations types¶

By default, new lots can only be created when receiving products, and existing lot numbers cannot be used. For sales orders, only existing lot numbers can be utilized, and new ones cannot be created on the delivery order.

To change the ability to use new (or existing) lot numbers on any operation type, go to the Inventory app ‣ Configuration ‣ Operations Types, and select the desired operation type.

On the operation type form, under the Lots/Serial Numbers section, tick the Create New checkbox to enable new lot numbers to be created during this operation type. Choose Use Existing ones if only existing lot numbers can be selected.

Suggerimento

For inter-warehouse transfers involving products tracked by lots, it can be useful to enable the Use Existing Lots/Serial Numbers option for warehouse receipts.

## Tracciabilità¶

Manufacturers and companies can refer to traceability reports to see the entire lifecycle of a product: where it came from, when it arrived, where it was stored, who it went to (and when).

To see the full traceability of a product, or group by lots, go to the Inventory app ‣ Products ‣ Lots/Serial Numbers. Doing so reveals the Lots/Serial Numbers dashboard.

From here, products with lot numbers assigned to them will be listed by default, and can be expanded to show the lot numbers those products have assigned to them.

To group by lots, begin by removing any filters in the Search… bar. Then, click the __(caret down) icon to open a drop-down menu of Filters, Group By options, and Favorites. Under the Group By section, click the Add Custom Group option, and select Lot/Serial Number from the drop-down menu.

Doing so reorganizes all the records on the page to display all existing lots and serial numbers, and can be expanded to show all quantities of products with that assigned number.

### Traceability report¶

To view a full stock moves report for a lot number, select the lot number line from the Lots/Serial Number dashboard. On the lot number form, click the Traceability smart button.

Vedi anche

[Product tracking](../product_tracking.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/product_tracking/lots.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reassign.html "Reassign lot/serial numbers") |
  * [precedente](create_sn.html "Assign serial numbers") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Numeri lotto


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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure