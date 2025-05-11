# Vendor bill sequence — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payments.html "Pagamenti") |
  * [precedente](deferred_expenses.html "Deferred expenses") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Vendor bill sequence



# Vendor bill sequence¶

When confirming a vendor bill, Odoo generates a unique vendor bill reference number. By default, it uses the sequence format `BILL/year/month/incrementing-number` (e.g., `BILL/2025/01/00001`), which restarts from `00001` each year.

However, it is possible to change the sequence format and its periodicity, and to mass-resequence vendor bills.

Nota

Le modifiche apportate ai numeri di riferimento vengono registrate nel chatter.

## Modificare la sequenza predefinita¶

To customize the default sequence, open the last confirmed vendor bill, click Reset to Draft, and edit the vendor bill’s reference number.

Odoo then explains how the detected format will be applied to all future vendor bills. For example, if the current vendor bill’s month is withdrawn, the sequence’s periodicity will change to every year instead of every month.

Suggerimento

The sequence format can be edited directly when creating the first vendor bill of a given sequence period.

## Mass-resequencing vendor bills¶

It can be helpful to resequence multiple vendor bill numbers. For example, when importing vendor bills from another accounting system and the reference originates from the previous software, continuity for the current year must be maintained without restarting from the beginning.

Nota

Questa funzione è disponibile solo per gli utenti con accesso come amministratore o consulente.

Follow these steps to resequence vendor bill numbers:

  1. attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode).

  2. In the vendor bills list view, select the vendor bills that need a new sequence.

  3. Fai clic sul menu __ Azioni e scegli Riordinamento.

  4. Nel campo Ordinamento, scegli di

     * mantenere l’ordine corrente: l’ordine dei numeri rimane lo stesso.

     * Riordinare per data contabile: il numero viene riordinato per data contabile.

  5. Configura la Prima nuova sequenza.

  6. Anteprima modifiche e fai clic su Conferma.




Nota

  * To indicate where the sequence change began, the first vendor bill in the new sequence is highlighted in red in the Vendor Bills list. This visual marker is permanent and purely informational.

  * If there are any irregularities in the new sequence, such as gaps, cancelled, or deleted entries within the open period, a Gaps in the sequence message appears in the Vendor Bills journal on the Accounting dashboard. To view more details about the related vendor bill(s), click Gaps in the sequence. This visual marker is temporary and will disappear once the entry’s accounting date is on or after the lock date.




Suggerimento

Resequencing is not possible:

  * When entries are before a lock date.

  * When the sequence leads to a duplicate.

  * When the range is invalid. For example, if the Bill Date doesn’t align with the date in the new sequence, such as using a 2024 sequence (BILL/2024/MM/XXXX) for an vendor bill dated in 2025.




In these cases, a Validation Error message appears.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/vendor_bills/sequence.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payments.html "Pagamenti") |
  * [precedente](deferred_expenses.html "Deferred expenses") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Vendor bill sequence


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
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto