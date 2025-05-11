# Revenues report — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../surveys.html "Sondaggi") |
  * [precedente](registration_desk.html "Banco registrazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Revenues report



# Revenues report¶

The Odoo **Events** application creates custom reports, based on event-related data and analytics. These reports can either be focused on _Attendees_ or _Revenues_.

The following documentation focuses on the reporting options related to event _Revenues_.

## Revenues reporting page¶

To access the _Attendees_ reporting page, navigate to Events app ‣ Reporting ‣ Revenues.

By default, the Revenues reporting page appears as a graph (a __(Line Chart) with __(Stacked) data). The default filters, Non-free tickets and Event Start Date: (current year), are present in the search bar.

Suggerimento

To learn more about the various graph views (and graph view options), refer to the [Graph views](../../essentials/reporting.html#reporting-using-graph) documentation.

The Revenues reporting page can also be viewed as a [pivot table](../../essentials/reporting.html#reporting-views-pivot), by clicking the __(Pivot) icon in the upper-right corner.

### Misure¶

Choosing specific [Measures](../../essentials/reporting.html#reporting-choosing-measures) is a quick way to customize reporting pages.

Regardless of the chosen view, the measures on the Revenues reporting page are as follows: Revenues, Untaxed Revenues, and Count.

Nota

In the default graph view of the Revenues reporting page, only the Revenues option is set in the Measures drop-down menu.

In graph view, only one of the Measures can be selected at a time.

When the pivot option is selected, all Measures options are selected, by default.

  * Revenues: shows the revenues generated from events.

  * Untaxed Revenues: shows the untaxed revenues generated from events.

  * Count: shows the total amount of registrants who attended events.




### Filters and grouping options¶

To reveal a drop-down menu of filter and grouping options to create custom reports, click the __(down arrow) to the right of the search bar.

Doing so opens a drop-down mega menu of options organized into columns: [Filters](../../essentials/search.html#search-preconfigured-filters), [Group By](../../essentials/search.html#search-group), and [Favorites](../../essentials/search.html#search-favorites).

Nota

If a time-related option has been selected from the Filters column (e.g. the default Event Start Date: (year) filter), a Comparison column appears, with comparison options for the corresponding time-related filter option selected.

Only **one** selection can be made from the Comparison column at a time.

Vedi anche

[Cercare, filtrare e raggruppare i record](../../essentials/search.html)

#### Filter options¶

In the Filters column of the drop-down mega menu, there are various event-related options that can be utilized to create custom reports, based on a number of specific criteria.

Multiple options in the Filters column can be selected at once.

The Filters column has the following options:

  * Non-free tickets: event tickets/registrations that were **not** free.

  * Free: event tickets/registrations that _were_ free.

  * Pending payment: event tickets/registrations that were purchased, but still have payment pending.

  * Sold: event tickets/registrations that have been successfully sold (and paid for).

  * Registration Date: Click the __(down arrow) icon to reveal a list of month, quarter, and year options. Select any number of these options to view a specific periods of time and see how many registrations happened during that time.

  * Upcoming/Running: include revenue-related information for events that are either currently running or are going to happen in the future.

  * Past Events: include revenue-related information for events that have already taken place.

  * Event Start Date: Click the __(down arrow) icon to reveal a list of month, quarter, and year options. Select any number of these options to designate event start dates to use as filters for revenue-related event data.

  * Event End Date: Click the __(down arrow) icon to reveal a list of month, quarter, and year options. Select any number of these options to designate event end dates to use as filters for revenue-related event data.

  * Published Events: Select this option to show revenue-related data for published events.

  * Add Custom Filter: Create a custom filter to analyze event-related revenue data. To learn more, refer to the documentation on [custom filters](../../essentials/search.html#search-custom-filters).




#### Group By options¶

In the Group By column of the drop-down mega menu, there are various event-related options to create custom groupings of data.

Multiple Group By options can be selected at once.

The Group By column has the following options:

  * Event Type: Group data based on the type of event.

  * Event: Organize data into individual groups, separated by events.

  * Product: Group data based on the event registration product.

  * Ticket: Group data based on the type of event ticket purchased by attendees.

  * Registration Status: Group data based on the status of registrations.

  * Sale Order Status: Group data based on the status of event-related sales orders.

  * Customer: Group data based on customer records.

  * Add Custom Group: Click the __(down arrow) icon to reveal a drop-down of grouping options. To select one, click on the desired option, and Odoo adds it to the Group By column. Multiple selections can be made.




## Sample report: event ticket analysis (graph)¶

The following is an example of how various filters and grouping options can create a useful analytic graph report related to event revenues. In this case, the configurations present data about sold or free tickets to published events, with the metrics separated by ticket type and event.

To create such a report, navigate to Events app ‣ Reporting ‣ Revenues. Stay in the default graph view, but remove the default filters from the search bar.

Then, click the __(down arrow) to the right of the search bar, to reveal the drop-down mega menu of filter and grouping options.

From here, select Free and Sold from the Filters column.

Then, since it is desired to **only** view data related to already published events, select the Published Events option in the Filters column, as well.

Next, in the Group By column, select the Event and Ticket options, **in that sequential order**. Doing so first groups the data by event, _then_ by ticket type, which provides a more useful array of data to analyze.

Importante

The order in which the options are selected in the Group By column directly affects how the data is presented on the report.

From there, additional configurations can be added for more detailed data, if desired.

If no additional filters or groupings are added, Odoo presents a graphical representation of data related to all _free_ or _sold_ tickets for _published events_ , grouped by _event_ , and organized by _ticket_ type.

## Sample report: event type analysis (pivot table)¶

The following is an example of how various filters and grouping options can create a useful analytic pivot table report related to event revenues. In this case, the configurations present data about how much revenue different event types have generated, in order to gauge which events are the most profitable.

First, navigate to Events app ‣ Reporting ‣ Revenues, and switch to the pivot table view, by clicking the __(Pivot) icon in the upper-right corner.

Keep the default filters (Non-free tickets and Event Start Date: (year)) in the search bar.

Next, open the Measures drop-down menu, and deselect the option for Count, because this report is only going to focus on revenues.

Then, click __ Total above the column titles, and select Event Type from the resulting drop-down menu.

With these configurations in place, all the revenues generated from the events (and their corresponding registrations) are displayed, organized by the event type (presented as expandable columns).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/events/revenues_report.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../surveys.html "Sondaggi") |
  * [precedente](registration_desk.html "Banco registrazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Revenues report


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