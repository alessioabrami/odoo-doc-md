# Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google_oauth.html "Collegare Gmail a Odoo utilizzando Google OAuth") |
  * [precedente](email_domain.html "Configurare record DNS per inviare e-mail in Odoo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth



# Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth¶

Odoo è compatibile con l’OAuth Azure di Microsoft per Microsoft 365. Per inviare e ricevere e-mail sicure da un dominio personalizzato, tutto ciò di cui hai bisogno è configurare alcune impostazioni nella piattaforma Azure e nel backend del database Odoo. La configurazione funziona sia con un indirizzo e-mail personale che un indirizzo creato da un dominio personalizzato.

Vedi anche

[Microsoft Learn: Guida introduttiva: Registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app)

Vedi anche

  * [Autenticazione accesso Microsoft Azure](../users/azure.html)

  * [Outlook Calendar synchronization](../../productivity/calendar/outlook.html)




## Configurazione nel portale Microsoft Azure¶

### Creare una nuova applicazione¶

Per iniziare, apri il [Portale Microsoft’s Azure](https://portal.azure.com/). Accedi con l’account Microsoft Outlook Office 365 se ne hai uno, oppure accedi con un account Microsoft. Un utente con accesso amministrativo alle impostazioni di Azure dovrà connettersi ed eseguire la seguente configurazione. In seguito, accedi alla sezione nominata Gestisci ID Microsoft Entra (precedentemente _Azure Active Directory_).

Ora, fai clic sul pulsante Aggiungi (+), situato nel menu in alto e seleziona Registrazione app. Nella finestra Registra un’applicazione, rinomina il campo Nome in `Odoo` o qualcosa di riconoscibile. Nella sezione Tipi di account supportati seleziona Account in qualsiasi directory organizzativa (qualsiasi directory Microsoft Entra ID - Multitenant) e account Microsoft (ad es. Skype, Xbox).

Nella sezione Reindirizza URL, seleziona Web come piattaforma e poi inserisci `https://<web base url>/microsoft_outlook/confirm` nel campo URL. Il `web.base.url` è soggetto a modifiche a seconda dell’URL utilizzato per accedere al database.

Nota

La documentazione sul [web.base.url](../../websites/website/configuration/domain_names.html#domain-name-web-base-url) spiega come bloccare un URL unico. È anche possibile aggiungere vari url di reindirizzamento nell’app Microsoft.

Dopo che l’URL è stato aggiunto al campo, Registra l’applicazione per crearla.

### Autorizzazioni API¶

Le Autorizzazioni API possono essere configurate in seguito. Odoo avrà bisogno di autorizzazioni API per poter leggere (IMAP) e inviare (SMTP) e-mail nella configurazione Microsoft 365. Per prima cosa, fai clic sul link Autorizzazioni API situato nella barra menu a sinistra. In seguito, fai clic sul pulsante (+) Aggiungi autorizzazione e seleziona Microsoft Graph sotto API Microsoft più utilizzate. In seguito, seleziona l’opzione Autorizzazioni delegate.

Nella barra di ricerca, digita Delegated permissions e fai clic su Add permissions per ognuno:

  * SMTP.Send

  * IMAP.AccessAsUser.All




Nota

L’autorizzazione User.Read verrà aggiunta per impsotazione predefinita.

## Assegnare utenti e gruppi¶

Dopo aver aggiunto le autorizzazioni API, torna alla Panoramica della Applicazione nella parte alta del menu laterale di sinistra.

Ora, aggiungi utenti all’applicazione. Nella scheda Essentials, fai clic sul link rinominato Applicazione gestita nella directory locale oppure sull’ultima opzione in fondo a destra della tabella.

Nel menu laterale di sinistra, seleziona Utenti e gruppi. In seguito, fai clic su (+) Aggiungi utente/gruppo. In base all’account, è possibile aggiungere un Gruppo e un Utente, oppure solo Utenti. Gli account personali consentono di aggiungere solo Utenti.

Sotto la sezione Utenti o Gruppi, fai clic su Nessuno selezionato e aggiungi gli utenti o gruppi di utenti che invieranno e-mail dall” account Microsoft in Odoo. Aggiungi utenti/gruppi, fai clic su Seleziona e poi Assegna all’applicazione.

### Creare credenziali¶

Una volta configurata l’app Microsoft Azure, è necessario creare delle credenziali per la configurazione di Odoo che includono l” ID client e il Segreto client. Per iniziare, l” ID client può essere copiato dalla pagina Panoramica dell’app. L” ID client o l” ID applicazione si trova nel campo Visualizza nome nella panoramica Essentials dell’app.

In seguito, è necessario recuperare il Valore segreto client. Per ottenere il valore, fai clic su Certificati e segreti nel menu laterale a sinistra. In seguito, bisogna generare un Segreto client. Per farlo, fai clic sul pulsante (+) Nuovo segreto client.

In una finestra sulla destra apparirà il pulsante Aggiungi segreto client. Nel campo Descrizione scrivi `Odoo Fetchmail` o qualcosa di riconoscibile e configura la data di scadenza.

Importante

Sarà necessario produrre e configurare un nuovo Segreto client se il primo scade. In questo caso, potrebbe verificarsi un’interruzione del servizio quindi la data di scadenza dovrebbe essere impostata alla data più lontana possibile.

In seguito, fai clic su Aggiungi quando inserisci i due valori. Verranno creati un Valore segreto client e un ID segreto. È importante copiare il Valore o il Valore segreto client in un blocco note in quanto verrà crittografato una volta chiusa la pagina. L” ID segreto non è necessario.

Dopo avere eseguito questi step, i seguenti elementi saranno pronti per essere configurati in Odoo:

  * un ID client (ID client o ID Applicazione);

  * un segreto client (Valore o Valore segreto client).




La configurazione lato Portale Microsoft Azure sarà così completa.

## Installazione in Odoo¶

### Inserire le credenziali Microsoft Outlook¶

Per prima cosa, apri il database Odoo e accedi al modulo App. In seguito, elimina il filtro App dalla barra di ricerca e digita `Outlook`. Infine, installa il modulo chiamato Microsoft Outlook.

Successivamente, vai su Impostazioni ‣ Impostazioni generali e nella sezione Comunicazioni assicurati che la casella per Server e-mail personalizzate sia spuntata. Così facendo, spunterà una nuova opzione per le credenziali Outlook.

Salva i progressi.

In seguito, copia e incolla l” ID client (ID applicazione) e il Segreto client (Valore segreto client) nei rispettivi campi e Salva le impostazioni.

### Configurare server e-mail in uscita¶

Nella pagina Impostazioni generali, nella sezione Server e-mail personalizzate, fai clic sul link Server e-mail in uscita per configurare l’account Microsoft.

Crea un nuovo server e-mail e spunta la casella per Outlook. La prossima tappa sarà compilare il Nome (può essere qualsiasi cosa) e il Nome utente dell’e-mail Microsoft Outlook.

Se il campo Filtro mittente è vuoto, inserisci un [dominio o indirizzo e-mail](email_servers_outbound.html#email-outbound-unique-address).

In seguito, fai clic su Collega il tuo account Outlook.

Si aprirà una nuova finestra da Microsoft per completare il processo di autorizzazione. Seleziona l’indirizzo e-mail appropriato che stai configurando in Odoo.

In seguito, autorizza Odoo ad accedere all’account Microsoft facendo clic su Sì. La pagina tornerà al nuovo Server e-mail in uscita appena configurato in Odoo. La configurazione carica automaticamente il token in Odoo e apparirà in verde un tag dal titolo Token Outlook valido.

Infine, fai clic su Prova connessione. Dovrebbe apparire un messaggio di conferma. Ora è possibile inviare e-mail sicure dal database Odoo attraverso Microsoft Outlook utilizzando l’autenticazione OAuth.

#### Configurazione con un signolo server e-mail in uscita¶

La configurazione di un singolo server in uscita è quella più semplice disponibile per Microsoft Azure e non richiede diritti di accesso aggiuntivi per gli utenti del database.

Verrà utilizzato un indirizzo e-mail generico per inviare e-mail a tutti gli utenti nel database. Ad esempio, potrebbe essere configurato con un alias `notifiche` (`notifiche@esempio.com`) o `contatto` (`contatto@esempio.com`). L’indirizzo dovrebbe essere configurato come Filtro mittente sul server. L’indirizzo deve corrispondere anche alla combinazione chiave `{mail.default.from}@{mail.catchall.domain}` nei parametri di sistema.

Vedi anche

Leggi la [documentazione relativa al filtro mittente](email_servers_outbound.html#email-outbound-different-servers-personalized-from-filtering) per maggiori informazioni.

Nota

È possibile accedere ai Parametri di sistema attivando la [Modalità sviluppatore (modalità di debug)](../developer_mode.html#developer-mode) in Impostazioni ‣ Funzioni tecniche ‣ Parametri ‣ Parametri di sistema.

Quando utilizzi questa configurazione, ogni e-mail inviata dal database utilizzerà l’indirizzo della casella e-mail `notifiche` configurata. Tuttavia, è bene tenere a mente che il nome del mittente apparirà ma l’indirizzo e-mail sarà diverso:

Example

Configurazione di un server e-mail in uscita singolo:

  * **Nome utente** (login) server e-mail in uscita = `notifiche@esempio.com`

  * Filtro mittente server e-mail in uscita = `notifiche@esempio.com`

  * `mail.catchall.domain` nei parametri di sistema = `example.com`

  * `mail.default.from` nei parametri di sistema = `notifiche`




#### Configurazione specifica per l’utente (utenti multipli)¶

Oltre ad un server e-mail generico, è possibile configurare server e-mail individuali per gli utenti di un database. Tali indirizzi e-mail devono essere configurati come Filtro mittente su ogni singolo server affinché la configurazione funzioni.

Questa configurazione è quella più difficile tra le due configurazioni di Microsoft Azure e richiede che tutti gli utenti configurati con i server e-mail abbiano i diritti di accesso alle impostazioni per stabilire una connessione al server e-mail.

##### Imposta¶

Ogni utente deve avere un server e-mail separato configurato. Il Filtro mittente deve essere configurato così che solo l’e-mail dell’utente verrà inviata da quel server. In altre parole, solo un utente con un indirizzo e-mail che corrisponde al Filtro mittente può usare il server.

Vedi anche

Leggi la [documentazione relativa al filtro mittente](email_servers_outbound.html#email-outbound-different-servers-personalized-from-filtering) per maggiori informazioni.

Un s:ref:`server fallback <azure_oauth/notifications>` deve essere configurato per consentire l’invio di notifiche. Il Filtro mittente del server dovrebbe avere il valore del `{mail.default.from}@{mail.catchall.domain}`.

Nota

È possibile accedere ai Parametri di sistema attivando la [Modalità sviluppatore (modalità di debug)](../developer_mode.html#developer-mode) in Impostazioni ‣ Funzioni tecniche ‣ Parametri ‣ Parametri di sistema.

Importante

La configurazione del server e-mail transazionale può funzionare insieme con un server e-mail di massa in uscita. Il Filtro mittente per il server e-mail di massa può essere vuoto ma è necessario per essere aggiunto nelle impostazioni dell’applicazione _Email Marketing_.

Vedi anche

Per maggiori informazioni sulla configurazione del server per le e-mail di massa consulta la sezione [Inviare e-mail con un server SMTP esterno](email_servers_outbound.html#email-outbound-custom-domain-smtp-server).

Example

Configurazione server e-mail in uscita con più utenti:

  * Utente n.1 casella di posta
    
    * **Nome utente** n.1 (login) server e-mail in uscita = `john@esempio.com`

    * Filtro mittente n.1 ` server e-mail in uscita = `john@esempio.com

  * Utente n.2 casella di posta
    
    * **Nome utente** n.2 (login) server e-mail in uscita = `jane@esempio.com`

    * Filtro mittente n.2 ` server e-mail in uscita = `jane@esempio.com

  * Notifiche casella di posta
    
    * **Nome utente** (login) n.3 server e-mail in uscita = `notifiche@esempio.com`

    * Filtro mittente n.3 server e-mail in uscita = `notifiche@esempio.com`

  * Parametri di sistema
    
    * `mail.catchall.domain` nei parametri di sistema = `example.com`

    * `mail.default.from` nei parametri di sistema = `notifiche`




### Configurare server e-mail in entrata¶

L’account in entrata deve avere le stesse impostazioni dell’account in uscita. Apri la sezione Server e-mail in entrata nelle Funzioni tecniche e Crea una nuova configurazione. Spunta o seleziona il pulsante accanto a Autenticazione OAuth Outlook e inserisci il nome utente Microsoft Outlook. Fai clic su Collega account Outlook. Comparirà il messaggio: Token Outlook valido Ora Prova e conferma l’account. L’account sarà pronto per ricevere e-mail nel database Odoo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/general/email_communication/azure_oauth.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google_oauth.html "Collegare Gmail a Odoo utilizzando Google OAuth") |
  * [precedente](email_domain.html "Configurare record DNS per inviare e-mail in Odoo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth


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
  *[DKIM]: DomainKeys Identified Mail) da inserire nel provider :abbr:`DNS (Domain Name System
  *[DMARC]: Domain-based Message Authentication, Reporting, and Conformance
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