# Locations dashboard — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](moves_history.html "Moves history dashboard") |
  * [precedente](stock.html "Stock report") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Locations dashboard



# Locations dashboard¶

The _Locations_ dashboard in the **Inventory** application provides an overview of on-hand storage locations for company products. Use this report to see where stock is stored, identify misplaced items, or view past inventory to see product locations on specific dates.

To access the locations report, the _Storage Locations_ feature must be enabled. To do that, go to Inventory app ‣ Configuration ‣ Settings. In the Warehouse section, tick the checkbox for Storage Locations, and click Save. Then, access the locations dashboard by navigating to Inventory app ‣ Reporting ‣ Locations.

Nota

The _Reporting_ menu in **Inventory** is only accessible to users with [admin access](../../../../general/users/access_rights.html).

## Navigate the locations dashboard¶

By default, the Locations dashboard lists all on-hand products in stock (in the Product column), along with the following information:

  * Location: current storage location. If a product is stored at `Shelf 1` and `Shelf 2`, the product is listed twice, showing quantities at each location.

  * Package: the package that the product is stored in, if any.

  * Lot/Serial Number: if the product has a lot or serial number, it is specified here.

  * On Hand Quantity: current quantity of products. Click the __(edit) icon to [modify the on-hand quantity](../inventory_management/count_products.html).

  * Reserved Quantity: on-hand quantity reserved for operations, such as pickings, delivery orders, or manufacturings.

  * Unit: the unit of measure of the product.




Click the buttons to the right of each row item to access additional information:

  * __ History: access the stock move history of the product, displaying information about the quantity and description of why the product was moved from one location to another.

Suggerimento

View what the product is reserved for, by clicking the __ History button on the far-right of the product line.

On the Moves History page, remove the __ Done filter from the search bar to reveal filter options, and select the To Do filter.

  * __ Replenishment: access the [reordering rules](../replenishment/reordering_rules.html) page to replenish products at the specific location.




In the upper-left corner of the page, click the New button to make an [inventory adjustment](../inventory_management/count_products.html) to record quantities of a certain product at a specific Location.

To view products, quantities, and their locations for a specified date, click the Inventory At Date button (also located in the upper-left corner of the page). Select a date and time in the Inventory at Date field, then click Confirm.

### View empty locations¶

To view which locations are currently empty, navigate to Inventory ‣ Configuration ‣ Locations.

Empty locations are designated by the checkbox in the Is Empty column. To show only empty locations, click into the search bar and select the Empty Locations filter.

## Generate reports¶

After learning how to navigate the locations dashboard, it can be used to create and share different reports.

A few common reports that can be created using the Locations dashboard are detailed below.

### Dead stock report¶

To get list of expired items, also referred to as _dead stock_ , follow these steps:

  1. Go to Inventory app ‣ Reporting ‣ Locations.

  2. Then, click into the search bar to reveal a drop-down list of Filters, Group By, and Favorite options.

  3. Enable the Internal Locations and Expiration Alerts option under the Filters section.




The report now displays a list of expired products.

Nota

This report can also be generated from the [Lot and Serials Numbers](../../product_management/product_tracking/expiration_dates.html#inventory-product-management-expiration-alerts) page, accessed by going to Inventory app ‣ Products ‣ Lots/Serial Numbers.

### Stranded inventory report¶

Businesses using multi-step flows in the **Inventory** or **Manufacturing** apps, may have _stranded_ items, which are products not in their proper storage locations, due to human error. Use this report to periodically check transfer locations (e.g. _WH/Input_ , _WH/Pre-Processing_) to ensure items are moved to their intended storage locations, and accurately recorded in the database.

To get a list of items that might be sitting idly in storage, follow these steps:

  1. Go to Inventory app ‣ Reporting ‣ Locations.

  2. In the search bar, begin typing the name of the location where products are intended to be moved to, such as `WH/Input`, or `WH/Packing`.

  3. Select the Search Location for: [location name] option from the resulting drop-down menu that appears beneath the search bar.




The report now displays a list of products at the transit location.

Example

Searching `Input` in Location shows a list of products at a _WH/Input_ location.

The list shows `500` quantities of `Chicken`, which is alarming if not refrigerated soon after reception. The stranded inventory report helps identify items that have been idling in non-storage locations.

### Inventory discrepancy report¶

To generate a report of items that have been moved since the last [inventory audit](../inventory_management/cycle_counts.html), follow these steps:

  1. Go to Inventory app ‣ Reporting ‣ Locations.

  2. Then, click into the search bar to reveal a drop-down list of Filters, Group By, and Favorite options.

  3. Enable the Internal Locations and Conflicts option from the Filters section.

  4. The report now displays items whose quantities have changed since the last cycle count.

  5. Click the __ History button to view inventory transfers, including receipts and deliveries, that have occurred since the inventory adjustment.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/reporting/locations.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](moves_history.html "Moves history dashboard") |
  * [precedente](stock.html "Stock report") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rendiconto](../reporting.html) »
  * Locations dashboard


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