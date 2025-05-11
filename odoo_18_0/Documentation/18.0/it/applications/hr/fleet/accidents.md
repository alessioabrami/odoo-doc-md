# Accidents — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payroll.html "Libro paga") |
  * [precedente](service.html "Servizi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Accidents



# Accidents¶

When managing a fleet, accidents are inevitable. Tracking accidents is crucial for understanding vehicle maintenance costs and identifying safe drivers.

Odoo’s _Fleet_ app offers multiple ways to track accidents. Below are step-by-step instructions for only **one** method to monitor accidents and repair costs.

## Struttura¶

For this example, to track accidents, two [service types](service.html#fleet-new-type) are created: `Accident - Driver's Fault` and `Accident - No Fault`.

This tracks various repairs associated with accidents, organized by who was at fault.

When an accident occurs, a service record is created. The specific repairs needed for the accident are logged in the _Description_ of the service record, and the details about the accident are logged in the _Notes_ section.

With this organizational structure, it is possible to view all accidents organized by fault, car, driver, or cost.

Nota

To manage accidents, the creation of service records is **required**.

Refer to the [Servizi](service.html) documentation for detailed instructions on creating service records in Odoo’s _Fleet_ app.

## Log accidents and repairs¶

To log an accident, and initiate the repair process, the first step is to [create a service record](service.html#fleet-service-form) detailing the specific repairs needed.

Nota

Some accidents require multiple repairs with several different vendors. For these scenarios, a separate service record is needed for each vendor performing repairs. To keep records organized, it is recommended to keep the _Notes_ field identical, as well as attaching the same important documentation, such as a police report.

Navigate to Fleet app ‣ Fleet ‣ Services to view the main Services dashboard. Click New in the top-left corner, and a blank service form loads.

Inserisci le seguenti informazioni nel modulo:

  * Description: enter the description of repairs needed to fully repair the vehicle, such as `Bodywork`, `Windshield Replacement`, or `Replacement Bumper, Tires, and Windows`.

  * Service Type: for this example, select either `Accident - Driver's Fault` or `Accident - No Fault`, depending on the situation.

When entering either of these two Service Types for the first time, type in the new service type, then click Create (new service type). A Create Service Type pop-up window appears, with the new service type populating the Name field. In the Category field, select Service from the drop-down menu, then click the Save & Close button.

Once an accident service type has been added to the database, it is available to select from the drop-down menu in the Service Type field.

  * Date: using the calendar popover window, select the date the accident occurred. Navigate to the desired month using the ____(arrow) icons, then click the date to select it.

  * Cost: leave this field blank, as the repair cost is not yet known.

  * Vendor: select the vendor performing the repairs using the drop-down menu. If the vendor has not already been entered in the system, type in the vendor name, and click either Create to add them, or Create and edit… to [add and configure the vendor](service.html#fleet-new-vendor).

  * Vehicle: select the vehicle that was in the accident from the drop-down menu. When the vehicle is selected, the Driver field is populated, and the unit of measure for the Odometer Value field appears.

  * Driver: the current driver listed for the selected vehicle populates this field when the Vehicle is selected. If a different driver was operating the vehicle when the accident occurred, select the correct driver from the drop-down menu.

  * Odometer Value: enter the odometer reading when the accident occurred. The units of measure are either in kilometers (km) or miles (mi), depending on how the selected vehicle was configured.

  * NOTES: enter the specific details of the accident at the bottom of the service form, such as `Hit a deer` or `Rear-ended at an intersection while stopped`.




Odoo provides the ability to attach any important paperwork, such as repair estimates and police reports, to the service record. To do so, click the __(paperclip) icon, located in the _chatter_ of the form, and a file explorer pop-up window appears. Navigate to the desired record, and click Open to upload the file.

> Nota
> 
> Once a file is added to a service record, a Files section appears in the _chatter_. To attach more records, click __ Attach files to add more documents.

## Service stages¶

In Odoo’s _Fleet_ app, there are four default service stages:

NewRunningCompletedCancelled

The default stage when a service record is created. The service has been requested, but repairs have not begun. The Cost field for this stage remains zero.

The repair is in-process, but not yet complete. The estimate for repairs is listed in the Cost field.

All repairs listed on the service form have been completed. The Cost field is updated to reflect the final total cost charged for the repairs.

The service request has been cancelled.

During the repair process, change the service status to reflect the vehicle’s current state in one of two ways: on the individual service record, or in the Kanban service view.

### Service record¶

Open the main _Services_ dashboard, by navigating to Fleet app ‣ Fleet ‣ Services. Next, click on the individual service record to open the detailed service form. Click the desired stage in the top-right corner, above the service form, to change the status.

### Vista kanban¶

Open the main _Services_ dashboard, by navigating to Fleet app ‣ Fleet ‣ Services. First, click the __ Kanban icon in the top-right of the screen, which organizes all repairs by vehicle.

Next, remove the default Service Type filter in the search bar. Upon doing so, all services appear in a Kanban view, organized by their respective Status.

Drag-and-drop the service record to the desired stage.

## Accident reporting¶

One of the main reasons to track accidents using the method outlined in this document is the ability to view the total accident cost, determine the safest drivers, and calculate the actual total cost for specific vehicles.

The main Services dashboard displays all the various accident information, while the Reporting dashboard displays the total cost for specific vehicles.

### Services dashboard¶

Navigate to Fleet app ‣ Fleet ‣ Services to view the Services dashboard. All service records are displayed in a __(List) view, grouped alphabetically, by Service Type.

The two service types created for accident tracking appear in the list: Accident - Driver Fault and Accident - No Fault.

Each grouping displays the number of records within each type, and lists the individual records beneath each grouping title.

Example

In this example, there are six accidents where the driver was at fault, and four accidents that were not the driver’s fault. This dashboard also displays the estimated total Cost for all the accidents in each group.

An estimated `$19,164.81` dollars are for driver-caused accident repairs, and an estimated `$2,548.21` dollars are for no-fault accidents.

Nota

The total Cost calculates **all** costs on the repair form, including estimated costs, as well as final repair costs. This number may not be accurate, if there are any repairs in the _Running_ stage, and the final bill has not yet been calculated.

### Reporting dashboard¶

Navigate to Fleet app ‣ Reporting ‣ Costs to view the Cost Analysis report. This report displays a __(Bar Chart) of all Contract and Service costs for the current year, organized by month (Date : (year)), by default. The Sum, represented by a gray dotted line, is the combined total of both the Contract and Service costs.

To view the total cost by vehicle, click the __(down arrow) icon at the right of the search bar, revealing a drop-down menu. Click Vehicle in the __ Group By column, and the data is organized by vehicle.

This displays the true cost for each vehicle, including both the contract cost (such as the monthly vehicle lease cost) and all service costs, including all accidents. Hover over a column to reveal a data popover window, which displays the vehicle name and the total cost. This allows for a more complete view of the vehicle cost.

To view the individual cost details for both contract costs and repairs, click the __(Pivot) icon in the top-right corner of the Cost Analysis dashboard. This displays each vehicle on a separate line, and displays the Contract cost and Service cost, as well as the Total cost.

Nota

The __(Pivot) view organizes the data by vehicle, by default, therefore grouping the data by Vehicle is not required. If this filer is already activated, it does not affect the presented data.

## Manage accident repairs¶

For companies with multiple employees, who manage a large fleet of vehicles, displaying only service records in the New and Running stages can be time-saving, if there are a large number of records in the _Services_ dashboard.

Navigate to Fleet app ‣ Fleet ‣ Services, where all service requests are organized by Service Type. Next, click the __(down arrow) icon at the right of the search bar, revealing a drop-down menu. Click Add Custom Filter in the __ Filters column, and a Add Custom Filter pop-up window appears.

Three drop-down fields need to be configured on the pop-up window.

In the first field, scroll down, and select Stage.

Leave the second field set to =.

Select Running from the drop-down menu in the last field.

Next, click the __(plus) icon to the right of the last field, and an identical rule appears beneath the current rule.

Then, change Running to New in the third field of the second rule, leaving the other fields as-is.

Click the Add button at the bottom to add the new custom filter.

This slight modification only presents services in the New and Running stages. This is a helpful report for a company managing a high number of repairs at any given time.

To have this report appear as the default report when opening the Services dashboard, click the __(down arrow) icon at the far-right of the search bar. Next, click Save current search, beneath the __ Favorites column, which reveals another drop-down column beneath it. Tick the checkbox beside Default Filter, then click Save. Then, this customized Services dashboard appears, by default, anytime the Services dashboard is accessed.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/fleet/accidents.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payroll.html "Libro paga") |
  * [precedente](service.html "Servizi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Accidents


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
  *[POS]: Punto vendita
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