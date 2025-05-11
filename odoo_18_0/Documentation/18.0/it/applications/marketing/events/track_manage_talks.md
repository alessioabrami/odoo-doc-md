# Talks, proposals, and agenda — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_templates.html "Event templates") |
  * [precedente](sell_tickets.html "Sell event tickets") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Talks, proposals, and agenda



# Talks, proposals, and agenda¶

With Odoo _Events_ , users can utilize a fully-integrated event website, where attendees can quickly access various tracks (talks, presentations, etc.), view entire agendas, and propose talks for the event.

## Event website¶

To access an event website, navigate to the specific event form in the Odoo _Events_ app, and click the Go to Website smart button. Or, while on the Odoo-built website for the company, click the Events header option, and select the desired event to view that event’s website.

On the event website, there is an event-specific subheader menu with different options to choose from.

With the _Schedule & Tracks_ setting enabled in the Odoo _Events_ app, the following links are automatically added to the subheader menu, located on the event website: Talks, Talk Proposals, and Agenda.

To enable the Schedule & Tracks setting, navigate to Events app ‣ Configuration ‣ Settings, tick the checkbox beside Schedule & Tracks, and click Save.

### Talks page¶

The Talks link takes the attendee to a page filled with all the planned tracks for the event.

At the top of Talks page, there are drop-down filter menus beside a Search a talk… search bar.

The first drop-down filter menu (with the starting title: Favorites) is the only drop-down filter menu that appears by default. When clicked, the resulting menu presents two options: Favorites and All Talks.

Selecting Favorites shows _only_ the tracks that have been favorited by the attendee.

Nota

If no tracks have been favorited, and the Favorites filter is selected, Odoo presents all the event tracks.

Selecting All Talks shows _all_ the tracks, regardless if they have been favorited or not.

The other drop-down filter menus that appear on this page are related to any configured tags (and tag categories) created for event tracks in the backend.

Suggerimento

To add tags and tag categories to track forms, open a desired event track form, and start typing a new tag in the Tags field. Then, click Create and edit… from the resulting drop-down menu.

Doing so reveals a Create Tags pop-up form.

From here, users see the recently added tag in the Tag Name field. Beneath that, there is an option to add a specific Color Index to the tag for added organization.

Lastly, there is the Category field, where users can either select a pre-existing category for this new tag, or create a new one.

All options in the Category field for tags appear as their own drop-down filter menu on the Talks page, located on the event website.

Beneath the drop-down filter menus at the top of the Talks page, there is a list of planned tracks for the specific event, organized by day.

If an attendee wishes to favorite a track, they can click the __(empty bell) icon, located to the right of the track title. Attendees will know a track has been favorited when they notice the icon has been changed to __(filled bell) icon.

Favoriting a track this way places it on the list of Favorites, which is accessible from the default drop-down filter menu, located at the top of the Talks page.

### Talk Proposals page¶

The Talk Proposals link takes attendees to a page on the event website, wherein they can formerly submit a proposal for a talk (track) for the event, via a custom online form.

In addition to the form, an introduction to the page, along with any other pertinent information related to the types of talks the event will feature can be added, if needed.

The talk proposal form can be modified in a number of different ways, via the web builder tools, accessible by clicking Edit while on the specific page.

Then, proceed to edit any of the default fields, or add new forms with the Form building block (located in the Blocks section of the web builder tools sidebar).

Once all the necessary information is entered into the form, the attendees just need to click the Submit Proposal button.

Then, that talk, and all the information entered on the form, can be accessed on the Event Tracks page for that specific event in the Proposal stage, which is accessible via the Tracks smart button on the event form.

At that point, an internal user can review the proposed talk, and choose to accept or deny the proposal.

If accepted, the internal user can then move the track to the next appropriate stage in the Kanban pipeline on the Event Tracks page for the event. Then, they can open that track form, and click the Go to Website smart button to reveal that track’s page on the event website.

From there, they can toggle the Unpublished switch in the header to Published, which allows all event attendees to view and access the talk.

### Agenda page¶

The Agenda link takes attendees to a page on the event website, showcasing an event calendar, depicting when (and where) events are taking place for that specific event.

Clicking any track on the calendar takes the attendee to that specific track’s detail page on the event website.

If an attendee wishes to favorite a track, they can click the __(empty bell) icon, located to the right of the track title. Attendees will know a track has been favorited when they notice the icon has been changed to __(filled bell) icon.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/events/track_manage_talks.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_templates.html "Event templates") |
  * [precedente](sell_tickets.html "Sell event tickets") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Talks, proposals, and agenda


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