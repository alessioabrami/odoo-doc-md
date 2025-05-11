# Measure quality check — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](picture_check.html "Take a Picture quality check") |
  * [precedente](pass_fail_check.html "Pass - Fail quality check") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality check types](../quality_check_types.html) »
  * Measure quality check



# Measure quality check¶

In Odoo _Quality_ , a _Measure_ check is one of the quality check types that can be selected when creating a new quality check or quality control point (QCP). _Measure_ checks prompt users to measure a certain aspect of a product and record the measurement in Odoo. For the quality check to pass, the recorded measurement must be within a certain _tolerance_ of a _norm_ value.

## Create a Measure quality check¶

There are two distinct ways that _Measure_ quality checks can be created. A single check can be manually created. Alternatively, a QCP can be configured that automatically creates checks at a predetermined interval.

This documentation only details the configuration options that are unique to _Measure_ quality checks and QCPs. For a full overview of all the configuration options available when creating a single check or a QCP, see the documentation on [quality checks](../quality_management/quality_checks.html#quality-quality-management-quality-checks) and [quality control points](../quality_management/quality_control_points.html#quality-quality-management-quality-control-points).

### Quality check¶

To create a single _Measure_ quality check, navigate to Quality ‣ Quality Control ‣ Quality Checks, and click New. Fill out the new quality check form as follows:

  * In the Type drop-down field, select the Measure quality check type.

  * In the Team drop-down field, select the quality team responsible for managing the check.

  * In the Instructions text field of the Notes tab, enter instructions for how the picture should be taken.




### Quality control point (QCP)¶

To create a QCP that generates _Measure_ quality checks automatically, navigate to Quality ‣ Quality Control ‣ Control Points, and click New. Fill out the new QCP form as follows:

  * In the Type drop-down field, select the Measure quality check type. Doing so causes two new fields to appear: Norm and Tolerance.

    * Use the first text-entry field of the Norm field to record the ideal measurement that the product should conform to. Use the second text-entry field to specify the unit of measurement that should be used.

    * The Tolerance field features two sub-fields: from and to. Use the from field to specify the minimum acceptable measurement, and the to field to specify the maximum acceptable measurement.

  * In the Team drop-down field, select the quality team responsible for managing the checks created by the QCP.

  * In the Instructions text field, enter instructions for how the measurement should be taken.




## Process a Measure quality check¶

Once created, there are multiple ways that _Measure_ quality checks can be processed. If a quality check is assigned to a specific inventory, manufacturing, or work order, the check can be processed on the order itself. Alternatively, a check can be processed from the check’s page.

### From the check’s page¶

To process a _Measure_ quality check from the check’s page, begin by navigating to Quality ‣ Quality Control ‣ Quality Checks, and select a quality check. Follow the Instructions for how to take the measurement.

After taking the measurement, record the value in the Measure field on the quality check form. To manually pass or fail the check, click Pass or Fail at the top-left corner of the check.

Alternatively, if the quality check is assigned to a QCP for which _norm_ and _tolerance_ values have been specified, click Measure at the top-left corner of the check instead. Doing so automatically marks the check as _Passed_ if the recorded value is within the specified _tolerance_ , or _Failed_ if the value is outside of it.

### On an order¶

To process a _Measure_ quality check on an order, select a manufacturing order or inventory order (receipt, delivery, return, etc.), for which a check is required. Manufacturing orders can be selected by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and clicking on an order. Inventory orders can be selected by navigating to Inventory, clicking the # To Process button on an operation card, and selecting an order.

On the selected manufacturing or inventory order, a purple Quality Checks button appears at the top of the page. Click the button to open the Quality Check pop-up window, which shows all of the quality checks required for that order.

To process a _Measure_ quality check, measure the product as instructed, then enter the value in the Measure field on the pop-up window. Finally, click Validate to register the recorded value.

If the value entered is within the range specified in the Tolerance section of the QCP, the quality check passes and the pop-up window closes. The rest of the manufacturing or inventory order can then be processed as usual.

However, if the value entered is outside of the specified range, a new pop-up window appears, titled Quality Check Failed. The body of the pop-up shows a warning message that states, You measured # units and it should be between # units and # units., as well as the instructions entered in the Message If Failure tab of the QCP. At the bottom of the pop-up, two buttons appear: Correct Measure and Confirm Measure.

If the measurement was not entered correctly and should be changed, select Correct Measure. Doing so re-opens the Quality Check pop-up window. Enter the corrected measurement in the Measure field, and then click Validate to complete the check.

If the measurement was entered correctly, click Confirm Measure instead, and the quality check fails. Follow any instructions that were listed on the Quality Check Failed pop-up window.

If a quality alert must be created, click the Quality Alert button that appears at the top of the manufacturing or inventory order after the check fails. Clicking Quality Alert opens a quality alert form on a new page.

Vedi anche

For a complete guide on how to fill out the quality alert form, view the documentation on [quality alerts](../quality_management/quality_alerts.html).

### On a work order¶

When configuring a QCP that is triggered during manufacturing, a specific work order can also be specified in the Work Order Operation field on the QCP form. If a work order is specified, a _Measure_ quality check is created for that specific work order, rather than the manufacturing order as a whole.

_Measure_ quality checks configured for work orders **must** be completed from the _Shop Floor_ module. To do so, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Select an MO that includes a work order for which a _Measure_ quality check is required.

On the MO, select the Work Orders tab, and click the Open Work Order (external link icon) button on the line of the work order to be processed. On the resulting Work Orders pop-up window, click the Open Shop Floor button to open the _Shop Floor_ module.

When accessed from a specific work order, the _Shop Floor_ module opens to the page for the work center where the order is configured to be processed, and isolates the work order’s card, so no other cards are shown.

Process the work order’s steps until the _Measure_ quality check step is reached. Click on the step to open a pop-up window that includes instructions for how the measurement should be taken. After taking the measurement, enter it in the Measure field of the pop-up window, and then click Validate.

If the measurement entered is within the range specified in the Tolerance section of the QCP, the quality check passes, and the pop-up window moves on to the next step of the work order. However, if the measurement entered is outside of the specified range, a new pop-up window appears, titled Quality Check Failed.

The body of the Quality Check Failed pop-up window shows a message that states, You measured # units and it should be between # units and # units, as well as the instructions entered in the Message If Failure tab of the QCP. At the bottom of the pop-up window, two buttons appear: Correct Measure and Confirm Measure.

If the measurement was not entered correctly, and should be changed, select Correct Measure. Doing so opens a new pop-up window, titled Quality Check. Enter the corrected measure in the Measure field, and then click Validate to complete the check and close the pop-up window.

If the measurement was entered correctly, click Confirm Measure instead, and the quality check fails. Follow any instructions that were listed on the Quality Check Failed pop-up window.

If a quality alert must be created, exit the pop-up window by clicking the X (close) button in the top-right corner.

Then, click the ⋮ (three vertical dots) button on the bottom-right corner of the work order card to open the What do you want to do? pop-up window.

On the What do you want to do? pop-up window, select the Create a Quality Alert button. Doing so opens a blank quality alert form in a new Quality Alerts pop-up window.

Vedi anche

For a complete guide on how to fill out quality alert forms, view the documentation on [quality alerts](../quality_management/quality_alerts.html).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/quality/quality_check_types/measure_check.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](picture_check.html "Take a Picture quality check") |
  * [precedente](pass_fail_check.html "Pass - Fail quality check") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality check types](../quality_check_types.html) »
  * Measure quality check


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