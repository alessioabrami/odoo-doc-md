# Lead times — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resupply_warehouses.html "Inter-warehouse replenishment") |
  * [precedente](report.html "Replenishment report") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
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

Automatically scheduling supplier orders streamlines procurement by showing users exactly when to confirm a request for quotation (RFQ) and when to expect the goods.

Key dates on an RFQ / PO¶ Field | Description  
---|---  
Order Deadline | Last calendar day to confirm the RFQ and convert it to a PO  
Expected Arrival | Arrival date of the products. Calculated by _Order Deadline_ \+ _Vendor Lead Time_  
  
In addition, Odoo has global security lead times, which are buffers that widen the [just-in-time](reordering_rules.html#inventory-warehouses-storage-just-in-time) (JIT) forecast window. The security lead times affect **only** replenishment methods that use [pull rules](../../shipping_receiving/daily_operations/use_routes.html)—for example [reordering rules](reordering_rules.html) or [make to order (MTO)](mto.html). They do not change the interval between _Order Deadline_ and _Expected Arrival_.

Vedi anche

[PO scheduling with reordering rules](reordering_rules.html)

Global security lead time buffers¶ Buffer | Scopo | Impact on dates  
---|---|---  
Purchase Security Lead Time | Extra calendar days to account for delays. Typically used to account for weekends or holidays. | None on the RFQ/PO; adds buffer days in the [JIT forecast window](reordering_rules.html#inventory-warehouses-storage-forecasted-date).  
Days to Purchase | Days the vendor needs to review an RFQ after it is sent. | None on the RFQ/PO; adds buffer days in the [JIT forecast window](reordering_rules.html#inventory-warehouses-storage-forecasted-date).  
  
Example

To tie all the purchase lead times together, consider this:

  * Today: April 21

  * Vendor Lead Time: 1 day

  * Purchase Security Lead Time: 4 days

  * Days to Purchase: 2 days




Days from today = 1 + 4 + 2 = 7

Forecasted date = April 28

Example of the JIT forecast window, which is April 21-28.¶

If an RFQ is created today, the following fields show:

  * Order Deadline: April 23 (\\(\text{Today} + 2\\))

  * Expected Arrival: April 24 (\\(\text{Order Deadline} + 1\\))




### Vendor lead time¶

To set a vendor lead time for orders arriving in the warehouse from a vendor location, begin by navigating to a product form through Purchase app ‣ Products ‣ Products.

Next, select the desired product, and switch to the Purchase tab. In the editable vendor pricelist, click the Add a line button to add vendor details, such as the Vendor name, Price offered for the product, and lastly, the Delivery Lead Time.

Nota

Multiple vendors and lead times can be added to the vendor pricelist. The default vendor and lead time selected is the entry at the top of the list.

Suggerimento

A PO is marked late if the _Expected Arrival_ date has passed, and appears in the _Late_ box on the **Purchase** app’s dashboard.

Example

On the vendor pricelist of the product form, the Delivery Lead Time for the selected vendor is set to `10 days.`

### Purchase security lead time¶

_Purchase security lead time_ is a global buffer to account for delays, applied to **all** vendors. To set it, go to Inventory app ‣ Configuration ‣ Settings.

Under Advanced Scheduling, tick the Security Lead Time for Purchase checkbox.

Next, enter the desired number of calendar days. By configuring the security lead time, a buffer is set to account for potential delays in supplier deliveries. Then, click Save.

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

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/replenishment/lead_times.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resupply_warehouses.html "Inter-warehouse replenishment") |
  * [precedente](report.html "Replenishment report") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
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
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: request for quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application programming interface
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost
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
  *[RUT]: Rol Único Tributario
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
  *[MOs]: manufacturing orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: purchase order
  *[MTO]: Make to Order
  *[SVLs]: stock move layers
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
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time