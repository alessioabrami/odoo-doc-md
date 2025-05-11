# Procedura di uscita — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention_report.html "Employee retention report") |
  * [precedente](equipment.html "Attrezzatura") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Procedura di uscita



# Procedura di uscita¶

When an employee leaves the company, it is important to have an offboarding plan to ensure all necessary steps are followed, such as returning equipment, revoking access to business systems, filling out HR forms, having an exit interview, and more. Depending on the company, there could be several different offboarding plans, configured for specific departments or divisions, that have different requirements and steps from the main offboarding plan.

In addition to an offboarding plan, the employee record must be updated to reflect their departure, log the reason why they left, close any open activities associated with the employee, and provide them with any important documents.

## View offboarding plan¶

Before offboarding can begin, it is recommended to check the default offboarding plan that comes preconfigured with the **Employees** app. To view the current default plan, navigate to Employees app ‣ Configuration ‣ Activity Plan. Click Offboarding to view the detailed offboarding plan form.

### Offboarding plan steps¶

The default Offboarding plan is minimal, with two default steps (three if the **Fleet** app is installed). All steps are To-Do activities, and are scheduled for the day the offboarding plan is launched (0 days Before Plan Date).

  * Organize knowledge transfer inside the team: The manager must ensure all knowledge the employee has relating to their job position, is either documented or shared with colleagues so there is no knowledge gap.

  * Take Back Fleet: The fleet manager ensures any vehicles assigned to the employee are either unassigned (available for other employees) or the next driver is assigned. This step only appears if the **Fleet** app is installed.

  * Take Back HR Materials: The manager must obtain any documents and materials the HR department requires. It is recommended to check with the HR department to ensure everything required for this step is completed.




## Modify offboarding plan¶

The default offboarding plan is minimal, so that modifications can be made to accommodate any company’s offboarding needs. Every company has different requirements, therefore it is necessary to add the required steps to the offboarding plan.

If the offboarding plan is universal, add or modify the default offboarding plan. If the offboarding plan needed is only for a specific department, then a new plan should be created, specifically for that department.

To modify the default plan, first navigate to Employees app ‣ Configuration ‣ Activity Plan, then click on Offboarding.

To modify a step, click on the step and an Open: Activities pop-up window appears. Make any desired modifications to the step, then click Save to accept the changes and close the pop-up window.

To add a new step, click Add a line at the bottom of the listed activities in the Activities To Create tab, and a blank Create Activities pop-up window appears. Enter all the information in the pop-up window, then click Save & Close if there are no other steps to add, or click Save & New if more steps are needed.

Configure all the desired steps for the offboarding plan.

## Create offboarding plan¶

For some companies, specific offboarding plans may be necessary for some departments. For these cases, a new department-specific offboarding plan may be needed.

To create a new offboarding plan, first navigate to Employees app ‣ Configuration ‣ Activity Plan. Click the New button in the upper-left corner, and a blank plan form loads.

Inserisci le seguenti informazioni nel modulo:

  * Plan Name: the specific name for the plan.

  * Model: This field specifies where this plan can be used. In this case, in the **Employees** app. This field is not able to be modified.

  * Department: if left blank (the default setting) the plan is available for all departments. To make the plan department-specific, select a department using the drop-down menu.




Next, add the various steps for the plan by clicking Add a line at the bottom of the listed activities in the Activities To Create tab, and a blank Create Activities pop-up window appears.

Enter the following information in the pop-up window:

  * Activity Type: Using the drop-down menu, select the specific activity to be scheduled. The default options are Email, Call, Meeting, To-Do, or Upload Document. If the **Sign** app is installed, a Request Signature option is available.

  * Summary: Enter a short description for the step.

  * Assignment: Using the drop-down menu, select the person assigned to perform the activity. The default options are: Ask at launch, Default user, Coach, Manager, and Employee. If the **Fleet** app is installed, a Fleet Manager option is available.

Nota

The selection for the Assignment role is in relation to the employee. If Coach is selected, the employee’s coach is assigned to the activity.

If Default user is selected, an Assigned to field appears. Using the drop-down menu, select the user who will always be assigned this activity.

  * Interval: Configure the fields in this line to determine the due date of the activity. Enter a number in the first field, then, using the drop-down menus in the following two fields, configure when the due date should be created; (`#`) of days, weeks, or months, either Before Plan Date or After Plan Date.




When the Create Activities for is completed, click Save & Close if there are no other steps to add, or click Save & New to add more steps, as needed.

Example

A company specializing in after-school art programs has two separate offboarding plans, one for the teachers working in the field, and one for office workers.

The offboarding plan for the teachers is set for the Art Program Teachers department, and includes specialized tasks relating to those jobs. These include ensuring all art supplies are catalogued and returned, all student feedback forms are turned in, and all access badges and keys for the various locations are returned.

## Launch offboarding plan¶

After an employee has given notice (typically two weeks) or once the company has decided to terminate the working relationship with the employee, the offboarding plan should be launched. Navigate to the Employees app and click on the departing employee profile. Click the Launch Plan button, and a blank Launch Plan pop-up window loads.

Using the drop-down menu, select the desired offboarding plan in the Plan field. Then, using the calendar selector, set a date in the Plan Date field. This is typically the day the employee gave notice, but any date can be selected.

The right-side of the Launch Plan pop-up window displays all the steps in the selected plan, grouped by what was selected in the Assignment fields for the various plan steps.

Once the Plan and Plan Date fields are configured, click the Schedule button, and Odoo schedules everything in the plan, according to their respective due dates. All scheduled activities appear in the chatter of the employee profile.

## Archive an employee¶

In Odoo, when an employee leaves the company they must be _archived_. This step should be done _after_ the employee has been fully offboarded. To archive an employee, first navigate to the Employees app. From here, locate the employee who is leaving the company, and click on their employee card.

The employee form loads, displaying all their information. Click the __(gear) icon in the top-left corner, and a drop-down menu appears. Click __ Archive, and an Employee Termination pop-up window appears.

Fill out the following fields on the form:

  * Departure Reason: Select a reason the employee is leaving from the drop-down menu. The default options are:

    * Fired: Select this option when an employee is being let go, and the company has given notice.

    * Resigned: Select this option when the employee no longer wishes to be employed, and the employee has given notice.

    * Resigned: Retired: Select this option when the employee is retiring.

    * Became Freelance: Select this option when the employee is no longer working for the company, but is becoming a freelance worker instead.

    * Mutual Agreement: Select this option when both parties have agreed to terminate their working relationship.

  * Contract End Date: Using the calendar selector, select the last day the employee is working for the company.

  * Detailed Reason: Enter a short description for the employee’s departure in this field.

  * Close Activities: Tick the checkbox next to each type of activity to close or delete any open activities associated with it. It is recommended to tick **all** checkboxes that are applicable. The available options are:

    * Appraisals: cancels all appraisals scheduled after the contract end date.

    * Contract: applies an end date for the current contract.

    * Company Car: removes the employee as the driver for their current company car, and [assigns the next driver](../fleet/new_vehicle.html#fleet-new-vehicle-new-driver), if applicable.

    * Equipment: unassigns the employee from any assigned equipment.

  * HR Info: Tick the checkbox next to Send Access Link to send a download link to the employee’s personal email address, containing all their personal HR files.

  * Private Email: This field appears if the HR Info checkbox is ticked. If there is a private email listed on the employee profile, this field is automatically populated. If no private email address is on their record, enter the private email address for the employee.




When the form is complete, click Apply. The employee record is archived, an email with a download link to their personal documents is sent to the employee’s private email address (if selected), and a red Archived banner appears in the top-right corner of the employee form. The chatter logs the Departure Date and Departure Reason, and if an access link was emailed.

Nota

While attempting to send the HR documents access link, an Invalid Operation pop-up window may appear, displaying the following error message:

Employee’s related user and private email must be set to use «Send Access Link» function: (Employee Name)

If this error appears, click Close to close the pop-up window, then tick the Send Access Link checkbox to deselect it on the Employee Termination pop-up window.

Click Apply to archive the employee and close the selected activities on the Employee Termination pop-up window, returning to the employee form.

Once the employee form, ensure the following fields are populated:

  * Private Information tab: Ensure an email address is entered in the Email field.

  * HR Settings tab: Ensure a Related User is selected in the corresponding field.




After the necessary information is entered, resend the HR documents access link

### Send HR documents access link¶

If the access link was not sent when first archiving the employee on the _Employee Termination_ form, it can be sent after the employee is archived at any point.

After an employee is archived, they are no longer visible on the main **Employees** app dashboard. To view the archived employees, navigate to the Employees app dashboard, and click the __(down arrow) in the search bar to reveal a drop-down menu. Select Archived, towards the bottom of the __ Filters column, then click away from the drop-down window to close it.

Now, only archived employees appear on the dashboard. Click on the desired employee to open their employee form. On this form, click the __(gear) icon in the top-left corner, then click Send HR Documents Access Link from the resulting drop-down menu. The chatter logs that the link was sent.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/employees/offboarding.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention_report.html "Employee retention report") |
  * [precedente](equipment.html "Attrezzatura") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Procedura di uscita


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record