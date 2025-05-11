# Fatture basate su tempo e materiali — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](milestone.html "Fatturare milestone di progetto") |
  * [precedente](proforma.html "Fatture proforma") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su tempo e materiali



# Fatture basate su tempo e materiali¶

La fatturazione basata su tempo e/o materiali viene solitamente utilizzata quando non è possibile stimare con precisione le dimensioni di un progetto o quando i requisiti di un progetto possono cambiare.

Si tratta di un contratto diverso da quello a prezzo fisso, in cui il cliente accetta di pagare un totale specifico per l’adempimento del contratto, indipendentemente da quanto deve essere pagato ai dipendenti, ai subappaltatori, ai venditori, ai fornitori e così via.

Grazie all’app Odoo _Vendite_ è possibile emettere fatture per il tempo e altre spese (ad es. di trasporto, di alloggio) così come acquisti necessari al completamento di un ordine.

## Configurazione app e impostazioni¶

Innanzitutto, per tenere traccia in modo accurato dell’avanzamento di un progetto, è **necessario** installare le applicazioni Odoo _Progetti_ e _Contabilità_.

Per installare l’app _Progetti_ , accedi alla dashboard principale di Odoo ‣ Applicazioni. In seguito, nella pagina Applicazioni, trova il blocco corrispondente all’app Progetti e fai clic su Attiva. La pagina si ricarica automaticamente e torna alla dashboard principale di Odoo, dove ora è possibile accedere all’app _Progetti_.

Ripeti lo stesso processo per installare l’applicazione _Contabilità_.

Dopo avere effettuato l’installazione, fai clic sull’icona dell’app Contabilità nella dashboard principale di Odoo e vai su Configurazione ‣ Impostazioni. Nella pagina relativa alle Impostazioni, arriva alla sezione Analitiche e assicurati che la casella accanto a Contabilità analitica sia selezionata.

In seguito, fai clic su Salva per salvare tutte le modifiche.

In seguito, accedi alla dashboard principale di Odoo ‣ app Progetti ‣ Configurazione ‣ Impostazioni. Sulla pagina delle Impostazioni, nella sezione Gestione tempo, assicurati che la casella accanto alla funzione Fogli ore sia selezionata.

In seguito, fai clic su Salva per salvare tutte le modifiche.

## Configurazione prodotto servizio¶

Grazie alla funzionalità _Fogli ore_ attivata nell’app _Progetti_ , è possibile fatturare il tempo speso su un progetto ma **solo** quando il prodotto è stato configurato nel modo che segue.

Importante

La fatturazione del tempo speso su un progetto è possibile **solo** con prodotti configurati come _Servizio_.

Per configurare un prodotto servizio, accedi al modulo Vendite ‣ Prodotti ‣ Prodotti. Nella pagina Prodotti, seleziona il prodotto servizio desiderato da configurare oppure fai clic su Nuovo per creare un nuovo prodotto.

Dal modulo del prodotto, nella scheda Informazioni generali, imposta il Tipo prodotto su Servizio. Successivamente, apri il menu a discesa nel campo Politica di fatturazione e scegli Basato su fogli ore.

In seguito, dal menu a discesa Crea un ordine, seleziona Progetto e lavoro. L’impostazione indica che quando un ordine di vendita viene creato con un prodotto servizio specifico, nell’app _Progetti_ viene creato un nuovo progetto con un nuovo lavoro.

Nota

È possibile scegliere l’opzione Lavoro dal menu a tendina Crea un ordine. Se scegli Lavoro, seleziona un progetto esistente e il lavoro apparirà nel campo Progetto che appare solo se scegli Lavoro nel campo Crea un ordine.

## Aggiungere tempo speso a un ordine di vendita¶

Dopo aver configurato in modo appropriato un prodotto servizio con la _Politica di fatturazione_ e l’opzione _Crea un ordine_ corrette, è possibile aggiungere del tempo speso a un ordine di vendita.

Per vedere il processo in azione, apri il modulo Vendite ‣ Nuovo per aprire un modulo di preventivo vuoto. Successivamente, aggiungi un Cliente e nella scheda Righe ordine, fai clic su Aggiungi prodotto e seleziona il prodotto servizio configurato dal menu a discesa.

Successivamente. fai clic su Conferma per confermare l’ordine.

Dopo aver confermato l’ordine di vendita, appariranno due pulsanti smart nella parte alta del modulo dell’ordine: Progetti e Lavori.

Se fai clic sul pulsante Progetti, potrai vedere il progetto specifico collegato all’ordine di vendita. Se invece fai clic sul pulsante Lavori, verrà mostrato il lavoro del progetto specifico correlato all’ordine di vendita. È possibile accedere a entrambi anche dall’app _Progetti_.

Per aggiungere delle ore a un ordine di vendita, fai clic sul pulsante Lavori.

Sul modulo del lavoro, seleziona la scheda Fogli ore. Dalla scheda Fogli ore, è possibile scegliere i dipendenti che lavoreranno sul progetto e i dipendenti o la persona che ha creato l’ordine di vendita può registrare il tempo speso sul progetto.

Per aggiungere un dipendente e registrare il tempo speso sul progetto, fai clic su Aggiungi riga nella scheda Fogli ore. In seguito, seleziona una Data e un Dipendente. Inoltre, è presente un’opzione per aggiungere una breve descrizione del lavoro svolto durante il tempo speso sulla task nella colonna Descrizione ma non è richiesto.

Infine, inserisci il tempo speso sul lavoro nella colonna Ore spese e fai clic per completare la riga nella scheda Fogli ore.

Nota

Il tempo inserito nella colonna Ore spese viene aggiunto immediatamente al campo Tempo assegnato (situato vicino alla parte superiore) come percentuale, il che mostra quante delle ore totali assegnate sono state effettuate.

Queste stesse informazioni si trovano sotto forma di ore numeriche nei campi Ore spese e Ore rimanenti, situati in fondo alla scheda Fogli ore.

Ripeti il processo per tutti i dipendenti e le ore spese sul progetto.

## Fatturare il tempo impiegato¶

Una volta aggiunti al lavoro del progetto tutti i dipendenti necessari e il tempo impiegato, si può tornare all’ordine di vendita per fatturare al cliente quelle ore. Per farlo, fai clic sul pulsante Ordine di vendita nella parte superiore del modulo del lavoro, oppure torna all’ordine di vendita tramite il percorso situato nella parte superiore sinistra dello schermo.

Tornando al modulo dell’ordine di vendita, il tempo aggiunto al lavoro viene mostrato nella scheda Righe ordine (nella colonna Consegnato) e nel nuovo pulsante smart Ore registrate nella parte superiore dell’ordine di vendita.

Per fatturare il cliente per il tempo speso sul progetto, fai clic su Crea fattura e seleziona Fattura normale dalla finestra pop-up Crea fatture. In seguito, fai clic su Crea bozza fattura.

Apparirà una Bozza fattura cliente che mostra tutto il lavoro svolto nella scheda Righe fattura.

Suggerimento

Fai attenzione alla colonna Distribuzione analitica nella Fattura cliente, poiché queste informazioni sono necessarie per garantire che le altre attività di fatturazione di tempo/materiale siano completate in modo corretto e accurato.

Fai clic su Conferma per confermare la fattura e proseguire con il processo di fatturazione.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

## Configurazione note spese¶

Per tracciare e fatturare delle spese relative a un ordine di vendita, è **necessario** installare l’app Odoo _Note spese_.

Per installare l’app _Note spese_ , accedi alla dashboard principale di Odoo ‣ Applicazioni. Successivamente, nella pagina delle Applicazioni, trova la scheda dell’app Note spese e fai clic su Attiva.

La pagina si aggiorna automaticamente e torna alla dashboard principale di Odoo, dove è ora possibile accedere all’applicazione Note spese.

## Aggiungere spese a un ordine di vendita¶

Per aggiungere una spesa a un ordine di vendita, apri l’applicazione Note spese. In seguito, dalla dashboard principale _Note spese_ , fai clic su Nuovo e apparirà un modulo vuoto.

Sul modulo, aggiungi una Descrizione della spesa (ad es. `Hotel`, `Biglietto aereo`). In seguito, nel campo Categoria, seleziona l’opzione corretta dal menu a discesa (ad es. Pasti, Chilometri, Viaggio e alloggio).

Nota

È possibile aggiungere e modificare categorie di note spese accedendo all’app Note spese ‣ Configurazione ‣ Categorie spese.

Successivamente, inserisci l’importo totale della spesa nel campo Totale, nonché le Imposte incluse eventualmente applicabili. in seguito, assicurati che sia selezionato il Dipendente corretto e indica chi ha pagato la spesa nel campo Pagato da: il Dipendente (da rimborsare) o la Azienda.

In seguito, nel campo Cliente da rifatturare, seleziona l’ordine di vendita appropriato dal menu a discesa. Poi, seleziona le informazioni dello stesso ordine di vendita anche nel campo Distribuzione analitica.

Nota

Il campo Distribuzione analitica avrà **solo** l’ordine di vendita corrispondente come opzione se l’ordine di vendita contiene un prodotto di servizio che viene fatturato in base a _Fogli ore_ , _Milestone_ o _Quantità consegnate_.

Se ci sono ricevute che devono essere caricate e allegate alla spesa, fai clic sul pulsante Allega ricevuta e carica i documenti necessari alla spesa. Questa operazione **non** è obbligatoria, ma può influire sull’approvazione o meno di una spesa.

Una volta inserite tutte le informazioni, fai clic su Crea resoconto per creare un resoconto di spesa che riporti tutte le informazioni sulle note spese appena inserite.

Poi, c’è l’opzione Invia al supervisore per l’approvazione. Una volta approvata, appare il Resoconto nella prossima busta paga.

Per mostrare un flusso completo in questo esempio, seleziona Invia al supervisore. In seguito, il manager farà clic su Approva per approvare la spesa e su Genera registrazioni contabili per registrare la spesa nel registro contabile.

## Fatturare le spese¶

Per fatturare a un cliente una spesa su un ordine di vendita, apri l’ordine di vendita relativo, sia dall’applicazione Vendite che dal resoconto della spesa nell’applicazione Note spese. Dal resoconto della spesa, fai clic sul pulsante Ordini di vendita nella parte superiore della pagina.

Se il resoconto sulla spesa era collegato all’ordine di vendita, la spesa appena configurata ha ora una propria riga nella scheda Righe ordine e può essere fatturata al cliente.

Per fatturare il cliente per la spesa sull’ordine di vendita, fai clic su Crea fattura e seleziona Fattura normale dalla finestra pop-up Crea fatture. In seguito, fai clic su Crea bozza fattura.

In questo modo si ottiene una Bozza fattura cliente per la spesa. A questo punto, il processo di fatturazione può essere completato come di consueto.

## Configurazione di un acquisto¶

Per fatturare a un cliente gli acquisti effettuati su un ordine di vendita, è necessario installare l’applicazione _Acquisti_.

Per installare l’app _Acquisti_ , accedi alla dashboard principale di Odoo ‣ Applicazioni. In seguito, nella pagina Applicazioni, trova il blocco corrispondente all’app Acquisti e fai clic su Attiva. La pagina si ricarica automaticamente e torna alla dashboard principale di Odoo, dove ora è possibile accedere all’app Acquisti.

## Aggiungere acquisti a un ordine di vendita¶

Per aggiungere un acquisto a un ordine di vendita, occorre prima creare un ordine di acquisto. Per creare un ordine di acquisto, apri il modulo Acquisti ‣ Nuovo per visualizzare un modulo di ordine di acquisto vuoto.

Per prima cosa, aggiungi un Fornitore all’ordine di acquisto. Successivamente, nella scheda Prodotti, fai clic sul menu a discesa opzioni colonna extra, rappresentato da due linee orizzontali con dei puntini, situate all’estrema destra delle intestazioni di colonna. Dal menu a discesa, seleziona Distribuzione analitica.

Dopo aver aggiunto la colonna Distribuzione analitica alle intestazioni della scheda Prodotti del modulo d’ordine d’acquisto, puoi aggiungere i prodotti all’ordine d’acquisto. A tal fine, fai clic su Aggiungi prodotto e seleziona il prodotto desiderato dal menu a discesa. Ripeti l’operazione per tutti i prodotti da aggiungere.

Importante

Affinché un acquisto venga correttamente fatturato su un ordine di vendita, il prodotto sull’ordine di acquisto **deve** essere contrassegnato come Può essere spesa, avere una Politica di fatturazione impostata su Quantità consegnate e avere l’opzione Al costo selezionata nel campo Rifattura spese della sua scheda prodotto.

In seguito, seleziona la Distribuzione analitica appropriata associata all’ordine di vendita a cui è legato l’ordine di acquisto. Per farlo, fai clic sul campo vuoto Distribuzione analitica per far apparire la finestra pop-up Analitica.

In seguito, dal menu a discesa Dipartimenti, seleziona la distribuzione analitica associata all’ordine di vendita da fatturare per l’acquisto.

Una volta inserite tutte le informazioni nella scheda Prodotti dell’ordine di acquisto, conferma l’ordine facendo clic su Conferma ordine. Successivamente, fai clic su Ricezione prodotti quando i prodotti sono stati ricevuti. In questo modo si crea un modulo di ricevuta.

Nota

Se è necessario inserire un numero di serie/lotto prima di convalidare la ricezione dei prodotti, fai clic sull’icona dettagli rappresentata da quattro linee orizzontali all’estrema destra della riga del prodotto.

Ciò permette di visualizzare la scheda Operazioni dettagliate, in cui è possibile aggiungere le quantità necessarie Numero di lotto/serie e quelle Completate. Quando sei pronto, fai clic su Conferma per confermare i dati.

In seguito, fai clic su Convalida per convalidare l’ordine di acquisto.

Successivamente, torna all’ordine d’acquisto, tramite il percorso di navigazione nella parte superiore della pagina e fai clic su Crea fattura per creare una fattura fornitore che può essere fatturata al cliente sull’ordine di vendita allegato.

Nota

Assicurati di inserire una Data di fatturazione nella Bozza fattura fornitore prima di confermare. Se _non_ viene inserita una Data fattura, viene visualizzata una finestra di errore che richiede l’inserimento di tale informazione prima di procedere alla conferma.

In seguito, fai clic su Conferma per confermare la fattura fornitore che viene aggiunta automaticamente all’ordine di vendita, dove può essere fatturata direttamente al cliente a esso collegato.

## Fatturare acquisti¶

Per fatturare a un cliente un acquisto su un ordine di vendita, prima aggiungi l’acquisto all’ordine di vendita, poi apri l’ordine di vendita desiderato nell’applicazione Vendite.

Nell’ordine di vendita allegato all’ordine di acquisto, il prodotto acquistato ha ora una propria riga prodotto nella scheda Righe ordine ed è pronto per essere fatturato.

Per fatturare l’acquisto al cliente, è sufficiente fare clic su Crea fattura, selezionare Fattura normale dalla finestra a comparsa Crea fatture, e poi fai clic su Crea bozza fattura.

In questo modo, viene visualizzata una Bozza fattura cliente con il prodotto dell’ordine di acquisto appena aggiunto alla scheda Righe fattura.

Per completare il processo di fatturazione, fai clic su Conferma per confermare la fattura, poi fai clic su Registra pagamento nel modulo pop-up Registra pagamento.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/invoicing/time_materials.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](milestone.html "Fatturare milestone di progetto") |
  * [precedente](proforma.html "Fatture proforma") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su tempo e materiali


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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
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
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
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