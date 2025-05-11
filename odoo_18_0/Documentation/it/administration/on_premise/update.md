# Aggiornamenti per correzione bug — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deploy.html "Configurazione sistema") |
  * [precedente](source.html "Installare dalla sorgente") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Aggiornamenti per correzione bug



# Aggiornamenti per correzione bug¶

## Introduzione¶

Per beneficiare di aggiornamenti, miglioramenti relativi alla sicurezza, correzioni di bug e incrementi delle prestazioni è necessario aggiornare Odoo ogni tanto.

La presente guida è valida per l’utilizzo di Odoo sulla propria infrastruttura di hosting. Se stai utilizzando una delle soluzioni cloud di Odoo, gli aggiornamenti vengono eseguiti in automatico per te.

La terminologia relativa agli aggiornamenti software spesso confonde. Di seguito troverai alcune definizioni generali:

Aggiornare (un’installazione Odoo)
    

Si riferisce al processo di ottenere la versione più recente del codice sorgente per la tua versione attuale di Odoo. Ad esempio, aggiornare Odoo Enterprise 13.0 all’ultima versione. L’aggiornamento non apporterà modifiche al contenuto del tuo database Odoo ed è possibile tornare indietro installando di nuovo la versione precedente del codice sorgente.

Aggiornare (un database Odoo)
    

Si riferisce ad una complessa operazione di elaborazione dati in cui la struttura e i contenuti del database vengono modificati in maniera permanente per renderlo compatibile con una nuova versione di Odoo. L’operazione è irreversibile e generalmente realizzata tramite il [servizio di aggiornamento database](https://upgrade.odoo.com/) di Odoo quando decidi di passare ad una nuova versione. Storicamente, il processo è noto anche con il nome di «migrazione» perché implica lo spostamento di dati nel database, anche se il database potrebbe trovarsi nella stessa posizione fisica dopo l’aggiornamento.

La presente pagina descrive i passaggi necessari per _aggiornare_ un’installazione Odoo all’ultima versione. Se vuoi avere più informazioni sull’aggiornamento di un database, consulta la [pagina per l’aggiornamento di Odoo](https://upgrade.odoo.com/).

## In breve¶

L’aggiornamento di Odoo viene realizzato installando la versione più recente del software rispetto alla versione attualmente in uso. I tuoi dati verranno conservati e non saranno modificati, a condizione che non venga disinstallato PostgreSQL (il motore del database che viene installato con Odoo).

Per eseguire l’aggiornamento, puoi consultare la nostra [guida di installazione](../on_premise.html) che spiega i metodi più comuni.

È opportuno far eseguire l’aggiornamento alla persona che ha implementato Odoo inizialmente, in quanto la procedura è molto simile.

Nota

Consigliamo sempre di scaricare una nuova versione di Odoo completa e aggiornata rispetto all’applicare manualmente patch, come le patch di sicurezza fornite con i relativi avvisi. Le patch vengono fornite principalmente per installazioni altamente personalizzate oppure per il personale tecnico che preferisce applicare temporaneamente piccole modifiche durante la fase di test di un aggiornamento completo.

## Fase 1: Scarica una versione di Odoo aggiornata¶

La pagina principale per il download è <https://www.odoo.com/page/download>. Se visualizzi il link «Compra» per scaricare Odoo Enterprise, assicurati di aver effettuato l’accesso su Odoo.com con le stesse credenziali del tuo abbonamento Odoo Enterprise.

In alternativa, puoi utilizzare il link unico per il download che si trova nell’e-mail di conferma d’acquisto di Odoo Enterprise.

Nota

Se hai eseguito l’installazione via Github, non è necessario scaricare una versione aggiornata (leggi in basso)

## Fase 2: Effettuare il back-up del database¶

La procedura di aggiornamento è abbastanza sicura e non dovrebbe modificare i tuoi dati. Tuttavia, è sempre meglio effettuare un back-up completo del database prima di applicare qualsiasi modifica sull’installazione e conservarlo in un posto sicuro, su un altro computer.

Se non hai disabilitato la pagina di gestione del database (scopri [qui](deploy.html#security) perché dovresti), puoi utilizzarla (link in fondo alla pagina) per scaricare un back-up del tuo o dei tuoi database. Se la disabiliti, utilizza la stessa procedura dei back-up che fai di solito.

## Fase 3: Installare la versione aggiornata¶

Scegli il metodo che corrisponde all’installazione attuale:

### Programmi di installazione¶

Se hai installato Odoo tramite un pacchetto di installazione scaricato dal nostro sito web (metodo consigliato), l’aggiornamento è molto semplice. Tutto ciò che devi fare è scaricare il pacchetto di installazione corrispondente al tuo sistema (vedi Fase 1) e installalo sul tuo server. Vengono aggiornati quotidianamente e includono le ultime modifiche alla sicurezza. Di solito, puoi semplicemente fare doppio clic sul pacchetto per installarlo. Dopo averlo fatto, assicurati di riavviare il servizio Odoo o il server e tutto dovrebbe essere installato.

### Installare dal codice sorgente (Tarball)¶

Se inizialmente hai installato Odoo con la versione «tarball» (archivio del codice sorgente), è necessario sostituire la cartella di installazione con una nuova versione. Per prima cosa, scarica l’ultimo tarball da Odoo.com. Sono aggiornati quotidianamente e includono le ultime modifiche di sicurezza (vedi Fase 1). Dopo aver scaricato il pacchetto, estrailo in una posizione temporanea sul tuo server.

Otterrai una cartella rinominata con la versione del codice sorgente, ad esempio «odoo-13.0+e.20190719» che contiene una cartella «odoo.egg-info» e la cartella dell’attuale codice sorgente chiamata «odoo» (per Odoo 10 e superiori) oppure «openerp» per versioni più vecchie. Puoi ignorare la cartella odoo.egg-info. Individua la cartella in cui è distribuita l’installazione corrente e sostituiscila con la nuova cartella «odoo» oppure «openerp» presente nell’archivio appena estratto.

Assicurati di rispettare la struttura della cartella. Ad esempio, la nuova cartella «addons» inclusa nel codice sorgente dovrebbe finire nello stesso percorso della versione precedente. In seguito, fai attenzione a qualsiasi file per configurazioni specifiche che potresti aer copiato o modificato manualmente nella vecchia cartella e copiali nella nuova. Infine, riavvia il servizio Odoo o il dispositivo e tutto dovrebbe essere pronto.

### Installare dal codice sorgente (Github)¶

Se in origine Odoo è stato installato con un clone Github completo delle repository ufficiali, la procedura di aggiornamento richiede l’estrazione del codice sorgente più recente tramite git. Entra nella directory di ciascuna repository (la repository principale di Odoo e la repository Enterprise) ed esegui i seguenti comandi:
    
    
    git fetch
    git rebase --autostash
    

L’ultimo comando potrebbe riscontrare conflitti del codice sorgente se hai modificato localmente il codice sorgente di Odoo. Il messaggio di errore ti restituirà l’elenco di file con conflitti e sarà necessario risolversi manualmente modificandoli e decidendo quale parte del codice mantenere.

In alternativa, se preferisci semplicemente ignorare le modifiche in conflitto e ripristinare la versione ufficiale, puoi utilizzare il seguente comando:
    
    
    git reset --hard
    

Infine, riavvia il servizio Odoo o il dispositivo.

### Docker¶

Consulta la [documentazione immagine Docker](https://hub.docker.com/_/odoo/) per istruzioni relative ad aggiornamenti specifici.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/on_premise/update.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deploy.html "Configurazione sistema") |
  * [precedente](source.html "Installare dalla sorgente") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Aggiornamenti per correzione bug


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