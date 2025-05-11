# Collegare una fotocamera — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](footswitch.html "Collegare un interruttore a pedale") |
  * [precedente](measurement_tool.html "Collegare uno strumento di misura") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una fotocamera



# Collegare una fotocamera¶

È possibile collegare una telecamera a una box IoT con un database Odoo in pochi passaggi. Una volta che la fotocamera è stata collegata a una box IoT, può essere utilizzata in un processo di produzione o può essere collegata a un punto di controllo qualità. In questo modo è possibile scattare foto quando viene raggiunto un punto/controllo di qualità prescelto o quando viene premuto un tasto specifico durante la produzione.

## Connessione¶

Per collegare una fotocamera a una box IoT, collega entrambi via cavo. Di solito, l’operazione viene effettuata tramite un cavo USB di qualsiasi tipo.

Se la fotocamera è [supportata](https://www.odoo.com/page/iot-hardware), non c’è bisogno di configurare nulla in quanto verrà individuata appena collegata.

## Collegare la fotocamera a un punto di controllo qualità per il processo di produzione¶

Nell’app Qualità, è possibile impostare un dispositivo su un Punto di controllo qualità. A tale scopo, spostati nell’app Qualità ‣ Controllo qualità ‣ Punti di controllo e apri il Punto di controllo desiderato che sarà collegato alla telecamera.

Nel modulo del punto di controllo, modifica lo stesso selezionando il campo Tipo e fai clic su Scatta una foto dal menu a tendina. Apparirà un campo chiamato Dispositivo dove potrai selezionare il _dispositivo_ allegato. Salva le modifiche se necessario.

La fotocamera è ora utilizzabile con il punto di controllo qualità selezionato. Quando il punto di controllo qualità viene raggiunto durante il processo di produzione, il database chiede all’operatore di scattare una foto.

Nota

È possibile accedere ai punti di controllo qualità anche dall’app IoT ‣ Dispositivi. Da qui, seleziona il dispositivo. Dalla scheda Punti controllo qualità è possibile aggiungere punti e dispositivi.

Suggerimento

In un modulo di controllo qualità, il Tipo di controllo può anche essere specificato in Fotografia. Spostati nell’app Qualità ‣ Controllo qualità ‣ Controlli qualità ‣ Nuovo per creare un nuovo controllo qualità dalla pagina Controlli qualità.

Vedi anche

  * [Quality control points](../../../inventory_and_mrp/quality/quality_management/quality_control_points.html)

  * [Quality alerts](../../../inventory_and_mrp/quality/quality_management/quality_alerts.html)




## Collegare la fotocamera a un centro di lavoro nell’app Produzione¶

Per collegare una fotocamera a un’azione, è necessario prima configurarla in un centro di lavoro. Apri l’app Produzione ‣ Configurazione ‣ Centri di lavoro. Quindi, vai alla voce Centro di lavoro desiderata in cui verrà utilizzata una fotocamera per visualizzare il modulo con i dettagli di quel centro di lavoro specifico. Da qui, aggiungi il dispositivo nella scheda Attivazioni IoT, nella colonna Dispositivo, facendo clic su Aggiungi riga.

Ora, il dispositivo della fotocamera può essere collegato all’opzione Scatta foto presente nel menu a tendina Azioni. Si può anche aggiungere un tasto per attivare l’azione.

Importante

Il primo trigger elencato viene scelto per primo. L’ordine dei trigger è importante e possono essere trascinati in qualsiasi ordine desiderato.

Nota

Nella schermata Ordini di lavoro, una grafica di stato indica se il database è stato collegato correttamente alla fotocamera.

Vedi anche

[Integrate IoT devices](../../../inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.html#workcenter-iot)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/iot/devices/camera.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](footswitch.html "Collegare un interruttore a pedale") |
  * [precedente](measurement_tool.html "Collegare uno strumento di misura") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una fotocamera


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
  *[MID]: Merchant ID
  *[TID]: Terminal ID