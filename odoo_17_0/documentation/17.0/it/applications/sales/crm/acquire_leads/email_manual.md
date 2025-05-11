# Creare lead (da e-mail o manualmente) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](send_quotes.html "Creare e inviare preventivi") |
  * [precedente](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare lead (da e-mail o manualmente)



# Creare lead (da e-mail o manualmente)¶

Oltre ai lead e opportunità creati nell’app attraverso un [modulo di contatto sul sito web](opportunities_form.html), è possibile aggiungere lead al _CRM_ da alias e-mail personalizzati e tramite la creazione manuale di nuovi record.

Per prima cosa, assicurati che le impostazioni relative ai _lead_ siano attivate nel database. Apri l’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. Infine, fai clic su Salva.

## Configurare alias delle email¶

Ogni team di vendita ha la possibilità di creare e utilizzare il proprio alias e-mail. Quando si inviano messaggi a questo indirizzo, viene creato un lead (od opportunità) con le informazioni contenute nel messaggio.

Per creare o aggiornare gli alias e-mail di un team di vendita, apri l’app CRM ‣ Configurazione ‣ Team vendite. Fai clic su un team dall’elenco che si apre per accedere alla pagina con i dettagli.

Nel campo Alias e-mail, inserisci un nome per l’alias e-mail o modifica il nome esistente. Nel campo Accetta e-mail da, utilizza il menu a discesa per scegliere chi può inviare messaggi a questo alias e-mail:

  * Tutti: i messaggi vengono accettati da qualsiasi indirizzo e-mail

  * Partner autenticati: accetta solo i messaggi provenienti da indirizzi e-mail associati al record di un partner (contatto o cliente)

  * Solo follower: accetta solo i messaggi di coloro che stanno seguendo un record relativo al team, come un lead o un’opportunità. I messaggi vengono accettati anche dai membri del team

  * Dipendenti autenticati: accetta solo i messaggi provenienti da indirizzi e-mail collegati a un record dell’applicazione _Dipendenti_




### Lead creati da e-mail¶

I contatti creati dai messaggi di alias e-mail possono essere visualizzati accedendo all’app CRM ‣ Lead. Fai clic su un lead dall’elenco per aprirlo e visualizzarne i dettagli.

L’e-mail ricevuta dall’alias viene aggiunta al thread del _chatter_ per il lead. L’oggetto del messaggio viene aggiunto al campo titolo e il campo E-mail viene aggiornato con l’indirizzo e-mail del contatto.

Nota

Se la funzione _lead_ **non** è abilitata nel database, i messaggi all’alias e-mail vengono aggiunti al database come opportunità.

Vedi anche

[Comunicazione in Odoo via e-mail](../../../general/email_communication.html)

## Creare lead manualmente¶

I lead possono essere aggiunti direttamente all’applicazione _CRM_ creando manualmente un nuovo record. Apri l’app CRM ‣ Lead per visualizzare un elenco di lead esistenti.

Suggerimento

È possibile aggiungere lead anche tramite il pulsante [Genera lead](lead_mining.html).

Nella parte in alto a sinistra dell’elenco, fai clic su Nuovo per aprire un modulo Lead vuoto.

Nel primo campo del nuovo modulo, inserisci un titolo per il nuovo lead. In seguito, inserisci un Nome contatto e un Nome azienda.

Nota

Se un lead [viene convertito in opportunità](convert.html), il campo Nome azienda viene utilizzato per collegare l’opportunità a un cliente esistente o per creare un nuovo cliente.

### Creare opportunità manualmente¶

Per creare manualmente un’opportunità, apri l’applicazione CRM ‣ Vendite ‣ La mia pipeline. In alto a sinistra della pagina, fai clic su Nuova per creare una nuova opportunità sotto forma di scheda Kanban. Nel campo Organizzazione/Contatto, inserisci il nome dell’azienda per cui è stata creata l’opportunità.

Scegli un nome e inseriscilo nel campo Opportunità. _Si tratta di un campo obbligatorio_. Quando si crea manualmente un’opportunità, è utile aggiungere un nome che si riferisca ai dettagli dell’opportunità.

Example

Nell’esempio che segue, l’opportunità viene denominata “5 sedie VP”. Questo identifica il prodotto a cui il cliente è interessato e il numero potenziale di prodotti.

Inserisci le informazioni di contatto per l’opportunità nei campi E-mail e Telefono.

Nel campo Ricavi previsti inserisci un valore stimato per l’opportunità.

Nota

Le informazioni contenute nei campi Ricavi previsti e priorità possono essere utilizzate per monitorare le prestazioni dei singoli addetti alle vendite e dei team. Per ulteriori informazioni, consulta le sezioni [Resoconto ricavi previsti](../performance/expected_revenue_report.html) e [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html).

Quindi, utilizza le icone __(stella) per assegnare una priorità.

  * ______: priorità bassa

  * ______: priorità media

  * ______: priorità alta

  * ______: priorità altissima




Nota

L’assegnazione di una priorità cambia l’ordine dei lead nella vista Kanban: i lead con priorità alta vengono visualizzati per primi.

Una volta inserite tutte le informazioni necessarie, fai clic su Aggiungi.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/acquire_leads/email_manual.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](send_quotes.html "Creare e inviare preventivi") |
  * [precedente](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare lead (da e-mail o manualmente)


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto