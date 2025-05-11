# Maintenance calendar — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_requests.html "Maintenance requests") |
  * [precedente](add_new_equipment.html "Add new equipment") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance calendar



# Maintenance calendar¶

Avoiding equipment breakdowns, and blocks in warehouse work centers, requires constant equipment maintenance. Timely corrective maintenance for machines and tools that break unexpectedly, as well as preventive maintenance to ensure that such issues are avoided, are key to keeping warehouse operations running smoothly.

In Odoo _Maintenance_ , users can access the _Maintenance Calendar_ to create, schedule, and edit both corrective and preventive maintenance requests, to stay on top of equipment and work centers.

## Create maintenance request¶

Maintenance requests can be created directly from the _Maintenance Calendar_. To access the calendar, navigate to Maintenance app ‣ Maintenance ‣ Maintenance Calendar.

To create a new request, click anywhere on the calendar. Doing so opens a New Event pop-up window. In the Name: field, assign a title to the new request.

Clicking Create on the pop-up window saves the new request with no additional details. If the request’s creation should be cancelled, click Cancel.

To add more details and schedule the request for a specific date and time, click Edit.

Clicking Edit opens a blank maintenance request form, where various details about the request can be filled out.

### Edit maintenance request¶

In the Request field, assign a title to the new request. In the Created By field, from the drop-down menu, select which user the request was created by. By default, this field populates with the user actually creating the request.

In the For field, from the drop-down menu, select if this request is being created for a piece of Equipment, or a Work Center.

Nota

If Work Center is selected in the For field’s drop-down menu, two additional fields appear on the form: Work Center and Block Workcenter.

In the Work Center field, select which work center in the warehouse this maintenance request applies to.

If the Block Workcenter option’s checkbox is ticked, it is not possible to plan work orders, or other maintenance requests, in this work center during the time that this request is being performed.

If Equipment is selected in the For field, which it is by default, select which machine or tool requires maintenance from the Equipment field. Once a specific piece of equipment is selected, a greyed-out Category field appears, listing the _Equipment Category_ to which the equipment belongs.

In the Worksheet Template field, if necessary, click the drop-down menu to select a worksheet template. These templates are custom templates that can be filled out by the employee performing the maintenance.

Under the Category field, the Request Date field displays the date requested for the maintenance to happen.

The Maintenance Type field provides two selectable radio button options: Corrective and Preventive.

Corrective maintenance is for requests that arise for immediate needs, such as broken equipment, while Preventive maintenance is for planned requests, to avoid breakdowns in the future.

If this request is tied to a specific MO, select that MO from the Manufacturing Order field.

From the drop-down menu for the Team field, select the desired maintenance team who will perform the maintenance. In the Responsible field, select the technician responsible for the request.

In the Scheduled Date field, click the date to open a calendar popover. From this popover, select the planned date of the maintenance, and click Apply to save the date.

In the Duration field, enter the the amount of hours (in a `00:00` format) that the maintenance is planned to take.

In the Priority field, choose a priority between one and three ⭐⭐⭐ (stars). This indicates the importance of the maintenance request.

If working in a multi-company environment, from the drop-down menu in the Company field, select the company to which this maintenance request belongs.

At the bottom of the form, there are two tabs: Notes and Instructions.

In the Notes tab, type out any internal notes for the team or technician assigned to the request, if necessary.

In the Instructions tab, if necessary, select one of the three radio button options to provide maintenance instructions to the assigned team or technician. The available methods for providing instructions are via PDF, Google Slide, or Text.

## Calendar elements¶

The _Maintenance Calendar_ provides various views, search functions, and filters to help keep track of the progress of ongoing and planned maintenance requests.

The following sections describe elements found across various views of the calendar.

### Filters and Favorites¶

To access the maintenance calendar, navigate to Maintenance app ‣ Maintenance ‣ Maintenance Calendar.

To add and remove filters for sorting data on the _Maintenance Calendar_ , click the 🔻 (triangle pointed down) icon, to the right of the search bar at the top of the page.

The left-hand side of the resulting drop-down menu lists all the different Filters users can select. By default, To Do and Active are selected, so all open requests are displayed.

Suggerimento

To add a custom filter to the Maintenance Calendar, click Add Custom Filter, under the Filters section of the drop-down menu. This opens an Add Custom Filter pop-up window.

From this pop-up window, configure the properties of the new rule for the filter. Once ready, click Add.

The right-hand side of the drop-down menu lists the Favorites, or any searches that have been saved as a favorite to be revisited at a later date.

To save a new Favorite search, select the desired Filters. Then, click Save current search. In the field directly below Save current search, assign a name to the search.

Under the assigned name, there are two options, to save the current search either as the Default filter, or as a Shared filter.

Selecting Default filter sets this filter as the default when opening this calendar view.

Selecting the Shared filter makes this filter available to other users.

Once ready, click Save. When clicked, the new Favorite filter appears in the Favorites column, and a ⭐ (gold star) icon appears with the filter’s name in the search bar.

### Visualizzazioni¶

The Maintenance Calendar is available in six different views: Calendar (default), Kanban, List, Pivot, Graph, and Activity.

#### Calendar view¶

Calendar is the default view displayed when the Maintenance Calendar is opened. There are a number of options in this view type for sorting and grouping information about maintenance requests.

In the top-left corner of the page, there is a drop-down menu set to Week, by default. Clicking that drop-down menu reveals the different periods of time, in which the calendar can be viewed: Day, Month, and Year. There is also an option to Show weekends, selected by default. If unselected, weekends are not shown on the calendar.

To the left of this menu, there is a ⬅️ (left arrow) icon and a ➡️ (right arrow) icon. Clicking these arrows moves the calendar backward or forward in time, respectively.

To the right of the drop-down menu set to Week, by default, is a Today button. Clicking this button resets the calendar to view today’s date, no matter which point in time is being viewed before clicking it.

At the far-right side of the page is a sidebar column, containing a minimized calendar set to today’s date, and a Technician list, displaying all the _Technicians_ with requests currently open. Click the (panel) icon at the top of this sidebar to open or close the sidebar.

Nota

The Technician list only displays if technicians are assigned to open requests, and individual technicians are only listed, if they are listed as Responsible on at least **one** maintenance request form.

#### Vista kanban¶

With the Kanban view, all open maintenance requests are displayed in Kanban-style columns, in their respective stages of the maintenance process.

Each maintenance request appears on its own task card, and each task card can be dragged-and-dropped to a different stage of the Kanban pipeline.

Each column has a name (i.e. In Progress). Hovering at the top of a column reveals a ⚙️ (gear) icon. Clicking the ⚙️ (gear) icon reveals a list of options for that column: Fold, Edit, Automations, and Delete.

Clicking Fold folds the column to hide its contents.

Clicking Edit opens an Edit: (stage name) pop-up window, with the corresponding stage name, wherein the column’s details can be edited. The following are the column options that can be edited:

  * Name: the name of the stage in the Kanban pipeline.

  * Folded in Maintenance Pipe: when checked, this stage’s column is folded by default in the Kanban view type.

  * Request Confirmed: when this box is not ticked, and the maintenance request type is set to _Work Center_ , no leave is created for the respective work center when a maintenance request is created. If the box _is_ ticked, the work center is automatically blocked for the listed duration, either at the specified date, or as soon as possible, if the work center is unavailable.

  * Sequence: the order in the maintenance process, in which this stage appears.

  * Request Done: if ticked, this box indicates this stage is the final step of the maintenance process. Requests moved to this stage are closed.




Once ready, click Save & Close. If no changes have been made, click Discard, or click the X icon to close the pop-up window.

#### Vista elenco¶

With the List view selected, all open maintenance requests are displayed in a list, with information about each request listed in its respective row.

The columns of information displayed in this view type are the following:

  * Subjects: the name assigned to the maintenance request.

  * Employee: the employee who originally created the maintenance request.

  * Technician: the technician responsible for the maintenance request.

  * Category: the category the equipment being repaired belongs to.

  * Stage: the stage of the maintenance process the request is currently in.

  * Company: if in a multi-company environment, the company in the database the request is assigned to.




#### Vista pivot¶

With the Pivot view selected, maintenance requests are displayed in a pivot table, and can be customized to show different data metrics.

To add more data to the pivot table, click the Measures button to reveal a drop-down menu. By default, Count is selected. Additional options to add to the table are Additional Leaves to Plan Ahead, Duration, and Repeat Every.

To the right of the Measures button is the Insert in Spreadsheet button. Clicking this button opens a pop-up window titled Select a spreadsheet to insert your pivot..

There are two tabs in this pop-up window: Spreadsheets and Dashboards. Click into one of these tabs, and select a spreadsheet or dashboard in the database to add this pivot table to. Once ready, click Confirm. If this table shouldn’t be added to a spreadsheet or dashboard, click Cancel, or click the X icon to close the pop-up window.

To the right of the Insert in Spreadsheet button are three buttons:

  * Flip axis: the x and y axis of the pivot data table flip.

  * Expand all: all the available rows and columns of the pivot data table expand fully.

  * Download xlsx: the pivot data table is downloaded as an .xlsx file.




#### Vista grafico¶

With the graph view selected, the following options appear between the search bar and visual representation of the data. These graph-specific options are located to the right of the Measures and Insert in Spreadsheet buttons.

There are three different types of graphs available to users to view the data:

  * Bar Chart: the data is displayed in a bar chart.

  * Line Chart: the data is displayed in a line chart.

  * Pie Chart: the data is displayed in a pie chart.




When viewing the data as a Bar Chart graph, the data can be formatted in the following ways:

  * Stacked: the data is stacked on the graph.

  * Descending: the data is displayed in descending order.

  * Ascending: the data is displayed in ascending order.




When viewing the data as a Line Chart graph, the data can be formatted in the following ways:

  * Stacked: the data is stacked on the graph.

  * Cumulative: the data is increasingly accumulated.

  * Descending: the data is displayed in descending order.

  * Ascending: the data is displayed in ascending order.




When viewing the data as a Pie Chart graph, all relevant data is displayed by default, and no additional formatting options are available.

#### Vista attività¶

With the Activity view selected, all open maintenance requests are listed in their own row, with the ability to schedule activities related to those requests.

Maintenance requests are listed in the Maintenance Request column as activities. Clicking a request opens a Maintenance Request popover that indicates the status of the request, and the responsible technician. To schedule an activity directly from the popover, click ➕ Schedule an activity. This opens a Schedule Activity pop-up window.

From the pop-up window, choose the Activity Type, provide a Summary, schedule a Due Date, and choose the responsible user in the Assigned to field.

Type any additional notes for the new activity in the blank space under the greyed-out Log a note… field. When clicked, this changes to Type «/» for commands.

Once ready, click Schedule to schedule the activity. Alternatively, click Schedule & Mark as Done to close the activity, click Done & Schedule Next to close the activity and open a new one, or click Cancel to cancel the activity.

With the Activity view selected, each activity type available when scheduling an activity is listed as its own column. These columns are Email, Call, Meeting, Maintenance Request, To-Do, Upload Document, Request Signature, and Grant Approval.

To schedule an activity with that specific activity type, click into any blank box on the corresponding row for the desired maintenance request, and click the ➕ (plus) icon. This opens an Odoo pop-up window, wherein the activity can be scheduled.

Vedi anche

  * [Maintenance requests](maintenance_requests.html)

  * [Add new equipment](add_new_equipment.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/maintenance/maintenance_calendar.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_requests.html "Maintenance requests") |
  * [precedente](add_new_equipment.html "Add new equipment") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance calendar


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time