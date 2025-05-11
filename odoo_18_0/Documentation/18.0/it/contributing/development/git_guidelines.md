# Git guidelines — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../documentation.html "Documentation") |
  * [precedente](coding_guidelines.html "Coding guidelines") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Contributing](../../contributing.html) »
  * [Development](../development.html) »
  * Git guidelines



# Git guidelines¶

## Configure your git¶

Based on ancestral experience and oral tradition, the following things go a long way towards making your commits more helpful:

  * Be sure to define both the user.email and user.name in your local git config
        
        git config --global <var> <value>
        

  * Be sure to add your full name to your Github profile here. Please feel fancy and add your team, avatar, your favorite quote, and whatnot ;-)




## Commit message structure¶

Commit message has four parts: tag, module, short description and full description. Try to follow the preferred structure for your commit messages
    
    
    [TAG] module: describe your change in a short sentence (ideally < 50 chars)
    
    Long version of the change description, including the rationale for the change,
    or a summary of the feature being introduced.
    
    Please spend a lot more time describing WHY the change is being done rather
    than WHAT is being changed. This is usually easy to grasp by actually reading
    the diff. WHAT should be explained only if there are technical choices
    or decision involved. In that case explain WHY this decision was taken.
    
    End the message with references, such as task or bug numbers, PR numbers, and
    OPW tickets, following the suggested format:
    task-123 (related to task)
    Fixes #123  (close related issue on Github)
    Closes #123  (close related PR on Github)
    opw-123 (related to ticket)
    

## Tag and module name¶

Tags are used to prefix your commit. They should be one of the following

  * **[FIX]** for bug fixes: mostly used in stable version but also valid if you are fixing a recent bug in development version;

  * **[REF]** for refactoring: when a feature is heavily rewritten;

  * **[ADD]** for adding new modules;

  * **[REM]** for removing resources: removing dead code, removing views, removing modules, …;

  * **[REV]** for reverting commits: if a commit causes issues or is not wanted reverting it is done using this tag;

  * **[MOV]** for moving files: use git move and do not change content of moved file otherwise Git may loose track and history of the file; also used when moving code from one file to another;

  * **[REL]** for release commits: new major or minor stable versions;

  * **[IMP]** for improvements: most of the changes done in development version are incremental improvements not related to another tag;

  * **[MERGE]** for merge commits: used in forward port of bug fixes but also as main commit for feature involving several separated commits;

  * **[CLA]** for signing the Odoo Individual Contributor License;

  * **[I18N]** for changes in translation files;

  * **[PERF]** for performance patches;




After tag comes the modified module name. Use the technical name as functional name may change with time. If several modules are modified, list them or use various to tell it is cross-modules. Unless really required or easier avoid modifying code across several modules in the same commit. Understanding module history may become difficult.

## Commit message header¶

After tag and module name comes a meaningful commit message header. It should be self explanatory and include the reason behind the change. Do not use single words like «bugfix» or «improvements». Try to limit the header length to about 50 characters for readability.

Commit message header should make a valid sentence once concatenated with `if applied, this commit will <header>`. For example `[IMP] base: prevent to archive users linked to active partners` is correct as it makes a valid sentence `if applied, this commit will prevent users to archive...`.

## Commit message full description¶

In the message description specify the part of the code impacted by your changes (module name, lib, transversal object, …) and a description of the changes.

First explain WHY you are modifying code. What is important if someone goes back to your commit in about 4 decades (or 3 days) is why you did it. It is the purpose of the change.

What you did can be found in the commit itself. If there was some technical choices involved it is a good idea to explain it also in the commit message after the why. For Odoo R&D developers «PO team asked me to do it» is not a valid why, by the way.

Please avoid commits which simultaneously impact multiple modules. Try to split into different commits where impacted modules are different. It will be helpful if we need to revert changes in a given module separately.

Don’t hesitate to be a bit verbose. Most people will only see your commit message and judge everything you did in your life just based on those few sentences. No pressure at all.

**You spend several hours, days or weeks working on meaningful features. Take some time to calm down and write clear and understandable commit messages.**

If you are an Odoo R&D developer the WHY should be the purpose of the task you are working on. Full specifications make the core of the commit message. **If you are working on a task that lacks purpose and specifications please consider making them clear before continuing.**

Finally here are some examples of correct commit messages :
    
    
    [REF] models: use `parent_path` to implement parent_store
    
     This replaces the former modified preorder tree traversal (MPTT) with the
     fields `parent_left`/`parent_right`[...]
    
    [FIX] account: remove frenglish
    
     [...]
    
     Closes #22793
     Fixes #22769
    
    [FIX] website: remove unused alert div, fixes look of input-group-btn
    
     Bootstrap's CSS depends on the input-group-btn
     element being the first/last child of its parent.
     This was not the case because of the invisible
     and useless alert.
    

Nota

Use the long description to explain the _why_ not the _what_ , the _what_ can be seen in the diff

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/contributing/development/git_guidelines.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../documentation.html "Documentation") |
  * [precedente](coding_guidelines.html "Coding guidelines") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Contributing](../../contributing.html) »
  * [Development](../development.html) »
  * Git guidelines


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