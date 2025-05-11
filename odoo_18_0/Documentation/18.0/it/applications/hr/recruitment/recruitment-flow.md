# Recruitment flow — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](add-new-applicants.html "Add new applicants") |
  * [precedente](new_job.html "Job positions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Recruitment flow



# Recruitment flow¶

When a prospective employee applies for a job in Odoo, there is a preconfigured process from the initial inquiry to the [creating of a new employee](offer_job_positions.html#recruitment-new-employee) once hired. The following outlines the default recruitment process for Odoo’s _Recruitment_ application.

Importante

The following is based on Odoo’s default recruitment pipeline. Be advised that if [modifications are made](../recruitment.html#recruitment-customize-stages) to the pipeline, the process differs.

## Nuova¶

At the start of the process, all applicants appear in the New stage on the Applications page, whether submitted online or if the applicant is [manually entered by a recruiter](add-new-applicants.html).

When the applicant’s card is created, Odoo automatically populates the Subject/Application, the Applicant’s Name, Email, and Mobile number, on the applicant’s card. This information is required when applying for a job position, by default.

Nota

If the website application form is modified, different fields may be populated, based on what information is requested on the website.

If the applicant entered any information in the _Short Introduction_ section of the online application, it populates the Application Summary tab at the bottom of the applicant’s card.

### Curriculum vitae¶

If a resumé was attached to the online application, it appears in the Files section of the chatter, and is also stored in the _Documents_ application.

To find the recruitment documents, navigate to the main Documents app dashboard, and click the Recruitment folder on the left-hand side. All recruitment documents are stored within that folder.

If the [CV Display](../recruitment.html#recruitment-cv-display) option was enabled in the [Settings](../recruitment.html#recruitment-settings) of the _Recruitment_ app, the resumé appears on the applicant’s card, on the right-hand side.

Nota

Depending on the browser zoom level, or size of the browser screen, the resumé may appear below the main applicant card information as a PDF link.

### Send interview¶

At any point in the hiring process, an interview can be sent to the applicant to obtain more information. These interviews are custom-made, and can be formatted in a variety of ways.

The _Surveys_ application is **required** to send interviews to an applicant, so it **must** be installed.

Odoo uses the term _interview_ , but these can be thought of as questionnaires, surveys, tests, certifications, etc. Custom interviews can be formatted to suit each individual job position’s needs. For more information on creating and editing interviews, refer to the [Job positions](new_job.html) documentation.

Example

A job position for a computer programmer could have an interview in the form of a programming quiz to determine the skill level of the applicant. A job position for a restaurant server could have a questionnaire inquiring about the applicant’s availability, if the desired applicant needs to be available on weekend evenings.

To send an interview to an applicant, first click the applicant’s card from the Applications page, to view the detailed applicant information. At the top-left of the applicant’s card, click the Send Interview button.

If the applicant’s card has an email address on file, a Send an interview pop-up window appears, with the Recipients, Subject, and email body populated.

Nota

To send an email to an applicant, there **must** be an Email address on the applicant’s card.

If an email address is not entered on the applicant’s card, when the Send Interview button is clicked, an Edit: (Applicant’s Name) pop-up window appears, _on top of_ the Send an interview pop-up window.

Enter the email address in the Email field, then click Save & Close.

Once the applicant’s information is saved, the Edit: (Applicant’s Name) pop-up window closes, and the Send an interview pop-up window remains.

Sometimes, preconfigured email templates in Odoo use dynamic placeholders, which are automatically filled with specific data when the email is sent. For example, if a placeholder for the applicant’s name is used, it is replaced with the actual name of the applicant in the email. For more detailed information on email templates, refer to the [Modelli e-mail](../../general/companies/email_template.html) documentation.

Add the email addresses of any additional recipients for the survey in the Additional emails field, if more people should receive the email. If an email address is in the database as a contact, add that contact in the Recipients field. If an email should be sent to someone who is not in the database as a contact, and they should **not** be added as a contact, add their email address in the Additional emails field.

If any attachments need to be added, click the __ Attachments button, and a file explorer window appears. Navigate to the desired file, and click Open to attach it to the email. The attachment loads, and is listed above the __ Attachments button.

If the emailed interview must be completed by a specific date, enter that date in the Answer deadline field, located in the lower-right area of the pop-up window.

To do so, click the empty field next to Answer deadline, and a calendar selector appears. Use the __(left) and __(right) arrows, on either side of the month, to navigate to the desired month. Then, click on the desired day to select the date.

The Mail Template field is pre-populated, based on the configuration for the interview. A different template can be chosen from the drop-down menu, if desired. If a new template is selected, the new email template loads in the email body.

To send the email with the interview link to the applicant, click Send at the bottom of the email pop-up window.

## Initial qualification¶

If an applicant seems to be a good potential candidate, they are moved to the Initial Qualification stage.

This stage exists to quickly sort candidates that have potential, from those that do not meet the requirements. No automatic actions, such as emails, are set for this stage. This stage simply informs the recruitment team to potentially set up a phone call or an interview with the candidate.

Nota

> In order to move an applicant’s card from one stage to another, the applicant’s card can either be dragged and dropped in the Kanban view of the Applications page to the desired stage, or the stage can be modified on the applicant’s card.
> 
> To change the stage on the applicant’s card, first click the desired applicant’s card from the Applications page. The current stage for the card is highlighted at the top on a status bar, above the card.
> 
> Click the desired stage for the card, and the stage changes. A log note indicating the stage change appears in the chatter, as well.

## First interview¶

After an applicant has passed the Initial Qualification stage, they can be manually moved to the First Interview stage on the Applications page, while in Kanban view.

To move the applicant to the next stage, drag-and-drop the applicant’s card to the First Interview stage.

Alternatively, open the desired applicant’s card from the Applications page, and click the First Interview stage on the status bar at the top of the individual applicant’s card.

Suggerimento

The First Interview stage can be modified, so when the applicant’s card moves to the First Interview stage, an email can be automatically sent to the applicant, stating an interview is requested. In this pre-configured email template, a link to the recruiting team’s calendar appears, allowing the applicant to schedule their interview.

[Edit](../recruitment.html#recruitment-edit-stage) the First Interview stage, and select the Recruitment: Schedule Interview option in the Email Template field, to automate this action.

## Second interview¶

After an applicant has passed the First Interview stage, they can be moved to the Second Interview stage. To move the applicant to the next stage, drag-and-drop the applicant’s card to the Second Interview stage from the Kanban view of the Applications page, or click on the Second Interview stage at the top of the individual applicant’s card.

When the applicant’s card moves to the Second Interview stage, there are no automatic activities or emails configured for this stage, by default. The recruiter can now [schedule a second interview](schedule_interviews.html#recruitment-schedule-interviews-recruitment-scheduled) with the applicant, following the same process as the first interview.

## Proposta contratto¶

After the applicant has completed the various interview processes, the next step is to [send the job offer](offer_job_positions.html).

Once the offer has been sent, drag-and-drop the applicant’s card to the Contract Proposal stage from the Kanban view of the Applications page, or click on the Contract Proposal stage at the top of the individual applicant’s card.

## Contratto firmato¶

Once the contract has been signed, and the applicant has been hired, the applicant’s card moves to the Contract Signed stage.

Drag-and-drop the applicant’s card to the Contract Signed stage from the Kanban view of the Applications page, or click the __(ellipsis) icon at the top of the individual applicant’s card, then click Contract Signed on the status bar.

## Refuse applicant¶

At any point in the recruitment process, a candidate can be [refused](refuse_applicant.html).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/recruitment/recruitment-flow.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](add-new-applicants.html "Add new applicants") |
  * [precedente](new_job.html "Job positions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Recruitment flow


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