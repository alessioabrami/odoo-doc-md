# Year-end closing — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../expenses.html "Costi") |
  * [precedente](customize.html "Custom reports") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Year-end closing



# Year-end closing¶

Year-end closing is vital for maintaining financial accuracy, complying with regulations, making informed decisions, and ensuring transparency in reporting.

## Anni fiscali¶

By default, the fiscal year is set to last 12 months and end on December 31st. However, its duration and end date can vary due to cultural, administrative, and economic considerations.

To modify these values, go to Accounting ‣ Configuration ‣ Settings. Under the Fiscal Periods section, change the Last Day field if necessary.

If the period lasts _more_ than or _less_ than 12 months, enable Fiscal Years and Save. Go back to the Fiscal Periods section and click ➜ Fiscal Years. From there, click Create, give it a Name, and both a Start Date and End Date.

Nota

Once the set fiscal period is over, Odoo automatically reverts to the default periodicity, taking into account the value specified in the Last Day field.

## Year-end checklist¶

### Before closure¶

Before closing a fiscal year, ensure first everything is accurate and up-to-date:

  * Make sure all bank accounts are fully [reconciled](../bank/reconciliation.html) up to year-end, and confirm that the ending book balances match the bank statement balances.

  * Verify that all [customer invoices](../customer_invoices.html) have been entered and approved and that there are no draft invoices.

  * Confirm that all [vendor bills](../vendor_bills.html) have been entered and agreed upon.

  * Validate all [expenses](../../expenses.html), ensuring their accuracy.

  * Corroborate that all [received payments](../payments.html) have been encoded and recorded accurately.

  * Close all [suspense accounts](../bank.html#accounting-bank-suspense).

  * Book all [depreciation](../vendor_bills/assets.html) and [deferred revenue](../customer_invoices/deferred_revenues.html) entries.




### Closing a fiscal year¶

Then, to close the fiscal year:

  * Run a [tax report](../reporting.html#accounting-reporting-tax-report), and verify that all tax information is correct.

  * Reconcile all accounts on the [balance sheet](../reporting.html#accounting-reporting-balance-sheet):

    * Update the bank balances in Odoo according to the actual balances found on the bank statements.

    * Reconcile all transactions in the cash and bank accounts by running the [aged receivables](../reporting.html#accounting-reporting-aged-receivable) and [aged payables](../reporting.html#accounting-reporting-aged-payable) reports.

    * Audit all accounts, being sure to fully understand all transactions and their nature, making sure to include loans and fixed assets.

    * Optionally, [match payments](../payments.html#accounting-payments-auto-reconcile-tool) to validate any open vendor bills and customer invoices with their payments. While this step is optional, it could assist the year-end closing process if all outstanding payments and invoices are reconciled, potentially finding errors or mistakes in the system.




Next, the accountant likely verifies balance sheet items and book entries for:

>   * year-end manual adjustments,
> 
>   * work in progress,
> 
>   * depreciation journal entries,
> 
>   * loans,
> 
>   * tax adjustments,
> 
>   * etc.
> 
> 


If the accountant is going through the year-end audit, they may want to have paper copies of all balance sheet items (such as loans, bank accounts, prepayments, sales tax statements, etc.) to compare these with the balances in Odoo.

Suggerimento

During this process, it is good practice to set a Journal Entries Lock Date to the last day (inclusive) of the preceding fiscal year by going to Accounting ‣ Accounting ‣ Lock Dates. This way, the accountant can be confident that nobody changes the transactions while auditing the books. Users from the _accountant_ access group can still create and modify entries.

#### Current year’s earnings¶

Odoo uses a unique account type called **current year’s earnings** to display the amount difference between the **income** and **expenses** accounts.

Nota

The chart of accounts can only contain one account of this type. By default, it is a 999999 account named Undistributed Profits/Losses.

To allocate the current year’s earnings, create a miscellaneous entry to book them to any equity account. Once done, confirm whether or not the current year’s earnings in the **balance sheet** is correctly reporting a balance of zero. If that is the case, set an All Users Lock Date to the last day of the fiscal year by going to Accounting ‣ Accounting ‣ Lock Dates.

Suggerimento

Install the Irreversible Lock Date (`account_lock`) module to make the All Users Lock Date _irreversible_ once set.

Nota

A specific year-end closing entry is **optional** in order to close out the **profit and loss statement**. The reports are created in real-time, meaning that the profit and loss statement corresponds directly with the year-end date specified in Odoo. Therefore, any time the **income statement** is generated, the beginning date corresponds with the beginning of the **fiscal year** and all account balances should equal zero.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/reporting/year_end.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../expenses.html "Costi") |
  * [precedente](customize.html "Custom reports") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Year-end closing


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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
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