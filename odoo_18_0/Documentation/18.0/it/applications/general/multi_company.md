# Multi-azienda — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot.html "Internet delle cose \(IoT\)") |
  * [precedente](companies/email_template.html "Modelli e-mail") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Multi-azienda



# Multi-azienda¶

In Odoo, possono coesistere varie aziende in un unico database. Ciò consente di condividere alcuni dati fra le varie aziende pur mantenendo le entità separate.

Prima di decidere se utilizzare la funzionalità multi-azienda, è necessario configurare vari fattori.

Importante

La funzionalità aziende multiple è disponibile **solo** per i database _Una app gratuita*_ oppure con i piani [Personalizzati](https://www.odoo.com/pricing-plan).

## Accedere a più aziende¶

L’elenco di [aziende accessibili da un dipendente](companies.html#general-employee-access) in un multi-company database è accessibile nella parte in alto a destra del menu Odoo principale, dove vengono elencate le aziende attive. Fai clic sul nome dell’azienda per visualizzare un elenco delle aziende consentite. Per passare a un’altra azienda, fai clic sul nome della stessa nel menu a tendina. Per attivare più aziende insieme, spunta le caselle accanto ai nomi delle aziende stesse.

Un esempio di utente con accesso a varie aziende. L’azienda attuale è MyCompany (San Francisco), mentre è attiva anche My Company (Chicago).¶

Nota

Il database potrebbe aggiornarsi dopo aver spuntato le caselle.

### Più aziende attive¶

Se più di un’azienda risulta attiva, una di esse viene evidenziata in viola ed elencata nella barra menu. Questa è considerata l’azienda _corrente_.

Quando crei un nuovo record, l’azienda attuale viene aggiunta al record nel campo _Azienda_ , ad eccezione delle seguenti circostanze:

  * il campo _Azienda_ per un nuovo prodotto o contatto viene lasciato vuoto;

  * Se nel sistema esiste già un documento correlato, il campo _Azienda_ nel nuovo record fa riferimento alla stessa azienda.




Example

Mitchell Admin ha più aziende attive ma l’azienda attuale è `My Company (Chicago)`. Quando crea un nuovo record per un prodotto, il campo Azienda viene lasciato vuoto per impostazione predefinita.

Quando viene creato un nuovo team di vendita, il campo Azienda viene compilato automaticamente con `My Company (Chicago)`.

## Condividere dati¶

In un multi-company database, alcuni record possono essere utilizzati da tutte le aziende (o diverse, in base ai permessi).

### Prodotti¶

In un multi-company database, i nuovi prodotti sono creati con il campo Azienda vuoto di default. Se il campo _Azienda_ resta vuoto, il prodotto viene condiviso in tutte le aziende.

### Contatti¶

Come i prodotti, anche i record dei contatti vengono condivisi fra le varie aziende per impostazione predefinita. Per limitare l’accesso a una sola azienda, fai clic sul campo Azienda nel modulo del contatto e seleziona l’azienda a cui assegnarlo.

## Transazioni interaziendali¶

La funzione [Transazioni interaziendali](companies.html#general-inter-company) consente a un’azienda del database di vendere o acquistare beni e servizi da un’altra azienda dello stesso database. I documenti di contropartita per gli ordini e le fatture possono essere generati e sincronizzati automaticamente, a seconda delle impostazioni di configurazione.

Avvertimento

Per garantire che le transazioni interaziendali vengano gestite correttamente, alcune configurazioni come posizioni di bilancio e localizzazioni devono essere impostate con attenzione. Vedi [Transazioni interaziendali](companies.html#general-inter-company) per maggiori informazioni.

## Casi d’uso¶

### Aziende multinazionali¶

Una catena multinazionale di vendita al dettaglio, che opera negli Stati Uniti e in Canada, ha bisogno di gestire le transazioni in valuta USD e CAD.

Inoltre, poiché i due Paesi hanno leggi e normative fiscali diverse, è nell’interesse del cliente utilizzare la funzione multiaziendale.

In questo modo è possibile effettuare le transazioni interaziendali necessarie per gestire i movimenti di magazzino attraverso i confini internazionali, semplificando al contempo le vendite ai clienti di entrambi i Paesi nella loro valuta.

### Processi separati¶

Una piccola azienda di mobili sta sviluppando una nuova linea di prodotti che richiede un processo di approvvigionamento, magazzino e produzione separati. I nuovi prodotti sono drasticamente diversi dal catalogo esistente. L’azienda sta pensando di utilizzare la funzione multi-azienda per trattare questa nuova linea come un’entità diversa.

Per evitare che il database diventi eccessivamente complesso, l’azienda di mobili non ha bisogno di aggiungere un’azienda completamente nuova. Può invece sfruttare le funzionalità esistenti, come [contabilità analitica](../finance/accounting/reporting/analytic_accounting.html) e i magazzini multipli, per gestire la nuova linea di prodotti, senza dover complicare eccessivamente le transazioni.

## Limitazioni¶

In alcuni casi, un multi-company database potrebbe _non_ essere la migliore opzione per via di potenziali limitazioni.

### Diritti di accesso¶

I diritti di accesso di un utente sono configurati a livello di database. Se un utente ha accesso a più di un’azienda in un multi-company database, i suoi diritti di accesso sono gli stessi per ogni azienda.

### Record condivisi¶

I record individuali vengono condivisi tra tutte le aziende oppure appartengono a una sola azienda.

### Reportistica in PDF¶

Alcune personalizzazioni, in particolare per i resoconti in PDF, si applicano a tutte le aziende. Non è sempre possibile separare i resoconti per le singole aziende.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/multi_company.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot.html "Internet delle cose \(IoT\)") |
  * [precedente](companies/email_template.html "Modelli e-mail") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Multi-azienda


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
  *[MRR]: Monthly Recurring Revenue
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
  *[MID]: Merchant ID
  *[TID]: Terminal ID