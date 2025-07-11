# Resoconto lead di qualità — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resellers.html "Partner") |
  * [precedente](unattended_leads_report.html "Resoconto lead non seguiti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto lead di qualità



# Resoconto lead di qualità¶

Un lead _di qualità_ è un lead che probabilmente si tradurrà in una vendita. Dovrebbe corrispondere alle caratteristiche che più comunemente si ritiene aiutino i venditori a concludere un affare, oltre a criteri più precisi che sono specifici per ogni organizzazione.

Nota

I criteri specifici che definiscono un _lead di qualità_ sono diversi per ogni organizzazione. Per maggiori informazioni, consulta la sezione Definire un lead di qualità.

Un _resoconto_ sui lead di qualità confronta il numero di lead di qualità ricevuti da ciascun addetto vendite in un determinato periodo di tempo, ad esempio negli ultimi 30 giorni. I manager dei team di vendita possono utilizzare questo resoconto per prendere decisioni più informate quando assegnano nuovi lead al loro team.

Example

> Un manager elabora un resoconto sulla qualità dei lead in base ai criteri della propria azienda:
> 
>   * i lead devono includere un numero di telefono e un indirizzo e-mail.
> 
>   * L’indirizzo e-mail deve avere un dominio professionale.
> 
>   * L’origine del lead deve essere una conversazione in live chat o un appuntamento con un addetto vendite.
> 
> 


Dopo aver eseguito il resoconto, il manager può vedere che, sebbene la capacità di tutti di chiudere un affare sia variata, alcuni membri del team di vendita hanno ricevuto un numero maggiore di lead di qualità rispetto ad altri.

> Sulla base di queste informazioni, il manager può decidere di assegnare un maggior numero di lead di qualità agli addetti vendite che attualmente si trovano nella fascia più bassa, per bilanciare la distribuzione dei lead di qualità.

## Creare un resoconto sui lead di qualità¶

Per creare un resoconto sui lead di qualità, accedi al modulo CRM ‣ Rendicontazione ‣ Pipeline per aprire la dashboard Analisi pipeline. Fai clic sulla barra Cerca… nella parte superiore della pagina ed elimina qualsiasi filtro attivo.

Fai clic sull’icona 🔻(triangolo in giù) a destra della barra Cerca… per aprire il mega menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti. Fai clic su Aggiungi filtro personalizzato. Si aprirà una finestra pop-up dal nome Aggiungi filtro personalizzato.

La finestra pop-up Aggiungi filtro personalizzato permette di creare filtri più specifici.

### Aggiungere filtri personalizzati¶

Per generare un resoconto sui lead di qualità, i filtri devono essere creati rispettando le seguenti condizioni:

  * Data di inizio: limita i risultati a quelli creati in un arco temporale specifico.

  * Team di vendita specifici: limita i risultati per includere solo i lead assegnati a uno o più team di vendita. Questo filtro è opzionale e non deve essere incluso se il resoconto è destinato all’intera azienda.

  * Escludi lead non assegnati: esclude i lead che non sono stati assegnati a un addetto vendite.

  * Includi lead archiviati: garantisce che i risultati includano sia i lead attivi che quelli inattivi.

  * Aggiungi regole per lead di qualità: include o esclude i risultati in base a criteri specifici di un’azienda o di un team di vendita.




Un esempio della finestra pop-up _Filtro personalizzato_ con tutte le regole predefinite configurate.¶

#### Aggiungere il filtro data di inizio¶

Inizia definendo il parametro della regola con un intervallo di date, facendo clic sul primo campo, a sinistra della riga, e digitando `Creato il` nella barra Cerca… o scorrendo l’elenco del menu per trovarlo.

Nel menu a discesa dell’operatore della regola, definisci ulteriormente il parametro selezionando uno dei due:

  * >= (maggiore di o uguale a) per specificare una data di inizio e includere tutte le voci _dopo_ la data di inizio scelta (così come il valore iniziale stesso); oppure

  * è tra per definire in modo più preciso un arco di tempo con una data di inizio e di fine ben precisa. Tutte le voci corrispondenti che rientrano nelle date di inizio e fine definite vengono incluse nel resoconto.




Con entrambe le opzioni, utilizza i selezionatori del giorno e dell’ora del calendario a comparsa, nel campo all’estrema destra, per definire il rispettivo intervallo di date. L’impostazione di questi valori conclude la creazione della prima regola.

#### Aggiungere il filtro team vendite¶

Nota

Questo filtro è facoltativo. Per visualizzare i risultati dell’intera azienda, **non** aggiungere questo filtro.

Per limitare i risultati del resoconto a uno o più team di vendita, fai clic su Nuova regola. In seguito, fai clic sul primo campo della nuova regola e digita `Team vendite` nella barra Ricerca… o scorri l’elenco per trovarla.

Nel secondo campo della regola, seleziona è in dal menu a discesa. La selezione di questo operatore limita i risultati ai team di vendita selezionati nel campo successivo.

Infine, nel terzo campo, seleziona il team di vendita desiderato dal menu a discesa. È possibile aggiungere più team in questo campo, dove ogni parametro viene trattato con un operatore “o” (ad es. “qualsiasi”) nella logica di ricerca.

#### Escludere lead non assegnati¶

In seguito, aggiungi una Nuova regola. Successivamente, fai clic sul primo campo della nuova regola e digita `Addetto vendite` nella barra Cerca…, oppure scorri l’elenco per trovarlo.

Nel secondo campo della regola, seleziona è impostato dal menu a discesa. La selezione di questo operatore esclude tutti lead non assegnati a un addetto vendite specifico.

#### Includere lead archiviati¶

Suggerimento

Anche questo filtro è facoltativo, in quanto aggiunge al resoconto i lead archiviati (inattivi), tuttavia ti consigliamo di includerlo in quanto inserisce nel resoconto _tutti_ i lead assegnati, indipendentemente dallo stato. Ciò garantisce una rappresentazione più accurata dei lead assegnati. Tuttavia, se vuoi ottenere un resoconto che includa solo i lead attivi, non attivare questa funzione.

In seguito, nell’angolo in alto a destra della finestra pop-up Aggiungi filtro personalizzato, sposta il pulsante toggle Includi archiviati su attivo.

Attivando questa funzionalità, i lead archiviati (non attivi) verranno aggiunti al resoconto.

#### Aggiungere regole per lead di qualità¶

I filtri aggiunti in questa fase variano a seconda di come un’organizzazione definisce un _lead di qualità_.

##### Definire un lead di qualità¶

Come definito in precedenza, un _lead di qualità_ è un lead che probabilmente si tradurrà in un’opportunità vinta. Sebbene i criteri esatti per un lead di qualità varino da un’organizzazione all’altra, spesso si tratta di una combinazione di fattori comunemente attribuiti a risultati di vendita positivi, oltre a fattori valutati dall’organizzazione specifica.

Oltre ai filtri di base e alle opzioni di raggruppamento illustrate nel Resoconto lead di qualità generale, è possibile applicare anche i seguenti filtri per definire un lead di qualità:

  * E-mail o Telefono: le informazioni contenute in questi campi possono aiutare a determinare se un lead è un contatto professionale o meno.

  * Origine: questo campo collega la generazione di lead e le altre attività di marketing provenienti da altre applicazioni Odoo tra cui _Live chat_ , _Social marketing_ e _E-mail marketing_.

  * Fase: questo filtro può essere utilizzato per eliminare o indirizzare i lead che hanno raggiunto fasi specifiche.

  * Mezzo: la fonte di un lead può indicare il suo livello di qualità, poiché i vari canali hanno tassi di vincita e ricavi attesi diversi.

  * Campagna: l’aggiunta di questo filtro aiuta a tenere traccia del successo dei diversi sforzi di marketing per catturare lead di alta qualità.

  * Motivo perdita: esclude i lead che possono sembrare di qualità in base a vari criteri, ma che sono stati contrassegnati come _persi_ per motivi specifici.

  * Tag: include o esclude risultati in base a uno o più tag personalizzati.




Suggerimento

Quando aggiungi regole a un filtro personalizzato, tieni presente le affermazioni che precedono ciascuna regola. L’affermazione che precede una regola determina se i risultati della ricerca devono corrispondere a **tutte** le regole sotto l’affermazione o a **qualsiasi** delle regole sotto l’affermazione.

## Visualizzare il resoconto¶

Importante

Nella parte superiore del modulo Aggiungi filtro personalizzato, c’è un’opzione che consente di abbinare qualsiasi o tutte le regole. Per eseguire correttamente il resoconto, devono essere inclusi solo i record che corrispondono a **tutti** i filtri seguenti. Prima di aggiungere i filtri, assicurati che l’opzione tutti sia selezionata in questo campo.

Dopo aver configurato i filtri, fai clic su Aggiungi. La visualizzazione predefinita del resoconto è un grafico a barre con i lead raggruppati per _fase_.

Per raggruppare i risultati per addetto vendite, fai clic sull’icona 🔻(triangolo in giù) a destra della barra Cerca… per aprire il mega menu a tendina. Sotto la sezione Raggruppa per, seleziona Addetto vendite. Nella stessa colonna, sotto la sezione Raggruppa per, fai clic su Aggiungi a gruppo personalizzato, poi seleziona Attivo nel menu a discesa risultante per sostituire lo _stato_ del lead, sotto il raggruppamento principale Addetto vendite.

Il resoconto ora mostra il numero totale di _lead di qualità_ che ciascun addetto vendite ha ricevuto nel periodo di tempo designato. Poiché ci sono filtri sovrapposti di tipo Raggruppa per, i lead raggruppati sono anche codificati a colori per identificare se sono _attivi_ o _contrassegnati come persi_.

Suggerimento

Per salvare questa ricerca per dopo, fai clic sull’icona 🔻(triangolo giù) accanto alla barra Cerca… per aprire il menu a discesa. Sotto la voce Preferiti, fai clic su Salva ricerca corrente.

Nel menu a tendina, rinomina il resoconto dall’etichetta `Pipeline` predefinita a `Lead di qualità` e fai clic su Salva.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/quality_leads_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](resellers.html "Partner") |
  * [precedente](unattended_leads_report.html "Resoconto lead non seguiti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto lead di qualità


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