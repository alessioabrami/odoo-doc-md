# Configure product — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](configure/type.html "Product type") |
  * [precedente](../product_management.html "Product management") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Product management](../product_management.html) »
  * Configure product



# Configure product¶

A group of products in Odoo can be further defined using:

  * [Units of measure (UoM)](configure/uom.html): a standard quantity for specifying product amounts (e.g., meters, yards, kilograms). Enables automatic conversion between measurement systems in Odoo, such as centimeters to feet.

    * _Ex: Purchasing fabric measured in meters but receiving it in yards from a vendor._

  * [Colli](configure/package.html): A physical container used to group products together, regardless of whether they are the same or different.

    * _Ex: A box containing assorted items for delivery, or a storage box of two hundred buttons on a shelf._

  * [Imballaggio](configure/packaging.html): groups the _same_ products together to receive or sell them in specified quantities.

    * _Ex: Cans of soda sold in packs of six, twelve, or twenty-four._




## Confronto¶

This table provides a detailed comparison of units of measure, packages, and packaging to help businesses evaluate which best suits their requirements.

Funzione | Unità di misura | Colli | Imballaggio  
---|---|---|---  
Scopo | Standardized measurement for product units (e.g., cm, lb, L) | Tracks the specific physical container and its contents | Groups a fixed number of items together for easier management (e.g., packs of 6, 12 or 24)  
Product uniformity | Defined per product; saved as one UoM in the database | Allows mixed products | Same products only  
Flessibile | Converts between vendor/customer UoMs and database UoM | Items can be added or removed from the container | Quantities are fixed (e.g., always packs of 6, 12 or 24)  
Complexity | Simplest for unit conversions | More complex due to container-level inventory tracking | Simpler; suitable for uniform product groupings  
Inventory tracking | Tracks product quantities within the warehouse in the specific UoM defined in the product form | Tracks package location and contents within the warehouse | Tracks grouped quantities but not individual items” locations  
Smooth barcode operations | Non disponibile | Requires scanning both the package and individual items for reception. (even if there are 30 items in a package). Can enable the [Move Entire Packages](configure/package.html#inventory-product-management-move-entire-pack) feature to update the package’s contained items” locations, when moving the package | Scanning a packaging barcode automatically records all included units. (e.g. 1 pack = 12 units)  
Product lookup | Non disponibile | Scanning a product’s barcode identifies its typical storage location in the Odoo database | Barcode identifies grouped quantity, not storage location  
Unique barcodes | Non disponibile | Unique barcodes for individual packages (e.g. Pallet #12) | Barcodes set at the packaging type level (e.g. for a pack of 6)  
Reusability | Not applicable | Can be disposable or reusable, configured via the [Package Use](configure/package.html#inventory-warehouses-storage-cluster-pack) field | Disposable only  
Container weight | Not applicable | Weight of the container itself is included in the _Shipping Weight_ field of a package (Inventory app ‣ Products ‣ Packages) | Weight of the container is defined in the _Package Type_ settings  
Lot/serial number tracking | Requires manual adjustments to track UoMs via lots (See use case for details) | Applies only to contained products | Applies to both contained products and the container  
Custom routes | Cannot be set | Cannot be set | Routes can define specific warehouse paths for a particular packaging type  
  
## Casi d’uso¶

After comparing the various features, consider how these businesses, with various inventory management and logistics workflows, came to their decision.

### Pallets of items using packaging¶

A warehouse receives shipments of soap organized on physical pallets, each containing 96 bars. These pallets are used for internal transfers and are also sold as standalone units. For logistical purposes, the pallet’s weight must be included in the total shipping weight for certain deliveries. Additionally, the pallet requires a barcode to facilitate tracking, and the number of individual bars of soap must be included in the stock count when the pallet is received.

After evaluating various options, _product packaging_ was the most suitable solution. Packaging enables assigning a barcode to a pallet, identifying it as a «pallet type» containing 96 soap bars. This barcode streamlines operations by automatically registering the grouped quantity. Key distinctions include:

  * **Warehouse tracking limitations** : Odoo tracks only the total quantity, not the number of packagings. For instance, if a pallet with 12 and 24 quantities is received, Odoo records 36 quantities, not the pallet details.

  * **Packaging barcodes are type-specific, not unique** : Barcodes represent packaging types (e.g., «pallet of 96 soap bars») but do not uniquely identify individual pallets, such as Pallet #1 or Pallet #2.




### Capture product information using barcode¶

An Odoo user expects the **Barcode** app to display the typical storage location of a product by scanning a barcode for a container.

_Packages_ was the most suitable. When the [appropriate setting is enabled](configure/package.html#inventory-warehouses-storage-enable-package), scanning a package barcode displays its contents in the **Barcode** app.

Packages represent physical containers, enabling detailed tracking of the items they hold. Scanning a package provides visibility into its contents and facilitates operations, like inventory moves.

### Track different units of measure in storage¶

A fruit juice distributor tracks multiple UoMs for their operations:

  * Fruits are purchased in tons.

  * Juice is produced and stored in kilograms.

  * Small samples are stored in grams for recipe testing.




_Unit of Measure_ was most suitable. Odoo automatically converts tons to kilograms during receipts. However, since Odoo tracks only one UoM per product in the database, the company uses lot numbers to differentiate UoMs:

  * LOT1: Grams (g)

  * LOT2: Kilograms (kg)




Manual inventory adjustments are required to convert between lots, such as subtracting 1 kg from LOT2 to add 1,000 g to LOT1. While functional, this workaround can be time-consuming and prone to errors.

  * [Product type](configure/type.html)
  * [Unità di misura](configure/uom.html)
  * [Colli](configure/package.html)
  * [Imballaggio](configure/packaging.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/configure.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](configure/type.html "Product type") |
  * [precedente](../product_management.html "Product management") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Product management](../product_management.html) »
  * Configure product


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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
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
  *[FEFO]: First Expired, First Out
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