# Maintenance setup — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../plm.html "Product lifecycle management") |
  * [precedente](maintenance_requests.html "Maintenance requests") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance setup



# Maintenance setup¶

Odoo _Maintenance_ helps companies schedule corrective and preventive maintenance on equipment used in their warehouse. This helps companies avoid equipment breakdowns, blocks in warehouse work centers, and emergency repair costs.

## Maintenance teams¶

When creating maintenance requests, a _maintenance team_ can be assigned to the request as the team responsible for handling the request.

To view existing maintenance teams, navigate to Maintenance app ‣ Configuration ‣ Maintenance Teams.

From the resulting Teams page, a list of all existing teams (if any) is displayed, with the Team Name, Team Members, and Company listed in the columns, by default.

To add a new team, click New. This adds a blank line at the bottom of the list of teams. In the blank field that appears below the Team Name column, assign a name to the new maintenance team.

In the Team Members column, click the field to reveal a drop-down menu with existing users in the database. Choose which users should be members of the new maintenance team.

Click Search More… to open a Search: Team Members pop-up window to search for users **not** shown on the initial drop-down menu.

In the Company column, if in a multi-company environment, click the drop-down menu to select the company in the database to which this new maintenance team belongs.

Once ready, click Save to save changes.

Suggerimento

The team members assigned to maintenance teams are also referred to as _Technicians_ , when viewing the _Maintenance Calendar_.

Navigate to Maintenance app ‣ Maintenance ‣ Maintenance Calendar, and click on an existing maintenance request. From the resulting popover, locate the Technician field. The name listed in the field is the team member, and is the user responsible for that particular request.

At the far-right side of the page is a sidebar column, containing a minimized calendar set to today’s date, and a Technician list, displaying all the technicians (or team members) with requests currently open.

## Attrezzatura¶

In Odoo _Maintenance_ , _equipment_ refers to machines and tools used internally in warehouse work centers. Equipment can include technology such as computers or tablets, power tools, machines used for manufacturing, and more.

### Equipment categories¶

Each piece of equipment belongs to an _equipment category_. Before adding new equipment, make sure that a fitting equipment category is created.

To create a new equipment category, navigate to Maintenance app ‣ Configuration ‣ Equipment Categories, and click New. Doing so opens a blank equipment category form.

On the blank form, assign a name in the Category Name field.

In the Responsible field, assign a user to be responsible for the equipment in this category, if necessary. By default, the user who creates the category is selected as Responsible, by default.

If in a multi-company environment, click the drop-down menu in the Company field, and select the company in the database to whom the equipment in this category belongs.

In the Email Alias field, assign an email alias to this category, if necessary.

In the Comments field, type any comments or notes for internal users to reference in relation to this category, if necessary.

Nota

Once a new equipment category is created, all equipment belonging to that category, as well as any past or currently open maintenance requests, are available from the equipment category form.

Navigate to Maintenance app ‣ Configuration ‣ Equipment Categories, and select a category to view. Locate the Equipment and Maintenance smart buttons at the top of the form.

Click the Equipment smart button to view all equipment belonging to this category. Click the Maintenance smart button to view any past, or currently open, maintenance requests.

### Machines & tools¶

To add new equipment, navigate to Maintenance app ‣ Equipment ‣ Machines & Tools, and click New. This opens a blank equipment form.

In the Name field, assign a name for the new equipment. In the Equipment Category field, click the drop-down menu and select which category this new equipment should belong to.

If in a multi-company environment, click the drop-down menu in the Company field, and select the company in the database to whom the new equipment belongs.

In the Used By field, select from one of three radio button options: Department, Employee, or Other.

If Department is selected, a Department field appears below the Used By field. Click the drop-down menu and select the department that uses this equipment.

If Employee is selected, an Employee field appears below the Used By field. Click the drop-down menu, and select the employee who uses this equipment.

If the Other option is selected, both the Department and Employee fields appear below the Used By field. Click the drop-down menus for the respective fields, and choose which department and employee uses this equipment.

In the Maintenance Team field, select the team responsible for this equipment. In the Technician field, select the team member/user responsible for this equipment.

In the Used in location field, enter the location wherein this equipment will be used, if not in an internal work center (e.g. in an office).

In the Work Center field, click the drop-down menu, and select which work center this equipment will be used in.

In the blank space under the Description tab at the bottom of the form, add any relevant information describing the equipment for users to reference.

#### Product Information tab¶

To add any relevant information while creating a new piece of equipment, from the equipment form, click the Product Information tab.

In the Vendor field, add the vendor from which the equipment was purchased. In the Vendor Reference field, add the product reference number obtained from the vendor, if applicable.

In the Model field, specify which model this equipment is, if applicable. If the equipment is serialized, add a serial number in the Serial Number field.

In the Effective Date field, click the date to reveal a calendar popover, and select a date. This date indicates when this equipment was first put in use, and will be used to compute the Mean Time Between Failure (MTBF) in the equipment’s Maintenance tab.

In the Cost field, specify how much the equipment cost to acquire, if applicable.

If the equipment is covered under a warranty, specify the Warranty Expiration Date by selecting a date from the calendar popover in that field.

#### Maintenance tab¶

Various maintenance metrics are available for each piece of equipment, and are automatically computed, based on corrective maintenance, and planned preventive maintenance.

To view the maintenance metrics for a specific piece of equipment, from the equipment form, click the Maintenance tab.

Doing so reveals the following fields:

  * Expected Mean Time Between Failure: the amount of time (in days) before the next failure is expected. This is the **only** field not greyed-out, and the **only** field users can edit.

  * Mean Time Between Failure: the amount of time (in days) between reported failures. This value is computed based on completed corrective maintenances.

  * Estimated Next Failure: the date on which the next failure is expected. This date is computed as the Latest Failure Date + MTBF.

  * Latest Failure: The date of the latest failure. The value in this field updates once a failure is reported for this equipment.

  * Mean Time To Repair: the amount of time (in days) it takes to repair this equipment upon failure. This value updates once a maintenance request is completed for this equipment.




## Work centers¶

To view the work centers where equipment is being used, and how the equipment is being used in them, navigate to Maintenance app ‣ Equipment ‣ Work Centers, and click into a work center.

From the resulting work center form, click the Equipment tab to view all machines and tools being used in that specific work center.

Each piece of equipment is listed with certain relevant information: the Equipment Name, the responsible Technician, the Equipment Category it belongs to, and a few important maintenance metrics: its MTBF, MTTR, and Est. Next Failure date.

Suggerimento

To add new equipment to a work center directly from the work center form, click Add a line under the Equipment tab. This opens an Add: Maintenance Equipment pop-up window.

From the pop-up window, select the equipment that should be added to the work center, and click Select.

Vedi anche

[Add new equipment](add_new_equipment.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/maintenance/maintenance_setup.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../plm.html "Product lifecycle management") |
  * [precedente](maintenance_requests.html "Maintenance requests") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Manutenzione](../maintenance.html) »
  * Maintenance setup


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