# Default barcode nomenclature — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gs1_nomenclature.html "GS1 barcode nomenclature") |
  * [precedente](transfers_scratch.html "Create and process transfers with barcodes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Default barcode nomenclature



# Default barcode nomenclature¶

_Barcode nomenclatures_ define how barcodes are recognized and categorized. When a barcode is scanned, it is associated to the **first** rule with a matching pattern. The pattern syntax is described in Odoo’s nomenclature list using a regular expression, and a barcode is successfully read by Odoo if its prefix and/or length matches the one defined in the barcode’s rule.

For instance, at a [Point of Sale](../../../sales/point_of_sale.html) station, product weight barcodes in the European Article Number (EAN) format, which begin with `21` and have five digits specifying the weight, are used to weigh products and generate a barcode depicting the weight and price. The `21` and five-digit weight is the barcode pattern used to identify the barcode and can be customized to ensure Odoo correctly interprets all barcodes for the business.

Nota

Barcodes are also commonly used with Odoo’s **Inventory** and **Barcode** apps.

Odoo **Barcode** supports EAN, Universal Product Code (UPC), and [GS1](gs1_nomenclature.html) formats. This document exclusively focuses on default rules and patterns in Odoo, which use UPC and EAN encoding.

Importante

To use UPC and EAN barcodes for uniquely identifying products across the entire supply chain, they **must** be [purchased from GS1](https://www.gs1.org/standards/get-barcodes).

In Odoo, custom barcode patterns can be defined to recognize barcodes specific to the company. Barcodes do not need to be purchased if used only within the company, such as in the example where the barcode is written in the EAN format.

## Configurazione¶

To use default nomenclature, navigate to Inventory app ‣ Configuration ‣ Settings. Under the Barcode section, tick the Barcode Scanner checkbox. Doing so installs the **Barcode** app in the database.

Next, in the Barcode Nomenclature field, ensure Default Nomenclature is selected. Then, click Save.

With the **Barcode** module installed, and the Default Nomenclature selected, the barcode actions using UPC and EAN, detailed in the default nomenclature list, are available for use. And, by default, Odoo automatically handles UPC/EAN conversion.

## Example: product weight barcode¶

To better understand how barcode nomenclature is used to identify products in Odoo, this example where product weight barcodes in EAN format are used to allow a [Point of Sale](../../../sales/point_of_sale.html) business to automatically print barcodes, and calculate the price using the weight of the item.

To set up barcodes for weighted products, the following rule is used:

Nome regola | Modello codice | Field in Odoo  
---|---|---  
Weighted Barcodes 3 Decimals | (21)….{NNDDD} | Barcode field on product form  
  
Example

To better understand the barcode pattern for weighted products, consider the barcode, `2112345000008`:

  * `21`: code that identifies this a barcode for weighted products.

  * `12345`: five digits (denoted by `.....` in the table above) that identify the product.

  * `00000`: five digits (denoted by `{NNDDD}` in the table) representing the weight of the product. On the product form, the five weight values **must** be `00000`. The first two digits are whole number values, and the last three digits are decimal values. For example, «13.5 grams» in the `{NNDDD}` format is `13500`.

  * `8`: [check digit](https://www.gs1.org/services/check-digit-calculator) for `211234500000`.




Together, these components make up a 13-character EAN \- 13 barcode.

To configure the product barcode for `Pasta Bolognese`, the EAN barcode for weighted products, `2112345000008`, is entered in the Barcode field on the product form (accessible by going to Inventory app ‣ Products ‣ Products, and selecting the desired product). In addition, the Unit of Measure is set to kg.

Next, a customer’s bowl of pasta is weighed to be `1.5` kilograms. This generates a new barcode for the pasta, according to the weight: `211234501500`, which has a check digit of `2`. The new barcode is `2112345015002`.

Ensure the products scan properly, by navigating to the Barcode app ‣ Operations. Next, click any operation type, such as Receipts. Then, click the New button to create a draft stock move. Scan the product weight barcode, such as `2112345015002`, and if the intended product appears, the barcode setup is correct.

## Create rules¶

Importante

Adding new rules is necessary for UPC and EAN formats that are **not** in Odoo’s default list, since barcodes cannot be read successfully if there are unknown fields.

> While new rules can be created, Odoo fields do **not** auto-populate with information from these rules. [Custom development](https://www.odoo.com/appointment/132) is required for this functionality.

To create a rule, first enable [developer mode](../../../general/developer_mode.html#developer-mode). Then, navigate to Inventory app ‣ Configuration ‣ Barcode Nomenclatures, and select Default Nomenclature.

On this page, configure the following optional fields:

  * UPC/EAN Conversion: determines if a UPC/EAN barcode should be automatically converted when matching a rule with another encoding. Options include Always (the default option), Never, EAN-13 to UPC-A, and UPC-A to EAN-13.

  * Is GS1 Nomenclature: ensure this checkbox is **not** ticked, as the Default Nomenclature uses UPC and EAN encoding, _not_ GS1 encoding.




On the Default Nomenclature page, click Add a line at the bottom of the table, which opens a Create Rules pop-up window to create a new rule.

The Rule Name field is used internally to identify what the barcode represents.

The Sequence field represents the priority of the rule; meaning the smaller the value, the higher the rule appears on the table.

The barcode Type field represents different classifications of information that can be understood by the system (e.g., Package, Lot, Location, Coupon, etc.).

The Encoding field specifies which encoding the barcode uses. This rule **only** applies if the barcode uses this specific encoding. The available Encoding options are: EAN-13, EAN-8, UPC-A, and GS1-28.

The Barcode Pattern field represents how the sequence of letters or numbers is recognized by the system to contain information about the product. Sometimes, when a certain amount of digits are required, the number of `.` is shown. `N` represents whole number digits, and `D` represent decimal digits.

Example

`1...` represents any 4-digit number that starts with 1. `NNDD` represents a two digit number with two decimal points. For example, `14.25` is 1425.

After filling in the information, click the Save & New button to save the rule, and instantly start creating another rule. Or, click Save & Close to save the rule, and return to the table of rules.

## Default nomenclature list¶

The table below contains Odoo’s list of Default Nomenclature rules. Barcode patterns are written in regular expressions.

Nome regola | Tipo | Codifica | Modello codice  
---|---|---|---  
Price Barcodes 2 Decimals | Prodotto valutato | EAN-13 | 23…..{NNNDD}  
Discount Barcodes | Prodotto scontato | Qualsiasi | 22{NN}  
Weight Barcodes 3 Decimals | Prodotto pesato | EAN-13 | 21…..{NNDDD}  
Customer Barcodes | Cliente | Qualsiasi | 042  
Coupon & Gift Card Barcodes | Buono sconto | Qualsiasi | 043|044  
Cashier Barcodes | Cassiere | Qualsiasi | 041  
Location barcodes | Luogo | Qualsiasi | 414  
Package barcodes | Collo | Qualsiasi | PACK  
Lot barcodes | Lotto | Qualsiasi | 10  
Magnetic Credit Card | Carta di credito | Qualsiasi | %.*  
Codici a barre per prodotti | Prodotto unitario | Qualsiasi | .*  
  
Nota

When the Barcode Pattern contains `.*`, it means it can contain any number or type of characters.

Vedi anche

[GS1 barcode nomenclature](gs1_nomenclature.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/barcode/operations/barcode_nomenclature.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gs1_nomenclature.html "GS1 barcode nomenclature") |
  * [precedente](transfers_scratch.html "Create and process transfers with barcodes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Default barcode nomenclature


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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