# Project dashboard — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tasks.html "Task management") |
  * [precedente](project_management.html "Project management") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Servizi](../../services.html) »
  * [Progetto](../project.html) »
  * Project dashboard



# Project dashboard¶

The project dashboard allows you to get a comprehensive overview of your project’s status. It displays information such as the total number of tasks, timesheets, and planned hours linked to the project, as well as detailed information about project milestones and its costs and revenues. Within the project dashboard, you can create Project updates, which allow you to take a snapshot of the project’s status at a certain point in time. As such, it is a crucial tool for effective project management and ensuring that your project stays on track.

## Using the project dashboard¶

To access the project dashboard, open the **Project** app and hover over the desired project’s card. Then, click the __( vertical ellipsis) icon and select Dashboard.

The left side of the dashboard displays a list of existing project updates, and the right side provides detailed information about records linked to the project, as well as milestones, profitability, and budgets.

Nota

The information displayed on the project dashboard varies depending on the applications installed on your database. For example, you will not see information about **Timesheets** , **Planning** , or **Purchase Orders** if the corresponding applications are not installed.

### Totals smart buttons¶

The following smart buttons are displayed on the top left of the project dashboard:

>   * Tasks: the number of completed (i.e., Done or Canceled [tasks](tasks/task_stages_statuses.html#project-tasks-task-stages-statuses-statuses)) and all tasks, in format completed/all, as well as the entire project’s completion percentage estimation.
> 
>   * Timesheets: the number of hours or days (depending on the **Timesheets** app configuration) linked to the project. This includes all [timesheets](../timesheets.html), whether or not they have been validated.
> 
>   * Planned: the number of hours that have been planned for shifts in the **Planning** app. This includes all [planned shifts](../planning.html), including past shifts and shifts that have not yet been published.
> 
>   * Documents: number of [documents](../../productivity/documents.html) in the project’s workspace.
> 
>   * Burndown Chart: click the smart button to access a [report](../../essentials/reporting.html) on the status of the project’s tasks over time.
> 
>   * Timesheets and Planning: click the smart button to access a [report](../../essentials/reporting.html) on the project’s timesheets and shifts.
> 
>   * **Additional fields** , such as Sales Orders, Sales Order Items, Purchase Orders, and more, represent the number of records linked to the project.
> 
> 


Suggerimento

Use the project dashboard smart buttons to update the project records easily. Click Timesheets to validate timesheets, Planned to create project planning, Documents to view and validate documents, etc.

### Milestone¶

This section is only visible if [milestones](../../sales/sales/invoicing/milestone.html) have been created for this project. Click Add Milestone to create a new milestone. Click a milestone in the checklist to edit it, enable its checkbox to mark it as completed, or click the __( trash) icon to remove it.

### Redditività¶

This section only applies to billable projects and provides a breakdown of project costs and revenues.

### Budget¶

If a budget has been set for the project, its status and related details are displayed in this section. Click Add Budget to create a new budget for the project.

Nota

[Analytic accounting](../../finance/accounting/reporting/analytic_accounting.html) must be enabled in your database’s **Accounting** application in order for this section to be displayed.

## Project updates¶

Project updates allow you to take a snapshot of the project’s overall status at a given point in time, for example, during a periodic (weekly, bi-weekly, or monthly) review. This allows you to compare specific data points, note any aspects of the project that need improvement, and estimate if the project is on or off track.

To create a new project update, go to the project dashboard, click New, and fill in the following fields:

>   * Status: Choose between On Track, At Risk, Off Track, On Hold, and Done. Once the status is set, a color-coded dot is displayed on the project’s Kanban card, allowing the project manager to easily identify which projects need attention.
> 
>   * Progress: Manually input the completion percentage based on the project’s progress.
> 
>   * Date and Author: These fields are automatically filled in with appropriate information based on the user who created the update and the current date.
> 
>   * Description: Use this rich-text field to gather notes. Depending on the project configuration (e.g., if the project is billable), this field may be pre-filled with current information on aspects such as profitability, budget, milestones, etc.
> 
> 


[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/project/project_dashboard.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tasks.html "Task management") |
  * [precedente](project_management.html "Project management") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Servizi](../../services.html) »
  * [Progetto](../project.html) »
  * Project dashboard


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[RFQ]: request for quotation
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
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: Valori separati da virgola