# Prodotti opzionali — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_signature_to_validate.html "Firme online per confermare gli ordini") |
  * [precedente](quote_template.html "Modelli preventivo") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Preventivi di vendita](../sales_quotations.html) »
  * Prodotti opzionali



# Prodotti opzionali¶

L’uso di prodotti opzionali è una strategia di marketing che prevede il cross-selling di prodotti insieme al prodotto principale. L’obiettivo è quello di offrire ai clienti prodotti utili e correlati, che possono portare a un aumento delle vendite.

Ad esempio, se un cliente vuole acquistare un’auto, può scegliere se ordinare anche i sedili massaggianti o ignorare l’offerta e acquistare semplicemente l’auto. La scelta di acquistare prodotti opzionali migliora l’esperienza del cliente.

## Prodotti opzionali sui preventivi¶

Con l’applicazione Odoo _Vendite_ , è possibile aggiungere o modificare i prodotti opzionali direttamente sui preventivi accedendo alla scheda Prodotti opzionali di un modulo di preventivo.

Per aggiungere uno o più prodotti opzionali a un preventivo, fai clic su Aggiungi un prodotto nella scheda Prodotti opzionali di un preventivo. In questo modo ottieni un campo vuoto nella colonna Prodotto.

Una volta fatto clic, appare un menu a tendina con i prodotti del database. Seleziona il prodotto desiderato dal menu a discesa per aggiungerlo come prodotto opzionale al modello di preventivo.

Suggerimento

Se il prodotto desiderato non è immediatamente visibile, scrivi il nome del prodotto desiderato nel campo e l’opzione apparirà nel menu a tendina. Successivamente, seleziona il prodotto desiderato per aggiungerlo al preventivo.

Nota

Quando un prodotto viene aggiunto, la quantità predefinita è `1` ma può essere modificata in qualsiasi momento.

Per eliminare qualsiasi riga con articoli dalla scheda Prodotti opzionali, fai clic sull’icona 🗑️ (cestino).

Fai clic sul pulsante Anteprima, situato nell’angolo superiore a sinistra del preventivo, per visualizzare un’anteprima del preventivo che i clienti riceveranno via e-mail, insieme ai prodotti opzionali che possono potenzialmente aggiungere al loro ordine, situati nella sezione Opzioni.

I clienti hanno la possibilità di aggiungere vari prodotti opzionali a un ordine facendo clic sull’icona 🛒 (carrello spesa) situata nella parte destra della riga prodotto opzionale.

Se il cliente seleziona dei prodotti opzionali, questi vengono aggiunti automaticamente al preventivo gestito dall’addetto vendite.

Quando il cliente aggiunge uno o più prodotti opzionali a un ordine, l’addetto alle vendite viene immediatamente informato della modifica, insieme a qualsiasi altra modifica apportata dal cliente a un ordine. In questo modo i venditori possono rimanere aggiornati su tutto ciò che riguarda un ordine nel backend dell’applicazione _Vendite_.

## Prodotti opzionali su modelli di preventivo¶

Nota

Assicurati di rileggere la documentazione sui [Modelli preventivo](quote_template.html) per comprendere meglio come funzionano i modelli di preventivo prima di leggere le informazioni seguenti.

Per i modelli di preventivo, proprio come un tipico modulo di preventivo, esiste anche una scheda Prodotti opzionali, in cui è possibile aggiungere prodotti o servizi correlati a un modello di preventivo.

Per aggiungere prodotti opzionali a un modello di preventivo, apri il modulo Vendite ‣ Configurazione ‣ Modelli di preventivo. In seguito, seleziona un modello di preventivo esistente da modificare o creane uno nuovo facendo clic su Nuovo.

Nel modulo del modello di preventivo, fai clic sulla scheda Prodotti opzionali. Nella scheda Prodotti opzionali, fai clic su Aggiungi riga e seleziona il prodotto desiderato da aggiungere come prodotto opzionale al modello di preventivo.

I prodotti aggiunti nella scheda Prodotti opzionali sono presenti nel preventivo, per impostazione predefinita, ogni volta che si utilizza quel particolare modello di preventivo. È possibile rimuovere questi prodotti e aggiungerne altri prima di inviare l’offerta al cliente.

Suggerimento

È meglio offrire prodotti opzionali che incoraggino il cliente ad aggiungere altri articoli all’ordine o che lo spingano ad acquistare una versione più costosa del prodotto inizialmente scelto.

Ad esempio, se un cliente acquista una sedia in legno, alcuni prodotti opzionali potrebbero essere: una garanzia sulla sedia e/o una sedia in legno con sedili in pelle.

Nota

Non c’è limite al numero di prodotti opzionali che possono essere aggiunti a un modello di preventivo.

Vedi anche

[Modelli preventivo](quote_template.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/sales_quotations/optional_products.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_signature_to_validate.html "Firme online per confermare gli ordini") |
  * [precedente](quote_template.html "Modelli preventivo") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Preventivi di vendita](../sales_quotations.html) »
  * Prodotti opzionali


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