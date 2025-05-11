# Year-end closing — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../expenses.html "Costi") |
  * [precedente](customize.html "Custom reports") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Year-end closing



# Year-end closing¶

Year-end closing is vital for maintaining financial accuracy, complying with regulations, making informed decisions, and ensuring transparency in reporting.

## Anni fiscali¶

By default, the fiscal year is set to last 12 months and end on December 31st. However, its duration and end date can vary due to cultural, administrative, and economic considerations.

To modify these values, go to Accounting ‣ Configuration ‣ Settings. Under the Fiscal Periods section, change the Last Day field if necessary.

If the period lasts _more_ than or _less_ than 12 months, enable Fiscal Years and Save. Go back to the Fiscal Periods section and click ➜ Fiscal Years. From there, click Create, give it a Name, and both a Start Date and End Date.

Nota

Once the set fiscal period is over, Odoo automatically reverts to the default periodicity, taking into account the value specified in the Last Day field.

## Year-end checklist¶

### Before closure¶

Before closing a fiscal year, ensure first everything is accurate and up-to-date:

  * Make sure all bank accounts are fully [reconciled](../bank/reconciliation.html) up to year-end, and confirm that the ending book balances match the bank statement balances.

  * Verify that all [customer invoices](../customer_invoices.html) have been entered and approved and that there are no draft invoices.

  * Confirm that all [vendor bills](../vendor_bills.html) have been entered and agreed upon.

  * Validate all [expenses](../../expenses.html), ensuring their accuracy.

  * Corroborate that all [received payments](../payments.html) have been encoded and recorded accurately.

  * Close all [suspense accounts](../bank.html#bank-accounts-suspense).

  * Book all [depreciation](../vendor_bills/assets.html) and [deferred revenue](../customer_invoices/deferred_revenues.html) entries.




### Closing a fiscal year¶

Then, to close the fiscal year:

  * Run a [tax report](../reporting.html#accounting-reporting-tax-report), and verify that all tax information is correct.

  * Reconcile all accounts on the [balance sheet](../reporting.html#accounting-reporting-balance-sheet):

    * Update the bank balances in Odoo according to the actual balances found on the bank statements.

    * Reconcile all transactions in the cash and bank accounts by running the [aged receivables](../reporting.html#accounting-reporting-aged-receivable) and [aged payables](../reporting.html#accounting-reporting-aged-payable) reports.

    * Audit all accounts, being sure to fully understand all transactions and their nature, making sure to include loans and fixed assets.

    * Optionally, [match payments](../payments.html#accounting-payments-auto-reconcile-tool) to validate any open vendor bills and customer invoices with their payments. While this step is optional, it could assist the year-end closing process if all outstanding payments and invoices are reconciled, potentially finding errors or mistakes in the system.




Next, the accountant likely verifies balance sheet items and book entries for:

>   * year-end manual adjustments,
> 
>   * work in progress,
> 
>   * depreciation journal entries,
> 
>   * loans,
> 
>   * tax adjustments,
> 
>   * etc.
> 
> 


If the accountant is going through the year-end audit, they may want to have paper copies of all balance sheet items (such as loans, bank accounts, prepayments, sales tax statements, etc.) to compare these with the balances in Odoo.

Suggerimento

During this process, it is good practice to set a Journal Entries Lock Date to the last day (inclusive) of the preceding fiscal year by going to Accounting ‣ Accounting ‣ Lock Dates. This way, the accountant can be confident that nobody changes the transactions while auditing the books. Users from the _accountant_ access group can still create and modify entries.

#### Current year’s earnings¶

Odoo uses a unique account type called **current year’s earnings** to display the amount difference between the **income** and **expenses** accounts.

Nota

The chart of accounts can only contain one account of this type. By default, it is a 999999 account named Undistributed Profits/Losses.

To allocate the current year’s earnings, create a miscellaneous entry to book them to any equity account. Once done, confirm whether or not the current year’s earnings in the **balance sheet** is correctly reporting a balance of zero. If that is the case, set an All Users Lock Date to the last day of the fiscal year by going to Accounting ‣ Accounting ‣ Lock Dates.

Suggerimento

Install the Irreversible Lock Date (`account_lock`) module to make the All Users Lock Date _irreversible_ once set.

Nota

A specific year-end closing entry is **optional** in order to close out the **profit and loss statement**. The reports are created in real-time, meaning that the profit and loss statement corresponds directly with the year-end date specified in Odoo. Therefore, any time the **income statement** is generated, the beginning date corresponds with the beginning of the **fiscal year** and all account balances should equal zero.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/reporting/year_end.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../expenses.html "Costi") |
  * [precedente](customize.html "Custom reports") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Year-end closing


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