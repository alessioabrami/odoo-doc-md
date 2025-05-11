# Regole di automazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](scheduled_actions.html "Scheduled actions") |
  * [precedente](closing.html "Close subscriptions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Regole di automazione



# Regole di automazione¶

With subscriptions up-and-running, it is important to stay up-to-date with customers. It is efficient to use automation to avoid having to manually go through the list of subscribers to see how things are going. That is where Odoo’s _automation rules_ feature comes into play.

The Odoo _Subscriptions_ application allows users to set up automatic emails, create tasks for salespeople, and even send satisfaction surveys for subscribers to evaluate their experience.

## Crea regole per l’automazione¶

To create an automated rule, start by navigating to Subscriptions app ‣ Configuration ‣ Automation Rules. This is where all the automation rules for subscriptions can be found.

The Automation Rules page shows each rule’s Name, Action To Do, what the automated rule will Trigger On, and the Company to which the rule applies.

To view or modify any existing automation rule, simply click the desired rule from this page.

Nota

When modifying an existing automation rule, Odoo «grays-out» the Action section of the form, and provides the following warning: _Action data can not be updated to avoid unexpected behaviors. Create a new action instead._

To create a new automation rule, click New.

Clicking New reveals a blank Automation Rules form with numerous fields to configure.

### Automation rule form fields¶

  * Action Name: title of the automated action rule.




#### Apply On section¶

The Apply On section dictates which subscription orders/customers this automated action applies to.

  * MRR Between: designate a range of monthly recurring revenue to target.

  * MRR Change More: designate a change of monthly recurring revenue to target, in either percentage or unit of currency.

  * Over: choose a period of time over which the designated KPIs (Key Performance Indicators) are calculated.

  * Rating Satisfaction: designate satisfaction as greater than or less than a percentage.

  * Status: select the status of the subscriptions to be included in this automation rule. The options are: Quotation, Quotation Sent, Sales Order, and Cancelled.

  * Stage goes from: designate when the automation rule should be activated using two fields that represent two different stages of the subscription.

  * Subscription Plans: choose specific subscription plans to target with the automation rule.

  * Products: select specific product(s) to target with the automation rule.

  * Customers: select specific customer(s) to target with the automation rule.

  * Company: in a multi-company environment, select a specific company’s subscription data to target with the automation rule.

  * Sales Team: select the data of specific sales team(s) to target with the automation rule.




Nota

If any field is left blank, the rule applies to every subscription without that specific designation.

Suggerimento

The number of subscriptions that match the configured criteria of the customized automation rule are displayed at the bottom of the Apply On field.

If that green subscriptions link is clicked, Odoo reveals a separate page showcasing all the subscriptions that meet that automation rule’s criteria.

#### Action section¶

The Action section dictates what action occurs when an automated rule is triggered.

In the Action To Do field, choose the action that will occur once the automated rule is triggered. When clicked, the following options become available on a drop-down menu:

  * Create next activity: creates the next activity to occur, which is configured in the Activity section that appears at the bottom of the automation rule form.

  * Send an email to the customer: sends an email to the customer(s) who fit the specified criteria of the automation rule.

  * Send an SMS Text Message to the customer: sends an SMS message to the customer(s) who fit the specified criteria of the automation rule.

  * Set Contract Health value: set the health value of the subscription contract.




If Send an email to the customer is selected in the Action To Do field, the following field appears:

  * Email Template: create (and edit) a new email template _or_ select from a list of pre-configured email templates to send to the customer(s).




If Send an SMS Text Message to the customer is selected in the Action To Do field, the following field appears:

  * SMS Template: create (and edit) a new SMS template _or_ select from a list of pre-configured SMS templates to send to the customer(s).




If Set Contract Health value is selected in the Action To Do field, the following field appears:

  * Health: designate the health of the subscription by choosing one of the following options: Neutral, Good, or Bad.




In the Trigger On field, decide whether the automated rule should be triggered on a Modification or Timed Condition.

Nota

A Trigger Now button appears at the top of the automation rule form _only_ when a trigger has been configured for the rule.

Avvertimento

When the Trigger Now button is clicked, Odoo will trigger the action on _all_ linked subscriptions, regardless of possible timed conditions.

Nota

Sending a SMS text message in Odoo requires In-App Purchase (IAP) credit or tokens. For more information on IAP, visit [Acquisti in-app (IAP)](../../essentials/in_app_purchase.html). For more information on sending SMS messages, visit [SMS Marketing](../../marketing/sms_marketing.html).

If Timed Condition is selected in the Trigger On field, the following fields appear:

  * Trigger Date: represents when the condition should be triggered. If left blank, the action is created upon subscription creation _and_ updates.

  * Delay After Trigger: select a delayed amount of time (Minutes, Hours, Days, or Months) for Odoo to wait before triggering the configured action. If a negative number is entered, the «delay» will occur _before_ the Trigger Date.




##### Activity section¶

If Create next activity is selected in the Action To Do field, an Activity section appears at the bottom of the Automation Rules form.

  * Activity Type: select an pre-configured activity type from the drop-down menu.

  * Title: enter a custom title for the chosen activity.

  * Note: leave a note for the employee to whom the activity is assigned.

  * Due Date In: enter an amount of days within which the activity should be completed.

  * Assign To: choose to assign the specified activity to either: Subscription Salesperson, Sales Team Leader, or Specific Users.




Nota

If Specific Users is selected as the Assign To option, a new Specific Users field appears beneath it, where a specific employee(s) can be chosen as the assignee(s) for the configured activity.

Vedi anche

  * [Abbonamenti](../subscriptions.html)

  * [Subscription plans](plans.html)

  * [Acquisti in-app (IAP)](../../essentials/in_app_purchase.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/subscriptions/automatic_alerts.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](scheduled_actions.html "Scheduled actions") |
  * [precedente](closing.html "Close subscriptions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Regole di automazione


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