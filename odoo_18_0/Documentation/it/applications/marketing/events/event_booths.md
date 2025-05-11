# Event booths — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_tracks.html "Event tracks") |
  * [precedente](event_templates.html "Event templates") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event booths



# Event booths¶

The Odoo _Events_ application provides users with the ability to create event booths, sell their availability, and manage their reservations.

## Configurazione¶

In order to create, sell, and manage booths for events, the _Booth Management_ feature must be activated.

To do that, navigate to Events app ‣ Configuration ‣ Settings, and tick the Booth Management checkbox. Then, click Save.

Importante

When the Booth Management setting is activated, a new [Product Type](../../inventory_and_mrp/inventory/product_management/configure/type.html) becomes available on all product forms: _Event Booth_.

This is important because every created booth **must** be assigned a _Booth Category_ on their respective booth form, and every booth category **must** have an _Event Booth_ product assigned to it.

## Booth categories¶

With the _Booth Management_ setting activated in the _Events_ app, the _Booth Categories_ option appears in the Configuration menu.

To access the Booth Category dashboard, go to Events app ‣ Configuration ‣ Booth Categories, which reveals a list of all created booth categories.

On the Booth Category page, the following information for each booth category is listed:

  * Name: the name of the booth category.

  * Create Sponsor: if checked, booking this booth category creates a sponsor for the user.

  * Product: the _Event Booth_ product associated with that specific booth category.

  * Price: the price of a booth in that booth category.




When the __(settings) icon, located to the far-right of the column titles, is clicked, a drop-down menu of additional column options appears. From the resulting drop-down menu, tick the checkbox beside Sponsor Level and/or Sponsor Type to reveal those columns on the Booth Category page.

To edit an existing booth category, select it from the list, and proceed to make any desired modifications from the event category form.

### Create booth category¶

To create a booth category from the Booth Category page, click the New button in the upper-left corner to reveal a blank booth category form.

Start by entering a name for the booth category in the top Booth Category field. This is a **requried** field.

To add a corresponding image to the booth category (e.g. a sample photo of how the booth looks), click the __(pencil) icon that appears when the cursor hovers over the camera placeholder in the upper-right corner of the booth category form. When clicked, proceed to upload the desired image to the booth category form, if needed.

In the Booth Details section, users **must** assign a Product to the category, and it **must** have _Event Booth_ set as the _Product Type_ on the product form.

And, regardless of the listed price on the _Event Booth_ product chosen, the user can input a custom Price to be applied for this booth category in the field below.

In the Sponsorship section, there is a Create Sponsor checkbox option. With that checkbox ticked, whenever a booth belonging to this category is booked, the user is created as an official _Sponsor_ of the event.

When the Create Sponsor checkbox is ticked, two additional fields appear beneath it: Sponsor Level and Sponsor Type.

Nota

Sponsor Level and Sponsor Type are purely to distinguish different distinctions of sponsors. For example, if a sponsor has been attached to a company for multiple years, they would be granted a higher level (e.g. _Gold_ level), which provides them with immediate credability and status. Whereas, conversely, a relatively new sponsor would be granted a lower level (e.g. _Bronze_ level), which coincides with its own credability and status.

Select a desired level of sponsorship from the Sponsor Level drop-down field.

Suggerimento

To modify any existing Sponsor Level, select it from the drop-down field, then click the __(right arrow) that appears at the end of the line. Doing so opens a separate page, wherein the Sponsor Level name and Ribbon Style can be changed, if necessary.

Users can also create a new Sponsor Level, by typing in the name of the new level, and clicking Create and edit… from the resulting drop-down menu.

Nota

Clicking Create from the resulting drop-down menu in this instance creates the sponsor level, but doesn’t immediately prompt the user to further configure it, via a Create Sponsor Level pop-up window.

Doing so reveals a Create Sponsor Level pop-up window.

From this pop-up window, confirm the newly-created Sponsor Level, and decide what kind of Ribbon Style should be applied, if any. The Ribbon Style options available in that drop-down field are: No Ribbon, Gold, Silver, and Bronze.

If one is selected, that Ribbon Style appears with the sponsor’s name on the event website.

On the booth category form, beneath those sections (Booth Details and Sponsorship), there is the Description tab. In this tab, proceed to enter any vital information related to the booth category that would be important for any potential booth-buyer to know about (e.g., the square footage, any amenities, size of display screen, etc.).

## Add booth to an event¶

In order to add a booth to an event, navigate to an existing event form, via Events app ‣ Events, and select the desired event from the Events dashboard. Or, click New to open a blank event form.

From the event form, to access the _Booths_ for that specific event, click the Booths smart button at the top of the page.

The Booths page is displayed in a Kanban view, by default, with two different stages: Available and Unavailable.

Nota

The Booths page of an event is also viewable in a __ List view, __ Graph view, and __ Pivot view. All of which are accessible, via their icons, in the upper-right corner of the Booths page.

The booths present in the Available stage are still available for people to purchase for the event. The booths present in the Unavailable stage have already been purchased, and are no longer available.

To modify any existing booth, simply click the desired booth from the Booths page, and proceed to make any necessary changes from the booth form. Or, create a new one, by clicking the New button in the upper-left corner to reveal a blank booth form.

### Booth form¶

The booth form in Odoo _Events_ lets users customize and configure event booths in a number of different ways.

Start by typing in a Name for the booth. This is a **required** field.

Then, apply a Booth Category to the booth. This is a **required** field.

Suggerimento

A new Booth Category can be created from this field, by typing in the name of the new category, and clicking Create and edit… from the resulting drop-down menu. Doing so reveals a Create Booth Category pop-up window, with all the standard fields found on a common booth category form.

Simply clicking Create from the resulting drop-down menu creates the category, but does not reveal the Create Booth Category pop-up window. The category would have to be modified later, via the _Booth Categories_ page (Events app ‣ Configuration ‣ Booth Categories).

Upon selecting a pre-existing Booth Category, two additional, non-modifiable fields appear: Product and Price. Both fields represent their respective selections for that specific booth category.

When a person purchases a booth rental through the event website, the subsequent renter-related fields on the form auto-populate, based on the information provided by the purchaser during the online transaction. The booth also automatically changes its status from _Available_ to _Unavailable_.

However, if the rental of a booth is conducted in any other way (e.g., in person, via sales order, etc.), the Renter, Renter Name, Renter Email, and Renter Phone fields can be entered in manually.

The status of the booth (Available or Unavailable) can also be changed manually, either by clicking the appropriate status from the status bar present on the booth form, or by dragging-and-dropping the desired booth into the appropriate stage, via the _Booths_ page Kanban view.

## Sell event booths¶

With event booths configured on the event form, via the event-specific _Booths_ pages, Odoo presents them on the event website, via the _Get A Booth_ event subheader link.

To access the _Get A Booth_ page on the event website, open the Events app, and select the desired event from the Events dashboard. From the event form, click the Go to Website smart button to be taken to the Odoo-built event website.

If the event subheader menu (with the Get A Booth option) is _not_ showing up on the event website, there are two ways to make it appear.

While on the event website, enter the edit mode by clicking the Edit button in the upper-right corner. Then, click into the Customize tab of the resulting sidebar of web design tools.

In the Customize tab, click the toggle switch for Sub-Menu (Specific), and click Save. Doing so reveals the event subheader menu with various options.

Alternatively, enter [Debug mode](../../general/developer_mode.html), and open the specific event form in the the _Events_ application.

On the event form, with _Debug mode_ on, an array of subheader menu options appears. Tick the checkbox for Website Submenu, in order for the submenu to appear on the event website. Doing so also ticks every other submenu-related checkbox automatically.

At this point, proceed to choose which options to keep on the event subheader menu. In this case, make sure the Booth Register checkbox is ticked.

From there, click the Get A Booth event subheader menu option. Doing so reveals the Get A Booth page, showcasing all the configured event booths that were created on the event form.

From here, the visitor can select their desired booth option, then Location. Next, they would click the Book my Booth(s) button, located at the bottom of the Get A Booth page.

Doing so reveals a Contact Details page, wherein they fill out either _Contact Details_ or _Sponsor Details_ , depending on how the booth was configured on the event form. The fields present on this form vary, depending on whether its meant for a basic contact or an event sponsor.

Nota

If the selected booth has the _Create Sponsor_ checkbox ticked, this page reads as _Sponsor Details_.

The information provided on this details page is used to auto-populate the renter-related information on the booth form on the event form in the _Events_ application.

Once the necessary information has been entered, the visitor then clicks the Go to Payment at the bottom of the page, and proceeds to complete the typical checkout process.

Upon a successful payment confirmation, that selected booth automatically moves to the _Unavailable_ stage on the event-specific _Booths_ page in the _Events_ application (accessible via the _Booths_ smart button on the event form).

Also, the provided _Sponsor_ information (if applicable) and _Sales Order_ information are accessible from the specific event form, via their respective smart buttons that appear at the top of the form.

Nota

Click the _Sponsors_ smart button to modify any information about the sponsor, if necessary.

Vedi anche

  * [Create events](create_events.html)

  * [Sell event tickets](sell_tickets.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/events/event_booths.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](event_tracks.html "Event tracks") |
  * [precedente](event_templates.html "Event templates") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event booths


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