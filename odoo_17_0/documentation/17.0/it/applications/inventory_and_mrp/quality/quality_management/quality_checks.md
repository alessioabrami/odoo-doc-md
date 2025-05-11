# Quality checks — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](failure_locations.html "Failure locations") |
  * [precedente](quality_alerts.html "Quality alerts") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality checks



# Quality checks¶

Quality checks are manual inspections conducted by employees, and are used to ensure the quality of products. In Odoo, a quality check can be conducted for a single product, or multiple products within the same inventory operation or manufacturing order.

Using a Quality Control Point (QCP), it is possible to create quality checks automatically at regular intervals. When quality checks are created by a QCP, they appear on a manufacturing or inventory order, where the employee processing the order will be prompted to complete them. For a full explanation of how to create and configure a QCP, see the documentation on [quality control points](quality_control_points.html#quality-quality-management-quality-control-points).

While quality checks are most commonly created automatically by a QCP, it is also possible to manually create a single quality check. Creating a check manually is useful when an employee wants to schedule a quality check that will only occur once, or register a quality check that they conduct unprompted.

## Manual quality check¶

To manually create a single quality check, navigate to Quality ‣ Quality Control ‣ Quality Checks, and click New. On the quality check form, begin by selecting an option from the Control per drop-down menu:

  * Operation requests a check for an entire operation (ex. delivery order) and all products within it.

  * Product requests a check for every unit of a product that is part of an operation (ex. every unit of a product within a delivery order).

  * Quantity requests a check for every quantity of a product that is part of an operation (ex. one check for five units of a product within a delivery order). Selecting Quantity also causes a Lot/Serial drop-down field to appear, from which can be selected a specific lot or serial number that the quality check should be conducted for.




Next, select an inventory operation from the Picking drop-down menu or a manufacturing order from the Production Order drop-down menu. This is necessary because Odoo needs to know for which operation the quality check is being conducted.

If the quality check should be assigned to a specific QCP, select it from the Control Point drop-down menu. This is useful if the quality check is being created manually, but should still be recognized as belonging to a specific QCP.

Select a quality check type from the Type drop-down field:

  * Instructions provides specific instructions for how to conduct the quality check.

  * Take a Picture requires a picture to be attached to the check before the check can be completed.

  * Pass - Fail is used when the product being checked must meet a certain criteria to pass the check.

  * Selecting Measure causes a Measure input field to appear, in which a measurement must be entered before the check can be completed.

  * Selecting Worksheet causes a Quality Template drop-down field to appear. Use it to select a quality worksheet that must be filled out to complete the check.




In the Team field, select the quality team that is responsible for the quality check. In the Company field, select the company that owns the product being inspected.

On the Notes tab at the bottom of the form, enter any relevant instructions in the Instructions text entry box (ex. “Attach a picture of the product”). In the Notes text entry box, enter any relevant information about the quality check (who created it, why it was created, etc.).

Finally, if the check is being processed immediately, click the Pass button at the top left of the screen if the check passes, or the Fail button if the check fails.

## Process quality check¶

Quality checks can be processed directly on the quality check’s page, or from a manufacturing or inventory order for which a check is required. Alternatively, if a quality check is created for a specific work order operation, the check is processed in the _Shop Floor_ module.

Nota

It is not possible to manually create a single quality check that is assigned to a specific work order operation. Quality checks for work order operations can only be created by a QCP. See the documentation on [Quality Control Points](quality_control_points.html#quality-quality-management-quality-control-points) for information about how to configure a QCP that will create quality checks for a specific work order operation.

### Quality check page¶

To process a quality check from the check’s page, begin by navigating to Quality ‣ Quality Control ‣ Quality Checks, then select the check to process. Follow the instructions for how to complete the check, listed in the Instructions field of the Notes tab at the bottom of the page.

If the quality check passes, click the Pass button at the top of the page. If the check fails, click the Fail button, instead.

### Quality check on order¶

To process a quality check on an order, select a manufacturing or inventory order (receipt, delivery, return, etc.), for which a check is required. Manufacturing orders can be selected by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and clicking on an order. Inventory orders can be selected by navigating to Inventory, clicking the # To Process button on an operation card, and selecting an order.

On the selected inventory or manufacturing order, a purple Quality Checks button appears at the top of the order. Click the button to open the Quality Check pop-up window, which shows all of the quality checks required for that order.

Follow the instructions that appear on the Quality Check pop-up window. If a Pass - Fail check is being processed, complete the check by clicking Pass or Fail at the bottom of the pop-up window. For all other quality check types, a Validate button appears instead. Click it to complete the check.

### Quality check on work order¶

To process a quality check for a work order, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Select an MO that includes a work order for which a quality check is required.

On the MO, select the Work Orders tab, and then click the Open Work Order (external link icon) button on the line of the work order to be processed. On the resulting Work Orders pop-up window, click the Open Shop Floor button to open the _Shop Floor_ module.

Vedi anche

For a full guide to the Shop Floor module, see the [Shop Floor overview](../../manufacturing/shop_floor/shop_floor_overview.html) documentation.

When accessed from a specific work order, the _Shop Floor_ module opens to the page for the work center where the order is configured to be processed, and isolates the work order’s card so that no other cards are shown.

Process the work order’s steps until the quality check step is reached. Click on the step to open a pop-up window that details how the check should be completed. After following the instructions, click Validate to complete the check. Alternatively, if a _Pass - Fail_ check is being processed, click either the Pass or Fail button.

It is also possible to complete a quality check by clicking the checkbox on the right side of the step. Doing so automatically marks the check as _Passed_.

Nota

The specific steps for processing a quality check depend upon the type of check being conducted. For information about processing each type of quality check, see the associated documentation:

  * [Instructions quality check](../quality_check_types/instructions_check.html)

  * [Pass - Fail quality check](../quality_check_types/pass_fail_check.html)

  * [Measure quality check](../quality_check_types/measure_check.html)

  * [Take a Picture quality check](../quality_check_types/picture_check.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/quality/quality_management/quality_checks.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](failure_locations.html "Failure locations") |
  * [precedente](quality_alerts.html "Quality alerts") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality checks


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