# Global filters — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../knowledge.html "Knowledge") |
  * [precedente](templates.html "Modelli") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Foglio di calcolo](../spreadsheet.html) »
  * Global filters



# Global filters¶

Create dynamic views of [inserted data](insert.html), by mapping data source fields to _global filters_ in the Odoo **Spreadsheets** app.

Nota

The global filters are represented by the  (global filter) icon, and enable data that was inserted via a pivot table, list, or chart to be filtered. Global filters differ from the _sort and filter_ feature for cell ranges represented by the __(filter) icon.

## Aggiungi filtri¶

Navigate to the Documents app and click on the desired spreadsheet, then open the  (global filter) filter menu.

Create a new filter by selecting one of the buttons under the Add a new filter… section:

  * Date: filter dates by matching data source date fields to a time range (e.g., _Month / Quarter_ , _Relative Period_ , or _From / To_).

  * Relation: filter records by matching data source fields to fields in a related model (e.g., _Lead/Opportunity_ , _Sales Order_ , or _Event Registration_).

  * Text: filter text by matching data source text fields to a string of text (e.g., _Restrict values to a range_ and/or provide a _Default value_).




Nota

Only filters that are able to be applied to the fields in the data source are shown.

### Data¶

The _Date_ global filter enables the filtering of data sources by a specific time range, to automatically filter on the current period, or to offset the time range relative to the period.

With the  (global filter) menu open, select the Date button to create a new date filter. The Filter properties menu displays the following fields for configuration below.

First, enter a name for the new date filter in the Label field.

Then, select one of the three period options in the Time range field:

  * Month / Quarter: enables a drop-down menu of specific months and quarters of a year (i.e., _Q1_ , _Q2_ , _January_ , etc.).

  * Relative Period: enables a drop-down menu of specific moving time frames (i.e., _Year to Date_ , _Last 7 Days_ , _Last 30 Days_ , etc.).

  * From / To: enables _Date from…_ and _Date to…_ date selection fields to define a specific time range (e.g., `06/05/2024` to `06/27/2024`).




Optionally, set a Default value for the Time range.

Nota

The Default value field only appears for Month / Quarter or Relative Period ranges.

If the Month / Quarter range is selected, tick the Automatically filter on the current period checkbox to define the default period of either Month, Quarter, or Year.

Next, configure the Field matching for each data source. To do so, expand the section by clicking on the Field matching heading, to reveal a list of the data sources in the spreadsheet where each data source has two fields for matching:

  * Date field: select a date field from the data source model to apply the time range to.

  * Period offset: (optionally) select an offset that shifts the time range by a relative period.

The options available are: Previous, Before Previous, Next, After Next.




Lastly, once all the information is entered on the form, click the Save button. If any of the data source fields do not match the data type of _date_ (or _datetime_), an error is shown stating Some required fields are not valid.

Example

Consider a Period offset of Next when using the Month / Quarter range to apply the filter to the _next_ period relative to the set time range.

With this configuration, selecting `January` `2024` as the date, filters data as `February` `2024`; where the selected month is offset to the next month.

### Relazione¶

The _Relation_ global filter enables the filtering of records in data sources by selecting a field from a related model.

With the  (global filter) menu open, select the Relation button to create a new relation filter. The Filter properties menu displays the following fields for configuration.

First, enter a name for the new relation filter in the Label field.

Then, select or search for a model from the Related model field.

Once a model is selected, the Default value and Field matching fields appear.

Optionally, set a Default value for the Related model. The available options are records of the model.

Next, configure the Field matching for each data source. To do so, expand the section by clicking on the Field matching heading, to reveal a list of the data sources in the spreadsheet where each data source has a field for matching.

Select a field from the data source model from which to apply the relation filter.

Lastly, once all the information is entered on the form, click the Save button. If any of the data source fields do not match the data type of the related model, an error is shown stating Some required fields are not valid.

Example

Consider a _Relation_ filter with the Related model set as Contact. The Field matching _CRM_ lead (`crm.lead`) pivot data sources are set to Customer.

With this configuration, selecting a customer record filters the pivot table to only leads that are related to the selected customer record.

### Testo¶

The _Text_ global filter enables the filtering of text by matching data source text fields to a string of text or to a range of predefined values.

With the  (global filter) menu open, select the Text button to create a new text filter. The Filter properties menu displays the following fields for configuration.

First, enter a name for the new text filter in the Label field.

Then, choose whether or not to Restrict values to a range by ticking the checkbox. Doing so, reveals a field to input a range within the spreadsheet. Either type in or select the range.

Next, configure the Field matching for each data source. To do so, expand the section by clicking on the Field matching heading, to reveal a list of the data sources in the spreadsheet where each data source has a field for matching.

Select a field from the data source model from which to apply the text filter.

Lastly, once all the information is entered on the form, click the Save button. If any of the data source fields do not match the data type of the related model, an error is shown stating Some required fields are not valid.

Example

Consider a text filter with the range `A2:A6` added to the Restrict values to a range field. The spreadsheet has five different product names listed as values in the cells of column `A`, rows `2` though `6`.

With the above configuration, a pivot table of products can be filtered by product name by selecting one of the 5 predefined values available in the text filter.

Furthermore, if the values in the range `A2:A6` are added dynamically– the text filter becomes dynamic as well.

## Manage filters¶

Open the  (global filter) filter menu by navigating to the Documents app and clicking on the desired spreadsheet.

Existing global filters appear under the Filters section. Filters can be used individually, or at the same time.

Suggerimento

The order of existing filters can be changed by hovering over a filter and using the  (drag handle) icon to change the position.

To reset a filter with set values back to default, click on the __(clear) icon next to the value in the filter.

To edit an existing filter, select the __(gear) icon to open the filter’s Filter properties menu. From here, edits can be made or the filter can be deleted by clicking the Remove button.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/spreadsheet/global_filters.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../knowledge.html "Knowledge") |
  * [precedente](templates.html "Modelli") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Foglio di calcolo](../spreadsheet.html) »
  * Global filters


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