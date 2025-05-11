# Overall equipment effectiveness — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](production_analysis.html "Production analysis") |
  * [precedente](allocation.html "Allocation reports") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Rendiconto](../reporting.html) »
  * Overall equipment effectiveness



# Overall equipment effectiveness¶

In Odoo’s _Manufacturing_ app, _overall equipment effectiveness_ (OEE) represents the amount of time a work center is fully productive. OEE is displayed as a percentage of the total time a work center is active.

Fully productive time is considered to be time when the work center is operational **and** processing work orders that have not exceeded their _expected duration_.

OEE helps manufacturing teams understand the efficiency of work centers, and the causes of manufacturing downtime.

Importante

Since OEE tracks work center productivity, using it requires enabling the work centers feature in the settings of the Manufacturing app.

To do so, navigate to Manufacturing app ‣ Configuration ‣ Settings, and tick the checkbox next to Work Orders, under the Operations heading. Then, click Save.

## Efficiency standards¶

For OEE to accurately reflect the percentage of fully productive time for a work center, the work center **must** be properly configured with the correct productivity metrics. These include the work center’s _time efficiency_ , _capacity_ , and _OEE target_.

### Time efficiency¶

Time efficiency represents the efficiency of a work center when processing work orders, and is represented as a percentage. A time efficiency value of 100% signifies that the work center processes work orders at the speed of the expected duration, as listed on a product’s BoM. A value less than or greater than 100% signifies that the work center processes work orders slower or faster than an operation’s expected duration, respectively.

To set the time efficiency for a work center, navigate to Manufacturing app ‣ Configuration ‣ Work Centers, and select a work center. On the General Information tab, enter a numerical value in the Time Efficiency field.

Example

Manufacturing a _chair_ product requires two operations: _cut_ and _assemble_. The product’s BoM lists an expected duration of 30 minutes for each operation.

The cut operation is carried out at the _cut station_ work center, which has a time efficiency value of 50%. This means it takes twice as long to complete the operation, for a total time of one hour.

The assemble operation is carried out at the _assembly line_ work center, which has a time efficiency value of 200%. This means it takes half as long to complete the operation, for a total time of 15 minutes.

### Capacità¶

Capacity represents how many units of a product can be produced in parallel at a work center. The duration of work orders for multiple units increases or decreases, based on how many units the work center can handle.

To set the capacity for a work center, navigate to Manufacturing app ‣ Configuration ‣ Work Centers, and select a work center. On the General Information tab, enter a numerical value in the Capacity field.

Example

A _drill station_ work center has a capacity of one unit. An MO is confirmed for 10 units of a _chair_ , a product manufactured using the drill station.

Since there are ten times as many units to produce than the work center can handle at once, the operation time is ten times the duration listed on the product’s BoM.

### OEE target¶

The OEE target is the goal for how much of a work center’s operating time should be fully productive time. It is displayed as a percentage, and should only be set as high as `100%`.

To set the OEE target for a work center, navigate to Manufacturing app ‣ Configuration ‣ Settings ‣ Work Centers, and select a work center. On the General Information tab, enter a numerical value of `100.00` or less in the OEE Target field.

## Calculating OEE¶

OEE is represented as a percentage value between zero and 100. The value signifies the amount of time that a work center was fully productive. The remainder signifies the amount of time that the work center was operating at less than full efficiency. This can occur for a number of reasons, including _reduced speed_ , _material availability_ , and _equipment failure_.

### Fully productive time¶

For a work center to be considered fully productive, it must be able to receive work orders, have the components necessary to process work orders, and be operating within the expected duration of the work order it is processing.

Example

An _assembly line_ work center is not blocked, and receives a work order to assemble a _bicycle_. The required components are available, so production begins as soon as they are picked and delivered to the work center. The work order has an expected duration of 30 minutes, and is completed in 27 minutes. All of this time is considered fully productive time.

### Reduced speed¶

When a work center is operating at reduced speed, it means that it is processing a work order that has exceeded its expected duration. While the work center may be operational, this is not considered fully productive time.

Example

A _cutting station_ work center receives a work order to cut boards for a _table_. The expected duration of the work order is 15 minutes. The work order ends up taking 18 minutes to complete. The work center is considered to have been operating at reduced speed during the three minutes that exceeded the expected duration.

### Material availability¶

Material availability refers to situations where a work center is able to accept a work order, but the required components are not available. This can occur because the components are not in stock, or are reserved for a different order.

Example

Manufacturing of a _bench_ requires 20 units of _wood_. A manufacturing order (MO) is confirmed for 10 units of the bench, but there is not enough wood in stock to begin manufacturing. The time it takes to acquire the wood is recorded as material availability downtime.

### Equipment failure¶

Equipment failure signifies any period of time when a work center is unusable due to maintenance issues with its equipment. This can be due to equipment breaking down, or when a work center is shut down for scheduled maintenance. In these cases, a work center can be blocked using a [maintenance request](../../maintenance/maintenance_requests.html).

Example

The drill at a _drill station_ work center breaks down, causing the work center to be unusable. A maintenance request is created to fix the drill, and the work center is blocked from receiving work orders. It takes two hours to fix the drill, and make the work center available again. This two-hour period is recorded as equipment failure downtime.

## OEE reporting¶

To view OEE reporting metrics for every work center, navigate to Manufacturing app ‣ Reporting ‣ Overall Equipment Effectiveness. This page shows the metrics for each work center with OEE data.

Alternatively, to see OEE reporting metrics for a single work center, navigate to Manufacturing app ‣ Configuration ‣ Work Centers, and select a work center. At the top of the work center’s form, click the __ OEE smart button.

By default, the main OEE reporting page shows data in a bar chart, while the page for a specific work center shows it in a pie chart. To select a different chart type on either page, click the __(bar chart), __(line chart), or __(pie chart) button above the displayed chart.

It is also possible to see OEE data in a pivot view, or a list displaying each time entry, by clicking the __(pivot view) or __(list view) buttons at the top-right corner of the page.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/reporting/oee.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](production_analysis.html "Production analysis") |
  * [precedente](allocation.html "Allocation reports") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Rendiconto](../reporting.html) »
  * Overall equipment effectiveness


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
  *[MPS]: Master Production Schedules
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
  *[SOs]: Sales Order
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
  *[MTO]: Make to Order
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