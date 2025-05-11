# Rendiconto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](search.html "Cercare, filtrare e raggruppare i record") |
  * [precedente](activities.html "Attività") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Rendiconto



# Rendiconto¶

Nel menu Rendiconto della maggior parte delle app, è possibile selezionare vari tipi di resoconti che ti permettono di analizzare e visualizzare i dati dei tuoi record.

## Selezionare una vista¶

A seconda del tipo di rendiconto, Odoo ti permette di visualizzare i dati in diviersi modi. A volte, è disponibile una vista fatta completamente su misura per un determinato tipo di rendiconto ma sono disponibili molte altre. Tuttavia, due sono le viste generiche specifiche per la rendicontazione: la vista grafico e la vista pivot.

### Vista grafico¶

La vista grafico viene utilizzata per visualizzare i dati dei record con lo scopo di aiutarti ad identificare schemi e tendenze. È possibile trovare la vista nel menu Rendiconto delle singole applicazioni ma anche altrove, ad esempio facendo clic sul **pulsante vista grafico** situato in alto a destra.

### Vista pivot¶

La vista pivot viene utilizzata per aggregare i dati dei record e dividerli per l’analisi. È possibile trovare la vista nel menu Rendiconto delle singole applicazioni ma anche altrove, ad esempio facendo clic sul **pulsante vista pivot** situato in alto a destra.

## Scegliere le misure¶

Dopo aver selezionato una vista, devi assicurarti che vengano [filtrati](search.html) solo i record rilevanti. In seguito, è necessario scegliere cosa misurare. Per impostazione predefinita, viene sempre selezionata una misura. Se desideri modificarla, fai clic su Misure e scegline una oppure diverse ma solo per viste pivot.

Nota

When you select a measure, Odoo aggregates the values recorded on that field for the filtered records. Only numerical fields ([integer](../studio/fields.html#studio-fields-simple-fields-integer), [decimal](../studio/fields.html#studio-fields-simple-fields-decimal), [monetary](../studio/fields.html#studio-fields-simple-fields-monetary)) can be measured. In addition, the Count option is used to count the total number of filtered records.

Dopo aver scelto cosa misurare, è possibile indicare in che modo [raggruppare](search.html#search-group) i dati in base alla dimensione da analizzare. Per impostazione predefinita, i dati vengono spesso raggruppati in _Data > Mese_, parametro utilizzato per analizzare l’evoluzione di una misura per un periodo formato da più mesi.

Suggerimento

Quando filtri un singolo periodo di tempo, viene visualizzata l’opzione per paragonarlo con un altro.

Example

Select measuresGroup measures

Tra le varie misure, è possibile aggiungere Margine e Numero totale al rendiconto di analisi delle vendite. Per impostazione predefinita, è la misura Importo imponibile ad essere selezionata.

È possibile raggruppare le misure per Categoria prodotto a livello delle righe sul precedente esempio di rendiconto di analisi delle vendite.

## Utilizzare la vista pivot¶

Raggruppare i dati è tipico della vista pivot in quanto permette di indagare per avere spunti di valore. Oltre ad utilizzare l’opzione Raggruppa per per aggiungere rapidamente un gruppo a livello delle righe, come mostrato nell’esempio in alto, è anche possibile fare clic sul pulsante più (➕) accanto all’intestazione Totale a livello delle righe _e_ colonne per poi selezionare uno dei **gruppi preconfigurati**. Per eliminarne uno, fai clic sul pulsante meno (➖).

Una volta aggiunto un gruppo, è possibile aggiungerne di nuovi nell’asse opposto oppure i sottogruppi appena creati.

Example

È possibile suddividere ulteriormente le misure del precendente rendiconto di analisi delle vendite di esempio per Addetto vendite a livello delle colonne e per Data ordine > Mese nella categoria prodotto Tutti / Vendibili / Mobili ufficio.

Suggerimento

  * Passa dal gruppo delle righe al gruppo delle colonne facendo clic sul pulsante per cambiare asse (⇄).

  * Fai clic sull’etichetta di una misura per visualizzare i valori in ordine crescente (⏶) o decrescente (⏷).

  * Scarica la versione `.xlsx` della tabella pivot facendo clic sul pulsante di download (⭳).




## Utilizzare la vista grafico¶

Tre sono i grafici disponibili: a barre, a linee e a torta.

I **grafici a barre** sono utilizzati per mostrare la distribuzione o il confronto di varie categorie. Sono particolarmente utili perché possono gestire insieme di dati più grandi.

I **grafici a linee** sono utili per mostrare l’evoluzione delle serie temporali e le tendenze nel tempo.

I **grafici a torta** sono utilizzati per mostrare la distribuzione o il confronto di un piccolo numero di categorie quando formano un insieme significativo.

Bar chartLine chartPie chart

Suggerimento

Per i grafici **a barre** e a **linee** , è possibile utillizzare l’opzione impilato quando hai almeno due gruppi che appaiono l’uno in cima all’altro e non uno accanto all’altro.

Stacked bar chartRegular bar chartStacked line chartRegular line chart

Per i grafici **a linee** , è possibile utilizzare l’opzione cumulativa per sommare i valori, particolarmente utile per mostrare i cambiamenti a livello di crescita in un determinato periodo di tempo.

Cumulative line chartRegular line chart

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/essentials/reporting.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](search.html "Cercare, filtrare e raggruppare i record") |
  * [precedente](activities.html "Attività") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Rendiconto


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
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