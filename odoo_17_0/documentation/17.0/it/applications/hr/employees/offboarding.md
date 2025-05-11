# Procedura di uscita — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention_report.html "Employee retention report") |
  * [precedente](certifications.html "Certificazioni") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Procedura di uscita



# Procedura di uscita¶

When an employee leaves the company, it is important to ensure their employee record is updated to reflect their departure, log the reason why, close any open activities associated with the employee, and provide them with any important documents.

## Archive an employee¶

In Odoo, when an employee leaves the company they must be _archived_. To archive an employee, first navigate to the Employees app. From here, locate the employee who is leaving the company, and click on their employee card.

The employee form loads, displaying all their information. Click the __(gear) icon in the top-left corner, and a drop-down menu appears. Click __ Archive, and an Employee Termination pop-up window appears.

Fill out the following fields on the form:

  * Departure Reason: Select a reason the employee is leaving from the drop-down menu. The default options are:

    * Fired: Select this option when an employee is being let go, and the company has given notice.

    * Resigned: Select this option when the employee no longer wishes to be employed, and the employee has given notice.

    * Retired: Select this option when the employee is retiring.

    * Became Freelance: Select this option when the employee is no longer working for the company, but is becoming a freelance worker instead.

  * Contract End Date: Using the calendar selector, select the last day the employee is working for the company.

  * Detailed Reason: Enter a short description for the employee’s departure in this field.

  * Close Activities: Tick the checkbox next to each type of activity to close or delete any open activities associated with it. It is recommended to tick **all** checkboxes that are applicable. The available options are:

    * Appraisals: cancels all appraisals scheduled after the contract end date.

    * Contract: applies an end date for the current contract.

    * Company Car: removes the employee as the driver for their current company car, and [assigns the next driver](../fleet/new_vehicle.html#fleet-new-vehicle-new-driver), if applicable.

    * Time Off: cancels any time off requests after the contract end date.

    * Allocations: removes the employee from any accrual plans they are on.

  * HR Info: Tick the checkbox next to Send Access Link to send a download link to the employee’s personal email address, containing all their personal HR files.

  * Private Email: This field appears if the HR Info checkbox is ticked. Enter the private email address for the employee.




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

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/employees/offboarding.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention_report.html "Employee retention report") |
  * [precedente](certifications.html "Certificazioni") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
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