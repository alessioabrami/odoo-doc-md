# Routes and push/pull rules — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_delivery_one_step.html "One-step receipt and delivery") |
  * [precedente](../daily_operations.html "Inbound and outbound flows") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Routes and push/pull rules



# Routes and push/pull rules¶

_Routes_ in Odoo control the movement of products between different locations, whether internal or external, using push and pull rules. Once set up, these rules help automate the logistics of product movement based on specific conditions.

Vedi anche

  * [Odoo Tutorials: Routes](https://www.youtube.com/watch?v=qkhDUezyZuc)

  * [Standard routes in Odoo](../daily_operations.html)




Nota

Routes are applicable on products, product categories, shipping methods, [packagings](../../product_management/configure/packaging.html#inventory-product-management-route-on-packaging), and on the sales order line.

## About routes and terminology¶

In a generic warehouse, there are receiving docks, a quality control area, storage locations, picking and packing areas, and shipping docks. All products go through all these locations. As the products move through the locations, each location triggers the products” specified route and rules.

In this example, vendor trucks unload pallets of ordered products at the receiving docks. Operators then scan the products in the receiving area. Depending on the product’s route and rules, some of these products are sent to a quality control area (for example, products that are components used in the manufacturing process), while others are directly stored in their respective locations.

Here is an example of a fulfillment route. In the morning, items are picked for all the orders that need to be prepared during the day. These items are picked from storage locations and moved to the picking area, close to where the orders are packed. Then, the orders are packed in their respective boxes, and conveyor belts bring them to the shipping docks, ready to be delivered to customers.

### Push rules¶

Push rules are used to _supply products into a storage locations_ as soon as they arrive at a specific receiving location.

Nota

Push rules can only be triggered if there are no pull rules that have already generated the product transfers.

In a [one-step receipt route](receipts_delivery_one_step.html), which uses one push rule, when a product arrives in the warehouse, a push rule can automatically transfer it to the _Storage Location_. Different push rules can be applied to different products, allowing for customized storage locations.

Push rule for the “Receive in one step” route.¶

For more information about configuring rules, skip to the Configure rules section.

### Pull rules¶

Pull rules trigger product moves on demand, such as a sales order or a [need to restock](../../warehouses_storage/replenishment/reordering_rules.html).

Pull rules work backward from the demand location. For example, in a [two-step delivery](receipts_delivery_two_steps.html#inventory-shipping-receiving-two-step-delivery) route, where items move from _Stock_ to _Output_ before being delivered to the _Customer Location_ , the pull rule first creates a transfer from _Output_ to the customer. If the product is not at _Output_ , another pull rule creates a transfer from _Stock_ to _Output_. The warehouse workers then process these transfers in the reverse order: picking, then shipping.

Pull rules for the “Deliver in two steps” route.¶

For more information about configuring rules, skip to the Configure rules section.

## Configurazione¶

Since _Routes_ are a collection of _Push and Pull Rules_ , Odoo helps you manage advanced route configurations such as:

  * Manage product manufacturing chains.

  * Manage default locations per product.

  * Define routes within the stock warehouse according to business needs, such as quality control, after-sales services, or supplier returns.

  * Help rental management by generating automated return moves for rented products.




To configure a route for a product, first, open the Inventory application and go to Configuration ‣ Settings. Then, in the Warehouse section, enable the Multi-Step Routes feature and click Save.

Nota

The Storage Locations feature is automatically activated with the Multi-Step Routes feature.

Once this first step is completed, the user can use pre-configured routes that come with Odoo, or they can create custom routes.

### Pre-configured routes¶

To access Odoo’s pre-configured routes, go to Inventory ‣ Configuration ‣ Warehouses. Then, open a warehouse form. In the Warehouse Configuration tab, the user can view the warehouse’s pre-configured routes for Incoming Shipments and Outgoing Shipments.

Some more advanced routes, such as pick-pack-ship, are also available. The user can select the route that best fits their business needs. Once the Incoming Shipments and Outgoing Shipments routes are set, head to Inventory ‣ Configuration ‣ Routes to see the specific routes that Odoo generated.

On the Routes page, click on a route to open the route form. In the route form, the user can view which places the route is Applicable On. The user can also set the route to only apply on a specific Company. This is useful for multi-company environments; for example, a user can have a company and warehouse in Country A and a second company and warehouse in Country B.

Vedi anche

[Applicable on packagings](../../product_management/configure/packaging.html#inventory-product-management-packaging-route)

At the bottom of the route form, the user can view the specific Rules for the route. Each Rule has an Action, a Source Location, and a Destination Location.

### Custom Routes¶

To create a custom route, go to Inventory ‣ Configuration ‣ Routes, and click on Create. Next, choose the places where this route can be selected. A route can be applicable on a combination of places.

Each place has a different behavior, so it is important to tick only the useful ones and adapt each route accordingly. Then, configure the Rules of the route.

If the route is applicable on a product category, the route still needs to be manually set on the product category form by going to Inventory ‣ Configuration ‣ Product Categories. Then, select the product category and open the form. Next, click Edit and under the Logistics section, set the Routes.

When applying the route on a product category, all the rules configured in the route are applied to **every** product in the category. This can be helpful if the business uses the dropshipping process for all the products from the same category.

The same behavior applies to the warehouses. If the route can apply to Warehouses, all the transfers occurring inside the chosen warehouse that meet the conditions of the route’s rules will then follow that route.

If the route is applicable on Sales Order Lines, it is more or less the opposite. The route must be manually chosen when creating a quotation. This is useful if some products go through different routes.

Remember to toggle the visibility of the Route column on the quotation/sales order. Then, the route can be chosen on each line of the quotation/sales order.

Finally, there are routes that can be applied to products. Those work more or less like the product categories: once selected, the route must be manually set on the product form.

To set a route on a product, go to Inventory ‣ Products ‣ Products and select the desired product. Then, go to the Inventory tab and under the Operations section, select the Routes.

Importante

Rules must be set on the route in order for the route to work.

#### Regole¶

The rules are defined on the route form. First, go to Inventory ‣ Configuration ‣ Routes and open the desired route form. Next, click Edit and in the Rules section, click on Add a line.

The available rules trigger various actions. If Odoo offers _Push_ and _Pull_ rules, others are also available. Each rule has an Action:

  * Pull From: this rule is triggered by a need for the product in a specific location. The need can come from a sales order being validated or from a manufacturing order requiring a specific component. When the need appears in the destination location, Odoo generates a picking to fulfill this need.

  * Push To: this rule is triggered by the arrival of some products in the defined source location. In the case of the user moving products to the source location, Odoo generates a picking to move those products to the destination location.

  * Pull & Push: this rule allows the generation of pickings in the two situations explained above. This means that when products are required at a specific location, a transfer is created from the previous location to fulfill that need. This creates a need in the previous location and a rule is triggered to fulfill it. Once the second need is fulfilled, the products are pushed to the destination location and all the needs are fulfilled.

  * Buy: when products are needed at the destination location, a request for quotation is created to fulfill the need.

  * Manufacture: when products are needed in the source location, a manufacturing order is created to fulfill the need.




The Operation Type must also be defined on the rule. This defines which kind of picking is created from the rule.

If the rule’s Action is set to Pull From or Pull & Push, a Supply Method must be set. The Supply Method defines what happens at the source location:

  * Take From Stock: the products are taken from the available stock of the source location.

  * Trigger Another Rule: the system tries to find a stock rule to bring the products to the source location. The available stock is ignored.

  * Take From Stock, if Unavailable, Trigger Another Rule: the products are taken from the available stock of the source location. If there is no stock available, the system tries to find a rule to bring the products to the source location.




## Example flow¶

In this example, let’s use a custom _Pick - Pack - Ship_ route to try a full flow with an advanced custom route.

First, a quick look at the route’s rules and their supply methods. There are three rules, all Pull From rules. The Supply Methods for each rule are the following:

  * Take From Stock: When products are needed in the WH/Packing Zone, _picks_ (internal transfers from WH/Stock to WH/Packing Zone) are created from WH/Stock to fulfill the need.

  * Trigger Another Rule: When products are needed in WH/Output, _packs_ (internal transfers from WH/Packing Zone to WH/Output) are created from WH/Packing Zone to fulfill the need.

  * Trigger Another Rule: When products are needed in Partner Locations/Customers, _delivery orders_ are created from WH/Output to fulfill the need.




This means that, when a customer orders products that have a _pick - pack - ship_ route set on it, a delivery order is created to fulfill the order.

Nota

If the source document for multiple tranfers is the same sales order, the status is not the same. The status will be Waiting Another Operation if the previous transfer in the list is not done yet.

To prepare the delivery order, packed products are needed at the output area, so an internal transfer is requested from the packing zone.

Obviously, the packing zone needs products ready to be packed. So, an internal transfer is requested to the stock and employees can gather the required products from the warehouse.

As explained in the introduction of the documentation, the last step in the process (for this route, the delivery order) is the first to be triggered, which then triggers other rules until we reach the first step in the process (here, the internal transfer from the stock to the packing area). Now, everything is ready to be processed so the customer can get the ordered items.

In this example, the product is delivered to the customer when all the rules have been triggered and the transfers are done.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations/use_routes.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_delivery_one_step.html "One-step receipt and delivery") |
  * [precedente](../daily_operations.html "Inbound and outbound flows") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Routes and push/pull rules


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
  *[UoM]: Units of Measure
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
  *[LIFO]: Last-In, First-Out
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