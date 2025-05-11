# Registra spese — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reimburse.html "Reimburse employees") |
  * [precedente](expense_reports.html "Expense reports") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Registra spese



# Registra spese¶

Once an expense report is [approved](approve_expenses.html), the next step is to post the expense report to the proper accounting journal.

Importante

To post expense reports to an accounting journal, the user **must** have the following [access rights](../../general/users/access_rights.html):

  * Accounting: _Accountant_ or _Adviser_

  * Expenses: _Manager_




Only expense reports with an _Approved_ status can post the expenses to a journal. To view all expense reports, navigate to Expenses app ‣ Expense Reports. Next, to view **only** approved expense reports that need to be posted, adjust the filters on the left side, so only the Approved checkbox is ticked.

Nota

The default All Reports dashboard displays all expense reports, except reports with a status of Refused.

Expense reports can be posted to accounting journals in two ways: individually or in bulk.

## Post individual reports¶

To post an individual report, navigate to Expenses app ‣ Expense Reports, and click on an individual report with a Status of Approved, to view the report form. In this view, several options are presented: Post Journal Entries, Report In Next Payslip, Refuse, or Reset to Draft.

Click Post Journal Entries to post the report.

The accounting journal the expenses are posted to is listed in the Journal field of the expense report.

After posting the expenses to an accounting journal, a Journal Entry smart button appears at the top of the screen. Click the Journal Entry smart button, and the details for the journal entry appear, with a status of Posted.

## Post multiple reports¶

To post multiple expense reports at once, navigate to Expenses app ‣ Expense Reports to view a list of expense reports. Next, select the reports to approve by ticking the checkbox next to each report being approved.

Nota

Only expense reports with a status of Approved are able to post the expenses to an accounting journal. If an expense report is selected that **cannot** be posted, such as an unapproved report, or the report has already been posted to a journal, the Post Entries button is **not** visible.

Suggerimento

To select **only** approved expense reports, adjust the filters on the left side, so that only the Approved checkbox is ticked. Next, tick the checkbox next to the Employee column title to select **all** the Approved reports in the list at once.

Next, click the Post Entries button.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses/post_expenses.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reimburse.html "Reimburse employees") |
  * [precedente](expense_reports.html "Expense reports") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Registra spese


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
  *[API]: application programming interface
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