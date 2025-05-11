# Google Traduttore — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cloud_storage.html "Archiviazione cloud") |
  * [precedente](geolocation.html "Geolocalizzazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Integrazioni](../integrations.html) »
  * Google Traduttore



# Google Traduttore¶

_Google Traduttore_ può essere utilizzato per tradurre i testi generati dagli utenti nel chatter Odoo.

## Console Google API¶

La maggior parte delle operazioni per l’integrazione di _Google Traduttore_ in Odoo viene effettuata con la _console Google API_. Una volta completati i seguenti processi, viene creata una _chiave API_ da inserire in Odoo.

Vedi anche

[Configurazione Google Traduttore su Google](https://cloud.google.com/translate/docs/setup?hl=it)

### Creare un nuovo progetto¶

Per iniziare, apri la [console di Google API](https://console.developers.google.com/). In seguito, accedi con il tuo account _Google Workspace_ se ce n’è uno, altrimenti accedi con l’account Gmail personale (che dovrebbe corrispondere all’indirizzo e-mail indicato per la fatturazione).

In seguito, fai clic su Crea progetto a destra della schermata di consenso OAuth.

Suggerimento

Se sono già presenti progetti nella _console Google API_ , fai clic sul menu a tendina accanto all’icona Google Cloud e apparirà una finestra. In seguito, fai clic su Nuovo progetto nella parte in alto a destra della finestra a comparsa.

Nella schermata Nuovo progetto, cambia il Nome progetto in `Odoo traduzione` e scegli la Posizione. Imposta la Posizione su _Organizzazione Google Workspace_. Se stai utilizzando un account Gmail personale, la Posizione può restare Nessuna organizzazione.

Fai clic su Crea per terminare questo step.

### Libreria API¶

In seguito, è necessario installare la _Cloud Translation API_ nel progetto appena creato. Per farlo, fai clic su Libreria nel menu a sinistra. Successivamente, cerca il termine `Cloud Translation API` e fai clic sul risultato che dovrebbe essere una _Google Enterprise API_ etichettata come Cloud Translation API.

Fai clic su Abilita per installare la libreria su questo progetto.

Importante

L’utilizzo dell’API _Google Translate_ **richiede** un account di fatturazione [Google](https://myaccount.google.com/).

Una volta configurato un account di fatturazione con _Google_ e attivata la libreria, fai clic su Gestisci per terminare la configurazione sull’API.

### Creare credenziali¶

Ora che il progetto è stato configurato e la Cloud Translation API* attivata, è **obbligatorio** creare delle credenziali che includono la _chiave API_.

Per iniziare il processo, fai clic su Credenziali nel menu laterale a sinistra.

Quindi, fai clic su Crea credenziali nel menu superiore e seleziona chiave API dal menu a discesa.

Copia la chiave API da utilizzare nella prossima sezione.

Importante

Per ragioni di sicurezza, l’utilizzo della _chiave API_ può essere limitato.

Per farlo, vai su _limitazioni API_ facendo clic su Modifica chiave API nella finestra a comparsa oppure facendo clic sulla chiave API nell’elenco presente sulla pagina Credenziali. In questa sezione è possibile configurare le restrizioni che comprendono la configurazione di un’applicazione per limitare l’utilizzo della chiave API e se la chiave API può chiamare qualsiasi API.

È consigliato limitare la _API traduzione_ Odoo per consentire **solo** le richieste dal database Odoo configurato e verso la _Cloud Translation API_.

Per aggiungere limitazioni al sito web, fai clic su Siti web, nella sezione Configura limitazione applicazione. In seguito, inserisci l’indirizzo del database sul quale stai utilizzando _Google Traduttore_ facendo clic su Aggiungi. Infine, aggiungi un URL e fai clic su Fatto.

Per limitare l’uso della chiave a un’API selezionata, seleziona innanzitutto Limita chiave, sotto la sezione Limitazioni API. Quindi utilizza il menu a discesa per scegliere l’API da configurare (_Cloud Translation API_).

Suggerimento

  * Salva la chiave API: copia la chiave API e conservala in un posto sicuro.

  * **Non** condividere pubblicamente la chiave API o esporla nel codice lato cliente.




## Configurazione Odoo¶

Per accedere all’integrazione in Odoo, accedi alla sezione Impostazioni dell’applicazione ‣ Discussioni. Inserisci la chiave API nel campo Traduzione dei messaggi. Quindi, Salva le impostazioni e _Google Translate_ potrà essere utilizzato in tutti i chatter del database.

## Tradurre nel chatter¶

Per tradurre il testo di un utente da un’altra lingua, fai clic sull’icona … (tre puntini) a destra del chatter. In seguiro, seleziona Traduci. Il contenuto verrà tradotto nella _lingua_ configurata nelle preferenze dell’utente.

Vedi anche

[Modificare la lingua](../users/language.html#language-install)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/integrations/google_translate.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cloud_storage.html "Archiviazione cloud") |
  * [precedente](geolocation.html "Geolocalizzazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Integrazioni](../integrations.html) »
  * Google Traduttore


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
  *[POS]: Punto vendita
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
  *[ISBN]: International Standard Book Number