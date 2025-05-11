# Canada — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chile.html "Cile") |
  * [precedente](brazil.html "Brasile") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Canada



# Canada¶

The Odoo Canada localization package provides tailored features and configurations for Canadian businesses.

A series of videos on the subject of Accounting are available through Odoo’s eLearning platform. These videos cover how to start from scratch, set up configurations, complete common workflows, and provide in-depth looks at some specific use cases.

Vedi anche

  * [Odoo Tutorials: Accounting & Invoicing](https://www.odoo.com/slides/accounting-and-invoicing-19)

  * [Odoo SmartClass: Accounting](https://www.odoo.com/slides/smartclass-accounting-121)




## Configurazione¶

Below are the available modules in Odoo for accounting use in Canada.

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Canadian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Canada - Accounting | `l10n_ca` | Base accounting module for Canadian localization.  
Canada - Accounting Reports | `l10n_ca_reports` | Adds Canadian accounting reports.  
Canadian Checks Layout | `l10n_ca_check_printing` | Enables the printing of payments on pre-printed check paper. Supports the three most common check formats and works natively with the linked checks from [checkdepot.net](https://checkdepot.net/collections/computer-checks/Odoo).

  * [Check on top: Quicken / QuickBooks standard](https://checkdepot.net/collections/computer-checks/odoo+top-check)
  * [Check on middle: Peachtree standard](https://checkdepot.net/collections/computer-checks/odoo+middle-check)
  * [Check on bottom: ADP standard](https://checkdepot.net/collections/computer-checks/odoo+Bottom-Check)

  
  
## Piano dei conti¶

The [chart of accounts (COA)](../accounting/get_started/chart_of_accounts.html) for the Canadian localization, in Odoo, has accounts grouped into seven main categories, with corresponding numeric values that prefix individual journal entries:

  * **Receivable** : the balance of money (or credit) due to the business for goods or services delivered or used, but not yet paid for by customers. AR is indicated by the journal code labeled (or beginning) with 1.

  * **Payable** : the business’s short-term obligations owed to its creditors or suppliers, which have not yet been paid. AP is indicated by the journal code labeled (or beginning) with 2.

  * **Equity** : the amount of money that would be returned to a company’s shareholders if all of the assets were liquidated and all of the company’s debt was paid off in the case of liquidation. Equity is indicated by the journal code labeled (or beginning) with 3 or 9.

  * **Assets** : items listed on the balance sheet that contains economic value or have the ability to generate cash flows in the future, such as a piece of machinery, a financial security, or a patent. Assets are indicated by the journal code labeled (or beginning) with 1.

  * **Liability** : refers to a company’s financial debts or obligations that arise during the course of business operations. Liabilities are indicated by the journal code labeled (or beginning) with 2.

  * **Income** : synonymous with _net income_ , this is the profit a company retains after paying off all relevant expenses from sales revenue earned. Income is indicated by the journal code labeled (or beginning) with 4 or 6.

  * **Expenses** : the cost of operations that a company incurs to generate revenue. Expenses are indicated by the journal code labeled (or beginning) with a 6.




Suggerimento

Predefined accounts are included in Odoo, as part of the CoA that’s installed with the Canadian localization package. The accounts listed below are preconfigured to perform certain operations within Odoo. It is recommended to **not** delete these accounts; however, if changes are needed, rename the accounts instead.

Type | Account Name  
---|---  
Current Assets |  Bank Suspense Account Outstanding Receipts Outstanding Payments Liquidity Transfer Stock Valuation Stock Interim (Received) Stock Interim (Delivered) Cost of Production  
Income |  Foreign Exchange Gain Cash Difference Gain Cash Discount Gain  
Expenses |  Cash Discount Loss Foreign Exchange Loss Cash Difference Loss  
Current Year Earnings | Undistributed Profits/Losses  
Receivable | Account Receivable  
Payable | Account Payable  
  
Vedi anche

  * [Piano dei conti](../accounting/get_started/chart_of_accounts.html)

  * [Promemoria contabile](../accounting/get_started/cheat_sheet.html)




## Fiscal positions¶

Canadian tax rates and taxable items vary by province and territory. Default fiscal positions are automatically created when the Odoo **Accounting** application is installed. To manage or configure additional fiscal positions, navigate to Accounting ‣ Configuration ‣ Fiscal Positions.

The following fiscal positions are available by default:

  * Alberta (AB)

  * British Columbia (BC)

  * Manitoba (MB)

  * New Brunswick (NB)

  * Newfoundland and Labrador (NL)

  * Nova Scotia (NS)

  * Northwest Territories (NT)

  * Nunavut (NU)

  * Ontario (ON)

  * Prince Edward Islands (PE)

  * Quebec (QC)

  * Saskatchewan (SK)

  * Yukon (YT)

  * International (INTL)




Nota

When considering what taxes to be applied, it is the province where the delivery occurs that matters. Therefore, delivery is the responsibility of the vendor and is accounted for at the customer location.

Example

  * A delivery is made to a customer from another province.
    

Set the fiscal position on the customer’s record to the province of the customer.

  * A customer from another province comes to pick up products.
    

No fiscal position should be set on the customer’s record.

  * An international vendor doesn’t charge any tax, but taxes are charged by the customs broker.
    

Set the fiscal position on the vendor’s record to _International_.

  * An international vendor charges provincial tax.
    

Set the fiscal position on the vendor’s record to your position.




Vedi anche

[Posizioni di bilancio (mappatura fiscale e contabile)](../accounting/taxes/fiscal_positions.html)

## Imposte¶

In Canada, tax rates and what is considered taxable vary by province and territory. Default _Sales_ and _Purchases_ taxes are created automatically when the Odoo **Accounting** application is installed. To manage existing or configure additional taxes, navigate to Accounting ‣ Configuration ‣ Taxes.

### AvaTax¶

**Avalara AvaTax** is a cloud-based tax calculation and compliance software that integrates with Odoo for several localizations, including Canada. Integrating AvaTax with Odoo provides real-time and region-specific tax calculations when items are sold, purchased, and invoiced in the database.

Importante

AvaTax is available for integration with databases/companies that have locations in Canada and/or the United States. Reference the [Paese fiscale](../accounting/taxes/avatax.html#avatax-fiscal-country) documentation for more information.

Vedi anche

Refer to the documentation articles below to integrate and configure an AvaTax account with an Odoo database:

  * [AvaTax integration](../accounting/taxes/avatax.html)

  * [Avalara management portal](../accounting/taxes/avatax/avalara_portal.html)

  * [Calculate taxes with AvaTax](../accounting/taxes/avatax/avatax_use.html)

  * Avalara’s support documents: [About AvaTax](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=dqa1657870670369_dqa1657870670369&topicId=About_AvaTax.html&_LANG=enus)




## Report¶

A number of [report selections](../accounting/reporting.html) are readily available for the Canadian localization, under the Accounting app ‣ Reporting drop-down menu:

  * [Balance Sheet](../accounting/reporting.html#accounting-reporting-balance-sheet): a «snapshot» of a company’s financial position at a specific point in time, which contains an overview of a company’s assets, liabilities, and equity.

Be sure to select the Balance sheet (CA) option from the __ Report filter.

  * [Profit & Loss](../accounting/reporting.html#accounting-reporting-balance-sheet): otherwise known as a _P &L statement_ or _income statement_ , provides a summary of a company’s revenues, expenses, and profits/losses over a given period of time.

Be sure to select the Profit and loss (CA) option from the __ Report filter.

  * Cash Flow Statement: shows how much cash and cash equivalents a company has received and spent in a given period.

  * [Executive Summary](../accounting/reporting.html#accounting-reporting-executive-summary): an overview report that covers the key performance indicators of a company’s financial position, such as revenue, profit, and debt.

  * [Tax Report](../accounting/reporting.html#accounting-reporting-tax-report): an official form filed for a tax authority that reports income, expenses, and other pertinent tax information. Tax reports allow taxpayers to calculate their tax liability, schedule tax payments, or request refunds for the overpayment of taxes. In Odoo, the tax report can be made monthly, every two months, quarterly, every 4 months, semi-annually, and annually.




Vedi anche

  * [Accounting reporting](../accounting/reporting.html)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




## Cash discount¶

Cash discounts can be configured from Accounting app ‣ Payment Terms. Each payment term can be set up with a cash discount and reduced tax.

Vedi anche

[Sconti di cassa e riduzioni fiscali](../accounting/customer_invoices/cash_discounts.html)

## Writing checks¶

The Canadian localization allows users to print checks for vendor payments. Be sure the _Canadian Checks Layout_ (`l10n_ca_check_printing`) module for the CA localization is [installed](../../general/apps_modules.html#general-install).

To enable check printing from Odoo, navigate to Accounting ‣ Configuration ‣ Settings and find the Vendor Payments section. From here, tick the Checks checkbox to reveal several fields for check configuration.

Select a Check Layout from the drop-down menu:

  * Print Check (Top) - CA

  * Print Check (Middle) - CA

  * Print Check (Bottom) - CA




Next, choose whether or not to enable the Multi-Pages Check Stub checkbox.

Optionally set a Check Top Margin, Check Left Margin, or Check Right Margin if required.

Tick the Print Date Label checkbox if a date label is required.

Once all check configurations are complete, Save the settings.

Suggerimento

Some of the check formats may require pre-printed paper from a third party vendor. [Pre-printed checks from checkdepot.net](https://checkdepot.net/collections/odoo-checks) are recommended.

Vedi anche

[Pay by checks](../accounting/payments/pay_checks.html)

## Receive pre-authorized debits¶

Pre-authorized debits are a method for receiving payments from customers, where the customer authorizes the business to withdraw funds from their bank account on a recurring basis. This functionality is commonly used for subscriptions, recurring invoices, and other regular payments.

In the Odoo Canadian localization, pre-authorized debits are facilitated through an [integration with Stripe](../payment_providers/stripe.html).

Vedi anche

  * [Setting up payment providers](../payment_providers.html)

  * [Stripe’s pre-authorized debit payments documentation](https://docs.stripe.com/payments/acss-debit)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/canada.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chile.html "Cile") |
  * [precedente](brazil.html "Brasile") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Canada


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Interchange
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
  *[API]: application programming interface
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
  *[OTP]: one-time password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: Chart of Accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: Automated Clearing House
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
  *[PAC]: fornitori autorizzati
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
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
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