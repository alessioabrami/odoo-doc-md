# Chatter — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../data_cleaning.html "Pulizia dati") |
  * [precedente](ice_servers.html "Configure ICE servers with Twilio") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Comunicazioni](../discuss.html) »
  * Chatter



# Chatter¶

The _Chatter_ feature is integrated throughout Odoo to streamline communication, maintain traceability, and provide accountability among team members. Chatter windows, known as _composers_ , are located on almost every record within the database, and allow users to communicate with both internal users and external contacts.

Chatter composers also enable users to log notes, upload files, and schedule activities.

## Chatter thread¶

A _chatter thread_ can be found on most pages in the database, and serves as a record of the updates and edits made to a record. A note is logged in the chatter thread when a change is made. The note includes details of the change, and a time stamp.

Example

A user, Mitchell Admin, needs to update the email address of a contact. After they save the changes to the contact record, a note is logged in the chatter of the contact record with the following information:

  * The date when the change occurred.

  * The email address as it was previously listed.

  * The updated email address.




If a record was created, or edited, via an imported file, or was otherwise updated through an intervention by the system, the chatter thread creates a log note, and credits the change to OdooBot.

## Aggiungi seguaci¶

A _follower_ is a user or contact that is added to a record and is notified when the record is updated, based on specific follower subscription settings. Followers can add themselves, or can be added by another user.

Nota

If a user creates, or is assigned to a record, they are automatically added as a follower.

To follow a record, navigate to any record with a chatter thread. For example, to open a _Helpdesk_ ticket, navigate to Helpdesk app ‣ Tickets ‣ All Tickets, and select a ticket from the list to open it.

At the top-right, above the chatter composer, click Follow. Doing this changes the button to read Following. Click it again to Unfollow.

### Manage followers¶

To add another user, or contact, as a follower, click the __(user) icon. This opens a drop-down list of the current followers. Click Add Followers to open an Invite Follower pop-up window.

Select one or more contacts from the Recipients drop-down list. To notify the contacts, tick the Send Notification checkbox. Edit the message template as desired, then click Add Followers.

To remove followers, click the __(user) icon to open the current followers list. Find the name of the follower to be removed, and click the __(remove) icon.

### Edit follower subscription¶

The updates a follower receives can vary based on their subscription settings. To see the type of updates a follower is subscribed to, and to edit the list, click the __(user) icon. Find the appropriate follower in the list, then click the __(pencil) icon. This opens the Edit Subscription pop-up window for the follower.

The list of available subscription settings varies depending on the record type. For example, a follower of a _Helpdesk_ ticket may be informed when the ticket is rated. This option would not be available for the followers of a _CRM_ opportunity.

Tick the checkbox for any updates the follower should receive, and clear the checkbox for any updates they should **not** receive. Click Apply when finished.

The Edit Subscription options vary depending on the record type. These are the options for a Helpdesk ticket.¶

## Log notes¶

The chatter function includes the ability to log internal notes on individual records. These notes are only accessible to internal users, and are available on any records that feature a chatter thread.

To log an internal note, first navigate to a record. For example, to open a _CRM_ opportunity, navigate to CRM app ‣ Sales ‣ My Pipeline, and click on the Kanban card of an opportunity to open it. Then, at the top-right, above the chatter composer, click Log note.

Enter the note in the chatter composer. To tag an internal user, type `@`, and begin typing the name of the person to tag. Then, select a name from the drop-down menu. Depending on their notification settings, the user is notified by email, or through Odoo.

Importante

Outside contacts can also be tagged in an internal log note. The contact then receives an email with the contents of the note they were tagged in, including any attachments added directly to the note. If they respond to the email, their response is logged in the chatter, and they are added to the record as a follower.

Outside contacts are **not** able to log in to view the entire chatter thread, and are only notified of specific updates, based on their follower subscription settings, or when they are tagged directly.

## Send messages¶

Chatter composers can send messages to outside contacts, without having to leave the database, or open a different application. This makes it easy to communicate with potential customers in the _Sales_ and _CRM_ applications, or vendors in the _Purchase_ app.

To send a message, first navigate to a record. For example, to send a message from a _CRM_ opportunity, navigate to CRM app ‣ Sales ‣ My Pipeline, and click on the Kanban card of an opportunity to open it. Then, at the top-right, above the chatter composer, click Send message.

Suggerimento

Press **Ctrl + Enter** to send a message, instead of using the Send button.

If any followers have been added to the record, they are added as recipients of the message.

Avvertimento

Followers of a record are added as recipients of a message automatically. If a follower should **not** receive a message, they must be removed as a follower before the message is sent, or a note is logged.

### Expand full composer¶

The chatter composer can be expanded to a larger pop-up window, allowing for additional customizations.

To open the full composer, click the __(expand) icon in the bottom-right corner of the composer window.

The expand icon in a chatter composer.¶

Doing this opens a Compose Email pop-up window. Confirm or edit the intended Recipients of the message, or add additional recipients. The Subject field auto-populates based on the title of the record, though it can be edited, if desired.

To use an [email template](../../general/companies/email_template.html) for the message, select it from the drop-down menu in the Load template field.

Nota

The number and type of templates available vary, based on the record the message is created from.

Click __(paperclip) icon to add any files to the message, then click Send.

### Edit sent messages¶

Messages can be edited after they are sent, to fix typos, correct mistakes, or add missing information.

Nota

When messages are edited after they have been sent, an updated message is **not** sent to the recipient.

To edit a sent message, click the __(ellipsis) icon menu to the right of the message. Then, select Edit. Make any necessary adjustments to the message.

To save the changes, press **Ctrl + Enter**. To discard the changes, press **Escape**.

Importante

Users with Admin-level access rights can edit any sent messages. Users without Admin rights can **only** edit messages they created.

## Cerca messaggi¶

Chatter threads can become long after a while, because of all the information they contain. To make it easier to find a specific entry, users can search the text of messages and notes for specific keywords.

First, select a record with a chatter thread. For example, to search a _CRM_ opportunity, navigate to CRM app ‣ Sales ‣ My Pipeline, and click on the Kanban card of an opportunity to open it. Then, at the top-right, above the chatter composer, click the __(search) icon to open the search bar.

Enter a keyword or phrase into the search bar, then hit **Enter** , or click the __(search) icon to the right of the search bar. Any messages or notes containing the keyword or phrase entered are listed below the search bar, with the keyword highlighted.

To be taken directly to a particular message in the chatter thread, hover over the upper-right corner of the result to reveal a Jump button. Click this button to be directed to that message’s location in the thread.

Search results in a chatter thread. Hover over the upper-right corner of a result to see the **Jump** option. Click it to be taken directly to that message in the chatter thread.¶

## Pianifica attività¶

_Activities_ are follow-up tasks tied to a record in an Odoo database. Activities can be scheduled on any database page that contains a chatter thread, Kanban view, list view, or activities view of an application.

To schedule an activity through a chatter thread, click the Activities button, located at the top of the chatter on any record. On the Schedule Activity pop-up window that appears, select an Activity Type from the drop-down menu.

Suggerimento

Le singole applicazioni presentano un elenco di _Tipi di attività_ specifici. Ad esempio, per visualizzare e modificare le attività disponibili per l’applicazione _CRM_ vai sull’app CRM ‣ Configurazione ‣ Tipi di attività.

Inserisci un titolo per l’attività nel campo Riepilogo situato nella finestra pop-up Programma attività.

Select a name from the Assigned to drop-down menu to assign the activity to a different user. Otherwise, the user creating the activity is automatically assigned.

Add any additional information in the optional Log a note… field.

Nota

Il campo Scadenza presente nella finestra pop-up Programma attività viene riempito automaticamente in base alle impostazioni di configurazione del Tipo di attività selezionato. Tuttavia, la data può essere modificata selezionando un giorno sul calendario per il campo Scadenza.

Per concludere, fai clic su uno dei seguenti pulsanti:

  * Programma: aggiunge l’attività al chatter corrispondente ad Attività pianificate.

  * Segna come completata: aggiunge i dettagli dell’attività al chatter corrispondente a Oggi. L’attività non viene programmata ma viene contrassegnata automaticamente come completata.

  * Completata/Programma successiva: aggiunge l’attività a Oggi contrassegnata come completata e apre una nuova finestra attività.

  * Abbandona: elimina tutte le modifiche apportate alla finestra pop-up.




Scheduled activities are added to the chatter for the record under Planned activities, and are color-coded based on their due date.

  * **Red** icons indicate an overdue activity.

  * **Yellow** icons indicate an activity with a due date scheduled for the current date.

  * **Green** icons indicate an activity with a due date scheduled in the future.




Suggerimento

Click the __(info) icon next to a planned activity to see additional details.

After completing an activity, click Mark Done under the activity entry in the chatter. This opens a Mark Done pop-up window, where additional notes about the activity can be entered. After adding any comments to the pop-up window, click: Done & Schedule Next, Done, or Discard.

After the activity is marked complete, an entry with the activity type, title, and any other details that were included in the pop-up window are listed in the chatter.

## Allega file¶

Files can be added as attachments in the chatter, either to send with messages, or to include with a record.

Nota

After a file has been added to a chatter thread, it can be downloaded by any user with access to the thread. Click the __(paperclip) icon to make the files header visible, if necessary. Then, click the __(download) icon the file to download it.

To attach a file, click the __(paperclip) icon located at the top of the chatter composer of any record that contains a chatter thread.

This opens a file explorer pop-up window. Navigate to the desired file, select it, then click Open to add it to the record. Alternatively, files can be dragged and dropped directly onto a chatter thread.

After files have been added, they are listed in the chatter thread, under a Files heading.

Nota

After at least one file has been added to a chatter record, a new button labeled Attach files appears below the Files heading. To attach any additional files, this is the button that **must** be used, instead of the __(paperclip) icon at the top of the chatter thread.

After the Files section heading appears in the thread, clicking the __(paperclip) icon no longer opens a file explorer pop-up window. Instead, clicking the __(paperclip) icon toggles the Files section from visible to invisible in the chatter thread.

## Integrazioni¶

Beyond the standard features, additional integrations can be enabled to work with the chatter feature, specifically _WhatsApp_ and _Google Translate_.

Importante

Before the _WhatsApp_ and _Google Translate_ integrations can be used with the chatter, they **must** be configured. Step-by-step instructions on how to set-up each of these features can be found in the documentation below:

  * [WhatsApp](../whatsapp.html)

  * [Google Translate](../../general/integrations/google_translate.html)




### WhatsApp¶

_WhatsApp_ is an instant messaging and voice-over-IP app that allows users to send and receive messages, as well as share content.

Avvertimento

 _WhatsApp_ is an Odoo Enterprise-only application that does **not** work in the Odoo Community edition. To sign up for an Odoo Enterprise edition, click here: [Odoo Free Trial](https://www.odoo.com/trial).

After _WhatsApp_ has been configured and enabled within a database, a WhatsApp button is added above the chatter composer on any applicable record. If one or more approved _WhatsApp_ templates are found for that model, clicking this button opens a Send WhatsApp Message pop-up window.

Importante

 _WhatsApp_ templates **must** be approved before they can be used. See [WhatsApp templates](../whatsapp.html#productivity-whatsapp-templates) for more information.

### Google Traduttore¶

_Google Translate_ can be used to translate user-generated text in the Odoo chatter.

To enable _Google Translate_ on a database, an _API key_ must first [be created](../../general/integrations/google_translate.html) through the [Google API Console](https://console.developers.google.com/).

After creating the API key, navigate to the Settings app ‣ Discuss section and paste the key in the Message Translation field. Click Save to save the changes.

#### Translate a chatter message¶

To translate a user’s text from another language, click the __(ellipsis) menu to the right of the chatter. Then, select Translate. The content translates to the language set in the [user’s preferences](../../general/users/language.html).

Importante

L’utilizzo dell’API _Google Translate_ **richiede** un account di fatturazione [Google](https://myaccount.google.com/).

Vedi anche

  * [Discuss](../discuss.html)

  * [Discuss Channels](team_communication.html)

  * [Activities](../../essentials/activities.html)

  * [WhatsApp](../whatsapp.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/discuss/chatter.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../data_cleaning.html "Pulizia dati") |
  * [precedente](ice_servers.html "Configure ICE servers with Twilio") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Comunicazioni](../discuss.html) »
  * Chatter


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