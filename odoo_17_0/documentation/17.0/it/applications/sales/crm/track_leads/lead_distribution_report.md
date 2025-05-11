# Resoconto distribuzione lead — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../performance.html "Analizzare le performance") |
  * [precedente](marketing_attribution.html "Resoconti attribuzione attività marketing") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto distribuzione lead



# Resoconto distribuzione lead¶

Un _resoconto di distribuzione dei lead_ può essere utilizzato per vedere se i lead attivi vengono assegnati in maniera equa tra i vari membri del team vendite. Può essere utilizzato anche per visualizzare la distribuzione di lead buoni o [di qualità](quality_leads_report.html) e vedere la frequenza di ricezione e retenzione dei lead per ogni addetto vendite.

I resoconti sulla distribuzione dei lead possono essere eseguiti ogni settimana per aiutare i venditori a mantenere la rotta, fornendo loro un’ampia quantità di buoni lead. Questi resoconti possono essere utilizzati anche per vedere se i membri dei team di vendita rimangono produttivi, se i lead buoni vengono persi troppo spesso da un venditore e quale percentuale di lead buoni viene conservata in generale.

## Creare resoconti di distribuzione dei lead¶

Per creare un resoconto sulla distribuzione dei lead, apri il modulo CRM ‣ Rendicontazione ‣ Pipeline, che mostra la dashboard Analisi pipeline.

Rimuovi tutti i filtri predefiniti nella barra di ricerca in cima alla pagina. In questo modo vengono visualizzati i dati relativi a _tutti_ i contatti.

Ora è possibile aggiungere [filtri personalizzati](../../../essentials/search.html#search-custom-filters) facendo clic sull’icona __(caret giù), a destra della barra di ricerca, per rivelare un menu a discesa di opzioni di ricerca e di filtri.

Vengono visualizzate tre colonne: [Filtri](../../../essentials/search.html#search-filters), [Raggruppa per](../../../essentials/search.html#search-group) e [Preferiti](../../../essentials/search.html#search-favorites). Per iniziare, spostati in fondo alla colonna Filtri e fai clic su Aggiungi filtro personalizzato. Si aprirà la finestra pop-up Aggiungi filtro personalizzato, in cui è possibile aggiornare filtri essenziali.

### Filtri essenziali¶

Le seguenti condizioni del filtro sono utilizzate per creare un resoconto di base sulla distribuzione dei lead. Insieme raccolgono tutti i lead creati entro un certo periodo di tempo che hanno un metodo di contatto associato e sono stati assegnati a un team di vendita.

#### Data di creazione del lead¶

Fai clic sul primo campo, sotto Corrisponde a una delle seguenti regole:, che contiene il valore Paese. Nel popover che appare, digita `Creato il` nella barra di ricerca o scorri l’elenco per individuarlo e selezionarlo.

Successivamente, nel secondo campo di quella riga, seleziona >= dal menu a discesa. Questo operatore include **solo** valori maggiori (o uguali) al valore del terzo campo più a destra.

Il terzo campo della finestra pop-up Aggiungi filtro personalizzato deve contenere la prima data di selezione dei lead.

Ad esempio, impostando la data al `01/01/2024 00:00:00` verranno inclusi solo i lead creati a partire dal primo giorno del 2024.

#### Team di vendita¶

Fai clic su Nuova regola per aggiungere un’altra riga al modulo e scegli Team vendite come parametro di questa regola. Successivamente, fai clic sul secondo campo della nuova regola e seleziona contiene dal menu a discesa. La selezione di questo operatore filtra tutti i record che contengono le parole nel terzo campo più a destra.

Suggerimento

Per alcune scelte predeterminate e limitate, come un team di vendita, l’operatore è in contribuisce a rendere più facile e accurata la selezione, tramite un menu a tendina nel terzo campo, invece di rischiare un errore di battitura o un valore errato nel campo della casella di testo che accompagna l’operatore contiene.

In questo terzo campo, inserisci il nome del team di vendita desiderato che deve essere incluso nel resoconto. È importante che tutti i valori degli argomenti di tipo contiene siano sufficientemente specifici e scritti correttamente come esistono in Odoo, altrimenti si rischia di restituire valori multipli (o pari a zero).

Importante

Aggiungendo più di una regola al modulo, emerge una nuova opzione nella parte superiore della finestra pop-up sopra tutti i filtri, per specificare se una qualsiasi __o tutte __le condizioni devono corrispondere. Questa distinzione è importante da impostare correttamente, poiché ha un impatto sulla logica di funzionamento dei filtri che restituiscono i dati.

Fai clic sulla voce di menu predefinita qualsiasi __e assicurati che venga invece scelta l’opzione tutti __. Questa impostazione mostrerà**solo** i record che corrispondono a _tutte_ le regole contenute nel modulo.

#### Metodo di contatto¶

Nota

Le istruzioni riportate di seguito non sono necessarie, tuttavia ti consigliamo vivamente di aggiungere un valore di contatto ai criteri di ricerca del resoconto. Molti lead spam, duplicati o di bassa qualità possono essere facilmente eliminati dal resoconto semplicemente aggiungendo una regola Telefono o E-mail.

Aggiungi un’altra Nuova regola al modulo e imposta il primo campo su Telefono. In seguito, seleziona è impostato dal menu a discesa del secondo campo. La selezione di questo operatore filtra **solo** i record che hanno un numero di telefono associato al lead.

In alternativa (o in aggiunta alla regola precedente), fai clic su Nuova regola e imposta il primo campo su E-mail. Successivamente, seleziona è impostato dal menu a discesa del secondo campo.

Queste regole aggiungono al resoconto solo i lead con un metodo di contatto associato.

#### Stato attivo¶

Fai clic sull’icona __(Aggiungi branch) a destra della riga `Telefono è impostato`, per aggiungere una nuova regola che si dirama dalle regole precedenti.

Due serie orizzontali di campi appaiono sotto una riga che mostra l’opzione qualsiasi __ di:. Questa impostazione filtra i record che corrispondono a **qualsiasi** regola contenuta all’interno. Utilizza la stessa logica di un operatore logico OPPURE (`|`).

Imposta il primo campo su Attivo. In seguito, seleziona è impostato nel campo successivo.

In seguito, fai clic sul pulsante __(Aggiungi nuova regola) accanto a Attivo è impostato per creare una nuova riga di campi sotto di essa.

Imposta il primo campo su Attivo. In seguito, seleziona non è impostato nel campo successivo.

Questa regola aggiunge lo stato di attività del lead al resoconto.

Nota

Lo stato attivo è un filtro importante da includere quando si crea un resoconto sulla distribuzione dei lead, perché include **tutti** i lead, indipendentemente dallo stato vinto/perso o attivo/inattivo nel rapporto. In questo modo si ottiene una visione completa di tutti i lead assegnati a ciascun membro del team vendite.

#### Raggruppa per¶

Una volta impostati tutti i filtri, fai clic sul pulsante Aggiungi per aggiungere questi filtri alla barra di ricerca. Per raggruppare il resoconto in modo appropriato, fai clic sull’icona __(caret giù), a destra della barra di ricerca, e fai clic su Addetto vendite nella sezione Raggruppa per. Tutti i risultati sono ora raggruppati in base al venditore assegnato a ciascun lead.

Una volta impostate le regole del filtro, fai clic sul pulsante viola Conferma in fondo al menu a comparsa per salvare il filtro personalizzato e chiudere il menu.

La dashboard Analisi pipeline viene nuovamente visualizzata con ogni regola di filtro nella barra di ricerca.

Fai clic sull’icona __(Grafico), a destra della barra di ricerca, per visualizzare il resoconto come grafico a barre. In alternativa, fai clic sull’icona __(Elenco) per visualizzare i lead in un elenco raggruppato.

Suggerimento

Per salvare il filtro in modo da poterlo riapplicare facilmente, fai clic sul pulsante Salva ricerca corrente nella sezione Preferiti del menu a discesa della barra di ricerca.

Successivamente, inserisci un nome per il filtro nella casella di testa in basso. Spunta la casella Condiviso per condividere il filtro con qualsiasi utente che abbia accesso alla pipeline. Infine, fai clic sul pulsante viola Salva per salvare il filtro.

Il filtro apparirà nella sezione Preferiti del menu a tendina con il nome che gli è stato dato e potrà essere applicato di nuovo facendo clic su di esso.

### Filtro per lead di qualità¶

Le seguenti condizioni aggiuntive vengono fornite come esempio di insieme di regole _buone_ ma _non complete_ per trovare lead di qualità. Questi filtri dovrebbero essere applicati oltre ai Filtri essenziali, nell’ordine specificato per ottenre un filtro super dettagliato.

  * **Indicato da:** filtro per i referral come per appuntamento o membro team vendite.

  * **Origine:** filtro per fonti UTM specifiche, come Facebook o LinkedIn.

  * **Note:** filtro per note interne.

  * **Tag:** filtro per tag categorici.

  * **E-mail:** filtro per domini e-mail specifici come gmail.com oppure yahoo.com.

  * **Addetto vendite:** filtro per lead associati ad alcuni membri del team vendite.




Queste condizioni possono essere aggiunte, eliminate o modificate per corrispondere al meglio alle informazioni che desideri includere nel resoconto.

Vedi anche

  * [Aggiungere regole per lead di qualità](quality_leads_report.html#quality-leads-report-add-quality-rules)

  * [Cercare, filtrare e raggruppare i record](../../../essentials/search.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/lead_distribution_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../performance.html "Analizzare le performance") |
  * [precedente](marketing_attribution.html "Resoconti attribuzione attività marketing") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto distribuzione lead


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