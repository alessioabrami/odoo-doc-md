# Non-current assets and fixed assets — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deferred_expenses.html "Deferred expenses") |
  * [precedente](invoice_digitization.html "AI-powered document digitization") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Non-current assets and fixed assets



# Non-current assets and fixed assets¶

**Non-current Assets** , also known as **long-term assets** , are investments that are expected to be realized after one year. They are capitalized rather than being expensed and appear on the company’s balance sheet. Depending on their nature, they may undergo **depreciation**.

**Fixed Assets** are a type of Non-current Assets and include the properties bought for their productive aspects, such as buildings, vehicles, equipment, land, and software.

For example, let’s say we buy a car for $ 27,000. We plan to amortize it over five years, and we will sell it for $ 7,000 afterward. Using the linear, or straight-line, depreciation method, $ 4,000 are expensed each year as **depreciation expenses**. After five years, the **Accumulated Depreciation** amount reported on the balance sheet equals $ 20,000, leaving us with $ 7,000 of **Not Depreciable Value** , or Salvage value.

Odoo Accounting handles depreciation by creating all depreciation entries automatically in _draft mode_. They are then posted periodically.

Odoo supports the following **Depreciation Methods** :

  * Linea retta

  * Decrescente

  * Declining Then Straight Line




Nota

The server checks once a day if an entry must be posted. It might then take up to 24 hours before you see a change from _draft_ to _posted_.

## Prerequisiti¶

Such transactions must be posted on an **Assets Account** rather than on the default expense account.

### Configure an Assets Account¶

To configure your account in the **Chart of Accounts** , go to Accounting ‣ Configuration ‣ Chart of Accounts, click on _Create_ , and fill out the form.

Nota

This account’s type must be either _Fixed Assets_ or _Non-current Assets_.

### Post an expense to the right account¶

#### Select the account on a draft bill¶

On a draft bill, select the right account for all the assets you are buying.

#### Choose a different Expense Account for specific products¶

Start editing the product, go to the _Accounting_ tab, select the right **Expense Account** , and save.

Suggerimento

It is possible to automate the creation of assets entries for these products.

#### Change the account of a posted journal item¶

To do so, open your Purchases Journal by going to Accounting ‣ Accounting ‣ Purchases, select the journal item you want to modify, click on the account, and select the right one.

## Assets entries¶

### Crea nuova voce¶

An **Asset entry** automatically generates all journal entries in _draft mode_. They are then posted one by one at the right time.

To create a new entry, go to Accounting ‣ Accounting ‣ Assets, click on _Create_ , and fill out the form.

Click on **select related purchases** to link an existing journal item to this new entry. Some fields are then automatically filled out, and the journal item is now listed under the **Related Purchase** tab.

Once done, you can click on _Compute Depreciation_ (next to the _Confirm_ button) to generate all the values of the **Depreciation Board**. This board shows you all the entries that Odoo will post to depreciate your asset, and at which date.

#### What does «Prorata Temporis» mean?¶

The **Prorata Temporis** feature is useful to depreciate your assets the most accurately possible.

With this feature, the first entry on the Depreciation Board is computed based on the time left between the _Prorata Date_ and the _First Depreciation Date_ rather than the default amount of time between depreciations.

For example, the Depreciation Board above has its first depreciation with an amount of $ 241.10 rather than $ 4,000.00. Consequently, the last entry is also lower and has an amount of $ 3758.90.

#### What are the different Depreciation Methods¶

The **Straight Line Depreciation Method** divides the initial Depreciable Value by the number of depreciations planned. All depreciation entries have the same amount.

The **Declining Depreciation Method** multiplies the Depreciable Value by the **Declining Factor** for each entry. Each depreciation entry has a lower amount than the previous entry. The last depreciation entry doesn’t use the declining factor but instead has an amount corresponding to the balance of the depreciable value so that it reaches $0 by the end of the specified duration.

The **Declining Then Straight Line Depreciation Method** uses the Declining Method, but with a minimum Depreciation equal to the Straight Line Method. This method ensures a fast depreciation at the beginning, followed by a constant one afterward.

### Assets from the Purchases Journal¶

You can create an asset entry from a specific journal item in your **Purchases Journal**.

To do so, open your Purchases Journal by going to Accounting ‣ Accounting ‣ Purchases, and select the journal item you want to record as an asset. Make sure that it is posted in the right account (see: Change the account of a posted journal item).

Then, click on _Action_ , select **Create Asset** , and fill out the form the same way you would do to create a new entry.

## Modification of an Asset¶

You can modify the values of an asset to increase or decrease its value.

To do so, open the asset you want to modify, and click on _Modify Depreciation_. Then, fill out the form with the new depreciation values and click on _Modify_.

A **decrease in value** posts a new Journal Entry for the **Value Decrease** and modifies all the future _unposted_ Journal Entries listed in the Depreciation Board.

An **increase in value** requires you to fill out additional fields related to the account movements and creates a new Asset entry with the **Value Increase**. The Gross Increase Asset Entry can be accessed with a Smart Button.

## Disposal of Fixed Assets¶

To **sell** an asset or **dispose** of it implies that it must be removed from the Balance Sheet.

To do so, open the asset you want to dispose of, click on _Sell or Dispose_ , and fill out the form.

Odoo Accounting then generates all the journal entries necessary to dispose of the asset, including the gain or loss on sale, which is based on the difference between the asset’s book value at the time of the sale and the amount it is sold for.

Nota

To record the sale of an asset, you must first post the related Customer Invoice so you can link the sale of the asset with it.

## Assets Models¶

You can create **Assets Models** to create your Asset entries faster. It is particularly useful if you recurrently buy the same kind of assets.

To create a model, go to Accounting ‣ Configuration ‣ Assets Models, click on _Create_ , and fill out the form the same way you would do to create a new entry.

Suggerimento

You can also convert a _confirmed Asset entry_ into a model by opening it from Accounting ‣ Accounting ‣ Assets and then, by clicking on the button _Save Model_.

### Apply an Asset Model to a new entry¶

When you create a new Asset entry, fill out the **Fixed Asset Account** with the right asset account.

New buttons with all the models linked to that account appear at the top of the form. Clicking on a model button fills out the form according to that model.

## Automate the Assets¶

When you create or edit an account of which the type is either _Non-current Assets_ or _Fixed Assets_ , you can configure it to create assets for the expenses that are credited on it automatically.

You have three choices for the **Automate Assets** field:

  1. **No:** this is the default value. Nothing happens.

  2. **Create in draft:** whenever a transaction is posted on the account, a draft _Assets entry_ is created, but not validated. You must first fill out the form in Accounting ‣ Accounting ‣ Assets.

  3. **Create and validate:** you must also select an Asset Model (see: Assets Models). Whenever a transaction is posted on the account, an _Assets entry_ is created and immediately validated.




Suggerimento

You can, for example, select this account as the default **Expense Account** of a product to fully automate its purchase. (see: Choose a different Expense Account for specific products).

Vedi anche

  * [Piano dei conti](../get_started/chart_of_accounts.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/vendor_bills/assets.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deferred_expenses.html "Deferred expenses") |
  * [precedente](invoice_digitization.html "AI-powered document digitization") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Non-current assets and fixed assets


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
  *[AVCO]: Average Cost Valuation
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