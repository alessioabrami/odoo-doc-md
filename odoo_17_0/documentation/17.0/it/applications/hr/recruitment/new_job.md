# Job positions — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recruitment-flow.html "Recruitment flow") |
  * [precedente](../recruitment.html "Selezione del personale") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Job positions



# Job positions¶

In Odoo _Recruitment_ , all job positions are shown on the default dashboard in the _Recruitment_ app. This includes positions that are being actively recruited for, as well as inactive positions.

Each job position is shown in an individual Kanban card. If the job position is active, and candidates can apply, a Published banner appears in the top-right corner of the card.

View submitted applications by clicking anywhere on a job position card.

## Create a new job position¶

To create a new job position from the main dashboard in the _Recruitment_ app, click the New button in the top-left corner, and a Create a Job Position modal appears.

First, enter the name of the Job Position (such as `Sales Manager`, `Mechanical Engineer`, etc.) in the field.

Next, enter an Application email by typing in the first half of the email address in the first field, then select the second half of the email using the drop-down menu in the second field. Applicants can send a resumé to this specific email address, and Odoo creates an application for them automatically.

When complete, click the Create button to save the entry, or the Discard button to delete it.

Once the job position has been created, it appears as a card in the Kanban view on the main _Recruitment_ app dashboard.

### Edit a new job position¶

After the job position is created, it’s time to enter the details for the position. Click on the ⋮ (three dots) icon in the upper-right corner of the relevant card to reveal several options, and then click Configuration to edit the details.

All the basic information about the job position is listed under the Recruitment tab.

None of the fields are required, but it is important to configure and populate the Department, Location, Employment Type, and Job Summary fields, as they are all visible to prospective applicants on the website.

The fields can be filled out as follows:

  * Department: select the relevant department for the job position. This is visible on the website.

  * Job Location: select the physical address for the job. If the job position is remote, leave this field blank. This is visible on the website.

  * Email Alias: enter an email address to which applicants can send a resumé. Once emailed, Odoo automatically creates an application for them.

  * Employment Type: select what type of position the job is, using the drop-down menu. The default options are Permanent, Temporary, Seasonal, Interim, Full-Time, and Part-Time. This is visible on the website.

  * Company: select the company the job is for. This field only appears if using a multi-company database.

  * Target: enter the number of employees to be hired for this position.

  * Is Published: activate this option to publish the job online.

  * Website: select the website the job is published on.

  * Recruiter: select the person responsible for recruiting this role.

  * Interviewers: select who should perform the interviews. Multiple people can be selected.

  * Interview Form: select an Interview form that applicants fill out prior to their interview.

  * Contract Template: select a contract template to be used when offering the job to a candidate.

  * Process Details section: this section contains information that is displayed online for the job position. This informs the applicants of the timeline and steps for the recruitment process, so they know when to expect a reply.

    * Time to Answer: enter the number of days before the applicant is contacted.

    * Process: enter the various stages the candidate goes through during the recruitment process.

    * Days to get an Offer: enter the number of days before the applicant should expect an offer after the recruitment process has ended.




Nota

The Process Details section is a text field. All answers are typed in rather than selected from a drop-down menu. The text is displayed on the website exactly as it appears in this tab.

Finally, enter the job description in the Job Summary tab.

### Create interview form¶

An _Interview Form_ is used to determine if a candidate is a good fit for a job position. Interview forms can be as specific or general as desired, and can take the form of a certification, an exam, or a general questionnaire. Interview forms are determined by the recruitment team.

Before creating an interview form, ensure the proper settings are enabled. Navigate to Recruitment app ‣ Configuration ‣ Settings, and under the Recruitment Process section, ensure the Send Interview Survey option is enabled.

Since there are no pre-configured forms in Odoo, all interview forms must be created. To create an interview form, start from the Recruitment tab of the Job Position form. In the Interview Form field, enter a name for the new interview form. As the name is typed, several options populate beneath the entry: Create (interview form name), Search More…, and Create and edit…. Click Create and edit… and a Create Interview Form modal appears.

Nota

The option Search More… only appears if there are any interview forms already created. If no interview forms exist, the only options available are Create (interview form name), and Create and edit….

Proceed to fill out the modal interview form as a typical survey. For specific directions on how to create a survey, refer to the [survey essentials](../../marketing/surveys/create.html) document, which provides step-by-step instructions on how to create and configure a survey.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/new_job.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recruitment-flow.html "Recruitment flow") |
  * [precedente](../recruitment.html "Selezione del personale") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Job positions


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
  *[FBM]: Fulfilled By Merchant
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