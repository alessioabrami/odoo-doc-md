# Filippine — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](romania.html "Romania") |
  * [precedente](peru.html "Perù") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Filippine



# Filippine¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the 🇵🇭 Philippines [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) to get all the default accounting features of the Philippine localization, such as a chart of accounts, taxes, and reports. These provide a base template to get started with using Philippine accounting.

Nota

  * When creating a new database and selecting the `Philippines` as a country, the fiscal localization module **Philippines - Accounting** is automatically installed.

  * If the module is installed in an existing company, the **chart of accounts** and **taxes** will _not_ be replaced if there are already posted journal entries.




### Chart of accounts and taxes¶

A minimum configuration default chart of accounts is installed, and the following types of taxes are installed and linked to the relevant account:

  * Sales and Purchase VAT 12%

  * Sales and Purchase VAT Exempt

  * Sales and Purchase VAT Zero-Rated

  * Sales and Purchase Withholding




For the withholding taxes (Accounting ‣ Configuration ‣ Taxes), there is an additional Philippines ATC field under the Philippines tab.

Nota

Taxes” ATC codes are used for the BIR 2307, SAWT and QAP reports. If a tax is created manually, its ATC code must be added.

### Contatti¶

When a company or an individual (not belonging to a company) contact is located in the Philippines, fill in the Tax ID field with their `Taxpayer Identification Number (TIN)`.

For individuals not belonging to a company, identify them by using the following additional fields:

  * First Name

  * Middle Name

  * Last Name




Nota

For both Company and Individual, the TIN should follow the `NNN-NNN-NNN-NNNNN` format. The branch code should follow the last digits of the TIN, or else it can be left as `00000`.

## Report¶

### BIR 2307 report¶

**BIR 2307** reports, also known as [Certificate of Creditable Tax Withheld at Source](https://www.bir.gov.ph/bir-forms?tab=Certificates&idTag=BIR2307&datasetCode=3381&label=2307&type=TAB%20LINK), can be generated for purchase orders and vendor payments with the applicable withholding taxes.

To generate a BIR 2307 report, select one or multiple vendor bills from the list view, and click Action ‣ Download BIR 2307 XLS.

Suggerimento

The same action can be performed on a vendor bill from the form view.

In the pop-up that opens, review the selection and click Generate.

This generates the `Form_2307.xls` file that lists all the vendor bill lines with the applicable withholding tax.

The process above can also be used for a _single_ vendor [payment](../accounting/payments.html) if it is linked to one or more [vendor bills](../accounting/payments.html) with applied withholding taxes.

Nota

  * If no withholding tax is applied, then the XLS file will not generate records for those vendor bill lines.

  * When grouping payments for multiple bills, Odoo splits the payments based on the contact. From a payment, clicking Action ‣ Download BIR 2307 XLS generates a report that only includes vendor bills related to that contact.




Importante

Odoo cannot generate the BIR 2307 PDF report or DAT files directly. The generated `Form_2307.xls` file can be exported to an _external_ tool to convert it to BIR DAT or PDF format.

### SLSP report¶

To access the SLSP report, go to Accounting ‣ Reporting ‣ Summary List of Sales and Purchases.

Click the buttons at the top to display the desired report:

  * Sales for the SLS report.

All customer invoices with the associated sales taxes applied are shown in this report.

  * Purchases for the SLP report.

All vendor bills with the associated purchase taxes applied are shown in this report.




By default, both reports exclude journal entries containing partners without a TIN number set and those with importation taxes set. To view or hide them, click Options: and select the required filter:

  * Including Partners Without TIN

  * Including Importations




To export the SLSP report, click Export SLSP.

Importante

Odoo cannot generate the DAT files directly. The Export SLSP and XLSX buttons are used to export an XLSX file, which can be processed using an _external_ tool to convert it to the DAT format.

### 2550Q tax report¶

The tax report report is accessible by navigating to Accounting ‣ Reporting ‣ Statement Reports ‣ Tax Report ‣ 2550Q(PH). The form is based on the latest _2550Q (Quarterly Value-Added Tax Return)_ Jan. 2023 version.

Suggerimento

Most lines in the tax report are automatically computed based on the taxes. For more accurate reporting and filing of the tax report, manual journal entries can also be mapped to the tax report through preconfigured **Tax Grids** for each tax report line.

Importante

Odoo cannot generate the 2550Q BIR formatted PDF report directly. It should be used as a reference when externally filing the form manually or online.

### QAP & SAWT reports¶

To access the QAP and SAWT reports, go to Accounting ‣ Reporting ‣ Tax Return, click the __ Report: button, and select SAWT & QAP (PH).

Click the buttons at the top to display the desired report:

  * SAWT for the SAWT report.

All customer invoices with the associated sales witholding taxes applied are shown in this report.

  * QAP for the QAP report.

All vendor bills with the associated purchase witholding taxes applied are shown in this report.




To export the SAWT and QAP reports in XLSX format, click Export SAWT & QAP.

Importante

Odoo cannot generate the DAT files directly. The Export SAWT & QAP and XLSX buttons are used to export an XLSX file, which can be processed using an _external_ tool to convert it to the DAT format.

## Check printing¶

The Philippine check print layout follows the latest PCHC standardized format. To enable check printing, go to Accounting ‣ Configuration ‣ Settings, enable Checks and set the Check Layout to `Print Check - PH`.

Checks are printed using the [standard workflow](../accounting/payments/pay_checks.html).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/philippines.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](romania.html "Romania") |
  * [precedente](peru.html "Perù") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
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
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation