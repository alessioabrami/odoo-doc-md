# Inbound and outbound flows — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](daily_operations/use_routes.html "Routes and push/pull rules") |
  * [precedente](../shipping_receiving.html "Shipping and receiving") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Inbound and outbound flows



# Inbound and outbound flows¶

Configuring inbound and outbound flows in Odoo is key to optimizing efficiency, traceability, and cost. Warehouse managers must balance speed and control, choosing between a streamlined process or added checkpoints.

Odoo offers one-step, two-step, and three-step flows, with more steps providing greater control but increasing operations. The best setup depends on quality checks, packaging, and warehouse size.

This guide helps businesses determine the most suitable configuration.

## One-step flow¶

The _one-step inventory flow_ is the simplest option, with minimal handling steps and the least traceability. In this setup, products move directly from vendors to stock or from stock to customers, with Odoo only tracking when items enter or leave the warehouse. This makes it ideal for businesses with high-volume, low-risk products or fast-moving operations where additional validation steps aren’t necessary.

  * **Receiving** : Products go directly into stock.

  * **Shipping** : Products ship directly from stock.

  * **Best for** : Small warehouses, low stock levels, and non-perishable items, where minimal processing is needed before products are stored or shipped.




Vedi anche

[One-step receipt and delivery](daily_operations/receipts_delivery_one_step.html)

## Two-step flow¶

A _two-step flow_ adds an input or output area for processing products before storage or shipment. Incoming goods can be unboxed and inspected before shelving, while outgoing shipments are sorted and consolidated before dispatch. This setup improves efficiency by assigning storage teams to picking and stocking, while dedicated teams handle unboxing, (possibly) packing, and final verification to reduce order fulfillment errors.

  * **Receiving** : Products move to an _input_ area before being transferred into stock.

    * Until transferred, received products are not automatically reserved for manufacturing, shipping, or other operations.

  * **Shipping** : Products move to an _output_ before shipping to allow for [sorting or consolidation](picking_methods.html).

  * **Best for** : Large warehouses, high stock levels, bulky items, and workflows that separate receiving from storage to improve organization and efficiency.




Vedi anche

[Two-step receipt and delivery](daily_operations/receipts_delivery_two_steps.html)

## Three-step flow¶

A three-step flow builds on the two-step process by adding a quality check and packing area, enforcing stricter processes and improving oversight.

Importante

While this setup enhances process control, separating picking and packing requires validation at each step. If the same person handles both, it may cause redundancy and slow operations.

Quality checks and packing do not require a three-step flow. Enable [quality control points](../../quality/quality_management/quality_control_points.html) separately or activate the [Packages feature](../product_management/configure/package.html#inventory-warehouses-storage-enable-package) in Odoo to incorporate these processes without adding extra transfer steps.

  * **Receiving** : Products follow a structured process: _input area_ → _quality control_ → _stock_.

  * **Shipping** : Products are _picked_ , _packed_ , and then _shipped_ , ensuring proper handling and organization.

  * **Best for** : Very large warehouses with strict quality control requirements, dedicated picking and packing workflows, and a need for clear traceability across multiple handling stages. Suitable when multiple teams manage different steps before products are stocked or shipped.




Vedi anche

  * [Three-step receipt](daily_operations/receipts_three_steps.html)

  * [Three-step delivery](daily_operations/delivery_three_steps.html)




## Add-ons¶

To optimize each flow, Odoo provides additional features that can enhance the process.

### Archivio¶

To organize and store products efficiently, use:

#### [Putaway rulesGuide products to specific storage locations based on predefined rules ](daily_operations/putaway.html)#### [Storage categoriesSet item or weight limits to prevent overstocking at the location and ensure proper organization ](daily_operations/storage_category.html)#### [ConsignmentKeep track of products owned by third parties ](daily_operations/owned_stock.html)

### Consegna¶

Tailor the outgoing shipment process to fit the business needs. Picking methods and removal strategies control how products are reserved for orders, while cross-docking and dropshipping determine how they move. Configuring these options in Odoo ensures visibility into product movement and confirms that items reach customers efficiently.

#### [Cross dockReceive products and immediately transfer them to another warehouse without storing them ](daily_operations/cross_dock.html)#### [DropshippingCoordinate with vendors to deliver orders directly to customers, bypassing internal stock ](daily_operations/dropshipping.html)#### [Picking methodsOptimize picking operations using piece, batch, cluster, or wave picking techniques ](picking_methods.html)#### [Removal strategiesUse FIFO, LIFO, or FEFO strategies to automate the selection of products for delivery ](removal_strategies.html)

### Personalizzazione¶

Odoo’s flexible framework enables businesses to tailor workflows to match specific operational needs.

#### [Custom routesDefine tailored receiving or delivery workflows to meet specific business needs ](daily_operations/use_routes.html)

  * [Routes and push/pull rules](daily_operations/use_routes.html)
  * [One-step receipt and delivery](daily_operations/receipts_delivery_one_step.html)
  * [Two-step receipt and delivery](daily_operations/receipts_delivery_two_steps.html)
  * [Three-step receipt](daily_operations/receipts_three_steps.html)
  * [Three-step delivery](daily_operations/delivery_three_steps.html)
  * [Putaway rules](daily_operations/putaway.html)
  * [Storage categories](daily_operations/storage_category.html)
  * [Organize a cross-dock in a warehouse](daily_operations/cross_dock.html)
  * [Sell stock from multiple warehouses using virtual locations](daily_operations/stock_warehouses.html)
  * [Consignment: buy and sell stock without owning it](daily_operations/owned_stock.html)
  * [Dropshipping](daily_operations/dropshipping.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](daily_operations/use_routes.html "Routes and push/pull rules") |
  * [precedente](../shipping_receiving.html "Shipping and receiving") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Inbound and outbound flows


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
  *[AVCO]: Average Cost
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
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