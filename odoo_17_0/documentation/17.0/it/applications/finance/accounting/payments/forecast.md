# Forecast future bills to pay — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](trusted_accounts.html "Trusted accounts \(send money\)") |
  * [precedente](pay_checks.html "Pay by checks") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Forecast future bills to pay



# Forecast future bills to pay¶

In Odoo, you can manage payments by setting automatic **Payments Terms** and **follow-ups**.

## Configuration: payment terms¶

In order to track vendor conditions, we use **Payment Terms** in Odoo. They allow keeping track of due dates on invoices. Examples of **Payment Terms** are:

  * 50% entro 30 giorni

  * 50% entro 45 giorni




To create them, go to Accounting ‣ Configuration ‣ Invoicing: Payment Terms and click on Create to add new terms or click existing ones to modify them.

Vedi anche

[Odoo Tutorials: Payment Terms](https://www.odoo.com/slides/slide/payment-terms-1679?fullscreen=1)

Once **Payment Terms** are defined, you can assign them to your vendor by default. To do so, go to Vendors ‣ Vendors, select a vendor, click the Sales & Purchase tab, and select a specific **Payment Term**. This way, every time you purchase from this vendor, Odoo automatically proposes the chosen Payment Term.

Nota

If you do not set a specific Payment Term on a vendor, you can still set one on the vendor bill.

## Forecast bills to pay with the aged payable report¶

To track amounts to be paid to the vendors, use the **Aged Payable** report. To access it, go to Accounting ‣ Reporting ‣ Partner Reports: Aged Payable. This report gives you a summary per vendor of the amounts to pay, compared to their due date (the due date being computed on each bill using the terms). This report tells you how much you will have to pay within the following months.

## Select bills to pay¶

You can get a list of all your vendor bills by going to Vendors ‣ Bills. To view only the bills that you need to pay, click Filters ‣ Bills to Pay. To view only overdue payments, select the Overdue filter instead.

You can also group bills by their due date by clicking Group By ‣ Due Date and selecting a time period.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/forecast.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](trusted_accounts.html "Trusted accounts \(send money\)") |
  * [precedente](pay_checks.html "Pay by checks") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Forecast future bills to pay


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