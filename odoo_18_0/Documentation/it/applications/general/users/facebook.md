# Autenticazione accesso Facebook — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Autenticazione accesso Google") |
  * [precedente](portal.html "Accedere al portale") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Facebook



# Autenticazione accesso Facebook¶

La funzione di accesso OAuth di _Facebook_ consente agli utenti di Odoo di accedere al proprio database con il proprio account Facebook.

Pericolo

I database ospitati su odoo.com **non** dovrebbero utilizzare il login OAuth per il proprietario o l’amministratore del database, in quanto questo scollegherebbe il database dal loro account odoo.com. Se l’OAuth è impostato per quell’utente, il database non potrà più essere duplicato, rinominato o gestito in altro modo dal portale odoo.com.

## Configurare Meta for Developers¶

Vai su [Meta for Developers](https://developers.facebook.com/) e accedi. Fai clic su Le mie app. Nella pagina Applicazioni, fai clic su Crea app.

Sulla pagina Casi d’uso, seleziona Autenticati e richiedi dati dagli utenti con Facebook login e poi fai clic su Avanti.

Nel campo Aggiungi un nome per l’app, inserisci `Odoo Login OAuth` o un titolo simile.

Nota

L’app e-mail contatto è automaticamente impostato sull’indirizzo e-mail associato all’account Meta. Se questo indirizzo di posta elettronica non viene monitorato regolarmente, può essere opportuno utilizzare un altro indirizzo di posta elettronica.

Fai clic su Avanti. Rivedi i Requisiti di pubblicazione, i Termini della piattaforma Meta e le Politiche degli sviluppatori. In seguito, fai clic su Crea app.

Importante

Facendo clic su Crea app ti potrebbe essere richiesta la password.

### Personalizzare l’app¶

Dopo aver creato la nuova app, apparirà la pagina Dashboard con un elenco di step da completare prima di poter pubblicare l’app. Da qui, fai clic su Personalizza aggiungendo un pulsante di accesso a Facebook.

Sulla pagina Personalizza, fai clic su Impostazioni.

Nel campo URL reindirizzamento OAuth valido, inserisci `https://<odoo base url>/auth_oauth/signin` e sostituisci `<odoo base url>` con l’URL del database applicabile.

Example

Se il database ha l’URL `https://example.odoo.com`, l’URL `https://example.odoo.com/auth_oauth/signin` deve essere inserito nel campo URL reindirizzamento OAuth valido.

Fai clic su Salva modifiche quando hai terminato.

### Configurare le impostazioni¶

All’estremità sinistra della pagina, fai clic su Impostazioni app ‣ Base. La pagina contiene impostazioni aggiuntive richieste prima che l’app possa essere inviata per l’approvazione.

Nel campo URL politica privacy, inserisci `https://www.odoo.com/privacy`.

Nota

<https://www.odoo.com/privacy> è la politica privacy predefinita per i database ospitati su odoo.com.

Fai clic sul campo Icona app per aprire una finestra per caricare un file. Da qui, seleziona e carica un’icona per l’app.

Nel campo Eliminazione dati utente, inserisci `https://www.odoo.com/Documentation/17.0/administration/odoo_accounts.html`.

Nota

La documentazione fornisce istruzioni su come eliminare il proprio account Odoo.

Infine, fai clic sul campo Categoria e seleziona Business e pagine dal menu a tendina.

Fai clic su Salva modifiche.

### Acquisire ID app¶

Dopo aver creato e approvato l’app, seleziona e copia l’ID app. Incolla l’informazione negli appunti o in un file, in quanto sarà necessaria nell’ultimo step per completare la configurazione.

### Pubblica¶

Nella parte sinistra della pagina, fai clic su Pubblica. In base allo staso dell’account Facebook collegato, potrebbero essere richiesti step aggiuntivi per la verifica e il test, entrambi elencati in questa pagina.

Dopo aver revisionato l’informazione, fai clic su Pubblica.

Vedi anche

Informazioni aggiuntive sullo sviluppo di app Meta, compresi ulteriori dettagli su creazione, test e casi d’uso, sono consultabili [alla pagina](https://developers.facebook.com/docs/development).

## Configurare Odoo¶

Per prima cosa, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode-activation).

Accedi all’app Impostazioni e scorri in basso verso la sezione Integrazione. Qui, spunta la casella denominata, Autenticazione OAuth. Fai clic su Salva.

In seguito, accedi al database una volta che appare la schermata di accesso.

Dopo aver eseguito l’accesso con successo, accedi all’app Impostazioni ‣ Utenti e aziende ‣ Fornitori OAuth. Fai clic su Facebook Graph.

Nel campo ID client, inserisci l’ID app dalla sezione precedente e poi spunta la casella Consentito.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/users/facebook.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Autenticazione accesso Google") |
  * [precedente](portal.html "Accedere al portale") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Facebook


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