# Hosting — Odoo 18.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_online.html "Odoo Online") |
  * [precedente](../administration.html "Gestire i database") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Hosting



# Hosting¶

## Modificare la soluzione di hosting¶

Le istruzioni per cambiare il tipo di hosting di un database dipendono dalla soluzione in uso attualmente e quale soluzione adottare per il database.

## Trasferire un database on-premise¶

### Verso Odoo Online¶

Importante

  * Odoo Online _non_ è compatibile con **app non standard**.

  * La versione attuale del database deve essere [supportata](supported_versions.html).




  1. Crea un [duplicato del database](on_premise.html#on-premise-duplicate).

  2. Nel duplicato, disinstalla tutte le **app non standard**.

  3. Utilizza il gestore del database per ottenere una _copia di backup con FIlestore_.

  4. [Create a support ticket](https://www.odoo.com/help-form) including the following:

     * il tuo **numero di abbonamento** ,

     * l”**URL** che vuoi utilizzare per il database (ad es., `azienda.odoo.com`) e

     * il **file di backup** come allegato o come link al file (richiesto per file più grandi di 60 MB).

  5. In seguito, Odoo si assicura che il database sia compatibile prima di lanciarlo online. Odoo potrebbe contattarti in caso di problemi tecnici durante il processo.




Nota

If you have time constraints, [create a support ticket](https://www.odoo.com/help-form) as soon as possible to schedule the transfer.

### Verso Odoo.sh¶

Segui le istruzioni nella [sezione Importa il tuo database](odoo_sh/getting_started/create.html#odoo-sh-import-your-database) della documentazione _Creare un progetto_ di Odoo.sh.

## Trasferire un database Odoo Online¶

Importante

Le [versioni intermedie](supported_versions.html#supported-versions) di Odoo Online non sono supportate da Odoo.sh o on-premise. Di conseguenza, se il database da trasferire presenta una versione intermedia, dovrebbe prima essere aggiornato alla [versione principale](supported_versions.html#supported-versions) successiva, aspettando il rilascio se necessario.

Example

Il trasferimento di un database online su Odoo 16.3 richiederà l’aggiornamento alla versione Odoo 17.0.

Suggerimento

Click the __( gear) button next to the database name on the [Odoo Online database manager](https://www.odoo.com/my/databases/) to display its version number.

Avvertimento

If there is an active Odoo subscription linked to the database being migrated, reach out to the Customer Service Manager or [contact Odoo support](https://www.odoo.com/help) to complete the subscription transfer.

### Verso on-premise¶

  1. Download a database backup by signing in to [the Odoo Online database manager](https://www.odoo.com/my/databases/), clicking the __( gear) button next to the database name, then selecting __ Download. If the download fails due to the file being too large, [contact Odoo support](https://www.odoo.com/help).

  2. RIpristina il database dal gestore di database sul tuo server locale utilizzando il backup.




### Verso Odoo.sh¶

  1. Download a database backup by signing in to [the Odoo Online database manager](https://www.odoo.com/my/databases/), clicking the __( gear) button next to the database name, then selecting __ Download. If the download fails due to the file being too large, [contact Odoo support](https://www.odoo.com/help).

  2. Segui le istruzioni nella [sezione Importa il tuo database](odoo_sh/getting_started/create.html#odoo-sh-import-your-database) della documentazione _Creare un progetto_ di Odoo.sh.




## Trasferire un database Odoo.sh¶

### Verso Odoo Online¶

Importante

Odoo Online _non_ è compatibile con **app non standard**.

  1. Disinstalla tutte le **app non standard** in un build temporaneo prima di farlo nell build di produzione.

  2. [Create a support ticket](https://www.odoo.com/help-form) including the following:

     * il tuo **numero di abbonamento** ,

     * l”**URL** che vuoi utilizzare per il database (ad es., `azienda.odoo.com`),

     * quale **ramo** deve essere trasferito,

     * in quale **area** vuoi che il database venga ospitato (USA, Europa o Asia),

     * quale utente(i) sarà l”**amministratore(i)** e

     * **quando** (e in quale fuso orario) vuoi che il database sia attivo e funzionante.

  3. In seguito, Odoo si assicura che il database sia compatibile prima di lanciarlo online. Odoo potrebbe contattarti in caso di problemi tecnici durante il processo.




Nota

  * If you have time constraints, [create a support ticket](https://www.odoo.com/help-form) as soon as possible to schedule the transfer.

  * Seleziona l”**area** più vicina per la maggior parte dei tuoi utenti per ridurre la latenza.

  * Il futuro **amministratore(i)** deve disporre di un account Odoo.com.

  * Configurare la **data e ora** di un database aiuta ad organizzare il passaggio dal server Odoo.sh ai server di Odoo online.

  * I database **non sono raggiungibili** durante la migrazione.




### Verso on-premise¶

  1. Scarica un [backup del tuo database di produzione Odoo.sh](odoo_sh/getting_started/branches.html#odoo-sh-branches-backups).

  2. RIpristina il database dal gestore di database sul tuo server locale utilizzando il backup.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/administration/hosting.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_online.html "Odoo Online") |
  * [precedente](../administration.html "Gestire i database") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Hosting


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