# Costi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expenses/log_expenses.html "Log expenses") |
  * [precedente](accounting/reporting/year_end.html "Year-end closing") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Costi



# Costi¶

Odoo **Expenses** streamlines the management of expenses. After an employee submits their expenses in Odoo, they are reviewed by management and accounting teams. Once approved, payments can then be processed, and disbursed back to the employee for reimbursement.

Vedi anche

[Odoo Expenses: product page](https://www.odoo.com/app/expenses)

## Set expense categories¶

The first step to track expenses is to configure the different types of expenses for the company (managed as _expense categories_ in Odoo). Each category can be as specific or generalized as needed. Go to Expenses app ‣ Configuration ‣ Expense Categories to view the current expensable categories in a default list view.

To create a new expense category, click New. A product form will appear, with the description field labeled Product Name.

Nota

Expense categories are managed like products in Odoo. The expense category form follows the standard product form in Odoo, and the information entered is similar. Expense products will be referred to as expense categories throughout this document since the main menu refers to these as Expense Categories.

Only two fields are required, the Product Name and the Unit of Measure. Enter the Product Name in the field, and select the Unit of Measure from the drop-down menu (most products will be set to Units).

Suggerimento

The _Sales_ app is where specification on the units of measure are created and edited (e.g. units, miles, nights, etc.). Go to Sales app ‣ Configuration ‣ Settings and ensure `Units of Measure` is enabled in the `Product Catalog` section. Click on the Units of Measure internal link to [view, create, and edit the units of measure](../inventory_and_mrp/inventory/product_management/configure/uom.html).

The Cost field on the product form is populated with a value of `0.00` by default. When a specific expense should always be reimbursed for a particular price, enter that amount in the Cost field. Otherwise, leave the Cost set to `0.00`, and employees will report the actual cost when submitting an expense report.

Nota

The Cost field is always visible on the expense category form, but the Sales Price field is _only_ visible if the Sales Price is selected under the Re-Invoice Expenses section. Otherwise, the Sales Price field is hidden.

Example

Here are some examples for when to set a specific Cost on a product vs. leaving the Cost at `0.00`:

  * **Meals** : set the Cost to `0.00`. When an employee logs an expense for a meal, they enter the actual amount of the bill and will be reimbursed for that amount. An expense for a meal costing $95.23 would equal a reimbursement for $95.23.

  * **Mileage** : set the Cost to `0.30`. When an employee logs an expense for «mileage», they enter the number of miles driven in the Quantity field, and are reimbursed 0.30 per mile they entered. An expense for 100 miles would equal a reimbursement for $30.00.

  * **Monthly Parking** : set the Cost to `75.00`. When an employee logs an expense for «monthly parking», the reimbursement would be for $75.00.

  * **Expenses** : set the Cost to `0.00`. When an employee logs an expense that is not a meal, mileage, or monthly parking, they use the generic Expenses product. An expense for a laptop costing $350.00 would be logged as an Expenses product, and the reimbursement would be for $350.00.




Select an Expense Account if using the Odoo _Accounting_ app. It is recommended to check with the accounting department to determine the correct account to reference in this field as it will affect reports.

Set a tax on each product in the Vendor Taxes and Customer Taxes fields, if applicable. It is considered good practice to use a tax that is configured with [Tax Included in Price](accounting/taxes.html#taxes-included-in-price). Taxes will be automatically configured if this is set.

Vedi anche

  * [Log expenses](expenses/log_expenses.html)

  * [Expense reports](expenses/expense_reports.html)

  * [Approve expenses](expenses/approve_expenses.html)

  * [Registra spese](expenses/post_expenses.html)

  * [Reimburse employees](expenses/reimburse.html)

  * [Re-invoice expenses](expenses/reinvoice_expenses.html)




  * [Log expenses](expenses/log_expenses.html)
  * [Expense reports](expenses/expense_reports.html)
  * [Approve expenses](expenses/approve_expenses.html)
  * [Registra spese](expenses/post_expenses.html)
  * [Reimburse employees](expenses/reimburse.html)
  * [Re-invoice expenses](expenses/reinvoice_expenses.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/expenses.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expenses/log_expenses.html "Log expenses") |
  * [precedente](accounting/reporting/year_end.html "Year-end closing") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Costi


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[API]: application programming interfaces
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
  *[POS]: point of sale
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