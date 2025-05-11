# Reparti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](certifications.html "Certificazioni") |
  * [precedente](onboarding.html "Inserimento lavorativo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Reparti



# Reparti¶

All employees in the **Employees** app fall under specific departments within a company.

## Create new departments¶

To make a new department, navigate to Employees app ‣ Departments, then click the New button in the top-left corner to reveal a blank department form. Fill out the following information on the department form:

  * Department Name: enter a name for the department.

  * Manager: using the drop-down menu, select the department manager.

  * Parent Department: if the new department is housed within another department (has a parent department), select the parent department using the drop-down menu.

  * Company: using the drop-down menu, select the company the department is part of. This field only appears in a multi-company database.

  * Color: select a color for the department. Click the colored box to display all the color options. Click on a color to select it.

  * Appraisal Templates: using the drop-down menu, select the appraisal form to be used for all employee appraisals within this department. If a new appraisal is desired, enter the name for the appraisal, then click Create and edit… to modify the new appraisal form. This field **only** appears if the **Appraisals** app is installed.

  * Appraisal Survey: using the drop-down menu, select the default survey to use for the department when requesting feedback from employees within the department. The default options are Employee Opinion Form, 360 Feedback, and Employee Appraisal Form. This field **only** appears if the **Appraisals** app is installed, _and_ the _360 Feedback_ option is enabled in the settings.




After the form is completed, click the __(cloud upload) icon to manually save the changes. When saved, a DEPARTMENT ORGANIZATION chart appears in the top-right of the department card, illustrating where the department lies in the organization.

Nota

The form auto-saves while data is entered, however the Department Organization chart does **not** appear until the form is manually saved. If the form is not saved, the Department Organization chart is visible upon opening the department card from the Departments dashboard.

Vedi anche

[Valutazioni](../appraisals.html)

## Departments dashboard¶

To view the currently configured departments, navigate to Employees app ‣ Departments. All departments appear in a Kanban view, and are listed in alphabetical order.

The default view for the Departments dashboard is a Kanban view. It is possible to view the departments in two other forms: a list view and a hierarchy view.

### Vista kanban¶

Each department has its own Kanban card on the main Departments dashboard. Each department card displays the following information, if available:

  * Name: the name of the department.

  * Manager: the name and image of the department manager.

  * Company: the company the department is part of, including the location icon.

  * Employees: the number of employees within the department.

  * Appraisals: the number of appraisals scheduled for employees in the department.

  * Time Off Requests: the number of unapproved time off requests for employees in the department [awaiting approval](../time_off/management.html#time-off-manage-time-off) . This **only** appears if there are requests to approve.

  * Allocation Requests: the number of unapproved allocation requests for employees in the department [awaiting approval](../time_off/management.html#time-off-manage-allocations). This **only** appears if there are requests to approve.

  * New Applicants: the number of [new applicants](../recruitment/recruitment-flow.html#recruitment-new) for a position within the department. This **only** appears if there are new applicants.

  * Expense Reports: the number of employees in the department with [open expense reports to approve](../../finance/expenses/approve_expenses.html). This **only** appears if there are any expense reports waiting for approval.

  * Absence: the number of employees with approved time off for the current day.

  * Color bar: the selected color for the department appears as a vertical bar on the left side of the department card.




Nota

Click on an alert in a department card, such as Time Off Requests, to reveal a list view of the requests to approve for that department

### Vista elenco¶

To view the departments in a list view, click the __(list) icon in the top-right corner. The departments appear in a list view, which displays the Department Name, Company, Manager, Employees, Parent Department, and Color for each department.

The departments are sorted alphabetically by Department Name, by default.

### Hierarchy view¶

To view the departments in a hierarchy view, click the __(Hierarchy) icon in the top-right corner. The departments appear in an organizational chart format, with the highest-level department at the top (typically `Executive Management`), and all other departments beneath it. All child departments of the first-level child departments are folded.

Each department card displays the Department Name, the Manager (and their profile image), the Number of Employees in the department, and the number of any child departments.

Click the Unfold button on a department card to expand it. Once expanded, the Unfold button changes to a Fold button. To collapse the department, click the Fold button. Only **one** department _per row_ can be unfolded at a time.

Click anywhere on a department card to open the department form. Click the (#) Employees smart button to view a list of all the employees in that department.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/employees/departments.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](certifications.html "Certificazioni") |
  * [precedente](onboarding.html "Inserimento lavorativo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Reparti


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