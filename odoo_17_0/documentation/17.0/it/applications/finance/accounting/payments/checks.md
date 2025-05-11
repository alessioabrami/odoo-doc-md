# Controlli — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](batch.html "Pagamenti raggruppati") |
  * [precedente](online/install_portal_patch.html "Install the patch to disable online invoice payment") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Controlli



# Controlli¶

There are two ways to handle payments received by checks in Odoo, either by using outstanding accounts or by bypassing the reconciliation process.

**Using outstanding accounts is recommended** , as your bank account balance stays accurate by taking into account checks yet to be cashed.

Nota

Both methods produce the same data in your accounting at the end of the process. But if you have checks that have not been cashed in, the **Outstanding Account** method reports these checks in the **Outstanding Receipts** account. However, funds appear in your bank account whether or not they are reconciled, as the bank value is reflected at the moment of the bank statement.

Vedi anche

  * [Outstanding accounts](../bank.html#bank-outstanding-accounts)

  * [Bank reconciliation](../get_started/cheat_sheet.html#accounting-reconciliation)




## Method 1: Outstanding account¶

When you receive a check, you [record a payment](../bank/reconciliation.html) by check on the invoice. Then, when your bank account is credited with the check’s amount, you reconcile the payment and statement to move the amount from the **Outstanding Receipt** account to the **Bank** account.

Suggerimento

You can create a new payment method named _Checks_ if you would like to identify such payments quickly. To do so, go to Accounting ‣ Configuration ‣ Journals ‣ Bank, click the Incoming Payments tab, and Add a line. As Payment Method, select Manual, and enter `Checks` as name.

## Method 2: Reconciliation bypass¶

When you receive a check, you [record a payment](../bank/reconciliation.html) on the related invoice. The amount is then moved from the **Account Receivable** to the **Bank** account, bypassing the reconciliation and creating only **one journal entry**.

To do so, you _must_ follow the following setup. Go to Accounting ‣ Configuration ‣ Journals ‣ Bank. Click the Incoming Payments tab and then Add a line, select Manual as Payment Method, and enter `Checks` as Name. Click the toggle menu button, tick Outstanding Receipts accounts, and in the Outstanding Receipts accounts column, and set the Bank account for the **Checks** payment method.

## Registrare un pagamento¶

Nota

By default, there are two ways to register payments made by check:

  * **Manual** : for single checks;

  * **Batch** : for multiple checks at once.




This documentation focuses on **single-check** payments. For **batch deposits** , see [the batch payments documentation](batch.html).

Once you receive a customer check, go to the related invoice (Accounting ‣ Customer ‣ Invoices), and click Register Payment. Fill in the payment information:

  * Journal: Bank;

  * Payment method: Manual (or **Checks** if you have created a specific payment method);

  * Memo: enter the check number;

  * Click Create Payment.




The generated journal entries are different depending on the payment registration method chosen.

## Registrazioni contabili¶

### Outstanding account¶

The invoice is marked as In Payment as soon as you record the payment. This operation produces the following **journal entry** :

Account | Statement Match | Dare | Avere  
---|---|---|---  
Conto di credito |  |  | 100.00  
Ricevute in sospeso |  | 100.00 |   
  
Then, once you receive the bank statements, match this statement with the check of the **Outstanding Receipts** account. This produces the following **journal entry** :

Account | Statement Match | Dare | Avere  
---|---|---|---  
Ricevute in sospeso | X |  | 100.00  
Banca |  | 100.00 |   
  
If you use this approach to manage received checks, you get the list of checks that have not been cashed in the **Outstanding Receipt** account (accessible, for example, from the general ledger).

### Reconciliation bypass¶

The invoice is marked as Paid as soon as you record the check.

With this approach, you bypass the use of **outstanding accounts** , effectively getting only one journal entry in your books and bypassing the reconciliation:

Account | Statement Match | Dare | Avere  
---|---|---|---  
Conto di credito | X |  | 100.00  
Banca |  | 100.00 |   
  
[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/checks.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](batch.html "Pagamenti raggruppati") |
  * [precedente](online/install_portal_patch.html "Install the patch to disable online invoice payment") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Controlli


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