# Plug-in Gmail — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../unsplash.html "Unsplash") |
  * [precedente](outlook.html "Plug-in Outlook") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Integrazioni](../../integrations.html) »
  * [Plug-in e-mail](../mail_plugins.html) »
  * Plug-in Gmail



# Plug-in Gmail¶

Il _plug-in Gmail_ integra un database Odoo con una casella di posta Gmail così gli utenti possono tenere traccia del lavoro tra Gmail e Odoo senza perdere informazioni.

## Utenti Odoo online¶

Segui i passaggi descritti di seguito per configurare il plug-in Gmail su database con host su Odoo online (od Odoo.sh).

### Installare il plug-in Gmail¶

Per prima cosa, accedi all’account Gmail che l’utente vuole collegare a Odoo.

Dalla casella di posta Gmail, fai clic sull’icona a forma di più nel pannello a destra per accedere ai componenti aggiuntivi. Se il pannello laterale non è visibile, fai clic sull’icona a forma di freccia nell’angolo in basso a destra della casella di posta per mostrarlo.

In seguito, usa la barra di ricerca per cercare `Odoo` e individua Odoo Inbox Addin.

In alternativa, accedi direttamente alla pagina Odoo Inbox Addin nel [marketplace di Google Workspace](https://workspace.google.com/marketplace/app/odoo_inbox_addin/873497133275).

Una volta individuato il plug-in, fai clic su Installa. In seguito, fai clic su Continua per avviare l’installazione.

Successivamente, seleziona l’account Gmail che l’utente vuole collegare a Odoo. In seguito, fai clic su Consenti per permettere a Odoo di accedere all’account Google. Google mostrerà una finestra a comparsa che conferma l’installazione.

### Configurare il database Odoo¶

La funzionalità plug-in e-mail deve essere attivata nel database Odoo per utilizzare il plug-in Gmail. Per attivare la funzionalità, vai su Impostazioni ‣ Impostazioni generali. Nella sezione Integrazioni, attiva plug-in e-mail e poi fai clic su Salva.

### Configurare la casella di posta Gmail¶

Nella casella di posta Gmail, nel pannello laterale destro è ora visibile l’icona viola di Odoo. Fai clic sull’icona di Odoo per aprire la finestra del plug-in. Poi fai clic su una qualsiasi e-mail nella casella di posta. Fai clic su Autorizza accesso nella finestra del plug-in per concedere a Odoo l’accesso alla casella di posta Gmail.

Successivamente, fai clic su Login. In seguito, inserisci l’URL del database Odoo che l’utente vuole collegare alla casella di posta Gmail e accedi al database.

Nota

Usa l’URL generale del database, non l’URL di una pagina specifica del database. Ad esempio, utilizza `https://mycompany.odoo.com`, non `https://mycompany.odoo.com/web#cids=1&action=menu`.

Infine, fai clic su Consenti per permettere a Gmail di accedere al database Odoo. In seguito, il browser mostrerà un messaggio di successo. Chiudi la finestra. Ora la casella di posta Gmail e il database Odoo sono connessi.

## Utenti Odoo on-premise¶

Segui i passaggi elencati per configurare il plug-in Gmail su database con host su server diversi da Odoo online (o Odoo.sh).

Nota

Come parte delle linee guida relative alla sicurezza, Google richiede ai creatori di componenti aggiuntivi di fornire un elenco di URL che possono essere utilizzati per azioni e reindirizzamenti lanciati da un componente aggiuntivo. Questo protegge gli utenti garantendo, ad esempio, che nessun componente aggiuntivo reindirizzi gli utenti verso un sito maligno. (Leggi di più su [Google Apps Script](https://developers.google.com/apps-script/manifest/allowlist-url?hl=it).)

Dato che Odoo può solo elencare il dominio `odoo.com` e non il dominio unico del server di ogni cliente on-premise, i clienti on-premise non possono installare il plug-in Gmail dal marketplace del Google Workspace.

### Installare il plug-in Gmail¶

Per prima cosa, accedi alla [GitHub repository](https://github.com/odoo/mail-client-extensions) per i plug-in e-mail Odoo. In seguito, fai clic sul pulsante verde Codice. Successivamente, fai clic su Scarica ZIP per scaricare i file plug-in e-mail sul computer dell’utente.

Apri il file ZIP sul computer. In seguito, vai su mail-client-extensions-master ‣ gmail ‣ src ‣ views e apri il file `login.ts` utilizzando qualsiasi editor di testi, come Notepad (Windows), TextEdit (Mac) o Visual Studio Code.

Elimina le seguenti tre righe di testo dal file `login.ts`:
    
    
    if (!/^https:\/\/([^\/?]*\.)?odoo\.com(\/|$)/.test(validatedUrl)) {
         return notify("The URL must be a subdomain of odoo.com");
    }
    

Questo comporterà la rimozione del vincolo del dominio `odoo.com` dal programma plug-in Gmail.

Nel file ZIP, vai su mail-client-extensions-master ‣ gmail e apri il file chiamato appsscript.json. Nella sezione urlFetchWhitelist, sostituisci tutti i riferimenti a `odoo.com` con il dominio unico del server del cliente Odoo.

In seguito, nella stessa cartella gmail, apri il file chiamato README.md. Segui le istruzioni nel file README.md per lanciare i file del plug-in Gmail come progetto Google.

Nota

Sul computer è necessario poter eseguire i comandi Linux per seguire le istruzioni descritte nel file README.md.

Dopo aver completato quest’operazione, condividi il progetto Google con l’account Gmail che l’utente vuole collegare a Odoo. In seguito, fai clic su Pubblica e Installa dal manifesto. Infine, fai clic su Installa componente aggiuntivo per installare il plug-in Gmail.

### Configurare il database Odoo¶

La funzionalità plug-in e-mail deve essere attivata nel database Odoo per utilizzare il plug-in Gmail. Per attivare la funzionalità, vai su Impostazioni ‣ Impostazioni generali. Nella sezione Integrazioni, attiva plug-in e-mail e poi fai clic su Salva.

### Configurare la casella di posta Gmail¶

Nella casella di posta Gmail, nel pannello laterale destro è ora visibile l’icona viola di Odoo. Fai clic sull’icona di Odoo per aprire la finestra del plug-in. Poi fai clic su una qualsiasi e-mail nella casella di posta. Fai clic su Autorizza accesso nella finestra del plug-in per concedere a Odoo l’accesso alla casella di posta Gmail.

Successivamente, fai clic su Login. In seguito, inserisci l’URL del database Odoo che l’utente vuole collegare alla casella di posta Gmail e accedi al database.

Nota

Usa l’URL generale del database, non l’URL di una pagina specifica del database. Ad esempio, utilizza `https://mycompany.odoo.com`, non `https://mycompany.odoo.com/web#cids=1&action=menu`.

Infine, fai clic su Consenti per permettere a Gmail di accedere al database Odoo. In seguito, il browser mostrerà un messaggio di successo. Chiudi la finestra. Ora la casella di posta Gmail e il database Odoo sono connessi.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/integrations/mail_plugins/gmail.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../unsplash.html "Unsplash") |
  * [precedente](outlook.html "Plug-in Outlook") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Integrazioni](../../integrations.html) »
  * [Plug-in e-mail](../mail_plugins.html) »
  * Plug-in Gmail


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