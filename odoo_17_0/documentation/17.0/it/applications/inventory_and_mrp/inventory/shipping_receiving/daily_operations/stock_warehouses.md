# Sell stock from multiple warehouses using virtual locations — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](owned_stock.html "Consignment: buy and sell stock without owning it") |
  * [precedente](cross_dock.html "Organize a cross-dock in a warehouse") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Sell stock from multiple warehouses using virtual locations



# Sell stock from multiple warehouses using virtual locations¶

While keeping stock and selling inventory from one warehouse might work for smaller companies, bigger companies might need to keep stock in, or sell from, multiple warehouses in multiple locations.

Sometimes products included in a single sales order might take stock from two (or more) warehouses; in Odoo, pulling products from multiple warehouses to satisfy sales demands can be done using _virtual locations_.

Importante

The solution in this document, describing the use of a virtual warehouse to fulfill orders for multiple warehouses, has some limitations. Consider the following before proceeding:

  1. When the Warehouse field is set to a virtual warehouse on a sales order, the virtual warehouse’s address is indicated on the picking, packing, and delivery forms, **not** the actual warehouse’s address.

  2. Each location has a `warehouse_id` (hidden field). This means that the stock in the virtual warehouse will **not** be the sum of the stock of the real warehouses, but rather the sum of the stock in the locations whose warehouse ID is the virtual warehouse.




Pericolo

Potential limitation for those using [two](receipts_delivery_two_steps.html) or [three-step delivery](delivery_three_steps.html):

  1. The output or packing zone on the various forms is incorrectly listed as the virtual warehouse’s address.

  2. There is no workaround for two or three-step deliveries.

  3. Proceed **only** if setting a virtual warehouse’s address as the output or packing zone makes sense for the company’s workflow.




Nota

In order to create virtual locations in warehouses, and proceed to the following steps, the Storage Locations and Multi-Step Routes features **must** be enabled.

To do so, go to Inventory app ‣ Configuration ‣ Settings, scroll down to the Warehouse section, and enable the Storage Locations and Multi-Step Routes options. Then, Save the changes to finish.

## Create virtual parent location¶

Before creating any virtual stock locations, create a new warehouse that acts as a _virtual_ warehouse — the _parent_ location of other physical warehouses.

Why a "virtual" warehouse?

Virtual warehouses are great for companies with multiple physical warehouses. This is because a situation might arise when one warehouse runs out of stock of a particular product, but another warehouse still has stock on-hand. In this case, stock from these two (or more) warehouses could be used to fulfill a single sales order.

The «virtual» warehouse acts as a single aggregator of all the inventory stored in a company’s physical warehouses, and is used (for traceability purposes) to create a hierarchy of locations in Odoo.

To create a new warehouse, go to Inventory app ‣ Configuration ‣ Warehouses, and click Create. From here, the warehouse Name and Short Name can be changed, and other warehouse details can be changed under the Warehouse Configuration tab.

Lastly, click Save to finish creating a _regular_ warehouse. Continue following the steps below to finish configuring the virtual parent warehouse.

Vedi anche

  * [Warehouse configurations](../../warehouses_storage/inventory_management/warehouses.html)

  * [Incoming and outgoing shipments](receipts_delivery_one_step.html#inventory-receipts-delivery-one-step-wh)

  * [Inter-warehouse replenishment](../../warehouses_storage/replenishment/resupply_warehouses.html)




## Create child warehouses¶

Create at least two _child_ warehouses to link to the virtual warehouse.

Importante

In order to take stock from multiple warehouses to fulfill a sales order, there needs to be at least **two** warehouses acting as child locations of the virtual parent location warehouse.

To do that, navigate to Inventory app ‣ Configuration ‣ Warehouses, click Create, and follow the preceding instructions to configure the physical stock locations.

Example

**Parent Warehouse**

Warehouse: `Virtual Warehouse`

Location: `VWH/Stock`

**Child Warehouses**

Warehouses: `Warehouse A` and `Warehouse B`

Locations: `WHA` and `WHB`

Importante

While the virtual stock location will be changed to “View” later, the Location Type **must** be Internal Location at this point to link the child warehouses in the next section.

## Link child warehouses to virtual stock¶

To set physical warehouses as child locations of the virtual location configured in the previous step, navigate to Inventory app ‣ Configuration ‣ Locations.

Remove any filters from the search bar. Then, click the physical warehouse Location that was previously created to be a child location (e.g. `WHA`), and click Edit.

Change the Parent Location field from Physical Locations to the virtual warehouse’s **stock location** (e.g. `VWH/Stock`) from the drop-down menu, and click Save.

Importante

To select the virtual warehouse’s stock location in the Parent Location drop-down menu, the parent warehouse stock location (e.g. `VWH/Stock`) **must** have its Location Type set to Internal Location.

Repeat the preceding steps to configure two or more child warehouses.

Once complete, the virtual, parent warehouse (e.g. `VWH/Stock`) fulfills orders using stock from child warehouses (e.g. `WHA` and `WHB`), if there is insufficient stock in any one location.

## Set virtual stock location as “view”¶

Set the virtual stock location’s Location Type to View, as it is a non-existent location used to group various physical warehouses together.

To do that, navigate to Inventory app ‣ Configuration ‣ Locations.

Click the virtual warehouse’s stock location (e.g. `VWH/Stock`) that was previously created, from the Locations list.

On the location form, under the Additional Information heading, set the Location Type to View. Save the changes.

Suggerimento

To view the total quantity across **all** linked child warehouses, go to the product form and click the On Hand smart button.

## Example: sell products from a virtual warehouse¶

To sell products from multiple warehouses using a virtual parent location, the database must have at least **two** warehouses configured — with at least **one** product, with quantity on-hand in each warehouse, respectively.

Example

The following product, `Toy soldier`, is available at each location with the quantities:

  * `WHA/Stock` : 1

  * `WHB/Stock` : 2

  * Warehouses `WHA` and `WHB` are child warehouses of the virtual warehouse `VWH`.




Create a quotation for the product by navigating to the Sales app and clicking Create. On the quote, add a Customer, and click Add a product to add the two products stored in the two warehouses.

Then, click the Other Info tab on the sales order form. Under the Delivery section, change the Warehouse field value to the virtual warehouse that was previously created. Next, Confirm the sales order.

Then, click the Delivery smart button. From the warehouse delivery form, confirm that the Source Location value matches the Warehouse field value from the sales order. Both should list the virtual warehouse location.

Finally, on the warehouse delivery form, under the Detailed Operations tab, confirm that the Locations in the From column for each product match the child locations that are tied to the virtual parent location.

Importante

> The Source Location on the warehouse delivery form, and the Warehouse under the Other Info tab on the sales order, **must** match for products in the sales order to be pulled from different warehouses.

  * If the virtual warehouse is not in the Source Location field on the warehouse delivery form, retry product reservation by:

    * Running the scheduler: turn on [developer mode](../../../../general/developer_mode.html#developer-mode), and then go to Inventory app ‣ Operations ‣ Run Scheduler.

    * Clicking Check Availability on the delivery order.

  * If the virtual warehouse is **not** assigned to the Warehouse field on the sales order, then cancel it, and create a new sales order with the virtual warehouse set in the Warehouse field.

  * If the Warehouse field is missing on the sales order form, then the multiple child warehouses may not have been set up correctly. Review the previous section to ensure the correct settings.




Suggerimento

To use a virtual _parent_ location as the default warehouse for sales orders, each salesperson should have the virtual warehouse assigned to them from the drop-down menu next to Default Warehouse on their employee form.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations/stock_warehouses.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](owned_stock.html "Consignment: buy and sell stock without owning it") |
  * [precedente](cross_dock.html "Organize a cross-dock in a warehouse") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Sell stock from multiple warehouses using virtual locations


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