# Creare e inviare preventivi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_mining.html "Estrarre lead") |
  * [precedente](email_manual.html "Creare lead \(da e-mail o manualmente\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare e inviare preventivi



# Creare e inviare preventivi¶

Una volta che un lead qualificato è stato convertito in un’opportunità, il passo successivo è creare e consegnare un preventivo. Questo processo può essere facilmente gestito attraverso l’applicazione _CRM_ di Odoo.

## Creare un nuovo preventivo¶

Per creare un nuovo preventivo, apri l’app CRM per poi accedere alla Pipeline nella dashboard principale del _CRM_.

Da qui, fai clic su qualsiasi opportunità per aprirla. Revisiona le informazioni esistenti e aggiorna i campi, se necessario.

Nota

Se è già stato creato un preventivo per quest’opportunità, è possibile trovarlo facendo clic sul pulsante Preventivo nella parte superiore del modulo. Anche il numero di preventivi esistenti è elencato sul pulsante smart.

Nella parte in alto a sinistra del modulo, fai clic sul pulsante Nuovo preventivo.

Importante

Per far apparire il pulsante Nuovo preventivo, **bisogna** installare l’app **Vendite**.

Importante

Il campo Cliente **non** è richiesto sul modulo opportunità.

Tuttavia, le informazioni sul cliente devono essere aggiunte o collegate prima di poter inviare un preventivo. Se il campo Cliente è lasciato vuoto nell’opportunità, facendo clic sul pulsante Nuovo preventivo si aprirà una finestra pop-up con le seguenti opzioni:

  * Crea un nuovo cliente: crea un nuovo record cliente, utilizzando tutte le informazioni disponibili fornite nel modulo dell’opportunità.

  * Collega a un cliente esistente: apre un campo a discesa con i nomi dei clienti esistenti. Scegli un nome per collegare questo nuovo preventivo a un record cliente esistente.

  * Non collegare a un cliente: l’offerta **non** viene collegata a un cliente e non vengono apportate modifiche alle informazioni sul cliente.




Una volta fatto clic su questo pulsante, viene visualizzato un nuovo modulo di preventivo. Conferma le informazioni nella parte superiore del modulo e aggiorna i campi mancanti o errati:

  * Cliente: l’azienda o il contatto per cui è stato creato il preventivo.

  * Segnalatore: se il cliente è stato segnalato da un altro cliente o contatto, selezionalo dal menu a discesa in questo campo.

  * Indirizzo di fatturazione: l’indirizzo fisico a cui inviare la fattura.

  * Indirizzo di consegna: l’indirizzo fisico dove consegnare i prodotti.

  * Modello preventivo: se applicabile, seleziona un [modello di preventivo](../../sales/sales_quotations/quote_template.html) preconfigurato da questo campo.

  * Scadenza: data di scadenza della validità del preventivo.

  * Data preventivo: la data di creazione di ordini in bozza/inviati, la data di conferma di ordini confermati. Nota che questo campo è visibile solo se hai attivato la [modalità sviluppatore (debug)](../../../general/developer_mode.html).

  * Piano ricorrente: se il preventivo è per un prodotto o abbonamento ricorrente, scegli la configurazione del piano ricorrente da usare.

  * Listino prezzi: seleziona un listino prezzi da applicare all’ordine.

  * Termini di pagamento: seleziona qualsiasi termine di pagamento applicabile per questo preventivo.




Suggerimento

Il campo Scadenza si popola automaticamente in base alla data di creazione del preventivo e l’arco temporale di validità predefinito.

Per aggiornare l’arco temporale di validità predefinito, apri l’app Vendite ‣ Configurazione ‣ Impostazioni ‣ Preventivi e ordini e aggiorna il campo Validità predefinita del preventivo. Per disattivare la scadenza automatica, inserisci `0` in questo campo.

Una volta completate le modifiche, fai clic su Salva.

Quando usi un modello di preventivo, la data di scadenza si basa sul campo Validità del preventivo del modello. Per modificare il calcolo della data di validità di un modello, apri l’applicazione Vendite ‣ Configurazione ‣ Ordini di vendita ‣ Modelli di preventivo.

In seguito, fai clic su un modello per aprirlo e aggiorna il numero nel campo Validità preventivo.

### Righe ordine¶

Dopo aver aggiornato le informazioni relative al cliente, al pagamento e alla scadenza del nuovo preventivo, la scheda Righe ordine può essere aggiornata con le informazioni relative al prodotto.

Per farlo, fai clic su Aggiungi un prodotto nella scheda Righe ordine.

In seguito, digita il nome di un articolo nel campo Prodotto da cercare nel catalogo dei prodotti. Quindi, seleziona un prodotto dal menu a tendina o creane uno nuovo selezionando Crea o Crea e modifica.

Dopo aver selezionato un prodotto, aggiorna la Quantità, se necessario. Conferma le informazioni nei campi rimanenti.

Per eliminare una riga dal preventivo, fai clic sull’icona __(cestino).

Per organizzare i prodotti in sezioni, fai clic su Aggiungi una sezione e digita un nome per la sezione. Quindi, fai clic sull’icona __(trascinamento) a sinistra del nome e trascinala per spostare la sezione nella posizione appropriata. Sposta ogni prodotto usando lo stesso metodo per finire di organizzare le righe dell’ordine di preventivo.

#### Catalogo prodotti¶

Per aggiungere rapidamente più prodotti al preventivo, fai clic sul pulsante Catalogo per aprire il catalogo dei prodotti.

Tutti i prodotti nel database vengono elencati come schede e possono essere ordinati per Categoria prodotto e Attributi nel pannello di sinistra.

Per aggiungere un prodotto, fai clic sul pulsante __ Aggiungi sulla scheda prodotto. Imposta la quantità dell’articolo utilizzando i pulsanti __(aggiungi) o __(sottrai), oppure digita la quantità nel campo numerico tra i due pulsanti. Per rimuovere un articolo, fai clic sul pulsante __ Elimina della scheda prodotto.

Una volta impostate tutte le quantità dei prodotti, fai clic sul pulsante Torna al preventivo. Gli articoli selezionati nel catalogo prodotti appaiono ora nella scheda Righe ordine.

## Visualizzare l’anteprima e inviare un preventivo¶

Per visualizzare un’anteprima del preventivo come la vedrà il cliente, fai clic sul pulsante Anteprima. In questo modo si apre un’anteprima nel Portale clienti.

Dopo aver esaminato l’anteprima del cliente, fai clic su Torna alla modalità di modifica per tornare al modulo di preventivo nel backend.

Quando il preventivo è pronto per essere inviato al cliente, fai clic sul pulsante Invia con e-mail.

In questo modo si apre una finestra pop-up con un messaggio e-mail preconfigurato. Le informazioni del preventivo, comprese le informazioni di contatto, il costo totale e il titolo del preventivo, vengono importate dal preventivo stesso.

Un PDF del preventivo viene aggiunto come allegato all’e-mail.

Nota

Per creare il messaggio e-mail viene utilizzato un modello preconfigurato. Per modificare il modello, fai clic sul collegamento interno a destra del campo Carica modello, situato in fondo alla finestra pop-up dell’e-mail.

Per selezionare un nuovo modello, scegli un’opzione dal menu a discesa Carica modello.

Applica tutte le modifiche che ritieni necessarie e poi fai clic su Invia. Una copia del messaggio viene aggiunta nel _Chatter_ del record.

Dopo l’invio di un preventivo, il pulsante Preventivi dell’opportunità si aggiorna con un nuovo conteggio. Questo preventivo e tutti gli altri preventivi sono accessibili attraverso questo pulsante intelligente nella parte superiore dell’opportunità nell’applicazione _CRM_.

Eventuali preventivi allegati all’opportunità che sono stati confermati e che sono stati quindi convertiti in ordini di vendita, saranno dedotti dal numero elencato nel pulsante Preventivi. Il valore dell’ordine di vendita apparirà invece nel pulsante Ordini situato nello stesso pannello di controllo.

## Contrassegnare un’opportunità come vinta o persa¶

Per mantenere la pipeline aggiornata e precisa, le opportunità devono essere identificate come _vinte_ o _perse_ una volta che il cliente ha risposto a un preventivo.

Per contrassegnare un’opportunità come _vinta_ o _persa_ , torna all’opportunità utilizzando il percorso in alto a sinistra del modulo di preventivo oppure apri l’app CRM ‣ Vendite ‣ La mia pipeline e fai clic sull’opportunità che vuoi aprire.

In alto a sinistra del modulo, fai clic sul pulsante Vinta o Persa.

Se l’opportunità è contrassegnata come _vinta_ , al record viene aggiunto il banner verde Vinta e viene spostato nella fase Vinta corrispondente.

Contrassegnando un’opportunità come _persa_ , tramite il pulsante Persa si apre una finestra pop-up Imposta a persa, in cui è possibile inserire un Motivo della perdita.

Scegli un motivo esistente dal campo a discesa Motivo perdita. Se non è disponibile alcun motivo, creane uno nuovo inserendolo nel campo Motivo perdita per poi fare clic su Crea.

Suggerimento

È buona norma cercare di utilizzare il più possibile i valori preconfigurati del campo Motivo perdita o limitare la creazione di nuovi valori solo ai lead del team di vendita. L’uso di valori coerenti per questo parametro renderà l’analisi della pipeline più facile e più accurata quando si filtra per il parametro Motivo perdita.

Per configurare nuovi valori per questo campo, apri il modulo CRM ‣ Configurazione ‣ Motivi perdita e fai clic sia su Nuovo che su Salva per ogni nuova voce aggiunta all’elenco.

È possibile aggiungere note e commenti nel campo Nota di chiusura.

Una volta aggiunte tutte le informazioni desiderate nella finestra pop-up Imposta a persa, fai clic sul pulsante Imposta a persa.

Dopo aver fatto clic su Imposta a persa, la finestra pop-up scompare e Odoo torna al modulo dell’opportunità dove appare un nuovo banner rosso Persa nell’angolo in alto a destra dell’opportunità.

Quando un’opportunità viene contrassegnata come _persa_ , non è più considerata attiva e viene rimossa dalla pipeline.

Per visualizzare un’opportunità _persa_ nella pipeline, fai clic sull’icona freccia giù a destra della barra di ricerca e seleziona la voce Persa o Archiviata dal menu a tendina che appare.

Importante

Sebbene le opportunità contrassegnate come _perse_ siano considerate _archiviate_ , tieni presente che, affinché un’opportunità sia inclusa come _persa_ nella reportistica, essa **deve** essere contrassegnata specificamente come _persa_ , non come _archiviata_.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/crm/acquire_leads/send_quotes.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lead_mining.html "Estrarre lead") |
  * [precedente](email_manual.html "Creare lead \(da e-mail o manualmente\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare e inviare preventivi


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