# Cercare, filtrare e raggruppare i record — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](contacts.html "Contatti") |
  * [precedente](reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Cercare, filtrare e raggruppare i record



# Cercare, filtrare e raggruppare i record¶

Odoo consenti di cercare, filtrare e raggruppare i record da un’unica vista in modo da visualizzare solo quelli più importanti. La barra di ricerca è situata nella parte alta della vista. Digita cerca valori, o fai clic sull’icona 🔽 (freccia giù) per accedere ai menu a discesa Filtri, Raggruppa per, e Preferiti.

## Cercare dei valori¶

Utilizza il campo di ricerca per trovare rapidamente valori specifici e aggiungili come filtro. Inserisci il valore che vuoi cercare e seleziona l’opzione desiderata dal menu a discesa per applicare il filtro di ricerca.

Example

Invece di aggiungere un filtro personalizzato <search/custom-filters>`a record selezionati per i quali *Mitchell Admin* è l’addetto vendite nel rendiconto di *analisi delle vendite* (:menuselection:`App Vendite –> Rendiconto –> Vendite) puoi cercare `Mitch`, facendo clic su ⏵ (freccia destra) accanto a Cerca addetto vendite per: Mitch e seleziona Mitchell Admin.

Nota

Utilizzare il campo ricerca equivale a utilizzare l’operatore _contiene_ quando viene aggiunto un filtro personalizzato. Se inserisci un valore parziale e selezioni direttamente il campo desiderato (senza fare clic su ⏵ (freccia destra)), verranno inclusi _tutti_ i record che contengono i caratteri digitati per il campo selezionato.

## Filtri¶

I filtri vengono utilizzati per selezionare i record che corrispondono a criteri specifici. La selezione predefinita di record è specifica per ogni vista ma può essere modificata selezionando uno (o più) filtri preconfigurati o aggiungendo un filtro personalizzato.

### Filtri preconfigurati¶

Modifica la selezione predefinita di record facendo clic sull’icona 🔽 (freccia giù) dalla barra di ricerca e selezionando uno (o più) _filtri preconfigurati_ dal menu a discesa Filtri.

Example

Nel rendiconto _Analisi vendite_ (App Vendite ‣ Rendiconto ‣ Vendite) vengono selezionati per impostazione predefinita solo i record nella fase _ordine di vendita con una *data ordine_ compresa negli ultimi 365 giorni.

Per includere anche record nella fase _preventivo_ , seleziona Preventivi dal menu Filtri.

Inoltre, per includere _solo_ record relativi ad ordini di vendita e preventivi risalenti ad un anno specifico, ad esempio 2024, elimina il filtro esistente `Data ordine: ultimi 365 giorni` facendo clic sull’icona ❌ (elimina) per poi selezionare Data ordine ‣ 2024.

Nota

I Filtri preconfigurati sono raggruppati e ogni gruppo è separato da una riga orizzontale. La selezione di filtri preconfigurati appartenenti allo stesso gruppo fa si che i record corrispondando a _qualsiasi_ condzione applicata. Tuttavia, la selezione di filtri da gruppi differenti richiede che i record corrispondano a _tutte_ le condizioni applicate.

### Personalizzare i filtri¶

Se i filtri preconfigurati non sono abbastanza specifici, aggiungine uno. Per farlo, fai clic sull’icona 🔽 (freccia giù) nella barra di ricerca per poi selezionare Filtri ‣ Aggiungi filtro personalizzato.

La finestra popup Aggiungi filtro personalizzato mostra le opzioni corrispondenti, la regola del filtro e il pulsante Includi archiviati.

La configurazione predefinita per la corrispondenza è Corrisponde a una delle seguenti regole, il che indica che ogni regola filtro viene applicata in maniera indipendente. Per modificare la configurazione di corrispondenza in Corrisponde a tutte le regole è necessario aggiungere almeno due regole filtri al filtro personalizzato.

  * Corrisponde a tutte 🔽 le regole seguenti: **tutte** le regole filtro devono essere rispettate. Razionalmente, si tratta di un’operazione _E_ (`&`).

  * Corrisponde a qualsiasi 🔽 delle regole seguenti: **qualsiasi** regola filtro può essere rispettata. Razionalmente, si tratta di un’operazione _OPPURE_ (`|`).




Per impostazione predefinita, la regola filtro viene aggiunta al filtro personalizzato. Il seguente paragrafo descrive la struttura di una regola filtro:

  1. il primo campo inline da filtrare è il _nome campo*_. Alcuni campi presentano parametri ottimizzati, annidati all’interno di un altro campo. Questi campi hanno un’icona > (freccia) accanto che può essere selezionata per svelare i campi annidati.

  2. Il secondo campo inline è un _operatore_ condizionale utilizzato per confrontare il nome del campo con il valore. Gli [operatori condizionali disponibili](../../developer/reference/backend/orm.html#reference-orm-domains) sono specifici per il tipo di dati del campo.

  3. Il terzo campo inline è la variabile _valore_ del nome campo. L’inserimento del valore potrebbe apparire come menu a discesa, testo, numero, data/ora, selettore booleano o potrebbe essere vuoto in base all’operatore utilizzato e al tipo di dati del campo.




A destra dei criteri delle regole del filtro sono disponibili tre pulsanti in linea:

  1. ➕ (segno più): aggiunge una nuova regola al di sotto della regola esistente.

  2. (Aggiungi ramo): aggiunge un nuovo gruppo di regole al di sotto della regola esistente con le opzioni di corrispondenza disponibili qualsiasi e tutto per definire come ogni regola del ramo viene applicata al filtro. Se l’opzione di corrispondenza viene configurata come nel gruppo d’origine, i campi vengono spostasti nel gruppo d’origine.

Example

Se l’opzione di corrispondenza è impostata su Corrisponde a tutte 🔽 le regole seguenti e viene aggiunto un nuovo ramo con l’opzione di corrispondenza modificata da qualsiasi 🔽 a tutto🔽, il ramo appena aggiunto scompare e il gruppo di regole viene spostato nel gruppo d’origine.

  3. 🗑️ (cestino): elimina il nodo. Se il ramo di un nodo viene eliminato, vengono eliminati anche tutti i figli del nodo.




Una nuova regola filtro può essere aggiunta al filtro personalizzato facendo clic sul pulsante Nuova regola.

Una volta che i criteri del filtro vengono definiti, fai clic su Aggiungi per aggiungere il filtro personalizzato alla vista.

Example

Per raggiungere tutti i lead e le opportunità nella fase _Vinto_ dall’app CRM e avere un fatturato previsto maggiore di 1.000 $, devi configurare le seguenti impostazioni:

Corrisponde a tutte 🔽 (freccia giù) le regole seguenti:

  1. Fase corrisponde a Vinto

  2. Ricavi previsti > `1.000`

  3. qualsiasi 🔽 (freccia giù) di:

     * Tipo = Lead

     * Tipo = Opportunità




Suggerimento

Attiva la modalità sviluppatore per rivelare il nome tecnico e il tipo di dati di ogni campo così come la casella di testo # Editor codice al di sotto delle regole del filtro per visualizzare e modificare manualmente il dominio.

## Raggruppare record¶

La visualizzazione dei record in una vista può essere unita secondo uno dei _gruppi preconfigurati_. Per farlo, fai clic sull’icona 🔽 (freccia giù) nella barra di ricerca e poi seleziona una delle opzioni Raggruppa per dal menu a discesa.

Example

Per raggruppare i record per addetto vendite nel rendicondo _Analisi vendite_ (App Vendite ‣ Rendiconto ‣ Vendite) fai clic sull’opzione Addetto vendite dal menu a discesa Raggruppa per. La vista cambia per raggruppare i record per addetto vendite senza filtrare nessun record.

È possibile _personalizzare gruppi_ utilizzando un campo presente sul modello. Per farlo, fai clic su Aggiungi gruppo personalizzato e seleziona un campo dal menu a discesa.

Nota

È possibile utilizzare più gruppi nello stesso momento. Il primo gruppo selezionato rappresenta il principale, il secondo, aggiunto in seguito, divide le categorie del gruppo principale e così via. Inoltre, i filtri e i gruppi possono essere utilizzati insieme per ridefinire ulteriormente la vista.

## Confronto¶

Alcune dashboard per la reportistica includono la sezione Confronto nei menu a tendina delle barre Cerca…. Include il resoconto [Efficacia totale dell’impianto (OEE)](../inventory_and_mrp/manufacturing/reporting/oee.html) per l’app _Produzione_ e il resoconto [Acquisti](../inventory_and_mrp/purchase/advanced/analyze.html) per la relativa app,

Le opzioni nella sezione __ Confronto vengono usate per confrontare dati di due periodi diversi. È possibile scegliere tra due opzioni: (filtro tempo): Periodo precedente e (filtro tempo): Anno precedente.

Importante

Per alcuni resoconti, la sezione Confronto appare **solo** nella barra Ricerca… del menu a tendina se uno (o più) periodi di tempo sono stati selezionati nella colonna dei Filtri. Questo accade perché se non viene specificato un periodo di tempo, non apparirà nulla.

In aggiunta, alcuni resoconti consentono l’utilizzo della funzione Confronto solo se viene selezionato il tipo di grafico __(a torta) oppure la vista __(pivot). È possibile selezionare l’opzione Confronto anche se hai attivato un’altra vista ma facendolo la visualizzazione dei dati nel resoconto **non** cambierà.

Per visualizzare i dati utilizzando uno dei due metodi di confronto, inizia selezionando un periodo di tempo nella colonna dei Filtri della barra di Ricerca… del menu a tendina. In seguito, seleziona (filtro tempo): Periodo precedente o (filtro tempo): anno precedente nella sezione Confronto.

Una volta attivata una delle opzioni di Confronto, il resoconto confronta i dati del periodo selezionato con i dati aventi la stessa unità di tempo (mese, trimestre, anno), nel periodo o nell’anno precedente. La modalità di visualizzazione dei dati dipende dalla vista selezionata:

  * Il __(grafico a barre) mostra due barre affiancate, per ogni unità di tempo del periodo selezionato. La barra di sinistra rappresenta il periodo di tempo selezionato, mentre quella di destra rappresenta il periodo di tempo precedente.

  * Il __(grafico a righe) viene visualizzato con due righe, una che rappresenta il periodo di tempo selezionato e l’altra che rappresenta il periodo di tempo precedente.

  * Il __(grafico a torta) appare come un cerchio grande con un cerchio più piccolo all’interno. Il cerchio più grande rappresenta il periodo di tempo selezionato, mentre il cerchio più piccolo rappresenta il periodo di tempo precedente.

  * La __(tabella pivot) viene visualizzata con ogni colonna divisa in due colonne più piccole. La colonna di destra rappresenta il periodo di tempo selezionato, mentre la colonna di sinistra rappresenta il periodo di tempo precedente.




Example

Nel resoconto di Analisi della produzione dell’app Produzione, i dati del secondo trimestre del 2024 vengono confrontati con i dati del secondo trimestre del 2023. Il parametro Q2 è selezionato per il filtro Data di fine della barra di Ricerca… del menu a tendina. Nella sezione Confronto, è selezionato il parametro Data di fine: anno precedente.

L’anno in corso è il 2024, quindi il cerchio più grande mostra i dati del secondo trimestre (Q2) del 2024. Il cerchio più piccolo mostra i dati relativi al secondo trimestre (Q2) del 2023, ovvero lo stesso periodo di tempo, ma un _anno_ prima.

Se selezioni Data di fine: periodo precedente, il cerchio più piccolo mostra i dati del primo trimestre (Q1) del 2024, ovvero lo stesso periodo di tempo, ma un _periodo_ prima.

## Preferite¶

I preferiti sono un modo per salvare ricerche specifiche per usi futuri oppure come nuovo filtro predefinito per la vista.

Per salvare la vista attuale come preferita, fai clic sull’icona 🔽 (freccia giù) nella barra di ricerca e poi seleziona il menu a discesa Salva ricerca corrente per visualizzare le seguenti opzioni:

  * Nome filtro: nome della ricerca preferita.

  * Filtro predefinito: configura la ricerca preferita come filtro predefinito per la vista.

  * Condiviso: rende la ricerca preferita disponibile per tuti gli utenti. Per impostazione predefinita, la ricerca preferita è disponibile solo per l’utente che l’ha creata.




Una volta che le opzioni sono state configurate, fai clic su Salva per salvare la ricerca preferita.

Le preferenze salvate sono accessibili facendo clic sull’icona 🔽 (freccia giù) nella barra di ricerca, per poi selezionare il filtro salvato nel menu Preferiti. Per eliminare una preferenza, fai clic sull’icona 🗑️ (cestino) accanto alla ricerca preferita.

Suggerimento

Per visualizzare _tutte_ le ricerche preferite, come prima cosa attiva la modalità sviluppatore e vai su App Impostazioni ‣ Funzioni tecniche ‣ Interfaccia utente: Filtri definiti dall’utente. Da qui, tutte le ricerche preferite possono essere visualizzate, modificate, archiviate o eliminate.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/essentials/search.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](contacts.html "Contatti") |
  * [precedente](reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Cercare, filtrare e raggruppare i record


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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