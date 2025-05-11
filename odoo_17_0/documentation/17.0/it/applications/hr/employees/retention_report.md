# Employee retention report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../appraisals.html "Valutazioni") |
  * [precedente](offboarding.html "Procedura di uscita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Employee retention report



# Employee retention report¶

It is possible to determine the retention rate for a company by modifying an existing report.

First, navigate to Employees app ‣ Reporting ‣ Contracts to open the Employee Analysis report. This report shows the number of all employees for the Last 365 Days, in a default __ Line Chart.

Next, click the Measures __button in the upper-left corner, revealing a drop-down menu. Click # Departure Employee in the list, then click away from the drop-down menu to close it. Now, the report shows all the employees who were archived for the Last 365 Days.

To view this information in an easier format, click the __(Pivot) icon in the upper-right corner, and the data is presented in a pivot table.

The various employees, organized by department, populate the rows. The columns display the following totals: the monthly Wage, the Fuel Card budget, total Annual Employee Budget (also referred to as the _annual salary_), the number of New Employees, as well as the number of Departure Employees (employees who left).

## Employee retention rate comparison report¶

It is possible to compare data only for employees who left, compared to the total current employees, between two separate time periods. This is commonly referred to as the _employee retention rate_.

To view these metrics, first open the Employee Analysis report by navigating to Employees app ‣ Reporting ‣ Contracts. Click the __(Pivot) icon in the upper-right corner to view the information in a pivot table.

Next, click the Measures __button in the upper-left corner, revealing a drop-down menu. Click # New Employees, Annual Employee Budget, Fuel Card, and Wage in the list, to deselect these metrics and hide them in the table. Then, click Count at the bottom of the list to enable that metric.

Click away from the drop-down menu to close it. Now, the report shows all the employees who left the company (# Departure Employee), as well as the total number of employees (Count), for the Last 365 Days.

To compare the data for the current year with the previous year, click the __(down arrow) in the search bar, revealing multiple filter and grouping options. Click Last 365 Days in the __ Filters column, to turn off that filter. Then, click Date, and click the current year (in this example, 2024) from the resulting drop-down menu.

Once a selection is made beneath Date in the __ Filters column, a __ Comparison column appears. Click Date: Previous Year in the new column, then click off of the drop-down menu to close it.

Nota

In Odoo, in order to access the __ Comparison column, a specific time _other than_ Last 365 Days **must** be selected. If not, the __ Comparison column is **not** visible.

Now, the pivot table displays the total number of employees who left the company (# Departure Employee), as well as the total number of employees (Count) in the columns. These are further divided by the two different years, and also displays the Variation between the two.

The rows display the departments, and lists each individual employee for each department, in the rows.

For a more concise view of this report, click __ Total above the top row of the departments and employees, to collapse the rows. Now, the table presents the total number of employees who left the company for both years, compared to the total number of employees for both years, including the difference, in a percentage.

Example

In this example, 3 employees out of 83 left in 2023, and 8 employees out of 202 left in 2024. There was a 166.67% increase in the employees who left in 2024 as compared to 2023. Additionally, there was a 143.37% increase in the total number of employees in 2024 as compared to 2023.

To view more detailed rates for each department, click __ Total in the single row, revealing a drop-down menu, and click Department. Click away from the drop-down to close it, and now the pivot table displays the total number of employees who left (# Departure Employee), the total number of employees (Count), and the Variation (in a percentage) for both 2023 and 2024, organized by department.

Example

In this example, it can be determined that the Management department had the best retention rate in 2024 as compared to 2023, with a Variation rate of -100%. Additionally, it can be determined that the Management / Research & Development department had the most turnover, with a Variation of 300%.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/employees/retention_report.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../appraisals.html "Valutazioni") |
  * [precedente](offboarding.html "Procedura di uscita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Employee retention report


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