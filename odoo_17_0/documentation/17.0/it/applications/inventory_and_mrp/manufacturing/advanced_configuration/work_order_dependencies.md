# Work order dependencies — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../workflows.html "Workflow") |
  * [precedente](using_work_centers.html "Manage work orders using work centers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Work order dependencies



# Work order dependencies¶

When manufacturing certain products, specific operations may need to be completed before others can begin. In order to ensure operations are carried out in the correct order, Odoo _Manufacturing_ features a _work order dependencies_ setting. Enabling this setting allows for operations on a Bill of Materials (BoM) to be _blocked_ by other operations that should occur first.

## Configurazione¶

The _work order dependencies_ setting is not enabled by default. To enable it, begin by navigating to Manufacturing ‣ Configuration ‣ Settings. Then, enable the Work Orders setting, if it is not already active.

After enabling the Work Orders setting, the Work Order Dependencies setting appears below it. Enable Work Order Dependencies, then click Save to confirm the changes.

## Add dependencies to BoM¶

Work order dependencies are configured on a product’s BoM. To do so, navigate to Manufacturing ‣ Products ‣ Bills of Materials, then select a BoM, or create a new one by clicking New.

Scopri di più

For a complete guide on how to properly configure a new BoM, see the documentation on [creating a bill of materials](../basic_setup/bill_configuration.html).

On the BoM, click on the Miscellaneous tab, then enable the Operation Dependencies checkbox. This makes a new Blocked By option available in the settings of the Operations tab.

Next, click on the Operations tab. On the top-right of the tab, click on the tab’s settings button, then enable the Blocked By checkbox. This makes a Blocked By field appear for each operation on the Operations tab.

In the line of the operation that should be blocked by another operation, click the Blocked By field, and an Open: Operations pop-up window appears. In the Blocked By drop-down field on the pop-up window, select the blocking operation that must be completed _before_ the operation that is blocked.

Finally, save the BoM by clicking Save.

## Plan work orders using dependencies¶

Once work order dependencies have been configured on a BoM, Odoo _Manufacturing_ is able to plan when work orders are scheduled, based on their dependencies. To plan the work orders for a manufacturing order, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders.

Next, select a manufacturing order for a product with work order dependencies set on its BoM, or create a new manufacturing order by clicking New. If a new manufacturing order is created, select a BoM configured with work order dependencies from the Bill of Material drop-down field, then click Confirm.

After confirming the manufacturing order, select the Work Orders tab to view the work orders required to complete it. Any work orders that are _not_ blocked by a different work order display a `Ready` tag in the Status section.

Work orders that are blocked by one or more work orders display a `Waiting for another WO` tag instead. Once the blocking work order(s) are completed, the tag updates to `Ready`.

To schedule the manufacturing order’s work orders, click the Plan button at the top of the page. After doing so, the Scheduled Start Date field for each work order on the Work Orders tab auto-fills with the scheduled start date and time. A blocked work order is scheduled at the end of the time period specified in the Expected Duration field of the work order that precedes it.

Example

A manufacturing order is created for Product A. The manufacturing order has two operations: Cut and Assemble. Each operation has an expected duration of 60 minutes, and the Assemble operation is blocked by the Cut operation.

The Plan button for the manufacturing order is clicked at 1:30 pm, and the Cut operation is scheduled to begin immediately. Since the Cut operation has an expected duration of 60 minutes, the Assemble operation is scheduled to begin at 2:30 pm.

### Planning by workcenter¶

To see a visual representation of how work orders are planned, navigate to the Work Orders Planning page by going to Manufacturing ‣ Planning ‣ Planning by Workcenter. This page shows a timeline of all the work orders scheduled for each operation.

If one work order is blocked by the completion of another, the work order that is blocked is shown as scheduled to start after the work order blocking it. In addition, an arrow connects the two work orders, leading from the blocking operation to the blocked operation.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/work_order_dependencies.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../workflows.html "Workflow") |
  * [precedente](using_work_centers.html "Manage work orders using work centers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Work order dependencies


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: sales orders
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: bills of materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order