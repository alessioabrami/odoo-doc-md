# Inventory management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](inventory_management/warehouses.html "Magazzini") |
  * [precedente](../warehouses_storage.html "Warehouses and storage") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Warehouses and storage](../warehouses_storage.html) »
  * Inventory management



# Inventory management¶

In the Odoo _Inventory_ app, [warehouses](inventory_management/warehouses.html) handle the broader organization and distribution of stock across different physical sites, while [locations](inventory_management/use_locations.html) provide a more detailed breakdown within each warehouse for efficient item management.

This document serves as an introduction to the terminology and concepts necessary to master _Inventory_. For specific instructions and examples of how things work, refer to individual documentation pages.

Vedi anche

[Odoo Tutorials: Warehouses & Locations](https://www.youtube.com/watch?v=zMvudZVLuUo)

## Magazzini¶

[Warehouses](inventory_management/warehouses.html) represent a physical place, with a physical address, where a company’s items are stored.

Configure [routes](../shipping_receiving/daily_operations/use_routes.html) in a warehouse to control how products move to customers, from vendors, within the warehouse, or [between warehouses](replenishment/resupply_warehouses.html).

## Ubicazioni¶

[Locations](inventory_management/use_locations.html) refer to specific areas within a warehouse, such as shelves, floors, or aisles. These are sub-divisions within a warehouse, and are unique to that warehouse. Users can create and manage numerous locations within a single warehouse to organize inventory more precisely.

Vedi anche

  * [Ubicazioni](inventory_management/use_locations.html)

  * [Inventory adjustments](inventory_management/count_products.html)

  * [Cycle counts](inventory_management/cycle_counts.html)

  * [Scrap inventory](inventory_management/scrap_inventory.html)




### Location types¶

_Location types_ in Odoo help categorize and manage where products are, and what actions need to be taken with them. By default, on the Inventory app ‣ Configuration ‣ Locations page, only internal locations are displayed.

To view the seven location types in Odoo, select any location, and in the Location Type field, there are:

  * Vendor Location: defines an area where products purchased from vendors originate. Items here are **not** in stock.

  * View: used to organize and structure the warehouse hierarchy. For example, the view location `WH` (short for warehouse) groups all internal locations, such as `Stock`, receiving docks, quality checkpoints, and packing areas to show they all belong to the same warehouse.

Importante

View locations should **not** contain products, but it is possible to move them there.

  * Internal Location: storage locations within the warehouse. Items stored in these locations are accounted for in [inventory valuation](../product_management/inventory_valuation/using_inventory_valuation.html).

  * Customer Location: where sold products are tracked; items here are no longer in stock.

  * Inventory Loss: counterpart location to consume missing items or create stock, accounting for discrepancies.

In Odoo, examples of inventory loss locations are _Inventory Adjustment_ , used to account for discrepancies during an inventory count, and _Scrap_ , which is where damaged goods are sent to account for inventory losses.

> Example
> 
> `Virtual Locations/Inventory Adjustment` is a location with the Inventory Loss type. The database shows `65` units in `WH/Stock`, but an inventory check reveals `60`. To correct the quantity, five units are moved from `WH/Stock` to `Virtual Locations/Inventory Adjustment`.

  * Production: where raw materials are consumed, and [manufactured products](../../manufacturing.html) are created.

  * Transit Location: used for inter-company or inter-warehouse operations to track products shipped between different addresses, such as Physical Locations/Inter-warehouse transit.




Nota

In Odoo, location types are color-coded:
    

  * **Red** : internal locations

  * **Blue** : view locations

  * **Black** : external locations (including inventory loss, vendor, and customer locations).




### View locations in Odoo¶

Odoo databases include preconfigured view locations to organize the hierarchy of locations. These provide helpful context, and distinguish between internal and external locations.

  * _Physical locations_ group internal locations—such as secondary warehouses and subcontractor sites. Because [inventory valuation](../product_management/inventory_valuation/inventory_valuation_config.html) changes only when goods move from internal to external locations, Odoo uses physical locations to track stock that is off-site or in transit without affecting valuation.




> Example
> 
> When moving products in warehouses `WH` and `WH2`, the items are not in either warehouse, but still belong to the company. While in transit, they are placed in the `Inter-warehouse transit` location, a Transit Location type.
> 
> This location is under the view location, `Physical Locations`, indicating that `Inter-warehouse transit` is outside of a warehouse, but still part of the company. Doing so does not affect the inventory valuation of the products.

  * _Partner locations_ group customer and vendor locations (external locations) together. Transfers to these locations affect inventory valuation.

  * _Virtual locations_ are locations that do **not** exist physically, but it is where items that are not in inventory can be placed. These can be items that are no longer in inventory due to loss, or other factors.




  * [Magazzini](inventory_management/warehouses.html)
  * [Ubicazioni](inventory_management/use_locations.html)
  * [Inventory adjustments](inventory_management/count_products.html)
  * [Cycle counts](inventory_management/cycle_counts.html)
  * [Scrap inventory](inventory_management/scrap_inventory.html)
  * [Catalogo prodotti](inventory_management/product_catalog.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/inventory_management.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](inventory_management/warehouses.html "Magazzini") |
  * [precedente](../warehouses_storage.html "Warehouses and storage") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Warehouses and storage](../warehouses_storage.html) »
  * Inventory management


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
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Oder
  *[SVLs]: stock valuation layers
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