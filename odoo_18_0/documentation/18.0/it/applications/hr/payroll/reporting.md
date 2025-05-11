# Rendiconto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_entry_analysis.html "Work entry analysis") |
  * [precedente](payslips.html "Buste paga") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Rendiconto



# Rendiconto¶

The _Reporting_ section of the _Payroll_ app offers a variety of reports to choose from, organized by location.

The _Payroll_ report, _Work Entry Analysis_ report, and _Salary Attachment Report_ are default reports in the _Payroll_ app, and are available for all companies, regardless of location.

Beneath the three default reports are all localization-based reports, organized by country, in alphabetical order. These reports contain all the various information for the offered benefits and local tax laws.

To view all the available reports for the database, including all the localization-specific ones, navigate to Payroll app ‣ Reporting to view the available reports in a drop-down menu. Click on a specific report to view it.

If a report is unavailable to a user, an Invalid Operation pop-up window appears, stating: You must be logged in to a (country) company to use this feature, where «(country)» is the specific country the company is configured for.

## Default reports¶

### Libro paga¶

Click on Payroll app ‣ Reporting ‣ Payroll to display the Payroll Analysis report. This report shows all the payslips generated in the last 365 days, due to the default filter: `Last 365 Days Payslip`.

The report can display metrics for a variety of parameters. Click the Measures box to view a drop-down menu with the various metric options to display. The default options available include:

  * # Payslip

  * Basic Wage

  * Basic Wage for Time Off

  * Days of Paid Time Off

  * Days of Unforeseen Absence

  * Days of Unpaid Time Off

  * Gross Wage

  * Net Wage

  * Number of Days

  * Number of Hours

  * Work Days

  * Work Hours

  * Count




Net Wage is the default metric for the Payroll report.

#### Grafico a linee¶

A line chart is the default view for the _Payroll_ report. If a different view is selected, click the Line Chart button (represented by a 📈 (chart increasing) icon) in the menu bar to change the view back to a line chart.

Several options are available for the line chart. Click the corresponding button to activate the selection, and change the way the data is presented. These icons appear at the end of the chart options. The various options are:

  * Stacked: data is presented with each metric in its own line, «stacked» on top of each other. This helps visualize the distribution and variances between different categories.



  * Cumulative: data is presented with each metric on an individual line, with the total amount calculated by combining all the lines. This provides a comprehensive view of the cumulative data.



  * Descending: data is shown with the largest values on the left side of the chart, gradually decreasing towards the smallest values on the right side, along the x-axis. This arrangement helps emphasize trends or outliers at the extremes.



  * Ascending: data is presented with the smallest values on the left side of the chart, increasing towards the largest values on the right side, along the x-axis. This arrangement can be useful for highlighting progressive growth or trends.




Nota

These options can be combined to create a variety of views.

#### Grafico a barre¶

To display the data in a bar chart, click on the Bar Chart button (represented by a 📊 (bar chart) icon) in the menu bar.

Click the Stacked icon to view the bar chart in a stacked format (where multiple values appear in each column). Cumulative bar charts are useful for visualizing the progression over time or other categories.

An option to display the columns in Descending or Ascending order appears at the end of the options.

Suggerimento

Clicking an option enables it. To turn off the option, click it again. When the option is enabled the icon appears lighter, with a turquoise outline. When it is inactive, it appears gray, with no outline.

#### Grafico a torta¶

To display the data in a pie chart, click on the Pie Chart button (represented by a (pie chart) icon) in the menu bar. There are no additional options available in this view.

#### Tabella pivot¶

To display the data in a pivot table, click on the Pivot button (represented by a (pivot) icon) located in the far-right side of the top menu bar.

The default information displayed includes the number of payslips (# Payslip), the Net Wage, the Gross Wage, the number of Days of Paid Time Off, and the number of Days of Unpaid Time Off. The information is organized by department.

To display more information on the report, click the Measures button to reveal a drop-down menu. Then, click on any other metric to display it on the pivot table.

To sort the entries by a specific column, such as Net Wage, click on the column name twice. The first click selects the column, and the second click sorts the information in descending order.

To export the data in an XLSX format, click the Download xlsx button, represented by a ⬇️ (down arrow above a horizontal bar) icon, located at the far-right of the available icons. The information is then downloaded into a spreadsheet.

Any report can be inserted into a spreadsheet by clicking the Insert in Spreadsheet button. A Select a spreadsheet to insert your (type of report) pop-up window appears, asking which spreadsheet to place the information in. Select an existing spreadsheet or dashboard, or select a new Blank spreadsheet. Click the Confirm button to move to a spreadsheet view with the report added to it.

Nota

If the **Documents** app is **not** installed, the Insert in Spreadsheet option places the newly-created spreadsheet in the **Dashboards** app.

If the **Documents** application _is_ installed, the spreadsheet has the option to be stored in either the **Dashboards** app or **Documents** app.

## Filtri¶

At the top of each report, the default filters are shown inside the Search… box.

Click the ⬇️ (down arrow) icon in the search bar to display the available Filters. Filters show information that match the specific filter parameters.

Example

The Work Entries Analysis report has two default filters, the `Current month:(Month) (Year)` filter, and the `Validated` filter.

The Payroll report has only one default filter, the `Last 365 Days Payslip` filter.

The Salary Attachment Report has only one default filter, the `Payslip End Date: (Year)` filter.

All reports can include custom filters, or group information, by different metrics (employee, department, company, etc.).

Some reports have the option to compare the current report to the previous time period or year (a Comparison option).

Click on a parameter to select it and activate it. The report is immediately updated with the new parameters.

The updated report can be set as a _favorite_ report, meaning the parameters are stored for quick access in the future. To do that, click Save the current search, under the Favorites section, located in the search bar drop-down mega menu of filter options. Doing so reveals two options and a Save button.

To set the current report as the default configuration when the report is accessed, check the box next to Default filter. If the current report should be accessible to everyone in the database, check the box next to Share.

Finally, click Save, which saves the currently configured report. Then, it appears beneath the Favorites in the search bar drop-down mega menu of filter options.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/payroll/reporting.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_entry_analysis.html "Work entry analysis") |
  * [precedente](payslips.html "Buste paga") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Rendiconto


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
  *[POS]: Punto vendita
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