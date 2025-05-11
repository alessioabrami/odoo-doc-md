# Approve expenses — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](log_expenses.html "Log expenses") |
  * [precedente](../expenses.html "Costi") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Approve expenses



# Approve expenses¶

In Odoo, not just anyone can approve expense reports, only users with the necessary rights (or permissions) can. This means that a user **must** have at least _Team Approver_ rights for the _Expenses_ app. Employees with the necessary rights can review expense reports, approve or reject them, and provide feedback thanks to the integrated communication tool.

Please refer to the [access rights documentation](../../general/users.html) to learn more about managing users and their access rights.

## View expense reports¶

Users who are able to approve expense reports, typically managers, can easily view all expense reports they have access rights to. Go to Expenses app ‣ Expense Reports, to view the All Reports dashboard.

A list of all expense reports with a status of either To Submit, Submitted, Approved, Posted, or Done appears. Expense reports with a status of Refused are hidden, by default.

## Approve expense reports¶

Expense reports can be approved in two ways: individually or in bulk.

Importante

Only reports with a status of Submitted can be approved.

It is recommended to display only Submitted reports by ticking the checkbox beside the Submitted filter, in the left column, under the Status section.

If a report is **not** able to be approved, the Approve Report button **does not** appear on the All Reports page.

### Approve individual reports¶

To approve an individual report, navigate to Expenses app ‣ Expense Reports, and click on an individual report to view the report form.

From here, several options are presented: Approve, Refuse, and Reset to draft.

Click Approve to approve the report.

### Approve multiple reports¶

To approve multiple expense reports at once, first navigate to Expenses app ‣ Expense Reports to view a list of expense reports. Next, select the reports to approve by ticking the checkbox next to each report being approved, or tick the checkbox next to the Employee column title to select all the reports in the list.

Next, click the Approve Report button.

Suggerimento

It is possible for team managers to view all the expense reports for just their team members.

To do so, while on the All Reports page, click the __(down arrow) to the right of the search bar, then click My Team in the __ Filters section.

This presents all the reports for only the manager’s team.

## Refuse expense reports¶

Expense reports can **only** be refused on the individual expense report, and **not** from the All Reports dashboard. To open an individual expense report, navigate to Expenses app ‣ Expense Reports, then click on an individual expense report to view the report form.

If more information is needed, such as a missing receipt, communicate any necessary information requests in the _chatter_ of the report form. On the individual expense report, click Send message to open a message text box.

Type in a message, tagging the proper people, and post it to the _chatter_ by clicking Send. The message is posted in the chatter, and the tagged people are notified, via email.

Nota

The only people that can be tagged in a message are _followers_ of the specific report. To see who is a follower, click the __(user) icon to display the followers of the expense report.

To refuse an expense report, click Refuse, and a Refuse Expense pop-up window appears. Enter a brief explanation for the refusal beneath the REASON TO REFUSE EXPENSE field, then click Refuse.

Once the expense report is refused, the status changes to Refused, and the only button that appears in the top-left is Reset to Draft.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses/approve_expenses.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](log_expenses.html "Log expenses") |
  * [precedente](../expenses.html "Costi") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Approve expenses


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
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
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[POS]: Point Of Sale
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases