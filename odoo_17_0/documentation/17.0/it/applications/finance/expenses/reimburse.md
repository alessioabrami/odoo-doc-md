# Reimburse employees — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reinvoice_expenses.html "Re-invoice expenses") |
  * [precedente](post_expenses.html "Registra spese") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Reimburse employees



# Reimburse employees¶

After an expense report is [posted to an accounting journal](post_expenses.html), the next step is to reimburse the employee. Just like approving and posting expenses, employees can be reimbursed in two ways: with cash, check, or direct deposit (individually or in bulk), or reimbursed in a payslip.

## Impostazioni¶

Reimbursements can be paid via paycheck, check, cash, or bank transfer. To set up payment options, first configure the various settings by navigating to Expenses app ‣ Configuration ‣ Settings.

To reimburse employees for expenses in their paychecks, tick the checkbox beside the Reimburse in Payslip option in the Expenses section.

Next, set how payments are made in the Accounting section. Click the drop-down menu under Payment Methods, and select the desired payment option. Default options include paying by Manual (Cash), Checks (Bank), NACHA (Bank), and others. Leaving this field blank allows for **all** available payment options to be used.

When all desired configurations are complete, click Save to activate the settings.

## Reimburse individually¶

To reimburse an individual expense report, first navigate to Expenses app ‣ Expense Reports. All expense reports are presented in a default list view. Click on the expense report being reimbursed to view the report details.

Importante

**Only** expense reports with a status of Posted can be reimbursed.

Click the Register Payment button in the top-left corner of the expense report, and a Register Payment pop-up window appears. Enter the following information in the pop-up window:

  * Journal: Select the accounting journal to post the payment to using the drop-down menu. The default options are Bank or Cash.

  * Payment Method: Select how the payment is made using the drop-down menu. If Cash is selected for the Journal, the only option available is Manual. If Bank is selected for the Journal, the default options are Manual or Checks.

  * Recipient Bank Account: Select the employee’s bank account the payment is being sent to. If the employee has a bank account on file in the [Private Information tab](../../hr/employees/new_employee.html#employees-private-info) of their employee form in the **Employees** app, that bank account populates this field, by default.

  * Amount: The total amount being reimbursed populates this field, by default. The currency, located to the right of the field, can be modified using the drop-down menu.

  * Payment Date: Enter the date the payments are issued in this field. The current date populates this field, by default.

  * Memo: The text entered in the [Expense Report Summary](expense_reports.html) field of the expense report populates this field, by default.




When the fields of the pop-up window are completed, click the Create Payment button to register the payment, and reimburse the employee.

## Reimburse in bulk¶

To reimburse multiple expense reports at once, navigate to Expenses app ‣ Expense Reports to view all expense reports in a list view. Next, adjust the STATUS filters on the left side to only present expense reports with a status of Posted.

Suggerimento

Adjusting the STATUS filters to only show Posted expense reports is not necessary, but removes the step of selecting each individual report in the list.

Tick the checkbox next to the Employee column title to select all the reports in the list. Once ticked, the number of selected expense reports appears at the top of the page ((#) Selected). Additionally, a Register Payment button also appears in the upper-left corner.

Click the Register Payment button, and a Register Payment pop-up window appears. Enter the following information in the pop-up window:

  * Journal: Select the accounting journal the payment should be posted to, using the drop-down menu. The default options are Bank or Cash.

  * Payment Method: Select how the payment is made using the drop-down menu. If Cash is selected for the Journal, the only option available is Manual. If Bank is selected for the Journal, the default options are Manual or Checks.

  * Group Payments: When multiple expense reports are selected for the same employee, this option appears. Tick the checkbox to have only one payment made, rather than issuing multiple payments to the same employee.

  * Payment Date: Enter the date the payments are issued. The current date populates this field, by default.




When the fields on the pop-up window are completed, click the Create Payments button to register the payments, and reimburse the employees.

## Report in next payslip¶

If the _Reimburse in Payslip_ option is activated on the _Settings_ page, payments can be added to their next payslip, instead of issued manually.

Importante

Reimbursing expenses on payslips can **only** be done individually, on an expense report with a status of _Approved_. Once an expense report has a status of _Posted_ , the option to reimburse in the following payslip does **not** appear.

Navigate to Expenses app ‣ Expense Reports, and click on the individual expense report being reimbursed on the following paycheck. Click the Report in Next Payslip smart button, and the expenses are added to the next payslip issued for that employee. Additionally, a message is logged in the chatter stating the expense is added to the following payslip.

The status for the expense report remains Approved. The status only changes to Posted (and then Done), when the paycheck is processed.

Vedi anche

Refer to the [Payslips](../../hr/payroll/payslips.html) documentation for more information about processing paychecks.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses/reimburse.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reinvoice_expenses.html "Re-invoice expenses") |
  * [precedente](post_expenses.html "Registra spese") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Reimburse employees


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