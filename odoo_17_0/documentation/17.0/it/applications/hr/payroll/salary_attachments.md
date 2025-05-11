# Salary attachments — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payslips.html "Buste paga") |
  * [precedente](work_entries.html "Work entries") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Salary attachments



# Salary attachments¶

Salary attachments are portions of earnings taken directly out of a payslip for a specific purpose, whether voluntary or required.

When the deduction is voluntary, they are typically considered _deductions_. When the deduction is court-ordered, or involuntary, it is sometimes referred to as a _wage garnishment_. In Odoo, these are all universally called, _salary attachments_.

## Salary attachment types¶

To view the currently configured salary attachment types, navigate to Payroll app ‣ Configuration ‣ Salary Attachment Types. The default salary attachment types are: Attachment of Salary, Assignment of Salary, and Child Support.

Each salary attachment type displays the Name of the attachment type, the Code used when calculating payslips, a checkbox to indicate if there is No End Date, and whether it is Country specific (or universal).

### Create new salary attachment types¶

Pericolo

Upon installation of the **Payroll** application, the pre-configured default salary attachment types are linked to a variety of rules that are linked to various salary structures, as well as the installed [localization package](../../finance/fiscal_localizations.html#fiscal-localizations-packages).

It is **not** recommended to alter or modify **any** of the preconfigured salary attachment types, especially if they have been previously used on payslips in the database. Doing so may affect various salary rules, and can prevent the creation of payslips.

A new salary attachment type _can_ be created, but this should only be done when absolutely necessary. All salary attachments can be associated with one of the three default salary attachment types.

To make a new type of salary attachment, click the New button, and a blank Salary Attachment Types form loads. Enter the Name for the new salary attachment type in the corresponding field. Next, enter the Code used in the salary rules to compute payslips. Last, tick the No End Date checkbox if this salary attachment never expires.

If in a multi-company database, with locations in multiple countries, a Country field also appears on the Salary Attachment Types form. Select the country the attachment applies to, or leave blank if it is universal.

## Create a salary attachment¶

All salary attachments must be configured separately for each employee, for each type of salary attachment. To view the currently configured salary attachments, navigate to Payroll app ‣ Contracts ‣ Salary Attachments.

All salary attachments appear in a default list view, and displays the name of the Employees, Description, the salary attachment Type, the Monthly Amount, Start Date, and current Status.

To create a new salary attachment, click the New button in the top-left corner, and a blank Salary Attachment form loads. Enter the following information on the form:

  * Employees: Using the drop-down menu, select the desired employees. Multiple employees can be listed in this field.

  * Description: Enter a short description of the salary attachment.

  * Type: Using the drop-down menu, select the specific salary attachment type.

  * Start Date: Using the calendar selector, select the date the salary attachment goes into effect.

  * Estimated End Date: This field is **not** modifiable, and **only** appears after the Monthly Amount field is populated. This field is the estimated date when the salary attachment will be completed. Today’s date populates the field by default. Then, when the Total Amount field is populated, this date is updated.

  * Document: If any documentation is needed, such as a court order, click the Upload your file button, and a file explorer window loads. Select the desired document to attach it to the record. Only **one** document can be attached to a salary attachment.

  * Monthly Amount: Enter the amount taken out of each paycheck every month in this field.

  * Total Amount: This field **only** appears if the salary attachment type has no end date (the No End Date option is **not** ticked.)




Since the salary attachment form auto saves as the fields are populated, after making a salary attachment for an individual employee, there is no further action required.

If creating salary attachments for multiple employees on a single salary attachment form, after the form is filled out, click the Create Individual Attachments button. This creates separate salary attachments for each of the employees listed in the Employees field.

After the separate salary attachments have been created, the screen returns to the Salary Attachment dashboard, but with a Description filter, populated with the description filled in on the salary attachment form. All the salary attachments have a status of Running, since they are currently active. Clear the filter in the search box to view the default Salary Attachment dashboard in its entirety.

## Manage salary attachments¶

Salary attachments can have one of three statuses: _Running_ , _Completed_ , or _Canceled_. To view the current status of all salary attachments, navigate to Payroll app ‣ Contracts ‣ Salary Attachments.

All salary attachments appear in the order they were configured. To view the salary attachments by a particular metric, such as the Status, or Type, click on the column title to sort by that specific column.

### Completed salary attachments¶

When a salary attachment is created, it has a status of Running. Once the salary attachment is finished (the _Total Amount_ entered on the salary attachment form has been paid in full), the status automatically changes to _Completed_ , and the employee no longer has the money taken out of future paychecks.

If a salary attachment has been fulfilled, but has not automatically changed to _Completed_ , the record can be manually updated. To change the status, open the _Salary Attachment_ dashboard by navigating to Payroll app ‣ Contracts ‣ Salary Attachments.

Click on the record to update, and the detailed Salary Attachment form loads. On the individual Salary Attachment record, click the Mark as Completed button in the upper-left corner, and the status changes to Completed.

Example

The following is an example of when a payroll manager may need to manually change a salary attachment from Active to Cancelled.

Rose Smith has a salary attachment for a lawsuit settlement, where she is required to pay $3,000.00. A salary attachment is created that takes $250.00 a month out of Rose’s paycheck, to go towards this settlement payment.

After six months, Rose has paid $1,500.00 from her salary. She received a tax refund, and uses the money to pay off the remainder of the lawsuit settlement. After sending the relevant documentation to the payroll manager, showing the settlement has been paid in full, the payroll manager manually changes the status of her salary attachment to Completed.

### Cancel salary attachments¶

Any salary attachment can be cancelled at any time. To cancel a salary attachment, click on the individual attachment record from the main Salary Attachment dashboard to open the record. From the Salary Attachment record, click the Cancel button to cancel the salary attachment, and stop having the designated money taken out of future paychecks.

Vedi anche

[Salary attachment report](salary_attachment.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/payroll/salary_attachments.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payslips.html "Buste paga") |
  * [precedente](work_entries.html "Work entries") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Salary attachments


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