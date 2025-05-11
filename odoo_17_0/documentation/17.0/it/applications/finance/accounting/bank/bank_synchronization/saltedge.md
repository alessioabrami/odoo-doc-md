# Salt Edge — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ponto.html "Ponto") |
  * [precedente](../bank_synchronization.html "Sincronizzazione bancaria") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Conti bancari e di cassa](../../bank.html) »
  * [Sincronizzazione bancaria](../bank_synchronization.html) »
  * Salt Edge



# Salt Edge¶

**Salt Edge** è un fornitore di terze parti che aggrega le informazioni bancarie dai vostri conti bancari. Supporta circa 5000 istituti in più di 50 Paesi.

Odoo può sincronizzarsi direttamente con la vostra banca per importare automaticamente tutti gli estratti conto nel vostro database.

Vedi anche

  * ../sincronizzazione bancaria

  * ../transazioni




## Configurazione¶

### Collegamento dei conti bancari con Odoo¶

  1. Avviare la sincronizzazione facendo clic su :menuselezione:`Contabilità --> Configurazione --> Aggiungi un conto bancario`.

  2. Selezionare l’istituzione che si desidera sincronizzare. È possibile vedere se Salt Edge è il fornitore di terze parti dell’istituto selezionandolo.

  3. Dopo aver fornito il numero di telefono, viene richiesto un indirizzo e-mail. Questo indirizzo e-mail viene utilizzato per creare il proprio account Salt Edge. Assicuratevi di inserire un indirizzo e-mail valido, altrimenti non potrete accedere al vostro account Salt Edge.

  4. Dopo aver inserito l’indirizzo e-mail, si viene reindirizzati a Salt Edge per continuare il processo di sincronizzazione.

  5. Assicuratevi di dare il vostro consenso selezionando la casella di controllo del consenso.

  6. Completa la sincronizzazione seguendo i passi descritti di seguito.




### Aggiornare le credenziali¶

Per aggiornare le credenziali di Salt Edge o modificare le impostazioni di sincronizzazione, attiva la [modalità sviluppatore](../../../../general/developer_mode.html#developer-mode), vai su Contabilità ‣ Configurazione ‣ Sincronizzazione online e seleziona l’istituto di cui vuoi aggiornare le credenziali. Fai clic su Aggiorna credenziali per avviare il flusso e seguire gli step.

Non dimenticare di spuntare la casella per il consenso. In caso contrario, Odoo potrebbe non essere in grado di accedere alle tue informazioni.

### Recupera nuovi account¶

Per aggiungere nuovi conti online al collegamento, attiva la [modalità sviluppatore](../../../../general/developer_mode.html#developer-mode), accedi all’app Contabilità ‣ Configurazione ‣ Sincronizzazione online e seleziona l’istituto da cui desideri recuperare gli altri conti. Fai clic su Recupera conti per avviare il flusso.

Nota

Non dimenticare di spuntare la casella per il consenso. In caso contrario, Odoo potrebbe non essere in grado di accedere alle tue informazioni.

## FAQ¶

### Errore durante l’eliminazione della sincronizzazione con Odoo¶

Odoo non può eliminare definitivamente il collegamento creato con l’istituto bancario. Tuttavia, può revocare il consenso dato in modo che Odoo non sia più in grado di accedere al conto. L’errore che vedi è probabilmente un messaggio che conferma la revoca dell consenso ma non l’eliminazione del record perché esiste ancora all’interno di Salt Edge. Se desideri rimuovere completamente il collegamento, accedi al tuo account [Salt Edge](https://www.saltedge.com/dashboard) e cancella manualmente la sincronizzazione. Una volta completata l’operazione, potrai tornare su Odoo per cancellare il record.

### Errore conto già sincronizzato¶

Probabilmente hai già sincronizzato il tuo conto bancario con Salt Edge, controlla la [dashboard](https://www.saltedge.com/dashboard) e assicurati di non avere già una connessione con le stesse credenziali.

Se nella dashboard di Salt Edge è già presente una sincronizzazione con le stesse credenziali e questa sincronizzazione non è stata creata con Odoo, eliminala e creala dal database di Odoo.

Se già disponi di un collegamento con le stesse credenziali presenti nella dashboard Salt Edge creato con Odoo, attiva la [modalità sviluppatore](../../../../general/developer_mode.html#developer-mode), apri l’app Contabilità ‣ Configurazione ‣ Sincronizzazione online e fai clic su Aggiorna credenziali per riattivare il collegamento.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/bank/bank_synchronization/saltedge.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ponto.html "Ponto") |
  * [precedente](../bank_synchronization.html "Sincronizzazione bancaria") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Conti bancari e di cassa](../../bank.html) »
  * [Sincronizzazione bancaria](../bank_synchronization.html) »
  * Salt Edge


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