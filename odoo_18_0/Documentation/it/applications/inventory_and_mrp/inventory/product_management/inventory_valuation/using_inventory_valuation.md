# Using inventory valuation — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](landed_costs.html "Landed costs") |
  * [precedente](inventory_valuation_config.html "Automatic inventory valuation") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Using inventory valuation



# Using inventory valuation¶

_Inventory valuation_ is a quintessential accounting procedure that calculates the value of on-hand stock. Once determined, the inventory valuation amount is then incorporated into a company’s overall value.

In Odoo, this process can be conducted manually— by warehouse employees physically counting the products— or automatically through the database.

## Automatic inventory valuation¶

To use Odoo to automatically generate a trail of inventory valuation entries, first navigate to the Product Categories list by going to Inventory app ‣ Configuration ‣ Product Categories and select the desired product category. On the form, set the Inventory Valuation as Automated and the Costing Method to any of the three options.

Vedi anche

[Set up inventory valuation](inventory_valuation_config.html)

In order to understand how moving products in and out of stock affects the company’s overall value, consider the following product and stock moves scenario below.

### Receive a product¶

To track the value of incoming products, such as a simple _table_ , configure the product category on the the product itself. To get there, navigate to Inventory app ‣ Products ‣ Products and click the desired product. On the product form, click the ➡️ (right arrow) icon beside the Product Category field, which opens an internal link to edit the product category. Next, set the Costing Method as First In First Out (FIFO) and Inventory Valuation as Automated.

Suggerimento

Alternatively access the Product Categories dashboard by navigating to Inventory app ‣ Configuration ‣ Product Categories and select the desired product category.

Next, assume 10 tables are purchased at a price of $10.00, each. The PO for those tables will show the subtotal of the purchase as $100, plus any additional costs or taxes.

After selecting Validate on the PO, the Valuation smart button is enabled. Clicking on this button displays a report showing how the inventory valuation for the table was affected by this purchase.

Importante

[Developer mode](../../../../general/developer_mode.html#developer-mode) **must** be turned on to see the Valuation smart button.

Suggerimento

The [consignment](../../shipping_receiving/daily_operations/owned_stock.html) feature allows ownership to items in stock. Thus, products owned by other companies are not accounted for in the host company’s inventory valuation.

For a comprehensive dashboard that includes the inventory valuation of all product shipments, inventory adjustments, and warehouse operations, refer to the stock valuation report.

### Deliver a product¶

In the same logic, when a table is shipped to a customer and leaves the warehouse, the stock valuation decreases. The Valuation smart button on the DO, likewise, displays the stock valuation record as it does on a PO.

## Inventory valuation report¶

To view the current value of all products in the warehouse, first turn on [Developer mode](../../../../general/developer_mode.html#developer-mode) and navigate to Inventory app ‣ Reporting ‣ Valuation. The Stock Valuation dashboard displays detailed records of products with the Date, Quantity, Unit Value, and Total Value of the inventory.

Importante

[Developer mode](../../../../general/developer_mode.html#developer-mode) **must** be enabled to see the Valuation option under Reporting.

The Valuation At Date button, located in the top-left corner of the Stock Valuation page, reveals a pop-up window. In this pop-up, the inventory valuation of products available during a prior specified date can be seen and selected.

Suggerimento

View a detailed record of a product’s inventory value, stock move, and on-hand stock by selecting the teal ➡️ (right arrow) button to the right of the Reference column value.

### Update product unit price¶

For any company: lead times, supply chain failures, and other risk factors can contribute to invisible costs. Although Odoo attempts to accurately represent the stock value, _manual valuation_ serves as an additional tool to update the unit price of products.

Importante

Manual valuation is intended for products that can be purchased and received for a cost greater than 0, or have product categories set with Costing Method set as either Average Cost (AVCO) or First In First Out (FIFO).

Create manual valuation entries on the Stock Valuation dashboard by first navigating to Inventory app ‣ Reporting ‣ Valuation. Next, to enable the _product revaluation_ feature, select Group by ‣ Product to organize all the records by product. Click on the gray ▶️ (drop-down triangle) icon to reveal stock valuation line items below, as well as a teal ➕ (plus) button on the right.

Click the teal \+ (plus) button to open up the Product Revaluation form. Here, the inventory valuation for a product can be recalculated, by increasing or decreasing the unit price of each product.

Nota

The ▶️ (drop-down triangle) and ➕ (plus) buttons are only visible after grouping entries by product.

### Inventory valuation journal entries¶

In Odoo, automatic inventory valuation records are also recorded in the Accounting app ‣ Accounting ‣ Journal Entries dashboard. On this comprehensive list of accounting entries, inventory valuation records are identified by checking values in the Journal column, or looking for the Reference column value which matches the warehouse operation reference (e.g. `WH/IN/00014` for receipts).

Clicking on an inventory valuation journal entry opens a _double-entry accounting_ record. These records are generated by Odoo to track the change of value in inventory valuation as products are moved in and out of the warehouse.

Example

To view the inventory valuation of 10 _tables_ , costing $10.00 each, upon reception from the vendor, go to the Journal Entries page found in Accounting app ‣ Accounting ‣ Journal Entries. Here, click the journal line where the Reference column value matches the reference on the receipt, `WH/IN/00014`.

`Stock interim` is a holding account for money intended to pay vendors for the product. The `stock valuation` account stores the value of all on-hand stock.

Vedi anche

[Odoo Tutorial: Inventory Valuation](https://www.odoo.com/slides/slide/2795/share)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/inventory_valuation/using_inventory_valuation.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](landed_costs.html "Landed costs") |
  * [precedente](inventory_valuation_config.html "Automatic inventory valuation") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Using inventory valuation


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