# Helpdesk — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](helpdesk/overview.html "Panoramica") |
  * [precedente](field_service/worksheets.html "Fogli di lavoro") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Servizi](../services.html) »
  * Helpdesk



# Helpdesk¶

Odoo _Helpdesk_ is a ticketing-based customer support application. Multiple teams can be configured and managed in one dashboard, each with their own pipeline for tickets submitted by customers. Pipelines are organized in customizable stages that enable teams to track, prioritize, and solve customer issues quickly and efficiently.

## Create a Helpdesk team¶

To view or modify _Helpdesk_ teams, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. To create a new team, click the New button in the top-left of the dashboard.

On the blank Helpdesk team form, enter a Name for the new team. Then, enter a description of the team in the field below the team name, if desired. To change the company this team is assigned to, select it from the Company drop-down menu.

Importante

The team description is published on the public facing [website form](helpdesk/overview/receiving_tickets.html), where customers and portal users submit tickets. The description included in this field should **not** include any information that is for internal use only.

### Visibility & Assignment¶

The _Visibility_ settings alter which internal users and portal users have access to this team and its tickets. The _Assignment_ settings alter how users are assigned to handle each ticket.

#### Determine team visibility¶

Under the Visibility section, select one of the following options to determine who can view this team and its tickets:

  * Invited internal users (private): internal users can access the team and the tickets they are following. This access can be modified on each ticket individually by adding or removing the user as a follower. Internal users are considered _invited_ once they are added as followers to an individual ticket, or to the team itself.

  * All internal users (company): all internal users can access the team and all of its tickets.

  * Invited portal users and all internal users (public): all internal users can access the team and all of its tickets. Portal users can only access the tickets they are following.




Example

A `Customer Support` team, meant to handle general shipping and product issues, would have the visibility set on Invited portal users and all internal users.

At the same time, a `Financial Services` team handling tickets related to accounting or tax information would only need to be visible to Invited internal users.

Avvertimento

A team’s visibility can be altered after the initial configuration. However, if the team changes from public access to either private or company-only access, portal users are removed as followers from both the team, and from individual tickets.

#### Follow all team’s tickets¶

If a user should be notified about any updates regarding tickets for this team, select their name from the Followers drop-down menu, located in the Follow All Team’s Tickets field. Multiple users can be selected to follow a single team.

Importante

External contacts can be selected in the Followers field. If the team’s visibility is set to Invited internal users (private), followers are notified about updates to the team’s tickets, but are **not** able to view them in the portal.

#### Automatically assign new tickets¶

When tickets are received, they need to be assigned to a member of the team. This is done either manually on each ticket individually, or through Automatic Assignment. Check the Automatic Assignment checkbox to enable this feature for the team.

As soon as Automatic Assignment has been enabled, additional fields appear.

Select one of the following assignment methods, based on how the workload should be allocated across the team:

  * Each user is assigned an equal number of tickets: tickets are assigned to team members based on total ticket count, regardless of the number of open or closed tickets they are currently assigned.

  * Each user has an equal number of open tickets: tickets are assigned to team members based on how many open tickets they are currently assigned.




Nota

When Each user is assigned an equal number of tickets is selected, the overall number of tickets assigned to team members is the same, but it does **not** consider the current workload.

When Each user has an equal number of open tickets is selected, it ensures a balanced workload among team members, as it takes the current number of active tickets into account.

Finally, add the Team Members who are to be assigned tickets for this team. Leave the field empty to include all employees who have the proper assignments and access rights configured in their user account settings.

Importante

If an employee has time off scheduled in the _Time Off_ application, they are **not** assigned tickets during that time. If no employees are available, the system looks ahead until there is a match.

Vedi anche

  * [Manage users](../general/users.html#users-add-individual)

  * [Access rights](../general/users/access_rights.html)




## Create or modify stages¶

_Stages_ are used to organize the _Helpdesk_ pipeline and track the progress of tickets. Stages are customizable, and can be renamed to fit the needs of each team.

Importante

[Developer mode](../general/developer_mode.html#developer-mode) **must** be activated to access the stages menu. To activate developer mode, go to Settings app ‣ General Settings ‣ Developer Tools, and click Activate the developer mode.

To view or modify _Helpdesk_ stages, go to Helpdesk app ‣ Configuration ‣ Stages.

The default list view on the Stages page displays the stages currently available in _Helpdesk_. They are listed in the order they appear in the pipeline.

To change the order of the stages, click the __(drag) icon, to the left of the stage name, and drag it to the desired place on the list.

Suggerimento

Change the stage order on the Kanban view of a _Helpdesk_ team’s pipeline by dragging and dropping individual columns.

To create a new stage, click the New button at the top-left of the stage list. Doing so reveals a blank stage form.

Choose a Name for the new stage, and add a description, if desired. Then, proceed to fill out the remaining fields following the steps below.

### Add email and SMS templates to stages¶

When an Email Template is added to a stage, an email is automatically sent to the customer when a ticket reaches that specific stage in the pipeline. Likewise, adding an SMS Template triggers an SMS text message to send to the customer.

Importante

SMS Text Messaging is an [In-App Purchase (IAP)](../essentials/in_app_purchase.html) service that requires prepaid credits to work. Refer to [SMS Pricing FAQ](https://iap-services.odoo.com/iap/sms/pricing) for additional information.

To select an existing email template, select it from the Email Template field. Click on the __(right arrow) icon to the right of the field to edit the chosen template.

To create a new template, click the field, and enter a title for the new template. Then, select Create and edit from the drop-down menu that appears, and complete the form details.

Follow the same steps to select, edit, or create an SMS Template.

Vedi anche

[Modelli e-mail](../general/companies/email_template.html)

### Assign stages to a team¶

Make a selection in the Helpdesk Teams field on the Stages form. More than one team may be selected, since the same stage can be assigned to multiple teams.

### Fold a stage¶

By default, stages are unfolded in the Kanban view of either tickets dashboard: My Tickets (Helpdesk app ‣ Tickets ‣ My Tickets) or All Tickets (Helpdesk app ‣ Tickets ‣ All Tickets).

Tickets in an unfolded stage are visible in the pipeline under the stage name, and are considered _open_.

Stages can be configured to be folded in the Kanban view of a tickets page (My Tickets or All Tickets).

The name of the folded stages are still visible, though the tickets in the stage are no longer immediately visible.

To fold a stage, check the Folded in Kanban box on the Stages form.

Avvertimento

Tickets that reach a _folded_ stage are considered _closed_. Closing a ticket before the work is completed can result in reporting and communication issues. This setting should **only** be enabled for stages that are considered _closing_ stages.

Stages can be temporarily folded in the Kanban view of the tickets pipeline, as well.

View a specific team’s pipeline by navigating to Helpdesk app, and clicking the team’s Kanban card.

Select a stage to fold temporarily, then click the __(gear) icon, and select Fold from the drop-down menu.

Importante

Manually folding a stage from the Kanban view is temporary and does **not** close the tickets in the stage.

## Merge tickets¶

If duplicate tickets are found in _Helpdesk_ , they can be combined into a single ticket using the _merge_ feature.

Importante

The _merge_ feature is **only** accessible if the [Data Cleaning](../productivity/data_cleaning.html) application is installed on the database.

To merge two or more tickets, navigate to Helpdesk app ‣ Tickets ‣ All Tickets. Identify the tickets to be merged, and tick the checkbox at the far-left of each ticket to select them. Then, click the __ Actions icon, and select Merge from the drop-down menu. Doing so opens a new page where the selected tickets are listed with their Similarity rating. From here, click either [Merge](../productivity/data_cleaning.html#data-cleaning-merge-records) to combine the tickets, or DISCARD.

Vedi anche

  * [Odoo Tutorials: Helpdesk](https://www.odoo.com/slides/helpdesk-51)




  * Panoramica
    * [Receiving tickets](helpdesk/overview/receiving_tickets.html)
    * [Centro assistenza](helpdesk/overview/help_center.html)
    * [Service level agreements (SLA)](helpdesk/overview/sla.html)
    * [Rendiconto](helpdesk/overview/reports.html)
    * [Customer ratings](helpdesk/overview/ratings.html)
  * Avanzato
    * [After-Sales services](helpdesk/advanced/after_sales.html)
    * [Close tickets](helpdesk/advanced/close_tickets.html)
    * [Track and bill time](helpdesk/advanced/track_and_bill.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/helpdesk.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](helpdesk/overview.html "Panoramica") |
  * [precedente](field_service/worksheets.html "Fogli di lavoro") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Servizi](../services.html) »
  * Helpdesk


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