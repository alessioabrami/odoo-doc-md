# Prezzo medio sulla merce resa — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_units.html "Unità fiscali") |
  * [precedente](multi_currency.html "Sistema multi valuta") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Prezzo medio sulla merce resa



# Prezzo medio sulla merce resa¶

_La valutazione del costo medio_ (AVCO) è un metodo di valutazione del magazzino che valuta il costo in base al costo totale dei beni acquistati o prodotti durante un periodo, diviso per il numero totale di articoli disponibili. La valutazione del magazzino viene utilizzata per:

  * riflettere il valore delle attività di un’azienda;

  * tenere traccia dell’importo dei beni non venduti;

  * contabilizzare il valore monetario di beni che non hanno ancora generato profitto;

  * rendicontare il flusso di merci nel corso del trimestre.




Siccome il metodo AVCO utilizza la media ponderata per valutare il costo, è adatto alle aziende che vendono solo pochi prodotti diversi in grandi quantità. In Odoo, questa analisi dei costi viene _aggiornata automaticamente_ ogni volta che si ricevono i prodotti.

In questo modo, quando le consegne vengono rispedite al fornitore, Odoo genera automaticamente registrazioni contabili per riflettere la modifica nella valutazione del magazzino. Tuttavia, Odoo **non** aggiorna automaticamente il calcolo AVCO, perché questo può potenzialmente creare incongruenze con la valutazione del magazzino.

Nota

Questo documento affronta un caso d’uso specifico a scopo teorico. Per capire come configurare e utilizzare il metodo AVCO, consulta la documentazione relativa alla [configurazione della valutazione del magazzino](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.html).

Vedi anche

  * [Utilizzare la valutazione del magazzino](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/using_inventory_valuation.html)

  * [Altri metodi di valutazione del magazzino](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.html#inventory-warehouses-storage-costing-methods)




## Configurazione¶

Per utilizzare la valutazione del costo medio di magazzino per un prodotto, accedi all’app Magazzino ‣ Configurazione ‣ Categorie prodotto e seleziona la categoria che utilizzerà il metodo AVCO. Sulla pagina relativa alla categoria del prodotto, imposta il Metodo calcolo costi su `Costo medio (CU)` e la Valutazione magazzino su `Automatizzata`.

Vedi anche

[Configurazione valutazione magazzino](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.html)

## Utilizzare la valutazione del costo medio¶

Il metodo del costo medio sistema la valutazione del magazzino quando i prodotti vengono ricevuti in un deposito. La presente sezione spiega come funziona ma se non hai bisogno della spiegazione passa alla sezione caso pratico reso al fornitore.

### Formula¶

Quando arrivano nuovi prodotti, il nuovo costo medio per ogni prodotto viene ricalcolato utilizzando la formula:

\\[Avg~Cost = \frac{(Old~Qty \times Old~Avg~Cost) + (Incoming~Qty \times Purchase~Price)}{Final~Qty}\\]

  * **Old Qty** : quantità prodotto in stock prima di ricevere una nuova consegna;

  * **Old Avg Cost** : costo medio calcolato per un singolo prodotto dalla valutazione di magazzino precedente;

  * **Incoming Qty** : numero di prodotti in arrivo con la nuova consegna;

  * **Purchase Price** : prezzo stimato dei prodotti alla ricezione dei prodotti stessi (dato che la fattura fornitore potrebbe arrivare più tardi). L’importo include non solo il prezzo dei prodotti ma anche i costi aggiuntvi come spedizione, imposte e [costi sbarcati](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/landed_costs.html). Al momento della ricezione della fattura fornitore, il prezzo verrà sistemato;

  * **Final Qty** : quantità disponibile in stock dopo il movimento di magazzino.




Importante

Quando i prodotti lasciano il deposito, il costo medio **non** cambia. Scopri perché la valutazione del costo medio **non** viene rettificata qui.

### Calcolare il costo medio¶

Per capire come cambia il costo medio di un prodotto a ogni spedizione, tieni a mente la seguente tabella di operazioni e movimenti di magazzino. Ognuno di essi rappresenta un esempio diverso di come viene influenzata la valutazione del costo medio.

Operazione | Valore in ingresso | Valore di magazzino | Qtà disponibile | Costo medio  
---|---|---|---|---  
|  | 0 $ | 0 | 0 $  
Ricevere 8 tavoli a 10$/unità | 8*10$ | 80 € | 8 | 10 $  
Ricevere 4 tavoli a 16$/unità | 4*16$ | 144$ | 12 | 12 $  
Consegnare 10 tavoli | -10*12 $ | 24 $ | 2 | 12 $  
  
Exercise

Assicurati di aver compreso i calcoli di cui sopra rivedendo l’esempio “Ricevere 8 tavoli a 10$/unità”.

Inizialmente, le scorte relative al prodotto sono pari a 0, quindi tutti i valori sono pari a 0 $.

Durante la prima operazione di magazzino, vengono ricevuti `8` tavoli a un prezzo pari a `10 $` per unità. Il costo medio viene calcolato utilizzando la formula:

\\[Avg~Cost = \frac{0 + 8 \times $10}{8} = \frac{$80}{8} = $10\\]

  * Dato che la _quantità in entrata_ dei tavoli equivale a `8` e il _prezzo di acquisto_ per ognuno è pari a `10 $`,

  * Il valore di magazzino nel numeratore è pari a `80 $`;

  * `80 $` viene diviso per l’importo totale di tavoli da conservare, `8`;

  * `10 $` è il costo medio di un singolo tavolo dalla prima spedizione.




Per fare la verifica in Odoo, apri l’app _Acquisti_ e ordina `8` quantità di un nuovo prodotto, `Tavolo`, senza aver eseguito movimenti di magazzino, con un costo pari a `10 $` l’uno.

Nel campo Categoria prodotto della tabella presente nella scheda Informazioni generali del modulo del prodotto, fai clic sull’icona ➡️ (freccia) per aprire un Link esterno e modificare la categoria prodotto. Imposta il Metodo di calcolo costi su `Costo medio (AVCO)` e la Valutazione magazzino su `Automatizzata`.

Successivamente, torna all’ordine di acquisto. Fai clic su Conferma ordine e fai clic su Ricevi prodotti per confermare la ricezione.

In seguito, verifica il record di valutazione del magazzino generato dalla ricezione del prodotto aprendo l’app Magazzino ‣ Rendicontazione ‣ Valutazione magazzino. Seleziona il menu a discesa per il prodotto `Tavolo` e visualizza la colonna Valore totale per il _livello di valutazione_ (valutazione delle magazzino in un momento specifico = quantità disponibile * prezzo unitario). Gli 8 tavoli in stock valgono 80 $.

Suggerimento

Quando il Metodo calcolo costi della categoria prodotto è impostato su AVCO, anche il costo medio di un prodotto viene visualizzato nel campo Costo, sotto la sezione Informazioni generali, sulla pagina prodotto stessa.

#### Consegna prodotto (caso d’uso)¶

Per le spedizioni in uscita, i prodotti in uscita non influenzano la valutazione del costo medio. Anche se la valutazione del costo medio non viene ricalcolata, il valore del magazzino diminuisce comunque perché il prodotto viene prelevato dal magazzino e consegnato al cliente.

Exercise

Per dimostrare che la valutazione del costo medio non viene ricalcolata, esaminiamo l’esempio «Consegnare 10 tavoli».

\\[Avg~Cost = \frac{12 \times $12 + (-10) \times $12}{12-10} = \frac{24}{2} = $12\\]

  1. Dato che 10 tavoli sono in partenza per i clienti, la _quantità in entrata_ ora corrisponde `-10`. Il costo medio precedente (`$12`) viene utilizzato al posto del _prezzo di acquisto_ del fornitore;

  2. il _valore magazzino in entrata_ corrisponde a `-10 * $12 = -$120`;

  3. Il precedente _valore di magazzino_ (`$144`) viene aggiunto al _valore di magazzino in entrata_ (`-$120`), quindi `$144 + -$120 = $24`;

  4. Di conseguenza, rispetto al valore iniziale corrispondente a `12`, restano solo `2` tavoli dopo averne spediti `10`;

  5. `$24 / 2 = $12`, ovvero lo stesso costo medio dell’operazione precedente.




Per fare una verifica in Odoo, vendi `10` tavoli tramite l’app _Vendite_ , convalida la consegna e poi controlla il record di valutazione del magazzino tramite il percorso Magazzino ‣ Rendicontazione ‣ Valutazione magazzino. Nel livello di valutazione più alto, la consegna di `10` tavoli riduce il valore del prodotto di `-$120`.

**Nota** : ciò che non è rappresentato in questo record di valutazione del magazzino è il ricavo ottenuto da questa vendita, quindi la diminuzione non rappresenta una perdita per l’azienda.

## Restituire prodotti al fornitore (caso d’uso)¶

Poiché il prezzo pagato ai fornitori può differire dal prezzo a cui il prodotto è valutato con il metodo AVCO, Odoo gestisce gli articoli restituiti in modo specifico.

  1. I prodotti vengono restituiti ai fornitori al prezzo di acquisto originale, ma

  2. la valutazione del costo interno non cambia.




La tabella di esempio in alto viene aggiornata come segue:

Operazione | Qtà*Costo medio | Valore di magazzino | Qtà disponibile | Costo medio  
---|---|---|---|---  
|  | 24 $ | 2 | 12 $  
Restituire 1 tavolo pagato 10 $ | -1 * $12 | 12 $ | 1 | 12 $  
  
In altre parole, i resi ai venditori sono percepiti da Odoo come un’altra forma di uscita del prodotto dal magazzino. Per Odoo, poiché il tavolo è valutato 12 $ per unità, il valore di magazzino si riduce di `12 $` quando il prodotto viene restituito. Il prezzo di acquisto iniziale di `10 $` non è correlato al costo medio del tavolo.

Example

Per restituire un tavolo acquistato a `10 $`, apri la ricezione dall’app _Magazzino_ degli 8 tavoli acquistati nell’esercizio 1 accedendo alla Panoramica magazzino, per poi fare clic su Ricezioni e selezionare quella desiderata.

In seguito, fai clic su Reso sull’ordine di consegna convalidato e modifica la quantità a `1` nella finestra relativa al trasferimento inverso. Questo comporta la creazione di una spedizione in uscita per il tavolo. Seleziona Convalida per confermare la spedizione in uscita.

Torna a Magazzino ‣ Rendicontazione ‣ Valutazione magazzino per vedere come la spedizione in uscita riduce il valore del magazzino di 12 $.

### Eliminare errori di valutazione del magazzino nei prodotti in uscita¶

Possono verificarsi incongruenze nelle scorte di un’azienda quando la valutazione del costo medio viene ricalcolata sulle spedizioni in uscita.

Per dimostrare questo errore, la seguente tabella illustra uno scenario in cui 1 tavolo viene spedito a un cliente e un altro viene restituito a un fornitore al prezzo acquistato.

Operazione | Qtà*Prezzo | Valore di magazzino | Qtà disponibile | Costo medio  
---|---|---|---|---  
|  | 24 $ | 2 | 12 $  
Spedire 1 prodotto al cliente | -1 * 12 $ | 12 $ | 1 | 12 $  
Restituire 1 prodotto comprato inizialmente a 10 $ | -1 * 10 $ | **2 $** | **0** | 12 $  
  
Nell’operazione finale di cui sopra, la valutazione finale del magazzino per il tavolo è di `2 $` anche se sono rimasti `0` tavoli in magazzino.

Metodo corretto

Utilizza il costo medio per valutare il reso. Questo non significa che l’azienda riceve 12 $ per un acquisto di 10 $. L’articolo restituito per 10 $ è valutato internamente a 12 $. La variazione di valore del magazzino rappresenta un prodotto del valore di 12 $ che non viene più contabilizzato tra le attività dell’azienda.

## Contabilità anglosassone¶

In aggiunta all’utilizzo del metodo AVCO, le aziende che utilizzano la **contabilità anglosassone** posseggono anche un conto di deposito che tiene traccia dell’importo da pagare ai fornitori. Una volta che un fornitore consegna un ordine, il **valore di magazzino** aumenta in base al prezzo del fornitore stabilito per i prodotti che sono entrati in stock. Il conto deposito (chiamato **conto ingresso magazzino**) riceve il denaro e viene riconciliato solo alla ricezione della fattura fornitore.

Vedi anche

  * [Anglosassone vs. continentale](../../../inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.html#inventory-warehouses-storage-accounting-types)




La seguente tabella riporta le registrazioni contabili e i conti. Il conto _ingresso magazzino_ memorizza il denaro destinato a pagare i fornitori quando la fattura del fornitore non è ancora stata ricevuta. Per bilanciare i conti quando si restituiscono prodotti che presentano una differenza di prezzo tra il prezzo di **valutazione** del prodotto e il prezzo di acquisto, viene creato un conto _differenza di prezzo_.

Operazione | Ingresso magazzino | Diff prezzo | Valore di magazzino | Qtà disponibile | Costo medio  
---|---|---|---|---|---  
|  |  | 0 $ | 0 | 0 $  
Ricevere 8 tavoli a 10 $ | (80 $) |  | 80 € | 8 | 10 $  
Ricevere fattura fornitore pari a 80 $ | 0 $ |  | 80 € | 8 | 10 $  
Ricevere 4 tavoli a 16 $ | (64 $) |  | 144$ | 12 | 12 $  
Ricevere fattura fornitore pari a 64 $ | 0 $ |  | 144$ | 12 | 12 $  
Consegnare 10 tavoli al cliente | 0 $ |  | 24 $ | 2 | 12 $  
Restituire 1 tavolo comprato inizialmente a 10 $ | **10 $** | **2 $** | **12 $** | 1 | 12 $  
Ricevere rimborso fornitore 10 $ | 0 $ | 2 $ | 12 $ | 1 | 12 $  
  
### Ricezione prodotto¶

#### Riepilogo¶

Al momento della ricezione del prodotto, Odoo assicura che le aziende possano pagare i beni acquistati spostando, in via preventiva, un importo corrispondente al prezzo dei beni ricevuti nel [conto passivo](cheat_sheet.html), **Ingresso magazzino**. Successivamente, una volta ricevuta la fattura, l’importo nel conto deposito viene trasferito nel _Conto di debito_. I trasferimenti in questo conto indicano che la fattura è stata pagata. Il conto **ingresso magazzino** viene riconciliato al momento della ricezione della fattura fornitore.

La valutazione di magazzino è un metodo per calcolare quanto vale internamente ogni prodotto nelle scorte. Dato che c’è una differenza tra il prezzo di **valutazione** del prodotto e l’effettivo prezzo di **acquisto** del prodotto stesso, il conto **Valutazione magazzino** non è collegato alle operazioni di credito e debito del conto **Ingresso magazzino**.

Per concettualizzare tutto questo, segui la ripartizione.

#### Conti bilanciati con prodotti ricevuti¶

In questo esempio, un’azienda inizia con zero unità del prodotto `tavolo`, nelle scorte. In seguito, vengono ricevuti 8 tavoli dal fornitore:

  1. Il conto **Ingresso magazzino** conserva `80 $` del credito dovuto al venditore. L’importo in questo conto non è correlato al valore di magazzino.

  2. vengono **ricevuti** tavoli del valore di `80 $` (**debito** per il conto _valore magazzino_ di `80 $`) e

  3. bisogna **pagare** `80 $` per i beni ricevuti (**credito** per il conto _Ingresso magazzino_ pari a `80 $`).




##### In Odoo¶

Odoo genera una registrazione contabile quando vengono ricevute spedizioni che utilizzano il metodo di calcolo AVCO. Configura un Conto differenza di prezzo selezionando l’icona ➡️ (freccia) accanto al campo Categoria prodotto sulla pagina del prodotto.

Nella sezione Proprietà conto, crea un nuovo Conto differenza prezzo digitando il nome del conto e facendo clic su Crea e modifica. Successivamente, imposta il Tipo di conto su `Spese` e fai clic su Salva.

In seguito, ricevi la spedizione nell’app _Acquisti_ o _Magazzino_ e apri il modulo Contabilità ‣ Contabilità ‣ Registrazioni contabili. Nell’elenco, trova il Riferimento che corrisponde all’operazione di ricezione in magazzino per un prodotto specifico.

Fai clic sulla riga relativa a 8 tavoli. La registrazione contabile mostra che una volta ricevuti gli 8 tavoli, il conto `Valutazione scorte` è aumentato di `80 $`. Al contrario, il conto **ingresso magazzino** (impostato sul conto `Stock provvisorio (ricevuto)` di default) riceve un accredito di `80 $`.

#### Conti bilanciati una volta ricevuta la fattura fornitore¶

In questo esempio, un’azienda inizia con zero unità del prodotto tavolo in magazzino. In seguito, riceve dal fornitore 8 tavoli. Quando si riceve la fattura dal fornitore per 8 tavoli:

  1. usa `80 $` nel conto **Ingresso magazzino** per pagare la fattura. Questo comporta una compensazione e il conto ora è pari a `0 $`.

  2. Addebita il conto **Ingresso magazzino** di `80 $` (per riconciliare questo conto).

  3. Accredita `80 $` sul **Conto debito**. Questo conto memorizza l’importo che l’azienda deve a terzi, in modo che i contabili lo utilizzino per emettere gli assegni ai fornitori.




##### In Odoo¶

Al momento della richiesta del pagamento da parte del venditore, apri l’app Acquisti ‣ Ordini ‣ Acquisti e seleziona lo OdA corrispondente a 8 tavoli. All’interno dello OdA, seleziona Crea fattura fornitore.

Passa alla scheda Movimenti contabili per capire in che modo gli `80 $` vengono trasferiti dal conto deposito, `Stock provvisorio (ricevuto)` al `Conto passivo`. Conferma la fattura per registrare il pagamento al fornitore.

### Alla consegna dei prodotti¶

Nella tabella dell’esempio precedente, quando 10 prodotti vengono consegnati a un cliente, il conto **Ingresso magazzino** non viene toccato perché non ci sono nuovi prodotti in arrivo. Per semplificare:

  1. La **valutazione di magazzino** è pari a `120 $`. La sottrazione dalla valutazione del magazzino rappresenta un valore di `120 $` di prodotti in uscita dall’azienda.

  2. Addebita il **Conto di credito** per registrate i ricavi della vendita.




Understand Anglo-Saxon expensing

Nella registrazione contabile che fattura un cliente per 10 tavoli, i conti **Vendite prodotti** , **Imposte ricevute** e **Conto di credito** sono tutti relativi alla vendita del prodotto. Il conto **Conto di credito** è il conto in cui verrà ricevuto il pagamento del cliente.

La contabilità anglosassone riconosce il costo dei beni venduti (COGS) una volta effettuata la vendita. Quindi, fino a quando il prodotto non viene venduto, scartato o restituito, i costi di mantenimento del prodotto in magazzino non vengono contabilizzati. Il conto **Spese** viene addebitato di `120 $` per registrare i costi di stoccaggio di 10 tavoli durante questo periodo di tempo.

### Alla restituzione dei prodotti¶

Nella tabella dell’esempio precedente, quando restituisci un prodotto al fornitore acquistato a `10 $`, l’azienda aspetta un accredito di `10 $` nel **Conto di debito** da parte del fornitore. Tuttavia, dal conto **Ingresso magazzino** devono essere addebitati `12 $` perché il costo medio è pari a `12 $` al momento del reso. I `2 $` mancanti vengono considerati nel Conto differenza di prezzo, configurato nella Categoria prodotto del prodotto stesso.

Nota

Il comportamento dei conti _differenza di prezzo_ varia a seconda della localizzazione. In questo caso, il conto è destinato a memorizzare le differenze tra il prezzo del venditore e i metodi _automatizzati_ di valutazione delle scorte.

Riepilogo:

  1. addebitare il conto **Ingresso magazzino** di `10 $` per spostare il tavolo da magazzino a ingresso magazzino. Questo spostamento indica che il tavolo deve essere elaborato per una spedizione in uscita.

  2. Addebitare sul conto **Ingresso magazzino** un ulteriore importo pari a `2 $` per tenere conto della **Differenza di prezzo**.

  3. Accreditare `12 $` per la **Valutazione magazzino** perché l’articolo sta uscendo dal magazzino.




Una volta ricevuto il rimborso da parte del fornitore,

  1. accredita sul conto **Ingresso magazzino** `10 $` per riconciliare il prezzo del tavolo

  2. addebita `10 $` sul **Conto di debito** `$10` per far sì che i contabili incassino e registrino il pagamento nel loro registro.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/get_started/avg_price_valuation.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_units.html "Unità fiscali") |
  * [precedente](multi_currency.html "Sistema multi valuta") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Prezzo medio sulla merce resa


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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: point of sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: Servicio de Rentas Internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Fornitura Immediata di Informazioni
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: fornitori autorizzati
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda