# Autenticazione accesso Microsoft Azure — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ldap.html "Autenticazione LDAP") |
  * [precedente](google.html "Autenticazione accesso Google") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Microsoft Azure



# Autenticazione accesso Microsoft Azure¶

L’autenticazione OAuth di Microsoft Azure è una funzione utile che consente agli utenti di Odoo di accedere al proprio database con il proprio account Microsoft Azure.

Questo è particolarmente utile se l’organizzazione utilizza Azure Workspace e vuole che i dipendenti dell’organizzazione si colleghino a Odoo utilizzando i loro account Microsoft.

Avvertimento

I database ospitati su odoo.com non dovrebbero utilizzare il login OAuth per il proprietario o l’amministratore del database, in quanto questo scollegherebbe il database dal loro account odoo.com. Se l’OAuth è impostato per quell’utente, il database non potrà più essere duplicato, rinominato o gestito in altro modo dal portale odoo.com.

Vedi anche

  * [Outlook Calendar synchronization](../../productivity/calendar/outlook.html)

  * [Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth](../email_communication/azure_oauth.html)




## Configurazione¶

L’integrazione della funzione di accesso Microsoft richiede la configurazione su Microsoft e su Odoo.

### Parametri di sistema Odoo¶

Per prima cosa, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode) e vai su Impostazioni ‣ Funzioni tecniche ‣ Parametri di sistema.

Fai clic su Crea e sul nuovo modulo vuoto che appare aggiungi i seguenti parametri di sistema `auth_oauth.authorization_header` nel campo Chiave e imposta il Valore su `1`. In seguito, fai clic su Salva per terminare.

### Dashboard Microsoft Azure¶

#### Creare una nuova applicazione¶

Una volta configurati i parametri di sistema in Odoo, è necessario creare un’applicazione corrispondente in Microsoft Azure. Per iniziare a creare la nuova applicazione, vai sul [portale di Microsoft Azure](https://portal.azure.com/). Accedi con l’account Microsoft Outlook Office 365 se ne hai uno, altrimenti, accedi con un account Microsoft personale.

Importante

Un utente con accesso amministrativo alle _Impostazioni Azure_ deve connettersi ed eseguire i seguenti passaggi di configurazione.

In seguito, accedi alla sezione denominata Manage Microsoft Entra ID (precedentemente _Azure Active Directory_). Di solito, il link si trova al centro della pagina.

Ora, fai clic sul pulsante Aggiungi (+), situato nel menu in alto e seleziona Registrazione app dal menu a tendina. Nella finestra Registra un’applicazione, rinomina il campo Nome in `Odoo` o qualcosa di riconoscibile. Nella sezione Tipi di account supportati seleziona Accounts in this organizational directory only (Default Directory only - Single tenant).

Avvertimento

I tipi di account supportati possono variare a seconda del tipo di account Microsoft e dell’utilizzo finale dell’OAuth. Ad esempio: il login è destinato agli utenti interni di un’organizzazione o è destinato all’accesso al portale clienti? La configurazione di cui sopra è utilizzata per gli utenti interni di un’organizzazione.

Scegli solo account Microsoft personali se il pubblico target è costituito da utenti del portale. Scegli solo account in questa directory dell’organizzazione (Default Directory only - Single tenant) se il pubblico target è composto da utenti dell’azienda.

Nella sezione Reindirizza URL, seleziona Web come piattaforma e poi inserisci `https://<odoo base url>/auth_oauth/signin` nel campo URL. L”URL di base Odoo è il dominio canonico tramite il quale si può raggiungere la tua istanza Odoo (ad es. _mydatabase.odoo.com_ se il tuo host è su odoo.com) nel campo URL. In seguito, fai clic su Registra e l’applicazione verrà creata.

#### Autenticazione¶

Modifica l’autenticazione della nuova app facendo clic sull’elemento del menu di Autenticazione nel menu a sinistra dopo essere stato reindirizzato verso le impostazioni dell’applicazione dal passaggio precedente.

Successivamente, verrà scelto il tipo di _token_ necessari per l’autenticazione OAuth. Non si tratta di token di valuta, ma di token di autenticazione che vengono passati tra Microsoft e Odoo. Pertanto, non c’è alcun costo per questi token che vengono usati solo per scopi di autenticazione tra due API. Seleziona i token che devono essere emessi dall’endpoint di autorizzazione scorrendo la schermata verso il basso e selezionando le caselle chiamate: Token di accesso (usati per flussi impliciti) e Token ID (usati per flussi impliciti e ibridi).

Fai clic su Salva per essere sicuro di aver salvato le impostazioni.

#### Ottenere le credenziali¶

Dopo aver creato l’applicazione e averla autenticata nella console di Microsoft Azure, si procederà alla raccolta delle credenziali. Per farlo, fai clic sulla voce di menu Panoramica nella colonna di sinistra. Seleziona e copia l”ID applicazione (client) nella finestra che appare. Incolla questa credenziale negli appunti, poiché verrà utilizzata in seguito nella configurazione di Odoo.

Dopo aver completato il passaggio, fai clic su Endpoint nel menu in alto e fai clic su _copia icona_ accanto al campo OAuth 2.0 authorization endpoint (v2). Copia il valore negli appunti.

### Configurare Odoo¶

Infine, l’ultimo step nella configurazione di Microsoft Azure OAuth corrisponde alla configurazione di alcune impostazioni in Odoo. Accedi alle Impostazioni ‣ Integrazioni ‣ Autenticazione OAuth e spunta la casella per attivare la funzionalità di accesso OAuth. Fai clic su Salva per assicurarti che il processo venga salvato. In seguito, accedi al database quando apparirà la schermata di accesso.

Apri di nuovo l’app Impostazioni ‣ Integrazioni ‣ Autenticazione OAuth e fai clic su Fornitori OAuth. Ora, seleziona Nuovo nell’angolo in alto a sinistra e rinomina il fornitore `Azure`.

Incolla l”ID applicazione (client) dalla sezione precedente nel campo ID client. Dopo aver completato questa parte, incolla il nuovo valore OAuth 2.0 authorization endpoint (v2) nel campo URL autorizzazione.

Per il campo UserInfo URL, incolla il seguente URL: `https://graph.microsoft.com/oidc/userinfo`

Nel campo Ambito incolla il seguente valore: `openid profile email`. In seguito, potrai usare il logo Windows come classe CSS class sulla schermata di accesso inserendo il seguente valore: `fa fa-fw fa-windows` nel campo classe CSS.

Spunta la casella accanto al campo Consentito per attivare il fornitore OAuth. Infine, aggiungi `Microsoft Azure` al campo Etichetta pulsante accesso. Il testo apparirà accanto al logo Windows sulla pagina di accesso.

Salva le modifiche per completare la configurazione dell’autenticazione OAuth in Odoo.

### Flussi esperienza utente¶

Affinché un utente possa accedere a Odoo utilizzando Microsoft Azure, deve trovarsi nella Pagina di reimpostazione della password di Odoo. Questo è l’unico modo in cui Odoo è in grado di collegare l’account Microsoft Azure e consentire all’utente di accedere.

Nota

Gli utenti esistenti devono [reimpostare la propria password](../users.html#users-reset-password) per accedere alla pagina di reimpostazione della password di Odoo. I nuovi utenti Odoo devono fare clic sul link di invito per nuovi utenti inviato via e-mail e poi fare clic su Microsoft Azure. Gli utenti non devono impostare una nuova password.

Per accedere a Odoo la prima volta utilizzando il fornitore OAuth Microsoft Azure, accedi alla pagina di reimpostazione della password di Odoo (utilizzando il link di invito). Apparirà una pagina dedicata. In seguito, fai clic sull’opzione denominata Microsoft Azure. La pagina reindirizzerà alla pagina di accesso di Microsoft.

Inserisci l”indirizzo e-mail Microsoft e fai clic su Avanti. Segui il processo per accedere all’account. Se è attiva la 2FA, potrebbe essere necessario completare uno step aggiuntivo.

Infine, dopo aver effettuato l’accesso all’account, la pagina reindirizzerà a una pagina di autorizzazioni in cui verrà richiesto all’utente di Accettare le condizioni di accesso dell’applicazione Odoo alle sue informazioni Microsoft.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/users/azure.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ldap.html "Autenticazione LDAP") |
  * [precedente](google.html "Autenticazione accesso Google") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Microsoft Azure


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
  *[API]: application programming interfaces
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
  *[2FA]: Autenticazione a due fattori
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