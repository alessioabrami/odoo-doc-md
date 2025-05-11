# Campaign workflow activities — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](testing_running.html "Testing/running campaigns") |
  * [precedente](target_audience.html "Audience targeting") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign workflow activities



# Campaign workflow activities¶

A _workflow_ is the overall _activity_ structure of a marketing automation campaign. There can only be a single workflow in each campaign. However, a workflow can be made up of any number of activities to meet the needs of the campaign.

Workflow sequence of three activities; the last child activity has a trigger type of **Mail: not opened**.¶

## Attività¶

Activities are the methods of communication or server actions, organized in a workflow, that are executed within a campaign; they are the building blocks of the campaign’s workflow.

A new activity can be added to the workflow on a campaign form by selecting an existing campaign or [creating a new campaign](../marketing_automation.html#marketing-automation-campaigns) from the Marketing Automation app ‣ Campaigns dashboard, then clicking the Add new activity button in the Workflow section. Doing so opens the Create Activities pop-up window.

First, define the name of the activity in the Activity Name field, and select the type of activity to be executed from the Activity Type field.

Then, configure the activity’s Trigger, and optionally, the Expiry Duration and the DOMAIN of the activity.

Once the activity is fully configured, click Save & Close to add it to the campaign’s workflow, or click Save & New to add the activity to the workflow and open a new Create Activities pop-up window to add another activity. Clicking Discard closes the pop-up window without saving the activity.

### Tipi di attività¶

There are three different types of activities available in the _Marketing Automation_ app:

  * Email: an email that is sent to the target audience.

  * Server action: an internal action within the database that is executed.

  * SMS: a text message that is sent to the target audience.




#### E-mail¶

If Email is selected as the Activity Type, the option to Pick a Template in the Mail Template field is available.

To create a new template directly from the Mail Template field, start typing the title of the new template, then select Create and edit… to reveal a Create Marketing Template pop-up window. Proceed to create and configure the new email template.

Once the email template is configured, click Save & Close to save the activity, and return to the Create Activities pop-up window, in order to continue to configure the trigger.

Nota

The title used for the Mail Template **must** be unique from any other mail template titles in the campaign, and it also serves as the subject of the email.

Vedi anche

[Creating and configuring email templates](../email_marketing.html)

#### Azione server¶

If Server Action is selected as the Activity Type, the option to Pick a Server Action in the Server Action field is available. This field is a drop-down menu containing all the pre-configured server actions for the campaign’s Target model. Optionally, create a new server action.

After selecting a pre-configured server action, no other activity type configuration is needed. Click Save & Close to save the activity, and return to the Create Activities pop-up window, in order to configure the trigger.

Suggerimento

To view all server actions in the database, activate [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html#developer-mode), and navigate to Settings app ‣ Technical ‣ Actions ‣ Server Actions dashboard.

##### Create a new server action¶

The option to create a new server action is also available. To do so, type in the Server Action field a title for the new action, then click Create and edit…. Doing so reveals a blank Create Server Action pop-up window, wherein a custom server action can be created and configured.

On the Create Server Action pop-up window, select the Type of server action. The configuration fields change, depending on the selected Type:

  * Update Record: update the values of a record.

  * Create Activity: create an activity with the _Discuss_ app.

  * Send Email: post a message, a note, or send an email with the _Discuss_ app.

  * Send SMS: send an SMS, and log them on documents, with the _SMS_ app.

  * Add Followers or Remove Followers: add or remove followers on a record with the _Discuss_ app.

  * Create Record: create a new record with new values.

  * Execute Code: execute a block of Python code.

  * Send Webhook Notification: send a POST request to an external system.

  * Execute Existing Actions: define an action that triggers several other server actions.




Once the server action is configured, click Save & Close to save the activity, and return to the Create Activities pop-up window, in order to configure the trigger.

Suggerimento

Some of the server action types have advanced configurations available when [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html#developer-mode) is activated, such as specifying the Allowed Groups that can execute this server action.

#### SMS¶

If SMS is selected as the Activity Type, the option to Pick a Template in the SMS Template field is available.

To create a new template directly from the SMS Template field, start typing the title of the new template, and select Create and edit… to reveal a Create Marketing Template pop-up window. Proceed to create and configure the new SMS template.

Once the SMS template is configured, click Save & Close to save the activity, and return to the Create Activities pop-up window, in order to configure the trigger.

Vedi anche

[Creating and configuring SMS templates](../sms_marketing.html)

### Attivazione¶

Once an activity type is configured, the next step in the Create Activities pop-up window is to define when the activity should be executed. This is done in the Trigger field group.

To set an execution delay for the activity from when the trigger type occurs, type a whole number in the _interval number_ input (e.g. `2` is valid, `0` is also valid, and `1.5` is not).

Next, select the unit of time for the interval number in the _interval type_ drop-down menu, the options are: Hours, Days, Weeks, and Months.

Example

If the interval number is set to `0` and the interval type is set to Hours, the activity will be executed immediately after the trigger type occurs (at the next scheduled run of the [Mail: Email Queue Manager cron](../../general/email_communication/faq.html#email-issues-outgoing-execution-time)).

#### Trigger type¶

To define the event occurrence that sets the activity into motion, select a _trigger type_ from the drop-down menu:

  * beginning of workflow: the activity is executed when the campaign is started.




All other trigger types reveal a drop-down menu Activity field containing all of the other activities in the campaign. Selecting one of these types converts this activity into a child activity to be executed directly after the selected Activity:

  * another activity: to be executed after another activity in the campaign.

  * Mail: opened: the activity’s email was opened by the participant.

  * Mail: not opened: the activity’s email was **not** opened by the participant.

  * Mail: replied: the activity’s email was replied to by the participant.

  * Mail: not replied: the activity’s email was **not** replied to by the participant.

  * Mail: clicked: a link in the activity’s email was clicked by the participant.

  * Mail: not clicked: a link in the activity’s email was **not** clicked by the participant.

  * Mail: bounced: the activity’s email has bounced.

  * SMS: clicked: a link in the activity’s SMS was clicked by the participant.

  * SMS: not clicked: a link in the activity’s SMS was **not** clicked by the participant.

  * SMS: bounced: the activity’s SMS has bounced.




Example

If the trigger type is set to Mail: clicked, this activity is converted to a child activity and will execute **after** a participant clicks on a link from the parent activity defined in the Activity field.

### Expiry duration¶

Optionally, an Expiry Duration can be defined in the Create Activities pop-up window to cancel the execution of this activity after a specific amount of time. Selecting this checkbox reveals the Cancel after field with _interval_ and _interval type_ inputs.

Type a whole number in the interval number input (e.g. `2` is valid, `0` is also valid, and `1.5` is not). Then, select the unit of time for the interval number in the interval type drop-down menu, the options are: Hours, Days, Weeks, and Months.

Example

If the interval number is set to `2` and the interval type is set to Days, the activity will be cancelled if it has not been executed within 2 days of the trigger type.

### Activity domain¶

The DOMAIN section of the Create Activities pop-up window contains fields to further filter the target audience of the activity.

The Activity Filter field focuses this activity, **and** its child activities, even further on a specific group of the campaign’s filter. The process is the same as [defining filters](target_audience.html#marketing-automation-defining-filters) for the campaign, and the fields that are available to filter are also specific to the Target of the campaign.

The # record(s) beside the Activity Filter field indicates how many records are currently being targeted by this Activity Filter.

The Applied Filter displays the combined filters from the Activity Filter and the inherited campaign [Filter](target_audience.html). This field is read-only.

The # record(s) beside the Applied Filter field indicates how many records, in total, are currently being targeted by the activity.

## Child activities¶

Activities that are connected to, and triggered by, another activity are known as, _child activities_.

The activity that triggers a child activity is known as its _parent activity_.

A child activity can be added to a campaign’s workflow by hovering over the ➕ Add child activity button, located beneath the desired parent activity.

The child activity’s trigger types are specific to the parent activity type (_Email_ , _SMS_ , or _Server Action_), and are as follows:

EmailServer ActionSMS

Each trigger the child activity on the following conditions of the parent activity:

  * Add Another Activity: to be executed after the parent activity.

  * Opened: the email was opened by the participant.

  * Not Opened: the email was **not** opened by the participant.

  * Replied: the email was replied to by the participant.

  * Not Replied: the email was **not** replied to by the participant.

  * Clicked: a link in the email was clicked by the participant.

  * Not Clicked: a link in the email was **not** clicked by the participant.

  * Bounced: the email has bounced.




Triggers the child activity on the following condition of the parent activity:

  * Add Another Activity: to be executed after the parent activity.




Each trigger the child activity on the following conditions of the parent activity:

  * Add Another Activity: to be executed after the parent activity.

  * Clicked: a link in the SMS was clicked by the participant.

  * Not Clicked: a link in the SMS was **not** clicked by the participant.

  * Bounced: the SMS has bounced.




Once a trigger type is selected, the Create Activities pop-up window opens to configure the child activity. The process is the same as creating a new activity, with the exception that the Trigger field is pre-filled with the selected trigger type, and the Activity field has the parent activity selected.

Vedi anche

  * [Testing/running campaigns](testing_running.html)

  * [Campaign metrics](understanding_metrics.html)

  * [Audience targeting](target_audience.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/marketing_automation/workflow_activities.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](testing_running.html "Testing/running campaigns") |
  * [precedente](target_audience.html "Audience targeting") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign workflow activities


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