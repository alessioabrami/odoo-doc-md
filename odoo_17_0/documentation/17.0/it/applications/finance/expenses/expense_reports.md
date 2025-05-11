# Expense reports — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](post_expenses.html "Registra spese") |
  * [precedente](log_expenses.html "Log expenses") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Expense reports



# Expense reports¶

When expenses are ready to submit (such as, at the end of a business trip, or once a month), an _expense report_ needs to be created. Open the main Expenses app dashboard, which displays the My Expenses dashboard, by default. Alternatively, navigate to Expenses app ‣ My Expenses ‣ My Expenses.

Expenses are color-coded by status. Any expense with a status of To Report (expenses that still need to be added to an expense report) is shown in blue text. All other statuses (To Submit, Submitted, and Approved) the text appears in black.

## Create expense reports¶

First, select each desired expense to be added to the report on the My Expenses dashboard, by ticking the checkbox next to each entry, or quickly select all the expenses in the list by ticking the checkbox next to the Expense Date column title, if needed.

Another way to quickly add all expenses that are not on a expense report, is to click the Create Report button, _without_ selecting any expenses, and Odoo automatically selects all expenses with a status of To Submit that are not already on a report.

Nota

Any expense can be selected from the My Expenses list, except for expenses with a status of Approved.

The Create Report button is visible as long as there is a minimum of one expense on the list with a status of either To Report or To Submit.

When the Create Report button is clicked, all expenses with a status of To Submit that are _not_ currently on another expense report appears in the newly-created expense report.

If all expenses on the My Expenses report are already associated with another expense report, an Invalid Operation pop-up window appears, stating You have no expenses to report.

Once the expenses have been selected, click the Create Report button. The new report appears with all the expenses listed in the Expense tab. If there is a receipt attached to an individual expense, a __(paperclip) icon appears between the Customer to Reinvoice and Analytic Distribution columns.

When the report is created, the date range for the expenses appears in the Expense Report Summary field, by default. It is recommended to edit this field with a short summary for each report to help keep expenses organized. Enter a description for the expense report, such as `Client Trip NYC`, or `Office Supplies for Presentation`, in the Expense Report Summary field.

The Employee, Paid By, and Company fields autopoulate with the information listed on the individual expenses.

Next, select a Manager from the drop-down menu to assign a manager to review the report. If needed, update the Journal field, using the drop-down menu.

If some expenses are missing from the report, they can still be added from this report form. To do so, click Add a line at the bottom of the Expense tab.

An Add: Expense Lines pop-up window appears, displaying all the available expenses (with a To Submit status) that can be added to the report.

If a new expense needs to be added that does **not** appear on the list, click New to [create a new expense](log_expenses.html) and add it to the report.

Tick the checkbox next to each expense being added, then click Select.

Doing so removes the pop-up window, and the items now appear on the report.

Nota

Expense reports can be created in one of three places:

  1. Navigate to the main Expenses app dashboard (also accessible, via Expenses app ‣ My Expenses ‣ My Expenses)

  2. Navigate to Expenses app ‣ My Expenses ‣ My Reports

  3. Navigate to Expenses app ‣ Expense Reports




In any of these views, click New to create a new expense report.

## Submit expense reports¶

When an expense report is completed, the next step is to submit the report to a manager for approval. To view all expense reports, navigate to Expenses app ‣ My Expenses ‣ My Reports. Open the specific report from the list of expense reports.

Nota

Reports must be individually submitted, and **cannot** be submitted in batches.

If the list is large, grouping the results by status may be helpful, since only reports with a To Submit status need to be submitted; reports with an Approved or Submitted status do not.

The To Submit expenses are identifiable by the To Submit status, and by the blue text, while all other expense text appears in black.

Nota

The status of each report is shown in the Status column. If the Status column is not visible, click the __(additional options) icon at the end of the row, and tick the checkbox beside Status from the resulting drop-down menu.

Click on a report to open it, then click Submit To Manager. After submitting a report, the next step is to wait for the manager to approve it.

Importante

[Approving](approve_expenses.html) expenses, [posting](post_expenses.html) expenses, and [reimbursing](reimburse.html) expenses are **only** for users with the appropriate [access rights documentation](../../general/users.html).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses/expense_reports.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](post_expenses.html "Registra spese") |
  * [precedente](log_expenses.html "Log expenses") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Expense reports


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
  *[SOs]: Sales Order