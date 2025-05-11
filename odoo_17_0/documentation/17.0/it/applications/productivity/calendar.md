# Calendario — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](calendar/outlook.html "Outlook Calendar synchronization") |
  * [precedente](knowledge/properties.html "Proprietà") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Calendario



# Calendario¶

Odoo **Calendar** is a scheduling app that allows users to integrate a company’s business flow into a single management platform. By integrating with the other apps in Odoo’s ecosystem, **Calendar** allows users to schedule and organize meetings, schedule events, plan employee appraisals, coordinate projects, and more – all from the same platform.

Upon opening the Calendar app, users have an overview of their current meetings. The selected view option appears as a Day, Week, Month, or Year drop-down menu. Under the view options drop-down menu, users can also enable or disable Show weekends.

Suggerimento

Depending on the selected view option, users can click the ____(left or right arrow) buttons to switch between days, weeks, etc., and switch back to the current day with the Today button.

## Sync third-party calendars¶

Users can sync Odoo with existing [Outlook](calendar/outlook.html) and/or [Google](calendar/google.html) calendars, by heading to Calendar app ‣ Configuration ‣ Settings. From here, enter Client ID and Client Secret. There is also an option to pause synchronization by ticking the checkbox, or automating synchronization by keeping it blank.

Once the desired configurations are complete, be sure to click Save before moving on.

Events created in synced calendars automatically appear across the integrated platforms.

Vedi anche

  * [Synchronize Outlook calendar with Odoo](calendar/outlook.html)

  * [Synchronize Google calendar with Odoo](calendar/google.html)




## Create activities from chatter¶

Instantly create new meetings anywhere in Odoo through an individual record’s chatter, like in a **CRM** opportunity card or task in the **Projects** app.

From the chatter, click on the Activities button. In the Schedule Activity pop-up window, select the desired Activity Type, which populates a set of buttons, depending on the activity.

Activities that involve other schedules, like Meeting or Call for Demo, link to the **Calendar** app. Select one of these activities to link to the **Calendar** app, then hit Open Calendar to navigate back to the app. Alternatively, it is also possible to Schedule & Mark as Done to close out the activity, or select Done & Schedule Next to keep the Schedule Activity window open to create another.

Vedi anche

[Schedule activities in Odoo](../essentials/activities.html)

## Plan an event¶

To put an event on the calendar, open the Calendar app, and click into the target date. On the New Event pop-up window that appears, start by adding the event title.

The target date auto-populates in the Start field. This can be changed by clicking into the date section, and selecting a date from the calendar. For multi-day events, select the end date in the second field, then click Apply.

Tick the All Day checkbox if there is no specific start or end time.

For events with specific start and stop times, ensure the All Day checkbox is unticked to enable time selection. With the All Day checkbox unticked, time selections appear in the Start field.

The signed-in user auto-populates as the first attendee. Additional Attendees can be added or created from here, as well.

For virtual meetings, copy and paste the URL into the space provided in the Videocall URL field. Or, click __ Odoo meeting to create a link.

Next, either create the event by clicking Save & Close, or select More Options to further configure the event.

Suggerimento

Once the event is created, users can click into the virtual meeting directly from the calendar event to access more configuration options.

The Description field allows users to add additional information and details about the meeting.

Click More Options to navigate to the meeting form, which provides additional configurations for the event:

  * Duration: Define the length of the meeting in hours, or toggle the All Day switch.

  * Recurrent: Tick the checkbox to create a recurring meeting. Once selected, this opens new fields:

    * Timezone: Select the timezone for which this meeting time is specified.

    * Repeat: Select the recurring period of this meeting. Depending on what type of recurrence has been selected, a subsequent field appears, in which users can indicate when the meeting should recur. For example, if Monthly is selected as the Repeat option, a new field appears, in which the user decides on what Day of Month the meeting should recur.

    * Until: Select the limited Number of repetitions this meeting should recur, the End date of when the recurrences should stop, or if the meetings should recur Forever.

  * Tags: Add tags to the event, like `Customer Meeting` or `Internal Meeting`. These can be searched and filtered in the **Calendar** app when organizing multiple events.

  * Appointment: Link existing or new appointments. These can be configured through the Share Availabilities button from the main **Calendar** dashboard.

  * Privacy: Toggle between visibility options to control who can view the event.

  * Organizer: This is defaulted to the current Odoo user. Select a new one from existing users, or create and edit a new user.

  * Description: Add additional information or details about the meeting.

  * Reminders: Select notification options to send to attendees. Choose a default notification, or configure new reminders.




## Coordinate with teams” availability¶

When scheduling an event for multiple users, on the **Calendar** app dashboard, tick the checkbox next to Attendees to view team members” availability. Tick (or untick) the checkbox next to listed users to show (or hide) individual calendars.

## Condividi disponibilità¶

On the **Calendar** app main dashboard, click the Share Availabilities button at the top of the page. Next, click and drag to select the available times and dates on the calendar to add them as options in the invitation.

Suggerimento

To remove a selected time range, hover over the availability to click the __(trash) icon.

Nota

Within the Share Availabilities feature, selecting times is only possible on the _Day_ calendar views.

Once availability has been selected, click the __ Open button to navigate to the associated appointment.

Several configuration options are available on the appointment form:

In the Scheduling field, set a minimum hour window to ensure appointments are confirmed a specified amount of time in advance. For example, set `01:00` to require attendees to confirm at least one hour before their appointment time.

In the Allow Cancelling field, set a maximum hour window before the appointment that attendees are able to cancel.

The Availability on field enables attendees to book Users or Resources, such as meeting rooms or tables. After selecting Users or Resources, type in the desired user or resource in the space below.

The Front-End Display field is used to choose No Picture or Show Pictures related to the selected user or resource on the appointment page.

If Resources has been selected in the Availability on field, users have an option to Manage Capacities.

Tick the checkbox to limit the maximum amount of people that can use the resource at the same time.

The Assignment Method field enables the order in which attendees book their time and user/resource:

  * Pick User/Resource then Time

  * Select Time then User/Resource




If Resources has been selected in the Availability On field, a third option is available, Select Time then auto-assign.

Optionally, configure the following tabs:

  * Schedule tab

  * Options tab

  * Questions tab

  * Messages tab




Click the Preview button to see how the appointment link looks for attendees.

Once the configurations are finished, click the Share button to generate a link to send directly, or click Publish to publish the appointment selection on the connected Odoo website.

### Schedule tab¶

In the Schedule tab of the appointment form, time slots can be managed. The target date and time populate as the first time slots.

To add a new time slot, hit Add a line. Click into the new blank space under the From field, then select and enter the new target start date and time, respectively. Repeat under the new blank space under To to select and enter the new target end date and time.

### Options tab¶

The Options tab provides additional configurations:

  * Website: Specify which website this meeting invitation will be published on.

  * Timezone: This defaults to the company’s timezone selected in the **Settings** app. To change the timezone, select the desired option from the drop-down menu.

  * Location: Select or create new locations from the drop-down menu. If this field is left empty, the meeting is considered to be taking place online.

  * Videoconference Link: Select from Odoo Discuss or Google Meet to include a video conference link in the meeting invitation, or leave it blank to prevent generating a meeting URL.

  * Manual Confirmation: Only shown if Resources has been selected in the Availability On field. Tick the checkbox and enter a maximum percentage of the selected resource(s)” total capacity to create a manual confirmation requirement to finalize the meeting.

  * Up-front Payment: Tick the checkbox to require users to pay before confirming their booking. Once this is ticked, a link appears to __ Configure Payment Providers, which enables online payments.

  * Limit to Work Hours: If Users has been selected in the Availability On field, tick the checkbox to limit meeting time slots to the selected [users” working hours](../hr/employees/new_employee.html).

  * Create Opportunities: When this is selected, each scheduled appointment creates a new **CRM** opportunity.

  * Reminders: Add or delete notification reminders in this field. Select the blank space for additional options.

  * Confirmation Email: Tick the checkbox to automatically send a confirmation email to attendees once the meeting is confirmed. Select from the email templates or click Search More…, then New to create a custom template.

  * Cancelation Email: Tick the checkbox to automatically send a cancelation email to attendees if the meeting is canceled. Select from the email templates or click Search More…, then New to create a custom template.

  * CC to: Add contacts to be notified of meeting updates in this field, regardless if they attend the meeting.

  * Allow Guests: Tick the checkbox to allow attendees to invite guests.




### Questions tab¶

In the Questions tab, add questions for the attendee to answer when confirming their meeting. Click Add a line to configure a Question. Then select a Question Type, optionally add a Placeholder answer, and choose whether it is a Required Answer.

To learn how to create more comprehensive questionnaires, head to the **Survey** app documentation on [creating and configuring data-capturing questions](../marketing/surveys/questions.html).

### Messages tab¶

In the Introduction Message field of the Messages tab, add additional meeting information that appears on the invitation.

Information added to the Extra Message on Confirmation field appears once the meeting is confirmed.

  * [Outlook Calendar synchronization](calendar/outlook.html)
  * [Google Calendar synchronization](calendar/google.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/calendar.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](calendar/outlook.html "Outlook Calendar synchronization") |
  * [precedente](knowledge/properties.html "Proprietà") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Calendario


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
  *[MRR]: Monthly Recurring Revenue
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
  *[URL]: Uniform Resource Locators
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