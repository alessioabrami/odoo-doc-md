# Salary attachment report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../time_off.html "Ferie") |
  * [precedente](work_entry_analysis.html "Work entry analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Salary attachment report



# Salary attachment report¶

_Salary attachments_ in Odoo refer to a portion of an employee’s earnings that are designated for a specific purpose, both voluntary and involuntary. These can include contributions to a retirement plan, repayment of a loan, wage garnishments, or child support.

Voluntary salary attachments, such as repaying a loan, or contributing to a charity on a monthly basis, are considered _Assignments of Salary_ in Odoo. Salary attachments that are required, such as a lawsuit settlement repayment, or repaying a tax lien, are considered _Attachments of Salary_ in Odoo. Child support payments have their own category, and are simply referred to as _Child Support_ in Odoo.

To view this report, navigate to Payroll app ‣ Reporting ‣ Salary Attachment Report. The Salary Attachment Report shows all deductions or allocations per employee, organized by payslip, in a default pivot table. The default filter is the end of the current year (Payslip End Date: (year)). The employees populate the rows, while the various deductions populate the columns, organized by type of deduction, and further grouped by individual payslip.

The default report contains **all** payslips for the current year, so the report typically contains a large number of columns. This could make it difficult to view all the data at once, as the report may be very wide and require scrolling to view all the data.

To view a condensed version of salary attachments, and have all the salary attachment columns visible on one page, click the __ Total icon at the top of the report, above the various payslips.

This presents the salary attachments for the current year, and only displays three columns, Attachment of Salary, Assignment of Salary, and Child Support.

Each entry displays the total amount paid for each specific type of salary attachment, for each employee.

The report can be downloaded as an XLSX file, or [inserted into a spreadsheet](../../productivity/spreadsheet/insert.html) using the corresponding buttons at the top.

Click the Measures button to reveal the options of what data is displayed. Assignment of salary, Attachment of salary, and Child support are all selected and visible, by default, while the Count option is not.

Click an option to either show or hide that particular metric. A __(checkmark) icon indicates the data is visible.

## Compare to previous year¶

The Salary Attachment Report can be compared to the report for the previous time period or the previous year.

To view these comparisons, click the __(down arrow) icon in the search bar, then click either Payslip End Date: Previous Period or Payslip End Date: Previous Year, beneath the __ Comparison column.

The report updates and displays the current time period values, and the previous time period values, as well as the Variation between the two, in a percentage.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/payroll/salary_attachment.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../time_off.html "Ferie") |
  * [precedente](work_entry_analysis.html "Work entry analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Salary attachment report


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