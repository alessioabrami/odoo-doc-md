# Report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](participate.html "Participate in live chat") |
  * [precedente](chatbots.html "Chatbot") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Report



# Report¶

Odoo _Live Chat_ includes several reports that allow for the monitoring of operator performance and the identification of trends in customer conversations.

## Available reports¶

The following reports are included in the _Live Chat_ app:

  * Sessions History

  * Session Statistics

  * Operator Analysis




Nota

The _Live Chat Ratings Report_ can also be accessed through the Report menu. For more information on this report, and on the _Live Chat_ rating process, see [Live Chat Ratings](ratings.html).

To access a drop-down menu of all the available reports, navigate to Live Chat app ‣ Report.

### Storico Sessioni¶

The _Sessions History_ report displays an overview of live chat sessions, including session dates, participant name and country, session duration, the number of messages, and the rating. It also provides access to the complete transcripts of live chat sessions.

To access this report, navigate to Live Chat app ‣ Report ‣ Sessions History.

The information in this report can be exported, or inserted into a spreadsheet.

Click the ⚙️ (gear) icon to the right of the History page title, in the top-left corner. Doing so reveals a drop-down menu.

From the drop-down menu, click Export All to export all sessions to a spreadsheet, or Insert list in spreadsheet to insert the information in a new, or existing, spreadsheet.

To only export select sessions, first select the desired sessions to be exported from the list, by clicking the checkbox to the left of each individual session. With the sessions selected, click the ⚙️ (gear) Actions icon in the top-center of the page, and click Export or Insert list in spreadsheet.

To view the transcript of an individual conversation, click anywhere on the entry line. This opens the _Discuss_ thread for the conversation.

In the _Discuss_ thread, the conversation view displays the entire transcript of the conversation. At the top of the conversation, there is a list of the web pages the visitor browsed before beginning their chat session, along with corresponding time stamps. If the visitor left a rating, it is included at the end of the transcript.

### Statistiche Sessione¶

The _Session Statistics_ report provides a statistical overview of live chat sessions. The default view for this report displays sessions grouped by the date of creation.

To access this report, navigate to Live Chat app ‣ Reports ‣ Session Statistics.

The stacked bar graph view of the _Session Statistics_ report, with results grouped by Creation Date (hour), then by rating.¶

To view a different measure, click the Measures drop-down menu at the top-left of the report. The measures available for this report include:

  * # of speakers: number of participants in the conversation.

  * Days of activity: number of days since the operator’s first session.

  * Duration of Session (min): the duration of a conversation, in minutes.

  * Is visitor anonymous: denotes whether the conversation participant is anonymous.

  * Messages per session: the total number of messages sent in a conversation. This measure is included in the default view.

  * Rating: the rating received by an operator at the end of a session, if one was provided.

  * Session not rated: denotes if a session did **not** receive a rating at the end of the conversation.

  * Time to answer (sec): the average time, in seconds, before an operator responds to a chat request.

  * Visitor is Happy: denotes whether a positive rating was provided. If the visitor gave either a negative or neutral rating, they are considered _unhappy_.

  * Count: the total number of sessions.




### Analisi Operatore¶

The _Operator Analysis_ report is used to monitor the performance of individual live chat operators.

To access the report, navigate to Live Chat app ‣ Reports ‣ Operator Analysis.

The default view for this report is a bar chart, which only displays conversations from the current month, as indicated by the This Month default search filter. Conversations are grouped by operator.

To view a different measure, click the Measures drop-down menu at the top-left of the report. The measures available for this report include:

  * # of Sessions: the number of sessions an operator participated in. This measure is included by default.

  * Average duration: the average duration of a conversation, in seconds.

  * Average rating: the average rating received by the operator.

  * Time to answer: the average amount of time before the operator responds to a chat request, in seconds.

  * Count: the total number of sessions.




## View and filter options¶

On any Odoo report, the view and filter options vary, depending on what data is being analyzed, measured, and grouped. See below for additional information on the available views for the _Live Chat_ reports.

Nota

The Sessions History report is **only** available in list view.

### Vista pivot¶

The _pivot_ view presents data in an interactive manner. The Session Statistics and Operator Analysis reports are available in pivot view.

The pivot view can be accessed on a report by selecting the grid icon at the top-right of the screen.

To add a group to a row or column, click the ➕ (plus sign) icon next to Total, and then select one of the groups from the drop-down menu that appears. To remove one, click the ➖ (minus sign) icon, and de-select the appropriate option.

### Vista grafico¶

The _graph_ view presents data in either a _bar_ , _line_ , or _pie_ chart. The Session Statistics and Operator Analysis reports are available in graph view.

Switch to the graph view by selecting the line chart icon at the top-right of the screen. To switch between the different charts, select the desired view’s corresponding icon at the top-left of the chart, while in graph view.

Suggerimento

Both the bar chart and line chart can utilize the _stacked_ view option. This presents two or more groups of data on top of each other, instead of next to each other, making it easier to compare data.

### Save and share a favorite search¶

The _Favorites_ feature found on reports allows users to save their most commonly used filters, without having to reconstruct them every time they are needed.

To create and save a filter to the _Favorites_ section on the search bar drop-down menu, follow the steps below:

  1. Set the necessary parameters using the Filters and Group By options available in the Search… bar drop-down menu and the Measures drop-down menu at the top-left of the report.

  2. Click the 🔻(triangle pointed down) icon next to the Search… bar to open the drop-down menu.

  3. Under the Favorites heading, click Save current search.

  4. Rename the search.

  5. Select Default filter to have these filter settings automatically displayed when the report is opened. Otherwise, leave it blank.

  6. Select Shared to make this filter available to all other database users. If this box is not checked, the filter is only available to the user who creates it.

  7. Click Save to preserve the configuration for future use.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/livechat/reports.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](participate.html "Participate in live chat") |
  * [precedente](chatbots.html "Chatbot") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Report


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
  *[MRR]: Monthly Recurring Revenue
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
  *[URL]: Uniform Resource Locators
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