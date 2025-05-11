# Modelli — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](global_filters.html "Global filters") |
  * [precedente](functions.html "Functions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Foglio di calcolo](../spreadsheet.html) »
  * Modelli



# Modelli¶

Spreadsheet templates allow you to quickly create spreadsheets without starting from scratch.

Several pre-built templates are available when creating a new spreadsheet from the **Documents** app, such as:

  * budget reports,

  * pipeline revenue reports, or

  * sales commission report.




You can also save any spreadsheet as a template and manage and edit existing templates.

## Default templates¶

### Accounting: budget reports¶

Budget reports compare a company’s actual spending with its budget over a defined period. Two templates are available: one uses quarterly intervals (Budget Report (Quarterly)), while the other uses monthly intervals (Budget Report (Monthly)).

The cells under the Actuals column are automatically filled in with the amount of money made and spent over the corresponding period (month or quarter). The data is taken from posted journal items under [income and expense accounts](../../finance/accounting/get_started/chart_of_accounts.html#chart-of-account-type).

Avvertimento

Journal items under the Other Income account type are not considered when collecting data.

To analyze your budget’s performance, fill the cells under the Budget column with how much money you expect to make (Income rows) and spend (Expenses rows) over the related period and per account. Then, the performance (Perf.) column compares Actuals data to their corresponding budget, expressed as a percentage.

Lastly, the Net Profit row represents the total Income minus the total Expenses for the Actuals and Budget columns.

### CRM: pipeline revenue reports¶

Two pipeline revenue reports are available. The Pipeline Revenue Report (Monthly) is dedicated to one-time revenue (NRR), while the MRR/NRR Pipeline Revenue Report (Monthly) covers recurring and non-recurring revenue (MRR).

Suggerimento

Enable Recurring Revenues by going to CRM ‣ Configuration ‣ Settings.

The cells under the Actuals column are automatically filled in with the amount of monthly revenue from **won** opportunities.

To compute the revenue performance, fill in the monthly revenue targets.

  * For the Revenue by Team sheet, fill in the cells under the Target columns for each sales team.

  * For the Revenue by Salesperson sheet, open the Targets sheet and fill in the cells next to each salesperson. Use the Monthly Factor table below to adapt the main targets depending on the month of the year.




Then, the performance (Perf.) column compares Actuals data to their related budget, expressed as a percentage.

Lastly, the Forecasted column gathers the monthly revenue of leads multiplied by their Probability percentage.

Nota

For actuals and forecasts:

  * The Expected Closing date found on leads is used to assign them to a month.

  * The recurring monthly revenue is used even if the recurring plan’s number of months is set to a different value than 1 month. For example, a yearly plan’s revenue is divided by 12 months.




### Sales: sales commission¶

This report presents the monthly commission earned or due to each salesperson.

The Rate column is pre-filled with the percentage rate from the Rates tab, which can be customized for each product category according to the company’s policy. Adjusting the rate for a specific product category automatically updates the commission amount for that category.

The Invoiced column shows the total amount of untaxed invoices grouped by salesperson and month.

Lastly, the Comm. column is computed by multiplying the invoiced amount with the rate percentage.

## Save a spreadsheet as a template¶

Any spreadsheet can be saved as a template. From the menu bar, click File ‣ Save as template. Modify the default Template Name if necessary and click Confirm.

Nota

Templates are available to all users on the database.

## Manage and edit templates¶

Manage templates by going to Documents ‣ Configuration ‣ Spreadsheet Templates. Remove the My Templates [filter](../../essentials/search.html#search-preconfigured-filters) to view all templates in the database.

To edit an existing template, click `✎ Edit` next to the desired template. Modifications are automatically saved.

Suggerimento

Use the download button under the Data column to export a template in JSON format. The file can be imported into another database.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/spreadsheet/templates.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](global_filters.html "Global filters") |
  * [precedente](functions.html "Functions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Foglio di calcolo](../spreadsheet.html) »
  * Modelli


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[CSV]: Valori separati da virgola
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