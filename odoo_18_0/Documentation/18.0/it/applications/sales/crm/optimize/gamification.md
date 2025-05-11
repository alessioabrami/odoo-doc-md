# Gamification CRM — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [precedente](partner_autocomplete.html "Arricchire i contatti con l’autocompletamento del partner") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Gamification CRM



# Gamification CRM¶

Nell’applicazione _CRM_ di Odoo, gli _strumenti di gamification_ offrono l’opportunità di valutare e motivare gli utenti attraverso sfide, obiettivi e premi personalizzabili. Gli obiettivi vengono creati per indirizzare le azioni all’interno dell’applicazione _CRM_ e possono essere monitorati e premiati automaticamente dai team di vendita partecipanti.

## Configurazione¶

Per installare il modulo _Gamification CRM_ , accedi al modulo Applicazioni. Fai clic sulla barra Ricerca… nella parte alta della pagina ed elimina il filtro Applicazioni. Cerca `Gamification CRM`.

Fai clic sul pulsante Installa del Gamification CRM. Questo modulo presenta obiettivi e sfide relativi alle applicazioni _CRM_ e _Vendite_.

Nota

Se sono installate entrambe le applicazioni _CRM_ e _Vendite_ , il modulo _Gamification CRM_ viene installato automaticamente sul database.

Per accedere al menu degli _strumenti di gamification_ devi attivare la [Modalità sviluppatore (modalità di debug)](../../../general/developer_mode.html#developer-mode).

Successivamente, accedi all’app Impostazioni ‣ Strumenti di gamification.

## Creare badge¶

I _badge_ vengono assegnati agli utenti quando hanno completato una sfida. I badge possono essere assegnati in base al tipo di task completato e possono essere assegnati a più di un utente, a seconda del tempo impiegato per raggiungere l’obiettivo.

Per visualizzare i badge esistenti o crearne di nuovi, accedi al modulo Impostazioni ‣ Strumenti di gamification ‣ Badge.

Nota

Alcuni badge possono essere assegnati anche al di fuori delle sfide. Seleziona la scheda Kanban per il badge desiderato e poi fai clic su Assegna. Si aprirà una finestra pop-up dal nome Assegna badge. Seleziona un utente dal campo Chi vorresti premiare?.

Aggiungi qualsiasi informazione aggiuntiva sul motivo per cui l’utente riceve la ricompensa nel campo sottostante e poi fai clic su Assegna badge.

Per creare un nuovo badge, fai clic su Nuovo in alto a sinistra della pagina per aprire un modulo vuoto. Inserisci un nome per il Badge, seguito da una descrizione.

Il campo Assegnazione consentita a stabilisce quando è possibile assegnare un badge e da parte di chi:

  * Tutti: questo badge può essere assegnato manualmente da qualsiasi utente.

  * Un elenco specifico di utenti: questo badge può essere assegnato solo da un gruppo selezionato di utenti. Se scegli quest’opzione, verrà generato un nuovo campo dal nome Utenti autorizzati. Scegli l’utente appropriato dall’elenco a discesa.

  * Persone che hanno alcuni badge: questo badge può essere assegnato solo da utenti che già hanno ricevuto dei badge specifici. Se scegli quest’opzione, verrà generato un nuovo campo dal nome Riconoscimenti richiesti. Usa l’elenco a tendina per selezionare i badge che un utente deve possedere prima di poter assegnare il badge ad altri.

  * Nessuno, assegnato tramite sfide: questo badge non può essere assegnato manualmente ma solo tramite sfide.




Per limitare il numero di badge che un utente può inviare, spunta la casella Limite numero mensile per configurare un limite sul numero di volte in cui un utente può assegnare un badge specifico. Nel campo Numero limite, inserisci il numero massimo di volte al mese in cui è possibile inviare il badge, per persona.

## Creare una sfida¶

Per creare una sfida, accedi al modulo Impostazioni ‣ Strumenti di gamification ‣ Sfide. Fai clic su Nuova nell’angolo in alto a sinistra per aprire un modulo vuoto.

Nella parte alta del modulo, inserisci un Nome sfida.

### Creare regole di assegnazione¶

Per assegnare una sfida a utenti specifici, bisogna utilizzare una o più regole di assegnazione.

Fai clic sul primo campo sotto Assegna sfida a e seleziona un parametro dall’elenco a discesa per stabilire una regola. In seguito, fai clic sul campo successivo per stabilire l’operatore della regola. Se necessario, fai clic sul terzo campo per indicare un parametro più specifico.

Suggerimento

Per includere tutti gli utenti con autorizzazioni nell’app _Vendite_ , crea una regola con i seguenti parametri:

  * Gruppi

  * è in

  * `Vendite/Utente: solo documenti personali`




Nel campo Periodicità, seleziona un arco temporale per gli obiettivi da valutare automaticamente.

### Aggiungere obiettivi¶

Le sfide possono basarsi su un singolo obiettivo oppure possono includere più obiettivi con target diversi. Per aggiungere un obiettivo alla sfida, fai clic su Aggiungi riga nella scheda Obiettivi.

Nel campo Definizione obiettivo, scegli un obiettivo dall’elenco a discesa. Il campo Condizione si aggiorna automaticamente riflettendo la condizione impostata nella definizione dell’obiettivo.

Suggerimento

Il modulo _CRM gamification_ contiene obiettivi preconfigurati per i team di vendita:

  * Nuovi lead

  * Tempo per qualificare un lead

  * Giorni per chiudere un affare

  * Nuove opportunità

  * Nuovi ordini di vendita




Inserisci un Traguardo per l’obiettivo in base al Suffisso.

Ripeti questi passaggi per ogni altro obiettivo.

### Aggiungere premi¶

In seguito, fai clic sulla scheda Premio. Scegli i badge da assegnare Per il primo utente e Per gli utenti che hanno successo selezionandoli dall’elenco a discesa.

Nota

I badge vengono assegnati quando una sfida è terminata. Ciò avviene al termine di un periodo di esecuzione, alla data di fine di una sfida o quando la sfida viene chiusa manualmente.

Dopo aver completato la configurazione, fai clic sul pulsante Inizia sfida nella parte in alto a sinistra della pagina per iniziare la sfida.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/crm/optimize/gamification.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [precedente](partner_autocomplete.html "Arricchire i contatti con l’autocompletamento del partner") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Gamification CRM


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Puchase
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