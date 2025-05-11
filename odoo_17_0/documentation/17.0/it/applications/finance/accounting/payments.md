# Pagamenti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments/online.html "Online payments") |
  * [precedente](vendor_bills/sequence.html "Vendor bill sequence") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Pagamenti



# Pagamenti¶

In Odoo, i pagamenti possono essere collegati automaticamente a una fattura o a un conto, oppure essere registrazioni autonome da utilizzare in un secondo momento:

  * Se un pagamento è **collegato a una fattura o a una bolletta** , riduce/estingue l’importo dovuto sulla fattura. È possibile effettuare più pagamenti sulla stessa fattura.

  * Se un pagamento non è **collegato a una fattura o a un conto** , il cliente ha un credito in sospeso con l’azienda o l’azienda ha un debito in sospeso con un fornitore. Questi importi in sospeso riducono/assolvono le fatture/bollette non pagate.




Vedi anche

  * Trasferimenti interni

  * [Riconciliazione bancaria](bank/reconciliation.html)

  * Tutorial di Odoo: Configurazione banca <<https://www.odoo.com/slides/slide/bank-configuration-6832>>`_




## Registrazione di un pagamento da una fattura o da un conto¶

Clicking Register payment in a customer invoice or vendor bill generates a new journal entry and sets the amount due according to the payment amount. The counterpart is reflected in an [outstanding](bank.html#bank-outstanding-accounts) **receipts** or **payments** account. At this point, the customer invoice or vendor bill is marked as In payment or Partially paid. Then, when the outstanding account is reconciled with a bank transaction, the invoice or vendor bill changes to the Paid status.

To open the Journal Entry Info window and display more information about the payment, click the __(information) icon in the footer of the Invoice Lines tab. To access additional information, such as the related journal entry, click View.

Nota

  * The customer invoice or vendor bill must be in the Posted status to register the payment.

  * If a payment is unreconciled, it still appears in the books but is no longer linked to the invoice.

  * If a payment is (un)reconciled in a different currency, a journal entry is automatically created to post the currency exchange gains/losses (reversal) amount.

  * If a payment is (un)reconciled on an invoice with cash-basis taxes, a journal entry is automatically created to post the cash-basis tax (reversal) amount.




Suggerimento

If the main bank account is set as the [outstanding account](bank.html#bank-outstanding-accounts) on the bank journal’s payment method, registering the full payment on an invoice or bill moves the invoice/bill directly to the Paid status without requiring bank reconciliation.

## Registering payments not tied to an invoice or bill¶

When a new payment is registered via Customers / Vendors ‣ Payments, it is not directly linked to an invoice or bill. Instead, the account receivable or the account payable is matched with the **outstanding account** until it is manually matched with its related invoice or bill. Then, [reconciling](bank/reconciliation.html) the payment with the bank transaction completes the payment workflow.

### Payments matching¶

Nota

During the [bank reconciliation](bank/reconciliation.html) process, a remaining balance is identified if the total debits and credits do not match when records are compared with bank transactions. This balance must either be reconciled later or written off immediately.

#### For a single invoice or bill¶

A blue banner appears when validating a new invoice/bill and an **outstanding payment** exists for this specific customer or vendor. To match it with the invoice or bill, click Add under Outstanding Credits or Outstanding Debits.

The invoice or bill is then marked as In payment until the payment is [reconciled](bank/reconciliation.html) with its corresponding [bank transaction(s)](bank/transactions.html).

#### Matching payments¶

The Payments matching or Auto-reconcile tool allows reconciling journal items with each other (i.e., payments with customer invoices or vendor bills) either individually or in batches. Access the Accounting Dashboard, click the __( dropdown menu) button from the Customer Invoices or Vendor Bills journals, and select Payments Matching. Alternatively, go to Accounting ‣ Accounting ‣ Reconcile.

To manually Reconcile journal items, select the individual items from the list view and click Reconcile.

##### Auto-Reconcile Feature¶

To use the Auto-Reconcile feature, follow these steps:

  1. In the Journal Items to reconcile list view, click Auto-Reconcile next to the receivable or payable account (or a specific contact’s journal item in that account).

  2. In the Find Entries to Reconcile Automatically window, set the Reconcile field depending on how you want to match journal items:

     * Opposite balances one by one: Each debit journal item will be matched with the corresponding credit journal item of the same value.

     * Accounts with zero balances: All reconciled journal items will have the same matching number.

  3. Click Launch.




Invoices and bills are automatically matched to their corresponding payments and marked as In payment until they are [reconciled](bank/reconciliation.html) with their corresponding [bank transactions](bank/transactions.html).

## Registering payments on multiple invoices or bills (group payments)¶

To register payments on multiple invoices/bills, follow these steps:

  1. Go to Accounting ‣ Customers ‣ Invoices/Credit Notes or Accounting ‣ Vendors ‣ Bills/Refunds.

  2. In the list view, select the relevant invoices/credit notes or bills/refunds.

  3. Click __ Actions and select Register Payment.

  4. In the Register Payment window, select the Journal, the Payment Method, and the Payment Date.

  5. To combine all payments from the same contact into a single payment, enable the Group Payments option, or leave it unchecked to create separate payments.

  6. Click Create payment.




The invoices or bills are then marked as In payment until the bank transactions are [reconciled](bank/reconciliation.html) with the payments.

## Registering a single payment for multiple customers or vendors (batch payments)¶

Batch payments allow grouping payments from multiple customers to ease [reconciliation](bank/reconciliation.html). They are also useful when depositing [checks](payments/checks.html) or cash payments to the bank or for generating bank payment files such as [SEPA](payments/pay_sepa.html) or [NACHA](../fiscal_localizations/united_states.html#l10n-us-nacha).

Vedi anche

[Pagamenti raggruppati](payments/batch.html)

## Registering a partial payment¶

To register a partial payment, click on Register Payment from the related invoice or bill. In the case of a partial payment (when the Amount paid is less than the total remaining amount on the invoice or the bill), the Payment Difference field displays the outstanding balance. There are two options:

  * Keep open: Keep the invoice or the bill open and mark it with a Partial banner;

  * Mark as fully paid: Select an account in the Post Difference In field and change the Label if needed. A journal entry will be created to balance the accounts payable or receivable with the selected account.




## Reconciling payments with bank transactions¶

Once a payment has been registered, the status of the invoice or bill is In payment. The next step is [reconciling](bank/reconciliation.html) the payment with the related [bank transaction](bank/transactions.html) line to finalize the payment workflow and mark the invoice or bill as Paid.

  * [Online payments](payments/online.html)
    * [Install the patch to disable online invoice payment](payments/online/install_portal_patch.html)
  * [Controlli](payments/checks.html)
  * [Pagamenti raggruppati](payments/batch.html)
  * [SEPA Direct Debit (SDD) customer payments](payments/batch_sdd.html)
  * [Follow-up on invoices](payments/follow_up.html)
  * [Trasferimenti interni](payments/internal_transfers.html)
  * [Pay with SEPA](payments/pay_sepa.html)
  * [Pay by checks](payments/pay_checks.html)
  * [Forecast future bills to pay](payments/forecast.html)
  * [Trusted accounts (send money)](payments/trusted_accounts.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments/online.html "Online payments") |
  * [precedente](vendor_bills/sequence.html "Vendor bill sequence") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Pagamenti


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