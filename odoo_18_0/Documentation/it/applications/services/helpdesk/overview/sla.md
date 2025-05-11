# Service level agreements (SLA) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Rendiconto") |
  * [precedente](help_center.html "Centro assistenza") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Service level agreements (SLA)



# Service level agreements (SLA)¶

A _service level agreement_ (SLA) defines the level of support a customer can expect from a service provider. SLAs provide a timeline that tells customers when they can expect results and keeps the support team on target.

Nota

The _SLA Policies_ feature is enabled by default on newly created **Helpdesk** teams.

To turn off the feature, or edit the working hours, navigate to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. Click on a team to open that team’s configuration page.

From here, scroll to the Performance section. To turn off the SLAs feature for the team, clear the SLA Policies checkbox.

## Create a new SLA policy¶

To create a new policy, go to Helpdesk app ‣ Configuration ‣ SLA Policies, and click New.

Alternatively, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams, and click on a team. Then, click the SLA Policies smart button at the top of the team’s settings page, and click New.

On the blank SLA policy form, enter a Title and a Description for the new policy, and proceed to fill out the form using the steps below.

### Define the criteria for an SLA policy¶

The Criteria section is used to identify which tickets this policy is applied to.

Fill out the following fields to adjust the selection criteria:

Nota

Unless otherwise indicated, multiple selections can be made for each field.

  * Helpdesk Team: A policy can only be applied to one team. _This field is required._

  * Priority: The priority level for a ticket is identified by selecting one, two, or three of the __(star) icons, representing the priority level on the Kanban card or on the ticket itself. The SLA is **only** applied after the priority level has been updated on the ticket to match the SLA criteria. If no selection is made in this field, this policy only applies to tickets marked as `Low Priority`, meaning those with zero __(star) icons.

  * Tags: Tags are used to indicate what the ticket is about. Multiple tags can be applied to a single ticket.

  * Customers: Individual contacts or companies may be selected in this field.

  * Services: This field is available only if a team has the **Timesheets** app enabled. This allows the ticket to link directly to a specific line on a sales order, which must be indicated on the ticket in the Sales Order Items field.




Example

A support team needs to address urgent issues for VIP customers within one business day.

The new policy, titled `8 Hours to close`, is assigned to the `VIP Support` team. It **only** applies to tickets that are assigned three __(star) icons, which equates to an `Urgent` priority level.

At the same time, the tickets can be related to multiple issues, so the policy applies to tickets with `Repair`, `Service`, or `Emergency` tags.

### Establish a target for an SLA policy¶

A _target_ is the stage a ticket needs to reach, and the time allotted to reach that stage, in order to satisfy the SLA policy. Any stage assigned to a team may be selected for the Reach Stage field.

Time spent in stages selected in the Excluding Stages field are **not** included in the calculation of the SLA deadline.

Example

An SLA titled `8 Hours to Close` tracks the working time before a ticket is completed, and would have `Solved` as the Reach Stage. Simultaneously, an SLA titled `2 Days to Start` tracks the working time before work on a ticket has begun, and would have `In Progress` as the Reach Stage.

## Meet SLA deadlines¶

As soon as it is determined that a ticket fits the criteria of an SLA policy, a deadline is calculated. The deadline is based on the creation date of the ticket, as well as the targeted working hours.

Nota

The value indicated next to the Working Hours field of an SLA policy is used to determine the deadline. By default, this is determined by the value set in the Company Working Hours field under Settings app ‣ Employees ‣ Work Organization.

The deadline is then added to the ticket, as well as a tag indicating the name of the SLAs applied.

When a ticket satisfies an SLA policy, the SLA tag turns green, and the deadline disappears from view on the ticket.

Importante

If a ticket fits the criteria for more than one SLA, the earliest occurring deadline is displayed on the ticket. After that deadline has passed, the next deadline is displayed.

If the SLA deadline passes and the ticket has not moved to the Reach Stage, the SLA tag turns red. After the SLA has failed, the red tag stays on the ticket, even after the ticket is moved to the Reach Stage.

## Analyze SLA performance¶

The SLA Status Analysis report tracks how quickly an SLA is fulfilled, as well as the performance of individual team members. Navigate to the report, and corresponding pivot table, by going to Helpdesk app ‣ Reporting ‣ SLA Status Analysis.

### Vista pivot¶

By default, the report displays in a Pivot view. Any SLA policies in the database with tickets that failed to fulfill a policy, are in progress, or have satisfied a policy are listed. By default, they are grouped by team and ticket count.

The pivot view aggregates data, which can be manipulated by adding measures and filters.¶

To change the display, or add additional measurements, click the Measures button to reveal a drop-down menu of reporting criteria, and choose from the options available.

Whenever a measurement is picked, a __(check) icon appears in the drop-down menu to indicate that the measurement is included, and a corresponding new column emerges in the pivot table to show the relevant calculations.

To add a group to a row or column, click the __(plus) icon next to the policy name and then select one of the groups. To remove one, click the __(minus) icon next to the policy name.

### Vista grafico¶

Switch to the graph view by selecting the __(graph view) icon at the top of the screen. To switch between the different charts, select the _related icon_ at the top of the chart, while in graph view.

Bar ChartLine ChartPie Chart

A bar chart can deal with larger data sets and compare data across several categories.¶

A line chart can visualize data trends or changes over time.¶

A pie chart compares data among a small number of categories.¶

Suggerimento

Both the _bar chart_ and _line chart_ can utilize the _stacked_ view option. This presents two or more groups of data on top of each other, instead of next to each other, making it easier to compare data. While viewing either a bar chart or line chart, click the __(stacked) icon to toggle the stacked view option on or off.

### Cohort view¶

The _cohort_ view is used to track the changes in data over a period of time. To display the SLA Status Analysis report in a cohort view, click the __(cohort) icon, next to the other view options.

The cohort view examines the life cycle of data over time.¶

Vedi anche

  * [Reporting views](../../../essentials/reporting.html#reporting-views)

  * [Allow customers to close their tickets](../advanced/close_tickets.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/services/helpdesk/overview/sla.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Rendiconto") |
  * [precedente](help_center.html "Centro assistenza") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Service level agreements (SLA)


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
  *[SLA]: Service Level Agreements
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