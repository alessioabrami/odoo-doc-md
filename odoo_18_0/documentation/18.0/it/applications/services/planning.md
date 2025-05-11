# Pianificazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](field_service.html "Assistenza sul campo") |
  * [precedente](timesheets/overview/time_off.html "Create Timesheets upon Time Off Validation") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Servizi](../services.html) »
  * Pianificazione



# Pianificazione¶

**Odoo Planning** allows you to plan your team’s schedule and manage shifts and resources.

Handling your team’s planning comes with specific requirements that may vary widely depending on your business needs. The following concepts were introduced in Odoo Planning to meet those needs:

**Shifts** are dispatched to **resources** , which can be either human (employees) or material (e.g., equipment). The resources are assigned roles, which allows for organization of work within the team.

Once the initial configuration is done, planning shifts can be done manually or automated by using the Auto Plan feature.

An integration between the Planning and Sales apps allows the linking of sold services to roles and shifts in Planning. Additionally, integration with [Project](project.html) allows dedicating shifts, and thus time and resources, to specific projects.

Vedi anche

[Odoo tutorials: Planning](https://www.odoo.com/slides/planning-60)

## Configurazione¶

### Ruoli¶

To define the roles your resources perform (e.g., chef, bartender, waiter), go to Planning ‣ Configuration ‣ Roles, then click New, and fill in the Name (e.g., assistant, receptionist, manager). Then, choose the Resources that will perform this role. Resources can be either Employees or Materials.

Nota

  * If the Sales app is installed in your database, the Services field appears, allowing you to specify which roles are needed to perform services so that the shifts are dispatched to the right person.

  * Roles are taken into account when using the Auto Plan feature.




#### Property fields and roles¶

**Property fields** allow you to add custom fields to forms across several Odoo applications. Planning includes the possibility of adding property fields linked to roles to shifts.

To create a property field, switch to the list view from any schedule. From there, click View on the shift that you wish to edit. If the Role field is empty, fill it in with the desired role, then click the cog icon and select Add Properties. [Configure](../productivity/knowledge/properties.html) the new field according to your needs.

The property field is linked to the role and is included in the shift form of all shifts performed by this role.

Example

Some of the use cases of role property fields include:

  * **Accreditation** : for roles that require a specific permit (e.g., driving license)

  * **Location** : in companies that operate in multiple locations (e.g., shops or restaurants)

  * **Language** : in a multi-lingual environment (e.g., consulting company)




### Dipendenti¶

All employees can be included in the planning and assigned shifts.

To adapt the employee’s planning settings, go to Planning ‣ Configuration ‣ Employees, and choose the employee for whom you want to edit the settings. Then, go to the Work Information tab.

Suggerimento

You can do the same from the **Employees** app, which is installed by default along with Planning.

Two sections of the employee’s Work Information tab have an impact on Planning: Schedule (namely, the Working Hours field) and Planning.

#### Working hours¶

The Working Hours are taken into account when the Allocated Time and its percentage is calculated for shifts. If the Working Hours field is left blank, the employee is considered to be working flexible hours.

To create individual Working Hours, for example, for employees working part-time, click Search more…, then New.

Nota

The Working Hours and the Allocated Time in Planning can impact **Payroll** , if the employee’s contract is configured to generate work entries based on shifts.

Vedi anche

[Payroll documentation on working schedules](../hr/payroll.html#payroll-working-times)

#### Planning roles¶

Once an employee has one or more Roles:

  * When creating a shift for this employee, only the shift templates from the roles chosen in this field are displayed.

  * When a schedule is published, the employee is only notified of open shifts for the roles that are assigned to them.

  * When auto-assigning open shifts or planning sales orders, the employee is only assigned shifts for the roles assigned to them.




Additionally, when a Default role is defined:

  * When creating a shift for the employee, the default role is automatically selected.

  * This role also has precedence over the other roles of the employee when auto-assigning open shifts or planning sales orders.




Nota

If the Planning roles fields are left empty, there are no restrictions in the shift templates and open shifts shared with the employee. However, it’s not possible to use the **Auto Plan** feature for employee with no roles.

### Materiali¶

**Materials** are resources that can be assigned shifts and working hours but are not employees. For example, a construction company could use materials to create shifts for shared machines (e.g., cranes, forklifts).

Similarly to employees, materials can be assigned roles and working time.

### Shift templates¶

To create a shift template, click New on any schedule, then fill in the details of the shift. In order for the shift to be saved as a template, tick Save as Template.

Alternatively, you can go to Planning ‣ Configuration ‣ Shift Templates, then click New. Fill in the Start Hour and Shift Duration. The shift’s End Time is then calculated based on the Working Hours, taking into account working time as well as breaks.

Example

The employee’s working hours are Monday to Friday, 8 am to 5 pm, with a break between 12 and 1 pm.

  * Creating a shift template with a start hour of 9 am and a duration of 8 hours will result in the end hour being 5 pm, based on the working hours and the 1-hour break.

  * Creating a shift template with a start hour of 10 am and a duration of 10 hours will result in the end hour of 10 am the following day, as the company is closed at 5 pm according to the working hours.




Additionally, for each shift template, you can also configure:

  * Role: to link the shift to this specific role.

  * Project: to keep track of shifts that are dedicated to work on a project.




## Planning shifts¶

On opening the Planning app, the users see their own schedule. Users with admin roles can also see Schedule by Resource, Role, Project, or Sales Order, as well as reporting and configuration menus.

Nota

The schedule is displayed in the Gantt view, which allows you to edit (with a drag and drop), resize, split, and duplicate shifts without having to open them.

The following visual elements are used on the shifts in the schedules:

  * **Full color** : shifts that are planned and published.

  * **Diagonal stripes** : shifts that are planned but have yet to be published.

  * **Grayed-out background** : employees that are on time off.

  * **Progress bar** : currently ongoing shifts with timesheets linked to them.

  * **Grayed-out shift** : when copying shifts, the copied shifts are shown in full color, whereas previously existing shifts are temporarily greyed out. The color changes back to full color or diagonal stripes on the next refresh of the page or by removing the filter.




### Create a shift¶

To create a shift, go to any schedule, then click New. In the pop-up window that opens, fill in the following details:

  * **Templates** : If there is one or more templates existing in your database, they are displayed in the upper section of the pop-up window. Once selected, a template prefills the shift form accordingly.

  * Resource: Resources can be both employees or materials. If this field is left empty, the shift is considered an open shift.

  * Role: Select the role that the resource assigned will be performing. This field is used when auto-planning shifts. Once you select a role, the shift templates associated with it are displayed in the upper section of the pop-up window.

  * Project: If the Project app is installed in your database, this field allows you to link the project to the shift is available, allowing you to plan and track shifts dedicated to work on the selected project.

  * Sales Order Item: If the Sales app is installed in your database, this field allows you to link a sales order to the shift.

  * Repeat: Tick the checkbox and configure the Repeat Every field according to your needs. The following rules apply to recurring shifts:

    * All fields (e.g., Resource, Role, Project) are copied from the original shift except for the date, which is adjusted according to the Repeat Every field.

    * Recurrences are planned but not published.

    * By default, planned shifts are created six months in advance, after which they are created gradually. To change the time frame, [activate the Developer mode](../general/developer_mode.html#developer-mode), then go to Planning ‣ Configuration ‣ Settings and edit the Recurring Shifts.

  * Save as Template: When this option is ticked, a shift template is created with the same Start and End hours, Allocated time, Role, and Project.

  * Additional note sent to the employee: Click on the field to add a note.

  * Date: Choose the date and time of your shift. This is the only mandatory field when creating a shift.

  * Allocated time: Is calculated based on the date and the employee’s Working Schedule. See more in Shift Templates.




Click Publish & Save to confirm the shift and send the assigned employee their schedule by email.

Nota

The draft is visible on the admin planning view and can be identified by diagonal lines. The employee is only notified of the shift once it’s published.

Two kinds of notifications are sent to the employees depending on their account configuration:

  * Employees without user accounts are redirected to a dedicated **Planning portal**.

  * Employees with a user account are redirected to the My Planning view in the backend view of Odoo.




Suggerimento

The **split shifts** tool allows to easily split a long shift into segments. To do so, hover the mouse over the desired shift and click the __( scissors) icon.

### Open shifts and auto planning¶

The Auto Plan button allows you to assign **Open shifts** (shifts with no resource assigned) and create and assign shifts linked to sales orders or project.

The following features have an impact on auto planning:

  * **Roles** : Open shifts are only assigned to resources (employees or materials) that have the corresponding role assigned. It is not possible to use the Auto Plan feature for employee with no roles.

  * **Default roles** : The default role assigned to a resource is given priority over the other roles they have assigned to them.

  * **Conflicts** : Employees or materials cannot be assigned multiple shifts at the same time.

  * **Time off** : The employees’ time off is taken into account, as well as public holidays.

  * **Working hours** : Are taken into account when assigning shifts to employees or materials. It is not possible to use the Auto Plan feature for an employee who is working flexible hours.

  * **Contracts** : If the employee has an active contract, they won’t be assigned shifts that fall outside of their contract period.




Click Publish to confirm the schedule and notify the employees of their planning.

### Switching shifts and unassignment¶

Two features are available to allow employees to make changes to their schedule: **switching shifts** and **unassignment**.

Nota

These features are mutually exclusive. Switching shifts is possible by default and cannot be disabled. However, once the **Allow unassignment** feature is enabled, it replaces the option to switch shifts.

#### Switching shifts¶

Once shifts are planned and published, employees receive an email notification. If an employee wishes to switch a shift, they can click the unwanted shift and click Ask to switch.

The shift remains assigned to the original employee, but in the schedule, a notification informing that the assigned employee would like to switch shifts is visible on the shift.

The shift is then displayed to other employees who share the same role, and if they wish to assign it to themselves, they can click the I take it button.

Nota

The following rules apply:

  * Only the shifts matching the employee’s roles are displayed as available to them.

  * Switching shifts is not available for shifts in the past.




#### Unassignment¶

To allow employees to unassign themselves from shifts, go to Planning ‣ Configuration ‣ Settings, then tick the checkbox Allow Unassignment. Then, specify the maximum number of days that the employees can unassign themselves before the shift.

Once shifts are planned and published, employees receive an email notification. If shift unassignment is allowed, the employees can click the I am unavailable button, and the shift reverts to an open shift.

Nota

The following rules apply:

  * Only the shifts matching the employee’s roles are displayed in their schedule.

  * Unassigning shifts is not available for shifts in the past.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/services/planning.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](field_service.html "Assistenza sul campo") |
  * [precedente](timesheets/overview/time_off.html "Create Timesheets upon Time Off Validation") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Servizi](../services.html) »
  * Pianificazione


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
  *[CSV]: Valori separati da virgola
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