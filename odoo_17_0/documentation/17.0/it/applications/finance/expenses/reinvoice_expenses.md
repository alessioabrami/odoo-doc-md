# Re-invoice expenses — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment_providers.html "Online payments") |
  * [precedente](reimburse.html "Reimburse employees") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Re-invoice expenses



# Re-invoice expenses¶

If expenses are tracked on customer projects, they can be automatically charged back to the customer. This is done by creating an expense, referencing the sales order the expense is added to, and then creating an expense report.

Next, managers approve the expense report, before the accounting department posts the journal entries.

Finally, once the expense report is posted to a journal, the expenses appears on the specified SO. The SO is then invoiced, thus charging the customer for the expenses.

Importante

Approving expenses, posting expenses to accounting, and reinvoicing expenses on SOs is **only** possible for users with the appropriate [access rights](../../general/users/access_rights.html).

Vedi anche

This document provides lower-level instructions for the creation, submission, approval, and posting of expenses. For fully-detailed instructions for any of these steps, refer to the following documentation:

  * [Log expenses](log_expenses.html)

  * [Expense reports](expense_reports.html)

  * [Approving expenses](approve_expenses.html)

  * [Posting expenses in accounting](post_expenses.html)




## Imposta¶

First, specify the invoicing policy for each expense category. Navigate to Expenses app ‣ Configuration ‣ Expense Categories. Click on an expense category to view the expense category form. Under the INVOICING section, click the radio button next to the desired selection for Re-Invoice Expenses:

  * No: The expense category cannot be re-invoiced.

  * At cost: The expense category invoices expenses at the cost set on the expense category form.

  * Sales price: The expense category invoices at the sales price set on the expense form.




## Create an expense¶

First, when [creating a new expense](log_expenses.html), the correct information needs to be entered to re-invoice the expense to a customer. Using the drop-down menu, select the SO to add the expense to in the Customer to Reinvoice field.

Next, select the Analytic Distribution the expense is posted to. Multiple accounts can be selected, if desired.

To add another Analytic Distribution, click on the line to reveal the Analytic pop-over window. Click Add a line, then select the desired Analytic Distribution from the drop-down field. If selecting more than one Analytic Distribution, the Percentage fields **must** be modified. By default, both fields are populated with `100%`. Adjust the percentages for all the fields, so the total of all selected accounts equals `100%`.

Example

A painting company agrees to paint an office building that houses two different companies. During the estimate, a meeting is held at the office location to discuss the project.

Both companies agree to pay for the travel expenses for the painting company employees. When creating the expenses for the mileage and hotels, **both companies** are listed in the Analytic Distribution line, for 50% each.

## Create an expense report¶

After the expenses are created, the expense report must be [created](expense_reports.html#expenses-create-report) and [submitted](expense_reports.html#expenses-submit), in the same manner as all other expenses.

Once the expense report is submitted, a __ Sales Orders smart button appears at the top-center of both the expense report, and each individual expense record being reinvoiced.

Importante

Selecting the proper SO in the Customer to Reinvoice field is **critical** , since this is how expenses are automatically invoiced after an expense report is approved.

The Customer to Reinvoice field can be modified _only_ until an expense report is **approved**. After an expense report is approved, the Customer to Reinvoice field is no longer able to be modified.

## Approve and post expenses¶

Before [approving an expense report](approve_expenses.html), ensure the Analytic Distribution section is populated for every expense line.

If an Analytic Distribution entry is missing, assign the correct accounts from the drop-down menu, then click Approve.

Nota

The Approve button **only** appears after an expense report has been [submitted](expense_reports.html#expenses-submit).

The accounting department is typically responsible for [posting journal entries](post_expenses.html). To post expenses to an accounting journal, click Post Journal Entries. Once an expense report is approved, it can then be posted.

The SO is **only** updated _after_ the journal entries are posted. Once the journal entries are posted, the expenses now appear on the referenced SO.

## Fatturare le spese¶

After the expense report has been approved, and the journal entries have been posted, the SO is updated, and the customer can be invoiced.

Select the expense report, and click the __ Sales Orders smart button to open the SO. The expenses to be re-invoiced now appear on the SO.

Nota

More than one SO can be referenced on an expense report. If more than one SO is referenced, clicking the Sales Orders smart button opens a list displaying all the SOs associated with that expense report. Click on a SO to open the individual SO details.

The expenses are listed in the SO Order Lines tab.

Next, click Create Invoice, and a Create invoices pop-up window appears. Select if the invoice is a Regular invoice, a Down payment (percentage), or a Down payment (fixed amount). Then, click Create Draft Invoice. Doing so creates a draft invoice for the customer. Click Confirm to confirm the invoice, and the customer is invoiced for the expenses.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses/reinvoice_expenses.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment_providers.html "Online payments") |
  * [precedente](reimburse.html "Reimburse employees") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Costi](../expenses.html) »
  * Re-invoice expenses


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