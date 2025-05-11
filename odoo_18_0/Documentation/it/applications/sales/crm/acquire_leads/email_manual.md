# Creare lead (da e-mail o manualmente) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](send_quotes.html "Creare e inviare preventivi") |
  * [precedente](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare lead (da e-mail o manualmente)



# Creare lead (da e-mail o manualmente)¶

Oltre ai lead e opportunità creati nell’app attraverso un [modulo di contatto sul sito web](opportunities_form.html), è possibile aggiungere lead al _CRM_ da alias e-mail personalizzati e tramite la creazione manuale di nuovi record.

Per prima cosa, assicurati che le impostazioni relative ai _lead_ siano attivate nel database. Apri l’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. Infine, fai clic su Salva.

## Configurare alias e-mail¶

Ogni team di vendita ha la possibilità di creare e utilizzare il proprio alias e-mail. Quando si inviano messaggi a questo indirizzo, viene creato un lead (od opportunità) con le informazioni contenute nel messaggio.

Per creare o aggiornare gli alias e-mail di un team di vendita, apri l’app CRM ‣ Configurazione ‣ Team vendite. Fai clic su un team dall’elenco che si apre per accedere alla pagina con i dettagli.

Nel campo Alias e-mail, inserisci un nome per l’alias e-mail o modifica il nome esistente. Nel campo Accetta e-mail da, utilizza il menu a discesa per scegliere chi può inviare messaggi a questo alias e-mail:

  * Tutti: i messaggi vengono accettati da qualsiasi indirizzo e-mail

  * Partner autenticati: accetta solo i messaggi provenienti da indirizzi e-mail associati al record di un partner (contatto o cliente)

  * Solo follower: accetta solo i messaggi di coloro che stanno seguendo un record relativo al team, come un lead o un’opportunità. I messaggi vengono accettati anche dai membri del team

  * Dipendenti autenticati: accetta solo i messaggi provenienti da indirizzi e-mail collegati a un record dell’applicazione _Dipendenti_




### Lead creati da e-mail¶

I contatti creati dai messaggi di alias e-mail possono essere visualizzati accedendo all’app CRM ‣ Lead. Fai clic su un lead dall’elenco per aprirlo e visualizzarne i dettagli.

L’e-mail ricevuta dall’alias viene aggiunta al thread del _chatter_ per il lead. L’oggetto del messaggio viene aggiunto al campo titolo e il campo E-mail viene aggiornato con l’indirizzo e-mail del contatto.

Nota

Se la funzione _lead_ **non** è abilitata nel database, i messaggi all’alias e-mail vengono aggiunti al database come opportunità.

Vedi anche

[Comunicazione in Odoo via e-mail](../../../general/email_communication.html)

## Creare lead manualmente¶

I lead possono essere aggiunti direttamente all’applicazione _CRM_ creando manualmente un nuovo record. Apri l’app CRM ‣ Lead per visualizzare un elenco di lead esistenti.

Suggerimento

È possibile aggiungere lead anche tramite il pulsante [Genera lead](lead_mining.html).

Nella parte in alto a sinistra dell’elenco, fai clic su Nuovo per aprire un modulo Lead vuoto.

Nel primo campo del nuovo modulo, inserisci un titolo per il nuovo lead. In seguito, inserisci un Nome contatto e un Nome azienda.

Nota

Se un lead [viene convertito in opportunità](convert.html), il campo Nome azienda viene utilizzato per collegare l’opportunità a un cliente esistente o per creare un nuovo cliente.

### Creare opportunità manualmente¶

Per creare manualmente un’opportunità, apri l’applicazione CRM ‣ Vendite ‣ La mia pipeline. In alto a sinistra della pagina, fai clic su Nuova per creare una nuova opportunità sotto forma di scheda Kanban. Nel campo Organizzazione/Contatto, inserisci il nome dell’azienda per cui è stata creata l’opportunità.

Scegli un nome e inseriscilo nel campo Opportunità. _Si tratta di un campo obbligatorio_. Quando si crea manualmente un’opportunità, è utile aggiungere un nome che si riferisca ai dettagli dell’opportunità.

Example

Nell’esempio che segue, l’opportunità viene denominata “5 sedie VP”. Questo identifica il prodotto a cui il cliente è interessato e il numero potenziale di prodotti.

Inserisci le informazioni di contatto per l’opportunità nei campi E-mail e Telefono.

Nel campo Ricavi previsti inserisci un valore stimato per l’opportunità.

Nota

Le informazioni contenute nei campi Ricavi previsti e priorità possono essere utilizzate per monitorare le prestazioni dei singoli addetti alle vendite e dei team. Per ulteriori informazioni, consulta le sezioni [Resoconto ricavi previsti](../performance/expected_revenue_report.html) e [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html).

Quindi, utilizza le icone __(stella) per assegnare una priorità.

  * ______: priorità bassa

  * ______: priorità media

  * ______: priorità alta

  * ______: priorità altissima




Nota

L’assegnazione di una priorità cambia l’ordine dei lead nella vista Kanban: i lead con priorità alta vengono visualizzati per primi.

Una volta inserite tutte le informazioni necessarie, fai clic su Aggiungi.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/crm/acquire_leads/email_manual.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](send_quotes.html "Creare e inviare preventivi") |
  * [precedente](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare lead (da e-mail o manualmente)


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