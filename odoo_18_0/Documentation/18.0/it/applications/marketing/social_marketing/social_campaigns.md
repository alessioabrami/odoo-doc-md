# Social marketing campaigns — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../services.html "Servizi") |
  * [precedente](social_posts.html "Social posts") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing social](../social_marketing.html) »
  * Social marketing campaigns



# Social marketing campaigns¶

Social marketing campaigns help companies connect directly with the marketplace. These campaigns are helpful when introducing a new product to customers, explaining the value of a product or service, or when advertising an upcoming event or product release.

The most effective social marketing campaigns typically involve multiple channels to maximize content distribution, and Odoo’s _Social Marketing_ application acts as a singular control center to monitor, plan, post, track, and analyze all of the various content and content channels within a single dashboard.

## Campaigns page¶

To access a complete overview of all social marketing campaigns, open the Social Marketing application, and click Campaigns from the header menu. Doing so reveals a separate page with every campaign in a default kanban view.

Each _stage_ in the kanban view can be edited, by clicking the gear icon to the left of the \+ (plus sign) \- located to the right of the stage title.

Nota

The **gear icon** _only_ appears when the cursor hovers to the left of the **\+ (plus sign)**. When the gear icon is clicked, a drop-down menu reveals the options: Fold, Edit Stage, and Delete.

Clicking Fold minimizes that specific stage’s column. The stage column can be restored by clicking the folded version of it on the main Campaigns dashboard in the default kanban view.

Selecting Edit Stage reveals a pop-up window, in which the name and the sequence of the stage can be modified. If changes are made, be sure to click Save.

Clicking Delete removes the stage entirely.

Nota

To add a new stage to the pipeline, side-scroll to the right on the Campaigns dashboard, click Add a Column, enter in the desired information, and click Add.

Suggerimento

The same social marketing campaign information on the Campaigns dashboard can also be viewed as a list, by selecting the List option, located under the search bar, in the upper-right corner.

## Create social marketing campaigns¶

First, open the Social Marketing application, and select Campaigns from the header menu.

On the Campaigns dashboard, a new campaign can be created by clicking the quick add \+ (plus sign) located in the top-right corner of each stage in the pipeline, visible in the kanban view. Campaigns can also be created by clicking Create in the upper-left corner of the Campaigns dashboard.

Both options reveal a new campaign detail window directly on the Campaigns dashboard when clicked.

Here, the Campaign Name, Responsible, and Tags can be entered. When all modifications are complete, click Add to add the campaign to the database.

## Edit social marketing campaigns¶

In order to edit a campaign in greater detail, and create/send various forms of communications related to it, the template page for that campaign must be accessed and modified, accordingly. There are multiple ways to access a template page for a campaign.

  * After entering the pertinent information in the Quick Add campaign drop-down, click Edit.

  * Simply select the desired campaign from the Campaigns dashboard in list or kanban view.

  * On the Campaigns dashboard in the kanban view, select the ⋮ (three dots) drop-down menu on the desired campaign, and select Edit.




Any of the above routes will reveal the _Campaign Template_ page for that specific campaign.

## Social marketing campaign templates¶

On a _Campaign Template_ page, numerous elements can be customized/modified, and various forms of communications can be created, modified, and sent or scheduled. Below is a sample of a completed campaign template.

Importante

In order for the Send New Mailing option to appear on campaign templates, make sure the _Mailing Campaigns_ feature is enabled in the _Email Marketing_ app. To do that, navigate to Email Marketing ‣ Configuration ‣ Settings, activate Mailing Campaigns, and click Save.

Nota

In order for the Send SMS option to appear, the Odoo _SMS Marketing_ application must be installed on the database.

## Add content and communications to campaigns¶

If the proper settings and applications are installed (as instructed above), there are four forms of communication/content options that can be added to campaigns. Each of these options are displayed as buttons in the upper-left corner of the campaign template page.

  * Send New Mailing: reveals a blank email template on a separate page, in which the message can be fully customized in a variety of ways.

  * Send SMS: reveals a blank SMS template on a separate page, in which a SMS communication can be created and configured.

  * Send Social Post: reveals a blank social post template on a separate page, in which a post can be created, and applied to social media accounts that are already connected to the database.

  * Push Notification: reveals a similar blank social post template on a separate page, however, the Push Notification options are already pre-selected in the Post on field.




Whichever form of communication is created, once it’s completed, Odoo returns to the Campaign Template page, showcasing that new content in its corresponding tab (e.g. Mailings, SMS, Social Media, and/or Push Notifications).

As content and communications are added to a campaign, tabs for those specific mediums appear, along with a variety of analytical smart buttons (e.g. Revenues, Quotations, Leads, etc.).

These smart buttons, located at the top of the template, display different metrics related to the campaign, and its various communications and content. Clicking any smart button reveals a separate page dedicated to that particular element of the campaign, allowing for quicker, more organized analysis.

Nota

The Odoo _Social Marketing_ app is integrated with other Odoo applications, such as _Sales_ , _Invoicing_ , _CRM_ , and _Website_.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/social_marketing/social_campaigns.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../services.html "Servizi") |
  * [precedente](social_posts.html "Social posts") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing social](../social_marketing.html) »
  * Social marketing campaigns


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
  *[API]: application programming interfaces
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
  *[POS]: point of sale
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