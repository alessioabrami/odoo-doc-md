# Autenticazione accesso Google — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](azure.html "Autenticazione accesso Microsoft Azure") |
  * [precedente](facebook.html "Autenticazione accesso Facebook") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Google



# Autenticazione accesso Google¶

L” _autenticazione accesso Google_ è una funzione utile che consente agli utenti di Odoo di accedere al proprio database con il proprio account Google.

Questo è particolarmente utile se l’organizzazione utilizza Google e vuole che i dipendenti dell’organizzazione si colleghino a Odoo utilizzando i loro account Google.

Avvertimento

I database ospitati su odoo.com non dovrebbero utilizzare il login OAuth per il proprietario o l’amministratore del database, in quanto questo scollegherebbe il database dal loro account odoo.com. Se l’OAuth è impostato per quell’utente, il database non potrà più essere duplicato, rinominato o gestito in altro modo dal portale odoo.com.

Vedi anche

  * [Google Calendar synchronization](../../productivity/calendar/google.html)

  * [Collegare Gmail a Odoo utilizzando Google OAuth](../email_communication/google_oauth.html)




## Configurazione¶

L’integrazione della funzione di accesso Google richiede la configurazione _sia_ su Google _che_ su Odoo.

### Dashboard Google API¶

  1. Accedi alla [Dashboard Google API](https://console.developers.google.com/).

  2. Assicurati di aver aperto il progetto giusto. Se non hai ancora creato un progetto, fai clic su Crea progetto, inserisci il nome e altri dettagli relativi all’azienda e poi fai clic su Crea.

Suggerimento

Scegli il nome dell’azienda dal menu a tendina.




#### Schermata di consenso OAuth¶

  1. Nel menu a sinistra, fai clic sulla schermata di consenso OAuth.

  2. Scegli una delle opzioni tra (Interno/Esterno) e fai clic su Crea.

Avvertimento

Gli account Gmail _personali_ possono essere utilizzati solo con il tipo di utente **esterno** , il che significa che Google potrebbe richiedere l’approvazione o di aggiungere degli _Ambiti_. Tuttavia, l’uso di un account _Google WorkSpace_ consente di utilizzare il tipo di utente **interno**.

Inoltre, nota che quando la connessione API è in modalità di test _esterna_ , non è necessaria l’approvazione di Google. Il limite di utenti in questa modalità di test è impostato su 100 utenti.

  3. Completa i dettagli richiesti e le informazioni di dominio, poi fai clic su Salva e Continua.

  4. Nella pagina Ambiti, non modificare le opzioni relative ai campi e fai clic su Salva e continua.

  5. Se continui in modalità di prova (esterno), aggiungi gli indirizzi e-mail configurati nella fase Utenti test, facendo clic su Aggiungi utenti e poi sul pulsante Salva e continua. Verrà visualizzato un riepilogo della registrazione dell’applicazione.

  6. Infine, scorri fino in fondo e fai clic su Torna a dashboard.




#### Credenziali¶

  1. Nel menu a sinistra, fai clic su Credenziali.

  2. Fai clic su Create credenziali e seleziona ID client OAuth.

  3. Seleziona Applicazione web come Tipo di applicazione. Ora, configura le pagine consentite su cui verrà reindirizzato Odoo.

Per farlo, nel campo Authorized redirect URIs inserisci il dominio del database seguito da `/auth_oauth/signin`. Ad esempio: `https://mydomain.odoo.com/auth_oauth/signin`, e poi fai clic su Crea.

  4. Ora che il _client OAuth_ è stato creato, apparirà una schermata con ID client e Client segreto. Copia l”ID client per il seguito, poiché sarà necessario per la configurazione in Odoo, che sarà trattata nei passi successivi.




### Autenticazione Google su Odoo¶

#### Recuperare l’ID client¶

Una volta completati i passaggi precedenti, nella dashboard della Google API vengono generate due chiavi: ID client ID e Client segreto. Copia l”ID client.

#### Attivazione di Odoo¶

  1. Vai su Impostazioni generali Odoo ‣ Integrazioni e attiva Autenticazione OAuth.

Nota

Odoo potrebbe richiedere all’utente di effettuare nuovamente il login dopo questo passaggio.

  2. Torna su Impostazioni generali ‣ Integrazioni ‣ Autenticazione OAuth, attiva la selezione e Salva. Quindi, torna alle Impostazioni generali ‣ Integrazioni ‣ Autenticazione Google e attiva la selezione. Compila quindi ID client con la chiave della dashboard Google API e Salva.

Nota

La configurazione di Google OAuth2 è accessibile anche facendo clic su Fornitori OAuth sotto la voce Autenticazione OAuth in Integrazioni.




## Accedere a Odoo tramite Google¶

Per collegare l’account Google al profilo Odoo, fai clic su Accedi con Google al primo accesso a Odoo.

> Gli utenti esistenti devono [ripristinare la password](../users.html#users-reset-password) per accedere alla pagina Reset password, mentre i nuovi utenti possono cliccare direttamente su Accedi con Google, invece di scegliere una nuova password.

Vedi anche

  * [Google Cloud Platform Console Help - Configurazione OAuth 2.0](https://support.google.com/cloud/answer/6158849)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/general/users/google.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](azure.html "Autenticazione accesso Microsoft Azure") |
  * [precedente](facebook.html "Autenticazione accesso Facebook") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Google


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