# Pagamenti raggruppati — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [precedente](checks.html "Controlli") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pagamenti raggruppati



# Pagamenti raggruppati¶

Batch payments allow grouping payments from multiple customers or vendors into a single batch and generating a detailed deposit slip or payment file with a batch reference. This reference can be used during [reconciliation](../bank/reconciliation.html) to match bank transactions with the corresponding payments. This feature is particularly useful for submitting [SEPA Direct Debit payments](batch_sdd.html), depositing cash payments or [checks](checks.html), or generating outgoing payment files, such as [SEPA](pay_sepa.html) or [NACHA](../../fiscal_localizations/united_states.html#l10n-us-nacha).

## Configurazione¶

To enable batch payments, go to Accounting ‣ Configuration ‣ Settings, scroll down to the Customer Payments section, and enable Batch Payments.

## Batch creation¶

To create a batch payment, follow these steps:

  1. Make sure all payments to be included in the batch have been [registered](../payments.html#accounting-payments-from-invoice-bill).

  2. Go to Accounting ‣ Customers ‣ Payments.

  3. Select the payments to include in the batch.

Nota

All payments in the batch must use the same payment method. If needed, payments can be grouped using the Payment Method Line.

  4. Click Create batch or click __ Actions and select Create batch payment.

  5. In the batch payment form, review the selected payments. If any individual payments were missed, click Add a line and select the missing payments to be included in the batch.

  6. Once all relevant payments are included, click Validate to finalize the batch.




Nota

Once validated, no additional payments can be added to a batch.

Suggerimento

  * Click Print to download a list of the included payments.

  * To view existing batch payments, go to Accounting ‣ Customers ‣ Batch Payments.




### Riconciliazione bancaria¶

Once the bank transactions [have been created](../bank/transactions.html) in your database, you can [reconcile them with the batch payment](../bank/reconciliation.html#reconciliation-batch-payments).

Nota

If a specific payment could not be processed by the bank or is missing, remove the related line from the resulting entry section of the reconciliation view using the __( delete) button before validating the reconciliation.

Vedi anche

  * [Pagamenti](../payments.html)

  * [SEPA Direct Debit (SDD) customer payments](batch_sdd.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/batch.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [precedente](checks.html "Controlli") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pagamenti raggruppati


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