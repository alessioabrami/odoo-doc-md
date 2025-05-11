# Resoconto lead non seguiti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_leads_report.html "Resoconto lead di qualità") |
  * [precedente](lead_scoring.html "Assegnare lead con calcolo previsionale") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto lead non seguiti



# Resoconto lead non seguiti¶

_I lead non seguiti_ sono lead che hanno attività pianificate che sono in scadenza o scadute. Ogni volta che un’attività è programmata, Odoo tiene traccia della data di scadenza e invia promemoria via e-mail agli utenti a cui l’attività è assegnata.

Un _resoconto sui lead non seguiti_ raccoglie tutti i lead attivi nella pipeline con attività in scadenza o scadute, consentendo al responsabile delle vendite di identificare le opportunità che richiedono un’attenzione immediata.

Con un resoconto giornaliero sui lead non seguiti, i manager delle vendite possono ricordare ai propri team di occuparsi delle attività in sospeso prima che scadino, evitando di trascurare i lead e rafforzando i comportamenti proattivi degli addetti alle vendite.

Example

> Un responsabile delle vendite inizia la sua giornata estraendo un resoconto sui lead non seguiti e, passando alla visualizzazione a elenco, vede quanto segue:

Mitchell, membro del team, ha due lead nella fase _Proposta_ con attività da svolgere.

L’icona gialla 📞 (telefono) indica che il lead `Modern Open Space` ha l’attività «telefonata» programmata per oggi. L’icona rossa ✉️ (busta) indica che il lead `5 VP Chairs` ha l’attività «e-mail» scaduta.

Facendo clic sul lead “5 VP Chairs”, il responsabile delle vendite apre il record del lead e ne esamina il chatter. Vede che l’invio dell’e-mail era previsto due giorni fa, ma Mitchell non ha mai contrassegnato questa attività come eseguita.

Importante

Per ottenere un resoconto sui lead non seguiti, i team di vendita **devono** utilizzare regolarmente l’attività nella pipeline del _CRM_ , nelle schede dei singoli lead e delle opportunità.

Non è **possibile** eseguire un resoconto completo se gli addetti alle vendite non utilizzano la funzione _Attività_ nel _chatter_.

Per maggiori informazioni, consulta la sezione [Attività](../../../essentials/activities.html)

## Creare un resoconto sui lead non seguiti¶

Per creare un resoconto sui lead non seguiti, accedi al modulo CRM ‣ Rendicontazione ‣ Pipeline per aprire la dashboard Analisi pipeline. Fai clic sulla barra Cerca… nella parte superiore della pagina ed elimina tutti i filtri predefiniti.

Nota

Il filtro Creato il può restare attivo in quanto la variabile potrebbe essere utile da includere nel resoconto.

Successivamente, aggiungi filtri personalizzati facendo clic sull’icona 🔻(triangolo punta in giù) a destra della barra Ricerca… per aprire il menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti. Sotto la colonna Filtri, fai clic su Aggiungi filtro personalizzato per aprire la finestra pop-up Aggiungi filtro personalizzato.

La finestra pop-up Aggiungi filtro personalizzato permette di creare filtri più specifici.

### Aggiungere filtri personalizzati¶

Per generare un resoconto sui lead non seguiti, i filtri devono essere creati rispettando le seguenti condizioni:

>   * Attività scadute: limita i risultati solo ai lead con un’attività assegnata la cui data di scadenza è passata. È possibile modificare questa impostazione in modo da includere anche le attività previste per la data di generazione del resoconto.
> 
>   * Lead non assegnati: esclude i lead non assegnati a un addetto vendite.
> 
>   * Team di vendita specifici: limita i risultati per includere solo i contatti assegnati a uno o più team di vendita. Questo filtro è opzionale e non deve essere incluso se il resoconto è destinato all’intera azienda.
> 
> 


#### Aggiungere un filtro per attività scadute¶

Fai clic sul primo campo per la nuova regola e digita `Attività` nella barra Cerca…, oppure scorri l’elenco per trovarla. Successivamente, accanto ad Attività, fai clic su > (simbolo più grande di) per aprire un nuovo menu a tendina con condizioni secondarie.

Scrivi `Data di scadenza` nella barra Cerca… o scorri per cercare nell’elenco. Fai clic su Data di scadenza per aggiungerla alla regola.

> In seguito, fai clic sul campo successivo e seleziona <= dal menu a discesa. La selezione di questo operatore include tutte le attività con una data di scadenza fino alla data selezionata nel campo successivo.

Il terzo campo può contenere la data di oggi o essere sistemato se necessario.

#### Escludere lead non assegnati¶

Dopo aver filtrato le attività, aggiungi una Nuova regola. In seguito, fai clic sul primo campo per la nuova regola e digita `Addetto vendite` nella barra Cerca…, oppure scorri l’elenco per trovarlo.

Nel secondo campo della regola, seleziona è impostato dal menu a discesa. La selezione di questo operatore esclude tutti lead non assegnati a un addetto vendite specifico.

#### Aggiungere un team di vendita¶

Nota

Questo filtro è opzionale. Per visualizzare i risultati per l’intera azienda, **non** aggiungere questo filtro e continua a Visualizzare i risultati

Per limitare i risultati del resoconto a uno o più team di vendita, fai clic su Nuova regola. In seguito, fai clic sul primo campo della nuova regola e digita `Team vendite` nella barra Ricerca… o scorri l’elenco per trovarla.

Nel secondo campo della regola, seleziona è in dal menu a discesa. La selezione di questo operatore limita i risultati ai team di vendita selezionati nel campo successivo.

Infine, nel terzo campo, seleziona il team di vendita desiderato dal menu a discesa. È possibile aggiungere più team in questo campo, dove ogni parametro viene trattato con un operatore “o” (ad es. “qualsiasi”) nella logica di ricerca.

Un esempio della finestra pop-up **Aggiungi filtro personalizzato** con tutte le regole configurate.¶

## Visualizzare i risultati¶

Nella parte superiore del modulo Aggiungi filtro personalizzato, c’è un’opzione che consente di abbinare qualsiasi o tutte le regole. Per eseguire correttamente il resoconto, devono essere inclusi solo i record che corrispondono a **tutti** i filtri seguenti. Prima di aggiungere i filtri, assicurati che l’opzione tutti sia selezionata in questo campo.

Dopo aver configurato i filtri, fai clic su Aggiungi. Il resoconto risultante visualizza tutti i contatti assegnati a un venditore in cui un’attività è scaduta o è in scadenza alla data corrente. La visualizzazione predefinita è un grafico a barre, in cui i contatti sono raggruppati per _fase_.

Per raggruppare i risultati per venditore, fai clic sull’icona 🔻(triangolo punta in giù) a destra della barra Ricerca… per aprire il menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti. Sotto la sezione Raggruppa per, seleziona Addetto vendite.

Nota

L’opzione per raggruppare per Team di vendita è disponibile anche nella sezione Raggruppa per.

Per passare alla vista _elenco_ , fai clic sull’icona ≣ (elenco) nell’angolo in alto a destra dello schermo.

Suggerimento

> Facendo clic sull’icona (toggle) si apre un menu a discesa di colonne aggiuntive che possono essere aggiunte al resoconto.
> 
> Alcune opzioni vantaggiose per questo tipo di resoconto includono:
> 
>   * Attività: il riassunto delle ultime attività di questo lead.
> 
>   * Chiusura prevista: la data stimata per la vincita del lead.
> 
>   * Probabilità: tasso di successo stimato in base a questa fase.
> 
> 


Vedi anche

[Attività](../../../essentials/activities.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/unattended_leads_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_leads_report.html "Resoconto lead di qualità") |
  * [precedente](lead_scoring.html "Assegnare lead con calcolo previsionale") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconto lead non seguiti


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