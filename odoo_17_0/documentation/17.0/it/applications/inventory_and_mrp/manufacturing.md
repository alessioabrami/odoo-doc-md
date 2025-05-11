# Produzione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manufacturing/basic_setup.html "Basic setup") |
  * [precedente](inventory/shipping_receiving/removal_strategies/least_packages.html "Least packages removal") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Supply Chain](../inventory_and_mrp.html) »
  * Produzione



# Produzione¶

**Odoo Manufacturing** helps manufacturers schedule, plan, and process manufacturing orders. With the work center control panel, put tablets on the shop floor to control work orders in real-time and allow workers to trigger maintenance operations, feedback loops, quality issues, etc.

Vedi anche

  * [Odoo Tutorials: MRP](https://www.odoo.com/slides/mrp-29)

  * [Odoo Tutorials: Barcode Scanner](https://www.odoo.com/slides/barcode-30)

  * [IoT Boxes (MES)](../general/iot.html)




  * Basic setup
    * [Manufacturing product configuration](manufacturing/basic_setup/configure_manufacturing_product.html)
    * [Bill of materials](manufacturing/basic_setup/bill_configuration.html)
    * [One-step manufacturing](manufacturing/basic_setup/one_step_manufacturing.html)
    * [Two-step manufacturing](manufacturing/basic_setup/two_step_manufacturing.html)
    * [Three-step manufacturing](manufacturing/basic_setup/three_step_manufacturing.html)
    * [Manufacturing order costs](manufacturing/basic_setup/mo_costs.html)
  * Configurazione avanzata
    * [Managing BoMs for product variants](manufacturing/advanced_configuration/product_variants.html)
    * [Kits](manufacturing/advanced_configuration/kit_shipping.html)
    * [Manage semi-finished products](manufacturing/advanced_configuration/sub_assemblies.html)
    * [Manage work orders using work centers](manufacturing/advanced_configuration/using_work_centers.html)
    * [Work order dependencies](manufacturing/advanced_configuration/work_order_dependencies.html)
  * Workflow
    * [Master production schedule](manufacturing/workflows/use_mps.html)
    * [Work center time off](manufacturing/workflows/work_center_time_off.html)
    * [Scrap during manufacturing](manufacturing/workflows/scrap_manufacturing.html)
    * [Manufacturing backorders](manufacturing/workflows/manufacturing_backorders.html)
    * [Split and merge manufacturing orders](manufacturing/workflows/split_merge.html)
    * [Unbuild orders](manufacturing/workflows/unbuild_orders.html)
    * [Sottoprodotti](manufacturing/workflows/byproducts.html)
    * [Continuous product improvement](manufacturing/workflows/continuous_improvement.html)
  * Linea di produzione
    * [Shop Floor overview](manufacturing/shop_floor/shop_floor_overview.html)
    * [Shop Floor time tracking](manufacturing/shop_floor/shop_floor_tracking.html)
  * [Subappalto](manufacturing/subcontracting.html)
    * [Basic subcontracting](manufacturing/subcontracting/subcontracting_basic.html)
    * [Basic subcontracting lead times](manufacturing/subcontracting/basic_subcontracting_lead_times.html)
    * [Resupply subcontractor](manufacturing/subcontracting/subcontracting_resupply.html)
    * [Resupply subcontracting lead times](manufacturing/subcontracting/resupply_subcontracting_lead_times.html)
    * [Dropship to subcontractor](manufacturing/subcontracting/subcontracting_dropship.html)
    * [Dropship subcontracting lead times](manufacturing/subcontracting/dropship_subcontracting_lead_times.html)
  * Rendiconto
    * [Allocation reports](manufacturing/reporting/allocation.html)
    * [Overall equipment effectiveness](manufacturing/reporting/oee.html)
    * [Production analysis](manufacturing/reporting/production_analysis.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manufacturing/basic_setup.html "Basic setup") |
  * [precedente](inventory/shipping_receiving/removal_strategies/least_packages.html "Least packages removal") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Supply Chain](../inventory_and_mrp.html) »
  * Produzione


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