# Regno Unito — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](united_states.html "Stati Uniti") |
  * [precedente](united_arab_emirates.html "Emirati Arabi Uniti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Regno Unito



# Regno Unito¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the UK - Accounting and the UK - Accounting Reports modules to get all the features of the UK localization.

Nome | Nome tecnico | Descrizione  
---|---|---  
UK - Accounting | `l10n_uk` | 

  * CT600-ready chart of accounts
  * VAT100-ready tax structure
  * Infologic UK counties listing

  
UK - Accounting Reports | `l10n_uk_reports` | 

  * Accounting reports for the UK
  * Allows sending the tax report via the MTD-VAT API to HMRC.

  
UK BACS Payment Files | `account_bacs` | Allows generating Bacs files for bill and invoice payments  
  
Nota

  * Only UK-based companies can submit reports to HMRC.

  * Installing the module UK - Accounting Reports installs all two modules at once.




Vedi anche

  * [HM Revenue & Customs](https://www.gov.uk/government/organisations/hm-revenue-customs/)

  * [Overview of Making Tax Digital](https://www.gov.uk/government/publications/making-tax-digital/overview-of-making-tax-digital/)




## Piano dei conti¶

The UK chart of accounts is included in the UK - Accounting module. Go to Accounting ‣ Configuration ‣ Accounting: Chart of Accounts to access it.

Setup your CoA by going to Accounting ‣ Configuration ‣ Settings ‣ Accounting Import section and choose to Review Manually or Import (recommended) your initial balances.

## Imposte¶

As part of the localization module, UK taxes are created automatically with their related financial accounts and configuration.

Go to Accounting ‣ Configuration ‣ Settings ‣ Taxes to update the Default Taxes, the Tax Return Periodicity or to Configure your tax accounts.

To edit existing taxes or to Create a new tax, go to Accounting ‣ Configuration ‣ Accounting: Taxes.

Vedi anche

  * [taxes](../accounting/taxes.html)

  * Tutorial: [Tax report and return](https://www.odoo.com/slides/slide/tax-report-and-return-1719?fullscreen=1).




### Making Tax Digital (MTD)¶

In the UK, all VAT-registered businesses have to follow the MTD rules by using software to submit their VAT returns.

The **UK - Accounting Reports** module enables you to comply with the [HM Revenue & Customs](https://www.gov.uk/government/organisations/hm-revenue-customs/) requirements regarding [Making Tax Digital](https://www.gov.uk/government/publications/making-tax-digital/overview-of-making-tax-digital/).

Importante

If your periodic submission is more than three months late, it is no longer possible to submit it through Odoo, as Odoo only retrieves open bonds from the last three months. Your submission has to be done manually by contacting HMRC.

#### Register your company to HMRC before the first submission¶

Go to Accounting ‣ Reporting ‣ Tax report and click on Connect to HMRC. Enter your company information on the HMRC platform. You only need to do it once.

#### Periodic submission to HMRC¶

Import your obligations HMRC, filter on the period you want to submit, and send your tax report by clicking Send to HMRC.

Suggerimento

You can use dummy credentials to demo the HMRC flow. To do so, activate the [developer mode](../../general/developer_mode.html#developer-mode) and go to General Settings ‣ Technical ‣ System Parameters. From here, search for `l10n_uk_reports.hmrc_mode` and change the value line to `demo`. You can get such credentials from the [HMRC Developer Hub](https://developer.service.hmrc.gov.uk/api-test-user).

#### Periodic submission to HMRC for multi-company¶

Only one company and one user can connect to HMRC simultaneously. If several UK-based companies are on the same database, the user who submits the HMRC report must follow these instructions before each submission:

  1. Log into the company for which the submission has to be done.

  2. Go to General Settings, and in the Users section, click Manage Users. Select the user who is connected to HMRC.

  3. Go to the UK HMRC Integration tab and click Reset Authentication Credentials or Remove Authentication Credentials button.

  4. You can now register your company to HMRC and submit the tax report for this company.

  5. Repeat the steps for other companies” HMRC submissions.




Nota

During this process, the Connect to HMRC button no longer appears for other UK-based companies.

## Bacs files¶

Bacs files are electronic files used in the UK to process payments and transfers between bank accounts.

To enable the use of Bacs files, make sure the UK BACS Payment Files module is installed, then:

  1. Configure your Bacs Service User Number:

     1. Go to Accounting ‣ Configuration ‣ Settings and scroll down to the Customer Payments section.

     2. Enter your Service User Number under BACS and manually save.

  2. Configure your **bank** journal:

     1. Go to Accounting ‣ Configuration ‣ Journals and select your **bank** journal.

     2. In the Journal Entries tab, configure the Account Number and Bank fields.

     3. In the Incoming Payments and Outgoing Payments tabs, make sure the BACS Direct Debit payment method is enabled.

  3. Configure the contacts for whom you wish to use Bacs files: Access the contact form and, in the Accounting tab, click Add a line and fill in the Account Number and Bank fields.




### Bill payments¶

To generate Bacs files for bill payments, set the Payment Method to BACS Direct Debit when [registering vendor payments](../accounting/payments.html).

Then, create a vendor batch payment:

  1. Go to Accounting ‣ Vendors ‣ Batch Payments, and click New.

  2. Select the bank journal in the Bank field, set the Payment Method to BACS Direct Credit, and select a BACS Processing Date.

  3. Optionally, you can also:

     * select a BACS Expiry Date;

     * enable BACS Multi Mode to process the payments on their individual date.

  4. Click Add a line, select the payments you want to include, click Select, then Validate.




Once validated, the Bacs file is available in the chatter. You can also Re-generate Export File if you need a new Bacs file for that batch payment.

Vedi anche

[Pagamenti raggruppati](../accounting/payments/batch.html)

### Invoice payments¶

Before generating Bacs files for invoice payments, you must first create a **BACS Direct Debit Instruction** : Go to Accounting ‣ Customers ‣ BACS Direct Debit Instructions and click New. Select a Customer, their IBAN, and the Journal you wish to use.

To generate Bacs files for invoice payments, set the Payment Method to BACS Direct Debit when [registering invoice payments](../accounting/payments.html).

Suggerimento

If you register the payment for an invoice linked to a subscription or via Accounting ‣ Customers ‣ Payments, you can select the BACS Payment Type:

  * Direct debit-first collection of a series;

  * Direct debit single collection;

  * Direct debit repeating collection in a series;

  * Direct debit-final collection of a series.




Then, create a customer batch payment:

  1. Go to Accounting ‣ Customers ‣ Batch Payments, and click New.

  2. Select the bank journal in the Bank field, set the Payment Method to BACS Direct Credit, and select a BACS Processing Date.

  3. Optionally, you can also:

     * select a BACS Expiry Date;

     * enable BACS Multi Mode to process the payments on their individual date.

  4. Click Add a line, select the payments you want to include, click Select, then Validate.




Once validated, the Bacs file is available in the chatter. You can also Re-generate Export File if you need a new Bacs file for that batch payment.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/united_kingdom.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](united_states.html "Stati Uniti") |
  * [precedente](united_arab_emirates.html "Emirati Arabi Uniti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Regno Unito


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
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services