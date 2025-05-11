# Work approvals and overtime — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](hardware.html "Hardware") |
  * [precedente](kiosks.html "Kiosks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Presenze](../attendances.html) »
  * Work approvals and overtime



# Work approvals and overtime¶

Odoo’s **Attendances** app requires management oversight in order to ensure all logged attendances are correct, especially overtime hours and incomplete shifts.

## Management dashboard¶

All attendance records that require approval, typically due to overlapping work entries or unapproved time off, are managed from a centralized management dashboard. To access this, navigate to Attendances app ‣ Management.

The Management dashboard only displays attendance records for current employees that need to be approved, in a default list view. This is due to the two default filters in the search bar, the To Approve and Active Employees.

Each attendance record displays the following information:

  * Employee: the name of the employee

  * Check In: the date and time the employee checked in

  * Check Out: the date and time the employee checked out

  * Worked Time: the number of worked hours the employee logged

  * Worked Extra Hours: the amount of overtime worked

  * Extra Hours: the total extra hours logged

  * Overtime Status: the status of the attendance record. All attendance records that appear on this dashboard have a status of To Approve.




## Approvals and refusals¶

Attendance records can be approved and refused directly from the Management dashboard. At the far-right of each record, __ Approve and __ Refuse buttons appear. Click the corresponding button to either approve or refuse the logged attendance record.

Nota

When approving or refusing attendance records from the Management dashboard, it is **not** possible to view the details of the attendance record.

### Partial approvals¶

It is possible to approve a portion of the logged Extra Hours and not the full amount. To approve only a portion of overtime, click into an attendance record to view the details.

Click into the Extra Hours field and enter the amount of hours being approved. After editing the Extra Hours field, the Worked Extra Hours field becomes visible to display the difference between the Worked Time and Extra Hours fields.

Nota

The Worked Time field is the total hours the employee logged (the Worked Time and Extra Hours combined). For example, if an employee is scheduled to work eight hours, and worked five extra hours, the Worked Time is thirteen hours, and the Extra Hours is five hours. The worked Time field **cannot** be modified.

Click __ Approve to approve the updated Extra Hours. Once partially approved, the Worked Extra Hours field disappears, along with the __ Approve button. The difference in hours appears in the Extra Hours field.

Once overtime hours are partially approved, the status changes to Approved.

Importante

Once partial overtime is approved, it is still possible to deny overtime by clicking __ Refuse. The record can be modified as many times as needed.

Nota

Occasionally, verifying an employee’s location when checking-in may be needed. The method the employee checked-in to work is found on the individual record, in the Mode field.

The Mode field is not modifiable, as it only log the method the attendance record was created.

The possible options are:

  * Kiosk: the employee physically checked in or out using a [kiosk](kiosks.html) device. The employee was present at the kiosk to check-in.

  * Systray: the employee checked in or out [directly from the database](check_in_check_out.html). Depending on the IP Address displayed on the detailed attendance record, the employee’s location at the time of check-in can be determined.

  * Manual: the record was created manually in the **Attendances** app. This is typically done by management, to add a missing record.




## Create attendance records¶

When necessary, users with the required [access rights](../employees/new_employee.html#employees-work-info-tab) are able to create attendance records manually in the **Attendances** app. Some situations requiring this is when employees forget to check in and out for shifts, as employees cannot retroactively create attendance records.

To add a missing attendance record, navigate to Attendances app ‣ Overview. Click the New button in the upper-left corner. In the Create pop-up window, enter the following information on the form:

  * Employee: select the employee the record is being created for. The signed-in user populates this field, by default.

  * Check In: using the calendar modal, select the check in date and time, then click __ Apply. By default, the current date is selected, and the time is set to `00:00:00`.

  * Check Out: using the calendar modal, select the check out date and time, then click __ Apply. By default, the following date is selected, and the time is set to `00:00:00`.

  * Worked Time: this field is automatically populated with the difference from the selected Check In and Check Out times. This field **cannot** be modified.

  * Extra Hours: enter the number of overtime hours, if any, to be approved.




Importante

Once Extra Hours are added, they are automatically approved by the system. However, it is possible to manually refuse them, as explained in the Approvals and Refusals section.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/attendances/management.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](hardware.html "Hardware") |
  * [precedente](kiosks.html "Kiosks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Presenze](../attendances.html) »
  * Work approvals and overtime


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record