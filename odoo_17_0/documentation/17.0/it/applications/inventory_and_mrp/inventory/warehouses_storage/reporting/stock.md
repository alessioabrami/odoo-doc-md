# Stock report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](locations.html "Locations dashboard") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Stock report



# Stock report¶

Use the stock report in Odoo _Inventory_ for a detailed list of all stored products, including those reserved, purchased and in transit, as well as those delivered to customers.

Nota

The reporting feature is only accessible to users with [admin access](../../../../general/users/access_rights.html).

To access the stock report, go to Inventory app ‣ Reporting ‣ Stock.

## Navigate the stock report¶

On the stock report, the left sidebar includes several groupings to narrow down what is being shown. The default groupings are Warehouses, which filters products by specific warehouses, and Category, which shows products within a selected product category.

Nota

The Warehouse grouping is only available when there are multiple warehouses in the database. Refer to the [Magazzini](../inventory_management/warehouses.html) documentation for more details.

In the report itself, the columns represent:

  * Product: name of the product.

  * Unit Cost: average inventory valuation per unit, adjusted based on the cost to purchase and/or manufacture the product.

  * Total Value: Total inventory valuation of the product, calculated by multiplying unit cost by on-hand quantity.

Vedi anche

    * [Compute average cost inventory valuation per unit](../../../../finance/accounting/get_started/avg_price_valuation.html#inventory-avg-cost-formula)

    * [Inventory valuation methods](../../product_management/inventory_valuation/inventory_valuation_config.html)

  * On Hand: current quantity of products. Click the __(pencil) icon to [modify the on-hand quantity](../inventory_management/count_products.html).

  * Free to Use: on-hand quantity that are **not** reserved for delivery or manufacturing orders, and are available to sell or use.

  * Incoming: items expected to arrive at the warehouse. Number of products is based on quantities in confirmed purchase orders.

  * Outgoing: items expected to leave the warehouse or be consumed in manufacturing orders. Number of products is based on quantities in confirmed sales or manufacturing orders.




Click the buttons to the right of each row item to access additional information:

  * History: access the stock move history of the product, displaying information about the quantity and description of why the product was moved from one location to another.

  * Replenishment: access the [reordering rules](../replenishment/reordering_rules.html) page for the product to create or manage methods of procuring the product.

  * Locations: break down of on-hand quantity at multiple storage locations. Only available when the product is stored in multiple locations.

  * Forecast: access the forecasted report to view on-hand, incoming, and outgoing quantities. Report also contains links to confirmed purchase, sales, or manufacturing orders. Only available when there are confirmed sales, purchase, or manufacturing orders for the product.




### Opzioni di ricerca¶

FiltersGroup ByFavorites

The Filters section allows users to search among pre-made and custom filters to find specific stock records.

  * Published: display products published on the website. Only available with the _Website_ app installed.

  * Available in POS: display products available through the _Point of Sale_ app.

  * Available in Self: display products available in self order through the _Point of Sale_ app. Appears in the search because the Available in Self Order checkbox was ticked in the Point of Sale section of a product form’s Sales tab. The option is only available when the Available in POS checkbox is ticked.

  * Not available in Self: display products available in _PoS_ , but not available in self order.




Vedi anche

[Configure PoS products](https://youtu.be/REbA3TBhFa4)

  * Can be Sold: display products that can be sold to customers. Appears in the search because the Can be Sold checkbox is ticked on the product form.

  * Can be Purchased: display products that can be bought from vendors. Appears in the search because the Can be Purchased checkbox is ticked on the product form.

  * Can be Recurring: show subscription products, indicated by ticking the Recurring checkbox on the product form. Only available with the _Subscription_ app activated.

  * Can be Rented: show products that can be loaned to customers for a certain time. Appears in the search because the Can be Rented checkbox was ticked on the product form. Only available with the _Rental_ app installed.

  * Can be Subcontracted: display products that can be produced by a [third-party manufacturer](../../../manufacturing/subcontracting/subcontracting_basic.html). Available only with the _Manufacturing_ app installed.

  * Can be Expensed: show items that can be expensed. Only available with the _Expenses_ app installed.




Vedi anche

[Product type](../../product_management/configure/type.html)

The Group By section allows users to add pre-made and custom groupings to the search results.

  * Product Type: group items by [product type](../../product_management/configure/type.html).

  * Product Category: group items by product category. To configure these, go to Inventory app ‣ Configuration ‣ Products: Product Categories.

  * POS Product Category: group items by [point of sale product categories](../../../../sales/point_of_sale/configuration.html).




To save the current applied filters and groupbys, so the same information can be easily accessed after closing this page, click Save current search.

Optionally, tick the Default filter checkbox to make this current view the default filter when opening the stock report. Or tick the Shared checkbox to make the search option available to other users.

Lastly, click the Save button.

Vedi anche

[Cercare, filtrare e raggruppare i record](../../../../essentials/search.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/reporting/stock.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](locations.html "Locations dashboard") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Stock report


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
  *[MTO]: Make to Oder
  *[SVLs]: stock valuation layers