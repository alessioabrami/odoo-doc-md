# Customer ratings — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzato") |
  * [precedente](reports.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Customer ratings



# Customer ratings¶

Asking customers to rate the support they received from a _Helpdesk_ team provides an opportunity to gauge team performance and track customer satisfaction. Ratings can be published on the portal, providing customers with a general overview of the team’s performance.

## Enable customer ratings on Helpdesk teams¶

To enable _customer ratings_ on a helpdesk team, navigate to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. Select a team from the list and click on it to open the settings page. Scroll to the Performance section, and tick the Customer Ratings checkbox.

## Set a ratings request email template on a stage¶

To automatically request ratings from customers once their tickets have closed, an email template should be added to the appropriate stage.

After the Customer Ratings setting has been enabled on the team’s settings page, click the Set an Email Template on Stages link. Select a stage from the list, or click New to create a new stage.

Importante

Customers should only be asked to rate tickets once an issue has been resolved and their ticket is _closed_. Therefore, a _ratings request_ email should **only** be added to a stage that is folded in the Kanban, as tickets in a _folded stage_ are considered closed.

On the stage’s settings page, select the template, `Helpdesk: Ticket Rating Request` in the Email Template field. This template has been preconfigured with ratings customers can use to provide feedback. To view the template, click the arrow button to the right of the field.

After the template is added to the stage, it automatically sends a message when a ticket is moved to that stage. Customers are then asked to rate the support they received with colored icons.

>   * _Green smiling face_ \- Satisfied
> 
>   * _Yellow neutral face_ \- Okay
> 
>   * _Red frowning face_ \- Dissatisfied
> 
> 


After selecting a rating, customers are taken to a webpage where they can provide specific written feedback to support their rating. The rating is then submitted, and the rating, as well as any additional comments, are added to the chatter on the ticket.

Suggerimento

Customer ratings can also be viewed through the Customer Ratings report. To view this report, go to Helpdesk app ‣ Reporting ‣ Customer Ratings.

Vedi anche

[Modelli e-mail](../../../general/companies/email_template.html)

## Publish ratings on the customer portal¶

After enabling the Customer Ratings setting, an option to publish ratings on the team’s website appears. Enabling this setting provides portal users with an overview of the ratings the team has received over the last thirty days. Specific written feedback will not be included; only statistics of the team’s performance will be visible.

Importante

To display ratings on the customer portal, a team **must** have their visibility setting set to Invited portal users and all internal users (public). To enable this setting, navigate to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. Select a team from the list and click on it to open the settings page. Scroll to the Visibility & Assignment section, and tick the Invited portal users and all internal users (public) checkbox.

Next, to publish the ratings, go to Helpdesk app‣ Configuration ‣ Helpdesk Teams and select a team. Scroll to Performance and tick the checkbox for Publish this team’s ratings on your website.

To view the ratings for a team, a customer will log into the portal and navigate to one of their tickets. After clicking on the team name in the Managed By field, they will be directed to a page with the team’s ratings over the past thirty days.

Vedi anche

[Portal access](../../../general/users/portal.html)

### Manually hide individual ratings¶

Individual ratings can be manually hidden from the portal. This allows for specific ratings to be kept out of the performance metrics shared with customers.

To make a rating visible only to internal users, navigate to the page for a rating. This can be done in one of the following ways:

>   * Go to Helpdesk app ‣ Reporting ‣ Customer Ratings and click on one of the Kanban cards for an individual rating.
> 
>   * Navigate to Helpdesk app‣ Tickets ‣ All Tickets and remove the Open filter from the search bar. Then filter by Satisfied, Okay and/or Dissatisfied. Select a ticket from the results. Click the Rating smart button.
> 
> 


Once on the rating details page, check the Visible Internally Only box.

Vedi anche

  * [Close tickets](../advanced/close_tickets.html)

  * [Rendiconto](reports.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/helpdesk/overview/ratings.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzato") |
  * [precedente](reports.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Customer ratings


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
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement