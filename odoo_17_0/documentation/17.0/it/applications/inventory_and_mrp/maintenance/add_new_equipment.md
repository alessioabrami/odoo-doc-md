# Add new equipment — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_calendar.html "Maintenance calendar") |
  * [precedente](../maintenance.html "Manutenzione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Add new equipment



# Add new equipment¶

In Odoo, _equipment_ refers to any item that is used in everyday operations, including the manufacturing of products. This can mean a piece of machinery on a production line, a tool that is used in different locations, or a computer in an office space. Equipment registered in Odoo can be owned by the company that uses the Odoo database, or by a third party, such as a vendor in the case of equipment rentals.

Using Odoo _Maintenance_ , it is possible to track individual pieces of equipment, along with information about their maintenance requirements. To add a new piece of equipment, navigate to the Maintenance module, select Equipments ‣ Machines & Tools ‣ Create, and configure the equipment as follows:

  * Equipment Name: the product name of the piece of equipment

  * Equipment Category: the category that the equipment belongs to; for example, computers, machinery, tools, etc.; new categories can be created by navigating to Configuration ‣ Equipment Categories and clicking Create

  * Company: the company that owns the equipment; again, this can be the company that uses the Odoo database, or a third-party company

  * Used By: specify if the equipment is used by a specific employee, department, or both; select Other to specify both an employee and a department

  * Maintenance Team: the team responsible for servicing the equipment; new teams can be created by navigating to Configuration ‣ Maintenance Teams and selecting Create; the members of each team can also be assigned from this page

  * Technician: the person responsible for servicing the equipment; this can be used to assign a specific individual in the event that no maintenance team is assigned or when a specific member of the assigned team should always be responsible for the equipment; any person added to Odoo as a user can be assigned as a technician

  * Used in location: the location where the equipment is used; this is a simple text field that can be used to specify locations that are not work centers, like an office, for example

  * Work Center: if the equipment is used at a work center, specify it here; equipment can also be assigned to a work center by navigating to Maintenance ‣ Equipments ‣ Work Centers, selecting a work center or creating a new one using the Create button, and clicking the Equipment tab on the work center form




## Include additional product information¶

The Product Information tab at the bottom of the page can be used to provide further details about the piece of equipment:

  * Vendor: the vendor that the equipment was purchased from

  * Vendor Reference: the reference code assigned to the vendor

  * Model: the specific model of the piece of equipment

  * Serial Number: the unique serial number of the equipment

  * Effective Date: the date that the equipment became available for use; this is used to calculate the MTBF

  * Cost: the amount the equipment was purchased for

  * Warranty Expiration Date: the date on which the equipment’s warranty will expire




## Add maintenance details¶

The Maintenance tab at the bottom of the page provides information about the failure frequency of the piece of equipment:

  * Expected Mean Time Between Failure: the average number of days the equipment is expected to operate between failures. This number can be configured manually.

  * Mean Time Between Failure: the average number of days the equipment operates between failures. This number is calculated automatically based on previous failures, and cannot be configured manually.

  * Estimated Next Failure: the estimated date the equipment may experience its next failure. This date is calculated automatically based on the data in the Mean Time Between Failure and Latest Failure fields, and cannot be configured manually.

  * Latest Failure: the most recent date on which the equipment failed. This date is based on the creation date of the equipment’s most recent maintenance request, and cannot be configured manually.

  * Mean Time To Repair: the average number of days needed to repair the equipment. This number is calculated automatically based on the duration of previous maintenance requests, and cannot be configured manually.




Suggerimento

To see any open maintenance requests for a piece of equipment, go to the page for the equipment, and click the Maintenance smart button at the top of the page.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/maintenance/add_new_equipment.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](maintenance_calendar.html "Maintenance calendar") |
  * [precedente](../maintenance.html "Manutenzione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Add new equipment


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