# Lead times — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resupply_warehouses.html "Inter-warehouse replenishment") |
  * [precedente](report.html "Replenishment report") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rifornimenti](../replenishment.html) »
  * Lead times



# Lead times¶

Accurately forecasting delivery dates is vital for fulfilling customer expectations. In Odoo, the **Inventory** app allows for comprehensive lead time configuration, allowing coordination and planning of manufacturing orders, deliveries, and receipts.

## Lead time types¶

Different lead times for different operations can impact various stages of the order fulfillment process. Here’s a summary of the types of lead times in Odoo:

  * Customer lead time: default time frame for fulfilling customer orders. The customer lead time is the number of days from the date the sales order (SO) is confirmed to the date the products are shipped from the warehouse. This is also known as _delivery lead time_.

  * Sales security lead time: moves the _scheduled delivery date_ forward by a specified number of days. This serves as a buffer to allow ample time to prepare the outgoing shipment earlier, considering the possibility of delays in the fulfillment process.

  * Purchase lead time: number of days from the confirmation of a purchase order (PO) to the receipt of products. It provides insight on the time it takes for products to arrive at the warehouse, facilitating effective scheduling and planning of supplier deliveries.

  * Purchase security lead time: advances the order deadline on a PO by a specified number of days. This proactive approach of placing orders earlier mitigates the risk of vendor or shipping delays. Thus, for products that are set to replenish to order, the need appears on the _Replenishment report_ earlier, according to the specified number of days.

  * Days to Purchase: days needed for the vendor to receive a request for quotation (RFQ) and confirm it. It advances the deadline to schedule a RFQ by a specified number of days.

  * Manufacturing lead time: number of days needed to complete a manufacturing order (MO) from the date of confirmation. This lead time includes weekends (non-working hours in Odoo), and is used to forecast an approximate production date for a finished good.

  * Days to prepare manufacturing order: number of days needed to replenish components, or manufacture sub-assemblies of the product. Either set one directly on the bill of materials (BoM), or click _Compute_ to sum up purchase and manufacturing lead times of components in the BoM.

  * Manufacturing security lead time: moves the scheduled date of the MO forward by a specified number of days. When used in conjunction with [replenish to order](../replenishment.html#inventory-management-products-strategies), the security lead time makes the need appear earlier on the replenishment report.




## Sales lead times¶

Customer lead times and sales security lead times can be configured to automatically compute an _expected delivery date_ on a SO. The expected delivery date ensures a realistic _delivery dates_ setting for shipments from the warehouse.

Odoo issues a warning message if the set delivery date is earlier than the expected date, as it may not be feasible to fulfill the order by that time, which would impact other warehouse operations.

Example

A SO containing a `Coconut-scented candle` is confirmed on July 11th. The product has a customer lead time of 14 days, and the business uses a sales security lead time of 1 day. Based on the lead time inputs, Odoo suggests a delivery date in 15 days, on July 26th.

The following sections demonstrate how to automatically compute expected delivery dates.

### Customer lead time¶

Set the customer lead time on each product form, by navigating to the products page. To do so, go to Sales app ‣ Products ‣ Products. From there, select the desired product, and switch to the Inventory tab. Then, under the Customer Lead Time field, fill in the number of calendar days required to fulfill the delivery order from start to finish.

Example

Set a 14-day customer lead time for the `Coconut-scented candle` by navigating to its product form. Then, in the Inventory tab, type `14.00` days into the Customer Lead Time field.

### Sales security lead time¶

_Sales security lead time_ is set globally for the business in Inventory app ‣ Configuration ‣ Settings.

On the configuration page, under the Advanced Scheduling heading, locate the box for Security Lead Time for Sales, and click the checkbox to enable the feature.

Next, enter the desired number of calendar days. This security lead time is a buffer notifying the team to prepare for outgoing shipments earlier than the scheduled date.

Example

Setting the Security Lead Time for Sales to `1.00` day, pushes the Scheduled Date of a delivery order (DO) forward by one day. In that case, if a product is initially scheduled for delivery on April 6th, but with a one-day security lead time, the new scheduled date for the delivery order would be April 5th.

### Deliver several products¶

For orders that include multiple products with different lead times, the lead times can be configured directly from the quotation itself. On a quotation, click the Other Info tab, and set the Shipping Policy to:

  1. As soon as possible to deliver products as soon as they are ready. The Scheduled Date of the DO is determined by adding today’s date to the shortest lead time among the products in the order.

  2. When all products are ready to wait to fulfill the entire order at once. The Scheduled Date of the DO is determined by adding today’s date to the longest lead time among the products in the order.




Example

In a quotation containing 2 products, `Yoga mat` and `Resistance band,` the products have a lead time of 8 days and 5 days, respectively. Today’s date is April 2nd.

When the Shipping Policy is set to As soon as possible, the scheduled delivery date is 5 days from today: April 7th. On the other hand, selecting When all products are ready configures the scheduled date to be 8 days from today: April 10th.

## Purchase lead times¶

Automatically determining the dates on which to place orders from suppliers can help simplify the procurement process.

Odoo calculates the supplier shipment _receipt date_ , and PO deadline, based on the required date the product is needed in the warehouse. By working backwards from the receipt date, vendor lead times and purchase security lead times are taken into account, in order to determine the PO deadline.

This deadline is the date by which the order should be confirmed, in order to ensure timely arrival by the expected receipt date.

Vedi anche

[PO scheduling with reordering rules](reordering_rules.html)

### Vendor lead time¶

To set a vendor lead time for orders arriving in the warehouse from a vendor location, begin by navigating to a product form through Purchase app ‣ Products ‣ Products.

Next, select the desired product, and switch to the Purchase tab. In the editable vendor pricelist, click the Add a line button to add vendor details, such as the Vendor name, Price offered for the product, and lastly, the Delivery Lead Time.

Nota

Multiple vendors and lead times can be added to the vendor pricelist. The default vendor and lead time selected will be the entry at the top of the list.

Example

On the vendor pricelist of the product form, the Delivery Lead Time for the selected vendor is set to `10 days.`

By setting the vendor lead time, the expected arrival date of the item is automatically determined as the date of the PO confirmation, plus the vendor lead time. This ensures that warehouse employees are notified, if the products do **not** arrive within the expected timeframe.

Example

On a PO confirmed on July 11th, for a product configured with a 10-day vendor lead time, Odoo automatically sets the Receipt Date to July 21st. The receipt date also appears as the Scheduled Date on the warehouse receipt form, accessible from the Receipt smart button, located on the PO (Purchase Order).

### Purchase security lead time¶

_Purchase security lead time_ is set globally for the business in Inventory app ‣ Configuration ‣ Settings.

On the Settings page, under the Advanced Scheduling heading, tick the checkbox for Security Lead Time for Purchase.

Next, enter the desired number of calendar days. By configuring the security lead time, a buffer is set to account for potential delays in supplier deliveries. Then, click Save.

Example

Setting the Security Lead Time for Purchase to `2.00` days, pushes the Scheduled Date of receipt back by two days. In that case, if a product is initially scheduled to arrive on April 6th, with a two-day security lead time, the new scheduled date for the receipt would be April 8th.

### Days to purchase lead time¶

To set it up, go to Inventory app ‣ Configuration ‣ Settings. Under the Advanced Scheduling section, in the Days to Purchase field, specify the number of days required for the vendor to confirm a RFQ after receiving it from the company.

## Manufacturing lead times¶

Lead times can help simplify the procurement process for consumable materials and components used in manufactured products with bills of materials (BoMs).

The MO deadline, which is the deadline to begin the manufacturing process to complete the product by the scheduled delivery date, can be determined by configuring the manufacturing lead times and manufacturing security lead times.

### Manufacturing lead time¶

Manufacturing lead times for products are configured from a product’s bill of materials (BoM) form.

To add a lead time to a BoM, navigate to Manufacturing app ‣ Products ‣ Bills of Materials, and select the desired BoM to edit.

On the BoM form, click the Miscellaneous tab. Change the value (in days) in the Manuf. Lead Time field to specify the calendar days needed to manufacture the product.

Nota

If the selected BoM is a multi-level BoM, the manufacturing lead times of the components are added.

If the BoM product is subcontracted, the Manuf. Lead Time can be used to determine the date at which components should be sent to the subcontractor.

Establish a MO deadline, based on the _expected delivery date_ , indicated in the Scheduled Date field of the DO.

The MO deadline, which is the Scheduled Date field on the MO, is calculated as the _expected delivery date_ subtracted by the manufacturing lead time.

This ensures the manufacturing process begins on time, in order to meet the delivery date.

However, it is important to note that lead times are based on calendar days. Lead times do **not** consider weekends, holidays, or _work center capacity_ (the number of operations that can be performed at the work center simultaneously).

Vedi anche

  * [Manufacturing planning](../../../manufacturing/workflows/use_mps.html)

  * [Schedule MOs with reordering rules](reordering_rules.html)




Example

A product’s scheduled shipment date on the DO is August 15th. The product requires 14 days to manufacture. So, the latest date to start the MO to meet the commitment date is August 1st.

### Days to prepare manufacturing order¶

Configure the days required to gather components to manufacture a product by going to its BoM. To do that, go to Manufacturing app ‣ Products ‣ Bills of Materials, and select the desired BoM.

In the Miscellaneous tab of the BoM, specify the calendar days needed to obtain components of the product in the Days to prepare Manufacturing Order field. Doing so creates MOs in advance, and ensures there is enough time to either replenish components, or manufacture semi-finished products.

Suggerimento

Clicking Compute, located next to the Days to prepare Manufacturing Order field, calculates the longest lead time among all the components listed on the BoM.

_Purchase security lead times_ that impact this specific BoM are also added to this value.

Example

A BoM has two components, one has a manufacturing lead time of two days, and the other has a purchase lead time of four days. The Days to prepare Manufacturing Order is four days.

### Manufacturing security lead time¶

_Manufacturing security lead time_ is set globally for the business in Manufacturing app ‣ Configuration ‣ Settings. Under the Planning heading, tick the checkbox for Security Lead Time.

Next, enter the desired number of calendar days. By configuring the security lead time, a buffer is set to account for potential delays in the manufacturing process. Then, click Save.

Example

A product has a scheduled shipment date on the DO set for August 15th. The manufacturing lead time is 7 days, and manufacturing security lead time is 3 days. So, the Scheduled Date on the MO reflects the latest date to begin the manufacturing order. In this example, the planned date on the MO is August 5th.

## Global example¶

See the following example to understand how all the lead times work together to ensure timely order fulfillment:

  * **Sales security lead time** : 1 day

  * **Manufacturing security lead time** : 2 days

  * **Manufacturing lead time** : 3 days

  * **Purchase security lead time** : 1 day

  * **Vendor lead time** : 4 days




The customer places an order for a manufactured product on September 1st, and the scheduled delivery date from the warehouse is on September 20th. Odoo uses lead times and automated reordering rules to schedule the necessary operations, based on the outgoing shipment delivery date, September 20th:

  * **September 1st** : Sales order created, confirmed by salesperson.

  * **September 9th** : Deadline to order components to ensure they arrive in time when manufacturing begins (4-day supplier lead time).

  * **September 13th** : Scheduled date of receipt for components. Initially, it was set to 9/14, but the 1-day purchase security lead time pushed the date earlier by 1 day.

  * **September 14th** : Deadline to begin manufacturing. Calculated by subtracting the manufacturing lead time of 3 days, and the manufacturing security lead time of 2 days, from the expected delivery date of September 19th.

  * **September 19th** : Scheduled Date on the delivery order form indicates the updated expected delivery date, which was originally set as September 20th. But the sales security lead time pushed the date forward by a day.




Odoo’s replenishment planning maps a business” order fulfillment process, setting pre-determined deadlines and raw material order dates, including buffer days for potential delays. This ensures products are delivered on time.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/replenishment/lead_times.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resupply_warehouses.html "Inter-warehouse replenishment") |
  * [precedente](report.html "Replenishment report") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rifornimenti](../replenishment.html) »
  * Lead times


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
  *[API]: Application programming interface
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
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: sales orders
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
  *[BOM]: Bill of Materials
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