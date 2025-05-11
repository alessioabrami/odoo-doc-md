# Shipping and receiving — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shipping_receiving/daily_operations.html "Inbound and outbound flows") |
  * [precedente](warehouses_storage/reporting/aging.html "Inventory aging report") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Magazzino](../inventory.html) »
  * Shipping and receiving



# Shipping and receiving¶

  * [Inbound and outbound flows](shipping_receiving/daily_operations.html)
    * [Routes and push/pull rules](shipping_receiving/daily_operations/use_routes.html)
    * [One-step receipt and delivery](shipping_receiving/daily_operations/receipts_delivery_one_step.html)
    * [Two-step receipt and delivery](shipping_receiving/daily_operations/receipts_delivery_two_steps.html)
    * [Three-step receipt](shipping_receiving/daily_operations/receipts_three_steps.html)
    * [Three-step delivery](shipping_receiving/daily_operations/delivery_three_steps.html)
    * [Putaway rules](shipping_receiving/daily_operations/putaway.html)
    * [Storage categories](shipping_receiving/daily_operations/storage_category.html)
    * [Organize a cross-dock in a warehouse](shipping_receiving/daily_operations/cross_dock.html)
    * [Sell stock from multiple warehouses using virtual locations](shipping_receiving/daily_operations/stock_warehouses.html)
    * [Consignment: buy and sell stock without owning it](shipping_receiving/daily_operations/owned_stock.html)
    * [Dropshipping](shipping_receiving/daily_operations/dropshipping.html)
  * [Delivery methods](shipping_receiving/setup_configuration.html)
    * [Third-party shipping carriers](shipping_receiving/setup_configuration/third_party_shipper.html)
    * [Print shipping labels](shipping_receiving/setup_configuration/labels.html)
    * [Bpost integration](shipping_receiving/setup_configuration/bpost.html)
    * [DHL integration](shipping_receiving/setup_configuration/dhl_credentials.html)
    * [FedEx integration](shipping_receiving/setup_configuration/fedex.html)
    * [Sendcloud integration](shipping_receiving/setup_configuration/sendcloud_shipping.html)
    * [Starshipit shipping](shipping_receiving/setup_configuration/starshipit_shipping.html)
    * [UPS integration](shipping_receiving/setup_configuration/ups_credentials.html)
    * [Zebra label configuration](shipping_receiving/setup_configuration/zebra.html)
    * [How to cancel a shipping request to a shipper?](shipping_receiving/setup_configuration/cancel.html)
    * [Shipping cost invoicing](shipping_receiving/setup_configuration/invoicing.html)
    * [Change shipping label size](shipping_receiving/setup_configuration/label_type.html)
    * [Multi-package shipments](shipping_receiving/setup_configuration/multipack.html)
    * [Printable delivery PDFs](shipping_receiving/setup_configuration/print_on_validation.html)
  * [Reservation methods](shipping_receiving/reservation_methods.html)
    * [At confirmation reservation](shipping_receiving/reservation_methods/at_confirmation.html)
    * [Manual reservation](shipping_receiving/reservation_methods/manually.html)
    * [Before scheduled date reservation](shipping_receiving/reservation_methods/before_scheduled_date.html)
  * Picking methods
    * [Batch picking](shipping_receiving/picking_methods/batch.html)
    * [Cluster picking](shipping_receiving/picking_methods/cluster.html)
    * [Process wave transfers](shipping_receiving/picking_methods/wave.html)
  * [Removal strategies](shipping_receiving/removal_strategies.html)
    * [FIFO removal](shipping_receiving/removal_strategies/fifo.html)
    * [LIFO removal](shipping_receiving/removal_strategies/lifo.html)
    * [FEFO removal](shipping_receiving/removal_strategies/fefo.html)
    * [Closest location removal](shipping_receiving/removal_strategies/closest_location.html)
    * [Least packages removal](shipping_receiving/removal_strategies/least_packages.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shipping_receiving/daily_operations.html "Inbound and outbound flows") |
  * [precedente](warehouses_storage/reporting/aging.html "Inventory aging report") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Magazzino](../inventory.html) »
  * Shipping and receiving


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