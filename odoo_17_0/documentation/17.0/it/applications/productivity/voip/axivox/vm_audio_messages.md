# Voicemails and audio messages — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dynamic_caller_id.html "Dynamic caller ID") |
  * [precedente](manage_users.html "Manage users in Axivox") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Voicemails and audio messages



# Voicemails and audio messages¶

Managing voicemail is an important part of any business. A company needs to access their messages with ease, and stay on top of any missed calls. Recording audio messages, like thanking a caller for reaching out, or directing them to the right extension, is also a great way to personalize the business interaction, and set the tone with the customer.

This document covers the configuration of both voicemail and audio messages in the Axivox administrative portal.

## Set global language¶

To start using voicemails and audio messages with Axivox, the global language should be set in the Axivox admin portal settings. To do that, navigate to [manage.axivox.com](https://manage.axivox.com/). After logging into the portal, go to Settings ‣ Global language (e.g.: voicemail messages,…).

From here, set the language to either: Francais, English, Espanol, or Deutsch.

Then, click Save, followed by Apply changes in the upper-right corner of the General Settings page to implement the change into production.

## Activate voicemail¶

In order for a user to utilize voicemail in Axivox, the voicemail feature **must** be turned on in the Axivox administrative portal. To begin using voicemail with a user, navigate to [manage.axivox.com](https://manage.axivox.com/). Then, log in with the appropriate administrator credentials.

On the left menu of the Axivox administrative panel, click into Users.

Then, click into the specific user the voicemail should be activated for. Under the section marked, Voicemail, open the drop-down menu, and click on Yes.

Lastly, Save the change, then click Apply changes in the upper-right corner of the screen.

## Voicemail¶

The next step is to set up the individual voicemail boxes on the Axivox administrative portal. To access the portal, visit [manage.axivox.com](https://manage.axivox.com/) and log in. Then, navigate to Voicemails, located in the menu on the left.

If the voicemail option was activated in the user profile, using this process Activate voicemail, then a voicemail is automatically created on the Voicemails page.

Suggerimento

It should be noted that some of the administrative portal language is in French, as Axivox is a Belgian company. The global language is still set to one of the four options as seen here: Set global language.

### Manually create voicemail¶

To manually create a new voicemail box, click Add a voicemail on the Voicemails page. Or, edit an existing voicemail box, by clicking Edit to the far-right of an existing voicemail box on the Voicemails page.

Example

Suppose a sales or support team needs a general voicemail box. The voicemail would need to be created manually, and attached to an incoming number.

The new, manually-created voicemail box should be attached to an incoming number, so it can receive messages. To do so, navigate to Incoming numbers, located in the menu on the left. Then, click Edit to the far-right of the specific number the voicemail should be linked to.

In the Destination type for voice call field, click the drop-down menu, and select Voicemail. Then, open the drop-down menu on the next line labeled, Voicemail, and select the manually-created voicemail box.

Importante

If an incoming number is capable of receiving SMS/text messages, an additional field, Destination email address for Incoming SMS, is present.

To determine whether an incoming number is capable of receiving SMS/text messages, click Incoming numbers from the menu on the left, then check the SMS compatible column for the incoming number.

Then, if applicable, in the field labeled, Destination email address for Incoming SMS, enter an email to which incoming text messages sent to the incoming number can be received. Some incoming numbers (US +1) in Axivox are capable of receiving text messages from individuals and automated numbers.

Should this field be left empty, the default destination address is used, instead (as previously set in the beginning of the process for manually creating a voicemail).

Once all desired configurations are complete, click Save, then click Apply changes in the upper-right corner of the screen to implement the change into production.

### Notifiche¶

Now, whenever a voicemail is received on any of the automatically pre-configured or manually-linked voicemail boxes, an email is sent to the user’s email address, as listed in the Voicemails page, or in the user’s Axivox profile.

This information can be accessed by navigating to Users in the left menu, and clicking Edit next to the specific user in question.

## Forwarding to voicemail¶

In Axivox, there are also numerous forwarding settings for a user. To access these forwarding settings, go to [manage.axivox.com](https://manage.axivox.com/) and log in.

Next, navigate to Users, located in the menu on the left.

From there, click into the specific user the forwarding should be added to. Then, open the Forwardings tab.

If the user is busy on another call, or away from the phone, there is an option present in this tab to Send to voicemail as a last resort, located in the Forwarding on no answer and Forwarding on busy fields.

If the Send to voicemail as a last resort box is ticked, when the forwarding actions stated in each section are not successful, the caller is routed to the voicemail set on the particular user.

Vedi anche

For more information on forwarding and transfers, visit [Forwardings tab](manage_users.html#voip-axivox-forwardings-tab).

When all the desired configurations are complete, click Save, then click Apply changes in the upper-right corner of the screen to implement the change.

## Audio messages¶

It is possible to add audio messages _before_ a customer’s call is even taken, to inform them about the waiting time for deliveries, the availability of a product, or any other important promotional messages.

To record an audio message in Axivox, navigate to [manage.axivox.com](https://manage.axivox.com/) and log in.

Next, click on Audio messages in the menu on the left. From the Audio messages page, click Add a message.

Type in a Name, and click Save.

Upon clicking Save, the browser redirects back to the main Audio messages page, where the newly-created message can be found on the list.

There are two different ways to make the audio message. The user could either record the message over the phone, or type the message (in text), and select a computer-generated speaker to read the message.

### Record audio message¶

To record an audio message over the phone, click the orange button labeled, Record/Listen, located to the right of the desired message on the list to record, on the Audio messages page.

When clicked, a Record / listen to a message pop-up window appears. From here, the message is then recorded, via one of the extensions that is associated with the user. Under Extension to use for message management field, click the drop-down menu, and select the extension where Axivox should call to record the message.

Then, click OK to begin the call.

Nota

The user **must** be active in the production database with VoIP configured. To configure VoIP for a user, see this documentation: [VoIP services in Odoo with Axivox](axivox_config.html).

Upon connecting to the Axivox audio recorder management line, a recorded French-speaking operator provides the following options:

  1. Press `1` to record a message.

  2. Press `2` to listen to the current message.




Press either `1` or `2`, depending on whether or not there is already a message present in the system for this particular audio message that requires a review, before recording a new one.

Record the new audio message after pressing `1`, then press `#` to end the recording.

The French-speaking operator returns to the line presenting the first set of questions again:

  1. Press `1` to record a message.

  2. Press `2` to listen to the current message.




Press `#` to end the call.

### Write audio message¶

To type the message, and select a computerized speaker to say the text, navigate to the Audio messages in the menu on the left.

From the Audio messages page, select the blue button labeled, Text message, next to the corresponding audio message Name that the message should be attached to.

Doing so reveals a Convert text to message pop-up window.

From the Convert to text message pop-up window, click the drop-down menu next to the field labeled, Voice, and select an option for the Text to be read in.

After the Voice selection has been made, and the message has been written in the Text field, click Generate to process the audio file.

The text is read in the same language it is written in the Text field. Should the language differ in the Voice field, then an accent is used by the computerized speaker.

Finally, when these steps are complete, click Save to save the audio message.

To implement the changes, click Apply changes in the upper-right corner of the screen.

Suggerimento

To set a greeting or audio message in a dial plan element double-click on the element. This could be a Play a file element, or a Menu element, in which the caller should encounter an urgent message, or a dial-by-number directory.

For more information on dial plans see this documentation: [Dial plan basics](dial_plan_basics.html) or [Advanced dial plans](dial_plan_advanced.html).

## Music on-hold¶

Axivox has the option to add custom hold music to the call whenever a caller is waiting for their call to be answered. To add hold music to the Axivox administrative portal, navigate to the [manage.axivox.com](https://manage.axivox.com/), and log in.

Then, click on Music on hold from the menu on the left, and a Change the music on hold pop-up window appears.

On the Change the music on hold pop-up window, click the Choose File button to select an MP3 (MPEG Audio Layer 3) or WAV (Waveform Audio File Format ) file to be uploaded.

Nota

Only MP3 or WAV files can be uploaded to the Axivox administrative portal.

Once the file is selected, the Progression bar shows an upload status. When this activity completes, the window can be closed, by clicking Close.

When the desired changes are complete, click Apply changes in the upper-right corner of the screen.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/voip/axivox/vm_audio_messages.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dynamic_caller_id.html "Dynamic caller ID") |
  * [precedente](manage_users.html "Manage users in Axivox") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Voicemails and audio messages


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
  *[CSV]: Valori separati da virgola
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