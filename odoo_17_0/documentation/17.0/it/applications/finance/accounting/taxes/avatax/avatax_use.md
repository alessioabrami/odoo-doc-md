# Utilizzare AvaTax — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avalara_portal.html "Portale Avalara \(Avatax\)") |
  * [precedente](../avatax.html "Integrazione AvaTax") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Imposte](../../taxes.html) »
  * [Integrazione AvaTax](../avatax.html) »
  * Utilizzare AvaTax



# Utilizzare AvaTax¶

AvaTax è un software di calcolo delle imposte che può essere integrato con Odoo negli Stati Uniti e in Canada. Una volta completata la [configurazione dell’integrazione](../avatax.html), le imposte calcolate sono facili da utilizzare e automatiche.

## Calcolare le imposte¶

Calcola automaticamente le imposte sui preventivi e sulle fatture di Odoo con AvaTax, confermando i documenti durante il flusso delle vendite. In alternativa, è possibile calcolare le imposte manualmente facendo clic sul pulsante Calcola imposte, mentre i documenti sono in fase di bozza.

Suggerimento

Facendo clic sul pulsante Calcola imposte, le imposte verranno ricalcolate se vengono modificate le righe prodotto presenti sulla fattura.

Il calcolo delle imposte viene attivato con un trigger automatico e manuale nelle seguenti circostanze.

### Trigger automatici¶

  * Quando il rappresentante delle vendite invia il preventivo via e-mail tramite il pulsante Invia tramite e-mail (pop-up).

  * Quando il cliente visualizza il preventivo online sul portale.

  * Quando un preventivo viene confermato e diventa ordine di vendita.

  * Quando il cliente visualizza la fattura sul portale.

  * Quando viene convalidata una fattura in bozza.

  * Quando il cliente visualizza l’abbonamento nel portale.

  * Quando un abbonamento genera una fattura.

  * Quando il cliente accede alla schermata di pagamento sull’e-commerce.




### Trigger manuali¶

  * Il pulsante Calcola imposte in fondo al preventivo.

  * Il pulsante Calcola imposte nella parte alta della fattura.




Usa i pulsanti per ricalcolare manualmente le imposte relative alle vendite.

Suggerimento

Usa il campo Codice partner Avalara disponibile sui record del cliente, preventivi e fatture per confrontare i dati tra Odoo e Avalara. Questo campo si trova sotto la scheda Altre info dell’ordine di vendita o del preventivo nella sezione Vendite.

Sul record del cliente, accedi all’app _Contatti_ e seleziona un contatto. In seguito, apri la scheda Vendite e acquisti e il Codice partner Avalara nella sezione Vendite.

Importante

La posizione di bilancio Mappatura imposte automatica (AvaTax) viene applicata anche ai documenti Odoo come gli abbonamenti.

Vedi anche

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../fiscal_positions.html)




## Sincronizzazione AvaTax¶

La sincronizzazione avviene con AvaTax, quando la _fattura_ viene creata in Odoo. Ciò significa che l’imposta sulle vendite viene registrata con Avalara (sviluppatore del software AvaTax).

Per farlo, accedi all’app Vendite ‣ Ordini ‣ Preventivi. Seleziona un preventivo dall’elenco.

Dopo aver confermato un preventivo e aver convalidato la consegna, fai clic su Crea fattura. Indica se si tratta di una Fattura regolare, di un Acconto (percentuale) o di un Acconto (importo fisso).

Successivamente, fai clic su Crea e visualizza fattura. Le imposte registrate possono essere visualizzate nella scheda Movimenti contabili della fattura. Saranno disponibili varie imposte a seconda della posizione dell” Indirizzo di consegna.

Infine, fai clic sul pulsante Conferma per completare la fattura e avviare la sincronizzazione con il portale AvaTax.

Avvertimento

Non è possibile reimpostare a bozza una fattura perché questo causa l’annullamento della sincronizzazione con il portale AvaTax. Al contrario, fai clic su Aggiungi nota di credito e indica: `Sinc con portale AvaTx`. Consulta la documentazione: [Note di credito e rimborsi](../../customer_invoices/credit_notes.html).

## Sconti prezzo fisso¶

Aggiungi uno sconto a prezzo fisso a un cliente di valore, facendo clic su Aggiungi riga sulla fattura del cliente. Aggiungi lo sconto sul prodotto e configura il Prezzo su un valore positivo o negativo. Per ricalcolare le imposte, fai clic su Calcola imposte.

Suggerimento

Il calcolo delle imposte può essere effettuato anche su subtotali negativi e note di credito.

## Registrazione¶

È possibile registrare le azioni di Avalara/_AvaTax_ in Odoo per ulteriori analisi o verifiche di funzionalità. La registrazione è accessibile attraverso le impostazioni di _AvaTax_.

Per iniziare a registrare le azioni di _AvaTax_ , accedi all’app Contabilità ‣ Configurazione ‣ Impostazioni.

Successivamente, nella sezione Imposte, nelle impostazioni AvaTax, fai clic su Avvia registrazione per 30 minuti.

All’avvio del processo di registrazione, Odoo registrerà tutte le azioni di Avalara/_AvaTax_ eseguite nel database.

Per visualizzare i registri, fai clic su Mostra registrazioni a destra di Avvia registrazione per 30 minuti. In questo modo otterrai un elenco dettagliato delle azioni di Avalara/_AvaTax_. L’elenco è ordinabile in base alle seguenti colonne:

  * Creato il: l’orario del calcolo _AvaTax_.

  * Creato da: valore numerico dell’utente nel database.

  * Nome database: nome del database.

  * Tipo: per questo campo è possibile scegliere due valori, Server o Client.

  * Nome: nome di servizio di Avalara. In questo caso, sarà _AvaTax_.

  * Livello: sarà `INFO` per impostazione predefinita.

  * Percorso: indica il percorso seguito per fare il calcolo.

  * Riga: indica la riga sui cui è stato eseguito il calcolo.

  * Funzione: indica il calcolo utilizzato sulla riga.




Fai clic sulla riga di registrazione per svelare un altro campo chiamato Messaggio.

Il campo popola una trascrizione della transazione che comporta la creazione (o la rettifica) di una fattura di vendita utilizzando l’API _AvaTax_ Avalara.

La transazione include dettagli, come gli indirizzi di spedizione da e verso, le voci che descrivono i prodotti o i servizi, i codici fiscali, gli importi delle imposte e altre informazioni rilevanti.

Il Messaggio contiene le imposte calcolate per varie giurisdizioni e conferma la creazione (o rettifica) della transazione.

Suggerimento

È possibile creare campi personalizzati utilizzando Odoo _Studio_. Fai clic sul __(ellipsis) menu all’estremità destra della riga di intestazione. In seguito, fai clic su __ Aggiungi campo personalizzato. Si aprirà Odoo _Studio_.

Importante

Odoo _Studio_ richiede un piano tariffario _personalizzato_. Consulta il Customer Success Manager del database per aver più informazioni sul passaggio da un piano all’altro. Consulta la documentazione: [Studio](../../../../studio.html).

Vedi anche

  * [Integrazione AvaTax](../avatax.html)

  * [Portale Avalara (Avatax)](avalara_portal.html)

  * [Conformità imposte USA: video e-learning Avatax](https://www.odoo.com/slides/slide/us-tax-compliance-avatax-2858?fullscreen=1)

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../fiscal_positions.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/taxes/avatax/avatax_use.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avalara_portal.html "Portale Avalara \(Avatax\)") |
  * [precedente](../avatax.html "Integrazione AvaTax") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Imposte](../../taxes.html) »
  * [Integrazione AvaTax](../avatax.html) »
  * Utilizzare AvaTax


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