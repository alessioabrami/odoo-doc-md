# Valutazioni — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appraisals/new_appraisals.html "Conduct appraisals") |
  * [precedente](employees/retention_report.html "Employee retention report") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Valutazioni



# Valutazioni¶

In Odoo, the _Appraisals_ application can be used to evaluate employee performance on a recurring basis. Managers can evaluate the performance of their employees, and also allow employees to do a self-assessment of their own. Appraisals are customizable, and can be set for any kind of schedule desired.

Appraisals give employees valuable feedback, including actionable goals to work toward, and measurable skills to improve upon. Additionally, appraisals may form the basis for raises, promotions, and other benefits.

Regular appraisals are good for both the employees and the company, since they can accurately measure performance based on company goals, and show employees where they need to improve.

## Configurazione¶

The Configuration menu in the _Appraisals_ application is where the settings can be configured, feedback templates can be edited, frequencies can be set, evaluation scales can be managed, data for 360 feedback can be stored, and goal tags can be viewed/created.

### Impostazioni¶

To access the _Settings_ menu, navigate to Appraisals application ‣ Configuration ‣ Settings.

#### Feedback templates¶

Feedback templates are form outlines used during an employee appraisal. Any edits made to a template are, ultimately, reflected in the appraisals sent to employees.

There are two default templates pre-configured in Odoo _Appraisals_ : one for employee feedback, and one for manager feedback. Each contains several sections, along with questions, and brief explanations for how to respond to the questions.

The Employee Feedback Template has the following sections: My work, My future, and My feelings.

The Manager Feedback Template has the following sections: Feedback, Evaluation, and Improvements.

Any desired changes to the default feedback templates can be made by making changes directly in each template.

#### Valutazioni¶

The Appraisals section of the settings menu determines the frequency that appraisals are performed, and if it is possible to request additional feedback.

##### Appraisals plans¶

By default, appraisals are pre-configured to be automatically created six months after an employee is hired, with a second appraisal exactly six months after that.

Once those two initial appraisals have been completed in the employee’s first year, following appraisals are only created once a year (every twelve months).

To modify this schedule, change the number of months in the blank fields under the Appraisals Plans section.

Importante

If the Appraisals Plans section is modified, **all** empty Next Appraisal Dates are modified for **all** employees.

##### 360 feedback¶

The 360 Feedback option can be enabled to allow managers to request feedback from other employees using a different survey form, at any time, independent of the appraisal schedule.

Typically, managers ask for feedback from other people who work with an employee they manage. This includes the employee’s various managers, peers, and direct reports.

To view the 360 Feedback survey, click the → Internal link icon at the end of the Default Template field. The 360 Feedback survey loads, and any desired changes to the survey can be made.

For more information on how to edit a survey, refer to the [Create surveys](../marketing/surveys/create.html) document.

Importante

The 360 Feedback form is a pre-configured survey within the _Surveys_ application. In order to use the 360 Feedback option, including the ability to edit the survey, the _Surveys_ application **must** be installed.

### Evaluation scale¶

On each employee appraisal form, final rating options appear by default. To view and edit these options, navigate to Appraisals application ‣ Configuration ‣ Evaluation Scale. This presents the ratings in a list view.

The pre-configured ratings are Needs Improvement, Meets Expectations, Exceeds Expectations, and Strongly Exceeds Expectations. To add another rating, click the New button.

When the New button is clicked on the Evaluation Scale page, a blank line appears at the bottom of the list. Enter the name of the rating in the field.

To rearrange the order of the ratings, click the (six small gray boxes) icon to the left of a rating, and drag the rating to the desired position on the list.

### 360 feedback¶

The 360 Feedback section displays information for all the surveys currently configured in the _Appraisals_ application. To view the surveys, and their statistics, navigate to Appraisals application ‣ Configuration ‣ 360 Feedback.

Each appraisal (or survey) is presented in its own line on the 360 Feedback page, along with various information related to that particular appraisal.

Each appraisal includes the following information:

  * Survey Name: the name of the specific survey.

  * Responsible: the employee responsible for the survey, including the month and year they were given that designation.

  * Questions: the number of questions in that particular survey.

  * Average Duration: the average time a user spends completing the survey.

  * Registered: the number of people who have been sent the survey.

  * Completed: the number of people who have completed the survey.




Each appraisal also has two buttons at the end of each line: a Test button and a See Results button.

To see what an appraisal looks like for the end user (i.e. an employee), click the Test button, and the appraisal loads in a new browser tab. The entire appraisal loads, and can be clicked through without having to enter any answers.

To exit, close the tab. Or, click This is a Test Survey. → Edit Survey at the top of the page to be taken to the detail form for that particular survey.

To view the results from everyone who completed an appraisal, click the See Results button. This presents all the answers for the survey in a new tab. Each question provides information on how many people responded to a question, and how many people skipped it. All answers for each question are visible.

To exit, close the tab. Or, click → Edit Survey at the top of the page to be taken to the detail form for that particular survey.

In addition to viewing the responses from past appraisals and surveys, new surveys can also be created from the 360 Feedback page. Simply click the New button in the top-left of the page to create a new survey.

For more information on how to create a survey, refer to the [Create surveys](../marketing/surveys/create.html) document.

Nota

In previous versions of Odoo, this section was referred to as Surveys.

Vedi anche

  * [Conduct appraisals](appraisals/new_appraisals.html)

  * [Obiettivi](appraisals/goals.html)

  * [Appraisal analysis](appraisals/appraisal_analysis.html)

  * [Skills evolution](appraisals/skills_evolution.html)




  * [Conduct appraisals](appraisals/new_appraisals.html)
  * [Obiettivi](appraisals/goals.html)
  * [Appraisal analysis](appraisals/appraisal_analysis.html)
  * [Skills evolution](appraisals/skills_evolution.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/appraisals.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appraisals/new_appraisals.html "Conduct appraisals") |
  * [precedente](employees/retention_report.html "Employee retention report") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Valutazioni


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