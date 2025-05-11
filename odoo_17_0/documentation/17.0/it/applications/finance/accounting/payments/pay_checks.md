# Pay by checks — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forecast.html "Forecast future bills to pay") |
  * [precedente](pay_sepa.html "Pay with SEPA") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pay by checks



# Pay by checks¶

Once you decide to pay a supplier bill, you can select to pay by check. You can then print all the payments registered by check. Finally, the bank reconciliation process will match the checks you sent to suppliers with actual bank statements.

## Configurazione¶

### Activate checks payment methods¶

To activate the checks payment method, go to Accounting ‣ Configuration ‣ Settings, and scroll down to the Vendor Payments section. There, you can activate the payment method as well as set up the Check Layout.

Nota

  * Once the Checks setting is activated, the **Checks** payment method is automatically set up in the Outgoing Payments tabs of **bank** journals.

  * Some countries require specific modules to print checks; such modules may be installed by default. For instance, the U.S. Checks Layout module is required to print U.S. checks.




## Compatible check stationery for printing checks¶

### Stati Uniti¶

For the United States, Odoo supports by default the check formats of:

  * **Quickbooks & Quicken**: check on top, stubs in the middle and bottom;

  * **Peachtree** : check in the middle, stubs on top and bottom;

  * **ADP** : check in the bottom, and stubs on the top.




## Pay a supplier bill with a check¶

Paying a supplier with a check is done in three steps:

  1. registering a payment

  2. printing checks in batch for all registered payments

  3. reconciling bank statements




### Register a payment by check¶

To register a payment, open any supplier bill from the menu Purchases ‣ Vendor Bills. Once the supplier bill is validated, you can register a payment. Set the Payment Method to Checks and validate the payment.

### Print checks¶

On your Accounting Dashboard in the Bank Journal, you can see the number of checks registered. By clicking on Checks to print you have got the possibility to print the reconciled checks.

To print all checks in batch, select all payments from the list view and click on Print.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/pay_checks.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forecast.html "Forecast future bills to pay") |
  * [precedente](pay_sepa.html "Pay with SEPA") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pay by checks


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