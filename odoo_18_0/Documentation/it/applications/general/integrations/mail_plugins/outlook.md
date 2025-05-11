# Plug-in Outlook — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gmail.html "Plug-in Gmail") |
  * [precedente](../mail_plugins.html "Plug-in e-mail") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Integrazioni](../../integrations.html) »
  * [Plug-in e-mail](../mail_plugins.html) »
  * Plug-in Outlook



# Plug-in Outlook¶

Outlook permette alle applicazioni di terze parti di collegarsi per eseguire le azioni di un database dalle e-mail. Odoo dispone di un plug-in per Outlook che consente di creare un’opportunità dal pannello e-mail.

## Configurazione¶

Il [plug-in e-mail](../mail_plugins.html) Outlook deve essere configurato sia su Odoo che su Outlook.

### Abilitare il plug-in e-mail¶

Innanzitutto, attiva la funzionalità _plug-in e-mail_ nel database. Vai su Impostazioni ‣ Impostazioni generali ‣ Integrazioni, attiva Plug-in e-mail e Salva le impostazioni.

### Installare il plug-in Outlook¶

Scarica (Salva pagina come ‣ solo pagina web XML) il seguente file XML da caricare più tardi: <https://download.odoocdn.com/plugins/outlook/manifest.xml>.

In seguito, apri la casella di posta Outlook e seleziona un’e-mail. Dopo averlo fatto, fai clic sul pulsante Più azioni nella parte in alto a destra e seleziona Ottieni componenti aggiuntivi.

Suggerimento

Per le versioni di Microsoft Outlook installate localmente, accedi alla sezione del menu Ottieni componenti aggiuntivi mentre sei in modalità di anteprima (**non** con un messaggio aperto). Fai clic sull’icona … (ellisse) nella parte in alto a destra del messaggio visualizzato in anteprima, poi scorri in basso e fai clic su Ottieni componenti aggiuntivi.

Segui la procedura e seleziona la scheda I miei componenti aggiuntivi a sinistra.

Sotto Componenti aggiuntivi personalizzati verso il basso, fai clic su \+ Aggiungi add-in personalizzato e poi fai clic su Aggiungi da file…

Il prossimo passo consiste nell’allegare il file `manifest.xml` scaricato e poi fare clic su OK. In seguito, leggi l’avviso e fai clic su Installa.

### Collegare il database¶

Outlook verrà connesso al database Odoo. Per prima cosa, apri qualsiasi e-mail nella casella Outlook, fai clic sul pulsante Più azioni nella parte in alto a destra e seleziona Odoo per Outlook.

Il pannello a destra ora mostra anche le **Informazioni azienda**. Nella parte in basso, fai clic su Login.

Nota

Su un database di prova, è possibile inviare solo un numero limitato di richieste relative a **Informazioni aziendali** (_Lead enrichment_). Questa funzionalità richiede [crediti prepagati](../mail_plugins.html#mail-plugins-pricing).

Suggerimento

Se dopo un po” il pannello è ancora vuoto, è possibile che le impostazioni dei cookie del browser ne impediscano il caricamento. Nota che queste impostazioni cambiano anche se il browser è in modalità _incognito_.

Per sistemare il problema, configura il browser per consentire sempre i cookie sulla pagina del plugin di Odoo.

Per Google Chrome, modifica le impostazioni dei cookie del browser seguendo la guida: [https://support.google.com/chrome/answer/95647?hl=it&sjid=2322092630079085228-EU](https://support.google.com/chrome/answer/95647) e aggiungi `download.odoo.com` all’elenco di siti che possono utilizzare sempre i cookie.

Una volta completato il processo, è necessario aprire di nuovo il pannello Outlook.

Ora, inserisci l’URL del database Odoo e fai clic su Login.

In seguito, fai clic su Consenti per aprire la finestra pop-up.

Se l’utente non ha effettuato l’accesso sul database, inserisci le credenziali. Fai clic su Consenti per permettere al plug-in Outlook di collegarsi al database.

### Aggiungere una scorciatoia al plug-in¶

Per impostazione predefinita, il plug-in di Outlook può essere aperto dal menu _Più azioni_. Tuttavia, per risparmiare tempo, è possibile aggiungerlo accanto alle altre azioni predefinite.

Nella casella di posta di Outlook, fai clic su Impostazioni, poi su Mostra tutte le impostazioni Outlook.

Ora, seleziona Azioni personalizzate sotto E-mail, fai clic su Odoo per Outlook e poi su Salva.

Seguendo questo step, apri un’e-mail qualsiasi per visualizzare la scorciatoia.

### Utilizzare il plug-in¶

Ora che il plug-in è installato e funzionante, per creare un lead è sufficiente fare clic sulla `O` [icona di Odoo] o andare su Più azioni e fare clic su Odoo per Outlook. Il pannello laterale apparirà sul lato destro e sotto Opportunità fai clic su Nuovo. Si aprirà una nuova finestra con l’opportunità creata nel database di Odoo.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/integrations/mail_plugins/outlook.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gmail.html "Plug-in Gmail") |
  * [precedente](../mail_plugins.html "Plug-in e-mail") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Integrazioni](../../integrations.html) »
  * [Plug-in e-mail](../mail_plugins.html) »
  * Plug-in Outlook


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