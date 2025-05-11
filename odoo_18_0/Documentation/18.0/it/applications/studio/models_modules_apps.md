# Modelli, moduli e app — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automated_actions.html "Regole di automazione") |
  * [precedente](views.html "Viste") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Modelli, moduli e app



# Modelli, moduli e app¶

I modelli determinano la struttura logica di un database e come i dati vengono salvati, organizzati e manipolati. In altre parole, un modello è una tabella di informazioni che possono essere collegate ad altre tabelle. Di solito, un modello rappresenta un concetto di business come _ordini di vendita_ , _contatti_ o _prodotti_.

I moduli e le app contengono vari elementi come modelli, viste, file di dati, controller web e dati web statici.

Nota

Tutte le applicazioni sono moduli. I moduli più grandi e indipendenti vengono chiamati app mentre altri moduli rappresentano componenti aggiuntivi delle stesse app.

## Funzionalità consigliate¶

Quando crei un nuovo modello o una nuova app con Studio, puoi scegliere di aggiungere fino a 14 funzionalità per velocizzare il processo di creazione. Tali funzionalità legano campi, impostazioni predefinite e viste che di solito vengono utilizzati insieme per fornire alcune funzioni standard. La maggior parte delle funzioni possono essere aggiunte in seguito ma se fatto all’inizio, il processo di creazione del modello sarà più semplice. Inoltre, le funzioni interagiscono tra di loro, in alcuni casi, per aumentare l’utilità.

Example

La creazione di un modello con le funzionalità Immagine e Fasi del flusso attivate, comporta l’aggiunta dell’immagine nel layout della scheda della [vista Kanban](views.html#studio-views-multiple-records-kanban).

### Dettagli contatto¶

Selecting Contact details adds to the [Form view](views.html#studio-views-general-form) a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Contact_ model and two of its [Related Fields](fields.html#studio-fields-relational-fields-related-field): Phone and Email. The Contact field is also added to the [List view](views.html#studio-views-multiple-records-list), and the [Map view](views.html#studio-views-multiple-records-map) is activated.

Example

### Assegnazione utente¶

Selecting User assignment adds to the [Form view](views.html#studio-views-general-form) a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Contact_ model, with the following Domain: `Share User is not set` to only allow the selection of _Internal Users_. In addition, the many2one_avatar_user widget is used to display the user’s avatar. The Responsible field is also added to the [List view](views.html#studio-views-multiple-records-list).

Example

### Data e calendario¶

Selecting Date & Calendar adds to the [Form view](views.html#studio-views-general-form) a [Date field](fields.html#studio-fields-simple-fields-date) and activates the [Calendar view](views.html#studio-views-timeline-calendar).

### Intervallo date e Gantt¶

Selecting Date range & Gantt adds to the [Form view](views.html#studio-views-general-form) two [Date fields](fields.html#studio-fields-simple-fields-date) next to each other: one to set a start date, the other to set an end date, using the daterange widget, and activates the [Gantt view](views.html#studio-views-timeline-gantt).

### Fasi del flusso¶

Selecting Pipeline stages activates the [Kanban view](views.html#studio-views-multiple-records-kanban), adds several fields such as [Priority](fields.html#studio-fields-simple-fields-priority) and Kanban State, and three stages: New, In Progress, and Done. The Pipeline status bar and the Kanban State field are added to the [Form view](views.html#studio-views-general-form). The Color field is added to the [List view](views.html#studio-views-multiple-records-list).

Nota

La funzionalità Fasi del flusso può essere aggiunta anche più tardi.

### Etichette¶

Selecting Tags adds to the [modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Tags field](fields.html#studio-fields-relational-fields-tags), creating a _Tag_ model with preconfigured access rights in the process.

### Immagine¶

Selecting Picture adds to the top-right of the [Form view](views.html#studio-views-general-form) an [Image field](fields.html#studio-fields-simple-fields-image).

Nota

La funzionalità Immagine può essere aggiunta anche in seguito.

### Righe¶

Selecting Lines: adds to the [Form view](views.html#studio-views-general-form) a [Lines field](fields.html#studio-fields-relational-fields-lines) inside a Tab component.

### Note¶

Selecting Notes adds to the [Form view](views.html#studio-views-general-form) an [Html field](fields.html#studio-fields-simple-fields-html) using the full width of the form.

### Valore monetario¶

Selecting Monetary value adds to the [modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Monetary field](fields.html#studio-fields-simple-fields-monetary). The [Grafico](views.html#studio-views-reporting-graph) and [pivot](views.html#studio-views-reporting-pivot) views are also activated.

Nota

Il campo _Valuta_ viene aggiunto e nascosto nella vista.

### Azienda¶

Selecting Company adds to the [modulo](views.html#studio-views-general-form) and [Elenco](views.html#studio-views-multiple-records-list) views a [Many2One field](fields.html#studio-fields-relational-fields-many2one) linked to the _Company_ model.

Nota

Utile solo se lavori in un ambiente con più aziende.

### Ordinamento personalizzato¶

Se selezioni Ordinamento personalizzato, alla [vista elenco](views.html#studio-views-multiple-records-list) verrà aggiunta un’icona per riordinare manualmente i record.

Example

### Chatter¶

Selezionando Chatter, alla [vista modulo](views.html#studio-views-general-form) verranno aggiunte le funzionalità del chatter (inviare messaggi, registrare note e programmare attività).

Nota

La funzionalità Chatter può essere aggiunta anche in seguito.

Example

### Archiviazione¶

Se selezioni Archiviazione, alle viste [modulo](views.html#studio-views-general-form) ed [Elenco](views.html#studio-views-multiple-records-list) verrà aggiunta l’azione Archivia e i record archiviati verranno nascosti dalle ricerche e dalle viste.

## Esportare e importare personalizzazioni¶

Quando esegui una personalizzazione con Studio, al database viene aggiunto un nuovo modulo denominato `studio_customization`. È possibile esportare il modulo come file ZIP utilizzando la funzione Esportazione studio. Il modulo può quindi essere importato in un altro database Odoo. Ciò può essere utile, ad esempio, quando si imposta un nuovo modulo o per scopi di formazione.

Nota

Esportare e importare personalizzazioni in questo modo, invece di utilizzare le funzioni [Odoo standard di esportazione e importazione](../essentials/export_import_data.html) significa che i dati vengono importati in modo logico. Ad esempio, se il modulo contiene clienti e ordini di vendita, vengono prima creati i clienti perché sono necessari per la creazione degli ordini di vendita.

### Esportare personalizzazioni¶

Per esportare le personalizzazioni, fai clic sul pulsante __(Commuta a Studio) sulla dashboard principale di Odoo, poi su Esporta e in seguito hai due opzioni:

  * scaricare tutte le personalizzazioni di Studio facendo clic sul pulsante Esporta

  * scegliere quali dati esportare facendo clic su Configura dati demo e non da esportare.




#### Configurare dati da esportare¶

Per selezionare modelli specifici da esportare, fai clic su Nuovo nella schermata Esportazione Studio, poi inizia a digitare il nome del modello in questione o selezionalo dall’elenco.

Suggerimento

Fai clic su Preimpostazioni per visualizzare un elenco di tutti i modelli del database con record modificati con Studio e tutti i modelli personalizzati creati con Studio. Per configurare uno di questi modelli per l’esportazione, fai clic sul modello per aprirlo e apportare le modifiche richieste.

Seleziona le opzioni di cui hai bisogno:

  * Demo: se i record esportati devono essere considerati come dati demo quando vengono importati.

  * Allegati: se gli allegati relativi ai record esportati devono essere inclusi nell’esportazione.

  * Aggiornabile: se i record esportati devono poter essere aggiornati durante un aggiornamento del modulo.




Se necessario, modifica il Dominio per stabilire quali record del modello dovrebbero essere esportati. Per farlo, fai clic sul pulsante Modifica dominio oppure su __(Modifica filtro) e poi su Modifica dominio, se è il caso. Apporta tutte le modifiche necessarie.

Dopo aver configurato un modello per l’esportazione, fai clic su Esportazione Studio per tornare alla schermata principale. Per scaricare un file ZIP con le personalizzazioni per tutti i modelli elencati, fai clic su Esporta.

Nota

Non è necessario selezionare uno o più modelli, poiché tutti i modelli elencati saranno inclusi nell’esportazione. Per rimuovere un modello dall’esportazione, selezionalo e fai clic sul pulsante __ Azioni e poi __ Elimina.

Nella finestra Esportazione Studio:

  * lascia le caselle di controllo deselezionate per esportare solo le personalizzazioni effettuate con Studio.

  * seleziona Includi dati per includere i dati dai modelli selezionati nell’esportazione.

  * spunta Includi dati demo per includere dati dai modelli selezionati contrassegnati come dati demo. Selezionando quest’opzione, verrà selezionata anche la casella Includi dati.




Fai clic sul pulsante Esporta per scaricare il file ZIP.

### Importare personalizzazioni¶

Avvertimento

Prima di eseguire l’importazione, assicurati che il database di destinazione sia sulla stessa versione di Odoo e contenga le stesse applicazioni e moduli del database di origine. Studio non aggiunge i moduli sottostanti come dipendenze del modulo esportato.

Per importare e installare le personalizzazioni di Studio su un altro database Odoo:

  1. accedi al database di destinazione

  2. fai clic sul pulsante __(Commuta a Studio) sulla dashboard principale di Odoo e poi su Importa

  3. carica il file ZIP esportato. Se devi importare i dati demo, spunta l’opzione Carica dati demo

  4. Fai clic su Installa.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/studio/models_modules_apps.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automated_actions.html "Regole di automazione") |
  * [precedente](views.html "Viste") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Modelli, moduli e app


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