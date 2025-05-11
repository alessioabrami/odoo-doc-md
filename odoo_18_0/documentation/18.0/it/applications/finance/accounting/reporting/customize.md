# Custom reports — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](year_end.html "Year-end closing") |
  * [precedente](silverfin.html "Silverfin integration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Custom reports



# Custom reports¶

Odoo è dotato di un framework di reporting potente e facile da usare. Il motore consente di creare nuovi report, come **relazioni fiscali** , o **bilanci** e **dichiarazioni dei redditi** con **raggruppamenti** e **layout** specifici.

Importante

Attivare la modalità developer 1 per accedere all’interfaccia di creazione dei rapporti contabili.

Per creare un nuovo rapporto, andare su :menuselezione:`Contabilità --> Configurazione --> Gestione: Rapporti contabili`. Da qui è possibile creare un root report o un variant.

## Root reports¶

Root reports can be regarded as generic, neutral accounting reports. They serve as models on which local accounting versions are built. If a report has no root report, it is considered to be a root report itself.

Example

A tax report for Belgium and the US would both use the same generic version as a base and adapt it for their domestic regulations.

When creating a new root report, you need to create a **menu item** for it. To do so, open the report and then, on that same report, click on Action ‣ Create Menu Item. Refresh the page; the report is now available under Accounting ‣ Reporting.

Nota

Cases that require creating a new root report are rare, such as when a country’s tax authorities require a new and specific type of report.

## Varianti¶

Variants are country-specific versions of root reports and, therefore, always refer to a root report. To create a variant, select a generic (root) report in the Root Report field when creating a new report.

When a root report is opened from one of the accounting app’s main menus, all its variants are displayed in the variant selector in the top right corner of the view.

Example

In the following image, VAT Report (BE) is the variant of the root Generic Tax report.

## Righe¶

After having created a report (either root or variant), you need to fill it with lines. You can either create a new one by clicking on Add a line, or modify an existing line by clicking on it. All lines _require_ a Name, and can have an optional additional Code (of your choice) if you wish to use their value in formulas.

## Espressioni¶

Each line can contain one or multiple **expressions**. Expressions can be seen as **sub-variables** needed by a report line. To create an expression, click on Add a line _within_ a line report.

When creating an expression, you must attribute a label used to refer to that expression. Therefore, it has to be **unique** among the expressions of each line. Both a Computation Engine and a Formula must also be indicated. The **engine** defines how your **formula(s)** and **subformula(s)** are interpreted. It is possible to mix expressions using different computation engines under the same line if you need to.

Nota

Depending on the engine, subformulas may also be required.

### “Odoo Domain” engine¶

With this engine, a formula is interpreted as an [Odoo domain](../../../../developer/reference/backend/orm.html#reference-orm-domains) targeting `account.move.line` objects.

The subformula allows you to define how the move lines matching the domain are used to compute the value of the expression:

`sum`
    

The result is the sum of all the balances of the matched move lines.

`sum_if_pos`
    

The result is the sum of all the balances of the matched move lines if this amount is positive. Otherwise, it is `0`.

`sum_if_neg`
    

The result is the sum of all the balances of the matched move lines if this amount is negative. Otherwise, it is `0`.

`count_rows`
    

The result is the number of sub-lines of this expression. If the parent line has a group-by value, this will correspond to the number of distinct grouping keys in the matched move lines. Otherwise, it will be the number of matched move lines.

You can also put a `-` sign at the beginning of the subformula to **reverse** the sign of the result.

### “Tax Tags” engine¶

A formula made for this engine consists of a name used to match tax tags. If such tags do not exist when creating the expression, they will be created.

When evaluating the expression, the expression computation can roughly be expressed as: **(amount of the move lines with** `+` **tag)** `-` **(amount of the move lines with** `-` **tag)**.

Example

If the formula is `tag_name`, the engine matches tax tags `+tag_name` and `-tag_name`, creating them if necessary. To exemplify further: two tags are matched by the formula. If the formula is `A`, it will require (and create, if needed) tags `+A` and `-A`.

### “Aggregate Other Formulas” engine¶

Use this engine when you need to perform arithmetic operations on the amounts obtained for other expressions. Formulas here are composed of references to expressions separated by one of the four basic arithmetic operators (addition `+`, subtraction `-`, division `/`, and multiplication `*`). To refer to an expression, type in its parent line’s **code** followed by a period `.` and the expression’s **label** (ex. **code.label**).

**Subformulas** can be one of the following:

`if_above(CUR(amount))`
    

The value of the arithmetic expression will be returned only if it is greater than the provided bound. Otherwise, the result will be `0`.

`if_below(CUR(amount))`
    

The value of the arithmetic expression will be returned only if it is lower than the provided bound. Otherwise, the result will be `0`.

`if_between(CUR1(amount1), CUR2(amount2))`
    

The value of the arithmetic expression will be returned only if it is strictly between the provided bounds. Otherwise, it will be brought back to the closest bound.

`if_other_expr_above(LINE_CODE.EXPRESSION_LABEL, CUR(amount))`
    

The value of the arithmetic expression will be returned only if the value of the expression denoted by the provided line code and expression label is greater than the provided bound. Otherwise, the result will be `0`.

`if_other_expr_below(LINE_CODE.EXPRESSION_LABEL, CUR(amount))`
    

The value of the arithmetic expression will be returned only if the value of the expression denoted by the provided line code and expression label is lower than the provided bound. Otherwise, the result will be `0`.

`CUR` is the currency code in capital letters, and `amount` is the amount of the bound expressed in that currency.

You can also use the `cross_report` subformula to match an expression found in another report.

### “Prefix of Account Codes” engine¶

This engine is used to match amounts made on accounts using the prefixes of these accounts” codes as variables in an arithmetic expression.

Example

`21`

Arithmetic expressions can also be a single prefix, such as here.

Example

`21 + 10 - 5`

This formula adds the balances of the move lines made on accounts whose codes start with `21` and `10`, and subtracts the balance of the ones on accounts with the prefix `5`.

It is also possible to ignore a selection of sub-prefixes.

Example

`21 + 10\(101, 102) - 5\(57)`

This formula works the same way as the previous example but ignores the prefixes `101`, `102`, and `57`.

You can apply “sub-filtering” on **credits and debits** using the `C` and `D` suffixes. In this case, an account will only be considered if its prefix matches, _and_ if the total balance of the move lines made on this account is **credit/debit**.

Example

Account `210001` has a balance of -42 and account `210002` has a balance of 25. The formula `21D` only matches the account `210002`, and hence returns 25. `210001` is not matched, as its balance is _credit_.

Prefix exclusions can be mixed with the `C` and `D` suffixes.

Example

`21D + 10\(101, 102)C - 5\(57)`

This formula adds the balances of the move lines made on accounts whose code starts with `21` _if_ it is debit (`D`) and `10` _if_ it is credit (`C`), but ignores prefixes `101`, `102`, and subtracts the balance of the ones on accounts with the prefix `5`, ignoring the prefix `57`.

To match the letter `C` or `D` in a prefix and not use it as a suffix, use an empty exclusion `()`.

Example

`21D\()`

This formula matches accounts whose code starts with `21D`, regardless of their balance sign.

In addition to using code prefixes to include accounts, you can also match them with **account tags**. This is especially useful, for example, if your country lacks a standardized chart of accounts, where the same prefix might be used for different purposes across companies.

Example

`tag(25)`

This formula matches accounts whose associated tags contain the one with id _25_.

If the tag you reference is defined in a data file, an xmlid can be used instead of the id.

Example

`tag(my_module.my_tag)`

This formula matches accounts whose associated tags include the tag denoted by _my_module.my_tag_.

You can also use arithmetic expressions with tags, possibly combining them with prefix selections.

Example

`tag(my_module.my_tag) + tag(42) + 10`

The balances of accounts tagged as _my_module.my_tag_ will be summed with those of accounts linked to the tag with ID _42_ and accounts with the code prefix `10`

`C` and `D` suffixes can be used in the same way with tags.

Example

`tag(my_module.my_tag)C`

This formula matches accounts with the tag _my_module.my_tag_ and a credit balance.

Prefix exclusion also works with tags.

Example

`tag(my_module.my_tag)\(10)`

This formula matches accounts with the tag _my_module.my_tag_ and a code not starting with `10`.

### “External Value” engine¶

The “external value” engine is used to refer to **manual** and **carryover values**. Those values are not stored using `account.move.line`, but with `account.report.external.value`. Each of these objects directly points to the expression it impacts, so very little needs to be done about their selection here.

**Formulas** can be one of the following:

`sum`
    

If the result must be the sum of all the external values in the period.

`most_recent`
    

If the result must be the value of the latest external value in the period.

In addition, **subformulas** can be used in two ways:

`rounding=X`
    

Replacing `X` with a number instructs to round the amount to X decimals.

`editable`
    

Indicates this expression can be edited manually, triggering the display of an icon in the report, allowing the user to perform this action.

Nota

Manual values are created at the `date_to` currently selected in the report.

Both subformulas can be mixed by separating them with a `;`.

Example

`editable;rounding=2`

is a correct subformula mixing both behaviors.

### “Custom Python Function” engine¶

This engine is a means for developers to introduce custom computation of expressions on a case-by-case basis. The formula is the name of a **python function** to call, and the subformula is a **key** to fetch in the **dictionary** returned by this function. Use it only if you are making a custom module of your own.

## Colonne¶

Reports can have an **indefinite number** of columns to display. Each column gets its values from the **expressions** declared on the **lines**. The field expression_label of the column gives the label of the expressions whose value is displayed. If a line has no **expression** in that field, then nothing is displayed for it in this column. If multiple columns are required, you must use different **expression** labels.

When using the **period comparison** feature found under the Options tab of an accounting report, all columns are repeated in and for each period.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/reporting/customize.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](year_end.html "Year-end closing") |
  * [precedente](silverfin.html "Silverfin integration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Custom reports


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