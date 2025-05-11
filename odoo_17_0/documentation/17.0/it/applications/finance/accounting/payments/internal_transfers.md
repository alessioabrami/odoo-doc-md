# Trasferimenti interni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_sepa.html "Pay with SEPA") |
  * [precedente](follow_up.html "Follow-up on invoices") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Trasferimenti interni



# Trasferimenti interni¶

Internal money transfers can be handled in Odoo. At least two bank accounts are needed to make internal transfers.

Vedi anche

[How to add an additional bank account](../bank.html)

## Configurazione¶

An internal transfer account is automatically created on your database based on your company’s localization and depending on your country’s legislation. To modify the default Internal transfer account, go to Accounting ‣ Configuration ‣ Settings and scroll down to the Default Accounts section.

## Registrare un trasferimento interno da una banca all’altra¶

If you want to transfer money from one bank to another, access the Accounting Dashboard, click the drop-down selection button (⋮) on the bank from which you want to make the transfer, then click Payments. Select or create a payment, tick the Internal Transfer checkbox, and select a Destination Journal before you Confirm the internal transfer.

The money is now booked in the transfer account and another payment is automatically created in the destination journal.

Example

  * Registro banca (banca A)

**Conto** | **Debito** | **Credito**  
---|---|---  
Outstanding Payments account |  | 1.000 $  
**Giroconto interno** | **1.000 $** |   
  * Registro banca (banca B)

**Conto** | **Debito** | **Credito**  
---|---|---  
Outstanding Receipts account | 1.000 $ |   
**Giroconto interno** |  | **1.000 $**  



There is **one outstanding payment** and **one outstanding receipt** pending in your two bank account journals because the bank statement confirming the sending and receiving of the money has not been booked yet.

Once this is done, you can book and reconcile your bank statement lines as usual.

Vedi anche

[Riconciliazione bancaria](../bank/reconciliation.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/internal_transfers.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_sepa.html "Pay with SEPA") |
  * [precedente](follow_up.html "Follow-up on invoices") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Trasferimenti interni


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