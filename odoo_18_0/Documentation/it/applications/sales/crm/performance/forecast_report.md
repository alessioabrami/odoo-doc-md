# Resoconto previsionale — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [precedente](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto previsionale



# Resoconto previsionale¶

Il resoconto _previsionale_ dell’applicazione _CRM_ consente agli utenti di visualizzare le opportunità imminenti e di costruire una previsione delle vendite potenziali. Le opportunità sono raggruppate in base al mese della data di chiusura prevista e possono essere trascinate per modificare la scadenza.

Per accedere al resoconto _previsionale_ , accedi al modulo CRM ‣ Rendicontazione ‣ Previsione.

## Esplorare il resoconto previsionale¶

Il resoconto previsionale predefinito include le opportunità assegnate alla pipeline dell’utente corrente e che si prevede di chiudere entro quattro mesi. Mostra anche le opportunità a cui non è stata assegnata una data di chiusura prevista. Le opportunità sono raggruppate per mese in una vista __(Kanban).

### Data di chiusura prevista¶

Le opportunità sono raggruppate in base alla data assegnata nel campo _Chiusura prevista_ di un modulo opportunità. Per modificare questa data direttamente dalla pagina Previsione, seleziona la scheda Kanban dell’opportunità desiderata, poi fai clic e trascina la scheda nella colonna desiderata.

Nota

L’intervallo di tempo predefinito per le previsioni è _mese_. Si può cambiare facendo clic sul simbolo __(down) icon accanto alla barra Ricerca… nella parte superiore del resoconto. Nel menu a discesa risultante, sotto la voce Raggruppa per, fai clic su Chiusura prevista per espandere l’elenco delle opzioni disponibili e selezionare l’intervallo di tempo desiderato dall’elenco.

Dopo che un’opportunità viene aggiunta a un nuovo mese, il campo _Chiusura prevista_ del modulo dell’opportunità viene aggiornato alla data _ultima_ del nuovo mese.

Suggerimento

Il campo _Chiusura prevista_ può anche essere aggiornato manualmente sulla scheda dell’opportunità. Per farlo, fai clic sulla scheda Kanban di un’opportunità nella pagina Previsione per aprire il modulo con i dettagli dell’opportunità. Fai clic nel campo Chiusura prevista e utilizza il pop-up del calendario per selezionare una nuova data di chiusura.

### Ricavi ripartiti in proporzione¶

Nella parte superiore della colonna di ogni mese della pagina di reportistica previsionale, a destra della barra di avanzamento, si trova la somma delle entrate pro rata per quel periodo di tempo.

I ricavi ripartiti sono calcolati in base alla formula seguente:

\\[\text{Ricavi previsti} \volte \text{Probabilità} = \text{Ricavi ripartiti in proporzione}\\]

Quando le opportunità vengono spostate da una colonna all’altra, le entrate della colonna vengono aggiornate automaticamente per riflettere la modifica.

Example

Un resoconto previsionale per il mese di Giugno include due opportunità:

La prima opportunità, `Global Solutions`, ha un ricavo previsto di `3.800 $` e una probabilità del `90%`. Il risultato è un ricavo proporzionale di `3.420 $`.

La seconda opportunità, `Preventivo per 600 sedie`, ha un ricavo previsto di `22.500 $` e una probabilità del `20%`. Il risultato è un ricavo ripartito in proporzione di `4.500 $`.

Il ricavo combinato pro rata delle opportunità è di `7.920 $`, che viene elencato in cima alla colonna del mese.

Vedi anche

Per maggiori informazioni sull’assegnazione della probabilità alle opportunità, consulta la sezione [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html)

## Visualizzare i risultati¶

Fai clic sull’icona __(grafico area) per modificare la vista grafico. In seguito, fai clic sull’icona corrispondente nella parte superiore del resoconto per passare a un grafico a __(barre), __(linee) o __(torta).

Fai clic su __(pivot) icon per passare alla vista pivot o su __(list) icon per passare alla vista elenco.

Suggerimento

La [vista pivot](../../../essentials/reporting.html#reporting-using-pivot) può essere utilizzata per visualizzare e analizzare i dati in modo più approfondito. È possibile selezionare più misure ed è possibile visualizzare i dati per mese o per fase.

Vedi anche

Per salvare questo resoconto come _preferito_ , consulta la sezione [Preferiti](../../../essentials/search.html#search-favorites).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/crm/performance/forecast_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [precedente](expected_revenue_report.html "Resoconto ricavi previsti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Analizzare le performance](../performance.html) »
  * Resoconto previsionale


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
  *[MRR]: monthly recurring revenue
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