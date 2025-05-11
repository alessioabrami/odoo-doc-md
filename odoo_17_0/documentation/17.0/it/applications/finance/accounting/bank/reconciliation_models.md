# Modelli di riconciliazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](foreign_currency.html "Gestire un conto bancario in una valuta straniera") |
  * [precedente](reconciliation.html "Riconciliazione bancaria") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Modelli di riconciliazione



# Modelli di riconciliazione¶

I modelli di riconciliazione vengono utilizzati per automatizzare il processo di [riconciliazione bancaria](reconciliation.html), molto utile quando si ha a che fare con registrazioni ricorrenti come spese bancarie. I modelli di riconciliazione possono essere utili anche per gestire [sconti di cassa](../customer_invoices/cash_discounts.html).

Ogni modello viene creato in base a un tipo di modello e alle condizioni della transazione bancaria.

Vedi anche

  * [Sincronizzazione bancaria](bank_synchronization.html)

  * [Tutorial Odoo: Modelli di riconciliazione](https://www.odoo.com/slides/slide/reconciliation-models-1841?fullscreen=1)




## Tipi di modelli di riconciliazione¶

È possibile accedere ai modelli di riconciliazione dall’app Contabilità ‣ Configurazione ‣ Banca: Modelli di riconciliazione. Per ogni modello di riconciliazione, è necessario configurare un Tipo. Esistono tre tipi di modelli:

  * Pulsante per generare la voce di controparte: viene creato un pulsante nella sezione delle voci risultanti della vista di riconciliazione bancaria. Se fai clic su questo pulsante, si genera una voce di contropartita da riconciliare con la transazione attiva in base alle regole impostate nel modello. Le regole specificate nel modello determinano i conti, gli importi, le etichette e la distribuzione analitica della voce di contropartita

  * Regola per suggerire la voce di contropartita: utilizzata per le transazioni ricorrenti per abbinare la transazione a una nuova voce in base a condizioni che devono corrispondere alle informazioni della transazione

  * Regola per abbinare fatture cliente/fornitore: utilizzata per le transazioni ricorrenti per abbinare la transazione a fatture cliente e fornitore o pagamenti esistenti in base a condizioni che devono corrispondere alle informazioni della transazione.




## Modelli di riconciliazione predefiniti¶

In Odoo, sono disponibili vari modelli preconfigurati, in base alla localizzazione fiscale dell’azienda. È possibile aggiornarli se necessario. Gli utenti possono anche creare i propri modelli di riconciliazione facendo clic su Nuovo.

Importante

Se un record corrisponde a vari modelli di riconciliazione, verrà applicato il primo nella _sequenza_ dei modelli. Puoi riorganizzare l’ordine trascinando e rilasciando la maniglia accanto al nome.

### Corrispondenza perfetta fatture clienti/fornitori¶

Il modello dovrebbe essere il primo della _sequenza_ in quanto attiva la funzione di suggerimento dell’abbinamento di fatture cliente o fornitore esistenti con una transazione bancaria in base a determinate condizioni.

Odoo riconcilia automaticamente il pagamento quando viene selezionata l’opzione di Validazione automatica e le condizioni del modello vengono rispettate. In questo caso, il software si aspetta di trovare il riferimento della fattura o del pagamento sulla riga dell’estratto conto (una volta selezionata la voce Etichetta) e il nome del partner (se il campo Partner selezionato è stato selezionato) per suggerire la voce di contropartita corretta e riconciliare il pagamento automaticamente.

### Corrispondenza parziale fatture clienti/fornitori se sottopagate¶

Questo modello suggerisce una fattura cliente o fornitore che corrisponde parzialmente al pagamento quando l’importo ricevuto è leggermente inferiore all’importo della fattura, come nel caso di **sconti di cassa**. La differenza viene riconciliata con il conto indicato nella scheda voce della controparte.

Il Tipo del modello di riconciliazione è Regola per abbinare fatture ed è necessario impostare anche la Tolleranza di pagamento.

Nota

La Tolleranza di pagamento viene applicata solamente a pagamenti più piccoli. Non viene presa in considerazione quando si riceve un sovra pagamento.

Vedi anche

[Sconti di cassa e riduzioni fiscali](../customer_invoices/cash_discounts.html)

### Riga commissioni bancarie¶

Questo modello suggerisce una voce di controparte secondo le regole configurate per il modello. In questo caso, il Tipo del modello di riconciliazione è Regola per suggerire la voce della controparte e la Etichetta può essere utilizzata per identificare le informazioni che si riferiscono alle Commissioni bancarie nell’etichetta della transazione.

Nota

Le [espressioni regolari](https://regexone.com/), spesso abbreviate come **Regex** , possono essere utilizzate in Odoo in vari modi per cercare, convalidare e manipolare i dati nel sistema. Le regex possono essere potenti ma anche complicate quindi è necessario utilizzare saggiamente e con una buona conoscenza degli schemi con cui si lavora.

Per utilizzare le espressioni regolari nei modelli di riconciliazione, imposta il Tipo di transazione su Corrisponde a espressione regolare e aggiungi la tua espressione. Odoo recupera automaticamente le transazioni che corrispondono alla tua Regex e le condizioni specificate nel modello.

## Mappatura partner¶

La mappatura dei partner consente di stabilire regole per abbinare automaticamente le transazioni al conto partner corretto, risparmiando tempo e riducendo il rischio di errori che possono verificarsi durante la riconciliazione manuale. Ad esempio, è possibile creare una regola di mappatura dei partner per i pagamenti in entrata con numeri di riferimento specifici o parole chiave nella descrizione della transazione. Quando un pagamento in entrata soddisfa questi criteri, Odoo lo mappa automaticamente sul conto del cliente corrispondente.

Per creare una regola mappatura partner, apri la scheda Mappatura partner e riempi i campi Trova testo in etichetta, Trova testo nelle note e Partner.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/bank/reconciliation_models.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](foreign_currency.html "Gestire un conto bancario in una valuta straniera") |
  * [precedente](reconciliation.html "Riconciliazione bancaria") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Modelli di riconciliazione


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