# Inserimento lavorativo — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](departments.html "Reparti") |
  * [precedente](new_employee.html "Nuovi dipendenti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Inserimento lavorativo



# Inserimento lavorativo¶

When a new employee is hired, it is important to have an onboarding procedure that can be followed. This ensures that information, equipment, and training are provided to the employee and any other necessary steps for the business are assigned to the correct individuals.

Proper onboarding ensures that new employees are given all the information and tools needed to be successful in their roles and have a smooth transition to their new job.

## View onboarding plan¶

Before onboarding can begin, it is recommended to check the default onboarding plan that comes preconfigured with the **Employees** app. To view the current default plan, navigate to Employees app ‣ Configuration ‣ Activity Plan. Click Onboarding to view the detailed onboarding plan form.

The plan form displays the following information:

  * Plan Name: the specific name for the onboarding plan.

  * Model: specifies where this plan can be used. In this case, in the **Employees** app.

  * Department: if left blank (the default setting) this plan is available for all departments. Limit the use of the plan to a specific department by selecting the department using the drop-down menu.

  * Activities To Create: this tab lists all the onboarding steps. Each row displays:

    * Activity Type: the specific activity for the step. The default options are Email, Call, Meeting, To-Do, or Upload Document. If the **Sign** app is installed, a Request Signature option is available.

    * Summary: a one line description of the step.

    * Assignment: chooses who completes the activity, relative to the new hire:

      * Ask at launch: choose the user in the Assigned To field when launching the onboarding plan.

      * Default user: choose a user who always handles this activity. Defined in the Assigned to field.

      * Manager: assigns the employee’s manager as defined on the employee record.

      * Coach: assigns the employee’s coach as defined on the employee record.

      * Employee: the new hire completes the activity.

      * Fleet Manager: assigns the designated **Fleet** app manager. This option is only available if the **Fleet** app is installed.

    * Assigned to: this field remains blank, unless Default user is selected for the Assignment field. If Default user is selected, this field is populated with the selected user.

    * Document to sign: the corresponding document requiring a signature.

    * Interval: the time when the activity is active.

    * Unit: the set time interval, either days, weeks, or months.

    * Trigger: how scheduling is determined for the activity. Options are either Before Plan Date or After Plan Date.

Example

A laptop must be set up and registered to a new employee the day before they start work. The person who performs this step should always be the IT Manager, Abby Jones.

To configure this activity with these parameters, the Activity Type is set to To-Do, with a summary of Assign Laptop. The Assignment field is set to Default user, and the Assigned to field is set to Abby Jones. The Interval is 1, and the Unit is set to days. The Trigger is Before Plan Date.




### Onboarding plan steps¶

The default Onboarding plan includes three default steps. All steps are To-Do activities, and are scheduled for the day the onboarding plan is launched (0 days Before Plan Date).

  * Setup IT Materials: the manager must gather and configure all IT materials.

  * Plan Training: the manager must plan the training for the new employee.

  * Training: the new employee must complete the training planned by the manager.




## Modify onboarding plan¶

A single onboarding plan works only if the flow works for the entire company.

Nota

If the onboarding plan is universal, add to or modify the default onboarding plan. If department-specific onboarding plans are needed, create a new onboarding plan.

To modify the default plan, first navigate to Employees app ‣ Configuration ‣ Activity Plan, then click on Onboarding.

To modify a step, click on it. In the Open: Activities pop-up window, make any desired modifications to the step, then click Save.

To add a new step, click Add a line at the bottom of the listed activities in the Activities To Create tab, and a blank Create Activities pop-up window appears. Enter all the information in the pop-up window, then click Save & Close if there are no other steps to add, or click Save & New if more steps are needed.

## Create onboarding plan¶

Some companies require different onboarding plans, when there are department-specific onboarding procedures that do not apply to the whole company. For these cases, a new department-specific onboarding plan must be created.

To create a new onboarding plan, navigate to the desired plan and configure all the desired steps.

Example

A company specializing in the manufacturing and selling of outdoor metal furniture may have a large factory that produces the products, and a separate sales office. This company may have two separate onboarding plans, one for factory workers, and one for office workers.

The onboarding plan for the factory workers is set for the Manufacturing department, and includes specialized tasks relating to factory jobs. These include gathering the new employees uniform and safety gear, assigning a safety course, emailing their team about the new hire, going over benefits, and more.

## Launch onboarding plan¶

After an employee has been hired and their employee profile [is created](../recruitment/offer_job_positions.html#recruitment-new-employee), navigate to the desired employee’s profile by clicking on their Kanban card on the **Employees** app dashboard, then click the Launch Plan button on their employee profile, and a blank Launch Plan pop-up window loads.

In the Plan field, choose the desired onboarding plan. Then, using the calendar selector, set a date in the Plan Date field. This is typically the employee’s first day, but any date can be selected.

The right side of the Launch Plan pop-up window displays all the steps in the selected plan, grouped by what was selected in the Assignment fields on the plan form.

Once the Plan and Plan Date fields are configured, click the Schedule button, and Odoo schedules everything in the plan, according to their respective due dates.

All scheduled activities appear in the both chatter of the employee profile, and in the chatter of the user’s with assignments relating to the plan.

Nota

If any activity assignments were configured to Ask at launch, an Assigned to field appears on the Launch Plan pop-up window. Using the drop-down menu, select the user responsible for all the unassigned activities.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/employees/onboarding.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](departments.html "Reparti") |
  * [precedente](new_employee.html "Nuovi dipendenti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Inserimento lavorativo


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