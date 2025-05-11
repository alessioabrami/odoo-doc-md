# Manage work orders using work centers — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_order_dependencies.html "Work order dependencies") |
  * [precedente](sub_assemblies.html "Manage semi-finished products") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Manage work orders using work centers



# Manage work orders using work centers¶

Odoo Manufacturing allows for work orders to be carried out at specific work centers. When a manufacturing order is created for a product, any work orders listed in the Operations tab of the product bill of materials (BoM) will be automatically created as well and assigned to the specified work center. Work orders can be managed in the Manufacturing module by selecting Operations ‣ Work Orders.

In order to use work centers, the Work Orders feature must first be enabled. To do so, go to the Manufacturing module, select Configuration ‣ Settings, and activate the checkbox next to Work Orders. Work centers can then be created and managed by selecting Configuration ‣ Work Centers.

## Create a work center¶

Within the Manufacturing module, select Configuration ‣ Work Centers ‣ Create. The work center form can then be filled out as follows:

  * Work Center Name: give the work center a concise name that describes the type of operations it will be used for

  * Alternative Workcenters: specify an alternative work center for operations to be carried out at if the main work center is not available

  * Code: assign the work center a reference code

  * Working Hours: define the number of hours that the work center can be in use each week

  * Company: select the company that the work center belongs to




### Set standards for work center productivity¶

The General Information tab on the work center form allows for productivity goals to be assigned to a work center:

  * Time Efficiency: used to calculate the expected duration of a work order at the work center; for example, if a work order normally takes one hour and the efficiency is set to 200%, the work order will take 30 minutes

  * Capacity: the number of products that can be processed at the work center simultaneously

  * OEE Target: the target for efficiency at the work center

  * Time before prod.: setup time required before work can commence

  * Time after prod.: breakdown or cleanup time required after work is finished

  * Cost per hour: the cost of operating the work center for one hour

  * Analytic Account: the account where the cost of the work center should be recorded




### Assign equipment to a work center¶

Using the Equipment tab, it is possible for specific pieces of equipment to be assigned to a work center. The following information will be displayed for each piece of equipment added:

  * Equipment Name: the name of the piece of equipment

  * Technician: the technician responsible for servicing the equipment

  * Equipment Category: the category the equipment belongs to

  * MTBF: mean time between failures; the average time that the piece of equipment will operate before failing

  * MTTR: mean time to recovery; the average time it takes for the equipment to become fully operational again

  * Est. Next Failure: an estimate of when the next equipment failure will occur




Nota

MTBF, MTTR, and Est. Next Failure are all calculated automatically based on past failure data, if any exists.

### Integrate IoT devices¶

The IoT Triggers tab enables the integration of IoT devices with a work center:

  * Device: specifies the IoT device to be triggered

  * Key: the security key for the device

  * Action: the IoT device action triggered




## Use case: configure an alternative work center¶

When a work center is at capacity, it cannot accept any new work orders. Instead of waiting for the work center to become available, it is possible to specify an alternative work center where surplus work orders should be carried out.

Begin by creating a new work center. Configure the Equipment tab so that it has all of the same equipment as the main work center. This will ensure that the same tasks can be carried out at both work centers. Navigate to the main work center and include the new work center in the Alternative Workcenters selection field.

Now, create a new manufacturing order that uses the main work center for one of its operations. The main work center will automatically be selected for the operation in the Work Orders tab. After confirming the manufacturing order, click the Plan button that appears at the top left of the form.

If the main work center is at capacity, the work center selected for the operation will be automatically changed to the alternative work center.

## Monitor work center performance¶

Performance for an individual work center can be viewed by selecting Configuration ‣ Work Centers, and clicking on a work center. A variety of metrics showing work center performance can be viewed at the top right of the form:

  * OEE: overall effective efficiency, the percentage of time that the work center has been fully productive

  * Lost: the amount of time lost due to work stoppages

  * Load: the amount of time it will take to complete the current workload

  * Performance: the real duration of work time, shown as a percentage of the expected duration




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_order_dependencies.html "Work order dependencies") |
  * [precedente](sub_assemblies.html "Manage semi-finished products") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Manage work orders using work centers


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
  *[FBM]: Fulfilled By Merchant
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