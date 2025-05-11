# Fatturare milestone di progetto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expense.html "Reinvoice expenses to customers") |
  * [precedente](time_materials.html "Fatture basate su tempo e materiali") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatturare milestone di progetto



# Fatturare milestone di progetto¶

La fatturazione basata sulle milestone di progetto può essere utilizzata per progetti costosi o su larga scala. La serie di milestone di un progetto rappresenta una chiara sequenza di lavoro che porterà inevitabilmente al completamento del progetto e/o del contratto.

Questo metodo di fatturazione assicura all’azienda un flusso di denaro costante per tutta la durata del progetto. I clienti possono monitorare da vicino ogni fase dello sviluppo del progetto, oltre a pagare una fattura consistente in più rate, anziché in un’unica soluzione.

## Creare prodotti milestone¶

In Odoo, ogni milestone di progetto viene considerata un prodotto individuale.

Per creare e/o configurare prodotti che funzioni in questo modo, apri l’app Vendite ‣ Prodotti ‣ Prodotti. In seguito, fai clic su un prodotto, oppure creane uno nuovo facendo clic su Nuovo.

L’opzione di fatturazione in base a milestone è disponibile solo per alcuni tipi di prodotto.

On the product form, under the General Information tab, the Product Type field _must_ be set on any of the following options: Service, Event Ticket, Event Booth, or Course.

With any of those Product Type options selected, choose Based on Milestones from the Invoicing Policy drop-down menu.

Beneath that is the Create on Order field.

To ensure workflows are as seamless as possible, it is recommended that an option in the Create on Order field is selected.

Nota

Leaving it on the default Nothing option won’t negatively affect the desired workflow. However, a project _must_ then be created directly from a sales order form with that specific product. Once a project is created _then_ milestones and tasks can be created and configured.

When the Create on Order default option of Nothing is clicked, a drop-down menu is revealed with the following options:

  * Task: Odoo creates a task related to this milestone product in the _Projects_ app when this specific product is ordered.

  * Project & Task: Odoo creates a project and task related to this milestone product in the _Projects_ app when this specific product is ordered.

  * Project: Odoo creates a project related to this milestone product in the _Projects_ app when this specific product is ordered.




When Task is selected, a Project field appears. In this field, select to which existing project in the _Projects_ app this created task should be connected.

When Project & Task or Project is selected, two new fields appear: Project Template and Workspace Template.

The Project Template field provides template options to use for the project that will be created when this specific product is ordered.

The Workspace Template field provides template options to use for the workspace (for the _Documents_ app, not the _Projects_ app) that will be automatically generated for the project when this specific product is ordered.

Suggerimento

For organizational purposes, click the Sales tab on the product form, and enter a custom “Milestone” related descriptor in the Sales Description field. This information appears in the Description column on the Order Lines tab of the sales order.

Or, directly edit/modify the Description field on the Order Lines tab of the sales order.

This is _not_ a requirement.

## Invoice milestones¶

Nota

The following flow features a trio of milestone products that have Service set as their Product Type, and Task set on their Create on Order field.

> Those tasks are then attached to a pre-existing Project, which, in this case, is titled, Rebranding Projects.

To invoice milestones, create a sales order with the milestone product(s). To do that, go to Sales app ‣ New. Doing so reveals a blank quotation form.

From this quotation form, add a Customer. Then, click Add a product in the Order Lines tab. Next, add the milestone product(s) to the Order Lines tab.

Once the corresponding milestone product(s) have been added, click Confirm to confirm the order, which turns the quotation into a sales order.

When the order is confirmed, new smart buttons appear at the top of the sales order based on what was selected in the Create on Order field on the product form.

From the sales order, click the Milestones smart button. Doing so reveals a blank Milestones page. Click New to add milestones.

Enter a Name for the milestone. Next, apply it to the corresponding Sales Order Item. Lastly, assign a Deadline to the milestone, if desired.

Repeat that process for all milestone sales order items.

Then, return to the sales order, via the breadcrumbs. From the sales order, click the Tasks smart button. Doing so reveals a Tasks page with a task for each sales order item with that option designated in the Create on Order field.

To manually assign a configured milestone to a task, click the desired task, which reveals the task form. On the task form, select the appropriate milestone to which this task should be connected, in the Milestone field.

Repeat this process for all milestone tasks.

With those tasks properly configured, employees log in their progress as they work on the task, in addition to adding any notes related to the task.

Then, when that task is complete, that means that milestone has been reached. At that point, it is time to invoice that milestone.

To invoice a milestone, first return to the sales order — either via the breadcrumb links, or by navigating to Sales app ‣ Orders ‣ Orders and picking the appropriate sales order.

Back on the sales order form, click the Milestones smart button, and check the box in the Reached column for that particular task.

Next, return to the sales order — either by clicking View Sales Order on the Milestones page, or via the breadcrumb links.

Back on the sales order, the line item for the milestone that’s been reached has its Delivered column filled. That’s because the milestone has been reached, and therefore delivered.

Click Create Invoice in the upper-left corner. Doing so reveals a Create invoices pop-up window.

On the Create invoices pop-up window, leave the Create Invoice option on the default Regular Invoice selection, and click the Create Draft Invoice button.

Upon clicking Create Draft Invoice, Odoo reveals the Customer Invoice Draft, _only_ showing that reached milestone in the Invoice Lines tab.

From this invoice page, click the Confirm button to confirm the invoice. Then, when the customer has paid for this milestone, click Register Payment.

When Register Payment is clicked, a Register Payment pop-up window appears.

On this pop-up window, confirm the accuracy of the auto-populated fields, then click Create Payment.

When clicked, the pop-up window disappears, and Odoo returns to the invoice for that milestone, which now has a green In Payment banner in the upper-right corner. This banner signifies the invoice has been paid.

Then, return to the sales order, via the breadcrumb links. Back on the sales order, in the Order Lines tab, the reached milestone that’s been invoiced and paid for, now has its Invoiced column filled.

There is also a new Invoices smart button at the top of the sales order. Clicking that reveals all the invoices that are connected to this sales order.

Simply repeat the above process for each milestone as it is worked on, and subsequently, completed.

Continue that process until the entire project has been completed, each milestone has been invoiced, and the entire order has been paid for in full.

Vedi anche

  * [Fatture basate su tempo e materiali](time_materials.html)

  * [Fatture proforma](proforma.html)

  * [Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/invoicing/milestone.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expense.html "Reinvoice expenses to customers") |
  * [precedente](time_materials.html "Fatture basate su tempo e materiali") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatturare milestone di progetto


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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