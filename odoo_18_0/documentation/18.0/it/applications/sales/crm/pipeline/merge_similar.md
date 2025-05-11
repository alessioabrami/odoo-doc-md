# Unire lead e opportunità simili — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage_sales_teams.html "Gestire i team vendite") |
  * [precedente](lost_opportunities.html "Opportunità perse") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Unire lead e opportunità simili



# Unire lead e opportunità simili¶

Odoo rileva automaticamente _lead_ e _opportunità_ simili all’interno dell’applicazione _CRM_. L’identificazione di questi record duplicati consente di unirli senza perdere alcuna informazione nel processo. Questo non solo aiuta a mantenere la _pipeline_ organizzata, ma impedisce anche che i clienti vengano contattati da più di un addetto vendite.

Nota

Quando vengono unite delle opportunità, tutte le informazioni vengono trasferite correttamente, I dati dell’altra opportunità vengono registrati nel chatter e nei campi informazioni.

## Individuare lead e opportunità simili¶

I lead e le opportunità simili vengono identificati confrontando _l’indirizzo e-mail_ e il _numero di telefono_ del contatto associato. Se si trova un lead/opportunità simile, nella parte superiore del record del lead (o dell’opportunità) viene visualizzato il pulsante _Lead simili_.

### Confrontare lead e opportunità simili¶

Per confrontare i dettagli di lead/opportunità simili, apri l’app CRM ‣ Pipeline o CRM ‣ Lead. Apri un lead o un’opportunità e fai clic sul pulsante Lead simili. In questo modo si apre una vista Kanban che visualizza solo lead/opportunità simili. Fai clic su una scheda per visualizzare i dettagli del lead/opportunità e confermare se devono essere uniti.

## Unire lead e opportunità simili¶

Importante

Durante l’unione, Odoo dà la priorità al lead/opportunità che è stato creato per primo nel sistema, unendo le informazioni nel primo lead/opportunità creato. Tuttavia, se vengono uniti un lead e un’opportunità, il record risultante viene definito opportunità, indipendentemente dal record creato per primo.

Dopo aver confermato che i lead/opportunità devono essere uniti, torna alla vista Kanban usando il link breadcrumb o facendo clic sul pulsante Lead simili. Fai clic sull’icona __(elenco) per passare alla vista elenco.

Spunta la casella a sinistra della pagina per i lead/opportunità da unire. In seguito, fai clic sull’icona __ Azioni nella parte alta della pagina per accedere al menu a tendina. Dal menu a tendina, seleziona l’opzione Unisci per unire le opportunità e i lead selezionati.

Se selezioni Unisci dal menu a tendina __ Azioni, apparirà il pop-up modale Unisci. In questa finestra, sotto la sezione Assegna opportunità a, seleziona un Addetto vendite e un Team di vendita dai menu a discesa appropriati.

In basso ai campi verranno elencati i lead/opportunità da unire insieme alle informazioni correlate. Per unire i lead/opportunità selezionati, fai clic su Unisci.

Pericolo

L’unione è un’azione irreversibile. **Non** unire lead/opportunità a meno che non sia assolutamente certo che debbano essere combinati.

## Casi in cui non bisogna unire lead/opportunità¶

Ci possono essere casi in cui viene identificato un lead o un’opportunità simile, ma che _non_ deve essere unito. Queste circostanze variano in base ai processi del team di vendita e dell’organizzazione. Di seguito sono elencati alcuni scenari potenziali.

### Lead persi¶

Se un lead/opportunità viene contrassegnato come [perso](lost_opportunities.html), è ancora possibile unirlo con un lead od opportunità attivo. Il lead/opportunità risultante viene contrassegnato come attivo e aggiunto alla pipeline.

### Contatto diverso nell’organizzazione¶

I lead/opportunità della stessa organizzazione ma con punti di contatto diversi potrebbero non avere gli stessi bisogni. In questo caso, è bene _non_ unire questi record sebbene l’assegnazione dello stesso addetto alle vendite o team di vendita può evitare la duplicazione del lavoro e gli errori di comunicazione.

### Duplicati esistenti con più di un addetto vendite¶

Se nel database esistono più lead/opportunità, è possibile che vi siano più venditori assegnati che stanno lavorando attivamente in modo indipendente. Sebbene questi lead/opportunità debbano essere gestiti separatamente, ti consigliamo di etichettare i venditori interessati in una nota interna per garantire la visibilità.

### Le informazioni di contatto sono simili ma non uguali¶

I lead e le opportunità simili vengono identificati confrontando gli indirizzi e-mail e i numeri di telefono dei contatti associati. Tuttavia, se l’indirizzo e-mail è _simile_ , ma non _esatto_ , potrebbe essere necessario mantenerli indipendenti.

Example

Tre diversi lead sono stati aggiunti alla pipeline e assegnati a venditori diversi. Sono stati identificati come _Lead simili_ a causa degli indirizzi e-mail dei contatti.

Due dei nuovi lead provengono dalla stessa persona, `Robin`, e hanno gli stessi indirizzi e-mail. I lead devono essere uniti.

Il terzo lead ha lo stesso dominio e-mail, ma l’indirizzo è diverso, così come il nome del contatto. Pur provenendo molto probabilmente dalla stessa organizzazione, questo lead proviene da un contatto diverso e non deve essere unito.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/crm/pipeline/merge_similar.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage_sales_teams.html "Gestire i team vendite") |
  * [precedente](lost_opportunities.html "Opportunità perse") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Unire lead e opportunità simili


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