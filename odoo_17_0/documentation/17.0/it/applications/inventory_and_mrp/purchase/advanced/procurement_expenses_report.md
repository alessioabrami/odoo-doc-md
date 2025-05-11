# Procurement expenses report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../barcode.html "Codice a barre") |
  * [precedente](vendor_costs_report.html "Vendor costs report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Avanzato](../advanced.html) »
  * Procurement expenses report



# Procurement expenses report¶

With the _Purchase_ application, users can monitor procurement expenses over time. This report helps companies track and analyze spending, identify cost-saving opportunities, and ensure efficient budget management.

## Create procurement expenses report¶

To create a procurement expenses report, first navigate to Purchase app ‣ Reporting ‣ Purchase to open the Purchase Analysis dashboard.

By default, the dashboard displays a line chart overview of the Untaxed Total of Purchase Orders (POs) with a Confirmation Date for the current month, or of Requests for Quotation (RFQs) with a status of _Draft_ , _Sent_ , or _Cancelled_.

### Add filters and groups¶

On the top-right, click the __(pivot) icon to switch to pivot view.

Suggerimento

While the procurement expenses report can also be viewed as a __(bar chart), __(line chart), or __(pie chart), the pivot view provides the most detailed view of the data, and is the recommended starting point.

Remove any default filters from the Search… bar. Then, click the __(down) icon to open the drop-down menu that contains the Filters, Group By, and Favorites columns.

Nota

Unless otherwise specified, the report displays data from both RfQs and POs. This can be changed by selecting either Requests for Quotation or Purchase Orders under the Filters column.

Under the Filters column, select a time frame to use for comparison. The report can be filtered by either Order Date or Confirmation Date. Choose one from the list, and click the __(down) icon to specify the date range, either by month, quarter, or year.

Next, under the Group by column, select Vendor. Then, select Product Category, which is also located in the Group By column.

Nota

The selections under the Group By heading can be altered, depending on the needs of the individual company. For example, selecting Product, instead of Product Category, provides a more in depth look at the performance of specific items, in place of an entire category.

Next, make a selection under the Comparison heading that appears. These options are only available after the date range is selected under the Filters column, and vary based on that range. Previous Period adds a comparison to the previous period, such as the last month or quarter. Previous Year compares the same time period from the previous year.

Nota

While multiple time-based filters can be added at once, only one comparison can be selected at a time.

The filter for Q2, comparison for **Previous Period** , and group-by for **Vendor** and **Product Category** were selected.¶

### Add measures¶

After selecting the Filters, Group by, and Comparison settings, click out of the drop-down menu.

By default, the report displays data with the following measures: Order, Total, Untaxed Total, and Count. Click Measures at the top-left to open the drop-down list of available measures.

Click the following specific measures to include additional columns for the procurement expenses report:

  * Total and Untaxed Total: can include one or both measures. These are included for overall spending analysis.

  * Average Cost: included to evaluate cost efficiency.

  * Days to Confirm and Days to Receive: used to assess supplier performance.

  * Qty Ordered and Qty Received: used to understand order efficiency.

  * Qty Billed and Qty to be Billed: used to track order accuracy.




Suggerimento

Additional measures can be included in the report, if desired, to provide additional insights. For example, Gross Weight and Volume may be included for further logistics and management analysis.

After selecting all necessary measures, click out of the drop-down menu.

## Visualizzare i risultati¶

After all of the filters and measures have been selected, the report generates in the selected view.

Click Insert in Spreadsheet to add the pivot view into an editable spreadsheet format within the _Documents_ app.

Importante

The Insert in Spreadsheet option is **only** available if the _Documents Spreadsheet_ module is installed.

Nota

The procurement expenses report is also available in graph view. Click the __(area chart) icon to change to graph view. Click the corresponding icon at the top of the report to switch to a __(bar chart), __(line chart), or __(pie chart).

Vedi anche

Per salvare questo resoconto come _preferito_ , consulta la sezione [Preferite](../../../essentials/search.html#search-favorites).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/advanced/procurement_expenses_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../barcode.html "Codice a barre") |
  * [precedente](vendor_costs_report.html "Vendor costs report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Avanzato](../advanced.html) »
  * Procurement expenses report


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
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
  *[PO]: purchase order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure