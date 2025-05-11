# Creare preventivi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quote_template.html "Modelli preventivo") |
  * [precedente](../send_quotations.html "Send Quotations") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Creare preventivi



# Creare preventivi¶

In Odoo **Vendite** , è possibile creare e inviare preventivi ai clienti. Al momento della conferma di un preventivo, quest’ultimo si trasforma automaticamente in un _ordine di vendita_ che può essere fatturato e pagato.

## Impostazioni preventivo¶

Per accedere alle impostazioni, apri il modulo Vendite ‣ Configurazione ‣ Impostazioni e scorri fino alla sezione Preventivi e ordini.

  * Modelli di preventivo: attiva quest’opzione per creare modelli di preventivo con offerte standard per i prodotti che possono essere selezionati sui moduli di preventivo. Se spunti la casella, apparirà il campo aggiuntivo Modello predefinito con un link alla pagina Modelli di preventivo.

  * Firma online: richiedi una firma digitale per confermare gli ordini.

  * Pagamento online: richiedi un pagamento anticipato online ai clienti per confermare gli ordini. Puoi anche richiedere un pagamento totale o parziale (tramite acconto). Quando la casella viene selezionata, appare il campo aggiuntivo Importo pagamento anticipato (%). Inoltre, apparirà anche il collegamento alla pagina Fornitori di pagamento.

  * Validità predefinita del preventivo: stabilisci il periodo di validità (in giorni) del preventivo.

  * Ricorrenza predefinita: seleziona un periodo predefinito dal menu a discesa per usare un periodo di ricorrenza per un nuovo preventivo.

  * Avvisi vendita: ricevi messaggi di avviso sugli ordini che includono prodotti o clienti specifici.

  * Creatore preventivi PDF: personalizza l’aspetto dei preventivi grazie a intestazioni, descrizioni dei prodotti, piè di pagina e altro.

  * Blocco vendite confermate: assicurati che gli ordini già confermati non vengano modificati ulteriormente.

  * Fattura proforma: invia fatture proforma ai clienti.




Per attivare una di queste impostazioni, spunta la casella accanto all’opzione desiderata. In seguito, fai clic su Salva.

## Dashboard preventivi¶

La dashboard dei _Preventivi_ è la pagina che appare quando l’app Vendite è aperta.

Per impostazione predefinita, la dashboard dei Preventivi mostra tutti i preventivi correlati all’utente corrente, come indicato dal filtro predefinito I miei preventivi presente nella barra di ricerca.

Nota

Per visualizzare _tutti_ i preventivi nel database, elimina il filtro I miei preventivi dalla barra di ricerca.

I preventivi appaiono nella vista elenco predefinita ma possono essere visualizzati anche nella vista __ Kanban, __ calendario, tabella __ pivot, __ grafico oppure nella vista __ Attività.

Per visualizzare e/o modificare qualsiasi preventivo elencato nella dashboard Preventivi, fai clic sulla riga di preventivo desiderata dall’elenco e Odoo mostrerà il modulo specifico relativo al preventivo selezionato.

## Creare un preventivo¶

Per creare un preventivo, apri l’app Vendite e fai clic sul pulsante Nuovo, situato nell’angolo in alto a sinistra della dashboard Preventivi.

Importante

Il pulsante Nuovo è presente **solo** se la dashboard dei Preventivi viene visualizzata nella vista elenco o Kanban.

Dopo aver fatto clic sul pulsante Nuovo, apparirà un modulo di preventivo vuoto con vari campi e schede da configurare.

Inizia aggiungendo il nome del cliente nel campo Cliente nella parte alta del modulo. Si tratta di un campo **obbligatorio**.

Se le informazioni del cliente sono già presenti nel database, i campi Indirizzo di fatturazione e Indirizzo di consegna si popolano automaticamente con le informazioni salvate per questi campi, in base ai dati del record di contatto del cliente (che si trova nell’applicazione **Contatti**).

Se il cliente è stato referenziato da un altro cliente o contatto, inserisci il suo nome nel campo Segnalatore.

Se viene selezionato un Segnalatore, apparirà il campo, Piano di provvigione, in cui è possibile selezionare una commissione dal menu a discesa. Questa provvigione viene riconosciuta al contatto selezionato nel campo Segnalatore.

Successivamente, se non sono già stati inseriti automaticamente i dati del cliente, inserisci gli indirizzi appropriati nei campi Indirizzo di fatturazione e Indirizzo di consegna. Entrambi i campi sono **obbligatori**.

In seguito, se lo desideri, scegli un Modello di preventivo dal campo a tendina da applicare a questo preventivo. Nota che potrebbero comparire alcuni campi aggiuntivi, a seconda del modello selezionato.

La data predefinita che appare nel campo Scadenza si basa sul numero configurato nell’impostazione Validità predefinita del preventivo (in Vendite ‣ Configurazione ‣ Impostazioni).

Suggerimento

Quando si utilizza un modello di preventivo, la data del campo Scadenza si basa sulla cifra Validità del preventivo del modulo del modello.

Se il preventivo è per un prodotto o abbonamento ricorrente, seleziona il Piano ricorrente desiderato dal menu a discesa specifico.

Inoltre, è possibile selezionare un Listino prezzi specifico da applicare al preventivo.

Infine, seleziona i Termini di pagamento più adatti da usare per il preventivo.

### Scheda righe ordine¶

La prima scheda sul modulo del preventivo è la scheda Righe ordine.

In questa scheda, seleziona i prodotti e le relative quantità per aggiungerle al preventivo.

Due sono i modi che permettono di aggiungere prodotti al preventivo da questa scheda.

Fai clic su Aggiungi un prodotto, seleziona l’articolo desiderato dal campo a discesa Prodotto e procedi alla regolazione della quantità del prodotto selezionato, se necessario.

In alternativa, fai clic su Catalogo per visualizzare una pagina separata, che mostra ogni articolo (e ogni potenziale variante di prodotto) in un catalogo organizzato, con articoli organizzabili per Categoria prodotto e Attributi.

Da qui, è sufficiente individuare gli articoli desiderati, fare clic sul pulsante __ Aggiungi sulla scheda prodotto e scegliere la quantità, se necessario. Infine, fai clic sul pulsante Torna al preventivo nell’angolo in alto a sinistra per tornare al preventivo, dove gli articoli del catalogo appena selezionati si troveranno nella scheda Righe ordine.

Se nel preventivo è necessario organizzare adeguatamente più voci, fai clic su Aggiungi una sezione, inserisci un nome per la sezione e trascina l’intestazione della sezione nella posizione desiderata tra le voci della scheda Righe ordine. Il titolo della sezione appare in grassetto.

Se necessario, fai clic su Aggiungi nota sotto una determinata riga prodotto per aggiungere una nota personalizzata su quel prodotto specifico. La nota appare in corsivo. In seguito, se necessario, trascina la nota sotto la riga prodotto desiderata.

Sotto le righe prodotto, sono presenti alcuni pulsanti da poter utilizzare come: Codice buono sconto, Promozioni, Sconto e/o Aggiungi spedizione.

Vedi anche

  * [Use eWallets and gift cards](../products_prices/ewallets_giftcards.html)

  * [Discount and loyalty programs](../products_prices/loyalty_discount.html)

  * [Pricelists, discounts, and formulas](../products_prices/prices/pricing.html)




### Scheda prodotti opzionali¶

Apri la scheda Prodotti opzionali per selezionare prodotti correlati che possono essere presentati al cliente e che potrebbero comportare un aumento del prezzo.

Ad esempio, se il cliente vuole comprare un auto, un prodotto opzionale da offrire potrebbe essere un _gancio di traino_.

Vedi anche

[Prodotti opzionali](optional_products.html)

### Scheda Altre informazioni¶

Nella scheda Altre informazioni, sono presenti varie configurazioni legate al preventivo, divise in quattro sezioni diverse: Vendite, Consegna, Fatturazione e Monitoraggio.

Nota

Alcuni campi appaiono **solo** se sono state configurate impostazioni e opzioni specifiche.

#### Sezione vendite¶

Nella sezione Vendite della scheda Altre informazioni, è possibile configurare campi specifici legati alle vendite.

  * Addetto vendite: assegna un venditore dal menu a tendina da associare a questo preventivo. Per impostazione predefinita, in questo campo è selezionato l’utente che ha originariamente creato il preventivo.

  * Team di vendita: assegna un team vendite specifico a questo preventivo. Se l” addetto vendite selezionato è un membro del team vendite, il team viene aggiunto nel campo correlato.

  * Azienda: seleziona un’azienda dal menu a tendina a cui associare il preventivo. Questo campo appare solo quando si lavora in un ambiente multiaziendale.

  * Firma online: seleziona questa casella di controllo per richiedere una firma online del cliente per confermare l’ordine. Questo campo appare solo se è stata attivata l’impostazione _Firma online_.

  * Pagamento online: selezionando questa casella di controllo e inserendo una percentuale desiderata nel campo adiacente, richiedi al cliente un pagamento online (per la percentuale designata dell’importo totale) per confermare l’ordine. Questo campo appare solo se è stata attivata l’impostazione _Pagamento online_.

  * Riferimento cliente: Inserisci un ID di riferimento personalizzato per questo cliente. L’ID di riferimento inserito può contenere lettere, numeri o una combinazione di entrambi.

  * Tag: aggiungi tag specifici all’offerta per una maggiore organizzazione e una migliore ricercabilità nell’applicazione Odoo **Vendite**. Se necessario, è possibile aggiungere più tag.




#### Sezione Consegna¶

Nella sezione Consegna della scheda Altre informazioni, è possibile configurare campi specifici legati alla consegna.

  * Peso spedizione: visualizza il peso degli articoli spediti. Questo campo non è modificabile. Il peso dei prodotti viene configurato nelle schede dei singoli prodotti.

  * Termini di resa: seleziona un termine di resa (termine commerciale internazionale) da usare come termine predefinito per transazioni internazionali.

  * Ubicazione termine di resa: se utilizzi un termine di resa, inserisci in questo campo la località internazionale.

  * Politica di spedizione: seleziona la politica di spedizione desiderata dal menu a discesa. Se tutti i prodotti vengono consegnati in una sola volta, l’ordine di consegna viene programmato in base al miglior tempo di consegna del prodotto. Altrimenti, si basa sul tempo di consegna più breve. Le opzioni disponibili sono: Appena possibile o Quando tutti i prodotti sono pronti.

  * Data di consegna: fai clic sul campo vuoto per visualizzare un calendario dal quale è possibile selezionare la data di consegna del cliente. Se non è richiesta una data personalizzata, fai riferimento alla data prevista elencata a destra del campo.




#### Sezione Fatturazione¶

Nella sezione Fatturazione della scheda Altre informazioni, è possibile configurare campi specifici legati alla fatturazione.

  * Posizione di bilancio: seleziona una posizione di bilancio da usare per adattare imposte e conti per clienti o ordini di vendita/fatture specifici. Il valore predefinito deriva dal cliente. Se si sceglie un valore per questo campo, appariranno un’icona e il link cliccabile __ Aggiorna imposte. Dopo aver fatto clic, le imposte per il cliente e preventivo specifici sono aggiornate. Inoltre, apparirà anche una finestra di conferma.

  * Conto analitico: seleziona un conto analitico da applicare al cliente/preventivo.




#### Sezione Monitoraggio¶

Nella sezione Monitoraggio della scheda Altre informazioni, è possibile configurare campi specifici.

  * Documento di origine: inserisci il riferimento del documento da cui è stato creato il preventivo/ordine di vendita, se applicabile.

  * Opportunità: seleziona l’opportunità specifica (dall’app **CRM**) correlata al preventivo, se applicabile.

  * Campagna: seleziona la campagna di marketing correlata al preventivo, se applicabile.

  * Mezzo: seleziona il metodo grazie al quale è stato creato il preventivo (ad es. _e-mail_), se applicabile.

  * Origine: seleziona la fonte del link usato per generare il preventivo (ad es. _Facebook_), se applicabile.




Vedi anche

[Link tracker](../../../websites/website/reporting/link_tracker.html)

### Scheda Note¶

Nella scheda Note del modulo di preventivo, inserisci qualsiasi nota interna specifica sul preventivo stesso o sul cliente.

## Inviare e confermare preventivi¶

Una volta configurati tutti i campi e le schede necessarie, è il momento di inviare il preventivo al cliente per la conferma. Dopo la conferma, il preventivo si trasforma in un ordine di vendita ufficiale.

Nella parte alta del modulo troverai una serie di pulsanti:

  * Invia per e-mail: quando fai clic sul questo pulsante, appare una finestra pop-up con il nome e l’indirizzo e-mail del cliente nel campo Destinatari, il preventivo (e l’ID di riferimento) nel campo Oggetto e un breve messaggio predefinito nel corpo dell’e-mail, che può essere modificato, se necessario.

In basso, viene allegata una copia in PDF del preventivo. Una volta pronto, fai clic su Invia per inviare il preventivo via e-mail al cliente, in modo che possa esaminarlo e confermarlo.

  * Invia fattura proforma: questo pulsante appare **solo** se l’impostazione _Fattura proforma_ è stata attivata. Quando fai clic, appare una finestra pop-up con il nome e l’indirizzo e-mail del cliente nel campo Destinatari, la fattura _Proforma_ (e l’ID di riferimento) nel campo Oggetto e un breve messaggio predefinito nel corpo dell’e-mail, che può essere modificato, se necessario.

In basso, viene allegata una copia in PDF del preventivo. Una volta pronto, fai clic su Invia per inviare il preventivo via e-mail al cliente, in modo che possa esaminarlo e confermarlo.

  * Conferma: se clicchi su questo pulsante, il preventivo viene confermato e lo stato passa a Ordine di vendita.

  * Anteprima: se fai clic su questo pulsante, Odoo rivela un’anteprima dell’offerta che il cliente vede quando accede al suo portale clienti. Fai clic sul link __ Torna alla modalità di modifica nella parte superiore della pagina di anteprima, nel banner blu, per tornare al modulo del preventivo.

  * Annulla: se fai clic su questo pulsante, il preventivo viene annullato.




Nota

Se l’impostazione _Blocca vendite confermate_ è attiva, gli ordini di vendita verranno bloccati e verrà indicato come tale anche nel modulo dell’ordine di vendita.

A questo punto, il preventivo è stato confermato, trasformato in ordine di vendita e ora è pronto per essere fatturato e pagato.

Per maggiori informazioni sulla fatturazione, consulta la sezione [Fatture basate su quantità ordinate o consegnate](../invoicing/invoicing_policy.html)

Vedi anche

  * [Modelli preventivo](quote_template.html)

  * [Date di scadenza per i preventivi](deadline.html)

  * [Firme online per confermare gli ordini](get_signature_to_validate.html)

  * [Conferma ordine tramite pagamento online](get_paid_to_validate.html)

  * [Creazione preventivi in PDF](pdf_quote_builder.html)

  * [Fatture proforma](../invoicing/proforma.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/create_quotations.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quote_template.html "Modelli preventivo") |
  * [precedente](../send_quotations.html "Send Quotations") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Creare preventivi


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