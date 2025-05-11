# Resoconto ricavi previsti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forecast_report.html "Resoconto previsionale") |
  * [precedente](win_loss.html "Analisi flusso di opportunità") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto ricavi previsti



# Resoconto ricavi previsti¶

Le _entrate previste_ sono il valore totale in denaro dei lead che si prevede di chiudere entro una certa data, di solito la fine del mese corrente.

Un _resoconto sulle entrate previste_ raccoglie tutti i lead attivi in una pipeline di vendita che hanno una data di chiusura prevista e confronta l’andamento dei team di vendita in un determinato periodo di tempo.

Grazie a un resoconto mensile sui ricavi attesi, i responsabili delle vendite possono vedere quali membri del team stanno raggiungendo i loro obiettivi e chi potrebbe aver bisogno di ulteriore assistenza per chiudere contratti importanti.

## Creare un resoconto ricavi previsti¶

Per creare un resoconto ricavi previsti, accedi all’app CRM ‣ Rendicontazione ‣ Pipeline. Si aprirà la dashboard Analisi pipeline.

Importante

La dashboard _Analisi pipeline_ include diversi filtri nella barra di ricerca per impostazione predefinita. Rimuovili prima di aggiungere altri filtri personalizzati.

Nella parte in alto a sinistra del resoconto, fai clic su Misure, poi seleziona Ricavi previsti dal menu a discesa.

Nella parte alta della pagina, fai clic sull’icona 🔻(triangolo punta in giù) a destra della barra Ricerca… per aprire il menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti. Sotto la colonna Filtri, fai clic su Aggiungi filtro personalizzato per aprire la finestra pop-up Aggiungi filtro personalizzato.

### Aggiungere filtri personalizzati¶

Per generare un rapporto sui ricavi previsti, è necessario creare dei filtri per le seguenti condizioni:

>   * Data di chiusura prevista: limita i risultati a includere solo i lead che si prevede di chiudere entro un determinato periodo di tempo.
> 
>   * Escludi lead non assegnati: esclude i lead che non sono stati assegnati a un addetto vendite.
> 
>   * Team di vendita specifici: limita i risultati per includere solo i contatti assegnati a uno o più team di vendita. Questo filtro è opzionale e non deve essere incluso se il resoconto è destinato all’intera azienda.
> 
> 


#### Aggiungere il filtro data chiusura prevista¶

Nella finestra pop-up Aggiungi filtro personalizzato, fai clic sul primo campo della nuova regola. Scrivi `Ricavi attesi` nella barra Ricerca… o scorri per selezionare l’opzione dall’elenco. Fai clic nel secondo campo e seleziona è configurato. Questo limita i risultati affinché vengano inclusi solo lead con una data di chiusura stimata configurata.

Successivamente, fai clic sull’icona ➕ (più) a destra della regola per duplicarla.

Suggerimento

L’utilizzo dell’icona ➕ (più) rende più semplice aggiungere nuove regole basate sullo stesso filtro.

Nel secondo campo della nuova regola, seleziona è tra dal menu a discesa. In questo modo si crea un intervallo di tempo in cui la data di chiusura prevista deve verificarsi affinché le derivazioni siano incluse nei risultati.

Fai clic su ciascun campo data, uno alla volta, e utilizza la finestra popover del calendario per aggiungere una data di inizio e di fine alla regola. Di solito si tratta dell’inizio e della fine del mese corrente o del trimestre fiscale.

#### Escludere lead non assegnati¶

Dopo aver filtrato la data di chiusura prevista, aggiungi una Nuova regola. Quindi, fai clic nel primo campo della nuova regola e digita `Addetto vendite` nella barra Ricerca…, oppure scorri nell’elenco per selezionarlo. Fai clic sul secondo campo della regola e seleziona è configurato dal menu a discesa. In questo modo si escludono i risultati senza un addetto vendite assegnato.

#### Aggiungere un filtro per i team di vendita¶

Nota

Questo filtro è opzionale. Per visualizzare i risultati per l’intera azienda, **non** aggiungere questo filtro e continua a Visualizzare i risultati.

Per limitare i risultati del resoconto a uno o più team di vendita, fai clic su Nuova regola. In seguito, fai clic sul primo campo della nuova regola e digita `Team vendite` nella barra Ricerca… o scorri l’elenco per trovarla.

Nel secondo campo della regola, seleziona è in dal menu a discesa. La selezione di questo operatore limita i risultati ai team di vendita indicati nel campo successivo.

Infine, fai clic sul terzo campo e fai una selezione dall’elenco completo visualizzato nel menu a comparsa, oppure digita i primi caratteri del nome del team di vendita specifico per trovarlo e selezionarlo rapidamente come parametro.

Suggerimento

È possibile aggiungere più team alla regola `Team di vendita`, dove ogni parametro viene trattato con un operatore “o” (ad esempio “qualsiasi”) nella logica di ricerca.

## Visualizzare i risultati¶

Nella parte superiore del modulo Aggiungi filtro personalizzato, c’è un’opzione che consente di abbinare qualsiasi o tutte le regole. Per eseguire correttamente il resoconto, devono essere inclusi solo i record che corrispondono a **tutti** i filtri seguenti. Prima di aggiungere i filtri, assicurati che l’opzione tutti sia selezionata in questo campo.

Nella parte bassa del modulo Aggiungi filtro personalizzato, fai clic su Aggiungi.

### Opzioni di visualizzazione¶

Il resoconto sui ricavi previsti trae vantaggio dall’utilizzo di più viste. La vista grafico predefinita può essere utilizzata per identificare gli addetti vendite che si prevede porteranno il maggior numero di entrate, mentre la vista elenco e la vista pivot forniscono maggiori dettagli su contratti specifici.

Graph viewList viewPivot view

La _vista grafico_ viene utilizzata per visualizzare i dati ed è utile per identificare schemi e tendenze.

I _grafici a barre_ sono utilizzati per mostrare la distribuzione dei dati tra diverse categorie o tra diversi addetti vendite.

_I grafici a righe_ sono utili per mostrare l’andamento di un periodo di tempo.

_I grafici a torta_ sono utili per mostrare la distribuzione, o il confronto, dei dati tra un piccolo numero di categorie o di addetti vendite, in particolare come questi formino la parte significativa di un quadro complessivo.

La visualizzazione predefinita per il resoconto sui ricavi previsti è il grafico a barre impilate. Per passare a una visualizzazione diversa del grafico, fai clic su una delle icone in alto a sinistra del resoconto. Mentre il grafico a linee e il grafico a barre sono disponibili nella visualizzazione impilata, il grafico a torta non è disponibile.

Icone vista grafico in ordine: grafico a barre, grafico a righe, grafico a torta, grafico impilato.¶

La _vista elenco_ fornisce un elenco di tutti i lead che si prevede di chiudere entro la data stabilita. Facendo clic su un lead nella vista elenco si apre il record per un’analisi dettagliata, ma è possibile ricavare molte informazioni dalla vista di base.

Per passare alla vista elenco, fai clic sull’icona ≣ (elenco) nella parte in alto a destra del resoconto.

Per aggiungere ulteriori metriche al resoconto, fai clic sul _menu opzioni aggiuntive_ indicato dall’icona toggle in alto a destra dell’elenco.

Facendo clic sull’icona toggle nella vista _elenco_ si apre il menu _opzioni aggiuntive_.¶

Seleziona qualsiasi metrica aggiuntiva dal menu a discesa per aggiungerla alla vista elenco. Alcune opzioni che possono essere utili sono Chiusura prevista e Probabilità.

La vista _pivot_ organizza in una tabella dinamica tutti i lead che si prevede di chiudere entro la data designata.

Per passare alla vista pivot, fai clic sull’icona Pivot in alto a destra del resoconto.

Al momento della selezione della vista pivot per il resoconto, l’asse X elenca le fasi nella pipeline mentre l’asse Y raggruppa i risultati in base alla data di creazione. Per passare da un raggruppamento all’altro, fai clic sull’icona (⇄) nella parte alta del resoconto.

Per aggiungere ulteriori misure al rapporto, fai clic sul pulsante Misure in alto a sinistra del resoconto. Seleziona le metriche aggiuntive dal menu a tendina.

Per aggiungere un gruppo a una riga o colonna nella vista pivot, fai clic sul ➕ (segno più) accanto al Totale e poi seleziona uno dei gruppi. Per eliminarne uno, fai clic sul segno ➖ (segno menu) e deseleziona l’opzione appropriata.

Fai clic su Inserisci in foglio di calcolo per aggiungere la vista pivot in un formato di foglio di calcolo modificabile all’interno dell’applicazione _Dashboard_. Se è installata l’applicazione _Odoo Documenti_ , il resoconto può essere inserito in un foglio di calcolo vuoto o esistente e poi esportato.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/crm/performance/expected_revenue_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forecast_report.html "Resoconto previsionale") |
  * [precedente](win_loss.html "Analisi flusso di opportunità") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto ricavi previsti


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