# GS1 barcode nomenclature — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gs1_usage.html "GS1 barcode usage") |
  * [precedente](barcode_nomenclature.html "Default barcode nomenclature") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * GS1 barcode nomenclature



# GS1 barcode nomenclature¶

[GS1 nomenclature](https://www.gs1us.org/) consolidates various product and supply chain data into a single barcode. Odoo takes in [unique Global Trade Item Numbers](https://www.gs1.org/standards/get-barcodes) (GTIN), purchased by businesses, to enable global shipping, sales, and eCommerce product listing.

Configure GS1 nomenclature to scan barcodes of sealed boxes and identify essential product information, such as GTIN, lot number, quantity information, and more.

Importante

GTINs are unique product identification that **must** be [purchased from GS1](https://www.gs1.org/standards/get-barcodes) to use GS1 barcodes.

Vedi anche

  * [All GS1 barcodes](https://www.gs1.org/standards/barcodes/application-identifiers)

  * Odoo’s default GS1 rules

  * Why’s my barcode not working?




## Set up barcode nomenclature¶

To use GS1 nomenclature, navigate to the Inventory app ‣ Configuration ‣ Settings. Then under the Barcode section, check the Barcode Scanner box. Next, select Barcode Nomenclature ‣ Default GS1 Nomenclature from the default barcode nomenclature options.

The list of GS1 _rules_ and _barcode patterns_ Odoo supports by default is accessible by clicking the ➡️ (arrow) icon to the right of the Barcode Nomenclature selection.

In the Open: Nomenclature pop-up table, view and edit the GS1 Rule Names available in Odoo. The table contains all the information that can be condensed with a GS1 barcode, along with the corresponding Barcode Pattern.

Suggerimento

After setting GS1 as the barcode nomenclature, the Barcode Nomenclatures settings can also be accessed by a hidden menu that’s discoverable after enabling [developer mode](../../../general/developer_mode.html#developer-mode). Once enabled, navigate to the Inventory app ‣ Configuration ‣ Barcode Nomenclatures menu and finally, select Default GS1 Nomenclature.

## Use GS1 barcodes in Odoo¶

For product identification using GS1 barcodes in Odoo, businesses obtain a [unique GTIN](https://www.gs1.org/standards/get-barcodes) as an internationally distinct product identifier purchased from GS1. This GTIN is combined with specific product details following GS1’s designated _barcode pattern_. The barcode pattern’s arrangement of numbers and letters must adhere to GS1 conventions for accurate interpretation by global systems along the supply chain.

Every barcode starts with a 2-4 digit [application identifier](https://www.gs1.org/standards/barcodes/application-identifiers) (A.I.). This required prefix universally indicates what kind of information the barcode contains. Odoo follows GS1 rules for identifying information, as detailed in the default GS1 rules list. Including the relevant A.I. from the list enables Odoo to correctly interpret GS1 barcodes. While most barcode patterns have a fixed length requirement, certain ones, such as lots and serial numbers, have flexible length.

Suggerimento

For flexible-length barcode patterns not placed at the end of the GS1 barcode, use the FNC1 separator (`\x1D`) to end the barcode.

Example: The barcode pattern for lot numbers is 20 characters long. Instead of creating a 20-character lot number barcode, like `LOT00000000000000001`, use the FNC1 separator to make it shorter: `LOT001x1D`.

Refer to the GS1 nomenclature list to see a comprehensive list of all barcode patterns and rules to follow. Otherwise, refer to [this GS1 usage doc](gs1_usage.html#barcode-operations-gs1-usage) for specific examples of combining GTIN to product information and configuring the workflow.

Vedi anche

  * [Lots workflow](gs1_usage.html#barcode-operations-gs1-lots)

  * [Non-unit quantities workflow](gs1_usage.html#barcode-operations-quantity-ex)




### Create rules¶

GS1 rules are a specific format of information contained in the barcode, beginning with an A.I. and containing a defined length of characters. Scanning GS1 barcodes from the default GS1 list auto-fills corresponding data in the Odoo database.

Adding GS1 barcode rules in Odoo ensures accurate interpretation of unique, non-standard GS1 formats.

To do so, begin by turning on [developer mode](../../../general/developer_mode.html#developer-mode) and navigating to the Barcode Nomenclatures list in Inventory app ‣ Configuration ‣ Barcode Nomenclatures. Then, select the Default GS1 Nomenclature list item.

On the Default GS1 Nomenclature page, select Add a line at the bottom of the table, which opens a window to create a new rule. The Rule Name field is used internally to identify what the barcode represents. The barcode Types are different classifications of information that can be understood by the system (e.g. product, quantity, best before date, package, coupon). The Sequence represents the priority of the rule; this means the smaller the value, the higher the rule appears on the table. Odoo follows the sequential order of this table and will use the first rule it matches based on the sequence. The Barcode Pattern is how the sequence of letters or numbers is recognized by the system to contain information about the product.

After filling in the information, click the Save & New button to make another rule or click Save & Close to save and return to the table of rules.

## Barcode troubleshooting¶

Since GS1 barcodes are challenging to work with, here are some checks to try when the barcodes are not working as expected:

  1. Ensure that the Barcode Nomenclature setting is set as Default GS1 Nomenclature. Jump to the nomenclature setup section for more details.

  2. Ensure that the fields scanned in the barcode are enabled in Odoo. For example, to scan a barcode containing lots and serial numbers, make sure the Lots & Serial Numbers feature is enabled in [Odoo’s settings](gs1_usage.html#barcode-operations-lot-setup) and [on the product](gs1_usage.html#barcode-operations-lot-setup-on-product).

  3. Omit punctuation such as parentheses `()` or brackets `[]` between the A.I. and the barcode sequence. These are typically used in examples for ease of reading and should **not** be included in the final barcode. For more details on building GS1 barcodes, go to this section.

  4. When a single barcode contains multiple encoded fields, Odoo requires all rules to be listed in the barcode nomenclature for Odoo to read the barcode. This section details how to add new rules in the barcode nomenclature.

  5. Test barcodes containing multiple encoded fields, piece by piece, to figure out which field is causing the issue.

Example

When testing a barcode containing the GTIN, lot number, and quantity, start by scanning the GTIN alone. Then, test the GTIN with the lot number, and finally, try scanning the whole barcode.

  6. After diagnosing the encoded field is unknown, add new rules to Odoo’s default list to recognize GS1 barcodes with unique specifications.

Importante

While the new field will be read, the information won’t link to an existing field in Odoo without developer customizations. However, adding new rules is necessary to ensure the rest of the fields in the barcode are interpreted correctly.




## GS1 nomenclature list¶

The table below contains Odoo’s default list of GS1 rules. Barcode patterns are written in regular expressions. Only the first three rules require a [check digit](https://www.gs1.org/services/check-digit-calculator) as the final character.

Nome regola | Tipo | Modello codice | Tipo di contenuto GS1 | Odoo field  
---|---|---|---|---  
Serial Shipping Container Code | Collo | (00)(\d{18}) | Numeric identifier | Package name  
Global Trade Item Number (GTIN) | Prodotto unitario | (01)(\d{14}) | Numeric identifier | Barcode field on product form  
GTIN of contained trade items | Prodotto unitario | (02)(\d{14}) | Numeric identifier | Imballaggio  
Ship to / Deliver to global location | Ubicazione di destinazione | (410)(\d{13}) | Numeric identifier | Ubicazione di destinazione  
Ship / Deliver for forward | Ubicazione di destinazione | (413)(\d{13}) | Numeric identifier | Ubicazione di origine  
I.D. of a physical location | Luogo | (414)(\d{13}) | Numeric identifier | Luogo  
Batch or lot number | Lotto | (10) ([!»%-/0-9:-?A-Z_a-z]{0,20}) | Alpha-numeric name | Lotto  
Numero di serie | Lotto | (21) ([!»%-/0-9:-?A-Z_a-z]{0,20}) | Alpha-numeric name | Numero di serie  
Packaging date (YYMMDD) | Data di confezionamento | (13)(\d{6}) | Data | Pack date  
Best before date (YYMMDD) | Data di preferibile consumo | (15)(\d{6}) | Data | Best before date  
Expiration date (YYMMDD) | Data di scadenza | (17)(\d{6}) | Data | Expiry date  
Variable count of items | Quantità | (30)(\d{0,8}) | Misura | UoM: Units  
Count of trade items | Quantità | (37)(\d{0,8}) | Misura | Qty in units for containers (AI 02)  
Net weight: kilograms (kg) | Quantità | (310[0-5])(\d{6}) | Misura | Qty in kg  
Length in meters (m) | Quantità | (311[0-5])(\d{6}) | Misura | Qty in m  
Net volume: liters (L) | Quantità | (315[0-5])(\d{6}) | Misura | Qty in L  
Net volume: cubic meters (m3) | Quantità | (316[0-5])(\d{6}) | Misura | Qty in m3  
Length in inches (in) | Quantità | (321[0-5])(\d{6}) | Misura | Qty in inches  
Net weight/volume: ounces (oz) | Quantità | (357[0-5])(\d{6}) | Misura | Qty in oz  
Net volume: cubic feet (ft3) | Quantità | (365[0-5])(\d{6}) | Misura | Qty in ft3  
Packaging type | Tipo di imballaggio | (91) ([!»%-/0-9:-?A-Z_a-z]{0,90}) | Alpha-numeric name | Tipologia collo  
  
[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/barcode/operations/gs1_nomenclature.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gs1_usage.html "GS1 barcode usage") |
  * [precedente](barcode_nomenclature.html "Default barcode nomenclature") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * GS1 barcode nomenclature


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CIS]: Construction Industry Scheme
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
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time