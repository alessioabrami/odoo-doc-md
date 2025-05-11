# Maintenance requests — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_setup.html "Maintenance setup") |
  * [precedente](maintenance_calendar.html "Maintenance calendar") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance requests



# Maintenance requests¶

In order to keep equipment and work centers functioning properly, it is often necessary to perform maintenance on them. This can include preventive maintenance, intended to prevent equipment from breaking down, or corrective maintenance, which is used to fix equipment that is broken or otherwise unusable.

In Odoo _Maintenance_ , users can create _maintenance requests_ to schedule and track the progress of equipment and work center maintenance.

## Create maintenance request¶

To create a new maintenance request, navigate to Maintenance app ‣ Maintenance ‣ Maintenance Requests, and click New.

Begin filling out the form by entering a descriptive title in the Request field (e.g., `Drill not working`).

The Created By field auto-populates with the user creating the request, but a different user can be selected by clicking on the drop-down menu.

In the For drop-down menu, select Equipment if the maintenance request is being created for a piece of equipment, or Work Center if it is being created for a work center.

Depending on the option selected in the For field, the next field is titled either Equipment or Work Center. Using the drop-down menu for either field, select a piece of equipment or a work center.

If the _Custom Maintenance Worksheets_ setting is enabled in the _Maintenance_ app’s settings, a Worksheet Template field appears below the Equipment or Work Center field. If necessary, use this field to select a worksheet to be filled out by the employee performing the maintenance.

The next field is titled Request Date, and is set by default to the date on which the maintenance request is created. This date cannot be changed by the user.

In the Maintenance Type field, select the Corrective option if the request is intended to fix an existing issue, or the Preventive option if the request is intended to prevent issues from occurring in the future.

If the request is being created to address an issue that arose during a specific manufacturing order (MO), select it in the Manufacturing Order field.

If an MO was selected in the Manufacturing Order field, a Work Order field appears below it. If the issue arose during a specific work order, specify it in this field.

In the Team field, select the maintenance team that is responsible for managing the request. If a specific team member is responsible, select them in the Responsible field.

The Scheduled Date field is used to specify the date on which maintenance should take place, and the time it should begin. Choose a date by clicking on the field to open a calendar in a pop-up window, and then select a day on the calendar. Enter an hour and minute in the two fields below the calendar, and click Apply to save the date and time.

The Duration field is used to specify the time it takes to complete the maintenance request. Use the text-entry field to enter the time in a `00:00` format.

If Work Center was selected in the For field, a Block Workcenter checkbox appears below the Duration field. Enable the checkbox to prevent work orders or other maintenance from being scheduled at the specified work center while the maintenance request is being processed.

The Priority field is used to communicate the importance (or urgency) of the maintenance request. Assign the request a priority between zero and three ⭐⭐⭐ (stars), by clicking on the desired star number. Requests assigned a higher priority appear above those with a lower priority, on the Kanban board used to track the progression of maintenance requests.

In the Notes tab at the bottom of the form, enter any relevant details about the maintenance request (why the maintenance issue arose, when it occurred, etc.).

The Instructions tab is used to include instructions for how maintenance should be performed. Select one of the three options, and then include the instructions as detailed below:

  * PDF: click the Upload your file button to open the device’s file manager, and then select a file to upload.

  * Google Slide: enter a Google Slide link in the text-entry field that appears after the option is selected.

  * Text: enter the instructions in the text-entry field that appears after the option is selected.




## Process maintenance request¶

Once a maintenance request has been created, it appears in the _New Request_ stage of the _Maintenance Requests_ page, which can be accessed by navigating to Maintenance app ‣ Maintenance ‣ Maintenance Requests.

Maintenance requests can be moved to different stages by dragging and dropping them. They can also be moved by clicking on a request to open it in a new page, and then selecting the desired stage from the stage indicator bar, located above the top-right corner of the request’s form.

Successful maintenance requests should be moved to the Repaired stage, indicating that the specified piece of equipment or work center is repaired.

Failed maintenance requests should be moved to the Scrap stage, indicating the specified piece of equipment, or work center, could not be repaired, and must instead be scrapped.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/maintenance/maintenance_requests.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_setup.html "Maintenance setup") |
  * [precedente](maintenance_calendar.html "Maintenance calendar") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance requests


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
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
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
  *[MTBF]: Mean Time Between Failures