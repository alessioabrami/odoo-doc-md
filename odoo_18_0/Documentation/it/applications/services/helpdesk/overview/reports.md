# Rendiconto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ratings.html "Customer ratings") |
  * [precedente](sla.html "Service level agreements \(SLA\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Rendiconto



# Rendiconto¶

Reports in Odoo **Helpdesk** provide the opportunity to manage employee workloads, identify areas for improvement, and confirm if customer expectations are being met.

## Available reports¶

Details about the reports available in Odoo **Helpdesk** can be found below. To view the different reports, go to Helpdesk app ‣ Reporting, and select one of the following: Tickets Analysis, SLA Status Analysis, or Customer Ratings.

### Analisi Ticket¶

The _Tickets Analysis_ report (Helpdesk app ‣ Reporting ‣ Tickets Analysis) provides an overview of every customer support ticket in the database.

This report is useful for identifying where teams are spending the most time, and helps determine if there is an uneven workload distribution among the support staff. The default report counts the number of tickets per team and groups them by stage.

Alternative measures can be selected to track where the most time is spent at different points in the workflow. To change the measures used for the report that is currently displayed, or to add more, click the Measures button, and select one or more options from the drop-down menu:

  * Average Hours to Respond: average number of working hours between a message sent from the customer and the response from the support team. _This does not include messages sent when the ticket was in a folded stage._

  * Hours Open: number of hours between the date the ticket was created and the closed date. If there is no closed date on the ticket, the current date is used. **This measure is not specific to working hours.**

  * Hours Spent (Timesheets): number of _Timesheet_ hours logged on a ticket. _This measure is only available if Timesheets are enabled on a team, and the current user has the access rights to view them._

  * Hours to First Response: number of working hours between the date the ticket was received and the date on which the first message was sent. _This does not include email sent automatically when a ticket reaches a stage._

  * Rating (1-5): number out of five to represent customer feedback (Dissatisfied = 1, Okay/Neutral = 3, Satisfied = 5).

  * Remaining Hours on SO: hours remaining on a linked sales order.

  * Working Hours to Assign: number of working hours between the date the ticket was created and when it was assigned to a team member.

  * Working Hours to Close: number of working hours between the date the ticket was created and the date it was closed.

  * Working Hours until SLA Deadline: number of working hours remaining to reach the last SLA deadline on a ticket.

  * Count: number of tickets in total.




Nota

 _Working hours_ are calculated based on the default working calendar. To view or change the working calendar, go to the Settings application and select Employees ‣ Company Working Hours.

### Analisi stato SLA¶

The _SLA Status Analysis_ report (Helpdesk app ‣ Reporting ‣ SLA Status Analysis) [analyzes the performance](sla.html#helpdesk-analyze-sla-performance) of individual SLA (Service Level Agreement) policies.

By default, this report is filtered to show the number of SLAs failed, in progress, and the number that have been successful. The results are grouped by teams.

To change the measures used for the report that is currently displayed, or to add more, click the Measures button, and select one or more options from the drop-down menu:

  * Average Hours to Respond: average number of working hours between a message sent from the customer and the response from the support team. _This does not include messages sent when the ticket was in a folded stage._

  * Hours Open: number of hours between the date the ticket was created and the closed date. If there is no closed date on the ticket, the current date is used. **This measure is not specific to working hours.**

  * Hours Spent (Timesheets): number of _Timesheet_ hours logged on a ticket. _This measure is only available if Timesheets are enabled on a team, and the current user has the access rights to view them._

  * Hours to First Response: number of working hours between the date the ticket was received and the date on which the first message was sent. _This does not include email sent automatically when a ticket reaches a stage._

  * Number of SLA Failed: number of tickets that have failed at least one SLA.

  * Rating (1-5): number value representing customer feedback (Dissatisfied = 1, Okay/Neutral = 3, Satisfied = 5).

  * Remaining Hours on SO: hours remaining on a linked sales order.

  * Working Hours to Assign: number of working hours between the date the ticket was created and when it was assigned to a team member.

  * Working Hours to Close: number of working hours between the date the ticket was created and the date it was closed.

  * Working Hours to Reach SLA: number of working hours between the date the ticket was created and the date the SLA was satisfied.

  * Count: number of tickets in total.




Vedi anche

[Service Level Agreements (SLA)](sla.html)

### Valutazioni cliente¶

The _Customer Ratings_ report (Helpdesk app‣ Reporting ‣ Customer Ratings) displays an overview of the ratings received on individual support tickets, as well as any additional comments submitted with the rating.

Click on an individual rating to see additional details about the rating submitted by the customer, including a link to the original ticket.

Suggerimento

On the rating’s details page, tick the Visible Internally Only checkbox to hide the rating from public and portal users.

The _Customer Ratings_ report is displayed in a Kanban view by default, but can also be displayed in graph, list, or pivot view.

Vedi anche

[Ratings](ratings.html)

## Casi d’uso¶

### Assessing performance based on customer priority¶

The Tickets Analysis report can be used to evaluate the time it takes to address high-priority tickets compared to standard ones. This helps ensure that high-priority tickets are resolved promptly, and identifies any discrepancies in response times based on priority.

First, navigate to Helpdesk app ‣ Reporting ‣ Tickets Analysis. Click Measures, then select Working Hours to Close. Click into the search bar, then under Group By, select Priority. Finally, under Filters, select Closed.

Suggerimento

The pivot view is also useful for this version of the report.

### Monitoring SLA compliance over time¶

The SLA Status Analysis report can be used to track SLA compliance trends to identify periods with higher SLA breaches. SLA breaches happen when support teams fail to meet the response or resolution times promised in SLAs, leading to dissatisfied customers, potential financial penalties, and decreased team morale. Identifying these breaches is crucial for tracking real-time performance, uncovering patterns, and addressing root causes—like staffing issues or process inefficiencies.

First, navigate to Helpdesk app ‣ Reporting ‣ SLA Status Analysis. Click the __(Graph) icon, then the __(Line Chart) icon.

Nota

While the SLA Status Analysis report defaults to the pivot view, the line chart view provides a better visual representation for this specific use case.

Click Measures, then select Number of SLAs Failed. Doing so ensures the data on the report shows **only** information for tickets that failed at least one SLA. Click into the search bar, then under Group By, select SLA Deadline, and select a time frame, either Month, Week, or Day. This option shows when the highest number of tickets with SLAs are failing, allowing the team to identify patterns, and prepare for potential issues.

Suggerimento

The time frame selected for this report may vary depending on a few factors, including the amount of tickets received on a regular basis, the number of SLAs enabled in the database, and the workload of the team. It is worth experimenting to see what option delivers the most insights.

Vedi anche

[Odoo essentials reporting](../../../essentials/reporting.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/services/helpdesk/overview/reports.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ratings.html "Customer ratings") |
  * [precedente](sla.html "Service level agreements \(SLA\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Rendiconto


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
  *[EDI]: Electronic Data Exchange
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
  *[FBM]: Fulfilled by Merchant
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
  *[RFQs]: requests for quotation
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
  *[FAQs]: Frequently Asked Questions