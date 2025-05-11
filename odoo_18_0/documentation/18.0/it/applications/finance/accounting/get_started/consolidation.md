# Consolidamento — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](multi_currency.html "Sistema multi valuta") |
  * [precedente](chart_of_accounts.html "Piano dei conti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Consolidamento



# Consolidamento¶

Consolidation allows combining financial data from **multiple separate companies** , each with its own books, into a unified view, providing a «fair image» of the entire group’s financial health.

It helps create a clear, comprehensive view of the group’s financial performance by combining data from multiple companies.

## How it Works in Odoo¶

### Consolidation Tools¶

**Several tools** combined together will contribute to the construction of the financial consolidation:

  1. **Account Mapping:** Similar accounts from different companies can be mapped together. This allows Odoo to combine them correctly in consolidated reports. To map accounts, go to Accounting ‣ Configuration ‣ Chart of Accounts. Click View on the account line. In the Mapping tab, enter a code in the corresponding company Code column to map the account.

Nota

Import mapping or merge existing accounts using the merging tool can simplify the process.

  2. **Multi-Ledgers:** Ledgers are fundamental to the process of consolidation. They are either:

     * _Regular Ledgers:_ Each company in the consolidation scope has its own standard accounting ledger where all the regular day-to-day transactions are recorded. It excludes the company’s consolidation adjustment journals.

     * _Multi-Ledger for Consolidation:_ The company doing the actual consolidation also has a special multi-ledger. This one includes all the other companies” consolidation adjustments journals (the ones excluded from their own ledgers). This allows for viewing the total impact of all the adjustments.

To create a new ledger, go to Accounting ‣ Configuration ‣ Multi-Ledgers and hit the New button. Enter a name, pick the company the ledger is linked to and most importantly, determine which journals are to be excluded from the ledger.

  3. **Multi-Company Selector:** The consolidated view can be accessed using the multi-company
    

selector. Selecting the consolidating company as the current company and making the other companies visible in the selector, all the journal items are displayed from the consolidating company’s perspective.

  4. **Horizontal Groups:** Odoo’s reporting tools allow for combining multi-ledgers and using
    

horizontal groups to view the consolidated Balance Sheet or P&L. They also show how much each company contributes to the overall consolidated figures.

Follow these steps to create an Horizontal Group:

     * attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode).

     * Go to Accounting ‣ Configuration ‣ Horizontal Groups and click New.

     * Add a Group Name and select the Reports where the horizontal group can be used.

     * In the Field column, click Add a line.

     * In the Create rules window, add a Field and create a new Domain rule if needed. Then, click Save & Close.

Importante

When opened, financial reports usually default to a statutory view, using the company’s regular ledger (including its consolidation adjustment). To see the full consolidation picture, **make sure to select the multi-ledger** that includes all the consolidation adjustments.

  5. **Cumulative Translation Adjustments:** When consolidating companies with different currencies, Odoo handles the translation.

     * _Equity accounts:_ Use the historical exchange rate.

     * _Profit & Loss (P&L) accounts:_ Use the average exchange rate.

     * _Balance sheet accounts (excluding equity):_ Use the closing exchange rate.

Importante

The rates used are those of the company currently selected.




### Consolidating Companies vs. Branch Management¶

Consolidating companies involves **legally separate entities** whereas branches are **subdivisions** of a single legal entity which often share the head office’s resources (journals, taxes, accounts, fiscal positions) and are not consolidated in the same way.

## Account Merging¶

Accounts can be merged to reduce the number of accounts and standardize them across companies. This is optional; consolidation works without it.

To use the merge tool, select all the companies with an account that needs to be merged in the company selector in the top right corner of the screen.

Then, go to Accounting ‣ Configuration ‣ Chart of Accounts and select the accounts to merge. Click the __ Actions menu and select Merge accounts.

In the Merge accounts window, enable the Group by name? option if needed and click Merge.

The selected accounts are then merged into a single shared account, accessible by all the chosen companies, just as if the account had been directly created to be shared.

## Account Unmerging¶

Accounts can also be unmerged if needed.

Avvertimento

Note that unmerging accounts **will not unmerge the chatters** of the accounts. Once merged, the changes” histories are permanently merged.

To unmerge accounts, select a company with a shared account in the company selector at the top right corner of the screen. Then, go to Accounting ‣ Configuration ‣ Chart of Accounts and select the account to unmerge. Click the __ Actions menu and select Unmerge accounts.

An Odoo Warning confirmation pop-up window will appear, listing how the accounts will be split.

Click Unmerge. A new account linked to each company will be created for the previously shared account.

## Import a Mapping¶

To **import an account mapping** , select all the related companies in the company selector at the top right corner of the screen and go to Accounting ‣ Configuration ‣ Chart of Accounts.

First, to choose the fields to export, select the accounts, click the __ Actions button and select Export. Then, in the Export data window, add the Code mapping/Code, Code Mapping/Company and External ID fields using the __icon and click Export. No other field is required.

Second, rework it in a spreadsheet adding the desired code for each company on desired accounts.

Third, to reimport the file (xlsx or csv format) in Odoo, click Import and, in the Import Chart of Accounts section, click Import CoA. In the Accounting Import Guide, drop or click Upload Data File to import the file. Then, click Import.

Finally, the codes now take into account the mapping company per company.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/get_started/consolidation.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](multi_currency.html "Sistema multi valuta") |
  * [precedente](chart_of_accounts.html "Piano dei conti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Consolidamento


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
  *[SRI]: Servicio de Rentas Internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Fornitura Immediata di Informazioni
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