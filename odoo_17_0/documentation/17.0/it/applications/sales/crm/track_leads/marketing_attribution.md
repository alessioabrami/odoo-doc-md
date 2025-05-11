# Resoconti attribuzione attività marketing — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_distribution_report.html "Resoconto distribuzione lead") |
  * [precedente](resellers.html "Partner") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconti attribuzione attività marketing



# Resoconti attribuzione attività marketing¶

Utilizza l’applicazione _CRM_ di Odoo per compilare un _resoconto attribuzione attività marketing_ , che analizza l’origine dei lead e li raggruppa in modo tale da calcolare l’impatto complessivo del marketing sulla generazione di lead, l’attribuzione, il tasso di vincita e altro ancora.

## Dashboard analisi lead¶

Inizia accedendo alla dashboard Analisi lead tramite il percorso CRM ‣ Rendicontazione ‣ Lead.

Suggerimento

È possibile accedere ai resoconti anche dall’app CRM ‣ Lead, che è accessibile **solamente** se la funzionalità _Lead_ è stata attivata nella pagina delle _Impostazioni_.

Se la funzionalità _lead_ **non** è stata attivata, la dashboard può essere utilizzata per eseguire resoconti. È possibile accedervi seguendo il percorso CRM ‣ Vendite ‣ La mia pipeline.

Entrambe le dashboard contengono i criteri _Filtri_ e _Raggruppa per_ necessari per eseguire un resoconto di attribuzione.

Vedi anche

  * [Convertire lead in opportunità](../acquire_leads/convert.html)

  * [Creare lead](../acquire_leads/email_manual.html)




La vista __(grafico) viene mostrata per impostazione predefinita con i filtri :guilabel:`Attivo o inattivo e Creato il: [anno corrente] attivi nella barra Cerca…. La vista grafico mostra il numero di lead generati per mese e per team di vendita con ogni team di vendita assegnato al proprio colore a seconda del mese visualizzato.

Passa alla vista __(elenco) facendo clic sull’icona corrispondente situata nella parte in alto a destra della dashboard. Questo consente ai lead di essere visualizzati facilmente nel raggruppamento configurato tramite i parametri _Raggruppa per_.

## Aggiungere parametri UTM¶

Gli _Urchin Tracking Modules (UTM)_ sono frammenti di testo incorporati negli URL che vengono utilizzati per tracciare i dati dei visitatori. Questi includono parametri relativi al modo in cui un visitatore ha raggiunto il link, come il tipo di sito web visitato e/o la campagna di marketing da cui proviene la visita.

Odoo può utilizzare questi UTM come parametri nel resoconto attribuzione attività marketing per tracciare le metriche e le prestazioni delle campagne di marketing.

### Creare UTM¶

In Odoo, è possibile utilizzare il [link tracker](../../../websites/website/reporting/link_tracker.html) per creare e configurare UTM.

È possibile generare UTM automaticamente grazie alle applicazioni [E-mail marketing](../../../marketing/email_marketing.html) e [Marketing automation](../../../marketing/marketing_automation.html).

I parametri UTM utilizzati in un resoconto attribuzione attività marketing sono _Mezzo_ , _Origine_ e _Campagna_ , in ordine decrescente di copertura.

  * Il _Mezzo_ è l’UTM con la copertura più ampia e viene utilizzato per identificare il mezzo utilizzato per accedere al link. Può includere mezzi come i social media, le e-mail o il costo per clic (CPC).

  * Il parametro _Origine_ è più ristretto e viene utilizzato per identificare la fonte del traffico. Ad esempio, il nome di un sito web, il motore di ricerca utilizzato o una specifica piattaforma di social media.

  * Il parametro _Campagna_ è il più ristretto e può tracciare campagne di marketing specifiche in base al nome. Può includere il nome di un contest o di un prodotto, il tipo di vendita, ecc.




## Creare resoconti¶

Per iniziare a creare un resoconto, fai clic sull’icona __(freccia giù) a destra della barra Cerca… per visualizzare l’elenco dei parametri di filtraggio e raggruppamento.

I Filtri situati nella colonna di sinistra delle opzioni di ricerca, possono essere usati per mantenere solo i risultati che soddisfano il filtro scelto. Ad esempio, selezionando il filtro Vinto si possono visualizzare solo i lead che sono stati vinti nel resoconto di attribuzione.

La colonna centrale Raggruppa per viene utilizzata per organizzare i risultati in gruppi e può essere usata con o senza filtri.

Suggerimento

La configurazione di più opzioni Raggruppa per crea gruppi annidati, a seconda dell’opzione selezionata per prima. Ad esempio, selezionando Mezzo, seguito da Origine e poi Campagna, nella colonna Raggruppa per, tutti i risultati verranno ordinati _prima_ per mezzo, _poi_ per le fonti specifiche di ciascun mezzo, seguite dalle campagne di ciascuna fonte.

È possibile verificarlo osservando la direzione e l’ordine delle selezioni nel riquadro del gruppo che appare nella barra Cerca….

Example

Per un primo resoconto utile:

#. From the Filters column, select the Active filter to view only leads that are still marked as active. #. From the Group By column, select (in this specific order) Source, followed by the City or Country, depending on which grouping is more relevant.

Questo resoconto contiene tutti i lead attivi, raggruppati prima in base all’origine del lead, poi in base alla città o al Paese di provenienza. È utile per vedere la densità delle opportunità attive ordinate per località.

Grazie a questi dati, le campagne di marketing, come le conferenze o i cartelloni pubblicitari, possono essere indirizzate alle località che generano il maggior numero di entrate potenziali. Allo stesso modo, si può prestare maggiore attenzione all’aumento della diffusione nelle località in cui le campagne di marketing esistenti sono meno efficaci.

## Esportare resoconti¶

Per configurare i parametri del resoconto, inizia accedendo alla __(vista pivot) sulla dashboard Analisi lead.

Fai clic sul pulsante Misure per visualizzare le misure disponibili per il resoconto. Seleziona le misure desiderate dal menu a discesa (è possibile selezionare più di una) e verifica che le misure, i filtri e i gruppi siano visualizzati correttamente nella tabella pivot. Questo assicura che i dati siano pronti per l’esportazione.

Per esportare rapidamente i dati in un elenco, come file .xlsx, accedi alla vista __(vista elenco). Fai clic sull’icona Azioni __(ingranaggio), situata a destra del pulsante Analisi lead nella parte in alto a sinistra della pagina e fai clic su __ Esporta tutto. Il resoconto verrà scaricato automaticamente come file .xlsx.

Per maggiori opzioni di esportazione, il resoconto può essere esportato nell’app Odoo _Documenti_. Dalla vista __(vista elenco) della pagina Analisi lead facendo clic sull’icona Azioni __(ingranaggio) di nuovo. Ora, accedi ai __ fogli di calcolo e fai clic su __ Inserisci elenco in foglio di calcolo. Apparirà una finestra dal titolo Seleziona un foglio di calcolo da inserire nell’elenco.

Il resoconto può essere rinominato utilizzando il campo `Nome dell'elenco`. Il numero di elementi del resoconto può essere impostato con il campo etichettato: `Inserisci i primi _ record dell'elenco`. Successivamente, seleziona un nuovo Foglio di calcolo vuoto, oppure esegui l’esportazione in un foglio di calcolo esistente. Infine, fai clic sul pulsante Conferma.

Per esportare il resoconto come file .xlsx, da usare in un programma di fogli di calcolo esterno, fai clic sull’icona Azioni __(ingranaggio) e seleziona l’opzione __ Esporta tutto. Se richiesto, scegli una posizione del file, assegna un nome al file e fai clic su Salva.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/marketing_attribution.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_distribution_report.html "Resoconto distribuzione lead") |
  * [precedente](resellers.html "Partner") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Resoconti attribuzione attività marketing


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