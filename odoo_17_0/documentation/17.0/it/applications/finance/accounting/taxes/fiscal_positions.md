# Posizioni di bilancio (mappatura fiscale e contabile) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avatax.html "Integrazione AvaTax") |
  * [precedente](vat_verification.html "Verifica numero partita IVA \(VIES\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Posizioni di bilancio (mappatura fiscale e contabile)



# Posizioni di bilancio (mappatura fiscale e contabile)¶

Le imposte e i conti predefiniti sono impostati sui prodotti e sui clienti per creare nuove transazioni al volo. Tuttavia, a seconda della localizzazione dei clienti e dei fornitori e del tipo di attività, potrebbe essere necessario utilizzare tasse e conti diversi per una transazione.

Le **Posizioni di bilancio** consentono di creare regole per adattare automaticamente le imposte e i conti utilizzati per una transazione.

È possibile applicarle automaticamente, manualmente oppure assegnarle a un partner.

Nota

Nel [pacchetto di localizzazione fiscale](../../fiscal_localizations.html#fiscal-localizations-packages) soo disponibili diverse posizioni di bilancio predefinite.

## Configurazione¶

> ### Mappatura fiscale e contabile¶

Per modificare o creare una posizione di bilancio, apri l’app Contabilità ‣ Configurazione ‣ Posizioni di bilancio e apri la registrazione per modificarla oppure fai clic su Nuova.

La mappatura delle imposte e dei conti si basa sulle imposte e sui conti predefiniti definiti nella scheda prodotto.

  * Per mappare un’altra imposta o un altro conto, compila la colonna a destra (Imposta da applicare/ Conto alternativo da usare).




  * Per eliminare un’imposta, lascia vuoto il campo Imposta da applicare.

  * Per sostituire un’imposta con altre imposte, aggiungi più righe utilizzato la stessa Tassa su prodotto.




Nota

La mappatura funziona solo con imposte _attive_. Di conseguenza, assicurati che siano attive aprendo l’app Contabilità ‣ Configurazione ‣ Imposte.

## Proposta¶

### Applicazione automatica¶

Per applicare automaticamente una posizione di bilancio in base a una serie di condizioni, accedi a Contabilità ‣ Configurazione ‣ Posizioni di bilancio, apri la posizione di bilancio da modificare e spunta Rileva automaticamente.

Da qui, puoi attivarie varie condizioni:

  * IVA richiesta: il numero di partita IVA del cliente deve essere presente sul modulo di contatto.

  * Raggruppamento nazioni e Paese: la posizione di bilancio viene applicata solo al Paese o al raggruppamento nazioni selezionato.




Nota

  * Se la funzionalità [Verifica le partite IVA](vat_verification.html) è attiva, qualsiasi posizione di bilancio con l’opzione IVA richiesta attivata richiederà numeri di partita IVA intracomunitari validi per applicarle automaticamente.

  * Le imposte sugli ordini **e-commerce** vengono aggiornate automaticamente una volta che il cliente ha effettuato il login o ha compilato i dati di fatturazione.




Importante

La **sequenza** delle posizioni di bilancio definisce quale posizione di bilancio viene applicata se tutte le condizioni impostate su più posizioni di bilancio sono soddisfatte contemporaneamente.

Ad esempio, supponiamo che la prima posizione di bilancio di una sequenza sia rivolta a _Paese A_ mentre la seconda posizione di bilancio sia rivolta a un _raggruppamento nazioni_ che comprende _Paese A_. In questo caso, solo la prima posizione di bilancio sarà applicata ai clienti di _Paese A_.

### Applicazione manuale¶

Per selezionare manualmente una posizione di bilancio, apri un ordine di vendita, una fattura cliente o fornitore, apri la scheda Altre informazioni e seleziona la Posizione di bilancio desiderata prima di aggiungere le righe prodotto.

### Assegnare a un partner¶

Per definire quale posizione di bilancio deve essere utilizzata per impostazione predefinita per un partner specifico, apri il modulo Contabilità ‣ Clienti ‣ Clienti, seleziona il partner, apri la scheda Vendite e acquisti e seleziona la Posizione di bilancio.

Vedi anche

  * [Imposte](../taxes.html)

  * [Tariffe B2B (imposte escluse) e B2C (imposte incluse)](B2B_B2C.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/taxes/fiscal_positions.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avatax.html "Integrazione AvaTax") |
  * [precedente](vat_verification.html "Verifica numero partita IVA \(VIES\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Posizioni di bilancio (mappatura fiscale e contabile)


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
  *[API]: application programming interface
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
  *[sportello unico OSS]: One-Stop Shop