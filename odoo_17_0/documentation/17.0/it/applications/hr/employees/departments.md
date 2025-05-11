# Reparti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](certifications.html "Certificazioni") |
  * [precedente](new_employee.html "Nuovi dipendenti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Reparti



# Reparti¶

All employees in the _Employees_ app fall under specific departments within a company.

## Create new departments¶

To make a new department, navigate to Employees app ‣ Departments, then click New in the top-left to reveal a blank department form. Fill out the following information on the department form:

  * Department Name: enter a name for the department.

  * Manager: using the drop-down menu, select the department manager.

  * Parent Department: if the new department is housed within another department (has a parent department), select the parent department using the drop-down menu.

  * Custom Appraisal Templates: if employees in this department require a specific appraisal form that is different from the default appraisal form, tick the checkbox. If this option is activated, an Appraisal Templates tab appears below the form. This field **only** appears if the _Appraisals_ app is installed.

  * Company: using the drop-down menu, select the company the department is part of.

  * Appraisal Survey: using the drop-down menu, select the default survey to use for the department when requesting feedback from employees. This field **only** appears if the _Appraisals_ app is installed, **and** the _360 Feedback_ option is enabled in the settings.

  * Color: select a color for the department. Click the default white color box to display all the color options. Click on a color to select it.

  * Appraisal Templates tab: this tab **only** appears if the Custom Appraisal Templates options is activated on the form. Make any desired edits to the appraisal form. The appraisal form is used for appraisals for all employees within this department.




After the form is completed, click the __(cloud upload) icon to manually save the changes. When saved, a Department Organization chart appears in the top-right of the department card.

Nota

The form auto-saves while data is entered, however the Department Organization chart does **not** appear until the form is manually saved. If the form is not saved, the Department Organization chart is visible upon opening the department card from the Departments dashboard.

Vedi anche

Refer to the [Valutazioni](../appraisals.html) documentation for more information.

## Departments dashboard¶

To view the currently configured departments, navigate to Employees app ‣ Departments. All departments appear in a Kanban view, by default, and are listed in alphabetical order.

### Vista kanban¶

Each department has its own Kanban card on the main Departments __(Kanban) dashboard view, that can display the following information:

  * Department name: the name of the department.

  * Company: the company the department is part of.

  * Employees: the number of employees within the department.

  * Appraisals: the number of appraisals scheduled for employees in the department.

  * Time Off Requests: the number of unapproved time off requests for employees in the department [awaiting approval](../time_off/management.html#time-off-manage-time-off) . This **only** appears if there are requests to approve.

  * Allocation Requests: the number of unapproved allocation requests for employees in the department [awaiting approval](../time_off/management.html#time-off-manage-allocations). This **only** appears if there are requests to approve.

  * New Applicants: the number of [new applicants](../recruitment/recruitment-flow.html#recruitment-new) for a position in this department. This **only** appears if there are new applicants.

  * Expense Reports: the number of employees in the department with [open expense reports to approve](../../finance/expenses/approve_expenses.html). This **only** appears if there are any expense reports waiting for approval.

  * Absence: the number of absences for the current day.

  * Color bar: the selected color for the department appears as a vertical bar on the left side of the department card.




Nota

Click on an alert in a department card, such as Time Off Requests, to reveal a list view of the requests to approve. This list includes **all** open requests to approve, not just from the specific department.

The default view for the Departments dashboard is a Kanban view. It is possible to view the departments in two other forms: a list view and a hierarchy view.

### Vista elenco¶

To view the departments in a list view, click the __(list) icon in the top-right corner. The departments appear in a list view, which displays the Department Name, Company, Manager, Employees, Parent Department, and Color for each department.

The departments are sorted alphabetically by Department Name, by default.

Suggerimento

When in list view, departments can be managed in batch by selecting one or multiple record’s checkbox, then select the __ Actions button to reveal a drop-down menu of actions.

### Hierarchy view¶

To view the departments in a hierarchy view, click the __(hierarchy) icon in the top-right corner. The departments appear in an organizational chart format, with the highest-level department at the top (typically Management), and all other departments beneath it. All child departments of the first-level child departments are folded.

Each department card displays the Department Name, the Manager (and their profile image), the Number of Employees in the department, and the ability to expand the department (Unfold) if there are child departments beneath it.

Click the Unfold button on a department card to expand it. Once expanded, the Unfold button changes to a Fold button. To collapse the department, click the Fold button. Only **one** department _per row_ can be unfolded at a time.

Click anywhere on a department card to open the department form. Click the (#) Employees smart button to view a list of all the employees in that department, including all employees in the child departments beneath it, organized by individual department.

Example

> In the hierarchy view, if the (2) Employees button on the Management card is clicked (the highest-level department card), **all** employees appear in a list view, grouped by department. This is because **all** departments are children of the Management department.
> 
> If the (3) Employees button in the Sales department card is clicked, the employees from the Sales department, as well as its two child departments (East Coast Territory and West Coat Territory), appear in the list.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/employees/departments.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](certifications.html "Certificazioni") |
  * [precedente](new_employee.html "Nuovi dipendenti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
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
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price