# Analisi del flusso — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [precedente](../performance.html "Analizzare le performance") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Analisi del flusso



# Analisi del flusso¶

L’applicazione _CRM_ gestisce la pipeline di vendita mentre i lead/opportunità passano da una fase all’altra, dall’origine alla vendita (**Vincita**) o all’archiviazione (**Perdita**).

Dopo aver organizzato la pipeline, utilizza le opzioni di ricerca e i resoconti disponibili nella pagina _Analisi della pipeline_ per ottenere informazioni sull’efficacia della pipeline e dei suoi utenti.

Per accedere alla pagina _Analisi pipeline_ , apri il modulo CRM ‣ Rendicontazione ‣ Pipeline.

## Esplorare la pagina di analisi della pipeline¶

Dopo aver eseguito l’accesso alla pagina Analisi pipeline, si apre automaticamente un grafico a barre che mostra i lead dell’ultimo anno. Le barre rappresentano il numero di lead in ciascuna fase della pipeline di vendita, con un codice colore che indica il mese in cui il lead ha raggiunto quella fase.

Gli elementi interattivi della pagina Analisi pipeline permettono di modificare il grafico per visualizzare varie metriche nelle differenti viste. Da sinistra a destra, dall’alto verso il basso, gli elementi includono:

  * Azioni: rappresentate dall’icona ⚙️ (ingranaggio), posizionata accanto al nome della pagina Analisi pipeline. Facendo clic sull’icona, apparirà un menu a tendina con tre opzioni e i relativi menu secondari: Knowledge, Dashboard, Fogli di calcolo. (Consulta la sezione Salvare e condividere resoconti per maggiori informazioni)

    * L’opzione Knowledge è per collegare o inserire il grafico in un articolo dell’app _Knowledge_.

    * L’opzione Dashboard serve ad aggiungere il grafico a una dashboard nell’app _Dashboard_.

    * L’opzione Fogli di calcolo serve a collegare il grafico a un foglio di calcolo nell’app _Documenti_.

  * Barra Ricerca…: mostra i filtri e i raggruppamenti applicati al grafico. Per aggiungere nuovi filtri/gruppi, inseriscili nella barra di ricerca oppure fai clic sull’icona ⬇️ (freccia in giù) alla fine della barra, per aprire un menu a discesa di opzioni. (Consulta la sezione Opzioni di ricerca per maggiori informazioni)




Nell’angolo in alto a destra, sono presenti opzioni di vista rappresentate da varie icone. (Consulta la sezione Opzioni vista per maggiori informazioni)

  * Vista Grafico: mostra i dati in un grafico a barre. Si tratta della vista predefinita.

  * Vista pivot: mostra i dati in una tabella personalizzabile.

  * Vista coorte: mostra e organizza i dati in base alla settimana (predefinito), giorno, mese o anno di Creazione e Chiusura.

  * Vista elenco: mostra i dati in un elenco.




Nella parte a sinistra della pagina, sotto al nome della pagina Analisi pipeline, è possibile configurare più filtri e opzioni di visualizzazione.

  * Misure: apre un menu a tendina con varie misure che è possibile integrare in una vista grafico, pivot o coorte. Il menu a discesa Misure non è disponibile nella vista elenco. (Consulta la sezione Opzioni misure per maggiori informazioni)

  * Inserisci in foglio di calcolo: apre una finestra pop-up con opzioni per aggiungere un grafico o una tabella pivot a un foglio di calcolo nell’app _Documenti_ o una dashboard nell’app _Dashboard_. L’opzione non è disponibile per le viste coorte o elenco.




Se selezioni la vista grafico, avrai a disposizione le seguenti opzioni:

  * Grafico a barre: da grafico a grafico a barre.

  * Grafico a linee: da grafico semplice a grafico a linee.

  * Grafico a torta: da grafico semplice a grafico a torta.

  * Impilato: se selezionato, i risultati di ogni fase del grafico sono sovrapposti. Quando non è selezionato, i risultati di ogni fase vengono mostrati come singole barre.

  * Decrescente: riordina le fasi del grafico in ordine decrescente da sinistra a destra. Fai clic sull’icona una seconda volta per deselezionarla. A seconda dei criteri di ricerca, questa opzione potrebbe non essere disponibile.

  * Crescente: riordina le fasi del grafico in ordine crescente da sinistra a destra. Fai clic sull’icona una seconda volta per deselezionarla. A seconda dei criteri di ricerca, questa opzione potrebbe non essere disponibile.




Una volta selezionata la vista pivot, sono disponibili le seguenti opzioni:

  * Inverti assi: inverte gli assi X e Y della tabella.

  * Espandi tutto: quando vengono selezionati raggruppamenti aggiuntivi utilizzando le icone ➕ (segno più), il pulsante apre i raggruppamenti sotto ogni riga.

  * Download xlsx: scarica la tabella come file Excel.




### Opzioni di ricerca¶

La pagina Analisi pipeline può essere personalizzata con vari filtri e opzioni di raggruppamento.

Per aggiungere nuovi criteri di ricerca, inserisci il criterio desiderato nella barra oppure fai clic sull’icona ⬇️ (freccia giù), accanto alla barra di ricerca per aprire un menu a tendina con tutte le opzioni. Consulta le sezioni in basso per avere maggiori informazioni sul funzionamento di ogni opzione.

FiltersGroup ByComparisonFavorites

La sezione Filtri consente agli utenti di aggiungere filtri preconfigurati e personalizzati ai criteri di ricerca. È possibile aggiungere vari filtri a una sola ricerca.

  * La mia pipeline: mostra i lead assegnati all’utente corrente.

  * Opportunità: mostra i lead che sono stati qualificati come opportunità.

  * Lead: mostra i lead che non sono ancora stati qualificati come opportunità.

  * Attivo: mostra i lead attivi.

  * Inattivo: mostra i lead non attivi.

  * Vinto: mostra i lead contrassegnati come **Vinti**.

  * Perso: mostra i lead contrassegnati come **Persi**.

  * Creato il: mostra i lead che sono stati creati durante un periodo di tempo specifico. Per impostazione predefinita, si tratta dell’anno passato ma è possibile modificare il filtro a piacimento oppure rimuoverlo completamente.

  * Chiusura prevista: mostra i lead che si prevede di chiudere (contrassegnati come **Vinti**) durante un periodo di tempo specifico.

  * Data di chiusura: mostra i lead chiusi (contrassegnati come **Vinti**) durante un periodo di tempo specifico.

  * Archiviato: mostra i lead che sono stati archiviati (contrassegnati come **Persi**).

  * Aggiungi filtro personalizzato: consente all’utente di creare un filtro personalizzato con varie opzioni. (Consulta la sezione Aggiungi filtri e gruppi personalizzati per avere più informazioni)




La sezione Raggruppa per permette agli utenti di aggiungere raggruppamenti preconfigurati e personalizzati ai risultati di ricerca. È possibile aggiungere vari raggruppamenti per dividere i risultati in più segmenti.

Importante

L’ordine di aggiunta dei raggruppamenti influisce sulla visualizzazione dei risultati finali. Prova a selezionare le stesse combinazioni in un ordine diverso per vedere cosa funziona meglio per ogni caso d’uso.

  * Addetto vendite: raggruppa i risultati per addetto vendite a cui vengono assegnati lead.

  * Team vendite: raggruppa i risultati per team di vendita a cui vengono assegnati lead.

  * Città: raggruppa i risultati per città di provenienza del lead.

  * Paese: raggruppa i risultati per Paese di origine del lead.

  * Azienda: raggruppa i risultati per azienda a cui appartiene un lead (se nel database sono attive più aziende).

  * Fase: raggruppa i risultati per fasi della pipeline relativa alle vendite.

  * Campagna: raggruppa i risultati secondo la campagna di marketing da cui è stato creato il lead.

  * Mezzo: raggruppa i risultati per mezzo (e-mail, Google Adwords, sito web, ecc.) da cui proviene il lead.

  * Origine: raggruppa i risultati per elemento di origine (motore di ricerca, lead recall, newsletter, ecc.) del lead.

  * Data di creazione: raggruppa i risultati secondo la data di aggiunta al database del lead.

  * Data di conversione: raggruppa i risultati secondo la data in cui un lead è stato convertito in opportunità.

  * Chiusura prevista: raggruppa i risultati secondo la data prevista di chiusura del lead (contrassegnato come «Vinto»).

  * Data di chiusura: raggruppa i risultati secondo la data di chiusura di un lead (contrassegnato come «Vinto»).

  * Motivo perdita: raggruppa i risultati secondo la ragione selezionata quando un lead viene contrassegnato come «Perso».

  * Aggiungi gruppo personalizzato: permette all’utente di creare un gruppo personalizzato con numerose opzioni. (Consulta la sezione Aggiungere filtri e gruppi personalizzati per maggiori informazioni)




La sezione Confronto consente agli utenti di aggiungere confronti con gli stessi criteri di ricerca in un altro periodo di tempo.

Questa opzione è disponibile solamente se la ricerca include filtri basati sul tempo, come Creato il, Chiusura prevista oppure Data chiusura. Anche se è possibile aggiungere più filtri basati sul tempo in una sola volta, è possibile selezionare solo un confronto per volta.

  * Periodo precedente: aggiunge un confronto allo stesso criterio di ricerca dal periodo precedente.

  * Anno precedente: aggiunge un confronto allo stesso criterio di ricerca dall’anno precedente.




La sezione Preferiti permette agli utenti di salvare una ricerca per dopo così non è necessario crearla da capo ogni volta.

Le ricerche multiple possono essere salvate, condivise con altri o anche impostate come predefinite ogni volta che si apre la pagina Analisi pipeline.

  * Salva ricerca corrente: salva i criteri della ricerca corrente per dopo.

    * Filtro predefinito: quando salvi una ricerca, spunta questa casella per renderlo il filtro ricerca predefinito se sei sulla pagina Analisi pipeline.

    * Condivisa: quando salvi una ricerca, spunta questa casella per renderla disponibile ad altri utenti.




#### Aggiungere filtri e gruppi personalizzati¶

Oltre alle opzioni predefinite nella barra di ricerca, la pagina Analisi pipeline può utilizzare anche filtri e gruppi personalizzati.

I filtri personalizzati sono regole complesse che personalizzano ulteriormente i risultati della ricerca, mentre i gruppi personalizzati visualizzano le informazioni in modo più organizzato.

**Per aggiungere un filtro personalizzato:**

  1. nella pagina Analisi pipeline, fai clic sull’icona freccia giù accanto alla barra Ricerca….

  2. Nel menu a tendina, fai clic su Aggiungi filtro personalizzato.

  3. Apparirà la finestra pop-up Aggiungi filtro personalizzato con una regola predefinita (Paese è in _____) costituita da tre campi unici. Questi campi possono essere modificati per creare una regola personalizzata ed è possibile aggiungere più regole a un singolo filtro personalizzato.

  4. Per modificare una regola, inizia facendo clic sul primo campo (Paese) e seleziona un’opzione dal menu a tendina. Il primo campo stabilisce il soggetto principale della regola.

  5. Successivamente, fai clic sul secondo campo e seleziona un’opzione dal menu a discesa. Il secondo campo determina la relazione tra il primo e il terzo campo e di solito è un’affermazione **è** o **non è** , ma può anche essere un’affermazione **maggiore o minore di** e altro ancora.

  6. Infine, fai clic sul terzo campo e seleziona un’opzione dal menu a discesa. Il terzo campo determina l’oggetto secondario della regola.

  7. Una volta selezionati i tre campi, la regola è completa.

     * **Per aggiungere più moduli:** fai clic su Nuova regola e ripeti gli step 4-7, se necessario.

     * **Per eliminare una regola:** fai clic sull’icona 🗑️ (cestino) a destra della regola.

     * **Per duplicare una regola esistente:** fai clic sull’icona ➕ (segno più) a destra della regola.

     * **Per creare regole più complesse:** fai clic sull’icona Aggiungi branch a destra della regola. Questo aggiunge un altro modificatore sotto la regola per aggiungere un’istruzione di tipo «tutti di» oppure «qualsiasi di».




  8. Una volta che tutte le regole sono state aggiunte, fai clic su Aggiungi per aggiungere il filtro personalizzato ai criteri della ricerca.

     * **Per eliminare un filtro personalizzato:** fai clic sull’icona ✖️ (x) accanto al filtro nella barra di ricerca.




**Per aggiungere un gruppo personalizzato:**

  1. nella pagina Analisi pipeline, fai clic sull’icona freccia giù accanto alla barra di ricerca.

  2. Nel menu a tendina che appare, fai clic su Aggiungi gruppo personalizzato.

  3. Scorri le opzioni nel menu a discesa e seleziona uno o più gruppi.

     * **Per eliminare un gruppo personalizzato:** fai clic sull’icona ✖️ (x) accanto al gruppo personalizzato nella barra di ricerca.




### Opzioni misure¶

Per impostazione predefinita, la pagina Analisi pipeline misura il Numero totale di lead che corrispondono ai criteri della ricerca ma non può essere modificato per misurare altri elementi interessanti.

Per aggiungere la misura selezioanta, fai clic sul pulsante Misure nella parte in alto a sinistra della pagina e seleziona una delle seguenti opzioni dal menu a discesa:

  * Giorni per assegnare: misura il numero di giorni impiegati per assegnare un lead dopo la creazione.

  * Giorni per la chiusura: misura il numero di giorni necessari per chiudere un lead (contrassegnato come **Vinto**).

  * Giorni da convertire: misura il numero di giorni impiegati da un lead per essere convertito in un’opportunità.

  * Giorni di chiusura oltrepassati: misura il numero di giorni in cui un lead ha superato la data di chiusura prevista.

  * MRR atteso: misura i ricavi ricorrenti mensili per un lead.

  * Ricavi previsti: misura i ricavi previsti di un lead.

  * MRR ripartito in proporzione: misura il ricavo ricorrente mensile ripartito in proporzione di un lead.

  * Ricavi ricorrenti prorata: misura i ricavi ricorrenti prorata di un lead.

  * Ricavi ripartiti in proporzione: misura i ricavi prorata di un lead.

  * Ricavi ricorrenti: misura i ricavi ricorrenti di un lead.

  * Numero: misura l’importo totale di lead che corrispondono ai criteri di ricerca.




### Opzioni di visualizzazione¶

Dopo aver configurato i filtri, i raggruppamenti e le misure, la pagina Analisi pipeline può mostrare la data in vari modi. Per impostazione predefinita, la pagina usa la vista grafico ma è possibile modificarla in una vista pivot, coorte o elenco.

Per cambiare la visualizzazione della pipeline, fai clic su una delle quattro icone di visualizzazione, situate in alto a destra della pagina Analisi pipeline.

Graph ViewPivot ViewCohort ViewList View

La vista grafico è la selezione predefinita per la pagina Analisi pipeline. Visualizza l’analisi come: grafico a barre, grafico a linee o grafico a torta.

Questa opzione di visualizzazione è utile per visualizzare e confrontare rapidamente relazioni semplici, come il Numero di lead in ogni fase o i lead assegnati a ciascun Addetto vendite.

Per impostazione predefinita, il grafico misura il Numero di lead in ogni gruppo ma è possibile modificare l’impostazione facendo clic sul pulsante Misure per poi selezionare un’altra opzione dal menu a discesa risultante.

Suggerimento

Quando si utilizza un grafico a barre in questa vista, si consiglia di deselezionare l’opzione Impilato per rendere più leggibile la suddivisione dei risultati.

La vista pivot visualizza i risultati dell’analisi sotto forma di tabella. Per impostazione predefinita, la tabella raggruppa i risultati in base alle fasi della pipeline di vendita e misura i Ricavi previsti.

La vista pivot è utile per analizzare numeri più dettagliati di quelli che può gestire la vista grafico, oppure per aggiungere i dati a un foglio di calcolo, dove è possibile impostare formule personalizzate, come in un file Excel.

Le tre icone nella parte alta a sinistra della pagina eseguono le seguenti funzioni:

  * Inverti assi: inverte gli assi X e Y della tabella.

  * Espandi tutto: quando vengono selezionati raggruppamenti aggiuntivi utilizzando le icone ➕ (segno più), il pulsante apre i raggruppamenti sotto ogni riga.

  * Download xlsx: scarica la tabella come file Excel.




Nota

Il raggruppamento Fase non può essere rimosso, ma la misura può essere modificata facendo clic sul pulsante Misure e selezionando un’altra opzione.

La vista coorte visualizza l’analisi come periodi di tempo (coorti) che possono essere impostati su giorni, settimane, mesi o anni. Per impostazione predefinita, è selezionato il parametro Settimane.

Questa opzione di visualizzazione è utile soprattutto per confrontare il tempo impiegato per chiudere i lead.

Da sinistra a destra, dall’alto verso il basso, le colonne del grafico rappresentano quanto segue:

  * Creato il: le righe di questa colonna rappresentano le settimane dell’anno in cui esistono record corrispondenti ai criteri di ricerca.

    * Se impostata su Settimana, una riga con l’etichetta W52 2023 significa che i risultati si sono verificati nella: settimana 52 dell’anno 2023.

  * Misure: la seconda colonna nel grafico rappresenta la misura dei risultati. Per impostazione predefinita, è impostata su Numero ma puoi modificarla facendo clic sul pulsante Misure per poi selezionare un’opzione dal menu a discesa.

  * Data chiusura - Per giorno/settimana/mese/anno: questa colonna esamina la percentuale dei risultati misurati che sono stati chiusi nei giorni/settimane/mesi/anni successivi.

  * Media: la riga fornisce la media di tutte le altre righe nella colonna.




La vista coorte può anche essere scaricata come file Excel, cliccando sull’icona Download in alto a sinistra della pagina.

La vista elenco mostra un singolo elenco di tutti i contatti che corrispondono ai criteri di ricerca. Facendo clic su un lead si apre il record per un’analisi più approfondita. Ulteriori dettagli come Paese, Mezzo e altro ancora possono essere aggiunti all’elenco, facendo clic sull’icona Filtri in alto a destra dell’elenco stesso.

Questa opzione di visualizzazione è utile per esaminare molti record contemporaneamente.

Facendo clic sull’icona ⚙️ (ingranaggio), si aprirà il menu a discesa Azioni con le opzioni:

  * Importa record: apre una pagina per caricare un foglio di calcolo e un modello di foglio di foglio di calcolo per formattare facilmente i dati.

  * Esporta tutto: scarica l’elenco come file xlsx per Excel.

  * Knowledge: inserisci una vista, un link o l’elenco in un articolo nell’app _Knowledge_.

  * Dashboard: aggiunge l’elenco alla _Mia dashboard_ nell’app _Dashboard_.

  * Foglio di calcolo: collega o inserisci l’elenco in un foglio di calcolo nell’app _Documenti_.




Nota

Nella vista elenco, facendo clic su Nuovo verrà chiuso l’elenco e verrà aperta la pagina per un _Nuovo preventivo_. Se fai clic su Genera lead, si aprirà una finestra pop-up per la generazione di lead. Nessuna delle due funzioni è destinata a manipolare la vista elenco.

## Creare resoconti¶

Dopo aver capito come navigare la pagina di analisi della pipeline, la pagina Analisi della pipeline può essere usata per creare e condividere diversi resoconti. Tra le opzioni predefinite e i filtri e i raggruppamenti personalizzati, è possibile realizzare quasi tutte le combinazioni.

Una volta creati, i resoconti possono essere salvati nei preferiti, condivisi con altri utenti e/o aggiunti a dashboard e fogli di calcolo.

Di seguito, vengono elencati una serie di resoconti comuni che è possibile creare utilizzando la pagina Analisi pipeline.

### Resoconti vincite/perdite¶

Il calcolo vincite/perdite è il calcolo dei lead attivi o precedentemente attivi in una pipeline che sono stati contrassegnati come **vinti** o **persi** in un periodo di tempo specifico. Calcolando le opportunità vinte rispetto a quelle perse, i team possono chiarire gli indicatori di performance chiave (KPI) che stanno convertendo i lead in vendite, come ad esempio team o membri di team specifici, determinati mezzi o campagne di marketing e così via.

\\[\begin{equation} Rapporto vincita/perdita = \frac{Opportunità vinte}{Opportunità perse} \end{equation}\\]

Un resoconto sulle vittorie/perdite filtra i lead dell’ultimo anno, sia quelli vinti che quelli persi, e raggruppa i risultati in base alla loro fase nella pipeline. La creazione di questo resoconto richiede un filtro personalizzato e il raggruppamento dei risultati per Fase.

Segui gli step che seguono per creare un resoconto vincite/perdite:

  1. accedi all’app CRM ‣ Rendicontazione ‣ Pipeline.

  2. Sulla pagina Analisi pipeline, fai clic sull’icona ⬇️ (freccia giù) accanto alla barra di ricerca, per aprire un menu a tendina con filtri e raggruppamenti.

  3. Nel menu a discesa che appare, sotto il titolo Raggruppa per, fai clic su Fase.

  4. Nella sezione Filtri, fai clic su Aggiungi filtro personalizzato per aprire un altro menu pop-up.

  5. Nel menu pop-up Aggiungi filtro personalizzato, fai clic sul primo campo della sezione Corrisponde a una delle seguenti regole:. Per impostazione predefinita, questo campo mostra Paese.

  6. Facendo clic sul primo campo, verrà visualizzato un menu secondario con varie opzioni tra cui scegliere. Da questo menu secondario, trova e seleziona l’opzione Attivo. Di conseguenza, i campi restanti verranno popolati automaticamente.

Il primo campo corrisponde a: Attivo. Il secondo corrisponde a: è. Infine, il terzo campo corrisponde a: configurato.

Nel complesso, la regola corrisponde a: Attivo è configurato.

  7. Fai clic su Nuova regola, modifica il primo campo in Attivo e l’ultimo campo in non configurato. Nel complesso, la regola sarà Attivo non è configurato.

  8. Fai clic su Aggiungi.




Il resoconto ora mostra il Numero totale di lead, «Vinti» o «Persi», raggruppati per fase nella pipeline CRM. Passa con il mouse su una sezione del resoconto per vedere il numero di lead nella fase corrispondente.

#### Personalizzare resoconti vincite/perdite¶

Dopo aver creato un resoconto vincite/perdite, prova a utilizzare le opzioni in basso per personalizzare il resoconto stesso a seconda delle necessità.

Example

Un responsabile delle vendite potrebbe raggruppare vincite e perdite in base all’addetto vendite o al team di vendita, per vedere chi ha il miglior tasso di conversione. Oppure, un team di marketing potrebbe raggruppare vincite e perdite in base alle fonti o al mezzo di comunicazione, per determinare dove la pubblicità ha avuto più successo.

Filters and groupsPivot ViewList View

Per aggiungere più filtri e gruppi, fai clic sull’icona ⬇️ (freccia giù) accanto alla barra di ricerca e seleziona una o più opzioni dal menu a discesa.

Alcune opzioni utili includono:

  * Creato il: se si regola questo filtro su un periodo di tempo diverso, come gli ultimi 30 giorni o l’ultimo trimestre, si possono ottenere risultati più tempestivi.

  * Aggiungi filtro personalizzato: fai clic sull’opzione e scorrendo tra le varie disponibili nel menu a discesa, si aprirà un criterio di ricerca aggiuntivo come Ultimo aggiornamento fase oppure Motivo perdita.

  * Aggiungi gruppo personalizzato > Attivo: Facendo clic su Aggiungi gruppo personalizzato ‣ Attivo i risultati verranno separati in **Vinti** (vero) o **Persi** (falso). Indica in quale fase i lead vengono contrassegnati come **vinti** o **persi**.

  * Raggruppamenti multipli: aggiungi più scelte del tipo Raggruppa per per dividere i risultati in segmenti più importanti e gestibili.

    * L’aggiunta di un addetto vendite o di un team vendite divide il numero totale di lead per ogni Fase.

    * L’aggiunta di un Mezzo oppure Origine può rivelare quali canali di marketing generano più vendite.




Per impostazione predefinita, la vista pivot raggruppa i resoconti vincite/perdite per Fase e calcola i Ricavi previsti.

Per arricchire la tabella:

  1. fai clic sulla ⬇️ (freccia giù) accanto alla barra di ricerca.

  2. Nel menu pop-up, sostituisci il raggruppamento per Fase con qualcosa come Addetto vendite o Mezzo.

  3. Fai clic sul pulsante Misure e fai clic su Numero per aggiungere il numero di lead al resoconto.

     * Altre misure utili per la vista pivot includono Giorni da assegnare e Giorni alla chiusura.




Importante

Nella vista pivot, il pulsante Inserisci in foglio di calcolo potrebbe diventare grigio a causa della presenza di raggruppa per duplicati. Per ovviare al problema, sostituisci il raggruppamento Fase nella barra di ricerca con un’altra opzione.

Nella vista elenco, un resoconto vincite/perdite mostra tutti i lead in un’unica pagina.

Per organizzare al meglio l’elenco, fai clic su ⬇️ (freccia giù) accanto alla barra di ricerca e aggiungi raggruppamenti più rilevanti oppure riorganizza quelli esistenti. Per riordinare il raggruppamento, elimina tutte le opzioni di tipo Raggruppa per e aggiungile di nuovo nell’ordine desiderato.

Per aggiungere più colonne all’elenco:

  1. fai clic sull’icona Filtri nella parte in alto a destra della pagina.

  2. Seleziona le opzioni dal menu a tendina risultante. Alcuni filtri utili includono:

     * **Campagna** : mostra la campagna marketing che ha portato alla creazione di ogni lead.

     * **Mezzo** : mostra il mezzo marketing (banner, direct, e-mail, Google Adwords, telefono, sito web, ecc.) che ha portato alla creazione di ogni lead.

     * **Origine** : mostra l’origine di ogni lead (newsletter, lead recall, motore di ricerca, ecc.).




## Salvare e condividere resoconti¶

Dopo aver creato un resoconto, è possibile salvare i criteri della ricerca quindi non è necessario creare di nuovo il resoconto in futuro. I risultati delle ricerche salvate vengono aggiornati automaticamente ogni volta che viene aperto il resoconto.

Inoltre, i resoconti possono essere condivisi con altri o aggiunti a fogli di calcolo/dashboard per una maggiore personalizzazione e un accesso più semplice.

Save to FavoritesAdd to a SpreadsheetAdd to a Dashboard

Per salvare un resoconto per dopo:

  1. nella pagina Analisi pipeline, fai clic sull’icona ⬇️ (freccia giù), accanto alla barra di ricerca.

  2. Nel menu a discesa che appare, sotto il titolo Preferiti, fai clic su Salva ricerca corrente.

  3. Nel menu a discesa che appare successivamente, inserisci un nome per il resoconto.

     * Se spunti la casella Filtro predefinito, il resoconto diventerà l’analisi predefinita quando accedi alla pagina Analisi pipeline.

     * Se spunti la casella Condiviso, il resoconto sarà disponibile anche per altri utenti.

  4. Infine, fai clic su Salva. Il resoconto è stato salvato nella sezione Preferiti.




L’inserimento di un resoconto in un foglio di calcolo non solo salva una copia del resoconto, ma consente di aggiungere grafici e formule come in un file Excel.

Per salvare un resoconto come foglio di calcolo:

  * **Nella vista grafico o pivot** :

    1. fai clic sul pulsante Inserisci in foglio di calcolo.

    2. Nel menu pop-up che appare, fai clic su Conferma.

  * **Nella vista coorte o elenco** :

    1. Fai clic sull’icona ⚙️ (ingranaggio).

    2. Nel menu a discesa che appare, passa con il mouse sulla sezione Foglio di calcolo.

    3. Nel menu a discesa seguente, fai clic su Inserisci in foglio di calcolo oppure su Collega a foglio di calcolo.




I resoconti salvati sono visualizzabili nell’app _Documenti_.

> Suggerimento

Dopo aver modificato un foglio di calcolo e aggiunto formule supplementari, puoi aggiungere l’intero foglio di calcolo a un dashboard. Con questo metodo, il foglio di calcolo può essere aggiunto a una dashboard pubblica invece che esclusivamente alla mia dashboard.

  1. Fai clic su File ‣ Aggiungi alla dashboard.

  2. Nel menu pop-up che appare, dai un nome al foglio di calcolo e seleziona una Dashboard dove salvare il resoconto.

  3. Fai clic su Crea.




L’aggiunta di un resoconto a una dashboard permette di salvarlo per un secondo momento e lo rende facile da visualizzare insieme al resto della dashboard.

Per aggiungere un resoconto alla mia dashboard:

  1. nella pagina Analisi pipeline, fai clic sull’icona ⚙️ (ingranaggio).

  2. Nel menu a tendina che appare, passa con il mouse su Dashboard.

  3. Nel menu a discesa Aggiungi alla dashboard, inserisci un nome per il resoconto (per impostazione predefinita sarà nominato Pipeline).

  4. Fai clic su Aggiungi.




Per visualizzare un resoconto salvato:

  1. Torna alla pagina principale con tutte le app e apri l’app Dashboard ‣ La mia dashboard.




Vedi anche

  * [Convertire i Lead in opportunità](../acquire_leads/convert.html)

  * [Creare e inviare preventivi](../acquire_leads/send_quotes.html)

  * [Gestire le opportunità perse](../pipeline/lost_opportunities.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/performance/win_loss.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [precedente](../performance.html "Analizzare le performance") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Analisi del flusso


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