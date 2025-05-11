# Close tickets — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](track_and_bill.html "Track and bill time") |
  * [precedente](after_sales.html "After-Sales services") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * Close tickets



# Close tickets¶

Once work has been completed on a _Helpdesk_ ticket in Odoo, there are several ways it can be closed.

In addition to manually closing solved tickets, automatically closing inactive tickets keeps the pipeline up-to-date. At the same time, allowing customers to close their own tickets minimizes confusion around whether an issue is considered solved or not. This results in increased operational capacity for support teams, and higher customer satisfaction.

## Manually close solved tickets¶

As work on a ticket progresses, it is moved along to the next stage in the pipeline. Once the issue is solved, the ticket is moved to a _folded_ stage. This marks the ticket as _closed_.

To fold a stage, navigate to the Helpdesk app dashboard, and click on a team to open the to reveal that team’s pipeline on a separate page.

From the pipeline page, hover over a stage’s heading, and click the ⚙️ (gear) icon that appears in the top-right corner of that stage’s Kanban column.

From the menu that appears, select Edit. This opens the stage’s settings in a pop-up window.

In the pop-up window, check the box labeled, Folded in Kanban, towards the top of the window. Then, click Save & Close to confirm the changes.

Tickets that reach this stage are now considered: _closed_.

Avvertimento

Clicking the ⚙️ (gear) icon also displays the option to Fold the stage. This setting folds the stage _temporarily_ to simplify the Kanban view. This does **not** close the tickets in this stage. It also does **not** permanently fold the stage. If a stage needs to be folded, so the tickets can be marked as _closed_ , the Folded in Kanban checkbox **must** be checked on the stage’s settings.

## Automatically close inactive tickets¶

Tickets that are inactive for a set period of time can be automatically closed. At that point, they are moved to a folded stage.

To have Odoo automatically close inactive tickets, go to the desired team’s settings page, by navigating to Helpdesk app ‣ Configuration ‣ Helpdesk Teams, and selecting the desired team to configure. Under the Self-Service section, enable Automatic Closing.

After ticking the box for Automatic Closing, three new fields appear beneath:

  * Move to Stage

  * After (#) days of inactivity

  * In Stages




If one of the team’s stages is set to be folded in the Kanban view, the folded stage is the default selection in the Move to Stage field. If the team has more than one folded stage, the folded stage that occurs first in the pipeline is the default. If no stage is folded, the default selection is the last stage in the pipeline.

The After (#) days of inactivity field defaults to `7`, but can be adjusted if necessary.

Avvertimento

The After (#) days of inactivity field does **not** take the working calendar into account when tracking the amount of time a ticket has been inactive.

If only certain stages should be used to track days of inactivity, they can be added to the In Stages field.

Example

A team’s pipeline is created with the following stages:

  * `New`

  * `In Progress`

  * `Customer Feedback`

  * `Closed`




Tickets may linger in the Customer Feedback stage, because once an issue is solved, customers may not respond immediately. At that point, the tickets can be closed automatically.

Tickets in the New and In Progress stages could remain inactive due to assignment or workload issues. The support team may be looking into the issue even if they are not updating the ticket directly. Closing these tickets automatically would result in issues going unsolved.

Therefore, the Automatic Closing settings for this team would be configured as below:

  * Automatic Closing: _checked_

  * Move to Stage: `Solved`

  * After `7` days of inactivity

  * In Stages: `Customer Feedback`




## Allow customers to close their own tickets¶

Enabling the Closure by Customers setting allows customers to close their own tickets when they determine that their issue has been resolved.

To allow customers to close their own tickets, start by navigating to Helpdesk app ‣ Configuration ‣ Helpdesk Teams, and click on a team to open the team’s settings page. Next, scroll to the Self-Service section, and check the box for Closure by Customers.

Once the ticket closing settings are enabled, a Close Ticket button is available for customers when they view their ticket through the customer portal.

Nota

Customers are able to view their tickets by clicking the View the ticket link they receive by email. The link is included in the Helpdesk: Ticket Received template, which is added to the first stage of a team by default. This link does **not** require a customer to have access to the portal to view or respond to their ticket.

Customers with access to the portal can view their tickets under My Account ‣ Tickets.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/helpdesk/advanced/close_tickets.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](track_and_bill.html "Track and bill time") |
  * [precedente](after_sales.html "After-Sales services") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * Close tickets


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