# Add new applicants — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](schedule_interviews.html "Schedule interviews") |
  * [precedente](recruitment-flow.html "Recruitment flow") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Add new applicants



# Add new applicants¶

Once an applicant submits an application, either using the online application, or emailing a job position alias, an applicant card is automatically created in the _Recruitment_ application.

However, in some instances, applicants may need to be created manually in the database. This could be necessary if, for example, a company accepts paper applications in the mail, or is meeting prospective applicants at an in-person job fair.

To view current applicants, navigate to the Recruitment app, then click the desired job position card. Doing so reveals the Applications page, which displays all applicants for that specific role, in a default Kanban view, organized by stage.

Add new applicants from a job position’s Applications page by using either: the New button or the quick add button.

## Aggiunta rapida¶

On the Applications page, click the on the quick add button, represented by a small __(plus) icon in the top-right corner of each stage to quickly add a new applicant to that stage.

Enter the following information on the card:

  * Subject/Application: enter the title for the card. Typically, this is the applicant’s name, and job position being applied to. For example: `Laura Smith - HR Manager`. The text entered in this field is **not** visible in the Kanban view of the Applications page, unless the Applicant’s Name field is left blank.

  * Applicant’s Name: enter the applicant’s name. Displays as the card title in the Kanban view of the Applications page.

  * Email: enter the applicant’s email address.

  * Applied Job: the current job position populates this field. If needed, the job position can be changed by selecting a different position from the drop-down menu. If a different job position is selected, after the card is created, the card appears on the Applications page for that newly-selected job position.




After the information is entered, click Add. The applicant appears in the list, and a new blank applicant card appears.

If preferred, after entering the Applicant’s Name in the Kanban card that appears, click Edit, and a detailed applicant form loads. Refer to the New applicant form section for details about filling out the form.

When doing a quick add, clicking away from an empty card, or clicking the __( trash) icon, discards the applicant.

## New applicant form¶

On the new applicant form, the Subject / Application field is populated with the pre-selected job position, by default. Certain fields on the applicant card may also be pre-populated, depending on how the job position is configured. Typically, the Job section, as well as the Recruiter field, are pre-populated.

Complete the fields in the following sections on the new applicant form.

Nota

Depending on installed applications and configurations, some fields may **not** be displayed.

### Applicant section¶

  * Subject/Application Name: this is the **only** required field. Enter the title for the card in this field. Typically, this is the applicant’s name, and the job position being applied to. For example: `John Smith - Experienced Developer`. This field is **not** visible in the Kanban view of the Applications page, unless the Applicant’s Name is left blank.

  * Applicant’s Name: enter the applicant’s name. This field is displayed as the card title in the Kanban view of the Applications page.

  * Email: enter the applicant’s email address.

  * Phone: enter the applicant’s phone number.

  * Mobile: enter the applicant’s mobile number.

  * LinkedIn Profile: enter the web address for the applicant’s personal profile on LinkedIn.

  * Degree: select the applicant’s highest level of education from the drop-down menu. Options are: Graduate, Bachelor Degree, Master Degree, or Doctoral Degree. The Graduate option indicates the applicant graduated at the highest level of school before a Bachelor’s degree, such as a high school or secondary school diploma, depending on the country.

  * Interviewers: using the drop-down menu, select the people to conduct the interviews. The selected people **must** have either _recruiter_ or _officer_ rights configured for the _Recruitment_ application to appear in the drop-down list. Refer to the [Access rights](../../general/users/access_rights.html) documentation for more information.

  * Recruiter: select the user responsible for the entire recruitment process for the job position.

  * Evaluation: represents a rating for the applicant: one star (______) is Good, two stars (______) is Very Good, and three stars (______)is Excellent.

  * Source: using the drop-down menu, select where the applicant learned about the job position. The following options come pre-configured in Odoo: Search engine, Lead Recall, Newsletter, Facebook, Twitter, LinkedIn, Monster, Glassdoor, and Craigslist. To add a new Source, type in the source, then click Create «(new source)».

  * Medium: using the drop-down menu, specify how the job listing was found. The pre-configured options are: Banner, Direct, Email, Facebook, Google Adwords, LinkedIn, Phone, Television, Twitter (now known as «X»), or Website. To add a new Medium, type in the medium, then click Create «(new medium)».

  * Referred By User: if referral points are to be earned for this job position in the _Referrals_ application, select the user who referred the applicant from the drop-down menu. The _Referrals_ application **must** be installed for this field to appear.

  * Availability: select the available start date for the applicant. To select a date, click on the field to reveal a popover calendar. Use the __(left) and __(right) arrows on either side of the month to navigate to the desired month, then click the desired date. Leaving this field blank indicates the applicant can start immediately.

  * Tags: select as many tags as desired from the drop-down menu. To add a tag that does not exist, type in the tag name, then click Create «new tag» from the resulting drop-down menu.




### Job section¶

The following fields are pre-populated when creating a new applicant, as long as these field are specified on the job position form. Editing the fields is possible, if desired.

  * Applied Job: select the job position the applicant is applying to from the drop-down menu.

  * Department: select the department the job position falls under from the drop-down menu.

  * Company: select the company the job position is for using the drop-down menu. This field **only** appears when in a multi-company database.




### Contract section¶

  * Expected Salary: enter the amount the applicant is requesting in this field. The number should be in a `XX,XXX.XX` format. The currency is determined by the localization setting for the company.

    * Extra advantages…: if any extra advantages are requested by the applicant, enter it in the Extra advantages… field to the right of the Expected Salary field. This should be short and descriptive, such as `1 week extra vacation` or `dental plan`.

  * Proposed Salary: enter the amount to be offered to the applicant for the role in this field. The number should be in a `XX,XXX.XX` format.

    * Extra advantages…: if any extra advantages are offered to the applicant, enter it in the Extra advantages… field to the right of the Proposed Salary field. This should be short and descriptive, such as `unlimited sick time` or `retirement plan`.




### Application Summary tab¶

Any additional details or notes that should be added to the applicant’s card can be typed into this field.

### Skills tab¶

Skills can be added to the applicant’s card. For details on adding skills, refer to the [Create new employees](../employees/new_employee.html#employees-skills) document.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/recruitment/add-new-applicants.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](schedule_interviews.html "Schedule interviews") |
  * [precedente](recruitment-flow.html "Recruitment flow") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Add new applicants


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