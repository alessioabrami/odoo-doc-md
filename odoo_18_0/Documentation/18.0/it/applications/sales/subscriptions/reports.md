# Subscription reports — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../rental.html "Noleggio") |
  * [precedente](scheduled_actions.html "Scheduled actions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Subscription reports



# Subscription reports¶

The Odoo **Subscriptions** app provides a series of reporting pages to help companies analyze how subscriptions are performing.

On the _Subscriptions Analysis_ reporting page, users can view specific data related to recurring subscriptions, quantity of subscriptions, in-progress or paused subscriptions, and more.

The _Retention Analysis_ reporting page provides an organized table of subscription retention percentages over any period of time.

The _MRR Breakdown_ reporting page clearly divides MRR and ARR metrics for subscriptions into various graphs, lists, and charts.

And the _MRR Analysis_ reporting page offers a time-based collection of analytics showcasing how subscription MRR and ARR have changed over the course of any given period of time.

## Reporting page elements¶

All subscriptions-based reporting pages can be accessed via the Reporting header menu in the **Subscriptions** app.

The following sections describe elements found on each reporting page.

### Filters and Group By¶

_Filters_ are used to narrow down metrics to show specific analytics, whereas groupings (via the _Group By_ option) are used to gather the data from specific sections into groups for more organized analysis.

This section refers to both filters and groupings, as a combination of the two can be saved in the _Favorites_ section.

To modify the results being shown on any reporting page, click the __(down arrow) icon to the right of the search bar. Doing so reveals a drop-down menu of detailed filter and grouping options.

If desired, a filter or grouping (or combination of filters and/or groupings) can be saved in the Favorites section of that drop-down menu. To do so, click the __(down arrow) icon beside Save current search, located beneath the Favorites section.

This reveals a field to assign a title to the favorite filter. Two options are also found beneath the title field: Default filter and Shared.

Ticking the checkbox beside Default filter makes the newly-favorited filter the default option for that reporting page.

Ticking the checkbox beside Shared makes the newly-favorited filter available to other users in the database.

Nota

The Default filter and Shared options are **not** required, and only _one_ of these options can be selected at a time.

To save the filter, click Save in the Favorites section of the drop-down filter menu.

When clicked, that saved filter appears beneath the Favorites column of the drop-down filter menu, and a __(gold star) icon appears beside the favorite filter’s name in the search bar.

### Visualizzazioni¶

On the Subscription Analysis, MRR Breakdown, and MRR Analysis reporting pages, three different view options are located in the upper-right corner.

Nota

There are _no_ other view options available on the Retention Analysis reporting page.

The available view options, from left to right, are:

  * Graph

  * List

  * Pivot




Each view has its own series of related view-specific visual options.

#### Vista grafico¶

With the graph view selected, the following options appear between the search bar and visual representation of the data. These graph-specific options are located to the right of the Measures and Insert in Spreadsheet buttons.

The first three options, from left to right, represent different graph-related views. The remaining options represent different ways to organize and visualize that specific graph-related data.

From left to right, the specific graph-related view options are:

  * __ Bar Chart: showcases the data in a bar chart format.

  * __ Line Chart: showcases the data in a line chart format.

  * __ Pie Chart: showcases the data in a pie chart format.




Each graph view option has its own series of specific visual options, which are represented by the available buttons that appear to the right of the selected graph-related view option.

When the __ Bar Chart graph view is selected, the following visual options are available:

  * __ Stacked: showcases the data in a stacked visual format.

  * __ Descending: showcases the data in descending order.

  * __ Ascending: showcases the data in ascending order.




When the Line Chart graph view is selected, the following visual options are available:

  * __ Stacked: showcases the data in a stacked visual format.

  * __ Cumulative: showcases the data in accumulated, increasing format.

  * __ Descending: showcases the data in descending order.

  * __ Ascending: showcases the data in ascending order.




When the Pie Chart graph view is selected, there are no additional visual options.

#### Vista elenco¶

With the list view selected, the subscription metrics being analyzed are displayed in a simple list, which can be fully customized by using any of the available filters or groupings in the drop-down filter menu (accessible via the __(down arrow) icon to the right of the search bar).

Nota

With list view selected, the Measures drop-down menu and Insert in Spreadsheet button are _not_ available.

#### Vista pivot¶

With the pivot view selected, the subscription metrics are displayed in a data table, which can be fully customized.

The pivot data table can be customized using the options available in the Measures drop-down menu, and/or the filter grouping options available in the filter drop-down menu (accessible via the __(down arrow) icon to the right of the search bar).

Three pivot-specific options are available, located to the right of the Measures drop-down menu and Insert in Spreadsheet button.

From left to right, those pivot-specific view options are:

  * __ Flip axis: the `x` and `y` axis of the pivot data table flip.

  * __ Expand all: all the available rows and columns of the pivot data table expand fully.

  * __ Download .xlsx: the pivot data table is downloaded as an `.xlsx` file.




### Misure¶

The graph and pivot reporting pages have their own metric-specific Measures drop-down menu of data-related options to choose from, located in the upper-left corner, above the visual representation of metrics.

When the Measures button is clicked, a series of selectable measures becomes available, via a drop-down menu. When any of the options are selected from the Measures drop-down menu, the chosen metrics related to that specific measure appear on the reporting page.

Nota

For more information on the different measures that can be utilized on each reporting page, refer to the specific reporting page breakdowns found below in this documentation.

### Inserisci nel foglio di calcolo¶

Beside the Measures drop-down menu, there is an Insert in Spreadsheet button.

When clicked, the ability to add the configured data currently being showcased on the reporting page into a new or pre-existing spreadsheet or dashboard becomes available, via a pop-up window.

Select the desired option from this pop-up window, then click Confirm.

## Reporting pages¶

In the Odoo **Subscriptions** app, there are four different reporting pages available.

To access, analyze, and customize various reports related to subscriptions, navigate to Subscriptions app, and click the Reporting drop-down menu in the header to reveal the following reporting pages:

  * Subscriptions

  * Retention

  * MRR Breakdown

  * MRR Timeline




Clicking any of those options reveals a separate, fully-customizable reporting page focusing on that particular aspect of subscription data.

The following is a breakdown of those four specific reporting pages.

### Subscriptions analysis¶

To access the Subscriptions Analysis reporting page, navigate to Subscriptions app ‣ Reporting ‣ Subscriptions.

By default, the Bar Chart option, in the Graph view, is selected on the Subscriptions Analysis reporting page.

The following filters are also present in the search bar: In Progress or Paused and Recurring.

When the Measures button on the Subscriptions Analysis page is clicked, a series of metric-related options becomes available as a drop-down menu.

The metric-related options in the Measures drop-down menu on the Subscriptions Analysis page are:

  * Monthly Recurring

  * Quantità

  * Recurring Revenue

  * Untaxed Total

  * Yearly Recurring

  * Count




Nota

The Monthly Recurring measure option is selected by default.

When any of those available measures are clicked, Odoo displays that selected data on the reporting page for further analysis.

### Retention analysis¶

To access the Retention Analysis reporting page, navigate to Subscriptions app ‣ Reporting ‣ Retention.

The Retention Analysis reporting page differs from the other **Subscriptions** app reporting pages, in that it does **not** provide any additional view options. The data on this page is only presented in a customizable data chart.

When the Measures drop-down menu on the Retention Analysis reporting page is clicked, a series of metric-related options become available.

The metric-related options in the Measures drop-down menu on the Retention Analysis reporting page are:

  * Amount to invoice

  * Margin

  * Margin (%)

  * Prepayment percentage

  * Shipping Weight

  * Unpaid Amount

  * Count




Nota

The Count measure option is selected by default.

To the right of the Measures drop-down menu on the Retention Analysis page is an additional drop-down menu containing different time periods. The default time period is Month.

When clicked, a drop-down menu of various time period options become available.

The time period options are:

  * Day

  * Week

  * Month

  * Year




When a time period option from this drop-down menu is selected, the Retention Analysis reporting page showcases data for the configured measures and filters within that time period.

To the right of the time period drop-down menu, there is a download button, which allows the user to download the data presented on the Retention Analysis page as an Excel file.

### MRR breakdown¶

To access the MRR Breakdown reporting page, navigate to Subscriptions app ‣ Reporting ‣ MRR Breakdown.

By default, the data displayed on the MRR Breakdown reporting page is in graph view, with the Bar Chart option and Stacked option selected.

A default filter is also available in the search bar for Event Date: Month > Event Type.

When the Measures drop-down menu on the MRR Breakdown reporting page is clicked, a series of metric-related options become available.

The metric-related options in the Measures drop-down menu on the MRR Breakdown reporting page are:

  * Active Subscriptions Change

  * ARR Change

  * MRR Change

  * Count




Nota

The MRR Change measure option is selected by default.

Suggerimento

To make a different measure option the default, first, select the desired measure from the Measures drop-down menu. Then, click the __(down arrow) icon in the search bar to open the mega menu of filters and groupings.

In the Favorites column, click the __(down arrow) icon beside Save current search to reveal a field, where a title can be entered, along with two checkboxes:Default filter and Shared.

Tick the checkbox for Default filter, and click Save.

That newly-chosen measure option is now the default option that appears when this reporting page is accessed.

### MRR analysis¶

To access the MRR Analysis reporting page, navigate to Subscriptions app ‣ Reporting ‣ MRR Timeline.

By default, the data displayed on the MRR Analysis reporting page is in graph view, with the Line Chart option, Stacked option, and Cumulative option selected.

A default filter is also found in the search bar for Event Date: Month.

When the Measures drop-down menu on the MRR Analysis reporting page is clicked, a series of metric-related options become available.

The metric-related options in the Measures drop-down menu on the MRR Analysis reporting page are:

  * Active Subscriptions Change

  * ARR Change

  * MRR Change

  * Count




Nota

The MRR Change measure option is selected by default.

Vedi anche

  * [Abbonamenti](../subscriptions.html)

  * [Subscription plans](plans.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/subscriptions/reports.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../rental.html "Noleggio") |
  * [precedente](scheduled_actions.html "Scheduled actions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Subscription reports


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