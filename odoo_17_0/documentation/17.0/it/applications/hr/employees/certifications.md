# Certificazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](offboarding.html "Procedura di uscita") |
  * [precedente](departments.html "Reparti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Certificazioni



# Certificazioni¶

When jobs require specific knowledge, it is necessary to track employee certifications to ensure the necessary knowledge and certifications are in place.

Certifications include classes, tests, professional seminars, and more. There are no restrictions in terms of what type of certification records can be added in Odoo.

Importante

To access the _Employee Certifications_ report, the **Surveys** app **must** be installed.

## View certifications¶

To view a full list of all employee certifications, navigate to Employees app ‣ Reporting ‣ Certifications.

All certifications appear in a list view, grouped by employee. Each certification entry displays the following:

  * Employee: the employee’s name, along with their avatar image.

  * Name: the title of the certification.

  * Validity Start: when the employee received the certification.

  * Validity End: when the certification expires.

  * Certification: the corresponding course in the **Surveys** app that was completed by the employee, if applicable.




The entries are also color-coded. Current certifications that are still valid appear in black, expired certifications appear in red, and certifications that are going to expire within the next 90 days appear in orange.

Importante

**Only** certification records with the _Display Type_ set to _Certification_ on their certification form appear on the Employee Certifications report. All other certifications appear in the resume section of the [employee form](new_employee.html).

### View certifications by expiration status¶

When managing a large number of employees with a variety of certifications, it can be difficult to determine which employees need to keep necessary certifications current in the default list view. In this scenario, it is beneficial to view the certifications by expiration status.

To do so, navigate to Employees app ‣ Reporting ‣ Certifications. Next, click the __(down arrow) in the search bar, then click Add Custom Group, revealing a drop-down menu. Click Expiration Status, then click away from the drop-down menu to close it.

After doing so, all the certifications are organized by status, starting with Expired certifications, then certifications that are Expiring soon (within the next 90 days), and lastly, certifications that are still Valid.

This view provides an easy way to see which employees have certifications that are going to expire soon, to determine which employees need to take action to keep their certifications current.

## Log a certification¶

To log a certification for an employee, navigate to Employees app ‣ Reporting ‣ Certifications. Click New, and a blank certification form loads. Enter the following information on the form:

  * Title: Enter a short description for the certification in this field.

  * Employee: Using the drop-down menu, select the employee who received the certification.

  * Type: Using the drop-down menu, select the type of certification received. This field determines where on the employee’s resume the certification appears. To create a new Type, enter the type in the field, then click Create «type».

The default options are:

    * Experience: Select this option to have the certification appear in the _Experience_ section of the _Resume_ tab on the [employee form](new_employee.html).

    * Education: Select this option to have the certification appear in the _Education_ section of the _Resume_ tab on the [employee form](new_employee.html).

    * Internal Certification: Select this option to have the certification appear in the _Internal Certification_ section of the _Resume_ tab on the [employee form](new_employee.html).

    * Completed Internal Training: Select this option to have the certification appear in _Completed Internal Training_ section of the _Resume_ tab on the [employee form](new_employee.html).

  * Display Type: Select the visibility of the certification in this field. The default options are:

    * Classic: Select this option to have the certification appear in the _Resume_ section of the employee form, and **not** appear on the _Employee Certifications_ report.

    * Course: Select this option to have the certification appear in the _Resume_ section of the employee form, and **not** appear on the _Employee Certifications_ report. Once this option is selected, a Course field appears beneath the Display Type field. Using the drop-down menu, select the course the employee took. The course is created in the **Surveys** app.

    * Certification: Select this option to have the certification appear in the _Resume_ section of the employee form, **and** appear on the _Employee Certifications_ report. Once this is selected, a Certification field appears beneath the Display Type field. Using the drop-down menu, select the certification the employee took.

  * Description: Enter a description for the certification in this field.

  * Duration: Click into the first field, and a calendar pop-over window appears. Click on the start and end dates for the certification validity period. When the correct dates are selected, click __ Apply, and both fields are populated.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/employees/certifications.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](offboarding.html "Procedura di uscita") |
  * [precedente](departments.html "Reparti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Certificazioni


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