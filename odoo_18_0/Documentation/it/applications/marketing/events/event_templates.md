# Event templates — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_booths.html "Event booths") |
  * [precedente](track_manage_talks.html "Talks, proposals, and agenda") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event templates



# Event templates¶

The Odoo _Events_ application provides the ability to customize and configure event templates, which can be used to expedite the event-creation process.

These templates can be created and personalized in the application, and then selected from an event form, in order to quickly apply a series of settings and elements to the new event, all of which can be further modified, if needed.

## Event templates page¶

In the Odoo _Events_ application, event templates can quickly be created and modified.

To begin, navigate to Events app ‣ Configuration ‣ Event Templates. Doing so reveals the Event Templates page. Here, find all the existing event templates in the database.

By default, Odoo provides three pre-configured event templates: Exhibition, Training, and Sport, which all have their own unique customizations applied to them.

To change how these event templates appear on the _Template_ drop-down field on an event form, drag-and-drop them into any desired order, using the __(draggable) icon, located to the left of each event template line on the Event Templates page.

Vedi anche

To learn more about event forms, refer to the [Create events](create_events.html) documentation.

## Create event template¶

There are two ways to create and configure an event template in Odoo _Events_.

  1. **On the dashboard** , by navigating to Events app ‣ Configuration ‣ Event Templates and clicking the New button in the upper-left corner. Doing so reveals a blank event template form that can be customized in a number of different ways.

  2. **On an event form itself**. Start by typing the name of a new event template in the _Template_ field, and click Create and edit… from the resulting drop-down menu. Doing so reveals a _Create Template_ pop-up window, featuring all the same configurable fields and elements found on a standard event template form.




Nota

Clicking Create «[template name]» from the resulting drop-down menu, via the _Template_ field on an event form creates the event template in the database, but does **not** present the user with the _Create Template_ pop-up window.

The event template would have to be modified, by selecting it on the _Event Templates_ page (Events app ‣ Configuration ‣ Event Templates).

### Event template form¶

All the fields on a standard Event Template form are _also_ on the _Create Template_ pop-up window, accessible via the _Template_ field on an event form.

Start by providing the event template with a name in the Event Template field, located at the top of the form.

Beneath that field, there is a series of selectable checkboxes, all of which are related to how the event menu will be displayed on the event web page.

  * Website Submenu: enables a submenu on the event’s website. When this checkbox is ticked, every other checkbox in this series is automatically ticked, as well. Then, choose to untick (deselect) any of the checkbox options, as desired.

  * Tracks Menu Item: adds a submenu item to navigate to a page displaying all planned tracks for the event.

  * Track Proposals Menu Item: adds a submenu item to navigate to a page, in which visitors can fill out a form to propose a track (talk, lecture, presentation, etc.) to happen during the event.

  * Booth Menu Item: adds a submenu item that takes visitors to a separate page, where an event booth can be purchased. Event booths can be customized and configured in the Booths tab of the event template form, from the _Booth Categories_ page (Events app ‣ Configuration ‣ Booth Categories).

Importante

First, users **must** create a booth product with the required _Event Booth_ option set as the Product Type on the product form.

  * Exhibitors Menu Item: adds a submenu item that takes visitors to a separate page, showcasing all the exhibitors related to that specific event. Icons representing those exhibitors are also found on the footer of every event-specific web page, as well.

  * Community: adds a submenu item allowing attendees to access pre-configured virtual community rooms to meet with other attendees, and discuss various topics related to the event. When this checkbox is ticked, the Allow Room Creation feature becomes available.

  * Allow Room Creation: allow visitors to create community rooms of their own.

  * Register Button: adds a button at the end of the event submenu that takes visitors to the event-specific registration page when clicked.




Once the desired checkboxes have been ticked, select an appropriate Timezone for the event from the available drop-down menu.

Then, for organizational purposes, there is the option to add Tags to this event template.

There is also the option to Limit Registrations to this specific event template by ticking that checkbox. If ticked, proceed to enter the number of Attendees this template should be limited to.

Beneath those general information fields at the top of the event template form, there are five tabs:

  * [Tickets](create_events.html#events-event-tickets)

  * [Communication](create_events.html#events-event-communication)

  * Booths

  * [Questions](create_events.html#events-event-questions)

  * [Notes](create_events.html#events-event-notes)




#### Booths tab¶

The Booths tab on an event template form is the only tab that differentiates itself from a standard event form, where the other tabs (Tickets, Communication, Questions, and Notes) are present and configured using the same process. For more information about those tabs, refer to the [Create events](create_events.html) documentation.

Importante

To create a booth or booth category, an event booth product **must** be created in the database first, with the _Product Type_ set to _Event Booth_. **Only** products with that specific configuration can be selected in the required _Product_ field of a booth or booth category form.

Nota

Event booths can be created and customized in two ways in the Odoo _Events_ application. Either in the Booths tab of an event template form, or by navigating to Events app ‣ Configuration ‣ Booth Categories, and click New.

To add a booth from the Booths tab of an event template form, click Add a line. Doing so reveals a blank Create Booths pop-up window.

Start by providing a Name for this booth in the corresponding field at the top of the pop-up window.

Then, select an appropriate Booth Category from the drop-down field below. Booth categories can be created and modified from the _Booth Categories_ page in the _Events_ application, which is accessible by navigating to Events app ‣ Configuration ‣ Booth Categories.

Suggerimento

A Booth Category can be created directly from this field on the Create Booths pop-up window. To accomplish that, type the name of the new booth category in the Booth Category field, and select either Create or Create and edit… from the resulting drop-down menu.

Clicking Create merely creates the category, which can (and should be) customized at a later date. Clicking Create and edit… reveals a new Create Booth Category pop-up window, from which the category can be configured in a number of different ways.

From this pop-up window, proceed to name the Booth Category, modify its Booth Details settings, configure its Sponsorship options (if applicable), and leave an optional Description to explain any pertinent details related to this specific category of booths.

There is also the option to add a photo/visual representation of the booth category, via the (camera) icon in the upper-right corner.

When all desired configurations are complete, click the Save & Close button.

The same configurations and options are available by navigating to Events app ‣ Configuration ‣ Booth Categories, and clicking New.

Once the desired Booth Category is selected, the remaining fields on the Create Booths pop-up window (Currency, Product, and Price) autopopulate, based on information configured for that selected Booth Category.

Nota

These fields **cannot** be modified from the Create Booths pop-up window. They can only be modified from the specific booth category form page.

When all desired configurations are complete, click Save & Close to save the booth, and return to the event template form. Or, click Save & New to save the booth, and start creating another booth on a fresh Create Booths pop-up window. Click Discard to remove all changes, and return to the event template form.

Once the booth has been saved, it appears in the Booths tab on the event template form.

## Use event templates¶

Once an event template is complete, it is accessible on all event forms in the Odoo _Events_ application.

To use an event template, navigate to the Events app and click New to open a new event form.

From the event form, click the Template field to reveal all the existing event templates in the database. They appear in the same order as they are listed in on the _Event Templates_ page (Events app ‣ Configuration ‣ Event Templates).

Select the desired event template from the Template drop-down field on the event form. Pre-configured settings automatically populate the event form, saving time during the event creation process.

Any of these pre-configured settings related to the selected event template chosen in the Template field on an event form can be modified, as desired.

Vedi anche

[Create events](create_events.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/events/event_templates.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_booths.html "Event booths") |
  * [precedente](track_manage_talks.html "Talks, proposals, and agenda") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event templates


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