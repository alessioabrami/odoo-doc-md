# Take a Picture quality check — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../maintenance.html "Manutenzione") |
  * [precedente](measure_check.html "Measure quality check") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality check types](../quality_check_types.html) »
  * Take a Picture quality check



# Take a Picture quality check¶

In Odoo _Quality_ , a _Take a Picture_ check is one of the quality check types that can be selected when creating a new quality check or quality control point (QCP). _Take a Picture_ checks require a picture to be attached to the check, which can then be reviewed by a quality team.

## Create a Take a Picture quality check¶

There are two distinct ways that _Take a Picture_ quality checks can be created. A single check can be manually created. Alternatively, a QCP can be configured that automatically creates checks at a predetermined interval.

This documentation only details the configuration options that are unique to _Take a Picture_ quality checks and QCP. For a full overview of all the configuration options available when creating a single check or a QCP, see the documentation on [quality checks](../quality_management/quality_checks.html#quality-quality-management-quality-checks) and [quality control points](../quality_management/quality_control_points.html#quality-quality-management-quality-control-points).

### Quality check¶

To create a single _Take a Picture_ quality check, navigate to Quality ‣ Quality Control ‣ Quality Checks, and click New. Fill out the new quality check form as follows:

  * In the Type drop-down field, select the Take a Picture quality check type.

  * In the Team drop-down field, select the quality team responsible for managing the check.

  * In the Instructions text field of the Notes tab, enter instructions for how the picture should be taken.




### Quality control point¶

To create a QCP that generates _Take a Picture_ quality checks automatically, navigate to Quality ‣ Quality Control ‣ Control Points, and click New. Fill out the new QCP form as follows:

  * In the Type drop-down field, select the Take a Picture quality check type.

  * If the _Maintenance_ app is installed, a Device field appears after selecting the _Take a Picture_ check type. Use this field to specify a device that should be used to take quality check pictures. For information about managing devices in the _Maintenance_ app, see the documentation on [adding new equipment](../../maintenance/add_new_equipment.html#maintenance-equipment-management-add-new-equipment).

  * In the Team drop-down field, select the quality team responsible for managing the checks created by the QCP.

  * In the Instructions text field, enter instructions for how the picture should be taken.




## Process a Take a Picture quality check¶

Once created, there are multiple ways that _Take a Picture_ quality checks can be processed. If a quality check is assigned to a specific inventory, manufacturing, or work order, the check can be processed on the order itself. Alternatively, a check can be processed from the check’s page.

### From the check’s page¶

To process a _Take a Picture_ quality check from the check’s page, begin by navigating to Quality ‣ Quality Control ‣ Quality Checks, and then select a quality check. Follow the Instructions for how to take the picture.

After taking the picture, make sure it is stored on the device being used to process the quality check (computer, tablet, etc.). Then, click the ✏️ (pencil) button in the Picture section to open the device’s file manager. In the file manager, navigate to the picture, select it, and click Open to attach it.

### On an order¶

To process a _Take a Picture_ quality check on an order, select a manufacturing order or inventory order (receipt, delivery, return, etc.), for which a check is required. Manufacturing orders can be selected by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and clicking on an order. Inventory orders can be selected by navigating to Inventory, clicking the # To Process button on an operation card, and selecting an order.

On the selected manufacturing or inventory order, a purple Quality Checks button appears at the top of the page. Click the button to open the Quality Check pop-up window, which shows all of the quality checks required for that order.

Follow the instructions detailing how to take the picture, which are shown on the Quality Check pop-up window. After taking the picture, make sure it is stored on the device being used to process the quality check (computer, tablet, etc.).

Then, click the Take a Picture button in the Picture section to open the device’s file manager. In the file manager, navigate to the picture, select it, and click Open to attach it. Finally, click Validate on the Quality Check pop-up window to complete the quality check.

If a quality alert must be created, click the Quality Alert button that appears at the top of the manufacturing or inventory order after the check is validated. Clicking Quality Alert opens a quality alert form on a new page. For a complete guide on how to fill out quality alert forms, view the documentation on [quality alerts](../quality_management/quality_alerts.html#quality-quality-management-quality-alerts).

### On a work order¶

When configuring a QCP that is triggered during manufacturing, a specific work order can also be specified in the Work Order Operation field on the QCP form. If a work order is specified, a _Take a Picture_ quality check is created for that specific work order, rather than the manufacturing order as a whole.

_Take a Picture_ quality checks configured for work orders **must** be completed from the _Shop Floor_ module. To do so, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Then, select an MO that includes a work order for which a _Take a Picture_ quality check is required.

On the MO, select the Work Orders tab, and then click the Open Work Order (external link icon) button on the line of the work order to be processed. On the resulting Work Orders pop-up window, click the Open Shop Floor button to open the _Shop Floor_ module.

When accessed from a specific work order, the _Shop Floor_ module opens to the page for the work center where the order is configured to be processed, and isolates the work order’s card, so no other cards are shown.

Process the work order’s steps until the _Take a Picture_ quality check step is reached. Click on the step to open a pop-up window that includes instructions for how the picture should be taken. After taking the picture, make sure it is stored on the device being used to process the quality check (computer, tablet, etc.).

Then, click the Take a Picture button on the pop-up window to open the device’s file manager. In the file manager, navigate to the picture, select it, and click Open to attach it.

Finally, click Validate at the bottom of the pop-up window to complete the quality check. The pop-up window then moves on to the next step of the work order.

If a quality alert must be created, exit the pop-up window by clicking the X (close) button in the top-right corner.

Then, click the ⋮ (three vertical dots) button on the bottom-right corner of the work order card to open the What do you want to do? pop-up window.

On the What do you want to do? pop-up window, select the Create a Quality Alert button. Doing so opens a blank quality alert form in a new Quality Alerts pop-up window.

Vedi anche

For a complete guide on how to fill out quality alert forms, view the documentation on [quality alerts](../quality_management/quality_alerts.html).

## Review picture attached to quality check¶

After a picture has been attached to a check, it can then be reviewed by quality team members or other users. To do so, navigate to Quality ‣ Quality Control ‣ Quality Checks, and select a quality check to review.

The attached picture appears in the Picture section of the quality check form. After reviewing the picture, click the Pass button if the check passes, or the Fail button if the check fails.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/quality/quality_check_types/picture_check.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../maintenance.html "Manutenzione") |
  * [precedente](measure_check.html "Measure quality check") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality check types](../quality_check_types.html) »
  * Take a Picture quality check


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
  *[FBM]: Fulfilled by Merchant
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