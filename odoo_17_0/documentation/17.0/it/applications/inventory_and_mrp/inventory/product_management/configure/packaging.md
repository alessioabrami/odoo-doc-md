# Imballaggio — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../product_tracking.html "Product tracking") |
  * [precedente](package.html "Colli") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Imballaggio



# Imballaggio¶

In Odoo _Inventory_ , _packaging_ refers to disposable containers holding multiple units of a specific product.

For example, different packages for cans of soda, such as a 6-pack, a 12-pack, or a case of 36, **must** be configured on the individual product form. This is because packagings are product specific, not generic.

Suggerimento

Packaging can be used in conjunction with Odoo [Barcode](../../../barcode/setup/software.html#inventory-barcode-software). When receiving products from suppliers, scanning the packaging barcode automatically adds the number of units in the packaging to the internal count of the product.

## Configurazione¶

To use packagings, navigate to Inventory app ‣ Configuration ‣ Settings. Then, under the Products heading, enable the Product Packagings feature, and click Save.

## Create packaging¶

Packagings can be created directly on the product form, or from the Product Packagings page.

### From product form¶

Create packagings on a product form by going to Inventory app ‣ Products ‣ Products, and select the desired product.

Under the Inventory tab, scroll down to the Packaging section, and click Add a line. In the table, fill out the following fields:

  * Packaging (required): name of packaging that appears on sales/purchase orders as a packaging option for the product.

  * Contained quantity (required): amount of product in the packaging.

  * Unit of Measure (required): measurement unit for quantifying the product.

  * Sales: check this option for packagings intended for use on sales orders.

  * Purchase: check this option for packagings intended for use on purchase orders.




Nota

Access additional fields in the Packaging table below by clicking the __(additional options) icon to the far-right of the column titles in the Packaging section, and selecting the desired options from the drop-down menu that appears.

  * Barcode: identifier for tracing packaging in stock moves or pickings, using the [Barcode app](../../../barcode/operations/receipts_deliveries.html#barcode-operations-intro). Leave blank if not in use.

  * Company: indicates the packaging is only available at the selected company. Leave blank to make the packaging available across all companies.




Example

To create a packaging type for six units of the product, `Grape Soda`, begin by clicking Add a line. In the line, name the Packaging `6-pack`, and set the Contained quantity to `6`. Repeat this process for additional packagings.

### From product packagings page¶

To view all packagings that have been created, go to Inventory app ‣ Configuration ‣ Product Packagings. Doing so reveals the Product Packagings page with a complete list of all packagings that have been created for all products. Create new packagings by clicking New.

Example

Two soda products, `Grape Soda` and `Diet Coke`, have three types of packagings configured. On the Product Packagings page, each product can be sold as a `6-Pack` that contains 6 products, as a `12-Pack` of 12 products, or as a `Case` of 32 products.

### Partial reservation¶

After completing the packaging setup, packagings can be reserved in full or partial quantities for outgoing shipments. Partial packaging flexibility expedites order fulfillment by allowing the immediate shipment of available items, while awaiting the rest.

To configure packaging reservation methods, go to Inventory app ‣ Configuration ‣ Product Categories. Then, click New, or select the desired product category.

On the product category’s form, in the Logistics section, Reserve Packagings can be set to Reserve Only Full Packagings or Reserve Partial Packagings.

Importante

To see the Reserve Packaging field, the Product Packaging feature **must** be enabled. To enable this feature, go to Inventory app ‣ Configuration ‣ Settings, scroll to the Products section, tick the Product Packagings checkbox, and click Save.

Example

To better evaluate the options based on business needs, consider the following example:

  * a product is sold in twelve units per packaging.

  * an order demands two packagings.

  * there are only twenty-two units in stock.




When Reserve Only Full Packagings is selected, only twelve units are reserved for the order.

Conversely, when Reserve Partial Packagings is selected, twenty-two units are reserved for the order.

## Apply packagings¶

When creating a sales order in the Sales app, specify the packagings that should be used for the product. The chosen packaging is displayed on the SO under the Packaging field.

Example

18 cans of the product, `Grape Soda`, is packed using three 6-pack packagings.

## Routes for packaging¶

When receiving packagings, by default, they follow the warehouse’s [configured reception route](../../shipping_receiving/daily_operations.html). To **optionally** set up a packaging-specific route, go to Inventory app ‣ Configuration ‣ Routes.

Importante

The _Product Packagings_ , _Storage Locations_ , and _Multi-Step Routes_ features (found by going to Inventory app ‣ Configuration ‣ Settings) **must** be activated, and saved.

Vedi anche

[Routes and push/pull rules](../../shipping_receiving/daily_operations/use_routes.html)

### Create route¶

On the Routes page, click New, or select a route that is **not** for a warehouse. Next, in the Applicable on section, tick the Packagings checkbox.

Route with «Packagings» selected, with «Products» and «Warehouses» not selected.¶

### Apply route on packaging¶

Then, to apply the route, go to Inventory app ‣ Products ‣ Products, and select the product that uses packaging.

In the product form, switch to the Inventory tab. In the Packaging section that contains configured packagings, click the __(additional options) icon. Tick the Routes checkbox to make the column visible in the Packaging table.

In the Routes field, select the packaging-specific route. Repeat these steps for all packaging intended to use the route.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/configure/packaging.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../product_tracking.html "Product tracking") |
  * [precedente](package.html "Colli") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Imballaggio


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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In First Out
  *[FEFO]: First Expired, First Out
  *[UoMs]: Units of Measure