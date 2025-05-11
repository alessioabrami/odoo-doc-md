# Task creation — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recurring_tasks.html "Recurring tasks") |
  * [precedente](task_stages_statuses.html "Task stages and statuses") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Progetto](../../project.html) »
  * [Task management](../tasks.html) »
  * Task creation



# Task creation¶

Tasks in Odoo Project can be created manually or automatically, including from emails or website forms.

## Manual task creation¶

Open the Project app and choose the desired project. Create a new task by doing one of the following:

>   * Clicking the __( plus) button in the upper left corner. This creates a new task in the first stage of your Kanban view.
> 
>   * Pressing the __( plus) button next to the Kanban stage name. This creates a new task in this Kanban stage.
> 
> 


Fill in the Task Title and add one or more Assignees, then click Add.

### Task configuration¶

Click the task to open it. The task form includes the following fields that you can fill in:

>   * Task Title: title of the task.
> 
>   * __( Star): click the __( star) icon to mark the task as high priority. The icon will turn yellow. Click it again to remove the high priority.
> 
>   * Project: the project that this task belongs to.
> 
>   * Assignees: the person(s) in charge of handling the work on this task.
> 
>   * Tags: custom labels allowing to categorize and filter your tasks.
> 
>   * Customer: the person or company that will be billed for this task. This field only appears in tasks that belong to billable projects.
> 
>   * Sales Order Item: this can be either the sales order that was used to create this task, or a sales order that was linked to this task manually. This field only appears in tasks linked to billable projects.
> 
>   * Allocated Time: the amount of time that the work on this task is expected to last, tracked by timesheets.
> 
>   * Deadline: the expected end date of the task. Once this field is filled in, you can also add a start date to designate the entire time frame of the tasks” duration.
> 
> 


Suggerimento

  * You can also create new tasks by switching to the list or Gantt view and clicking New.

  * The following fields can also be edited directly from the Kanban view without opening the individual task: __(**priority**), Allocated hours, Assignees, and **task status**. You can also **color code** or Set a Cover image to your task by clicking the __(**vertical ellipsis**).

  * You can use the following keyboard shortcuts in the task title to configure new tasks (modify the values in the examples below according to your needs):

    * **30h** : to allocate 30 hours to the task.

    * **#tags** : to add tags to the task.

    * **@user** : to assign the task to a user.

    * **!** : to star the task as high priority.

Along with using the correct format, follow this order: the task’s name, followed by the allocated time, the tags, the assignee, and then the priority.

For example, if you want to create a task named «Prepare workshop», allocate 5h hours to it, add the «School» tag, assign it to Audrey and set its priority to High, enter the following task title: Prepare workshop 5h #school @Audrey !




## Creating tasks from an email alias¶

This feature allows for project tasks to be automatically created once an email is delivered to a designated email address.

To configure it, open the Project app, then click the __( vertical ellipsis) icon next to the desired project’s name. Select Settings, then open the Settings tab.

Fill in the Create tasks by sending an email to field as follows:

>   * **Section of the alias before the @ symbol** : type the name of the email alias, e.g. `contact`, `help`, `jobs`.
> 
>   * **Domain** : in most cases, this is filled in by default with your [domain](../../../general/email_communication.html).
> 
>   * **Accept Emails From** : refine the senders whose emails will create tasks in the project.
> 
> 


Once configured, the email alias can be seen under the name of your project on the Kanban dashboard.

When an email is sent to the alias, the email is automatically converted into a project task. The following rules apply:

  * The email sender is displayed in the Customer field.

  * The email subject is displayed in the Task Title field.

  * The email body is displayed in the Description field.

  * The whole content of the email is additionally displayed in the **chatter**.

  * All the recipients of the email (To/Cc/Bcc) that are Odoo users are automatically added as **followers** of the task.




## Creating tasks from a website form¶

If you have the Website app installed in your database, you can configure any form on your website to trigger the creation of tasks in a project.

  1. Go to the website page where you wish to add the the form and [add the Form building block](../../../websites/website/web_design/building_blocks.html#websites-website-web-design-building-blocks).

  2. In the website editor, edit the following fields:

     * Action: select Create a Task.

     * Project: choose the project that you want the new tasks to be created in.

  3. [Customize the form](../../../websites/website/web_design/building_blocks/dynamic_content.html#website-dynamic-content-form).




When the form is submitted, it automatically creates a project task. The task’s content is defined by the form’s corresponding fields.

Vedi anche

[Dynamic website content](../../../websites/website/web_design/building_blocks/dynamic_content.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/project/tasks/task_creation.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recurring_tasks.html "Recurring tasks") |
  * [precedente](task_stages_statuses.html "Task stages and statuses") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Progetto](../../project.html) »
  * [Task management](../tasks.html) »
  * Task creation


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