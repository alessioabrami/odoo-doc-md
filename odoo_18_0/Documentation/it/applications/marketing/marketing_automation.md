# Automazione marketing — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_automation/target_audience.html "Audience targeting") |
  * [precedente](email_marketing/analyze_metrics.html "Analyze metrics") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Automazione marketing



# Automazione marketing¶

Use the Odoo **Marketing Automation** application to create dynamic campaigns with actions that automatically occur within a defined duration, such as sending a series of timed mass emails or engaging with leads based on their interactions with marketing campaigns.

While the application is designed to be user-friendly for creating, launching, and reviewing marketing campaigns, it also provides advanced features to automate repetitive tasks throughout the database.

Get started by creating a new campaign from scratch or start with a campaign template.

Vedi anche

[Odoo Tutorials: Marketing](https://www.odoo.com/slides/marketing-27)

#### [Audience targetingConfigure the target audience for a campaign. ](marketing_automation/target_audience.html)#### [Workflow activitiesDefine the activities that occur within a campaign. ](marketing_automation/workflow_activities.html)#### [Testing/running campaignsLaunch a test or run a campaign. ](marketing_automation/testing_running.html)#### [Campaign metricsReview the metrics of a campaign. ](marketing_automation/understanding_metrics.html)

## Configurazione¶

To begin, make sure the **Marketing Automation** application is [installed](../general/apps_modules.html#general-install).

Importante

Installing the **Marketing Automation** application also installs the [Email Marketing](email_marketing.html) app, as most features of Odoo **Marketing Automation** are dependent on that specific application.

Additionally, install the [CRM](../sales/crm.html) and [SMS Marketing](sms_marketing.html) applications to access _all_ of the features available in **Marketing Automation**.

The following documentation assumes that all three of these dependent applications are installed on the database.

## Campagne¶

A _campaign_ refers to a workflow of activities that are automatically executed to a target audience, based on predefined filters, triggers, and durations of activities.

A new campaign can be created from scratch or from a template.

To create a campaign, navigate to the Marketing Automation application and click the New button to reveal a new campaign form.

### Campaign templates¶

Odoo provides six campaign templates to help users get started. The campaign template cards **only** display when there are no existing campaigns in the database. Once a campaign has been created, the template cards on the _Campaigns_ dashboard are replaced with a Kanban view of the existing campaigns.

To get started with a template, navigate to the Marketing Automation application, from the main Odoo dashboard, to open the Campaigns dashboard, which displays six [campaign template](marketing_automation/campaign_templates.html) cards:

  * __ Tag Hot Contacts

Send a welcome email to contacts and tag them if they click it.

  * __ Welcome Flow

Send a welcome email to new subscribers, remove the address that bounced.

  * __[ Double Opt-in](marketing_automation/campaign_templates/double_optin.html)

Send an email to new recipients to confirm their consent.

  * __ Commercial prospection

Send a free catalog and follow-up according to reactions.

  * __ Schedule Calls

If a lead is created for existing contact, schedule a call with their salesperson.

  * __ Prioritize Hot leads

Send an email to new leads and assign them a high priority if they open it.




These templates are designed to be used as starting points for creating new campaigns. Click one of the template cards to open the campaign form.

Suggerimento

To display the campaign template cards again after a campaign has been created, type the name of a campaign that does **not** exist in the database into the search bar, then press `Enter`.

For example, searching for `empty` displays the campaign template cards again, as long as there is not a campaign with the name «empty» in the database.

## Targets and filters¶

On the campaign form, the Target and Filter section, also referred to as the domain, contains the fields used to define the target audience for the campaign’s reach (i.e., the unique contact records in the database).

The target audience specifies the type of records available for use in the campaign, such as _Lead/Opportunity_ , _Event Registration_ , _Contact_ , and more.

### Record¶

The contacts in the system that fit the specified criteria for a campaign are referred to as _records_.

The number of records that are displayed next to the campaign Filter represent the total number of records the campaign is targeting.

### Partecipanti¶

The records that are engaged by the campaign are referred to as _participants_.

The number of participants engaged in a test run are shown in the _Tests_ smart button, which displays on the top of the campaign form after a test has been run.

The number of participants engaged in a running, or stopped, campaign are shown in the _Participants_ smart button at the top of the campaign form.

Vedi anche

[Audience targeting](marketing_automation/target_audience.html)

## Flusso di lavoro¶

A _workflow_ consists of an activity, many activities, or a sequence of activities organized in a campaign. A campaign’s workflow is defined in the Workflow section of the campaign form.

### Attività¶

_Activities_ are the methods of communication or server actions, organized in a workflow, that are executed within a campaign. Once running, each activity displays the number of participants that are engaged by the activity as _Success_ and _Rejected_ counts.

To create one of the following activities, click Add new activity in the Workflow section of the campaign form:

  * [Email](marketing_automation/workflow_activities.html#marketing-automation-email-activity-type): an email that is sent to the target audience.

  * [Server action](marketing_automation/workflow_activities.html#marketing-automation-sa-activity-type): an internal action within the database that is executed.

  * [SMS](marketing_automation/workflow_activities.html#marketing-automation-sms-activity-type): a text message that is sent to the target audience.




Vedi anche

[Campaign workflow activities](marketing_automation/workflow_activities.html)

## Testing and running¶

Once a campaign has been created, it can be tested to ensure the workflow is functioning as expected, to check for errors, and correct any mistakes before it reaches its target audience.

After testing, the campaign can be launched to start engaging the target audience. The campaign can also be launched _without_ testing, if the user is confident in the workflow.

Vedi anche

[Testing/running campaigns](marketing_automation/testing_running.html)

## Rendiconto¶

A range of reporting metrics are available to measure the success of each campaign. Navigate to Marketing Automation app ‣ Reporting to access the following menu options:

  * Link Tracker: displays the metrics of links to track the number of clicks.

  * Traces: displays the results of all activities from all campaigns.

  * Participants: displays an overview of the participants of all campaigns.




Additionally, each activity within the workflow of a campaign displays its engagement metrics.

Vedi anche

[Campaign metrics](marketing_automation/understanding_metrics.html)

  * [Audience targeting](marketing_automation/target_audience.html)
  * [Campaign workflow activities](marketing_automation/workflow_activities.html)
  * [Testing/running campaigns](marketing_automation/testing_running.html)
  * [Campaign metrics](marketing_automation/understanding_metrics.html)
  * Campaign templates
    * [Consenso doppio](marketing_automation/campaign_templates/double_optin.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/marketing_automation.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_automation/target_audience.html "Audience targeting") |
  * [precedente](email_marketing/analyze_metrics.html "Analyze metrics") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Automazione marketing


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