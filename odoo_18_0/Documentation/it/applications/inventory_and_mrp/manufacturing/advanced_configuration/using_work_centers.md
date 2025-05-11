# Work centers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_order_dependencies.html "Work order dependencies") |
  * [precedente](sub_assemblies.html "Multilevel BoMs") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Work centers



# Work centers¶

_Work centers_ are where **Manufacturing** work orders are processed, and can be used to track costs, make schedules, plan capacity, organize equipment, and track efficiency. Specifying a work center is required when a work order is defined in the _Operations_ tab of a bill of materials (BoM) for a product.

Importante

Work centers only appear if the Work Orders setting is enabled. To do so, navigate to Manufacturing app ‣ Configuration ‣ Settings, then tick the Work Orders checkbox. Work orders can be managed in the Manufacturing app by selecting Operations ‣ Work Orders.

Vedi anche

[Bill of materials](../basic_setup/bill_configuration.html)

## Work center configuration¶

### Crea un nuovo centro di produzione¶

In the **Manufacturing** app, select Configuration ‣ Work Centers and click the New button to open a new work center form.

  * Work Center Name: the label for the work center used to select it on a work order or on the reporting dashboards

  * Tag: reusable labels that can be used to sort work centers in list view

  * Alternative Workcenters: where a work order should be carried out if this work center is not available

  * Code: reference id for the work center that is displayed in the list view

  * Working Hours: the hours that work center can be used during the week




#### Working hours¶

_Working hours_ define when a work center should operate, based on a one- or two-week schedule. These hours also form the basis for calculating _overall equipment efficiency_ (OEE).

Nota

By default, Odoo uses the `Standard 40 hours/week` working hours, which expects work centers to operate between 8:00 AM and 5:00 PM on Monday through Friday.

To change the working hours, hover over the current Working Hours value and click the __( Internal link) icon to open the working hours form.

To create a new set of working hours, click the New button and give it a name. From here, edit any Work from or Work to value to adjust the time range. Remove a line by clicking click the __(trash) icon. To create a new time range, click Add a line at the bottom of the list.

Vedi anche

  * [Overall equipment effectiveness](../reporting/oee.html)

  * [Work center time off](../workflows/work_center_time_off.html)




### Set productivity standards and allowed employees¶

The General Information tab on the work center form allows for productivity goals to be assigned to a work center. These are used as the basis for calculating how much of the potential time the work center is being used and its operating costs.

  * Time Efficiency: a multiplier for how using this work center affects the normal speed of execution of a work order

Example

If a work center has older equipment and work orders take twice as long to produce, the `Time Efficiency` would be `50.00%`.

  * Capacity: the number of products that can be processed at the work center simultaneously

  * OEE Target: the target for efficiency at the work center

Example

If a work center is available for `8 hours per day` but is only expected to be used for `7 hours per day`, the OEE would be `87.50%`. \\(7/8*100=87.5\\)

Vedi anche

[Overall equipment effectiveness](../reporting/oee.html)

  * Setup Time: the time required before work can commence on a work order

  * Cleanup Time: breakdown or cleanup time required after a work order is finished

  * Cost per hour: the operating expense of that workstation. The per employee value is for estimating the average cost per employee.

> Vedi anche
> 
> [Manufacturing order costs](../basic_setup/mo_costs.html)

  * Allowed Employees: the employees who can perform work at the work center. If blank, all employees are allowed.

> Example
> 
> If equipment at a work center requires a certification to operate, Allowed Employees could list only those employees who have the certification.




### Set production capacities¶

The Capacity setting on a work center creates a default value for how many units can be produced at one time in a work center. To specify that a work center can produce different quantities of different products, select the Specific Capacities tab.

Suggerimento

To specify production capacities in different measurements from a count of units, enable the _Units of Measure_ feature in the **Inventory** app.

Vedi anche

[Add new equipment](../../maintenance/add_new_equipment.html)

### Integrate IoT devices¶

The IoT Triggers tab enables the integration of IoT devices with a work center:

  * Device: specifies the IoT device to be triggered

  * Key: the security key for the device

  * Action: the IoT device action triggered




## Assigning equipment to work centers¶

The **Maintenance** app makes it possible to add specific equipment to a work center and individually track its costs and productivity. It also adds the Equipment and Maintenance tabs to the work center form, used to list equipment and schedule maintenance activities.

Vedi anche

[Add new equipment](../../maintenance/add_new_equipment.html)

### Configure equipment¶

Using the Equipment tab, it is possible for specific pieces of equipment to be assigned to a work center. The following information is displayed for each piece of equipment added:

  * Equipment Name: the name of the piece of equipment

  * Technician: the technician responsible for servicing the equipment

  * Equipment Category: the category the equipment belongs to

  * MTBF: mean time between failures; the average time that the piece of equipment will operate before failing

  * MTTR: mean time to recovery; the average time it takes for the equipment to become fully operational again

  * Est. Next Failure: an estimate of when the next equipment failure will occur




Nota

MTBF, MTTR, and Est. Next Failure are all calculated automatically based on past failure data, if any exists.

## Work center planning¶

The currently scheduled work orders can be viewed by accessing Manufacturing app ‣ Planning ‣ Planning by Workcenter.

Different views show how many individual work orders are scheduled, how many minutes of each hour the work center is in production, and the dates and times that are currently scheduled for work orders. Times and planned work centers can be changed by clicking to access the individual work order.

## Work center performance¶

Performance for an individual work center can be viewed by selecting Configuration ‣ Work Centers, and clicking on a work center. Metrics are displayed in smart buttons at the top of the form.

  * OEE: overall equipment effectiveness, the percentage of time that the work center has been productive out of its available work hours.

> Vedi anche
> 
>     * [Overall equipment effectiveness](../reporting/oee.html)

  * Lost: the amount of time lost due to work stoppages

  * Load: the amount of time it will take to complete the current workload

  * Performance: the real duration of work time, shown as a percentage of the expected duration




## Use case: measuring performance by shift using work centers¶

Work centers support defined working hours, enabling the tracking of production efficiency by shift. To configure shift-based tracking, create working hours for each of the shifts, then duplicate versions of each work center for each of the shifts. With this setup, comparing shift productivity can be done with any of the available [reporting](../../../essentials/reporting.html) tools.

### Working hours for multiple shifts¶

To create working hours for multiple shifts, open a work center form and in the Working Hours field click the __( Internal link), and then click the New button to create a new set of hours for the second shift.

Example

A manufacturer has two shifts: a day shift from 5 AM to 1 PM and a night shift from 1 PM to 9 PM. Starting from any existing work center, edit the existing working hours to match the day shift.

Once the day shift is saved, click the __(cog) icon and select Duplicate. Rename this new schedule `Night Shift` and change each Work from to 1 PM and Work from to 9 PM.

### Work centers for multiple shifts¶

To create the duplicate work centers, return to the work center view by navigating to Configuration ‣ Work Centers and duplicating each of the work centers that are used by both shifts, either on the individual work center forms, or directly from the list view.

Suggerimento

To duplicate work centers directly from the list view, click the __(checkbox) that appears above the list items to select all. Then, click the __ Actions button at the top of the list and select Duplicate.

Example

> A manufacturer has two work centers, `Assembly Line 1` and `Assembly Line 2`, and two working hours, `Day Shift` and `Night Shift`.

To create versions of `Assembly Line 1` and `Assembly Line 2` for each shift, duplicate each of the work centers. Select the first work center and add the shift name in that work center’s name and assign it the appropriate working hours. Optionally, configure each work center to use its opposite shift counterpart as an alternate work center to make sure that manufacturing orders get assigned to both. Tags can also help make a visual distinction between each shift.

> Suggerimento
> 
> Use the __(left arrow) and __(right arrow) buttons in the top left corner to move on to the next form in the list without returning to the list view.

### Reports comparing different shifts¶

With multiple work centers created to represent shifts, reports that sort by work center will now compare shifts. This can be used to compare the number of work orders that are being assigned each shift, the OEE, or actual time that each shift is taking to produce a product.

Example

A report has been created to compare the time efficiency of two shifts producing the same product in the same work center.

To create this report, go to Reporting ‣ Work Orders and click to remove the __**Ready** _or_ **Waiting** _or_ **Pending** _or_ **In Progress** filter by clicking the __ Remove icon on its right side. Next, click the Measures button and select Duration Deviation (%)

In this case, the day shift has on average taken more than the expected time to produce products (-6.50%) while the night shift took less than the expected time (15.00%).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_order_dependencies.html "Work order dependencies") |
  * [precedente](sub_assemblies.html "Multilevel BoMs") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Work centers


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
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: manufacturing order
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
  *[API]: Application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: sales orders
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: bills of materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
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