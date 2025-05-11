# Allocazioni — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](request_time_off.html "Request time off") |
  * [precedente](../time_off.html "Ferie") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Allocazioni



# Allocazioni¶

Once [time off types](../time_off.html#time-off-time-off-types) and [accrual plans](../time_off.html#time-off-accrual-plans) have been configured, the next step is to _allocate_ , or give, time off to employees.

The _Allocations_ page of the **Time Off** app is **only** visible to users who have either _Time Off Officer_ or _Administrator_ access rights for the **Time Off** application. For more information on access rights, refer to the [access rights](../../general/users/access_rights.html) documentation.

## Allocate time off¶

To create a new allocation, navigate to Time Off app ‣ Management ‣ Allocations.

This presents a list of all current allocations, including their respective statuses.

Click New to allocate time off, and a blank Allocation form appears.

After entering a name for the allocation on the first blank field of the form, enter the following information:

  * Time Off Type: Using the drop-down menu, select the type of time off that is being allocated to the employees.

  * Allocation Type: Select either Regular Allocation or Accrual Allocation. If the allocation is **not** based on an [accrual plan](../time_off.html#time-off-accrual-plans), select Regular Allocation.

  * Accrual Plan: If Accrual Allocation is selected for the Allocation Type, the Accrual Plan field appears. Using the drop-down menu, select the accrual plan with which the allocation is associated. An accrual plan **must** be selected for an Accrual Allocation.

  * Validity Period/Start Date: If Regular Allocation is selected for the Allocation Type, this field is labeled Validity Period. If Accrual Allocation is selected for the Allocation Type, this field is labeled Start Date.

The current date populates the first date field, by default. To select another date, click on the pre-populated date to reveal a popover calendar window. Navigate to the desired start date for the allocation, and click on the date to select it.

If the allocation expires, select the expiration date in the next date field. If the time off does _not_ expire, leave the second date field blank. No Limit appears in the field if no date is selected.

If Accrual Allocation is selected for the Allocation Type, this second field is labeled Run until.

Importante

If the Start Date entered is in the middle of a period of time, such as the middle of the month, Odoo applies the allocation to the beginning or end of the period, depending on the _Accrued Gain Time_ entered on the [accrual plan](../time_off.html#time-off-accrual-plans) (either _At the start of the accrual period_ , or _At the end of the accrual period_) instead of the specific date entered.

For example, an allocation is created, and references an accrual plan that grants time _At the start of the accrual period_ , monthly, on the first of the month.

On the allocation form, the Allocation Type is set to Accrual Allocation, and the Start Date entered is `06/16/24`.

Odoo’s **Time Off** app retroactively applies the allocation to the beginning of the time period entered in the Start Date.

Therefore, this allocation accrues time from `06/01/24`, rather than `06/16/24`.

Additionally, if on the accrual form, the allocation references an accrual plan that grants time _`At the end of the accrual period_ , the allocation accrues time from `7/01/24` rather than `6/18/24`.

  * Allocation: Enter the amount of time that is being allocated to the employees. This field displays the time in either Hours or Days, depending on how the selected [Time Off Type](../time_off.html#time-off-time-off-types) is configured.

  * Add a reason…: If any description or note is necessary to explain the time off allocation, enter it in this field at the bottom of the form.




### Multiple Allocations¶

When allocating time off, it is common to allocate time to several employees at once. This is done using the Multiple Requests feature.

To allocate time to multiple employees in a single allocation, navigate to Time Off app ‣ Management ‣ Allocations. Then, click the __(Actions) icon in the upper-left corner, then click __ Multiple Requests. This reveals a Multiple Requests pop-up window.

This form is identical to the Allocation form, with an additional Mode field. The Mode field determines how multiple employees are selected.

Using the drop-down menu, select one of the following Modes:

  * By Employee: This option allows for the selection of multiple individual employees that are unrelated in terms of department, company, or tags. Selecting this reveals an Employees field. Select the employees to receive the allocation in the Employees field. There is no limit to the amount of employees that can be selected.

  * By Company: This option allows for the selection of all employees within a specific company. Selecting this reveals a Company field. Select the Company to assign the allocation to. Only one company can be assigned in the Company field. When a company is selected, _all_ employees within the company receive the allocation.

  * By Department: This option allows for the selection of all employees within a specific department. Selecting this reveals a Department field. Select the Department to assign the allocation to. Only one department can be assigned in the Department field. When a department is selected, _all_ employees within the department receive the allocation.

  * By Employee Tag: This option allows for the selection of all employees with a specific tag. Selecting this reveals an Employee Tag field. Select the desired Employee Tag to select all employees with that tag. Only one tag can be assigned in the Employee Tag field. When a tag is selected, _all_ employees with that tag receive the allocation.




Next, select the Time Off Type using the drop-down menu. Once a Time Off Type is selected, the placeholder name, “Allocation Request”, changes to the name of the selected Time Off Type, including the amount of days. Change the name of the allocation, if desired.

Fill out the remainder of the Multiple Requests form, then click Create Allocations when done.

## Request allocation¶

If an employee has used all their time off, or will run out of time off, they can request an allocation for additional time. Allocations can be requested in one of two ways, either from the [Dashboard](my_time.html#time-off-dashboard) or the [My Allocations](my_time.html#time-off-my-allocations) view.

To create a new allocation request, click either the New Allocation Request button on the main **Time Off** dashboard, or the New button in the My Allocations list view. Both buttons open a new allocation request form.

Nota

Both options open a new allocation request form, but when requested from the Dashboard, the form appears in a pop-up window, and the _Validity Period_ field does **not** appear. When requested from the My Allocations list view, the screen navigates to a new allocation request page, instead of presenting a pop-up window.

Enter the following information on the new allocation request form:

  * Time Off Type: Select the type of time off being requested for the allocation from the drop-down menu. After a selection is made, the title updates with the time off type.

  * Validity Period: By default, the current date populates this field, and it is **not** able to be modified. This field **only** appears when requesting an allocation from the My Allocations view (Time Off ‣ My Time ‣ My Allocations).

  * Allocation: Enter the amount of time being requested in this field. The format is presented in either Days or Hours, depending on how the Time Off Type is configured. Once this field is populated, the name of the allocation request is updated to include the amount of time being requested.

  * Add a reason…: Enter a description for the allocation request in this field. This should include any details that approvers may need to approve the request.




If the request was created from the Dashboard, click the Save & Close button on the New Allocation pop-up window to save the information and submit the request.

If the form was completed from the My Allocations list view, the information is automatically saved as it is entered. However, the form can be saved manually at any time by clicking the __(cloud upload) icon.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/time_off/allocations.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](request_time_off.html "Request time off") |
  * [precedente](../time_off.html "Ferie") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Allocazioni


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