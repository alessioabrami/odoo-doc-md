# Giordania — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](united_arab_emirates.html "Emirati Arabi Uniti") |
  * [precedente](hong_kong.html "Hong Kong") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Human resources](../../../hr.html) »
  * [Libro paga](../../payroll.html) »
  * [Payroll localizations](../payroll_localizations.html) »
  * Giordania



# Giordania¶

The Jordan **Payroll** localization package offers a comprehensive solution for managing payroll in compliance with Jordanian labor laws. It supports income tax calculations using progressive tax brackets, social security contributions from both employees and employers and basic salary calculations, including allowances such as housing and transportation.

## Configurazione¶

[Install](../../../general/apps_modules.html#general-install) the following modules to get all the features of the Jordan **Payroll** localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Jordan - Payroll | `l10n_jo_hr_payroll` | Payroll module supporting basic calculation, tax income brackets, and national contribution tax and social security  
Jordan - Payroll with Accounting | `l10n_jo_hr_payroll_account` | Bridge module between **Payroll** and **Accounting**  
  
Vedi anche

[Jordan fiscal localization documentation](../../../finance/fiscal_localizations/jordan.html)

## Basic calculations¶

The Jordan **Payroll** localization package in Odoo provides foundational payroll management tools that are compliant with Jordan’s labor laws and regulations. Key features include:

  * **Basic salary calculations** : Odoo supports the computation of employee salaries based on predefined salary structures, ensuring accurate payroll processing.

  * **Social security contributions** : It handles social security deductions for employees and employer contributions, aligning with local regulations.

  * **Taxation support** : The system is configured to handle income tax calculations in Jordan, including deductions based on progressive tax brackets as required by Jordanian labor and tax laws.

  * **Custom allowances and deductions** : The localization supports additional allowances, deductions, or overtime as part of payroll computation.




These features ensure businesses can manage payroll effectively and comply with Jordanian-specific legal requirements. For enhanced functionality, businesses may leverage Odoo’s flexibility to customize payroll workflows.

## Social security¶

The Jordan **Payroll** localization package in Odoo simplifies social security management by automating calculations for both employees and employers. Contributions are based on a percentage of the employee’s basic salary, with a maximum insurable wage cap in line with Jordanian Social Security Corporation (SSC) regulations.

### Employee contributions¶

Odoo calculates the employee’s social security deduction as 7.5% of their basic salary, up to the insurable wage cap of 3,000 JOD. If the employee’s salary exceeds this cap, the deduction is based on the capped amount. This ensures compliance with SSC requirements and reflects accurately on the employee’s payslip.

### Employer contributions¶

For employers, Odoo computes social security contributions as 14.25% of the employee’s basic salary, also capped at 3,000 JOD. Like the employee contributions, if the salary exceeds this cap, the employer’s contribution is calculated based on the capped amount. These contributions include pensions, workplace injury insurance, and other mandated benefits.

### Key features¶

  * **Capped contributions** : The system ensures that both employee and employer contributions are aligned with the SSC-mandated insurance cap.

  * **Automated calculations** : Contributions are automatically calculated and included in payroll, reducing errors and administrative work.

  * **Compliance with regulations** : Odoo’s configuration ensures full compliance with Jordanian social security laws, reflecting the correct rates and caps for both sides.




## Income tax calculation¶

The Jordan **Payroll** localization package automates income tax calculations using progressive tax brackets, ensuring compliance with Jordanian labor laws. The system applies income tax rates based on the employee’s annual gross income, with higher brackets subject to increased percentages. The calculations are divided into six brackets, and the appropriate tax is deducted monthly.

### Tax brackets¶

  * **5% bracket** : Applicable to annual gross income up to 5,000 JOD. Odoo calculates 5% of the income within this range. If the gross income is below 5,000 JOD, the entire amount is taxed at 5%.

  * **10% bracket** : Applicable to annual gross income between 5,001 and 10,000 JOD. Only the portion of income exceeding 5,000 JOD is taxed at 10%. For example, if the gross income is 7,000 JOD, only 2,000 JOD is taxed at 10%.

  * **15% bracket** : Applicable to annual gross income between 10,001 and 15,000 JOD. The portion of income exceeding 10,000 JOD up to 15,000 JOD is taxed at 15%. For instance, if the gross income is 12,000 JOD, only 2,000 JOD is taxed at 15%.

  * **20% bracket** : Applicable to annual gross income between 15,001 and 20,000 JOD. Income within this range is taxed at 20%, with deductions automatically adjusted by Odoo.

  * **25% bracket** : Applicable to annual gross income between 20,001 and 1,000,000 JOD. Income beyond 20,000 JOD up to 1,000,000 JOD is taxed at 25%. For higher incomes, Odoo ensures accurate calculations by applying the cap of this range.

  * **30% bracket** : Applicable to annual gross income exceeding 1,000,000 JOD. Any income above this amount is taxed at 30%, with the system ensuring accurate monthly deductions for high-income earners.




### Automated process¶

Odoo determines the appropriate tax bracket for each employee based on their gross annual income and applies the corresponding rates. These deductions are prorated and deducted monthly, simplifying payroll management and ensuring compliance.

### Key features¶

  * **Progressive tax system** : Calculates taxes for each income range individually, ensuring fairness and accuracy.

  * **Automated deductions** : Ensures a smooth payroll workflows with accurate and timely monthly tax deductions.

  * **Alignment with Jordanian regulations** : Fully complies with Jordanian tax laws, minimizing manual intervention and errors.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/payroll/payroll_localizations/jordan.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](united_arab_emirates.html "Emirati Arabi Uniti") |
  * [precedente](hong_kong.html "Hong Kong") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Human resources](../../../hr.html) »
  * [Libro paga](../../payroll.html) »
  * [Payroll localizations](../payroll_localizations.html) »
  * Giordania


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
  *[POS]: Punto vendita
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