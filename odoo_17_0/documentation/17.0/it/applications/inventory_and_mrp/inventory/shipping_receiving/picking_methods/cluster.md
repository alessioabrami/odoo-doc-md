# Cluster picking — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](wave.html "Process wave transfers") |
  * [precedente](batch.html "Batch picking") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Picking methods](../picking_methods.html) »
  * Cluster picking



# Cluster picking¶

Cluster picking is an advanced order fulfillment approach derived from [batch picking](batch.html#inventory-misc-batch-picking).

In this strategy, pickers load a cart with multiple packages, each designated for a specific _sales order_ (SO). Then, the picker travels to each storage location, and places the products directly in the package of the associated order.

This method is most efficient for medium-sized companies, with high order volumes, and relatively few unique products, since the method eliminates the need for sorting products into packages for customers after picking.

However, cluster picking does have some disadvantages. For instance, urgent orders cannot be prioritized, and optimized batches must be manually created beforehand. As a result, the picking process can lead to bottlenecks.

Example

  1. SO 1 calls for one apple and orange

  2. SO 2 calls for one apple and banana

  3. SO 3 calls for one apple, orange, and banana




Apples are stored in Shelf A, oranges in Shelf B, and bananas in Shelf C.

To pick products for three orders at once, the cart is loaded with three empty packages.

Starting at Shelf A, the picker places apples into each package. Next, the picker navigates to Shelf B, and places oranges in the packages designated for SO 1 and SO 3\. Finally, the picker pushes the cart to Shelf C, and loads packages for SO 2 and SO 3 with a banana, each.

With the packages for all three SOs packed, the picker pushes the cart to the output location, where the packages are sealed and prepared for shipment.

## Configurazione¶

To enable cluster picking, begin by navigating to Inventory app ‣ Configuration ‣ Settings. Under the Operations heading, activate the Packages and Batch Transfers options.

Since batch picking is used to optimize the _pick_ operation in Odoo, the Storage Locations and Multi-Step Routes options, under the Warehouse heading, must also be checked on this settings page.

_Storage locations_ allow products to be stored in specific locations they can be picked from, while _multi-step routes_ enable the picking operation itself.

When finished, click Save.

### Packages setup¶

After the Packages feature is enabled, navigate to Inventory app ‣ Products ‣ Packages, and click the New button to create a new package.

On the new package form, the Package Reference is pre-filled with the next available `PACK` number in the system. Pack Date is automatically set to the creation date of the form.

Set the Package Use field to Reusable Box.

Vedi anche

[Packages](../../product_management/configure/package.html)

Example

A package intended for cluster picking is named `CLUSTER-PACK-3` for easy identification. For this workflow, the products are directly packed using their intended shipping boxes, so Package Use is set to Disposable Box.

## Create cluster batch¶

To see how cluster picking works in Odoo, navigate to the Sales app, and create SOs that will be fulfilled together in the same batch. After confirming an SO, the Delivery smart button becomes visible. Displayed inside the icon is a number representing the amount of steps in the outgoing shipment process.

Example

Begin by creating three SOs for the apples, oranges, and bananas, as shown in the example above.

After confirming the SO, the Delivery smart button displays the number `2`, indicating there are two operations to complete: `Pick` and `Delivery`.

With the SOs created, orders now must be grouped into batches. To do so, navigate to the _Inventory_ dashboard and select the operation type card, Delivery Orders or Pick (whichever is the first operation in the delivery flow).

Doing so displays a filtered list of outgoing operations with the Ready status, indicating that all the products in the SO are in stock.

Nota

Cluster pick batches can be created for outgoing shipments in one, two, or three steps.

Vedi anche

  * [Delivery in one step](../daily_operations/receipts_delivery_one_step.html)

  * [Delivery in two steps](../daily_operations/receipts_delivery_two_steps.html)

  * [Delivery in three steps](../daily_operations/delivery_three_steps.html)




Click the checkbox to the left of the corresponding outgoing operation to add them to the batch. With the desired pickings selected, click the ⚙️ Actions (gear) button, and select the Add to batch option from the resulting drop-down menu.

Example

To create a cluster batch, as shown in the example above, in a warehouse configured with two-step outgoing shipments, the following pick operations are selected:

  * `WH/PICK/00007`: linked to SO 88 for one apple and orange.

  * `WH/PICK/00008`: linked to SO 89 for one apple and banana.

  * `WH/PICK/00009`: linked to SO 90 for one apple, orange, and banana.




Doing so opens an Add to batch pop-up window, wherein the employee Responsible for the picking can be assigned.

Choose from the two options in the Add to field to either: add to an existing batch transfer, or create a new batch transfer.

To create draft batch pickings to be confirmed at a later date, select the Draft checkbox.

Conclude the process by clicking Confirm.

## Process batches¶

To process batches, navigate to Inventory app ‣ Operations ‣ Batch Transfers. Click on a batch to select it.

In the Detailed Operations tab, products that are to be picked are grouped by location.

Under the Source Package or Destination Package field, enter the package used for the picking.

Nota

Use the Source Package field when the picking package is configured as _reusable_ on the package form. This means the products are temporarily placed in a container during picking, before getting transferred to their final shipping box.

Alternatively, use the Destination Package field when the product is directly placed in its _disposable_ shipping box during picking.

Example

Process the cluster batch for the three orders of apples, oranges, and bananas example by assigning each picking to a dedicated package.

At the storage location for apples, `WH/Stock/Shelf A`, assign the apples in all three pickings to one of the three disposable packages, `CLUSTER-PACK-1`, `CLUSTER-PACK-2`, or `CLUSTER-PACK-3`.

Record this in Odoo using the Destination Package field in the Detailed Operations tab.

### In Barcode¶

To process cluster pickings directly from the _Barcode_ app, select the Batch Transfers button from the _Barcode_ dashboard. Then, select the desired batch.

On the batch transfer screen, the products in the picking are grouped by location, and each line is color-coded to associate products in the same picking together.

Then, follow the prompt to Scan the source location barcode for the storage location of the first product. Then, scan the barcode for the product and package to process the transfer.

Repeat this for all products, and click the Validate button.

Nota

To find the package barcode, navigate to Inventory app ‣ Products ‣ Packages, select the desired package, click the ⚙️ (gear) icon at the top of the package form, and select the Print option.

Next, select one of the three print options to generate the package barcode from the Package Reference field.

Example

Begin processing the cluster picking by going to the first storage location, `Shelf A`, and scanning the [location barcode](../../../barcode/setup/software.html#barcode-setup-location). Doing so highlights all the pickings that need products from this particular location.

Scan the barcode for the apple, which highlights the picking (labeled in red) for the product `Apple`, for the picking, `WH/PICK/00007`.

Then, scan the `CLUSTER-PACK-1` package barcode, and place the product in the designated package.

Suggerimento

After creating a batch transfer and assigning a package to a picking, Odoo suggests the specified package by displaying the name _in italics_ under the product name, ensuring pickers place products into the correct boxes.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/picking_methods/cluster.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](wave.html "Process wave transfers") |
  * [precedente](batch.html "Batch picking") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Picking methods](../picking_methods.html) »
  * Cluster picking


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