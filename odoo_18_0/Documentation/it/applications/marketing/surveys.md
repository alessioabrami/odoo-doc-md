# Sondaggi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](surveys/create.html "Create surveys") |
  * [precedente](events/revenues_report.html "Revenues report") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Sondaggi



# Sondaggi¶

Companies gather valuable insights from customers and employees through surveys, aiding informed decision-making.

With Odoo _Surveys_ , users create various surveys, questionnaires, certifications, assessments, and so much more. These can be used to collect feedback, evaluate the success of a recent event, and measure the satisfaction of customers and/or employees. This process yields valuable insights into shifting market trends.

Vedi anche

[Odoo Tutorials: Surveys](https://www.odoo.com/slides/surveys-62)

#### [Create surveysDiscover how to create surveys with Odoo. ](surveys/create.html)#### [Scoring surveysLearn how to create and analyze survey scores with Odoo. ](surveys/scoring.html)#### [Create questionsSee how to create, configure, and customize all types of survey questions with Odoo. ](surveys/questions.html)#### [Live Session surveysFind out everything there is to know about Odoo’s unique Live Session surveys. ](surveys/live_session.html)#### [Survey analysisExplore the various ways to analyze surveys using Odoo’s in-depth reporting pages. ](surveys/analysis.html)

## Bacheca¶

Upon opening the _Surveys_ application, Odoo presents the main dashboard of the _Surveys_ application, otherwise known as the Surveys page.

Suggerimento

The _Surveys_ dashboard can be accessed at any time throughout the application by clicking Surveys from the header menu.

In the upper-left corner, there is a New button. When clicked, Odoo presents a blank survey form that can be used to create a survey.

On the dashboard, all the surveys that have been created in the database are displayed in a default Kanban view.

From left-to-right, after the survey name, the user who is responsible for it, and the month it was created, each line on the _Surveys_ dashboard shows the following:

  * Number of Questions in that particular survey

  * Average Duration of the survey (how long it typically takes a participant to complete)

  * Number of Registered participants for the survey

  * Number of times that particular survey has been Completed

  * Percentage and data bar showcasing how many people have Passed or become Certified

Nota

The Passed percentage and bar **only** appears when a _Required Score_ has been configured for that particular survey.

The Certified percentage and bar **only** appears if that particular survey has the _Is a Certification_ option enabled on the survey form.

If neither Passed nor Certified appear on the line, that indicates the survey is without a _Required Score_ and was not enabled with the _Is a Certification_ option.

  * Number of Courses related to that survey, which **only** appears if more than one course has been created and attached to a single survey




Nota

A half-trophy background image behind the survey name indicates that the survey is a _Certification_.

To the far-right of those data points on the survey lines, located on the _Surveys_ application dashboard, are a collection of buttons.

Those buttons are as follows:

  * Share: click to reveal a Share a Survey pop-up form that can be used to invite potential participants to the survey - complete with a Survey Link that can be copied and sent to potential participants, and a Send by Email toggle switch.

When the Send by Email toggle is active (green switch), additional fields appear, in which Recipients, Additional Emails, and a Subject can be added to the email.

Below that, a dynamic email template, complete with a Start Certification button appears, which can be modified, as well, if needed.

Attachments can be added to the email, as well as an Answer deadline can be set, if needed.

Once modifications are complete, click Send to send that email invite to all the email addresses/contacts listed in the Recipients field.

Suggerimento

The default Mail Template for survey invites can be edited by navigating to Settings ‣ Technical ‣ Email Templates and searching for `Survey: Invite`.

Nota

The Send by Email toggle switch is **not** present when the survey line has zero questions.

The Survey Link only appears when the survey’s _Access Mode_ is set to _Anyone with the link_.

The Additional Emails field only appears when the survey’s _Require Login_ field is **not** active.

  * Test: click to take a test version of the survey in a new tab, from the point-of-view of a survey participant, in order to check for any errors or inconsistencies.

  * See results: click to reveal a new tab showcasing detailed metrics and graphical representations of all survey participants, questions, and responses for deeper analysis.

  * Start Live Session: click to initiate a _Live session_ survey, and reveal a session manager window in a new tab. This button is **not** present for surveys that have enabled the _Is a Certification_ option on the survey form.

  * End Live Session: click to end a _Live session_ survey that has been officially started. This button option **only** appears on survey lines that have previously initiated a live session.




Above the buttons that are located to the far-right of the survey lines, a ⋮ (three dots) icon appears when the cursor hovers over that particular line. When the ⋮ (three dots) icon is clicked, a drop-down menu with some configuration-related options appear:

The options are:

  * Edit Survey: when clicked, Odoo reveals the survey form for that particular survey, which can then be modified in a number of different ways.

  * Share: when clicked, Odoo reveals the Share a Survey pop-up form that can be used to invite potential participants to the survey.

  * Delete: when clicked, Odoo presents a pop-up window, wherein the user **must** confirm they want to delete the survey entirely, which they can do by clicking the Delete button at the bottom of the pop-up window.

  * Color: users can opt to choose a color to add to the survey line on the dashboard for added organizational purposes, if needed.




Beneath the buttons that are located to the far-right of the survey lines, there is an _Activities_ button, represented by a 🕘 (clock) icon. When clicked, a mini pop-up window appears, from which activities related to that particular survey can be scheduled and customized.

### Vista elenco¶

The _Surveys_ dashboard is shown in the Kanban view, by default, but there is also a list view option available in the upper-right corner, represented by a ≣ (bars) icon.

When the ≣ (bars) icon is clicked, the survey related data is displayed in a list view.

The columns shown on the _Surveys_ app dashboard, while in list view, are as follows:

  * Survey Title

  * Responsible

  * Average Duration

  * Registered

  * Success Ratio (%)

  * Avg Score (%)




Suggerimento

Additional columns can be added to the _Surveys_ application dashboard, while in list view, by clicking the _additional options_ drop-down menu, located to the far-right of the column titles, represented by a (slider with two dots) icon.

### Activities view¶

To have the _Surveys_ application dashboard display nothing but the activities associated to the surveys in the database, click the 🕘 (clock) icon to the far-right of the other view options, located in the upper-right corner.

Doing so reveals a table with rows and columns. The rows show the different surveys in the database, and the columns depict the various activity types.

Nota

A new survey cannot be created in this view, as it is solely for the purpose of creating and viewing scheduled activities.

## Create surveys¶

Learn about all the different options and configurations that can be utilized when creating a survey in Odoo.

Vedi anche

[Create surveys](surveys/create.html)

## Scoring surveys¶

Discover how to measure a survey participant’s performance, or overall satisfaction, with Odoo’s detailed (and fully customizable) survey scoring options.

Vedi anche

[Scoring surveys](surveys/scoring.html)

## Create questions¶

With Odoo _Surveys_ , there are many question types and options to choose from, providing the ability to create any kind of unique survey, questionnarire, and/or certification.

Vedi anche

[Create questions](surveys/questions.html)

## Live Session surveys¶

The _Live Session_ survey option available in Odoo can enhance in-person demonstrations and presentations, where participants” real-time responses can be used to dictate where the conversation goes next.

Vedi anche

[Live Session surveys](surveys/live_session.html)

## Survey analysis¶

Once the surveys start to come in, it is time to analyze the responses from your participants. Fortuantely, the in-depth reporting pages and options available in Odoo _Surveys_ provide countless ways to examine everything related to surveys, and their submitted responses.

Vedi anche

[Survey analysis](surveys/analysis.html)

  * [Create surveys](surveys/create.html)
  * [Scoring surveys](surveys/scoring.html)
  * [Create questions](surveys/questions.html)
  * [Live Session surveys](surveys/live_session.html)
  * [Survey analysis](surveys/analysis.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/surveys.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](surveys/create.html "Create surveys") |
  * [precedente](events/revenues_report.html "Revenues report") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Sondaggi


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
  *[CTR]: click-through rate
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