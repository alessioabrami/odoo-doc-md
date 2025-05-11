# Filippine — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](saudi_arabia.html "Arabia Saudita") |
  * [precedente](peru.html "Perù") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Filippine



# Filippine¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the 🇵🇭 Philippines [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) to get all the default accounting features of the Philippine localization, such as a chart of accounts, taxes, and the BIR 2307 report. These provide a base template to get started with using Philippine accounting.

Nota

  * When creating a new database and selecting the `Philippines` as a country, the fiscal localization module **Philippines - Accounting** is automatically installed.

  * If the module is installed in an existing company, the **chart of accounts** and **taxes** will _not_ be replaced if there are already posted journal entries.

  * The BIR 2307 report is installed, but the withholding taxes may need to be manually created.




### Chart of accounts and taxes¶

A minimum configuration default chart of accounts is installed, and the following types of taxes are installed and linked to the relevant account:

  * Sales and Purchase VAT 12%

  * Sales and Purchase VAT Exempt

  * Sales and Purchase VAT Zero-Rated

  * Purchase Withholding




For the withholding taxes (Configuration ‣ Taxes), there is an additional Philippines ATC field under the Philippines tab.

Nota

Taxes” ATC codes are used for the BIR 2307 report. If a tax is created manually, its ATC code must be added.

### Contatti¶

When a company or an individual (not belonging to a company) contact is located in the Philippines, fill in the Tax ID field with their `Taxpayer Identification Number (TIN)`.

For individuals not belonging to a company, identify them by using the following additional fields:

  * First Name

  * Middle Name

  * Last Name




Nota

For both Company and Individual, the TIN should follow the `NNN-NNN-NNN-NNNNN` format. The branch code should follow the last digits of the TIN, or else it can be left as `00000`.

## BIR 2307 report¶

**BIR 2307** report data, also known as [Certificate of Creditable Tax Withheld at Source](https://www.bir.gov.ph/index.php/bir-forms/certificates.html), can be generated for purchase orders and vendor payments with the applicable withholding taxes.

To generate a BIR 2307 report, select one or multiple vendor bills from the list view, and click Action ‣ Download BIR 2307 XLS.

Suggerimento

The same action can be performed on a vendor bill from the form view.

A pop-up appears to review the selection, then click on Generate.

This generates the `Form_2307.xls` file that lists all the vendor bill lines with the applicable withholding tax.

The process above can also be used for a _single_ vendor [payment](../accounting/payments.html) if it is linked to one or more [vendor bills](../accounting/payments.html) with applied withholding taxes.

Nota

  * If no withholding tax is applied, then the XLS file will not generate records for those vendor bill lines.

  * When grouping payments for multiple bills, Odoo splits the payments based on the contact. From a payment, clicking Action ‣ Download BIR 2307 XLS generates a report that only includes vendor bills related to that contact.




Importante

Odoo cannot generate the BIR 2307 PDF report or DAT files directly. The generated `Form_2307.xls` file can be exported to an _external_ tool to convert it to BIR DAT or PDF format.

## SLSP Report¶

The **SLSP** report, also known as the _Summary List of Sales and Purchases_ , can be viewed and exported (in XLSX format). The report can be viewed from Reporting ‣ Partner Reports ‣ Summary List of Sales and Purchases.

The report is split into two sections, which can be accessed from their respective buttons at the top:

  * Sales for SLS report

All customer invoices with the associated sales taxes applied are shown in this report.

  * Purchases for SLP report

All vendor bills with the associated purchase taxes applied are shown in this report.




By default, both reports exclude journal entries containing partners without a TIN number set and those with importation taxes set. To view or hide them, the Options: button gives additional filters to include these, among others:

  * `Including Partners Without TIN`

  * `Including Importations`




Importante

Odoo cannot generate the DAT files directly. The Export SLSP and XLSX buttons export an XLSX file, which can be processed using an _external_ tool to convert to the DAT format.

## 2550Q Tax report¶

The tax report report is accessible by navigating to Reporting ‣ Statement Reports ‣ Tax Report ‣ 2550Q(PH). The form is based on the latest _2550Q (Quarterly Value-Added Tax Return)_ Jan. 2023 version.

Suggerimento

Most lines in the tax report are automatically computed based on the taxes. For more accurate reporting and filing of the tax report, manual journal entries can also be mapped to the tax report through preconfigured **Tax Grids** for each tax report line.

Importante

Odoo cannot generate the 2550Q BIR formatted PDF report directly. It should be used as a reference when externally filing the form manually or online.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/philippines.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](saudi_arabia.html "Arabia Saudita") |
  * [precedente](peru.html "Perù") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Filippine


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
  *[FBM]: Fulfilled By Merchant
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