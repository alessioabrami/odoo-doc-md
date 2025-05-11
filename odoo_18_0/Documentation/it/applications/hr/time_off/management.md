# Amministrazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../recruitment.html "Selezione del personale") |
  * [precedente](my_time.html "My time") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Amministrazione



# Amministrazione¶

Time off and allocation requests undergo an approval process before being granted. Requests either need one or two approvals, if any, depending on how the specific type of time off is configured. All these configurations can be found under the _Management_ section of the _Time Off_ application.

Only people who can approve allocation and time off requests have the Management section visible in the _Time Off_ application.

## Manage time off¶

To view time off requests that need approval, navigate to Time Off app ‣ Management ‣ Time Off. Doing so reveals the All Time Off page.

The only time off requests that are visible on this page belong to employees the user either has Time Off Officer or Administrator access rights for in the _Time Off_ application.

The default filter on the All Time Off page is `Waiting For Me`.

This filter only presents time off requests that need to be approved for current employees on the user’s team, with a status of either To Approve or Second Approval.

On the left side of the All Time Off page, there are various grouping options that can be used to narrow down the presented time off requests, located beneath the Status and Department headings.

Since only time off requests that need to be approved are shown, the only Status options are All, To Approve, and Second Approval.

The various departments the user is a member of, and manages employees under, also appear on the left side of the page, under Departments.

Nota

If there are no requests that fall under one of the status options or departments, that status or department is **not** visible on the left-side menu.

To only display time off requests for specific departments, click on the Department on the left-hand side of the page. Only requests within the selected department are then presented.

The status column displays the status of each request, with the status highlighted in a specific color.

The To Approve and Second Approval requests are highlighted in yellow, and are the only ones that appear in the list by default.

If the `Waiting For Me` filter is removed, all statuses appear.

Approved requests are highlighted in green, To Submit (drafts) requests are highlighted in blue, and the Refused requests are highlighted in gray.

To approve a time off request, click the __ Approve button at the end of the line.

To validate a time off request that has already been approved, and is waiting on a second approval, click the __ Validate button at the end of the line.

To refuse a request, click the __ Refuse button at the far end of the line.

For more details, click anywhere on the time off request line (except for the __ Approve, __ Validate icon, and __ Refuse buttons). Doing so loads that specific time off request form. Depending on the rights of the user, changes can be made.

To modify the request, make any desired changes to the form. All changes are automatically saved.

It is also possible to approve, validate, or refuse the request from this form. Click the Approve button to approve, the Validate button to validate, or the Refuse button to refuse the request.

## Manage allocations¶

To view allocations that need approval, navigate to Time Off app ‣ Management ‣ Allocations. Doing so reveals the Allocations page.

The user is only presented with allocations for employees they have either Time Off Officer or Administrator access rights for in the _Time Off_ application.

The default filters configured on the Allocations page are My Team and Active Employee. These default filters _only_ present employees on the user’s team (who they manage) and active employees. Inactive records are not shown.

The left side of the Allocations page has various grouping options to narrow down the presented allocation requests.

The Status options are: All, To Approve, Refused, and Approved. Click on a specific Status to view only requests with that specific status.

To view all allocation requests, regardless of status, click All under the Status heading.

It is also possible to display allocation requests by department. Click on the desired Department on the left side of the Allocations page, to only present allocations for that specific department.

Nota

The groupings on the left side **only** present allocation requests that fall under the default filters of My Team and Active Employee, if those default filters are not removed from the Search… bar. Only the statuses for allocation requests that fall under those filters are presented on the left side.

For example, if there are no requests with a status of To Submit, that status option does not appear in the left-hand side of the Allocations page.

All departments for the user’s employees appear in the list. If there are no allocation requests that fall under that department matching the preconfigured filters, the list is blank.

It is always possible to remove any of the preconfigured filters, by clicking the __(remove) icon on the specific filter to remove it.

The status column displays the status of each request, with the status highlighted in a specific color.

The To Approve requests are highlighted in yellow, Approved requests are highlighted in green, and the Refused requests are highlighted in gray.

To approve an allocation request, click the __ Validate button at the end of the line. To refuse a request, click the __ Refuse button.

If more details are needed, click anywhere on the allocation request line (except for the __ Validate or __ Refuse buttons) to view the specific request in detail, via the allocation request form.

Depending on the rights of the user, changes can be made to the allocation request form that appears. To modify the request, make any desired changes to the form. All changes are automatically saved.

It is also possible to approve or refuse the request from this form. Click the Validate button to approve, or the Refuse button to refuse the request.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/time_off/management.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../recruitment.html "Selezione del personale") |
  * [precedente](my_time.html "My time") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Amministrazione


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