# Build — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](status.html "Stato") |
  * [precedente](branches.html "Filiali") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Build



# Build¶

## Panoramica¶

In Odoo.sh, un build corrisponde ad un database gestito da un server Odoo ([odoo/odoo](https://github.com/odoo/odoo) e [odoo/enterprise](https://github.com/odoo/enterprise)), in esecuzione su una revisione specifica dell’archivio di progetto e in un ambiente in contenitori. Il suo scopo è di provare il comportamento del server, del database e delle funzionalità attraverso la revisione.

In questa vista, ogni riga rappresenta un ramo, e la cella di una riga rappresenta un build del ramo stesso.

La maggior parte delle volte, i build vengono creati seguendo i push Github relativi ai rami del tuo archivio. È possibile crearli anche quando esegui altre operazioni, come importare un database su Odoo.sh o chiedere il rebuild di un ramo nel tuo progetto.

Se durante il processo di creazione non vengono visualizzati errori o messaggi di avviso, significa che il build è stato creato con successo e sarà evidenziato in verde.

Se durante il processo di creazione vengono visualizzati errori o messaggi di avviso, significa che il build non è stato creato con successo e sarà evidenziato in rosso.

Se durante la creazione vengono visualizzati messaggi di avviso ma non ci sono errori, il build viene considerato quasi riuscito. Sarà evidenziato in giallo per indicare allo sviluppatore che sono stati visualizzati degli avvisi.

I build non sempre creano un database da capo. Ad esempio, quando esegui il push di un cambiamento nel ramo di produzione, il build creato avvia il server con la nuova revisione e prova a caricare il database di produzione corrente. Se non vengono visualizzati errori, il build viene considerato riuscito.

## Fasi¶

### Produzione¶

Il primo build di un ramo di produzione crea un database da capo. Se il build ha esito positivo, il database viene considerato come database di produzione del tuo progetto.

Da questo momento, i push sul ramo di produzione porteranno alla creazione di nuovi build che provano a caricare il database usando un server in esecuzione con la nuova revisione.

Se il build è riuscito o presenta avvisi ma non errori, il database di produzione funzionerà con questo build insieme con la revisione associata al build stesso.

Se il build non riesce a caricare o aggiornare il database, verrà riutilizzato il build precedente per caricare il database e quindi il database funzionerà utilizzando un server che utilizza la revisione di successo precedente .

Il build utilizzato per far funzionare il database di produzione è sempre il primo dell’elenco dei build. Se un build fallisce, viene messo dopo il build che sta eseguendo il database di produzione.

### Staging¶

I build di staging duplicano il database di produzione e provano a caricare il duplicato con le revisioni dei rami di staging.

Ogni volta che esegui il push di una nuova revisione su un ramo di staging, il build creato utilizza una nuova copia del database di produzione. I database non vengono riutilizzati tra i build dello stesso ramo e ciò garantisce:

  * che i build di staging usino database simili alla produzione così non eseguirai test con dati vecchi;

  * che tu possa giocare quanto vuoi nello stesso database di staging per poi chiedere il rebuild quando vuoi ricominciare con una nuova copia della produzione.




Tuttavia, questo significa che se apporti modifiche ai database di staging e non le applichi alla produzione, esse non verranno trasferite al prossimo build dello stesso ramo di staging.

### Sviluppo¶

I build di sviluppo portano alla creazione di nuovi database, al caricamento di dati demo e all’esecuzione di unit test.

Il build verrà considerato non riuscito ed evidenziato in rosso se durante l’installazione i test falliscono, in quanto hanno lo scopo di generare errori se si verifica qualcosa di sbagliato.

Se tutti i test riescono con successo e non vi sono errori, il build verrà considerato riuscito.

Secondo l’elenco di moduli da installare e provare, il build di sviluppo può impiegare fino ad 1 ora per essere pronto. Ciò è dovuto al grande numero di test configurati nella suite di moduli Odoo.

## Funzionalità¶

Il ramo di produzione apparirà sempre per primo e gli altri rami verranno ordinati secondo l’ultimo build creato. Inoltre, è possibile filtrare i rami.

Per ogni ramo, è possibile accedere all’ultimo database del build utilizzando il link _Connect_ e passare al codice del ramo utilizzando il link _Github_. Per altri rami diversi dalla produzione, puoi creare un nuovo build che utilizzerà l’ultima revisione del ramo utilizzando il link _rebuild_. L’ultimo link non è disponibile se un build è già in corso per il ramo.

Per ogni build, è possibile accedere alle modifiche della revisione utilizzando il pulsante con l’icona Github. È possibile accedere al database del build come amministratore utilizzando il pulsante _Connect_. Inoltre, puoi accedere al database con un altro utente utilizzando il pulsante _Connect as_ nel menu a discesa del pulsante _Connect_.

Nel menu a discesa del build, puoi accedere alle stesse funzionalità della [vista rami](branches.html#odoosh-gettingstarted-branches-tabs): _Registri_ , _Shell web_ , _Editor_ , _E-mail in uscita_. Hai anche la possibilità di _Scaricare un dump_ del database del build.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/odoo_sh/getting_started/builds.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](status.html "Stato") |
  * [precedente](branches.html "Filiali") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Build


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