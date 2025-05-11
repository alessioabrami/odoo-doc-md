# Product type — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Unità di misura") |
  * [precedente](../configure.html "Configure product") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Product type



# Product type¶

In Odoo, goods and services are both set up as _products_. When setting up a new product, there are several fields that should be carefully chosen, as they determine how to invoice and track a business” goods or services.

To configure an existing product, go to Inventory app ‣ Products ‣ Products, and select the desired product from the list. Alternatively, from the Products menu, click New to create a new product.

Vedi anche

[Odoo Tutorials: Product Type](https://www.youtube.com/watch?v=l6j0ZkP5mLM)

## For sale vs. purchase¶

Goods and services can be designated as those that can be bought, sold, or both. On the product form, tick the Sales checkbox if a product can be _sold_ to a customer (e.g. finished goods). Tick Purchase if the product can be _purchased_ (e.g. raw materials).

Example

If a resale clothing shop buys discounted denim jackets and sells them at a higher cost to the end consumer, the `Jacket` product form might have _both_ the Sales and Purchase checkbox ticked.

On the other hand, say the store occasionally sews new jackets using denim and thread as raw materials. In the `Denim` and `Thread` product forms, only Purchase should be ticked, whereas the `Handmade Jacket` product form would only tick Sales.

## Goods vs. services¶

When configuring a product, a Product Type needs to be selected on the General Information tab of a product form. Each product type impacts different operations in other Odoo applications, such as **Sales** and **Purchase** , and should be chosen carefully.

  * Goods: a tangible, material object (e.g. anything from a hamburger to a house)

  * Service: an intangible, immaterial offering (e.g., a repair, a haircut, call center assistance)

  * Combo: any mix of goods and services (e.g. a new car (_good_) with an oil change included (_service_))




Nota

Due to their immaterial nature, services are not trackable in Odoo’s **Inventory** application.

## Configure goods¶

Selecting Goods as the Product Type automatically triggers the appearance of a few fields and tabs in the product form:

  * Inventory tab: From here, [purchasing and manufacturing routes](../../shipping_receiving/daily_operations/use_routes.html) and product logistics, such as product weight and customer lead time, can be specified.

  * Invoicing Policy field: This field determines at what point in the sales process a customer is invoiced.

Importante

The Invoicing Policy field **only** appears if the **Sales** app is installed.

  * Track Inventory field: This checkbox determines whether Odoo tracks inventory for this product.

  * Smart buttons: Some smart buttons appear above the form when Goods is selected; others show upon selecting a Track Inventory method. For example, On Hand and Forecasted display when Track Inventory is ticked. In general, most smart buttons on a product form link to inventory operations.




### Invoicing policy¶

The Invoicing policy field only shows on the product form if a product is for sale (in other words, if Sales is ticked, and the **Sales** app is installed).

When configuring a product for sale, it is necessary to choose an [invoicing policy](../../../../sales/sales/invoicing/invoicing_policy.html). When an invoicing policy of Ordered quantities is selected, customers are invoiced once the sales order is confirmed. When Delivered quantities is selected, customers are invoiced once the delivery is completed.

### Tracked vs. untracked goods¶

The Track Inventory field on the product form determines a lot of Odoo’s **Inventory** operations.

_Tracked_ products are those for which stock and inventory are maintained. Examples include finished goods and, often, the raw materials or components needed to make them.

When Track Inventory is ticked, a drop-down menu appears, offering for inventory to be tracked one of three ways: By Unique Serial Number, By Lots, or By Quantity.

_Untracked_ products (sometimes referred to as _non-inventory_ products) are typically consumed in a short period of time, meaning that stock/inventory does _not_ need to be maintained. Non-inventory products are often essential, but exact counts are unnecessary. Examples include: office supplies, packaging materials, or items used in production that do not need to be individually tracked.

Suggerimento

Tick the Track Inventory checkbox if it is necessary to track a product’s stock at various locations, for inventory valuation, with lots and/or serial numbers, or when using reordering rules.

Vedi anche

[Tracking storable products using lot and serial numbers](../product_tracking.html)

### Inventory operations by product type¶

Whether a good is tracked or untracked affects common **Inventory** operations, like transfers and reordering rules.

The table below summarizes which operations (and smart buttons) are enabled for tracked vs. untracked goods. Click highlighted chart items to navigate to detailed sections and related documents.

Inventory operation | Monitorata | Untracked  
---|---|---  
Show on-hand quantity | Sì | No  
Show forecasted quantity | Sì | No  
Use reordering rules | Sì | No  
Can be included in a purchase order | Sì | Sì  
Use putaway rules | Sì | No  
Can be manufactured, subcontracted, or used in another good’s BoM | Sì | Sì  
[Use inventory adjustments](../../warehouses_storage/inventory_management/count_products.html) | Sì | No  
[Use inventory valuation](../inventory_valuation/using_inventory_valuation.html) | Sì | No  
Create transfer | Sì | Sì  
[Use lot/serial number tracking](../product_tracking.html) | Sì | No  
[Can be placed in a kit](../../../manufacturing/advanced_configuration/kit_shipping.html) | Sì | Sì  
Can be placed in a package | Sì | Sì  
Appears on inventory reports | Sì | No  
  
#### Magazzino¶

##### On-hand and forecasted quantities¶

A tracked product’s on-hand and forecasted quantities, based on incoming and outgoing orders, are reflected on the product form with two smart buttons:

  * __ On-Hand Quantity: This represents the number of units currently available in inventory. Click the button to view or add stock levels for a tracked product.

  * __ Forecasted: This represents the number of units _expected_ to be available in inventory after all orders are taken into account. In other words, \\(\text{forecasted} = \text{on hand quantity} + \text{incoming shipments} - \text{outgoing shipments}\\). Click the button to view the Forecasted Report.




On the other hand, untracked products are regarded as _always_ available. Consequently, On-Hand Quantity is not tracked, and there is no Forecasted quantity available.

##### Putaway rules and storage¶

Both tracked and untracked goods can optimize storage using:

  * __[ Putaway Rules](../../shipping_receiving/daily_operations/putaway.html): This represents putaway rules that apply to a good, such as where to store it when a new shipment arrives.

  * __[ Storage Capacities](../../shipping_receiving/daily_operations/storage_category.html): This represents any storage capacity limitations specified for this good. For example, a warehouse may require that only ten (or less) sofas be stored there at any given time, due to their large size.




##### Rifornimenti¶

###### Reordering rules¶

Only tracked products can trigger [reordering rules](../../warehouses_storage/replenishment/reordering_rules.html) to generate purchase orders. Untracked goods _cannot_ be managed using reordering rules.

Reordering rules can be configured directly on the product form via the __(refresh) icon.

Nota

If reordering rules already exist on a product, Odoo re-labels this button to Min / Max, to show the minimum and maximum number of units that must be in stock.

###### Creare ordini di acquisto¶

Both tracked and untracked products can be included in a request for quotation in the **Purchase** app. However, when receiving untracked products, their on-hand quantity does not change upon validating the receipt (`WH/IN`).

###### Replenish smart button¶

The Replenish smart button allows all goods to be restocked directly from the product form, according to the _Preferred Route_.

Vedi anche

[Replenishment](../../warehouses_storage/replenishment.html) [Odoo Tutorials: Replenishment Methods for Manufacturing](https://www.youtube.com/watch?v=vtjeMGcG8aM)

#### Produzione¶

Both tracked and untracked products can be manufactured, [subcontracted](../../../manufacturing/subcontracting.html), or included in another product’s [bill of materials (BoM)](../../../manufacturing/basic_setup/bill_configuration.html).

On the product form for a tracked or untracked good, there are several smart buttons that may appear for manufacturing operations:

  * __ Bill of Materials: This shows the BoMs used to make this product.

  * __ Used In: This shows other goods that include this product in their BoM.




#### Transfer goods¶

_Transfers_ are warehouse operations that involve the movement of goods. Examples of transfers include [deliveries and receipts](../../shipping_receiving/daily_operations/receipts_delivery_one_step.html), as well as [internal transfers](../../warehouses_storage/replenishment/resupply_warehouses.html) between warehouses.

When creating a transfer for tracked products in the **Inventory** app, transfers modify the on-hand quantity at each location. For example, transferring five units from the internal location `WH/Stock` to `WH/Packing Zone` decreases the recorded quantity at `WH/Stock` and increases it at `WH/Packing Zone`.

For untracked products, transfers can be created, but exact quantities at each storage location are not tracked.

#### Colli¶

Both tracked and untracked (non-inventory), products can be placed in [packages](package.html).

However, for non-inventory products, the quantity is not tracked, and the product is not listed in the package’s Contents (which can be accessed by going to Inventory app ‣ Products ‣ Packages, and selecting the desired package).

An untracked product was placed in the package, but the **Content** section does not list it.¶

Additionally, if the _Move Entire Packages_ feature is enabled, moving a package updates the location of the contained tracked products but not the contained untracked products. To enable this feature, navigate to Inventory app ‣ Configuration ‣ Operations Types, select any operation, and tick the Move Entire Packages checkbox.

#### Inventory reports¶

**Only** tracked products appear on the following reports.

Importante

These reports are only available to users with [administrator access](../../../../general/users/access_rights.html).

  * [Stock report](../../warehouses_storage/reporting/stock.html): This report provides a comprehensive list of all on-hand, unreserved, incoming, and outgoing tracked inventory. To access the report, go to Inventory app ‣ Reporting ‣ Stock.

  * [Location report](../../warehouses_storage/reporting/locations.html): This report shows a breakdown of which tracked products are held at each location (internal, external, or virtual). The report is only available with the _Storage Location_ feature activated (Inventory app ‣ Configuration ‣ Settings). To access it, go to Inventory app ‣ Reporting ‣ Locations.

  * [Moves History report](../../warehouses_storage/reporting/moves_history.html): This report summarizes where and when this good has moved in/out of stock. To access the report, go to Inventory app ‣ Reporting ‣ Moves History. Alternatively, click the __ In / Out smart button on a product form to filter the report on that product’s specific moves history.

  * Moves Analysis: This report provides a pivot table view of inventory transfers by operation type.

  * [Stock Valuation report](../inventory_valuation/using_inventory_valuation.html#inventory-management-reporting-valuation-report): A detailed record of the monetary value of all tracked inventory.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/configure/type.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Unità di misura") |
  * [precedente](../configure.html "Configure product") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Product type


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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In First Out
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