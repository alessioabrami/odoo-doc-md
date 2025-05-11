# Stock valuation dashboard — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../shipping_receiving.html "Shipping and receiving") |
  * [precedente](moves_history.html "Moves history dashboard") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Stock valuation dashboard



# Stock valuation dashboard¶

When a company has physical assets, such as inventory, they often want to know approximately how much has been spent on these goods, or how much they are worth at the moment. This process of assigning a monetary value to account for inventory is known as _stock valuation_.

This value is often reported for accounting purposes. For instance, an insurance company may want to know the value of goods stored in a warehouse, in the event of a flood or fire.

[Stock valuation](../../product_management/inventory_valuation/using_inventory_valuation.html) typically utilizes one of two accounting systems:

  * **Perpetual** : The inventory is constantly (perpetually) being updated, and the value is constantly changing.

  * **Periodic** : The inventory value is checked on an occasional (periodic) basis, and the value is set at this occasional time.




Using [tracked inventory](../../product_management/configure/type.html#inventory-product-management-tracking-inventory) in Odoo necessitates a _perpetual_ inventory accounting system because of the need to know when and where inventory exists, and how much of it is available or forecasted. There are a few common [stock valuation methods](../../product_management/inventory_valuation/inventory_valuation_config.html#inventory-warehouses-storage-costing-methods) used in Odoo: _standard price_ , _average cost_ (AVCO), and _first in, first out_ (FIFO) accounting. It is important to know that the valuation method chosen for a product impacts the calculation of several fields in the stock valuation reports.

## Open the dashboard¶

Odoo’s _Stock Valuation_ dashboard displays the financial value of all tracked inventory, according to each product’s stock valuation method. This report can provide insights into potential issues in the supply chain, such as sunken purchase costs or delays in profitability. To access the dashboard, go to Inventory app ‣ Reporting ‣ Valuation.

Importante

The Reporting menu in **Inventory** is only accessible to users with [admin access](../../../../general/users/access_rights.html).

This dashboard has three different views, or inventory reports — list view (i.e. the default stock valuation report), pivot view (i.e. the stock aging report), and graph view. Each view can be customized with different fields to break down inventory valuation by product, operation type, date, or company.

All three views can be filtered by various fields. To apply filters, click into the search bar at the top of the report, or click the drop-down arrow next to it. For example, selecting the filter Has Remaining Qty will show only products that are currently in stock.

## List view: stock valuation¶

By default, the Stock Valuation dashboard displays in _list view_ , represented by the __(list) icon. This report shows a detailed record of stock movements and their valuations.

### Configura¶

The following columns are displayed by default:

  * Date: the date and time when the stock move was created. The valuation report is sorted by this field by default, emphasizing the importance of time when valuing inventory. To sort the report by a different column, simply click on the column title.

  * Reference: the reference document associated with this stock move (e.g., a warehouse receipt, a delivery order, or a manual inventory adjustment).

  * Product: the product that is being moved and valued.

  * Quantity: the number of units by which this product’s stock has increased or decreased in this particular stock move.

  * Total Value: the value of the product’s stock in this particular stock move, calculated by multiplying the Quantity and Unit Value.




Nota

If a Reference document includes several goods, there will be a separate line item generated on the report for each good.

There are additional fields that can be added to this view to provide more insight into the stock’s valuation. To add fields, click the __(adjust) icon, and select the desired fields:

  * Lot/Serial Number: the uniquely identifying lot or serial number for this product.

  * Company: for businesses that operate with multiple companies, this field displays the company by which this stock move took place.

  * Remaining Quantity: the number of units remaining for this valuation of the product, after demand has been accounted for (even from other stock moves). This field can be especially helpful for FIFO and AVCO accounting, as it conveys which units of stock came into a warehouse first and the value of said stock.

  * Unit Value: the cost of one unit of the product for the company (**not** the price to consumers).

  * Description: a description of the reason for this stock valuation (typically, a stock move has occurred). By default, this field is set as the concatenation of the Reference and Product fields. However, the field may also display other important messages for this line item, such as a note stating that the line item is an adjustment due to a change in the product’s inventory valuation method.

  * Remaining Value: the value of this product’s current stock levels for this particular stock move, after demand has been accounted for. Along with Remaining Quantity, this field can be especially helpful for FIFO and AVCO accounting, as they convey which stock came into a warehouse first and the value of said stock.




Suggerimento

Some of these settings may not appear unless first enabled in **Settings** application.

### Stock valuation layers (SVLs)¶

Each line item in the Stock Valuation report represents a record in Odoo’s system known as a _stock valuation layer (SVL)_. SVLs are generated when products move in a way that impacts their stock valuation. Specifically, the stock moves that generate SVLs are warehouse receipts, deliveries, dropshipping orders, and dropshipping returns. These stock moves must first be validated (by clicking the Validate button) for the SVL to be created.

If a product’s inventory valuation method changes on the product form, new line items are generated on the Stock Valuation report to reflect the resulting SVLs. For example, if the valuation method changes from _standard price_ to either AVCO or FIFO accounting, _revaluation entries_ will be automatically posted to reflect the change in pricing for goods that remain in stock. One entry will be negative to «remove» the old pricing, and the second entry will be positive to record the new pricing. These entries are connected to journal entries in Odoo’s **Accounting** app.

Below is an example of what the Stock Valuation table shows when a few stock moves have occurred for a product using standard price accounting.

Conversely, the following image depicts what the _Stock Valuation_ Report table might look like after a product has switched from standard price to FIFO accounting.

Example

The Remaining Value and Remaining Quantity fields are derived from what occurs at the SVL level in Odoo and, as such, are better understood with an example.

Frankie’s Consignment Shop buys sweaters at the cost, or Unit Value, of `5.00` dollars. For the first time, Frankie’s purchases and receives a Quantity of `100.00` sweaters in one stock move, then re-sells and delivers `-10.00` sweaters in a second stock move.

In the first stock move line item, the Remaining Quantity will change from `100.00` to `90.00`, once the second stock move is recorded. This change reflects that, although 100 sweaters were originally purchased, only 90 of those sweaters remain in stock and should be counted in the valuation. Similarly, the Remaining Value will drop from `$500.00` to `$450.00`. The Total Value will remain at `$500.00`, regardless of subsequent transactions.

On the other hand, the Remaining Quantity of the second stock move line item will be recorded and remain at `0.00` because the quantity of `-10.00` was sold. In the system, because the SVL was a sale, there is no stock left that needs to be valued from that transaction.

### Change the valuation date¶

To see the valuation of stock moves at a specific date and time, click the Valuation At Date button, located in the top-left corner of the Stock Valuation page. The report will show the Quantity and Total Value of each stock move.

Nota

The Remaining Quantity and Remaining Value of the stock moves will _not_ be point-in-time for any dates chosen in the past. The stock moves shown when selecting a past date will still display the _current on-hand quantity and value_ of the products.

Example

A business has 100 sofas in stock on January 1st and sells 20 of those sofas on February 1st. The Remaining Quantity of the SVL will drop from `100.00` to `80.00` on February 1st. If no other stock moves take place, and on February 1st, the Valuation at Date is selected as January 1st, the Remaining Quantity will still show as `80.00`.

## Pivot view: stock aging¶

From the Stock Valuation dashboard, access pivot view by clicking the __(pivot) icon. This view is essentially a _stock aging report_ , and it shows the on-hand quantity and value of inventory by purchase date, which can help monitor products with expiration dates.

### Configura¶

By default, the pivot view shows the value of all _product categories_ by _day and month_. Clicking the __(plus) icon in each column or row will reveal a drop-down list of options to create a more granular breakdown of the inventory valuation. The drop-down options include: Product, Lot/Serial Number, Product Category, Date, Company, or Add Custom Group Clicking the __(minus) icon collapses the field back to an empty state.

In the table, the Remaining Qty column displays the number of on-hand items, and Remaining Value displays the total cost of purchasing these items.

## Vista grafico¶

The stock value can be depicted graphically by clicking the __(graph) icon. By default, the graph is displayed in __line chart view and filtered to show the cumulative total of all inventory value over time in Odoo.

At the top of the report, a __bar chart or __pie chart view can be selected instead.

Vedi anche

[Odoo reporting essentials](../../../../essentials/reporting.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/reporting/aging.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../shipping_receiving.html "Shipping and receiving") |
  * [precedente](moves_history.html "Moves history dashboard") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Stock valuation dashboard


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
  *[MTO]: Make to Oder
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