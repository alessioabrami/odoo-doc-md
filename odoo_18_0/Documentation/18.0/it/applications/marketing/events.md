# Eventi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](events/create_events.html "Create events") |
  * [precedente](sms_marketing/pricing_and_faq.html "SMS Pricing and FAQ") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Eventi



# Eventi¶

Explore the various aspects of the Odoo **Events** detailed dashboard, and useful settings, that can be utilized to generate and gather valuable data about events (and their attendees), which can then be used to improve decision-making and event-planning.

Vedi anche

[Odoo Tutorials: Events](https://www.odoo.com/slides/surveys-63)

#### [Create eventsDiscover how to create events with Odoo. ](events/create_events.html)#### [Sell event ticketsLearn how to create, configure, and sell event tickets. ](events/sell_tickets.html)#### [Track and manage talksSee how to create, track, and manage event tracks with Odoo. ](events/track_manage_talks.html)#### [Event templatesExpedite the event-creation process with event templates. ](events/event_templates.html)#### [Event tracksLearn how to create, track, and manage event tracks with Odoo. ](events/event_tracks.html)#### [Event boothsCreate, manage, and sell event booths. ](events/event_booths.html)#### [Registration DeskInstantly grant access to event attendees with Odoo’s Registration Desk feature. ](events/registration_desk.html)#### [Revenues reportAnalyze the financial success of events with Odoo. ](events/revenues_report.html)

## Events dashboard¶

When the **Events** application is opened, Odoo reveals the main Events dashboard, which can be viewed in a number of different ways. Those different view options are accessible from the Events dashboard in the upper-right corner, via a series of view-related icon buttons.

By default, the Events dashboard is displayed in the __ Kanban view, which is populated with a variety of pipeline stages.

This view showcases all the events in the database in their respective stages. By default, the stages are: New, Booked, Announced, Ended, and Cancelled.

Nota

The Ended and Cancelled stages are folded, by default, and located to the right of the other stages.

On each event card, find the scheduled date of the event, the name of the event, the location, the number of expected Attendees, any scheduled activities related to the event, the status of the event, and the person responsible for the event.

To quickly add a new event to a pipeline, click the __(plus) icon at the top of the stage to which the event should be added to reveal a blank Kanban card to fill out.

In this blank Kanban card, enter the name of Event, along with the start and end Date and time.

Then, either click Add to add it to the stage and edit it later, or click Edit to add the event to stage and edit its configurations on a separate page.

Each event card can be dragged-and-dropped into any stage on the Kanban pipeline, providing easy organizational access.

## Impostazioni¶

To access the event settings and feature options in Odoo **Events** , navigate to Events app ‣ Configuration ‣ Settings. From here, tick the checkboxes beside the desired settings and/or features, and click Save to activate them.

### Events section¶

In the Events section of the Settings page, there are selectable features that can be enabled to add various elements to events created with the Odoo **Events** application.

The Schedule & Tracks feature allows users to manage and publish a schedule with tracks for events. _Tracks_ is a catch-all term that refers to talks, lectures, demonstrations, presentations, and other similar elements that users may choose to include as part of an event.

When the Schedule & Tracks feature is enabled, two additional fields appear beneath it: Live Broadcast and Event Gamification.

The Live Broadcast feature lets users air tracks online, via a _YouTube_ integration.

The Event Gamification feature lets users share a quiz after any event track, in order for attendees to gauge how much they learned from the track they just saw/heard. Companies can also benefit from this feature, in that the subsequent responses and results of the quizzes can help determine where a company’s strengths and weaknesses are, when it comes to their presentations.

Next, is the Online Exhibitors feature. This feature allows users to display sponsors and exhibitors on event pages, which can serve as a valuable incentive to encourage partners and businesses to participate in the event.

The Jitsi Server Domain field represents an external conferencing service that is integrated with Odoo. It is what is used to create and host virtual conferences, community rooms, and other similar elements for events.

The Community Chat Rooms feature allows users to create virtual conference rooms for event attendees, providing them with a centralized place to meet and discuss anything related to the event.

Lastly, there is the Booth Management feature. This feature provides users with the ability to create and manage event booths and booth reservations. When enabled, users can create different booth tiers, with individual price points, and sell them to interested parties.

### Registration section¶

The Registration section of the Settings page provides selectable settings that are directly related to event registration.

The Tickets setting allows users to sell event tickets, via standard sales orders.

The Online Ticketing setting creates a selectable _Event Ticket_ product type on product forms, which provides users with the ability to sell event tickets online, via their website/eCommerce store.

### Attendance section¶

In the Attendance section of the Settings page, there is a selectable setting that is directly related to how attendees can attend/enter the event.

The Use Event Barcode setting, when activated, enables barcode (and QR code) scanning for attendees to enter the event. This provides attendees with quick access, and helps Odoo users easily track, manage, and analyze all event attendees.

The Barcode Nomenclature field, beneath the Use Event Barcode setting, is set to Default Nomenclature, by default, but can be changed at any time.

## Create events¶

With Odoo **Events** , events can be manually created from scratch or built off of pre-made templates.

Once launched, the **Events** application then integrates with the **Website** app for the front-end promotion and registration of the event for attendees, the **Sales** app for the purchasing ability of paid tickets, and the **CRM** application through customizable lead generation rules.

Vedi anche

[Create events](events/create_events.html)

## Sell event tickets¶

Create custom ticket tiers (with various price points) for potential event attendees to choose from, directly on the event template form, under the _Tickets_ tab.

Odoo simplifies the ticket-purchasing process by providing plenty of payment method options, as well.

Vedi anche

[Sell event tickets](events/sell_tickets.html)

## Track and manage talks¶

Discover how to access various event tracks (talks, presentations, etc.), view entire agendas, and learn how attendees can propose talks for the event.

Vedi anche

[Talks, proposals, and agenda](events/track_manage_talks.html)

## Event templates¶

Learn the process to customize and configure event templates, which can be used to expedite the event-creation process.

Vedi anche

[Event templates](events/event_templates.html)

## Event booths¶

Explore the various ways to create, manage, and sell event booths with the Odoo **Events** application.

Vedi anche

[Event booths](events/event_booths.html)

## Event tracks¶

Find out how to create, manage, and schedule different experiences (aka _Tracks_) for events with Odoo.

Vedi anche

[Event tracks](events/event_tracks.html)

## Registration desk¶

Grant access to event attendees quickly and easily with the Odoo **Events** _Registration Desk_ feature.

Vedi anche

[Banco registrazioni](events/registration_desk.html)

## Revenues report¶

Gain invaluable insight into event-related revenues with customizable reports and metrics.

Vedi anche

[Revenues report](events/revenues_report.html)

  * Create events
    * [New event](events/create_events.html#new-event)
    * Event form
      * [Tickets tab](events/create_events.html#tickets-tab)
      * Communication tab
        * [E-mail](events/create_events.html#mail)
      * [Questions tab](events/create_events.html#questions-tab)
      * [Scheda Note](events/create_events.html#notes-tab)
    * [Publish events](events/create_events.html#publish-events)
    * [Send event invites](events/create_events.html#send-event-invites)
  * Sell event tickets
    * [Configurazione](events/sell_tickets.html#configuration)
    * [Sell event tickets with the Sales app](events/sell_tickets.html#sell-event-tickets-with-the-sales-app)
    * [Sell event tickets through the Website app](events/sell_tickets.html#sell-event-tickets-through-the-website-app)
  * Talks, proposals, and agenda
    * Event website
      * [Talks page](events/track_manage_talks.html#talks-page)
      * [Talk Proposals page](events/track_manage_talks.html#talk-proposals-page)
      * [Agenda page](events/track_manage_talks.html#agenda-page)
  * Event templates
    * [Event templates page](events/event_templates.html#event-templates-page)
    * Create event template
      * Event template form
        * [Booths tab](events/event_templates.html#booths-tab)
    * [Use event templates](events/event_templates.html#use-event-templates)
  * Event booths
    * [Configurazione](events/event_booths.html#configuration)
    * Booth categories
      * [Create booth category](events/event_booths.html#create-booth-category)
    * Add booth to an event
      * [Booth form](events/event_booths.html#booth-form)
    * [Sell event booths](events/event_booths.html#sell-event-booths)
  * Event tracks
    * [Configurazione](events/event_tracks.html#configuration)
    * Event Tracks page
      * Create event track
        * Speaker tab
          * [Contact Details section](events/event_tracks.html#contact-details-section)
          * [Speaker Bio section](events/event_tracks.html#speaker-bio-section)
        * [Description tab](events/event_tracks.html#description-tab)
        * [Interactivity tab](events/event_tracks.html#interactivity-tab)
        * [Add Quiz button](events/event_tracks.html#add-quiz-button)
    * [Publish event track](events/event_tracks.html#publish-event-track)
  * Banco registrazioni
    * [Registration Desk page](events/registration_desk.html#registration-desk-page)
    * [Scansiona un badge](events/registration_desk.html#scan-a-badge)
    * [Select attendee](events/registration_desk.html#select-attendee)
  * Revenues report
    * Revenues reporting page
      * [Misure](events/revenues_report.html#measures)
      * Filters and grouping options
        * [Filter options](events/revenues_report.html#filter-options)
        * [Group By options](events/revenues_report.html#group-by-options)
    * [Sample report: event ticket analysis (graph)](events/revenues_report.html#sample-report-event-ticket-analysis-graph)
    * [Sample report: event type analysis (pivot table)](events/revenues_report.html#sample-report-event-type-analysis-pivot-table)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/events.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](events/create_events.html "Create events") |
  * [precedente](sms_marketing/pricing_and_faq.html "SMS Pricing and FAQ") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Eventi


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
  *[CTR]: click-through rate
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