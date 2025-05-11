# Visualizzazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](models_modules_apps.html "Modelli, moduli e app") |
  * [precedente](fields.html "Campi e widget") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Visualizzazioni



# Visualizzazioni¶

Le viste sono le interfacce che permettono di visualizzare i dati contenuti in un [modello](models_modules_apps.html). Un modello può avere varie viste o più semplicemente vari modi di mostrare gli stessi dati. In Studio, le viste sono organizzate in quattro categorie: generale, più record, linea del tempo e reportistica.

Suggerimento

  * Per modificare la vista predefinita di un modello, [accedi a Studio](../studio.html#studio-access), vai su Viste, fai clic sull’icona __( ellissi) accanto alla vista desiderata e fai clicc su Imposta come predefinita.

  * È possibile modificare le viste utilizzando l’editor XML integrato. Attiva la [Modalità sviluppatore](../general/developer_mode.html#developer-mode), vai sulla vista che vuoi modificare, apri la finestra Vista e fai clic su </> XML.

Importante

Se modifichi una vista utilizzando l’editor XML, evita di apportare modifiche direttamente alle viste standard ed ereditate, poiché queste verrebbero azzerate e perse durante gli aggiornamenti o gli upgrade dei moduli. Assicurati sempre di selezionare le viste corrette ereditate da Studio: quando modifichi una vista in Studio trascinando e rilasciando un nuovo campo, ad esempio, viene generata automaticamente una specifica vista ereditata da Studio e il relativo XPath, che definisce la parte modificata della vista.




## Viste generali¶

Nota

Le impostazioni descritte di seguito si trovano nella scheda Vista della vista stessa tranne se specificato altrove.

### Modulo¶

La vista Modulo __viene utilizzata per creare e modificare record come contatti, ordini di vendita, prodotti, ecc.

  * Per strutturare un modulo, trascina e rilascia l’elemento Schede e colonne che trovi nella sezione \+ Aggiungi.

  * Per evitare che gli utenti creino, modifichino o eliminino record, deseleziona le opzioni Può creare, Può modificare o Può eliminare.

  * Per aggiungere un pulsante, fai clic su Aggiungi pulsante nella parte alta del modulo, inserisci un”Etichetta e seleziona l’azione del pulsante:

    * Esegui azione server: seleziona un”[azione server](../../developer/reference/backend/actions.html#reference-actions-server) da eseguire dal menu a tendina;

    * Chiama un metodo: specifica qualsiasi metodo Python esistente già definito in Odoo.

  * To add a smart button, click the __( plus) icon in the top-right corner of the form. Enter a Label, choose an Icon, and select a [related field](fields.html#studio-fields-relational-fields-related-field).




Example

### Attività¶

La vista Attività __viene utilizzata per programmare e avere una panoramica di tutte le attività (e-mail, chiamate, ecc.) collegate ai record.

Nota

Questa vista può essere modificata solo con Studio modificando il codice XML.

Example

### Ricerca¶

La vista Cerca __viene aggiunta su altre viste per filtrare, raggruppare e cercare record.

  * Per aggiungere Filtri personalizzati e dare loro una struttura utilizzando dei Separatori, apri la sezione \+ Aggiungi e trascinali e rilasciali nella sezione Filtri.

  * Per aggiungere un campo esistente nel menu a tendina di ricerca, vai nella sezione \+ Aggiungi e trascinalo e rilascialo nella sezione Campi con autocompletamento.




Example

## Viste record multipli¶

Nota

Le impostazioni descritte di seguito si trovano nella scheda Vista della vista stessa tranne se specificato altrove.

### kanban¶

La vista Kanban __viene spesso utilizzata per supportare i flussi aziendali spostando i record tra le varie fasi o come modo alternativo per visualizzare i record all’interno di _carte_.

Nota

Se la vista Kanban esiste, viene utilizzata per impostazione predefinita per mostrare dati su dispositivi mobili al posto della vista elenco.

  * Per impedire agli utenti di creare nuovi record, deseleziona Può creare.

  * Per creare record direttamente dalla vista, in modo minimalistico, abilita l’opzione Creazione rapida.

  * Per impostare un raggruppamento predefinito per i record, seleziona un campo nella sezione Raggruppamento predefinito per.




Example

### Elenco¶

La vista Elenco __viene utilizzata per avere una panoramica di più record alla volta, controllarli e modificarli.

  * Per evitare che gli utenti creino, modifichino o eliminino record, deseleziona le opzioni Può creare, Può modificare o Può eliminare.

  * Per creare e modificare record direttamente dalla vista, seleziona Aggiungi record in basso, Aggiungi record in alto oppure Apri vista scheda sotto Quando crei un record.

Nota

Questo impedisce agli utenti di aprire record nella vista modulo dalla vista elenco.

  * Per modificare vari record insieme, spunta Abilita modifica massiva.

  * Per modificare il modo in cui i record vengono ordinati per impostazione predefinita, seleziona uno dei campi disponibili nella sezione Ordina per.

  * Per impostare un raggruppamento predefinito per i record, seleziona un campo nella sezione Raggruppamento predefinito per.

  * Per aggiungere un pulsante, fai clic su Aggiungi pulsante nella parte alta dell’elenco, inserisci un”Etichetta e seleziona l’azione del pulsante:

    * Esegui azione server: seleziona un”[azione server](../../developer/reference/backend/actions.html#reference-actions-server) da eseguire dal menu a tendina;

    * Chiama un metodo: specifica qualsiasi metodo Python esistente già definito in Odoo.




Suggerimento

To add a __( drag handle) icon to reorder records manually, add an [Integer field](fields.html#studio-fields-simple-fields-integer) with the Handle widget.

Example

### Mappa¶

La vista Mappa __viene utilizzata per mostrare i record su una mappa. Ad esempio, viene utilizzata nell’app Assistenza sul campo per pianificare l’itinerario tra vari lavori.

Nota

A [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Contact_ model is required to activate the view, as the contact address is used to position records on the map.

  * Per scegliere quale tipo di contatto bisogna usare sulla mappa, selezionalo nel campo Contatto.

  * Per nascondere il nome o l’indirizzo del record, spunta Nascondi nome o Nascondi indirizzo.

  * Per aggiungere informazioni da altri campi, selezionale nei Campi aggiuntivi.

  * Per avere un suggerimento di percorso tra i vari record, spunta Abilita itinerario e scegli quale campo dovrebbe essere usato per ordinare i record per il percorso.




Example

## Viste sequenza temporale¶

Nota

  * When you first activate one of the timeline views, you need to select which [Date](fields.html#studio-fields-simple-fields-date) or [Date & Time](fields.html#studio-fields-simple-fields-date-time) fields on your model should be used to define when the records start and stop in order to display them on the view. You can modify the Start Date Field and Stop Date Field after activating the view.

  * Le impostazioni descritte di seguito si trovano nella scheda Vista della vista stessa tranne se specificato altrove.




### Calendario¶

La vista Calendario __viene utilizzata per avere una panoramica e gestire i record in un calendario.

  * Per creare record direttamente dalla vista invece di aprire la Vista modulo, attiva l’opzione Creazione rapida.

Nota

Questo funziona solo su modelli specifici che possono essere _creati rapidamente_ utilizzando solo un _nome_. Tuttavia, la maggior parte dei modelli non supportano la creazione rapida ed è necessario aprire la vista Modulo per completare i campi richiesti.

  * Per colorare i record sul calendario, seleziona un campo nella sezione Colore. Tutti i record che condividono lo stesso valore per quel campo vengono mostrati utilizzando lo stesso colore.

Nota

Dato che il numero di colori è limitato, lo stesso colore potrebbe essere assegnato a più valori.

  * To display events lasting the whole day at the top of the calendar, select a [Checkbox field](fields.html#studio-fields-simple-fields-checkbox) that specifies if the event lasts the whole day.

  * Per scegliere la scala temporale predefinita utilizzata per visualizzare gli eventi, seleziona Giorno, Settimana, Mese o Anno nella sezione Modalità di visualizzazione predefinita.




Nota

You can also use a Delay Field to display the duration of the event in hours by selecting a [Decimal](fields.html#studio-fields-simple-fields-decimal) or [Integer](fields.html#studio-fields-simple-fields-integer) field on the model which specifies the duration of the event. However, if you set an End Date Field, the Delay Field will not be taken into account.

Example

### Coorte¶

La vista Coorte :icon:`oi-view-cohort`z viene utilizzata per esaminare il ciclo di vita dei record in un periodo di tempo specifico. Ad esempio, viene utilizzata nell’app Abbonamenti per mostrare il tasso di ritenzione degli abbonamenti.

  * Per visualizzare un valore (ad es. il valore aggregato di un determinato campo) sulla vista per impostazione predefinita, seleziona un campo Misura.

  * Per scegliere la fascia oraria da utilizzare di default per raggruppare i risultati, seleziona Giorno, Settimana, Mese o Anno nella sezione Intervallo.

  * Per modificare la modalità coorte, seleziona Ritenzione la percentuale di record che rimangono in un periodo di tempo, parte dal 100% e diminuisce con il passare del tempo oppure Disdetta la percentuale di record in uscita in un periodo di tempo, inizia con lo 0% e aumenta con il passare del tempo.

  * Per modifica il modo in cui la Linea del tempo avanza, seleziona sia In avanti (da 0 a +15) o Indietro (da -15 a 0). Spesso viene utilizzata l’opzione In avanti.




Example

### Gantt¶

La vista Gantt __viene utilizzata per prevedere ed esaminare l’avanzamento complessivo dei record. I record vengono rappresentati da una barra sotto una scala temporale.

  * Per evitare che gli utenti creino o modifichino record, deseleziona le opzioni Può creare o Può modificare.

  * Per riempire le celle in grigio ogni volta che un record non deve essere creato in quel punto (ad es., su week-end per i dipendenti), spunta Visualizza indisponibilità.

Nota

Il modello sottostante deve supportare questa funzionalità e non può essere fatto con Studio. È supportato per le app Progetti, Ferie, Pianificazione e Produzione.

  * Per mostrare una riga con il totale in basso, spunta Visualizza riga totali.

  * Per minimizzare più record in una sola riga, spunta Comprimi primo livello.

  * Per scegliere in che modo i record sono raggruppati nelle righe di default (ad es., per dipendente o per progetto), seleziona un campo in Raggruppa per predefinito.

  * Per definire la scala temporale predefinita per visualizzare i record, seleziona Giorno, Settimana, Mese o Anno nella sezione Scala predefinita.

  * Per colorare i record sulla vista, seleziona un campo nella sezione Colore. Tutti i record che condividono lo stesso valore per quel campo vengono mostrati utilizzando lo stesso colore.

Nota

Dato che il numero di colori è limitato, lo stesso colore potrebbe essere assegnato a più valori.

  * Per specificare con quale grado di precisione ogni scala temporale deve essere divisa per, seleziona Quarto d’ora, Mezz’ora, od Ora nel campo Precisione giorno, Mezza giornata o Giorno nel campo Precisione settimana e Precisione mese.




Example

## Viste rendiconto¶

Nota

Le impostazioni descritte di seguito si trovano nella scheda Vista della vista stessa tranne se specificato altrove.

### pivot¶

La vista Pivot __viene utilizzata per esplorare e analizzare in modo interattivo i dati contenuti nei record. Nello specifico, è utile per raggruppare dati numeri, creare categorie ed eseguire il drill-down dei dati espandendo e comprimendo diversi livelli.

  * Per accedere a tutti i record i cui dati sono raggruppati in una cella, spunta Accedi ai record dalla cella.

  * Per dividere i dati in varie categorie, seleziona uno o più campi in Raggruppamento colonne, Raggruppamento riga - Primo livello o Raggruppamento riga - Secondo livello.

  * Per aggiungere vari tipi di dati da misurare utilizzando la vista, seleziona un campo in Misure.

  * Per mostrare un numero di record che compongono i dati aggregati in una cella, spunta Mostra conteggio.




Example

### Grafico¶

La vista Grafico __viene utilizzata per illustrare i dati dei record in una grafico a barre, righe o a torta.

  * Per modificare il grafico predefinito, seleziona Barra, Riga o Torta sotto Tipo.

  * Per scegliere una dimensione dati predefinita (categoria), seleziona un campo sotto Prima dimensione e se necessario, un altro per Seconda dimensione.

  * Per selezionare un tipo di dati predefinito da misurare utilizzando la vista, seleziona un campo in Misura.

  * _Solo per grafici a barre e righe_ : per ordinare le varie categorie di dati in base ai valori, seleziona Crescente (dal più basso al più alto) o Decrescente (dal più alto al più basso) nella sezione Ordinamento.

  * _Solo per grafici a barre e a torta_ : per accedere a tutti i record i cui dati sono raggruppati in una categoria del grafico, spunta Accedi ai record dal grafico.

  * _Solo per grafici a barre_ : quando usi due dimensioni di dati (categorie), mostra le due colonne una sopra all’altra di default spuntando Grafico impilato.




Example

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/studio/views.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](models_modules_apps.html "Modelli, moduli e app") |
  * [precedente](fields.html "Campi e widget") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Visualizzazioni


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