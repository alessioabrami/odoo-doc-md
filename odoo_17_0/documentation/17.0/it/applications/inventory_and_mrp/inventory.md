# Magazzino — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](inventory/product_management.html "Product management") |
  * [precedente](../inventory_and_mrp.html "Supply Chain") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Supply Chain](../inventory_and_mrp.html) »
  * Magazzino



# Magazzino¶

Odoo _Inventory_ is both an inventory application and a warehouse management system. The app allows users to easily manage lead times, automate replenishment, configure advanced routes, and more.

Vedi anche

  * [Odoo Tutorials: Inventory](https://www.odoo.com/slides/inventory-24)




  * Product management
    * [Configure product](inventory/product_management/configure.html)
      * [Product type](inventory/product_management/configure/type.html)
      * [Unità di misura](inventory/product_management/configure/uom.html)
      * [Colli](inventory/product_management/configure/package.html)
      * [Imballaggio](inventory/product_management/configure/packaging.html)
    * [Product tracking](inventory/product_management/product_tracking.html)
      * [Use serial numbers to track products](inventory/product_management/product_tracking/serial_numbers.html)
      * [Assign serial numbers](inventory/product_management/product_tracking/create_sn.html)
      * [Numeri lotto](inventory/product_management/product_tracking/lots.html)
      * [Reassign lot/serial numbers](inventory/product_management/product_tracking/reassign.html)
      * [Expiration dates](inventory/product_management/product_tracking/expiration_dates.html)
    * Valutazione dell’inventario
      * [Automatic inventory valuation](inventory/product_management/inventory_valuation/inventory_valuation_config.html)
      * [Using inventory valuation](inventory/product_management/inventory_valuation/using_inventory_valuation.html)
      * [Landed costs](inventory/product_management/inventory_valuation/landed_costs.html)
  * Warehouses and storage
    * [Inventory management](inventory/warehouses_storage/inventory_management.html)
      * [Magazzini](inventory/warehouses_storage/inventory_management/warehouses.html)
      * [Ubicazioni](inventory/warehouses_storage/inventory_management/use_locations.html)
      * [Inventory adjustments](inventory/warehouses_storage/inventory_management/count_products.html)
      * [Cycle counts](inventory/warehouses_storage/inventory_management/cycle_counts.html)
      * [Scrap inventory](inventory/warehouses_storage/inventory_management/scrap_inventory.html)
    * [Rifornimenti](inventory/warehouses_storage/replenishment.html)
      * [Replenish on order (MTO)](inventory/warehouses_storage/replenishment/mto.html)
      * [Reordering rules](inventory/warehouses_storage/replenishment/reordering_rules.html)
      * [Replenishment report](inventory/warehouses_storage/replenishment/report.html)
      * [Lead times](inventory/warehouses_storage/replenishment/lead_times.html)
      * [Inter-warehouse replenishment](inventory/warehouses_storage/replenishment/resupply_warehouses.html)
    * Rendiconto
      * [Stock report](inventory/warehouses_storage/reporting/stock.html)
      * [Locations dashboard](inventory/warehouses_storage/reporting/locations.html)
      * [Moves history dashboard](inventory/warehouses_storage/reporting/moves_history.html)
      * [Inventory aging report](inventory/warehouses_storage/reporting/aging.html)
  * Shipping and receiving
    * [Inbound and outbound flows](inventory/shipping_receiving/daily_operations.html)
      * [Routes and push/pull rules](inventory/shipping_receiving/daily_operations/use_routes.html)
      * [One-step receipt and delivery](inventory/shipping_receiving/daily_operations/receipts_delivery_one_step.html)
      * [Two-step receipt and delivery](inventory/shipping_receiving/daily_operations/receipts_delivery_two_steps.html)
      * [Three-step receipt](inventory/shipping_receiving/daily_operations/receipts_three_steps.html)
      * [Three-step delivery](inventory/shipping_receiving/daily_operations/delivery_three_steps.html)
      * [Putaway rules](inventory/shipping_receiving/daily_operations/putaway.html)
      * [Storage categories](inventory/shipping_receiving/daily_operations/storage_category.html)
      * [Organize a cross-dock in a warehouse](inventory/shipping_receiving/daily_operations/cross_dock.html)
      * [Sell stock from multiple warehouses using virtual locations](inventory/shipping_receiving/daily_operations/stock_warehouses.html)
      * [Consignment: buy and sell stock without owning it](inventory/shipping_receiving/daily_operations/owned_stock.html)
      * [Dropshipping](inventory/shipping_receiving/daily_operations/dropshipping.html)
    * [Delivery methods](inventory/shipping_receiving/setup_configuration.html)
      * [Third-party shipping carriers](inventory/shipping_receiving/setup_configuration/third_party_shipper.html)
      * [Print shipping labels](inventory/shipping_receiving/setup_configuration/labels.html)
      * [Bpost integration](inventory/shipping_receiving/setup_configuration/bpost.html)
      * [DHL integration](inventory/shipping_receiving/setup_configuration/dhl_credentials.html)
      * [FedEx integration](inventory/shipping_receiving/setup_configuration/fedex.html)
      * [Sendcloud integration](inventory/shipping_receiving/setup_configuration/sendcloud_shipping.html)
      * [Starshipit shipping](inventory/shipping_receiving/setup_configuration/starshipit_shipping.html)
      * [UPS integration](inventory/shipping_receiving/setup_configuration/ups_credentials.html)
      * [Zebra label configuration](inventory/shipping_receiving/setup_configuration/zebra.html)
      * [How to cancel a shipping request to a shipper?](inventory/shipping_receiving/setup_configuration/cancel.html)
      * [Shipping cost invoicing](inventory/shipping_receiving/setup_configuration/invoicing.html)
      * [Change shipping label size](inventory/shipping_receiving/setup_configuration/label_type.html)
      * [Multi-package shipments](inventory/shipping_receiving/setup_configuration/multipack.html)
      * [Printable delivery PDFs](inventory/shipping_receiving/setup_configuration/print_on_validation.html)
    * [Reservation methods](inventory/shipping_receiving/reservation_methods.html)
      * [At confirmation reservation](inventory/shipping_receiving/reservation_methods/at_confirmation.html)
      * [Manual reservation](inventory/shipping_receiving/reservation_methods/manually.html)
      * [Before scheduled date reservation](inventory/shipping_receiving/reservation_methods/before_scheduled_date.html)
    * Picking methods
      * [Batch picking](inventory/shipping_receiving/picking_methods/batch.html)
      * [Cluster picking](inventory/shipping_receiving/picking_methods/cluster.html)
      * [Process wave transfers](inventory/shipping_receiving/picking_methods/wave.html)
    * [Removal strategies](inventory/shipping_receiving/removal_strategies.html)
      * [FIFO removal](inventory/shipping_receiving/removal_strategies/fifo.html)
      * [LIFO removal](inventory/shipping_receiving/removal_strategies/lifo.html)
      * [FEFO removal](inventory/shipping_receiving/removal_strategies/fefo.html)
      * [Closest location removal](inventory/shipping_receiving/removal_strategies/closest_location.html)
      * [Least packages removal](inventory/shipping_receiving/removal_strategies/least_packages.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](inventory/product_management.html "Product management") |
  * [precedente](../inventory_and_mrp.html "Supply Chain") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Supply Chain](../inventory_and_mrp.html) »
  * Magazzino


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
  *[MPS]: Master Production Schedules
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
  *[SO]: Sales order
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
  *[SOs]: Sales Order
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