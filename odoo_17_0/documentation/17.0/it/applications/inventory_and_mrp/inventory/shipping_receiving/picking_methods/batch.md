# Batch picking — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cluster.html "Cluster picking") |
  * [precedente](../picking_methods.html "Picking methods") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Picking methods](../picking_methods.html) »
  * Batch picking



# Batch picking¶

_Batch picking_ enables a single picker to handle multiple orders at once, reducing the time needed to navigate to the same location in a warehouse.

When picking in batches, orders are grouped and consolidated into a picking list. After the picking, the batch is taken to an output location, where the products are sorted into their respective delivery packages.

Vedi anche

Use Barcode app for pickings

Since orders _must_ be sorted at the output location after being picked, this picking method suits businesses with a few products that are ordered often. Storing high-demand items in easily accessible locations can increase the number of orders that are fulfilled efficiently.

## Configurazione¶

To activate the batch picking option, begin by going to Inventory app ‣ Configuration ‣ Settings. Under the Operations section, check the Batch Transfers box.

Since batch picking is a method to optimize the _pick_ operation in Odoo, the Storage Locations and Multi-Step Routes options under the Warehouse heading must also be checked on this settings page. When finished, click Save.

Lastly, enable the warehouse picking feature, by navigating to the warehouse settings page, which is accessible from Inventory app ‣ Configuration ‣ Warehouses.

From here, select the desired warehouse from the list. Then, from the radio options available for Outgoing Shipments, select either the Send goods in output and then deliver (2 steps) or Pack goods, send goods in output and then deliver (3 steps).

Vedi anche

  * [Delivery in two steps](../daily_operations/receipts_delivery_two_steps.html)

  * [Three-step delivery](../daily_operations/delivery_three_steps.html)




## Create batch transfers¶

Manually create batch transfers directly from the Inventory app ‣ Operations ‣ Batch Transfers page. Click the New button to begin creating a batch transfer.

On the batch transfer form, fill the following fields out accordingly:

  * Responsible: employee assigned to the picking. Leave this field blank if _any_ worker can fulfill this picking.

  * Operation Type: from the drop-down menu, select the operation type under which the picking is categorized.

  * Scheduled Date: specifies the date by which the Responsible person should complete the transfer to the output location.




Next, in the Transfers list, click Add a line to open the Add: Transfers window.

If the Operation Type field was filled, the list will filter transfer records matching the selected Operation Type.

Click the New button to create a new transfer.

Once the transfer records are selected, click Confirm to confirm the batch picking.

Example

A new batch transfer assigned to the Responsible, `Joel Willis`, for the `Pick` Operation Type. The Scheduled Date is set to `August 11`.

Clicking the Add a line button opens the Add:Transfers window, displaying only pickings. This is because the Operation Type was set to `Pick` on the batch transfer form.

Click the checkbox to the left of the transfers, `WH/PICK/00001` and `WH/PICK/00002`, to include them in the new transfer. Then, click the Select button to close the Add:Transfers window.

### Add batch from transfers list¶

Another method of creating batch transfers is available using the Add to batch option in a list. Navigate to the Inventory app ‣ Operations drop-down menu, and select any of the Transfers to open a filtered list of transfers.

On the transfers list, select the checkbox to the left of the selected transfers to add in a batch. Next, navigate to the Actions ⚙️ (gear) button, and click Add to batch from the resulting drop-down menu.

Doing so opens an Add to batch pop-up window, wherein the employee Responsible for the picking can be assigned.

Choose from the two radio options to add to an existing batch transfer or create a new batch transfer.

To begin with a draft, select the Draft checkbox.

Conclude the process by clicking Confirm.

## Process batch transfer¶

Handle batch transfers in the Inventory app ‣ Operations ‣ Batch Transfers page.

From here, select the intended transfer from the list. Then, on the batch transfer form, input the Done quantities for each product, under the Detailed Operations tab. Finally, select Validate to complete the picking.

Suggerimento

Be certain the batch transfer is complete when the Validate button is highlighted in purple. If the Check Availability button is highlighted instead, that means there are items in the batch that are currently _not_ available in-stock.

Example

In a batch transfer involving products from pickings, `WH/PICK/00001` and `WH/PICK/00002`, the Detailed Operations tab shows that the product, `Cabinet with Doors`, has been picked because the Done column matches the value in the Reserved column. However, `0.00` quantities have been picked for the other product, `Cable Management Box`.

Only in-stock products are visible in the Detailed Operations tab.

To view the complete product list, switch to the Operations tab. On this list, the Demand column indicates the required quantity for the order. The Reserved column shows the available stock to fulfill the order. Lastly, the Done column specifies the products that have been picked, and are ready for the next step.

Example

The product, `Desk Pad`, from the same batch as the example above, is only visible in the Operations tab because there are no Reserved quantities in-stock to fulfill the batch picking.

Click the Check Availability button to search the stock again for available products.

### Crea ordine residuo¶

On the batch transfer form, if the Done quantity of the product is _less_ than the Reserved quantity, a pop-up window appears.

This pop-up window provides the option: Create Backorder?.

Clicking the Create Backorder button automatically creates a new batch transfer, containing the remaining products.

Click No Backorder to finish the picking _without_ creating another batch picking.

Click Discard to cancel the validation, and return to the batch transfer form.

## Process batch transfer: Barcode app¶

Created batch transfers are also listed in the Barcode app, accessible by selecting the Batch Transfers button.

By default, confirmed batch pickings appear on the Batch Transfers page. On that page, click on the desired batch transfer to open the detailed list of products for the picking.

For the chosen batch transfer, follow the instructions at the top of the page in the black background. Begin by scanning the product’s barcode to record a single product for picking. To record multiple quantities, click the ✏️ (pencil) icon, and enter the required quantities for the picking.

Nota

Products from the same order are labeled with the same color on the left. Completed pickings are highlighted in green.

Example

In a batch transfer for 2 `Cabinet with Doors`, 3 `Acoustic Bloc Screens`, and 4 `Four Person Desks`, the `3/3` and `4/4` Units indicate that the last two product pickings are complete.

`1/2` units of the `Cabinet with Doors` has already been picked, and after scanning the product barcode for the second cabinet, Odoo prompts the user to `Scan a serial number` to record the unique serial number for [product tracking](../../product_management/product_tracking/serial_numbers.html#inventory-product-management-configure-lots).

Once all the products have been picked, click on Validate to mark the batch transfer as Done.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/picking_methods/batch.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cluster.html "Cluster picking") |
  * [precedente](../picking_methods.html "Picking methods") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Picking methods](../picking_methods.html) »
  * Batch picking


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