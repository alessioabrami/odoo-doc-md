# Account odoo.com — Odoo 18.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](../developer.html "Developer") |
  * [precedente](mobile.html "App Odoo per dispositivi mobili") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Account odoo.com



# Account odoo.com¶

Questo documento descrive come modificare e gestire un account Odoo.com, compresa l’aggiunta di un database client, l’eliminazione di un account, la reimpostazione della password e l’abilitazione dell’autenticazione a due fattori.

## Garantire l’accesso degli utenti al database¶

Un database può essere collegato a un account Odoo.com creato in precedenza da un altro account Odoo.com. Questo permette al database di apparire nella pagina _I miei database_. Per farlo, l’account Odoo.com del cliente deve essere aggiunto al database come utente.

Per prima cosa, accedi all’account Odoo.com con il quale è stato creato il database client. Nella dashboard principale del database, accedi all’applicazione **Impostazioni** e fare clic su Gestisci utenti nella sezione Utenti. Fai clic sul pulsante Nuovo e inserisci un nome nel campo Nome per questo utente. Successivamente, inserisci l’indirizzo e-mail utilizzato per registrare l’account Odoo.com desiderato nel campo E-mail. Torna alle Impostazioni usando il percorso e apparirà la finestra pop-up Inviti utenti, sapendo che l’aggiunta di altri utenti aumenterà l’importo dell’abbonamento.

Fai clic su Conferma per fare apparire l’elenco di Utenti. Un invito viene automaticamente inviato all’indirizzo e-mail. Una volta confermato, il database del cliente appare nella pagina **I miei database** dell’account Odoo.com di destinazione.

Suggerimento

Per fornire accesso completo al database per questo utente, imposta il campo Dashboard sotto la sezione Produttività su Amministratore. In seguito, imposta il campo Amministrazione sotto la sezione Amministrazione su Impostazioni.

## Eliminare un account Odoo.com¶

Per eliminare un account Odoo.com, inizia facendo clic sull’icona del profilo nell’angolo in alto a destra (rappresentato dal nome utente e dall’icona) per svelare un menu a discesa. Dal menu a discesa, seleziona Il mio account Odoo.com per aprire il portale utente.

Dal portale utente, puoi accedere all’opzione eliminata andando su Il mio account ‣ Modifica impostazioni di sicurezza ‣ Elimina account. È possibile accedervi anche andando su <https://www.odoo.com/my/home>.

Pericolo

L’eliminazione di un account Odoo.com è irreversibile. Fai attenzione quando esegui l’azione perché l’account Odoo.com **non** è recuperabile una volta eliminato.

Dopo aver cliccato sul pulsante Elimina account apparirà una finestra con la richiesta di conferma per l’eliminazione dell’account.

Per confermare l’eliminazione, inserisci la Password e il Login dell’account che stai eliminando. In seguito, fai clic sul pulsante Elimina account per confermare l’eliminazione.

## Modificare la password dell’account Odoo.com¶

Per modificare la password di un account Odoo.com, è necessario accedere all’account utente Odoo.com dalla pagina di accesso. Dopo aver eseguito l’accesso, vai nell’angolo in alto a destra dello schermo e fai clic sull’icona ▼ (freccia giù) accanto all’icona del profilo. In seguito, seleziona Il mio account e apparirà la dashboard del portale.

Per modificare la password Odoo.com, fai clic sul link Modifica impostazioni sicurezza, nella sezione Sicurezza account. Successivamente, apporta le modifiche necessarie digitando la Password attuale, la Nuova password e verificala. Come ultima cosa, fai clic su Modifica password per completare la modifica.

Nota

Se un cliente desidera modificare l’accesso, contatta il supporto Odoo [qui](https://www.odoo.com/help).

Nota

Le password per gli utenti Odoo.com e del portale restano separate anche se viene utilizzato lo stesso indirizzo e-mail.

## Aggiungere l’autenticazione a due fattori¶

Per aggiungere l’autenticazione a due fattori, è necessario accedere all’account utente Odoo.com dalla pagina di accesso. Dopo aver eseguito l’accesso, vai nell’angolo in alto a destra dello schermo e fai clic sull’icona ▼ (freccia giù) accanto all”icona del profilo. In seguito, seleziona Il mio account e apparirà la dashboard del portale.

Se l’utente vuole attivare l’autenticazione a due fattori (2FA) per l’accesso a Odoo.com, fai clic sul link Modifica impostazioni sicurezza sotto la sezione Sicurezza account.

Fai clic su Abilita autenticazione a due fattori per abilitare la 2FA. In seguito, conferma la password attuale nel campo Password. Successivamente, fai clic su Conferma password e attiva la 2FA in un’app 2FA (Google Authenticator, Authy, etc.), scansionando il codice QR o inserendo un Codice di verifica.

Infine, fai clic su Abilita autenticazione due fattori per completare la configurazione.

Nota

Nella sezione Il mio account gli utenti di Odoo.com possono anche accedere a:

  * Dashboard partner

  * I miei servizi in app

  * Dashboard app.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/odoo_accounts.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](../developer.html "Developer") |
  * [precedente](mobile.html "App Odoo per dispositivi mobili") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Account odoo.com


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions