# Automatic inventory valuation — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](using_inventory_valuation.html "Using inventory valuation") |
  * [precedente](../inventory_valuation.html "Valutazione dell’inventario") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Automatic inventory valuation



# Automatic inventory valuation¶

All of a company’s stock on-hand contributes to the valuation of its inventory. That value should be reflected in the company’s accounting records to accurately show the value of the company and all of its assets.

By default, Odoo uses a periodic inventory valuation (also known as manual inventory valuation). This method implies that the accounting team manually posts journal entries, based on the physical inventory of the company, and warehouse employees take the time to count the stock. In Odoo, each product category reflects this, with the Costing Method set to Standard Price, and the Inventory Valuation (not visible by default) set to Manual.

Alternatively, perpetual (automatic) inventory valuation creates real-time _journal entries_ in the _Accounting_ app whenever stock enters or leaves the company’s warehouse.

This document is focused on the proper setup of automatic inventory valuation, which is an integrated valuation method that ensures journal entries in the _Accounting_ app match stock valuation updates in the _Inventory_ app. For an introduction of inventory valuation in Odoo, refer to the [Using inventory valuation](using_inventory_valuation.html) documentation.

Avvertimento

Switching from manual to automatic inventory valuation may cause discrepancies between stock valuation and accounting journals.

One [successful strategy](https://www.odoo.com/r/Kvfg) for switching to automated valuation:

  1. Clear existing stock (possibly with an [inventory adjustment](../../warehouses_storage/inventory_management/count_products.html))

  2. Change the inventory valuation method to _Automatic_

  3. Return the existing stock, with the original monetary value (using an inventory adjustment)




Once the existing stock is recovered, the Odoo _Accounting_ app automatically generates the journal entries to corresponding stock valuation records.

## Configurazione¶

To properly set up automatic inventory valuation, follow these steps in Odoo:

  1. Install Accounting app and enable specific settings

  2. Set Automatic inventory valuation on product categories

  3. Set costing method




### Accounting setup¶

To use automatic inventory valuation, install the _Accounting_ app. Next, go to Accounting app ‣ Configuration ‣ Settings, and in the Stock Valuation section, tick the Automatic Accounting checkbox. Then, click Save.

Nota

Enabling Automatic Accounting shows the previously invisible _Inventory Valuation_ field on a product category.

Refer to the Expense and Stock input/output sections of documentation for details on configuring the accounting journals shown.

### Product category setup¶

After enabling inventory valuation, the next step is to set the product category to use automatic inventory valuation.

Go to Inventory app ‣ Configuration ‣ Product Categories, and select the desired product category. In the Inventory Valuation section, set the Inventory Valuation field to Automated. Repeat this step for every product category intending to use automatic inventory valuation.

Nota

After enabling automatic accounting, each new stock move layer (SVL), that is created during inventory valuation updates, generates a journal entry.

## Costing method¶

After enabling inventory valuation, the _costing method_ for calculating and recording inventory costs is defined on the product category in Odoo.

Go to Inventory app ‣ Configuration ‣ Product Categories and select the desired product category. In the Inventory Valuation section, select the appropriate Costing Method:

Standard PriceAverage Cost (AVCO)First In First Out (FIFO)

The default costing method in Odoo. The cost of the product is manually defined on the product form, and this cost is used to compute the valuation. Even if the purchase price on a purchase order differs, the valuation is the cost defined on the product form.

Operazione | Costo unitario | Qtà disponibile | Valore in ingresso | Valore di magazzino  
---|---|---|---|---  
| 10 $ | 0 |  | 0 $  
Receive 8 products for $10/unit | 10 $ | 8 | 8*10$ | 80 €  
Receive 4 products for $16/unit | 10 $ | 12 | 4*16$ | $120  
Deliver 10 products | 10 $ | 2 | -10*12 $ | 20 €  
Receive 2 products for $9/unit | 10 $ | 4 | 2 * $10 | $40  
  
Calculates the valuation of a product based on the average cost of that product, divided by the total number of available stock on-hand. With this costing method, inventory valuation is _dynamic_ , and constantly adjusts based on the purchase price of products.

Operazione | Costo unitario | Qtà disponibile | Valore in ingresso | Valore di magazzino  
---|---|---|---|---  
| 0 $ | 0 |  | 0 $  
Receive 8 products for $10/unit | 10 $ | 8 | 8*10$ | 80 €  
Receive 4 products for $16/unit | 12$ | 12 | 4*16$ | 144$  
Deliver 10 products | 12$ | 2 | -10*12 $ | 24 $  
Receive 2 products for $6/unit | $9 | 4 | 2 * $6 | $36  
  
How are unit cost and inventory value calculated at each step?

  * When receiving four products for $16 each:

    * Inventory value is calculated by adding the previous inventory value with the incoming value: \\($80 + (4 * $16) = $144\\).

    * Unit cost is calculated by dividing the inventory value by the quantity on-hand: \\($144 / 12 = $12\\).

  * When delivering ten products, the average unit cost is used to calculate the inventory value, regardless of the purchase price of the product. Therefore, inventory value is \\($144 + (-10 * $12) = $24\\).

  * Receive two products for $6 each:

    * Inventory value: \\($24 + (2 * $6) = $36\\)

    * Unit cost: \\($36 / 4 = $9\\)




Nota

When choosing Average Cost (AVCO) as the Costing Method, changing the numerical value in the _Cost_ field for products in the respective product category creates a new record in the _Inventory Valuation_ report to adjust the value of the product. The _Cost_ amount is then automatically updated, based on the average purchase price of both the inventory on-hand and the costs accumulated from validated purchase orders.

Tracks the costs of incoming and outgoing items in real-time, and uses the real price of the products to change the valuation. The oldest purchase price is used as the cost for the next good sold, until an entire lot of that product is sold. When the next inventory lot moves up in the queue, an updated product cost is used based on the valuation of that specific lot.

This method is arguably the most accurate inventory valuation method for a variety of reasons, but it is highly sensitive to input data and human error.

Operazione | Costo unitario | Qtà disponibile | Valore in ingresso | Valore di magazzino  
---|---|---|---|---  
| 0 $ | 0 |  | 0 $  
Receive 8 products for $10/unit | 10 $ | 8 | 8*10$ | 80 €  
Receive 4 products for $16/unit | 12$ | 12 | 4*16$ | 144$  
Deliver 10 products | $16 | 2 |  -8 * $10 -2 * $16 | $32  
Receive 2 products for $6/unit | $11 | 4 | 2 * $6 | $44  
  
How are unit cost and inventory value calculated at each step?

  * When receiving four products for $16 each:

    * Inventory value is calculated by adding the previous inventory value to the incoming value: \\($80 + (4 * $16) = $144\\).

    * Unit cost is calculated by dividing the inventory value by the quantity on-hand: \\($144 / 12 = $12\\).

>     * When delivering ten products, eight units were purchased for $10, and two units were purchased for $16.

    * First, the incoming value is calculated by multiplying the on-hand quantity by the purchased price: \\((-8 * $10) + (-2 * $16) = -112\\).

    * The inventory value is calculated by subtracting the incoming value from the previous inventory value: \\($144 - $112 = $32\\).

    * Unit cost is calculated by dividing the inventory value by the remaining quantity: \\($32 / 2 = $16\\).

  * When receiving two products for $6, inventory value is \\($32 + $12 = $44\\). Unit cost is \\($44 / 4 = $11\\).




Avvertimento

Changing the costing method greatly impacts inventory valuation. It is highly recommended to consult an accountant first before making any adjustments here.

Vedi anche

[Using inventory valuation](using_inventory_valuation.html)

When the Costing Method is changed, products already in stock that were using the Standard costing method **do not** change value; rather, the existing units keep their value, and any product moves from then on affect the average cost, and the cost of the product will change. If the value in the Cost field on a product form is changed manually, Odoo generates a corresponding record in the _Inventory Valuation_ report.

Nota

It is possible to use different valuation settings for different product categories.

## Types of accounting¶

With automated inventory valuation set up, the generated journal entries depend on the chosen accounting mode: _Continental_ or _Anglo-Saxon_.

Suggerimento

Verify the accounting mode by activating the [Modalità sviluppatore (modalità di debug)](../../../../general/developer_mode.html#developer-mode), and navigating to Accounting app ‣ Configuration ‣ Settings.

Then, in the Search… bar, look for `Anglo-Saxon Accounting`, to see if the feature is enabled. If it is **not** enabled, _Continental_ accounting mode is in use.

In _Anglo-Saxon_ accounting, the costs of goods sold (COGS) are reported when products are sold or delivered. This means the cost of a good is only recorded as an expense when a customer is invoiced for a product.

So, for **manual** valuation method, set the _Expense Account_ to _Stock Valuation_ for the current asset type; for **automatic** valuation method, set the _Expense Account_ to an _Expenses_ or a _Cost of Revenue_ type (e.g. _Cost of Production_ , _Cost of Goods Sold_ , etc.).

In _Continental_ accounting, the cost of a good is reported as soon as a product is received into stock. Because of this, the _Expense Account_ can be set to **either** _Expenses_ or a _Cost of Revenue_ type, however, it is more commonly set to an _Expenses_ account.

Refer to the Expense and Stock input/output sections for details on configuring each account type.

### Conto di costo¶

To configure the _expense account_ , which is used in both manual and automatic inventory valuation, go to the Account Properties section of the intended product category (Inventory app ‣ Configuration ‣ Product Categories). Then, choose an existing account from the Expense Account drop-down menu.

To ensure the chosen account is the correct Type, click the __(right arrow) icon to the right of the account. Then, set the account type based on the information below.

Anglo-SaxonContinental

AutomatedManual

In Anglo-Saxon accounting for automated inventory valuation, set the Expense Account to the `Expenses` account. Then, click the __(right arrow) icon to the right of the account.

In the pop-up window, choose Expenses or Cost of Revenue from the Type drop-down menu.

To configure the Expense Account, choose Stock Valuation from the field’s drop-down menu. Verify the account’s type by clicking the __(right arrow) icon, and then ensure the Type is Current Assets.

AutomatedManual

Set the Expense Account to the Expenses or Cost of Revenue account type.

Set the Expense Account to the Expenses or Cost of Revenue account type.

#### Stock input/output (automated only)¶

To configure the Stock Input Account and Stock Output Account, go to Inventory app ‣ Configuration ‣ Product Categories and select the desired product category.

In the Inventory Valuation field, select Automated. Doing so makes the Account Stock Properties section appear. These accounts are defined as follows:

  * Stock Valuation Account: when automated inventory valuation is enabled on a product, this account will hold the current value of the products.

  * Stock Journal: accounting journal where entries are automatically posted when a product’s inventory valuation changes.

  * Stock Input Account: counterpart journal items for all incoming stock moves will be posted in this account, unless there is a specific valuation account set on the source location. This is the default value for all products in a given category, and can also be set directly on each product.

  * Stock Output Account: counterpart journal items for all outgoing stock moves will be posted in this account, unless there is a specific valuation account set on the destination location. This is the default value for all products in a given category, and can also be set directly on each product.




Anglo-SaxonContinental

In Anglo-Saxon accounting, the Stock Input Account and Stock Output Account are set to _different_ Current Assets accounts. This way, delivering products and invoicing the customer balance the _Stock Output_ account, while receiving products and billing vendors balance the _Stock Input_ account.

To modify the account type, go to the click the __(right arrow) icon to the right of the stock input/output account. In the pop-up window, choose Current Assets from the Type drop-down menu.

The _Stock Input_ account is set to `Stock Interim (Received)`, a _Current Asset_ account type.¶

In Continental accounting, the Stock Input Account and Stock Output Account are set to **the same** Current Assets account. That way, one account can be balanced when items are bought and sold.

Example

The stock input and output accounts are both set to `Stock Interim (Received)`, a Current Assets account type. They can also be set to the `Stock Interim (Delivered)`, as long as the input and output accounts are assigned to the **same** account.

## Inventory valuation reporting¶

To start, go to Accounting app ‣ Reporting ‣ Balance Sheet. Click the Current Assets line item to unfold the drop-down menu, and look for the nested Stock Valuation, Stock Interim (Received), and Stock Interim (Delivered) lines.

Suggerimento

At the top of the dashboard, click the As of [date] button to display accounting records up to a specified date.

Vedi anche

  * Stock accounts and what they do

  * [Promemoria contabile](../../../../finance/accounting/get_started/cheat_sheet.html)




Access more specific information by clicking the __(ellipsis) icon to the right of the desired journal. Select General Ledger to see a list of all of the journal entries, where each line item’s __(ellipsis) icon can be clicked to reveal the View Journal Entry option to open the individualized journal entry.

Additionally, annotations to the Balance Sheet can be added by choosing Annotate, filling in the text box, and clicking Save.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](using_inventory_valuation.html "Using inventory valuation") |
  * [precedente](../inventory_valuation.html "Valutazione dell’inventario") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Automatic inventory valuation


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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expired, First Out
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