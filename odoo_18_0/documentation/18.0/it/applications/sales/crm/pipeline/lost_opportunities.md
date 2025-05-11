# Opportunità perse — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](merge_similar.html "Unire lead e opportunità simili") |
  * [precedente](../pipeline.html "Organizzare il flusso") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Opportunità perse



# Opportunità perse¶

Non tutte le opportunità si concludono con una vendita. Per mantenere aggiornata la pipeline, è necessario identificare le opportunità _perse_. Specificare il motivo per cui un’opportunità è stata persa aiuta a identificare i problemi ricorrenti, a rivelare le opportunità di coaching e può aiutare a migliorare la strategia di vendita complessiva.

Nota

[L’unione di opportunità perse](merge_similar.html) con opportunità attive comporta il reinserimento nella pipeline.

## Contrassegnare un’opportunità come persa¶

Per contrassegnare un’opportunità come persa, per prima cosa è necessario aprire l’app CRM e poi seleziona un’opportunità dalla pipeline facendo clic sulla scheda kanban corrispondente. Di conseguenza, apparirà il modulo con i dettagli dell’opportunità.

In seguito, fai clic su Persa, nella parte in alto del modulo con i dettagli dell’opportunità.

In seguito, si aprirà la finestra pop-up Imposta a persa. Dal menu a discesa Motivo perdita, scegli un motivo di perdita esistente. Se non è disponibile alcun motivo, creane uno nuovo inserendolo nel campo Motivo perdita e facendo clic su Crea.

È possibile aggiungere note e commenti extra al motivo della perdita nel campo Nota di chiusura.

Suggerimento

Nella finestra pop-up Imposta a persa, non sono necessari né il campo Motivo perdita né il campo Nota di chiusura. Tuttavia, ti consigliamo di includere queste informazioni per motivi di tracciabilità, responsabilità e rendicontazione.

Una volta aggiunte tutte le informazioni desiderate nella finestra pop-up Imposta a persa, fai clic sul pulsante Imposta a persa.

Dopo aver fatto clic su Imposta a persa, un banner rosso dal titolo Persa verrà aggiunto nell’angolo in alto a destra dell’opportunità.

Nota

Per contrassegnare un’opportunità _non attiva_ (archiviata) come persa, inserisci il valore `0` percento nel campo Probabilità.

## Creare/modificare motivi perdita¶

Per creare un nuovo motivo di perdita o modificarne uno esistente, accedi all’app CRM ‣ Configurazione ‣ Motivi perdita.

Per modificare un motivo di perdita esistente, fai clic sul motivo da modificare per evidenziarlo. Da qui, modifica il motivo selezionato modificando il campo Descrizione.

Per creare un nuovo motivo di perdita, fai clic su Nuovo nell’angolo in alto a sinistra della pagina Motivi perdita. Inserisci il nuovo motivo di smarrimento nel campo Descrizione.

## Visualizzare opportunità perse¶

Per recuperare le opportunità, apri l’app CRM ‣ Vendite ‣ La mia pipeline. In seguito, fai clic sulla barra di ricerca nella parte alta della pagina e poi elimina tutti i filtri predefiniti.

Apri il menu a tendina Filtri facendo clic sull’icona __(tendina) a destra della barra di ricerca per aprire il menu a discesa che contiene le opzioni Filtri, Raggruppa per e Preferiti divise in colonne specifiche.

Seleziona l’opzione the Persa dalla sezione Filtri. Dopo aver selezionato Persa, solo le opportunità contrassegnate come `Perse` appariranno nella pagina Pipeline.

### Organizzare le opportunità per motivo perdita¶

Per filtrare le opportunità in base a un motivo specifico di perdita, fai clic sull’icona __(tendina) a destra della barra di ricerca per aprire il menu a discesa. Oltre al filtro Persa, sotto la colonna Filtri, fai clic su Aggiungi filtro personalizzato e si aprirà una finestra pop-up con lo stesso nome: Aggiungi filtro personalizzato.

Nella finestra pop-up Aggiungi filtro personalizzato, fai clic sul primo campo e scrivi `Motivo perdita` nella barra di ricerca, oppure scorri per cercare nella lista e individuarlo. In seguito, fai clic sul campo successivo e seleziona = dal menu a tendina. Fai clic sul terzo campo e seleziona un motivo di perdita dal menu a discesa. Infine, fai clic su Aggiungi.

Suggerimento

Per visualizzare i risultati per più di un motivo di smarrimento, seleziona l’operatore è in nel secondo campo del filtro personalizzato nella finestra pop-up Aggiungi filtro personalizzato. La scelta di questo operatore consente di selezionare più motivi di perdita nel terzo campo.

## Ripristinare le opportunità perse¶

Per ripristinare un’opportunità persa, apri il modulo CRM per svelare la dashboard Pipeline. Oppure, apri l’app CRM ‣ Vendite ‣ La mia pipeline. Da qui, fai clic sull’icona __(tendina) a destra della barra di ricerca per aprire il menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti.

Nella colonna Filtri, seleziona Persa. Così facendo, nella pagina Pipeline, verranno svelate tutte le opportunità perse.

Suggerimento

Per vedere tutte le opportunità nel database, elimina il filtro La mia pipeline predefinito dalla barra di ricerca.

Dal modulo con i dettagli dell’opportunità persa, fai clic su Ripristina nell’angolo in alto a sinistra. Il banner rosso Persa scomparirà dal modulo dell’opportunità.

### Ripristinare più opportunità perse in una volta¶

Per ripristinare più opportunità insieme, apri il mega menu della dashboard facendo clic sull’icona __(tendina) (a destra della barra di ricerca) e seleziona l’opzione predefinita Persa situata sotto la parte sinistra della colonna Filtri.

Successivamente, seleziona l’opzione di visualizzazione a elenco, rappresentata dall’icona __(elenco) nell’angolo in alto a destra. In questo modo, tutte le opportunità della pagina Pipeline vengono visualizzate in un elenco. Una volta scelta la visualizzazione a elenco, seleziona la casella di controllo a sinistra di ogni opportunità da ripristinare.

Una volta selezionate le opportunità desiderate, fai clic sul menu a discesa __ Azioni nella parte superiore della pagina Pipeline. Dal menu a discesa __(Azioni), seleziona Annulla archiviazione.

In questo modo si rimuovono le opportunità selezionate dalla pagina Pipeline perché non rientrano più nei criteri del filtro Persa. Elimina il filtro Persa dalla barra di ricerca per visualizzare le opportunità appena ripristinate.

## Gestire lead persi¶

Se i _lead_ sono attivati in un database, possono essere contrassegnati come _persi_ allo stesso modo delle opportunità. I lead utilizzano gli stessi motivi di perdita delle opportunità.

Nota

Per attivare i lead, apri il modulo CRM ‣ Configurazione ‣ Impostazioni e seleziona la casella di controllo Lead. Questo aggiunge un nuovo menu Lead alla barra dei menu dell’intestazione nella parte superiore della pagina.

### Segnare un contatto come perso¶

Per contrassegnare un lead come perso, apri il modulo CRM ‣ Lead e seleziona un lead dall’elenco. In questo modo verrà visualizzato il modulo dei dettagli del lead. Successivamente, fai clic su Perso, situato nella parte superiore del modulo con i dettagli del lead.

In seguito, si aprirà la finestra pop-up Imposta a persa. Dal menu a discesa Motivo perdita, scegli un motivo di perdita esistente. Se non è disponibile alcun motivo, creane uno nuovo inserendolo nel campo Motivo della perdita per poi selezionare Crea.

È possibile aggiungere ulteriori note e commenti sotto il motivo della perdita indicato nel campo Note di chiusura.

Una volta aggiunte tutte le informazioni desiderate nella finestra pop-up Imposta a persa, fai clic sul pulsante Imposta a persa.

### Ripristinare lead persi¶

Per ripristinare un lead perso, apri il modulo CRM ‣ Lead, quindi fai clic sull’icona __(tendina) a destra della barra di ricerca per aprire il menu a discesa che contiene le colonne Filtri, Raggruppa per e Preferiti.

Nella colonna Filtri, seleziona Persa. Così facendo, tutti i lead persi verranno mostrati nella pagina Lead.

In seguito, fai clic sul lead perso che vuoi ripristinare, per aprire con i moduli del lead.

Dal modulo con i dettagli del lead perso, fai clic su Ripristina nell’angolo in alto a sinistra. Il banner rosso Persa scomparirà dal modulo del lead.

### Ripristinare più lead alla volta¶

Per ripristinare più lead in una sola volta, apri il modulo CRM ‣ Lead, apri il menu a tendina Filtri e seleziona l’opzione Perso. Seleziona la casella di controllo a sinistra di ogni lead da ripristinare.

Una volta selezionate le opportunità desiderate, fai clic sul menu a discesa __ Azioni nella parte superiore della pagina Pipeline. Dal menu __(Azioni), seleziona Annulla archiviazione.

In questo modo, i lead selezionati vengono rimossi dalla pagina Lead perché non rientrano più nei criteri del filtro Perso. Elimina il filtro Perso dalla barra di ricerca per visualizzare i lead appena ripristinate.

Vedi anche

[Analisi flusso di opportunità](../performance/win_loss.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/crm/pipeline/lost_opportunities.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](merge_similar.html "Unire lead e opportunità simili") |
  * [precedente](../pipeline.html "Organizzare il flusso") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Opportunità perse


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