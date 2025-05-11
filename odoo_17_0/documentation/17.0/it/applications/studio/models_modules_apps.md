# Modelli, moduli e app — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automated_actions.html "Regole di automazione") |
  * [precedente](views.html "Visualizzazioni") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Modelli, moduli e app



# Modelli, moduli e app¶

I modelli determinano la struttura logica di un database e come i dati vengono salvati, organizzati e manipolati. In altre parole, un modello è una tabella di informazioni che possono essere collegate ad altre tabelle. Di solito, un modello rappresenta un concetto di business come _ordini di vendita_ , _contatti_ o _prodotti_.

I moduli e le app contengono vari elementi come modelli, viste, file di dati, controller web e dati web statici.

Nota

Tutte le applicazioni sono moduli. I moduli più grandi e indipendenti vengono chiamati app mentre altri moduli rappresentano componenti aggiuntivi delle stesse app.

## Funzionalità consigliate¶

Quando crei un nuovo modello o una nuova app con Studio, puoi scegliere di aggiungere fino a 14 funzionalità per velocizzare il processo di creazione. Tali funzionalità legano campi, impostazioni predefinite e viste che di solito vengono utilizzati insieme per fornire alcune funzioni standard. La maggior parte delle funzioni possono essere aggiunte in seguito ma se fatto all’inizio, il processo di creazione del modello sarà più semplice. Inoltre, le funzioni interagiscono tra di loro, in alcuni casi, per aumentare l’utilità.

Example

La creazione di un modello con le funzionalità Immagine e Fasi del flusso attivate, comporta l’aggiunta dell’immagine nel layout della scheda della [vista Kanban](views.html#studio-views-multiple-records-kanban).

### Dettagli contatto¶

Selecting Contact details adds to the [Form view](views.html#studio-views-general-form) a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Contact_ model and two of its [Related Fields](fields.html#studio-fields-relational-fields-related-field): Phone and Email. The Contact field is also added to the [List view](views.html#studio-views-multiple-records-list), and the [Map view](views.html#studio-views-multiple-records-map) is activated.

Example

### Assegnazione utente¶

Selecting User assignment adds to the [Form view](views.html#studio-views-general-form) a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Contact_ model, with the following Domain: `Share User is not set` to only allow the selection of _Internal Users_. In addition, the many2one_avatar_user widget is used to display the user’s avatar. The Responsible field is also added to the [List view](views.html#studio-views-multiple-records-list).

Example

### Data e calendario¶

Selecting Date & Calendar adds to the [Form view](views.html#studio-views-general-form) a [Date field](fields.html#studio-fields-simple-fields-date) and activates the [Calendar view](views.html#studio-views-timeline-calendar).

### Intervallo date e Gantt¶

Selecting Date range & Gantt adds to the [Form view](views.html#studio-views-general-form) two [Date fields](fields.html#studio-fields-simple-fields-date) next to each other: one to set a start date, the other to set an end date, using the daterange widget, and activates the [Gantt view](views.html#studio-views-timeline-gantt).

### Fasi del flusso¶

Selecting Pipeline stages activates the [Kanban view](views.html#studio-views-multiple-records-kanban), adds several fields such as [Priority](fields.html#studio-fields-simple-fields-priority) and Kanban State, and three stages: New, In Progress, and Done. The Pipeline status bar and the Kanban State field are added to the [Form view](views.html#studio-views-general-form). The Color field is added to the [List view](views.html#studio-views-multiple-records-list).

Nota

La funzionalità Fasi del flusso può essere aggiunta anche più tardi.

### Etichette¶

Selecting Tags adds to the [Modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Tags field](fields.html#studio-fields-relational-fields-tags), creating a _Tag_ model with preconfigured access rights in the process.

### Immagine¶

Selecting Picture adds to the top-right of the [Form view](views.html#studio-views-general-form) an [Image field](fields.html#studio-fields-simple-fields-image).

Nota

La funzionalità Immagine può essere aggiunta anche in seguito.

### Righe¶

Selecting Lines: adds to the [Form view](views.html#studio-views-general-form) a [Lines field](fields.html#studio-fields-relational-fields-lines) inside a Tab component.

### Note¶

Selecting Notes adds to the [Form view](views.html#studio-views-general-form) an [Html field](fields.html#studio-fields-simple-fields-html) using the full width of the form.

### Valore monetario¶

Selecting Monetary value adds to the [Modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Monetary field](fields.html#studio-fields-simple-fields-monetary). The [Grafico](views.html#studio-views-reporting-graph) and [pivot](views.html#studio-views-reporting-pivot) views are also activated.

Nota

Il campo _Valuta_ viene aggiunto e nascosto nella vista.

### Azienda¶

Selecting Company adds to the [Modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Company_ model.

Nota

Utile solo se lavori in un ambiente con più aziende.

### Ordinamento personalizzato¶

Se selezioni Ordinamento personalizzato, alla [vista elenco](views.html#studio-views-multiple-records-list) verrà aggiunta un’icona per riordinare manualmente i record.

Example

### Chatter¶

Selezionando Chatter, alla [vista modulo](views.html#studio-views-general-form) verranno aggiunte le funzionalità del chatter (inviare messaggi, registrare note e programmare attività).

Nota

La funzionalità Chatter può essere aggiunta anche in seguito.

Example

### Archiviazione¶

Se selezioni Archiviazione, alle viste [Modulo](views.html#studio-views-general-form) ed [Elenco](views.html#studio-views-multiple-records-list) verrà aggiunta l’azione Archivia e i record archiviati verranno nascosti dalle ricerche e dalle viste.

## Esportare e importare personalizzazioni¶

Quando realizzi una personalizzazione con Studio, al tuo database viene aggiunto un nuovo modulo chiamato Personalizzazioni Studio,

Per esportare le personalizzazioni, vai su Dashboard principale ‣ Studio ‣ Personalizzazioni ‣ Esporta per scaricare un file ZIP contenente tutte le personalizzazioni.

Per importare e installare le personalizzazioni in un altro database, collegati al database di destinazione e vai su Dashboard principale ‣ Studio ‣ Personalizzazioni ‣ Importa, carica il file ZIP esportato in precedenza prima di fare clic sul pulsante Importa.

Avvertimento

Prima di eseguire l’importazione, assicurati che il database di destinazione abbia le stesse app e gli stessi moduli del database di origine. Studio non aggiunge i moduli di base come dipendenze del modulo esportato.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/studio/models_modules_apps.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automated_actions.html "Regole di automazione") |
  * [precedente](views.html "Visualizzazioni") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Modelli, moduli e app


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