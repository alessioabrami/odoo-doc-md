# Create events — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sell_tickets.html "Sell event tickets") |
  * [precedente](../events.html "Eventi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Create events



# Create events¶

With the _Events_ application, event organizers can create and configure in-person or online-only events in Odoo. Each new event contains a number of customizable options that are geared around specific event logistics, as needed per event, such as ticket sales and registration desk, booths, tracks, sponsors, rooms, and more.

Events can be manually created from scratch or built off of pre-made templates. Once launched, the _Events_ application then integrates with the _Website_ app for the front-end promotion and registration of the event for attendees, the _Sales_ app for the purchasing ability of paid tickets, as well the _CRM_ application through customizable lead generation rules.

## New event¶

To create a new event, begin by navigating to the Events app to land on the default Events dashboard, in the __ Kanban view. From there, or alternatively from the __ List or __ Gantt views, click the New button in the upper-left corner of the dashboard to open up a new event form.

Nota

If certain fields do not readily appear on the event form, that means an additional application needs to be installed, or the database is not operating in a multi-company environment.

For example, the Twitter Wall field **only** appears if the _Social Marketing_ app is installed, and the Company field **only** appears if the database is working in a multi-company environment.

These are just _additional_ elements that can be used for an event. They are **not** required to create, host, and manage an event with Odoo _Events_.

## Event form¶

At the top of the event form are a series of smart buttons related to various event metrics, which will autopopulate with pertinent data once attendees begin to register, booths and sponsors sign on for the event, the event takes place, and so on.

Primarily, these smart buttons are used as logistical portals to perform specific actions for the event. The numeric displays are primarily for quick reference points.

While those visual metrics are useful, they can still be clicked, and used to navigate to specific event-related pages to modify and/or perform any desired actions.

Beneath the smart buttons is the event form, which contains various fields and clickable tabs that serve to configure the initial, necessary details of the event.

The following are fields found on an event form:

  * Event Name: the title of the event. This field is **required**.

Nota

To the right of the entered Event Name, there is a language tooltip, represented by an abbreviated language indicator (e.g. `EN`). When clicked, a Translate: name pop-up window appears, displaying various pre-configured language translation options available in the database.

  * Date: when the event is scheduled to take place (expressed in your local timezone). This field is auto-populated, but modifiable, and is **required**.

  * Display Timezone: the timezone in which the event dates/times will be displayed on the website. This field is auto-populated, but modifiable, and is **required**.

  * Language: designate a specific language for all event communications to be translated into, if necessary. This field is blank, by default, so if event-related communications are being sent to recipients who speak a different language, be sure to configure this field properly.

  * Twitter Wall: creates a separate page on the event website to feature specific social posts on X (formerly Twitter) that contain pre-determined desired elements.

Suggerimento

To create and customize a Twitter Wall, type the name of the desired wall into the field, and select Create and edit… from the resulting drop-down menu.

Doing so reveals Create Twitter Wall pop-up window.

From this window, enter a Wall Name. Then, select a certain word or hashtag for Odoo to search for on X, like `#WoodWorkingExpo24`, for example.

Next, determine the Type of tweets Odoo should showcase with that predetermined criteria. The choices in this field are: Recent, Popular, or Mixed.

Users also have the option to add a brief Description to the wall, as well.

Lastly, the greyed-out, non-modifiable Website URL field will autopopulate with the full URL needed to access the document through the event website.

An image can also be added to the wall by clicking the __(pencil) icon that appears when the cursor hovers over the (camera) placeholder image in the upper-right corner of the pop-up window.

Then, from the resulting file explorer window, select the desired image to be added to the wall.

This Twitter Wall field **only** appears on the event form if the _Social Marketing_ app is installed, and an X account has been added as a stream on the application. To learn more, check out the [Social Marketing](../social_marketing.html) documentation.

  * Template: choose a pre-configured event template from the resulting drop-down menu.

Or, create a new one directly from this field, by typing in the name of the new template, and selecting either:

    * Create (which creates the template, and can be edited later) or

    * Create and edit… (which creates the template, and reveals a separate template page to configure the template in greater detail).

  * Tags: add any corresponding tags to briefly describe the event (e.g. `Online`, `Conference`, etc.). Multiple tags can be added per event.

Suggerimento

Tags can be displayed on events that are listed on the website by enabling the _Show on Website_ checkbox from Events app ‣ Configuration ‣ Event Tag Categories.

  * Organizer: designate the organizer of the event (a company, contact, or employee).

  * Responsible: designate a user in the database to be responsible for this event.

  * Company: designate which company in the database to which this event is related. This field **only** appears if working in a multi-company environment. This field is auto-populated, but modifiable, and is **required**.

  * Website: choose to restrict the publishing of this event to a specific website created in Odoo. If this field is left blank, the event can be published on _all_ websites in the database. To learn more, refer to the [Multiple websites](../../websites/website/configuration/multi_website.html) documentation.

  * Venue: enter event venue details. This field pulls pertinent information from the _Contacts_ application. Alternatively, Venue information can be manually added in this field, as well. At the very least, there **must** be a venue name, address, city, zip code/region, and country entered.

  * Exhibition Map: if desired, click the Upload your file button to upload an image of the event venue map.

  * Limit Registrations: if this checkbox is ticked, a limit to the amount of registrations is added to the event, and that desired limit amount **must** be entered in the blank field before Attendees.

  * Badge Dimension: select a desired paper format dimension for event badges. The options are: A4 foldable, A6, or 4 per sheet.

  * Badge Background: if desired, click the Upload your file button to upload a custom background image for event badges.




When the above fields in the event form have been adequately filled in, move on to the four tabs at the bottom of the event form for further customization.

Those tabs are: Tickets, Communication, Questions, and Notes.

### Tickets tab¶

Create custom tickets (and ticket tiers) for events in the Tickets tab of an event form.

To create a ticket, click Add a line in the Tickets tab. Then, enter a name for the ticket (e.g. `Basic Ticket` or `VIP`) in the Name field.

In the Product field, either select the pre-configured Event Registration product, or create a new one by typing in the name of the new event registration product, and then select either Create or Create and edit… from the resulting drop-down menu.

Importante

Upon installing Odoo _Events_ , a new product type, _Event Ticket_ , becomes available on product forms (Sales ‣ Products ‣ Products). In order for an event registration product to be selectable in the _Tickets_ tab, the event registration Product Type **must** be set to Event Ticket.

Suggerimento

Existing event registration products can be modified directly from this field, as well, by clicking the __(right arrow) icon, located beside the event registration product. Doing so reveals that product’s form. If the _Inventory_ application is installed, additional choices are available to customize for the product.

Next, set the registration cost of the ticket in the Price field.

Nota

The _Sales Price_ defined on the event registration product’s product form sets the default cost of a ticket. Modifying the Price of a ticket in the Tickets tab, sets a new registration cost of the ticket for that event.

Next, determine a Sales Start and Sales End date in their respective fields. To do that, click into the blank field to reveal a calendar popover. From there, select the desired date and time, then click __ Apply.

Then, if desired, designate a Maximum amount of that specific ticket that can be sold.

The Taken column populates with the number of tickets that are sold.

Optionally, in the Color column, add a custom color to differentiate ticket badges. The selected color displays on ticket badges when printed.

To delete any tickets from the Tickets tab, click the __(trash can) icon on the corresponding line for the ticket that should be deleted.

Suggerimento

To add an optional Description column to the Tickets tab, click the __(additional options) drop-down menu, located to the far-right of the column titles.

Then, tick the checkbox beside Description from the resulting drop-down menu.

When added, the option to add brief descriptions for each event ticket appears, which can be used to inform attendees of any perks or amenities that may coincide with specific ticket purchases.

### Communication tab¶

In the Communication tab of an event form, create various marketing communications that can be scheduled to be sent at specific intervals leading up to, and following, the event.

Nota

By default, Odoo provides three separate pre-configured communications on every new event form. One is an email sent after each registration to confirm the purchase with the attendee. The other two are email event reminders that are scheduled to be sent at different time intervals leading up to the event to remind the recipient of the upcoming event.

To add a communication in the Communication tab, click Add a line. Then, select the desired type of communication in the Send field. The options are: Mail, SMS, Social Post, or WhatsApp.

There is no limit to the number of communications that can be added in the Communication tab of an event form.

To delete a communication from the Communication tab, click the __(trash can) icon on the corresponding communication line. Doing so removes the communication from the event entirely.

Importante

The Social Post option **only** appears if the _Social Marketing_ application is installed. The WhatsApp option **only** appears if the _WhatsApp Integration_ module is installed.

[WhatsApp](../../productivity/whatsapp.html) templates **cannot** be edited during active configuration. A separate approval from _Meta_ is required.

#### E-mail¶

Select an existing email template from the Template drop-down menu.

Next, define the Interval, Unit, and Trigger from their respective drop-down fields, letting Odoo know when the communication should be sent.

The Unit options are: Immediately, Hours, Days, Weeks, and Months.

Then, select an option from the Trigger drop-down menu. The options are: After each registration, Before the event, and After the event.

The Sent column populates with the number of sent communications. And, beside the number are different icons that appear, depending on the status of that particular communication.

The status of _Running_ is represented by a __(three gears) icon. The status of _Sent_ is represented by a __(checkmark) icon. And, the status of _Scheduled_ is represented by an __(hourglass) icon.

Example

To send a confirmation email an hour after an attendee registers for an event, configure the following communication:

  * Interval: `1`

  * Unit: Hours

  * Trigger: After each registration




Nota

Existing email templates can be modified directly from the Template drop-down menu, if necessary, by clicking the __(right arrow) icon next to the template name. Doing so reveals a separate page where users can edit the Content, Email Configuration, and Settings of that particular email template.

To view and manage all email templates, activate [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html#developer-mode) and navigate to Settings ‣ Technical ‣ Email: Email Templates. Modify with caution as email templates effect all communications where the template is used.

### Questions tab¶

In the Questions tab of an event form, users can create brief questionnaires for registrants to interact with, and respond to, after they register for the event.

These questions can be focused on gathering basic information about the attendee, learning about their preferences, expectations, and other things of that nature. This information can also be used to create more detailed reporting metrics, in addition to being utilized to create specific lead generation rules.

Nota

By default, Odoo provides three questions in the Questions tab for every event form. The default questions require the registrant(s) to provide their Name and Email, and make it optional to include their Phone number, as well.

The information gathered from the Questions tab can be found on the Attendees dashboard, accessible via the __ Attendees smart button. Odoo populates individual records that contain basic information about the registrant(s), as well as their preferences.

To add a question in the Questions tab, click Add a line. Doing so reveals a Create Question pop-up window. From here, users can create and configure their question.

First, enter the question in the field at the top of the form. Then, decide if the question should require a Mandatory Answer and/or if Odoo should Ask once per order, by ticking their respective boxes, if desired.

If the Ask once per order checkbox is ticked, the question will only be asked once, and its value is propogated to every attendee in the order (if multiple tickets are purchased at once). If the checkbox is _not_ ticked for this setting, Odoo will present the question for every attendee that is connected to that registration.

Next, select a Question Type option:

  * Selection: provide answer options to the question for registrants to choose from. Selectable answer options can be managed in the Answers column at the bottom of the pop-up window.

  * Text Input: lets the users enter a custom response to the question in a text field.

  * Name: provides registrants with a field for them to enter their name.

  * Email: provides registrants with a field for them to enter their email address.

  * Phone: provides registrants with a field for them to enter their phone number.

  * Company: provides registrants with a field for them to enter a company they are associated with.




Once all the desired configurations have been entered, either click Save & Close to save the question, and return to the Questions tab on the event form, or click Save & New to save the question and immediately create a new question on a new Create Question pop-up window.

As questions are added to the Questions tab, the informative columns showcase the configurations of each question.

The informative columns are the following:

  * Title

  * Mandatory

  * Once per Order

  * Type

  * Answers (if applicable)




For Selection and Text Input types, a __ Stats button appears on the right side of the question line. When clicked, Odoo reveals a separate page, showcasing the response metrics to that specific question.

To delete any question from the Questions tab, click the __(trash can) icon on the corresponding question line.

There is no limit to the number of questions that can be added in the Questions tab of an event form.

### Scheda Note¶

In the Notes tab of an event form, users can leave detailed internal notes and/or event-related instructions/information for attendees.

In the Note field of the Notes tab, users can leave internal notes for other event employees, like «to-do» lists, contact information, instructions, and so on.

In the Ticket Instructions field of the Notes tab, users can leave specific instructions for people attending the event that appear on the attendees ticket.

## Publish events¶

Once all configurations and modifications are complete on the event form, it is time to publish the event on the website. Doing so makes the event visible to website visitors, and makes it possible for people to register for the event.

To publish an event after all the customizations are complete, click the __ Go to Website smart button at the top of the event form. Doing so reveals the event’s web page, which can be customized like any other web page on the site, via the Edit button.

To learn more about website design functionality and options, consult the [Building block](../../websites/website/web_design/building_blocks.html) documentation.

Once the event website is ready to be shared, click the red Unpublished toggle switch in the header menu, changing it to a green Published switch. At this point, the event web page is published, and viewable/accessible by all website visitors.

## Send event invites¶

To send event invites to potential attendees, navigate to the desired event form, via Events app ‣ Events, and click into the desired event. Following this, click the Invite button in the upper-left corner of the event form.

Doing so reveals a blank email form to fill out, as desired. To learn more about how to create and customize emails like this, refer to the [Create an email](../email_marketing.html#email-marketing-create-email) documentation.

Proceed to create and customize an email message to send as an invite to potential attendees. Remember to include a link to the registration page on the event website, allowing interested recipients to quickly register.

Suggerimento

Sending emails from Odoo is subject to a daily limit, which, by default, is 200. To learn more about daily limits, visit the [Limite giornaliero raggiunto](../../general/email_communication/faq.html#email-issues-outgoing-delivery-failure-messages-limit) documentation.

Vedi anche

[Talks, proposals, and agenda](track_manage_talks.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/events/create_events.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sell_tickets.html "Sell event tickets") |
  * [precedente](../events.html "Eventi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Create events


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