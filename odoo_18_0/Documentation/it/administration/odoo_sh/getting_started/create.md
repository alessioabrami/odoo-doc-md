# Creare un progetto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](branches.html "Filiali") |
  * [precedente](../getting_started.html "Esordiente") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Creare un progetto



# Creare un progetto¶

## Distribuire la piattaforma¶

Vai su [Odoo.sh](https://www.odoo.sh/) e fai clic sul pulsante _Distribuisci piattaforma_.

## Accedere con Github¶

Accedi con il tuo account Github. Se non disponi di un account, fai clic sul link _Crea un account_.

## Autorizzare Odoo.sh¶

Concedi a Odoo.sh di accedere al tuo account come richiesto facendo clic sul pulsante _Autorizza_.

In pratica, Odoo.sh ha bisogno di:

  * conoscere le credenziali e l’e-mail Github;

  * creare un nuovo archivio in caso tu decida di iniziare da capo;

  * leggere gli archivi esistenti inclusi quelli delle tue organizzazioni in caso voglia iniziare da un archivio esistente;

  * creare un webhook per ricevere una notifica ogni volta che vengono apportate modifiche;

  * eseguire modifiche per rendere la distribuzione più semplice unendo rami o aggiungendo nuovi [moduli secondari](https://git-scm.com/book/en/v2/Git-Tools-Submodules) ad esempio.




## Inviare il progetto¶

Scegli se vuoi iniziare da capo creando un nuovo archivio o se vuoi utilizzarne uno esistente.

In seguito, scegli un nome o seleziona l’archivio che vuoi utilizzare.

Scegli la versione di Odoo che desideri utilizzare. Se pianifichi di importare un database o un insieme di applicazioni esistente potresti aver bisogno di scegliere la versione corrispondente. Se inizi da capo, usa l’ultima versione.

Inserisci il tuo _codice abbonamento_ chiamato anche _abbonamento di riferimento_ , _numero di contratto_ o _codice di attivazione_.

Si tratta del codice dell’abbonamento Enterprise che include Odoo.sh.

I partner possono utilizzare i codici partnership per iniziare una prova. Se i clienti dovessero avviare un progetto, dovrebbero ottenere un abbonamento Enterprise che include Odoo.sh e utilizzarne il codice abbonamento. Il partner otterrà il 50% dell’importo come commissione. Contatta l’addetto vendite o l’account manager per saperne di più.

Al momento dell’invio del modulo, se ricevi una notifica che segnala la non validità dell’abbonamento, significa che:

  * non è un abbonamento esistente;

  * non è un abbonamento partnership;

  * è un abbonamento Enterprise ma non include Odoo.sh;

  * non è né un abbonamento partnership né un abbonamento Enterprise (ad es. abbonamento online).




In caso di dubbi sul tuo abbonamento, contatta il [supporto Odoo](https://www.odoo.com/help).

## Hai finito!¶

Puoi iniziare ad utilizzare Odoo.sh. Il tuo primo backup sta per essere creato. A breve, potrai collegarti al tuo primo database.

## Importare un database¶

È possibile importare il database nel progetto Odoo.sh se sviluppato in una [versione supportata](../../supported_versions.html) di Odoo.

### Spingere i moduli in produzione¶

Se utilizzi moduli community o personalizzati, aggiungili ad un ramo del tuo archivio Github. I database ospitati sulla piattaforma online Odoo.com non presentano moduli personalizzati. Gli utenti di tali database possono saltare questa fase.

I moduli possono avere la struttura che preferisci, Odoo.sh individuerà automaticamente le cartelle che contengono componenti aggiuntivi Odoo. Ad esempio, puoi inserire tutte le cartelle dei moduli nella directory radice del tuo archivio o raggruppare i moduli in cartelle per categorie da te definite (contabilità, progetti…).

Per i moduli community disponibili negli archivi Git pubblici, è possibile considerare di aggiungerli utilizzando [Moduli secondari](../advanced/submodules.html#odoosh-advanced-submodules).

In seguito, puoi sia [rendere questo ramo un ramo di produzione](branches.html#odoosh-gettingstarted-branches-stages) o [unirlo al tuo ramo di produzione](branches.html#odoosh-gettingstarted-branches-mergingbranches).

### Scaricare un backup¶

#### Database on-premise¶

Accedi all’URL del tuo database on-premise `/web/database/manager` e scarica un backup.

Avvertimento

Se non puoi accedere al gestore dei database, potrebbe essere stato disabilitato dal tuo amministratore di sistema. Consula la [documentazione relativa alla sicurezza del gestore di database](../../on_premise/deploy.html#db-manager-security).

Avrai bisogno della password principale del server del database. Se non la conoscim contatta l’amministratore del sistema.

Scegli come formato di backup uno zip che includa il filestore.

#### Database Odoo online¶

[Accedi al gestore dei database](https://accounts.odoo.com/my/databases/manage) e scarica un backup del tuo database.

Avvertimento

Le versioni online (ad es. _saas-*_) non sono supportate su Odoo.sh.

### Caricare il backup¶

In seguito, nel progetto Odoo.sh, fai clic sulla scheda backup del ramo di produzione e importa il backup appena scaricato.

Una volta che il backup è stato importato, è possibile accedere utilizzando il pulsante _Collegati_ nello storico del ramo.

### Verificare i server per le e-mail in uscita¶

Di seguito, trovi un server e-mail predefinito fornito con Odoo.sh. Per utilizzarlo, non dovrebbe esserci nessun server e-mail in uscita abilitato e configurato per il database in Impostazioni ‣ Funzioni tecniche ‣ Server e-mail in uscita ([Modalità sviluppatore](../../../applications/general/developer_mode.html#developer-mode) deve essere attivata).

Dopo aver importato il database, tutti i server e-mail in uscita vengono disabilitati così da poter utilizzare il server e-mail Odoo.sh fornito di base.

Avvertimento

Port 25 è (e rimarrà) chiuso. Se vuoi collegarti ad un server SMTP esterno, dovresti utilizzare i port 465 e 587.

### Verificare le azioni programmate¶

Tutte le azioni programmate vengono disabilitate dopo l’importazione.

Questo serve ad evitare che sul database appena importato vengano eseguite azioni che potrebbero impattare la produzione in corso, come inviare e-mail in coda, elaborare e-mail di massa o sincronizzare servizi di terze parti (calendari, hosting di file…).

Se pianifichi di rendere il database importato il tuo database di produzione, abilita le azioni programmate di cui hai bisogno. Puoi verificare cosa è già abilitato nel database di origine e attivare le stesse azioni nel database importato. Le azioni programmate si trovano in Impostazioni ‣ Funzioni tecniche ‣ Automazione ‣ Azioni programmate.

### Registra il tuo abbonamento¶

L’abbonamento viene scollegato dopo l’importazione.

Il database importato viene considerato un duplicato per impostazione predefinita e quindi l’abbonamento enterprise viene eliminato in quanto è possibile collegare solo un database ad un abbonamento.

Se pianifichi di renderlo il tuo database di produzione, scollega il vecchio database dall’abbonamento e registra il nuovo database importato. Leggi la [documentazione relativa alla registrazione dei database](../../on_premise.html) per avere istruzioni.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/odoo_sh/getting_started/create.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](branches.html "Filiali") |
  * [precedente](../getting_started.html "Esordiente") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Creare un progetto


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
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