# Pagamenti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments/online.html "Online payments") |
  * [precedente](vendor_bills/sequence.html "Vendor bill sequence") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Pagamenti



# Pagamenti¶

In Odoo, i pagamenti possono essere collegati automaticamente a una fattura o a un conto, oppure essere registrazioni autonome da utilizzare in un secondo momento:

  * Se un pagamento è **collegato a una fattura o a una bolletta** , riduce/estingue l’importo dovuto sulla fattura. È possibile effettuare più pagamenti sulla stessa fattura.

  * Se un pagamento non è **collegato a una fattura o a un conto** , il cliente ha un credito in sospeso con l’azienda o l’azienda ha un debito in sospeso con un fornitore. Questi importi in sospeso riducono/assolvono le fatture/bollette non pagate.




Vedi anche

  * [Internal transfers](bank/internal_transfers.html)

  * [Riconciliazione bancaria](bank/reconciliation.html)

  * Tutorial di Odoo: Configurazione banca <<https://www.odoo.com/slides/slide/bank-configuration-6832>>`_




## Metodo di pagamento¶

Several payment methods are available in Odoo to allow different configurations for different types of payments. Examples of payment methods include manual payments (such as cash), [checks](payments/pay_checks.html), and batch payment files (such as [NACHA](../fiscal_localizations/united_states.html#l10n-us-ach-electronic-transfers) and [SEPA](payments/pay_sepa.html)). Payment methods can be configured in the Incoming Payments and Outgoing Payments tabs of a bank or cash journal.

Vedi anche

[Metodo di pagamento](../../sales/point_of_sale/payment_methods.html) for Point of Sale

### Preferred payment method¶

A contact’s preferred payment method can be set so that when a payment is created for that contact, the payment method is automatically selected by default. Invoices and bills can be filtered by Payment Method to simplify group payments.

To set a preferred Payment Method for a customer or a vendor, go to Accounting ‣ Customers ‣ Customers or Accounting ‣ Vendors ‣ Vendors and select the customer or vendor. In the Sales & Purchase tab of the contact form, select the preferred Payment Method in the Sales section for invoice payments or for vendor bill payments in the Purchase section.

Suggerimento

Access a full list of all contacts from the Customers or Vendors list view by removing the Customers or Vendors filter. Alternatively, access the full contact list through the Contacts app.

### Controlli¶

[Vendor bills can be paid by check](payments/pay_checks.html) using a dedicated outgoing payment method, which allows check numbers to be tracked and checks to be printed directly from Odoo.

For incoming customer check payments, you can use the default Manual Payment payment method, or you can create a payment method specifically for checks to help identify such payments quickly. To create a _Check_ payment method, follow these steps:

  1. Go to Accounting ‣ Configuration ‣ Journals and select the Bank journal.

  2. In the Incoming Payments tab, click Add a line.

  3. As Payment Method, select Manual, then enter `Check` as the Name.




When registering a customer payment on an invoice or not related to an invoice, use the new Check payment method.

Nota

Registering a customer payment by check in Odoo does not move funds. Checks must be deposited in order to make the payment. Once deposited to your bank, the check should appear as a [bank transaction](bank/transactions.html), at which point it can be [reconciled](bank/reconciliation.html) with the registered payment.

Suggerimento

  * For best practice, enter the check number as the Memo when registering a customer payment by check.

  * [Batch payments](payments/batch.html) can simplify reconciling deposits containing multiple checks.




## Registrazione di un pagamento da una fattura o da un conto¶

To register a payment for an invoice or a bill, follow these steps:

  1. Click Pay on a customer invoice or vendor bill. In the Pay window, select the Journal and the Payment Date.

  2. If previously set, the contact’s preferred Payment Method is automatically selected by default but can be updated if necessary.

  3. If using [payment terms](customer_invoices/payment_terms.html), the Amount is automatically set based on the installment amounts defined by the payment term. To pay the full amount instead, click full amount.

  4. If necessary, edit the Memo.

  5. Click Create Payment.




After the payment is registered, the customer invoice or vendor bill is marked as In payment.

Without outstanding accountsUsing outstanding accounts

If no [outstanding accounts](bank.html#accounting-bank-outstanding-accounts) are configured, no journal entry is created. To display more information about the payment, click the Payments smart button.

When the invoice or vendor bill is [reconciled](bank/reconciliation.html) with a bank transaction, its status is updated to Paid.

Nota

  * If a bank transaction is reconciled in a different currency, a journal entry is automatically created to post the currency exchange gains/loss amount.

  * When a bank transaction is reconciled with an invoice with cash-basis, a journal entry is automatically created to post the cash-basis tax amount.




By default, payments in Odoo do not create journal entries, but they can easily be configured to create journal entries using [outstanding accounts](bank.html#accounting-bank-outstanding-accounts).

Registering a payment on a customer invoice or vendor bill generates a new journal entry and reduces the Amount Due based on the payment amount. The counterpart is reflected in an [outstanding](bank.html#accounting-bank-outstanding-accounts) **receipts** or **payments** account. At this point, the customer invoice or vendor bill is marked as In payment. Then, when the payment is [reconciled](bank/reconciliation.html) with a bank transaction, the invoice or vendor bill status changes to Paid.

The __information icon next to the payment line displays more information about the payment. To access additional information, such as the related journal, click View.

Nota

  * Unreconciling a payment unlinks it from the invoice or bill but does not delete the payment.

  * If a payment is (un)reconciled in a different currency, a journal entry is automatically created to post the currency exchange gains/losses (reversal) amount.

  * If a payment is (un)reconciled on an invoice with cash-basis taxes, a journal entry is automatically created to post the cash-basis tax (reversal) amount.




Suggerimento

If the main bank account is set as the outstanding account on the bank journal’s payment method, registering the full payment on an invoice or bill moves the invoice/bill directly to the Paid status without requiring bank reconciliation.

## Registering payments not tied to an invoice or bill¶

When a new payment is registered via Customers / Vendors ‣ Payments, it is not directly linked to an invoice or bill.

Without outstanding accountsUsing outstanding accounts

Payments that are not linked to an invoice or bill should not be registered without using [outstanding accounts](bank.html#accounting-bank-outstanding-accounts), as there is no way to associate the payment with the invoice or bill since no journal entry is created for the payment. The amount paid or received is not reflected in the accounting and the Amount Due is not updated based on the payment amount.

Instead, the payment’s journal entry matches the outstanding account with the account receivable or the account payable until the payment is manually matched with its related invoice or bill. Then, [reconciling](bank/reconciliation.html) the payment with the bank transaction completes the payment workflow.

### Payments matching¶

Nota

During the [bank reconciliation](bank/reconciliation.html) process, a remaining balance is identified if the total debits and credits do not match when records are compared with bank transactions. This balance must either be reconciled later or written off immediately.

#### For a single invoice or bill¶

Without outstanding accountsUsing outstanding accounts

By default, payments in Odoo do not create journal entries. As a result, there is no payment to match.

A blue banner appears when validating a new invoice/bill and an **outstanding payment** exists for this specific customer or vendor. To match it with the invoice or bill, click Add under Outstanding Credits or Outstanding Debits.

The invoice or bill is then marked as In payment until the payment is [reconciled](bank/reconciliation.html) with its corresponding [bank transaction(s)](bank/transactions.html).

#### For multiple invoices or bills¶

Without outstanding accountsUsing outstanding accounts

By default, payments in Odoo do not create journal entries. As a result, there is no payment to match, but this feature can still be used to match miscellaneous journal items.

The Payments matching or Auto-reconcile tool allows reconciling journal items with each other (i.e., payments with customer invoices or vendor bills) either individually or in batches. Access the Accounting Dashboard, click the __( ellipsis) button from the Customer Invoices or Vendor Bills journals, and select Payments Matching. Alternatively, go to Accounting ‣ Accounting ‣ Reconcile.

To manually Reconcile journal items, select the individual items from the list view and click Reconcile.

##### Auto-Reconcile Feature¶

Without outstanding accountsUsing outstanding accounts

To use the Auto-Reconcile feature, follow these steps:

  1. In the Journal Items to reconcile list view, click Auto-Reconcile next to the receivable or payable account (or a specific contact’s group of journal items in that account).

  2. In the Reconcile automatically window, click Reconcile.




To use the Auto-Reconcile feature, follow these steps:

  1. In the Journal Items to reconcile list view, click Auto-Reconcile next to the receivable or payable account (or a specific contact’s group of journal items in that account).

  2. In the Reconcile Automatically window, set the Reconcile field depending on how you want to match journal items:

     * Perfect Match: Each debit journal item will be matched with the corresponding credit journal item of the same value.

     * Clear Accounts: All reconciled journal items will have the same matching number, as they are selected from the same account.

  3. Click Reconcile.




Invoices and bills are automatically matched to their corresponding payments and marked as In payment until they are [reconciled](bank/reconciliation.html) with their corresponding [bank transactions](bank/transactions.html).

## Registering payments on multiple invoices/credit notes or bills/refunds (group payments)¶

To register payments on multiple invoices/credit notes or bills/refunds, follow these steps:

  1. Go to Accounting ‣ Customers ‣ Invoices/Credit Notes or Accounting ‣ Vendors ‣ Bills/Refunds.

  2. In the list view, click into the search bar, group by Payment Method, select the relevant invoices/credit notes or bills/refunds and click Pay.

  3. In the Pay window, select the Journal and the Payment Date.

  4. If previously set, the contact’s preferred Payment Method is automatically selected by default but can be updated if necessary.

  5. If using [payment terms](customer_invoices/payment_terms.html), the Amount is automatically set based on the installment amounts defined by the payment term. To pay the full amount instead, click full amount.

  6. To combine all payments from the same contact into a single payment, enable the Group Payments option, or leave it unchecked to create separate payments.

  7. Click Create payment.




Without outstanding accountsUsing outstanding accounts

The invoices or bills are then marked as In payment until they are [reconciled](bank/reconciliation.html) with the bank transactions.

The invoices or bills are then marked as In payment until the bank transactions are [reconciled](bank/reconciliation.html) with the payments.

## Registering a single payment for multiple customers or vendors (batch payments)¶

Batch payments allow grouping payments from multiple customers to ease [reconciliation](bank/reconciliation.html). They are also useful when depositing checks or cash payments to the bank or for generating bank payment files such as [SEPA](payments/pay_sepa.html) or [NACHA](../fiscal_localizations/united_states.html#l10n-us-nacha).

Vedi anche

[Pagamenti raggruppati](payments/batch.html)

### Payments matching¶

The Payments matching tool opens all unreconciled journal items and allows them to be processed individually, matching all payments and journal items. Go to the Accounting Dashboard, go to Accounting ‣ Accounting ‣ Reconcile or click the __( ellipsis) button from the Customer Invoices or Vendor Bills journals, and select Payments Matching.

Nota

During the [reconciliation](bank/reconciliation.html), if the sum of the debits and credits does not match, there is a remaining balance. This either needs to be reconciled at a later date or written off directly.

## Registering a partial payment¶

To register a partial payment, click on Pay from the related invoice or bill.

Without outstanding accountsUsing outstanding accounts

In the case of a partial payment (when the Amount paid is less than the total remaining amount on the invoice or the bill), fill in the Amount in the Pay window.

In the case of a partial payment (when the Amount paid is less than the total remaining amount on the invoice or the bill), the Payment Difference field displays the outstanding balance. There are two options:

  * Keep open: Keep the invoice or the bill open and mark it with a Partial banner;

  * Mark as fully paid: Select an account in the Post Difference In field and change the Label if needed. A journal entry will be created to balance the accounts payable or receivable with the selected account.




## Reconciling payments with bank transactions¶

Without outstanding accountsUsing outstanding accounts

Once a payment has been registered, the status of the invoice or bill is In payment. The next step is [reconciling](bank/reconciliation.html) the related [bank transaction](bank/transactions.html) line with the invoice or bill to finalize the payment workflow and mark the invoice or bill as Paid.

Once a payment has been registered, the status of the invoice or bill is In payment. The next step is [reconciling](bank/reconciliation.html) the payment with the related [bank transaction](bank/transactions.html) line to finalize the payment workflow and mark the invoice or bill as Paid.

  * [Online payments](payments/online.html)
    * [Install the patch to disable online invoice payment](payments/online/install_portal_patch.html)
  * [Pagamenti raggruppati](payments/batch.html)
  * [SEPA Direct Debit (SDD) customer payments](payments/batch_sdd.html)
  * [Follow-up on invoices](payments/follow_up.html)
  * [Pay with SEPA](payments/pay_sepa.html)
  * [Pay by checks](payments/pay_checks.html)
  * [Forecast future bills to pay](payments/forecast.html)
  * [Trusted accounts (send money)](payments/trusted_accounts.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/payments.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments/online.html "Online payments") |
  * [precedente](vendor_bills/sequence.html "Vendor bill sequence") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
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
  *[FBM]: Fulfilled by Merchant
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
  *[POS]: point of sale
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
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record