# Campaign metrics — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](campaign_templates.html "Campaign templates") |
  * [precedente](testing_running.html "Testing/running campaigns") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign metrics



# Campaign metrics¶

_Campaign metrics_ are detailed statistics and analytics within a marketing campaign, measuring its success and effectiveness. Triggered marketing activities populate relevant activity blocks with real-time metrics, in the campaign detail form.

## Activity analytics¶

In the Workflow section of a campaign detail form in the _Marketing Automation_ app, where the various campaign activities are located, a collection of useful data can be found on every individual activity block, like number of communications Sent, percentage of messages that have been Clicked, and more.

To the left of the activity block, the configured [trigger time](workflow_activities.html) is displayed as a duration (either Hours, Days, Weeks, or Months) if it corresponds to period after the workflow begins.

Nota

If the trigger time is dependent on another activity or triggering action (e.g. Mail: Replied, etc.) the time is displayed, along with the necessary action for that activity to be activated (e.g. `Replied after 2 Hours`).

In the activity block, an icon represents each activity type. An ✉️ (envelope) icon means the activity is an email. Three tiny, interlocking ⚙️ (gear) icons means the activity is an internal action. And, a small, basic 📱 (mobile) icon means the activity is an SMS.

Suggerimento

The activity type name is also displayed in smaller font below the activity title.

Beside the activity icon, at the top of the activity block, is the title of the activity. To the right of the activity title, there are Edit and Delete buttons.

Click Edit to open the Open: Activities pop-up form for that specific activity, in which that activity can be modified. Click the Delete button to completely delete that specific activity from the workflow.

Vedi anche

[Campaign workflow activities](workflow_activities.html)

### Activity graph tab¶

In every activity block, the Graph (pie chart icon) tab is open by default, displaying related metrics as a simple line graph. The success metrics are represented in `green` and the rejected metrics are represented in `red`.

Numerical representations of both Success and Rejected activities are shown to the right of the line graph.

Suggerimento

Hovering over any point in the line graph of the activity block reveals a notated breakdown of data for that specific date.

Beneath the graph in the activity block, for _Email_ or _SMS_ activity types, a line of accessible data figures provide a bird’s eye view of the campaign activity, including: Sent (numerical), Clicked (percentage), Replied (percentage), and Bounced (percentage).

Suggerimento

Clicking any of those stats on the DETAILS line, beneath the line graph, reveals a separate page containing every specific record for that particular data point.

### Activity filter tab¶

Next to the Graph tab on the activity block, there’s the option to open a Filter tab (represented by a filter/funnel icon).

Clicking the Filter tab on an activity block, reveals what the specific filters are for that particular campaign activity, and how many records in the database match that specific criteria.

Suggerimento

Clicking the records link beneath the displayed filter reveals a separate pop-up window containing a list of all the records that match that specific campaign activity rule(s).

## Link tracker¶

Odoo tracks all URLs used in marketing campaigns. To access and analyze those URLs, navigate to Marketing Automation app ‣ Reporting ‣ Link Tracker. Doing so reveals a Link Statistics page, wherein all campaign-related URLs can be analyzed.

The default view on the Link Statistics page is the Bar Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Pie Chart.

Beside that, there is also the option to view the statistics as Stacked, and the data can be put into Descending or Ascending order.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Number of Clicks or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

## Tracce¶

Odoo tracks all activities used in every marketing campaign. The data related to these activities can be accessed and analyzed in the Traces page, which can be found by navigating to Marketing Automation app ‣ Reporting ‣ Traces.

The default view on the Traces page is the Bar Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Pie Chart.

At the top of the graph, there’s a color key, informing the user which activities have been Processed, Scheduled, and Rejected. There’s also an outline indicator to inform users of the Sum of certain activities, as well.

Beside the various view option in the upper-left corner of the Traces page, there is also the option to view the statistics as Stacked, and the data can be put into Descending or Ascending order.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Document ID or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

## Partecipanti¶

Odoo tracks all participants related to every marketing campaign. The data related to these participants can be accessed and analyzed in the Participants page, which can be found by navigating to Marketing Automation app ‣ Reporting ‣ Participants.

The default view on the Participants page is the Pie Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Bar Chart.

At the top of the graph, there’s a color key that describes the type of participants found in the graph.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Record ID or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/marketing_automation/understanding_metrics.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](campaign_templates.html "Campaign templates") |
  * [precedente](testing_running.html "Testing/running campaigns") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign metrics


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record