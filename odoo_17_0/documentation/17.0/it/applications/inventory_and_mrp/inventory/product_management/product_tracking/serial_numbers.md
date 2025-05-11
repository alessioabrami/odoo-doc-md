# Use serial numbers to track products — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](create_sn.html "Assign serial numbers") |
  * [precedente](../product_tracking.html "Product tracking") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Use serial numbers to track products



# Use serial numbers to track products¶

_Serial numbers_ are one of the two ways to identify and track products in Odoo. A serial number is a unique identifier assigned incrementally (or sequentially) to an item or product, used to distinguish it from other items and products.

Serial numbers can consist of many different types of characters: they can be strictly numerical, they can contain letters and other typographical symbols, or they can be a mix of all of the above.

The goal of assigning serial numbers to individual products is to make sure that every item’s history is identifiable when it travels through the supply chain. This can be especially useful for manufacturers that provide after-sales services to products that they sell and deliver.

Vedi anche

[Numeri lotto](lots.html)

## Enable lots & serial numbers¶

To track products using serial numbers, the Lots & Serial Numbers feature must be enabled. To enable this, go to Inventory app ‣ Configuration ‣ Settings, scroll down to the Traceability section, and click the box next to Lots & Serial Numbers. Remember to click the Save button to save changes.

## Configure serial number tracking on products¶

Once the Lots & Serial Numbers setting has been activated, individual products can now be tracked using serial numbers. To configure this, go to Inventory app ‣ Products ‣ Products, and choose a desired product to track.

Once on the product form, click Edit, and click the Inventory tab.

Once on the product form, click Edit, navigate to the Inventory tab, and scroll to the Traceability section. Then, select the By Unique Serial Number option, and click Save to save the changes. Existing or new serial numbers can now be selected and assigned to newly-received or manufactured batches of this product.

Avvertimento

If a product doesn’t have a serial number assigned to it, a user error pop-up window will appear. The error message states that the product(s) in stock have no lot/serial number. However, a lot/serial number can be assigned to the product by making an inventory adjustment.

### Create new serial numbers for products already in stock¶

New serial numbers can be created for products already in stock with no assigned serial number. To do this, go to Inventory ‣ Products ‣ Lots/Serial Numbers, and click Create. Doing so reveals a blank lots/serial numbers form. On this form, a new Lot/Serial Number is generated automatically.

Suggerimento

While Odoo automatically generates a new lot/serial number to follow the most recent number, it can be edited and changed to any desired number, by clicking the line under the Lot/Serial Number field, and changing the generated number.

Once the Lot/Serial Number is generated, click the blank field next to Product to reveal a drop-down menu. From this menu, select the product to which this new number will be assigned.

This form also provides the option to adjust the Quantity, to assign a unique Internal Reference number (for traceability purposes), and to assign this specific lot/serial number configuration to a specific website in the Website field (if working in a multi-website environment).

A detailed description of this specific lot/serial number can also be added in the Description tab below.

When all desired configurations are complete, click the Save button to save all changes.

After a new serial number has been created, assigned to the desired product, and saved, navigate back to the product form, by going to Products ‣ Products, and selecting the product that this newly-created serial number was just assigned to.

On that product’s detail form, click the Lot/Serial Numbers smart button to view the new serial number.

## Manage serial numbers for shipping and receiving¶

Serial numbers can be assigned for both **incoming** and **outgoing** goods. For incoming goods, serial numbers are assigned directly on the purchase order form. For outgoing goods, serial numbers are assigned directly on the sales order form.

### Assign serial numbers to newly received products¶

Assigning serial numbers to **incoming** goods can be done on the receipt, by clicking the [Detailed Operations smart button](create_sn.html#inventory-product-management-detailed-operations) or by clicking the ⦙≣ (bulleted list) icon in the product line.

Vedi anche

[Assign serial numbers](create_sn.html)

Avvertimento

Clicking Validate before assigning a serial number to received quantities will cause a User Error pop-up to appear. The pop-up requires entry of a lot or serial number for the ordered products. The RFQ **cannot** be validated without a serial number being assigned.

There are multiple ways to do this: manually assigning serial numbers, automatically assigning serial numbers, and copy/pasting serial numbers from a spreadsheet.

#### Assign serial numbers automatically¶

If a large quantity of products need individual serial numbers assigned to them, Odoo can automatically generate and assign serial numbers to each of the individual products.

To accomplish this, start with the First SN field in the Detailed Operations pop-up window, and type the first serial number in the desired order to be assigned.

Then, in the Number of SN field, type the total number of items that need newly-generated unique serial numbers assigned to them.

Finally, click Assign Serial Numbers, and a list will populate with new serial numbers matching the ordered quantity of products.

#### Copy/paste serial numbers from a spreadsheet¶

To copy and paste serial numbers from an existing spreadsheet, first populate a spreadsheet with all of the serial numbers received from the supplier (or manually chosen upon receipt). Then, copy and paste them in the Lot/Serial Number Name column. Odoo will automatically create the necessary number of lines based on the amount of numbers pasted in the column.

From here, the To locations and Done quantities can be manually entered in each of the serial number lines.

Suggerimento

For purchase orders that include large quantities of products to receive, the best method of serial number assignment is to automatically assign serial numbers using the Assign Serial Numbers button located on the PO. This prevents any serial numbers from being reused or duplicated, and improves traceability reporting.

Once all product quantities have been assigned a serial number, click the Confirm button to close the pop-up. Then, click Validate.

A Traceability smart button appears upon validating the receipt. Click the Traceability smart button to see the updated Traceability Report, which includes: a Reference document, the Product being traced, the Lot/Serial #, and more.

Once all product quantities have been assigned a serial number, click Confirm to close the popup, and click Validate. A Traceability smart button will appear upon validating the receipt. Click the Traceability smart button to see the updated Traceability Report, which includes: a Reference document, the Product being traced, the Lot/Serial #, and more.

### Manage serial numbers on delivery orders¶

Assigning serial numbers to **outgoing** goods can be done directly from the sales order (SO).

To create an SO, navigate to the Sales app, and click the Create button. Doing so reveals a new, blank quotation form. On this blank quotation form, fill out the necessary information, by adding a Customer, and adding products to the Product lines (in the Order Lines tab), by clicking Add a product.

Then, choose the desired quantity to sell by changing the number in the Quantity column.

Once the quotation has been filled out, click the Confirm button to confirm the quotation. When the quotation is confirmed, the quotation becomes an SO, and a Delivery smart button appears.

Click the Delivery smart button to view the warehouse receipt form for that specific SO.

From here, click the Additional Options menu, represented by a `hamburger` icon (four horizontal lines, located to the right of the Unit of Measure column in the Operations tab). Clicking that icon reveals a Detailed Operations pop-up.

In the pop-up, a Lot/Serial Number will be chosen by default, with each product of the total Reserved quantity listed with their unique serial numbers (most likely listed in sequential order).

To manually change a product’s serial number, click the drop-down menu under Lot/Serial Number, and choose (or type) the desired serial number. Then, mark the Done quantities, and click Confirm to close the pop-up.

Finally, click the Validate button to deliver the products.

Upon validating the delivery order, a Traceability smart button appears. Click the Traceability smart button to see the updated Traceability Report, which includes: a Reference document, the Product being traced, the Date, and the Lot/Serial # assigned.

The Traceability Report can also include a Reference receipt from the previous purchase order (PO), if any of the product quantities shared a serial number assigned during receipt of that specific PO.

## Manage serial numbers for different operations types¶

By default in Odoo, the creation of new serial numbers is only allowed upon **receiving** products from a purchase order. **Existing** serial numbers cannot be used. For sales orders, the opposite is true: new serial numbers cannot be created on the delivery order, only existing serial numbers can be used.

To change the ability to use new (or existing) serial numbers on any operation type, go to Inventory app ‣ Configuration ‣ Operations Types, and select the desired Operation Type.

For the Receipts operation type, found on the Operations Types page, the Use Existing Lots/Serial Numbers option can be enabled, by selecting Receipts from the Operations Types page, clicking Edit, and then clicking the checkbox beside the Use Existing Lots/Serial Numbers option (in the Traceability section). Lastly, click the Save button to save the changes.

For the Delivery Orders operation type, located on the Operations Types page, the Create New Lots/Serial Numbers option can be enabled, by selecting Delivery Orders from the Operations Types page, clicking Edit, and clicking the checkbox beside the Create New Lots/Serial Numbers option (in the Traceability section). Be sure to click Save to save changes.

## Serial number traceability¶

Manufacturers and companies can refer to the traceability reports to see the entire lifecycle of a product: where it came from (and when), where it was stored, and who it went to.

To see the full traceability of a product, or group by serial numbers, go to Inventory app ‣ Products ‣ Lots/Serial Numbers. Doing so reveals the Lots/Serial Numbers dashboard.

From here, products with serial numbers assigned to them will be listed by default, and can be expanded to show what serial numbers have been specifically assigned to them.

To group by serial numbers (or lots), first remove any default filters from the search bar in the upper-right corner. Then, click Group By, and select Add Custom Group, which reveals a mini drop-down menu. From this mini drop-down menu, select Lot/Serial Number, and click Apply.

Doing so reveals all existing serial numbers and lots, and can be expanded to show all quantities of products with that assigned number. For unique serial numbers that are not reused, there should be just one product per serial number.

Suggerimento

For additional information regarding an individual serial number (or lot number), click the line item for the serial number to reveal that specific serial number’s Serial Number form. From this form, click the Location and Traceability smart buttons to see all stock on-hand using that serial number, and any operations made using that serial number.

Vedi anche

[Product tracking](../product_tracking.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/product_tracking/serial_numbers.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](create_sn.html "Assign serial numbers") |
  * [precedente](../product_tracking.html "Product tracking") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Use serial numbers to track products


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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure