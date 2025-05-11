# Helpdesk — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](helpdesk/overview.html "Panoramica") |
  * [precedente](field_service/worksheets.html "Fogli di lavoro") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Servizi](../services.html) »
  * Helpdesk



# Helpdesk¶

Odoo **Helpdesk** is a ticket-based customer support application. Multiple teams can be configured and managed in one dashboard, each with their own pipeline for tickets submitted by customers. Pipelines are organized in customizable stages that enable teams to track, prioritize, and solve customer issues quickly and efficiently.

## Create a Helpdesk team¶

To view or modify **Helpdesk** teams, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. To create a new team, click the New button on the top-left of the dashboard.

On the blank Helpdesk team form, enter a Name for the new team. Then, enter a description of the team in the field below the team name, if desired. To change the company this team is assigned to, select it from the Company drop-down menu.

Importante

The team description is published on the public facing [website form](helpdesk/overview/receiving_tickets.html), where customers and portal users submit tickets. The description included in this field should **not** include any information that is for internal use only.

### Visibility & Assignment¶

The _Visibility_ settings alter which internal users and portal users have access to this team and its tickets. The _Assignment_ settings alter how users are assigned to handle each ticket.

#### Determine team visibility¶

Under the Visibility section, select one of the following options to determine who can view this team and its tickets:

  * Invited internal users (private): Internal users can access the team and the tickets they are following. This access can be modified on each ticket individually by adding or removing the user as a follower. Internal users are considered _invited_ once they are added as followers to an individual ticket, or to the team itself.

  * All internal users (company): All internal users can access the team and all of its tickets.

  * Invited portal users and all internal users (public): All internal users can access the team and all of its tickets. Portal users can only access the tickets they are following.




Example

A `Customer Support` team, meant to handle general shipping and product issues, would have the visibility set on Invited portal users and all internal users.

At the same time, a `Financial Services` team handling tickets related to accounting or tax information would only need to be visible to Invited internal users.

Avvertimento

A team’s visibility can be altered after the initial configuration. However, if the team changes from _Invited portal users and all internal users (public)_ access to either _Invited internal users (private)_ or _All internal users (company)_ -only access, portal users are removed as followers from both the team, and from individual tickets.

#### Follow all team’s tickets¶

If a user should be notified about any updates regarding tickets for this team, select their name from the Followers drop-down menu, located in the Follow All Team’s Tickets field. Multiple users can be selected to follow a single team.

Importante

External contacts can be selected in the Followers field. If the team’s visibility is set to Invited internal users (private), followers are notified about updates to the team’s tickets, but are **not** able to view them in the portal.

#### Automatically assign new tickets¶

When tickets are received, they need to be assigned to a member of the team. This is done either manually on each individual ticket, or through Automatic Assignment. Check the Automatic Assignment checkbox to enable this feature for the team.

Select one of the following assignment methods, based on how the workload should be allocated across the team:

  * Each user is assigned an equal number of tickets: Tickets are assigned to team members based on total ticket count, regardless of the number of open or closed tickets they are currently assigned.

  * Each user has an equal number of open tickets: Tickets are assigned to team members based on how many open tickets they are currently assigned.




Nota

When Each user is assigned an equal number of tickets is selected, the overall number of tickets assigned to team members is the same, but it does **not** consider the current workload.

When Each user has an equal number of open tickets is selected, it ensures a balanced workload among team members, as it takes the current number of active tickets into account.

Finally, add the Team Members who are to be assigned tickets for this team. Leave the field empty to include all employees who have the proper assignments and access rights configured in their user account settings.

Importante

If an employee has time off scheduled in the **Time Off** application, they are **not** assigned tickets during that time. If no employees are available, the system looks ahead until there is a match.

Vedi anche

  * [Manage users](../general/users.html#users-add-individual)

  * [Access rights](../general/users/access_rights.html)




## Merge tickets¶

If duplicate tickets are found in **Helpdesk** , they can be combined into a single ticket using the _merge_ feature.

Importante

The _merge_ feature is **only** accessible if the [Data Cleaning](../productivity/data_cleaning.html) application is installed on the database.

To merge two or more tickets, navigate to Helpdesk app ‣ Tickets ‣ All Tickets. Identify the tickets to be merged, and tick the checkbox at the far-left of each ticket to select them. Then, click the __ Actions icon, and select Merge from the drop-down menu. Doing so opens a new page where the selected tickets are listed with their Similarity rating. From here, click either [Merge](../productivity/data_cleaning.html#data-cleaning-merge-records) to combine the tickets, or DISCARD.

## Convert tickets to opportunities¶

Some tickets may be better handled by the sales team, rather than the support team. In this case, tickets can be converted to _opportunities_ and assigned to a sales team for follow-up.

Importante

This feature is **only** available if the [CRM](../sales/crm.html) app is installed.

To convert a ticket to an opportunity, first navigate to a ticket, either from a team’s pipeline, or by navigating to Helpdesk app ‣ Tickets and clicking a ticket to open it.

At the top of the ticket, click the Convert to Opportunity button.

Nota

If [leads](../sales/crm/acquire_leads/convert.html) are enabled on the **CRM** app, tickets are converted to _leads_ , and the button reads Convert to Lead.

This opens the Convert to Opportunity pop-up. Fill in or select the following information on the pop-up:

  * Customer: Select whether to Create a new customer, Link to an existing customer, or Do not link to a customer. If Link to a customer is chosen, select the appropriate customer name from the Customer drop-down.

  * Sales Team: Specify which Sales Team and Salesperson this created opportunity is assigned to.




After completing the form, click Convert to Opportunity. Doing so creates a new opportunity in the **CRM** app. The original ticket is linked in the chatter of the new opportunity for traceability.

Nota

After the ticket is converted to an opportunity, the ticket is archived.

Vedi anche

  * [Odoo Tutorials: Helpdesk](https://www.odoo.com/slides/helpdesk-51)




  * Panoramica
    * [Fasi](helpdesk/overview/stages.html)
    * [Receiving tickets](helpdesk/overview/receiving_tickets.html)
    * [Centro assistenza](helpdesk/overview/help_center.html)
    * [Service level agreements (SLA)](helpdesk/overview/sla.html)
    * [Rendiconto](helpdesk/overview/reports.html)
    * [Customer ratings](helpdesk/overview/ratings.html)
  * Avanzato
    * [After-Sales services](helpdesk/advanced/after_sales.html)
    * [Close tickets](helpdesk/advanced/close_tickets.html)
    * [Track and bill time](helpdesk/advanced/track_and_bill.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/services/helpdesk.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](helpdesk/overview.html "Panoramica") |
  * [precedente](field_service/worksheets.html "Fogli di lavoro") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
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