# Budget — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](intrastat.html "Intrastat") |
  * [precedente](analytic_accounting.html "Contabilità analitica") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Budget



# Budget¶

Analytic budgets track specific activities and projects using analytic accounts, helping businesses make informed decisions about specific departments, projects, or other groups of transactions. In contrast, financial budgets are tied to the general ledger accounts that appear on the profit and loss and focus on the company’s overall economic position.

## Analytic budgets¶

Analytic budgets allow for allocating and tracking income and expenses in detail, breaking down costs and revenues by specific projects, departments, or groups of transactions. Analytic budgets can be applied across various departments or projects to measure profitability and performance. Odoo manages analytic budgets using [analytic accounting](analytic_accounting.html).

To activate the option for creating analytic budgets, go to Accounting ‣ Configuration ‣ Settings, and enable Budget Management in the Analytics section.

Importante

Odoo structures budgets using [plans](analytic_accounting.html#accounting-analytic-accounting-analytic-plans) and [accounts](analytic_accounting.html#accounting-analytic-accounting-analytic-accounts), which must be configured _before_ creating a budget.

### Set an analytic budget¶

To create a new budget, go to Accounting ‣ Accounting ‣ Analytic Budgets and click New. Make sure the following fields are appropriately completed: Budget Name, Period, and Budget Type.

Click Add a line in the Budget Lines tab to structure the budget with the [analytic plans](analytic_accounting.html#accounting-analytic-accounting-analytic-plans) and [accounts](analytic_accounting.html#accounting-analytic-accounting-analytic-accounts) previously created. While the [analytic plans](analytic_accounting.html#accounting-analytic-accounting-analytic-plans) correspond to the column names, select the [analytic accounts](analytic_accounting.html#accounting-analytic-accounting-analytic-accounts) to define the budget lines and set the amounts for each in the Budgeted column. Once all the budget lines are settled, click Open. If changes need to be made once the budget’s status is Open, there are two options:

  * Reset to Draft: To overwrite the data, then reopen the budget.

  * Revise: A new budget will be created. Once it is Open, a Rev reference is added to the Budget Name. The original budget is then Revised.




### Check an analytic budget¶

Once the budget is Open, two additional columns are available: Committed and Achieved. These columns” amounts are automatically calculated based on the related [analytic distribution](analytic_accounting.html#accounting-analytic-accounting-analytic-distribution) of journal items. When the [analytic distribution](analytic_accounting.html#accounting-analytic-accounting-analytic-distribution) of a journal item within the budget’s period is updated, the budget’s columns for the analytic account(s) selected in the distribution are automatically updated. The Achieved amount reflects the current result according to the items of confirmed journal entries for the associated [analytic account](analytic_accounting.html#accounting-analytic-accounting-analytic-accounts). In contrast, the Committed amount displays the full value of the Achieved amount, plus any confirmed sales or purchase orders that have not yet been invoiced or billed.

Nota

  * When a line in a request for quotation or purchase order includes an analytic distribution, a Budget smart button appears, providing a link to the budget report for more details.

  * For Open budgets, if a request for quotation or a purchase order is created using the associated analytic distribution and exceeds the allocated budget amount, the corresponding purchase order line is highlighted in red.




To reveal the Theoretical amount or percentage, use the __( adjust settings) icon in the Budget Lines” header. The Theoretical amount represents the amount of money that could theoretically have been spent or should have been received based on the current date relative to the start/end dates. Click Details to open a filtered view of the budget report related to that specific budget line.

Nota

Deleting a budget is only allowed in the Draft and Cancelled stages.

To view the budget lines of one or multiple budgets directly from the Budgets list view, select the budget(s) and click Budget Lines.

### Generate periodic budgets¶

To create periodic budgets (monthly, quarterly, and yearly) for the selected Analytic Plans, click Generate. A new budget is created for each Period between the start and end dates:

  * If a single analytic plan is selected, each budget includes a line for each account in that analytic plan.

  * If multiple analytic plans are selected, each budget includes a line for each account/analytic plan combination.




To generate periodic budgets, follow these steps:

  1. In the Budgets list view, click Generate.

  2. In the Generate Budget window, set the dates and select the Period and the Analytic Plans.

  3. Click Split to create the periodic budgets.

  4. Click Budgets in the top-left corner to return to the Budgets list view.

  5. One by one, click on the different periodic budgets with the Draft status to open them and set the amounts in the Budgeted column for each analytic account linked to the chosen analytic plans.

  6. Click Open for each periodic budget.




### Rendiconto¶

To perform various reporting actions, go to Accounting ‣ Reporting ‣ Budget Report, then:

  * Track, analyze, and compare budget data.

  * Filter and group data using the __( plus-square) or __(minus-square) icon.

  * Drill down into the report to see more details on the actual amounts and transactions.

  * Export the data for further analysis or reporting needs.




## Financial budgets¶

Financial budgets are structured around specific income and expense accounts and transactions for official financial reporting and compliance purposes.

Nota

Financial budgets are available on the [Profit and Loss](../reporting.html#accounting-reporting-profit-and-loss) report.

### Set a financial budget¶

To create a new financial budget, follow these steps:

  1. Go to Accounting ‣ Reporting ‣ Profit and Loss to open the [Profit and Loss](../reporting.html#accounting-reporting-profit-and-loss) report.

  2. Click the __(calendar) button to use the date selector and choose a period.

  3. Click the __ Budget button and name the budget. A new column labeled with the budget name will appear next to the Balance column.

  4. Assign amounts to each account requiring analysis.

  5. A new % column will appear to the right of the new budget column, indicating the current status.




Different financial budgets can be created using these steps for comparison purposes.

Nota

The date selector enables the division of periods and navigation between periods, automatically updating the amounts accordingly.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/reporting/budget.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](intrastat.html "Intrastat") |
  * [precedente](analytic_accounting.html "Contabilità analitica") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Budget


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
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
  *[POS]: point of sale
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