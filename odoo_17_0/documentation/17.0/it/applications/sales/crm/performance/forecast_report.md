# Resoconto previsionale — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [precedente](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto previsionale



# Resoconto previsionale¶

Il resoconto _previsionale_ dell’applicazione _CRM_ consente agli utenti di visualizzare le opportunità imminenti e di costruire una previsione delle vendite potenziali. Le opportunità sono raggruppate in base al mese della data di chiusura prevista e possono essere trascinate per modificare la scadenza.

Per accedere al resoconto _previsionale_ , accedi al modulo CRM ‣ Rendicontazione ‣ Previsione.

## Esplorare il resoconto previsionale¶

Il resoconto previsionale predefinito include le opportunità assegnate alla pipeline dell’utente corrente e che si prevede di chiudere entro quattro mesi. Mostra anche le opportunità a cui non è stata assegnata una data di chiusura prevista. Le opportunità sono raggruppate per mese in una vista __(Kanban).

### Data di chiusura prevista¶

Le opportunità sono raggruppate in base alla data assegnata nel campo _Chiusura prevista_ di un modulo opportunità. Per modificare questa data direttamente dalla pagina Previsione, seleziona la scheda Kanban dell’opportunità desiderata, poi fai clic e trascina la scheda nella colonna desiderata.

Nota

L’intervallo di tempo predefinito per le previsioni è _mese_. Si può cambiare facendo clic sul simbolo __(down) icon accanto alla barra Ricerca… nella parte superiore del resoconto. Nel menu a discesa risultante, sotto la voce Raggruppa per, fai clic su Chiusura prevista per espandere l’elenco delle opzioni disponibili e selezionare l’intervallo di tempo desiderato dall’elenco.

Dopo che un’opportunità viene aggiunta a un nuovo mese, il campo _Chiusura prevista_ del modulo dell’opportunità viene aggiornato alla data _ultima_ del nuovo mese.

Suggerimento

Il campo _Chiusura prevista_ può anche essere aggiornato manualmente sulla scheda dell’opportunità. Per farlo, fai clic sulla scheda Kanban di un’opportunità nella pagina Previsione per aprire il modulo con i dettagli dell’opportunità. Fai clic nel campo Chiusura prevista e utilizza il pop-up del calendario per selezionare una nuova data di chiusura.

### Ricavi ripartiti in proporzione¶

Nella parte superiore della colonna di ogni mese della pagina di reportistica previsionale, a destra della barra di avanzamento, si trova la somma delle entrate pro rata per quel periodo di tempo.

I ricavi ripartiti sono calcolati in base alla formula seguente:

\\[\text{Ricavi previsti} \volte \text{Probabilità} = \text{Ricavi ripartiti in proporzione}\\]

Quando le opportunità vengono spostate da una colonna all’altra, le entrate della colonna vengono aggiornate automaticamente per riflettere la modifica.

Example

Un resoconto previsionale per il mese di Giugno include due opportunità:

La prima opportunità, `Global Solutions`, ha un ricavo previsto di `3.800 $` e una probabilità del `90%`. Il risultato è un ricavo proporzionale di `3.420 $`.

La seconda opportunità, `Preventivo per 600 sedie`, ha un ricavo previsto di `22.500 $` e una probabilità del `20%`. Il risultato è un ricavo ripartito in proporzione di `4.500 $`.

Il ricavo combinato pro rata delle opportunità è di `7.920 $`, che viene elencato in cima alla colonna del mese.

Vedi anche

Per maggiori informazioni sull’assegnazione della probabilità alle opportunità, consulta la sezione [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html)

## Visualizzare i risultati¶

Fai clic sull’icona __(grafico area) per modificare la vista grafico. In seguito, fai clic sull’icona corrispondente nella parte superiore del resoconto per passare a un grafico a __(barre), __(linee) o __(torta).

Fai clic su __(pivot) icon per passare alla vista pivot o su __(list) icon per passare alla vista elenco.

Suggerimento

La [vista pivot](../../../essentials/reporting.html#reporting-using-pivot) può essere utilizzata per visualizzare e analizzare i dati in modo più approfondito. È possibile selezionare più misure ed è possibile visualizzare i dati per mese o per fase.

Vedi anche

Per salvare questo resoconto come _preferito_ , consulta la sezione [Preferite](../../../essentials/search.html#search-favorites).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/performance/forecast_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [precedente](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto previsionale


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