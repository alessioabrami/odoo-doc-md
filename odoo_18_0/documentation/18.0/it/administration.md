# Gestire i database — Odoo 18.0 documentazione

### Navigazione

  * [indice](genindex.html "Indice generale")
  * [moduli](py-modindex.html "Indice del modulo Python") |
  * [successivo](administration/hosting.html "Hosting") |
  * [precedente](applications/general/developer_mode.html "Modalità sviluppatore \(modalità di debug\)") |
  * [Odoo 18.0 documentazione](index-2.html) »
  * Gestire i database



# Gestire i database¶

Queste guide forniscono istruzioni su come installare, mantenere e aggiornare i database Odoo.

Vedi anche

[Storico delle versioni](administration/supported_versions.html)

## Installazione¶

A seconda dell’uso previsto, ci sono molteplici modi per installare Odoo…o non installarlo affatto.

  * [Online](administration/odoo_online.html) è il modo più semplice per utilizzare Odoo in produzione o per testarlo.

  * [I programmi d’installazione](administration/on_premise/packages.html) sono adatti per provare Odoo e sviluppare moduli. Possono essere utilizzati per la produzione a lungo termine con distribuzioni aggiuntive e lavori di manutenzione.

  * [L’installazione dalla fonte](administration/on_premise/source.html) fornisce una grande flessiblità, in quanto permette, ad esempio, di utilizzare più versioni Odoo nello stesso sistema. È adeguata per sviluppare moduli e può essere utilizzata come base per la distribuzione di produzione.

  * Un’immagine di base [Docker](https://hub.docker.com/_/odoo/) è disponibile per lo sviluppo o la distribuzione.




## Versioni¶

Ci sono due versioni differenti.

**Odoo Community** è la versione del software free e open-source, rilasciato secondo i termini della licenza GNU LGPLv3 <<https://github.com/odoo/odoo/blob/master/LICENSE>>`_. È la base su cui si fonda Odoo Enterprise.

**Odoo Enterprise** è la versione shared source del software, che dà accesso a più funzionalità, inclusi supporto funzionale, aggiornamenti e hosting. I [prezzi](https://www.odoo.com/pricing-plan) partono da un piano gratuito.

Suggerimento

[Passa da Community a Enterprise](administration/on_premise/community_to_enterprise.html) in qualsiasi momento (eccetto per l’installazione alla fonte).

  * [Hosting](administration/hosting.html)
  * [Odoo Online](administration/odoo_online.html)
  * Odoo.sh
    * Panoramica
      * [Introduzione a Odoo.sh](administration/odoo_sh/overview/introduction.html)
    * Esordiente
      * [Creare un progetto](administration/odoo_sh/getting_started/create.html)
      * [Filiali](administration/odoo_sh/getting_started/branches.html)
      * [Build](administration/odoo_sh/getting_started/builds.html)
      * [Stato](administration/odoo_sh/getting_started/status.html)
      * [Impostazioni](administration/odoo_sh/getting_started/settings.html)
      * [Editor online](administration/odoo_sh/getting_started/online-editor.html)
      * [Il primo modulo](administration/odoo_sh/getting_started/first_module.html)
    * Avanzato
      * [Contenitori](administration/odoo_sh/advanced/containers.html)
      * [Moduli secondarii](administration/odoo_sh/advanced/submodules.html)
      * [Domande tecniche frequenti](administration/odoo_sh/advanced/frequent_technical_questions.html)
  * [On-premise](administration/on_premise.html)
    * [Programmi di installazione](administration/on_premise/packages.html)
    * [Installare dalla sorgente](administration/on_premise/source.html)
    * [Aggiornamenti per correzione bug](administration/on_premise/update.html)
    * [Configurazione sistema](administration/on_premise/deploy.html)
    * [Gateway di posta elettronica](administration/on_premise/email_gateway.html)
    * [IP geo](administration/on_premise/geo_ip.html)
    * [Passare da Community a Enterprise](administration/on_premise/community_to_enterprise.html)
  * [Aggiorna](administration/upgrade.html)
  * [Database neutralizzato](administration/neutralized_database.html)
  * [Versioni supportate](administration/supported_versions.html)
  * [App Odoo per dispositivi mobili](administration/mobile.html)
  * [Account odoo.com](administration/odoo_accounts.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration.rst)

### Navigazione

  * [indice](genindex.html "Indice generale")
  * [moduli](py-modindex.html "Indice del modulo Python") |
  * [successivo](administration/hosting.html "Hosting") |
  * [precedente](applications/general/developer_mode.html "Modalità sviluppatore \(modalità di debug\)") |
  * [Odoo 18.0 documentazione](index-2.html) »
  * Gestire i database


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
  *[EDI]: electronic data interchange
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
  *[FBM]: Fulfilled By Merchant
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