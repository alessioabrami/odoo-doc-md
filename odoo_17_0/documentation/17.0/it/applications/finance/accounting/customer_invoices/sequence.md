# Sequenza fattura — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](snailmail.html "Posta ordinaria") |
  * [precedente](electronic_invoicing.html "Fatturazione elettronica \(EDI\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Sequenza fattura



# Sequenza fattura¶

When confirming an invoice, Odoo generates a unique invoice reference number. By default, it uses the sequence format `INV/year/incrementing-number` (e.g., `INV/2025/00001`), which restarts from `00001` each year.

Tuttavia, è possibile modificare il formato della sequenza e la periodicità e risequenziare le fatture in massa.

Nota

Le modifiche apportate ai numeri di riferimento vengono registrate nel chatter.

## Modificare la sequenza predefinita¶

Per personalizzare la sequenza predefinita, apri l’ultima fattura confermata, fai clic su Reimposta a bozza e modifica il numero di riferimento della fattura.

Odoo spiega poi come il formato rilevato verrà applicato a tutte le fatture future. Ad esempio, se viene aggiunto il mese della fattura corrente, la periodicità della sequenza passerà a ogni mese anziché a ogni anno.

Suggerimento

Il formato della sequenza può essere modificato direttamente durante la creazione della prima fattura di un determinato periodo di sequenza.

## Risequenziare le fatture in massa¶

Può essere utile ricollegare più numeri di fattura. Ad esempio, quando si importano fatture da un altro sistema di fatturazione o di contabilità e il riferimento proviene dal software precedente, è necessario mantenere la continuità per l’anno in corso senza ricominciare dall’inizio.

Nota

Questa funzione è disponibile solo per gli utenti con accesso come amministratore o consulente.

Segui i passaggi per riordinare i numeri di fattura:

  1. attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode).

  2. Dalla dashboard Contabilità, apri il registro relativo alle Fatture cliente.

  3. Seleziona le fatture che hanno bisogno di una nuova sequenza.

  4. Fai clic sul menu __ Azioni e scegli Riordinamento.

  5. Nel campo Ordinamento, scegli di

     * mantenere l’ordine corrente: l’ordine dei numeri rimane lo stesso.

     * Riordinare per data contabile: il numero viene riordinato per data contabile.

  6. Configura la Prima nuova sequenza.

  7. Anteprima modifiche e fai clic su Conferma.




Nota

  * To indicate where the sequence change began, the first invoice in the new sequence is highlighted in red in the Customer Invoices list. This visual marker is permanent and purely informational.

  * If there are any irregularities in the new sequence, such as gaps, cancelled, or deleted entries within the open period, a Gaps in the sequence message appears in the Customer Invoices journal on the Accounting dashboard. To view more details about the related invoice(s), click Gaps in the sequence. This visual marker is temporary and will disappear once the entry’s accounting date is on or after the lock date.




Suggerimento

Resequencing is not possible:

  * When entries are before a lock date.

  * When the sequence leads to a duplicate.

  * When the range is invalid. For example, if the Invoice Date doesn’t align with the date in the new sequence, such as using a 2024 sequence (INV/2024/XXXXX) for an invoice dated in 2025.




In these cases, a Validation Error message appears.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/sequence.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](snailmail.html "Posta ordinaria") |
  * [precedente](electronic_invoicing.html "Fatturazione elettronica \(EDI\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Sequenza fattura


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