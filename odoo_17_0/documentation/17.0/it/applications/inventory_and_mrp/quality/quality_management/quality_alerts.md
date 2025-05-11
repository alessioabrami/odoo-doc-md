# Quality alerts — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_checks.html "Quality checks") |
  * [precedente](quality_control_points.html "Quality control points") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality alerts



# Quality alerts¶

In the Odoo _Quality_ app, _quality alerts_ are used to notify quality teams of product defects or other issues. Quality alerts can be created from a manufacturing or inventory order, from a work order in the _Shop Floor_ module, or directly within the _Quality_ app.

## Create quality alerts¶

There are multiple ways to create a new quality alert:

  * **From the Quality app itself** , by to Quality ‣ Quality Control ‣ Quality Alerts, and then click New to open a quality alert form.

  * Navigate to Manufacturing ‣ Operations ‣ Manufacturing Orders, and then select an MO. Click the Quality Alert button at the top of the MO to open a quality alert form in a new page.

Importante

This method can only be used if a quality check has been requested for the MO. The Quality Alert button will not appear otherwise.

  * Open the Inventory app, click the # To Process button on an inventory order type card (Receipts, Delivery Orders, etc.), and then select an order. Click the Quality Alert button at the top of the order to open a quality alert form in a new page.

Importante

This method can only be used if a quality check has been requested for the inventory order. The Quality Alert button will not appear otherwise. If the button does not appear, a quality alert can also be created by clicking the ⚙️ (gear) icon at the top of the page and selecting the Quality Alert option from the resulting menu.

  * Open the Shop Floor module, and then select a work center from the navigation bar at the top of the page. Then, click the ⋮ (three vertical dots) button at the bottom-right of a work order card to open the What do you want to do? menu. Select the Create a Quality Alert option from this menu to open a quality alert in a pop-up window.




Nota

Depending on how a new quality alert form is opened, certain fields on the form may already be filled in. For example, if a quality alert is created from a work order card in the _Shop Floor_ module, the Product and Work Center are pre-filled.

### Quality alerts form¶

After opening a new quality alert form, begin by giving it a short Title that summarizes the issue with the product.

Then, if the quality alert is referencing:

  * **A specific product or product variant** , select it from the Product or Product Variant drop-down menus.

  * **A specific work center** , select it from the Work Center drop-down menu.

  * **A specific picking order** , select it from the Picking drop-down menu.




Next in the Team field, select the quality team that is responsible for managing the quality alert. If a specific employee should be responsible for the quality alert, select them from the Responsible drop-down menu.

In the Tags field, select any tags relevant to the quality alert from the drop-down menu.

Use the Root Cause field to select the cause of the quality issue, if known.

Lastly, choose a Priority level by selecting a ⭐ (star) number between one and three. Quality alerts with higher priorities appear at the top of the Quality Alerts Kanban board in the _Quality_ app.

At the bottom of the quality alert form are four tabs which aid in adding supplemental information or actions to be taken for the quality alert. They can be filled out as follows:

  * In the Description tab, enter a description of the quality issue.

  * Use the Corrective Actions tab to detail the steps that should be taken to fix the issue.

  * Use the Preventive Actions tab to detail what should be done to prevent the issue from occurring in the future.

  * In the Miscellaneous tab, select the Vendor of the product. If using an Odoo database which manages multiple companies, select the relevant company in the Company field. Finally, specify when the alert was assigned to a quality team in the Date Assigned field.




## Manage quality alerts¶

To view all existing quality alerts, navigate to Quality ‣ Quality Control ‣ Quality Alerts. By default, alerts are displayed in a Kanban board view, which organizes them into different stages based on where they are in the review process.

To move an alert to a different stage, simply drag and drop it on the desired stage. Alternatively, select a quality alert to open it, and then click the desired stage above the top-right corner of the quality alert form.

To create a new alert within a specific stage, click the \+ (plus) button to the right of the stage name. In the new alert card that appears below the stage title, enter the Title of the alert, and then click Add. To configure the rest of the alert, select the alert card to open its form.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/quality/quality_management/quality_alerts.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](quality_checks.html "Quality checks") |
  * [precedente](quality_control_points.html "Quality control points") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Qualità](../../quality.html) »
  * [Quality control basics](../quality_management.html) »
  * Quality alerts


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