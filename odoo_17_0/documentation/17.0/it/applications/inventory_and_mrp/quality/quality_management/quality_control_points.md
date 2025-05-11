# Quality control points — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_alerts.html "Quality alerts") |
  * [precedente](../quality_management.html "Quality control basics") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality control points



# Quality control points¶

In Odoo, _quality control points_ (QCPs), are used to automatically create [quality checks](quality_checks.html) at predetermined intervals. QCPs can be configured to create quality checks for specific operations (manufacturing, delivery, etc.), as well as specific products within those operations.

Using QCPs allows quality teams to ensure products are being regularly inspected for defects and other issues.

## Configure quality control points¶

To create a new QCP, navigate to Quality ‣ Quality Control ‣ Control Points, and then click New.

Begin filling out the new QCP by entering a unique Title that makes the QCP easily identifiable.

In the Products field, select one or more products the QCP should apply to. If the QCP should apply to an entire product category, select it in the Product Categories field.

In the Operations field, select the operation(s) that should trigger the QCP. For example, selecting the Manufacturing option in the Operations field causes a quality check to be created for new manufacturing orders (MOs).

Nota

When creating a new QCP, at least one operation must be listed in the Operations field. However, the Products and Product Categories fields can be left blank. If they are left blank, the QCP generates quality checks for every instance of the specified operation(s).

If the Manufacturing operation is selected in the Operations field, a new field appears below it, titled Work Order Operation. From this field, select a specific work order to generate quality checks for that operation, rather than the manufacturing operation in general.

For example, a QCP could be configured to create quality checks for the `Assembly` work order of the `Coffee Table` product. Then, if a new MO is confirmed for a `Coffee Table`, the QCP creates a quality check specifically for the `Assembly` operation.

The Control Per field is set to one of three options that determine _when_ a new quality check is created:

  * Operation: one check is requested for the specified operation, as a whole.

  * Product: one check is requested for each _unique_ product included in the specified operation. For example, a delivery operation for one table and four chairs would generate two checks, since two _unique_ products are included in the operation.

  * Quantity: a check is requested for a certain percentage of items within the specified operation. This percentage is set by enabling the Partial Transfer Test checkbox, and then entering a numerical value in the Percentage field that appears below. If the checkbox is not enabled, one quality check is created for the full quantity.




The Control Frequency field is set to one of three options that determine _how often_ a new quality check is created:

  * All: a quality check is requested every time the conditions of the QCP are met.

  * Randomly: a quality check is randomly requested for a certain percentage of operations, which can be specified in the Every #% of Transfers field that appears below.

  * Periodically: a quality check is requested once every set period of time, which is specified by entering a numerical value in the field below, and choosing either Days, Weeks, or Months as the desired time interval.




In the Type field, specify the type of quality check that should be performed. The method for processing quality checks created by the QCP depends upon the type of quality check selected:

  * Instructions checks provide specific instructions for how to complete the quality check.

  * Take a Picture checks require a picture of the product be uploaded for later review by the assigned quality team.

  * Register Production checks prompt manufacturing employees to confirm the quantity of the product that was produced during the manufacturing operation.

  * Pass - Fail checks specify a criterion that products must meet for the check to pass.

  * Measure checks prompt employees to record a measurement of the product that must be within a tolerance of a norm value for the check to pass.

  * Worksheet checks provide an interactive worksheet that must be filled out by the employee processing the check.




Importante

An _Instructions_ check is the same as a step on a work order for an MO.

When a step is added to a work order, Odoo stores it in the Quality app as a QCP. It is possible to manually create a QCP with the _Instructions_ check type, and even assign it to an operation other than manufacturing, like receipts.

However, when creating a control point specifically for quality control purposes, using a different check type is probably more effective.

In the Team field, specify the quality team that is responsible for managing the QCP, and the quality checks it creates. If a specific quality team member is responsible for the QCP, select them in the Responsible field.

The Step Document field has two options that specify the location of an instructional document detailing how to complete the quality checks created by the QCP.

Select Specific Page of Operation Worksheet if the document is included with the instructional worksheet for the work order, then enter the page number in the Worksheet Page field that appears below.

Select Custom if the document should be included in the Instructions tab at the bottom of the QCP.

In the Instructions tab at the bottom of the form, enter instructions for how to complete the quality checks created by the QCP.

If the Custom option was selected in the Step Document field above, a document can be attached in this tab. To do so, either select the Upload your file button to open the device’s file manager, and then select a file, or add a link to a Google Slides document in the Google Slide Link field.

In the Message If Failure tab, include instructions for what to do if the quality check fails. For example, instruct the employee processing the quality check to create a [quality alert](quality_alerts.html).

The Notes tab is used to provide additional information about the QCP, like the reason it was created. The information entered in this tab is **not** shown to employees processing the quality checks created by the QCP.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/quality/quality_management/quality_control_points.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_alerts.html "Quality alerts") |
  * [precedente](../quality_management.html "Quality control basics") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality control points


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
  *[MO]: Manufacturing Order
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
  *[SO]: Sales order
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
  *[SOs]: Sales Order
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
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points