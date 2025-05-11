# Utilizzare attività per i team di vendita — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_enrichment.html "Arricchimento lead") |
  * [precedente](gamification.html "Gamification CRM") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Utilizzare attività per i team di vendita



# Utilizzare attività per i team di vendita¶

Le _attività_ rappresentano operazioni di follow-up legate a un record in un database _Odoo_. Le attività possono essere programmate su qualsiasi pagina del database contenente una finestra di dialogo, una vista Kanban, una vista elenco oppure la vista attività di un’applicazione.

Attività pianificate per lead e opportunità.¶

## Tipi di attività¶

Nell’app _CRM_ è disponibile un insieme di tipi di attività. Per visualizzare l’elenco di tipi di attività disponibili, accedi all’app CRM ‣ Configurazione ‣ Tipi di attività.

Nota

Nel database sono disponibili tipi di attività aggiuntivi che possono essere utilizzati in varie applicazioni. Per accedere all’elenco completo di tipi di attività, apri il modulo Impostazioni, scorri fino alla sezione Comunicazioni e fai clic su Tipi di attività.

I tipi di attività preconfigurati per il modulo _CRM_ sono i seguenti:

>   * E-mail: aggiunge un promemoria nel chatter che invita l’addetto vendite a inviare un’e-mail.
> 
>   * Chiamata: apre un collegamento al calendario dove l’addetto vendite può pianificare quando chiamare il cliente.
> 
>   * Meeting: apre un link al calendario in cui l’addetto vendite può programmare un incontro con il contatto.
> 
>   * Da fare: aggiunge un promemoria generale su un’attività da svolgere nel chatter.
> 
>   * Carica documento: aggiunge un link all’attività in cui è possibile caricare un documento esterno. Nota che l’applicazione _Documenti_ **non** è necessaria per utilizzare questo tipo di attività.
> 
> 


Nota

Se sono installate altre applicazioni, come _Vendite_ o _Contabilità_ , altri tipi di attività sono resi disponibili nell’applicazione _CRM_.

### Creare un nuovo tipo di attività¶

Per creare un nuovo tipo di attività, fai clic su Nuovo nella parte in alto a sinistra della pagina per aprire un modulo vuoto.

Nella parte alta del modulo, inizia scegliendo un Nome per il nuovo tipo di attività.

#### Impostazioni attività¶

##### Azione¶

Il campo _Azione_ specifica lo scopo dell’attività. Alcune azioni attivano comportamenti specifici dopo la programmazione di un’attività.

  * Se selezioni Carica documento, nel chatter, all’attività pianificata verrà aggiunto direttamente un link per caricare un documento.

  * Se selezioni Chiamata oppure Incontro, gli utenti hanno la possibilità di aprire il proprio calendario per programmare l’attività stessa.

  * Se hai selezionato Richiedi firma, all’attività pianificata viene aggiunto un link che apre una finestra pop-up relativa alla richiesta di firma.




Nota

Le azioni da selezionare disponibili per un tipo di attività variano in base alle applicazioni installate nel database.

##### Utente predefinito¶

Per assegnare automaticamente l’attività ad un utente specifico quando il tipo di attività è programmato, scegli un nome dal menu a discesa Utente predefinito. Se il campo è vuoto, l’attività viene assegnata all’utente che l’ha creata.

##### Riepilogo predefinito¶

Per inserire delle note indipendentemente dalla data di creazione del tipo di attività, inseriscile nel campo Riepilogo predefinito.

Nota

Le informazioni presenti nei campi Utente predefinito e Riepilogo predefinito vengono incluse al momento della creazione di un’attività. Tuttavia, possono essere modificate prima che l’attività venga programmata o salvata.

#### Attività successiva¶

Per suggerire o avviare automaticamente una nuova attività dopo che un’altra è stata contrassegnata come completata, è necessario configurare il Tipo di concatenamento.

##### Suggerimento attività successiva¶

Nel campo Tipo di concatenamento, seleziona Suggerisci prossima attività. Dopo averlo fatto, il campo al di sotto diventa Suggerisci. Fai clic sul menu a discesa del campo Suggerisci per selezionare qualsiasi attività da consigliare come follow-up per questo tipo di attività.

Nel campo Programma, scegli un scadenza predefinita per queste attività. Per farlo, configura il numero che vuoi di Giorni, Settimane o Mesi. In seguito, scegli tra dopo la data di completamento oppure dopo la scadenza dell’attività precedente.

Le informazioni del campo Programma possono essere modificate prima della programmazione dell’attività.

Quando tutte le impostazioni sono state configurate, fai clic su Salva.

Nota

Se un’attività ha il Tipo di concatenamento configurato su Suggerisci prossima attività e presenta attività elencate nel campo Suggerisci, gli utenti vengono presentati con raccomandazioni per le attività da svolgere nelle fasi successive.

##### Avviare attività successiva¶

Se configuri il Tipo di concatenamento su Attiva attività successiva, quest’ultima verrà lanciata immediatamente una volta che la precedente viene completata.

Se selezioni Attiva attività successiva nel campo Tipo di concatenamento, il campo in basso diventa: Attiva. Dal menu a discesa del campo Attiva, seleziona l’attività che dovrebbe essere avviata una volta completata.

Nel campo Programma, scegli un scadenza predefinita per queste attività. Per farlo, configura il numero che vuoi di Giorni, Settimane o Mesi. In seguito, scegli tra dopo la data di completamento oppure dopo la scadenza dell’attività precedente.

Le informazioni del campo Programma possono essere modificate prima della programmazione dell’attività.

Quando tutte le impostazioni sono state configurate, fai clic su Salva.

Nota

Quando il Tipo di concatenamento di un’attività è configurato su Attiva attività successiva, contrassegnato l’attività come _Completata_ , l’attività immediatamente successiva elencata nel campo Attiva viene lanciata.

## Monitorare le attività¶

Per mantenere la pipeline aggiornata con la visione più accurata dello stato delle attività, non appena si interagisce con un lead, l’attività associata deve essere contrassegnata come _Completata_. In questo modo ci si assicura che l’attività successiva possa essere programmata secondo le necessità. Inoltre, si evita che la pipeline sia ingombra di attività scadute.

La pipeline è più efficace quando è aggiornata e precisa rispetto alle interazioni che sta monitorando.

## Piani attività¶

_I piani di attività_ sono sequenze preconfigurate di attività. Quando si lancia un piano di attività, ogni attività della sequenza viene programmata automaticamente.

Per creare un nuovo piano, accedi al modulo CRM ‣ Configurazione ‣ Piano attività. Fai clic su Nuovo nella parte in alto a sinistra della pagina per aprire un modulo Piani lead vuoto.

Inserisci un nome per il nuovo piano nel campo Nome piano. Nella scheda Attività da creare, fai clic su Aggiungi riga per aggiungere una nuova attività.

Seleziona un Tipo di attività dal menu a discesa. Fai clic su Cerca di più per vedere un elenco completo di tipi di attività disponibili oppure per crearne uno nuovo.

Successivamente, nel campo Riepilogo, inserisci tutti i dettagli per descrivere le specifiche dell’attività, comprese le istruzioni per il venditore o le informazioni dovute al completamento dell’attività. Il contenuto di questo campo viene incluso nell’attività programmata e può essere modificato in seguito.

Scegli una delle seguenti opzioni per il campo Assegnazione:

>   * Chiedi al lancio: le attività vengono assegnate a un utente quando il piano è stato programmato.
> 
>   * Utente predefinito: le attività vengono sempre assegnate a un utente specifico.
> 
> 


Se scegli Utente predefinito per il campo Assegnazione, scegli un utente per il campo Assegnato a.

Suggerimento

> I piani di attività possono presentare attività assegnate a utenti predefiniti e a utenti assegnati all’avvio del piano.

In seguito, configura la tempistica dell’attività. Le attività possono essere programmate prima della data del piano o dopo. Usa i campi Intervallo e Unità per impostare la scadenza dell’attività. Infine, nel campo Trigger, scegli se l’attività deve avvenire prima o dopo la data del piano.

Example

Viene creato un piano di attività per gestire i contatti ad alta priorità. In particolare, questi lead devono essere contattati rapidamente con un meeting programmato a due giorni dal primo contatto. Il piano viene configurato con le seguenti attività:

  * E-mail due giorni **prima** della data del piano

  * Meeting zero giorni **prima** della data del piano

  * Crea preventivo tre giorni **dopo** la data del piano

  * Carica documenti tre giorni **dopo** la data del piano

  * Follow-up cinque giorni **dopo** la data del piano




In questo modo si stabilisce la _data del piano_ come scadenza dell’incontro, che è l’obiettivo del piano. Prima di questa data, c’è il tempo necessario per contattare il cliente e preparare il meeting. Dopo tale data, l’addetto alle vendite ha il tempo di creare un preventivo, caricare il documento ed eseguire il follow-up.

Ripeti questi step per ogni attività inclusa nel piano.

### Lanciare un piano attività¶

Per lanciare un piano attività su un’opportunità _CRM_ , accedi al modulo CRM e fai clic sulla scheda Kanban di un’opportunità per aprirla.

Nella parte in alto a destra del chatter, fai clic su Attività per aprire una finestra pop-up Pianifica attività.

Nel campo Piano, seleziona il piano attività che vuoi lanciare. Verrà generato un Riassunto del piano che elenca le attività incluse nel piano. Seleziona una Data piano usando il popover del calendario. Questo aggiorna il Riassunto del piano con date limite basate sugli intervalli configurati sul piano attività.

Seleziona un utente nel campo Assegnato a. L’utente è assegnato a una qualsiasi delle attività del piano configurate con l’opzione Chiedi al lancio nel campo Assegnazione.

Fai clic su Pianifica.

I dettagli del piano vengono aggiunti al chatter, oltre a ciascuna attività.

Vedi anche

  * [Attività](../../../essentials/activities.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/optimize/utilize_activities.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_enrichment.html "Arricchimento lead") |
  * [precedente](gamification.html "Gamification CRM") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Utilizzare attività per i team di vendita


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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