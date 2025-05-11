# Delivery methods — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](setup_configuration/third_party_shipper.html "Third-party shipping carriers") |
  * [precedente](daily_operations/dropshipping.html "Dropshipping") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Delivery methods



# Delivery methods¶

When activated in Odoo, the _Delivery Methods_ setting adds the option of calculating the cost of shipping on sales orders and e-commerce shopping carts.

When integrated with a [third-party carrier](setup_configuration/third_party_shipper.html#inventory-shipping-third-party), shipping prices are calculated based on the carrier’s pricing and packaging information.

Vedi anche

  * [Third-party shipping carrier setup](setup_configuration/third_party_shipper.html#inventory-shipping-third-party)

  * [Odoo Tutorials: Delivery Prices](https://www.odoo.com/slides/slide/delivery-prices-613?fullscreen=1)




## Configurazione¶

To calculate shipping on sales orders and e-commerce, the _Delivery Costs_ module must be installed. To do so, navigate to the Apps application from the main Odoo dashboard.

Then, remove the Apps filter, and type in `Delivery Costs` in the Search… bar. After finding the Delivery Costs module, click Activate to install it.

## Add shipping method¶

To configure delivery methods, go to Inventory app ‣ Configuration ‣ Shipping Methods.

Nota

If the Shipping Methods option is not available from the Configuration drop-down menu, verify whether the feature is enabled by following these steps:

  1. Go to Inventory app ‣ Configuration ‣ Settings.

  2. Scroll to the Shipping section and enable the Delivery Methods feature by checking the corresponding checkbox.




On the Shipping Methods page, add a method by clicking New. Doing so opens a form to provide details about the shipping provider, including:

  * Shipping Method (_Required field_): the name of the delivery method (e.g. `flat-rate shipping`, `same day delivery`, etc.).

  * Provider (_Required field_): choose the delivery service, like Fedex, if using a [third-party carrier](setup_configuration/third_party_shipper.html#inventory-shipping-third-party). Ensure the integration with the shipping carrier is properly installed and select the provider from the drop-down menu.

For more details on configuring custom shipping methods, such as fixed price, based on rules, or pickup in store options, refer to their respective sections below.

  * Website: configure shipping methods for an e-commerce page. Select the applicable website from the drop-down menu, or leave it blank to apply the method to all web pages.

  * Company: If the shipping method should apply to a specific company, select it from the drop-down menu. Leave the field blank to apply the method to all companies.

  * Routes: select the applicable route(s) to define different delivery methods, such as standard or express shipping, based on varying lead times. For more information, jump to the Set routes on shipping method section.



  * Delivery Product (_Required field_): the product listed on the sales order line as the delivery charge.

  * Free if order amount is above: checking this box enables free shipping if the customer spends above the specified amount.




For examples on how to configure specific shipping methods, refer to the sections below.

### Prezzo fisso¶

To configure a shipping price that is the same for all orders, go to Inventory app ‣ Configuration ‣ Shipping Methods. Then, click New, and on the shipping method form, set the Provider to the Fixed Price option. Selecting this option makes the Fixed Price field become available, which is where the fixed rate shipping amount is defined.

To enable free shipping if the amount of the order exceeds a specified amount, check the box Free if order amount is above and fill in the amount.

Example

To set up `$20` flat-rate shipping that becomes free if the customer spends over `$100`, fill in the following fields:

  * Shipping Method: `Flat-rate shipping`

  * Provider: Fixed Price

  * Fixed Price: `$20.00`

  * Free if order amount is above: `$100.00`

  * Delivery Product: `[SHIP] Flat`




### Based on rules¶

To calculate the price of shipping based on pricing rules, set the Provider field to the Based on Rules option. Optionally, adjust Margin on Rate and Additional margin to include additional shipping costs.

#### Create pricing rules¶

Navigate to the Pricing tab and click Add a line. Doing so opens the Create Pricing Rules window, where the Condition related to the product weight, volume, price, or quantity is compared to a defined amount to calculate the Delivery Cost.

Once finished, click either Save & New to add another rule, or Save & Close.

Example

To charge customers $20 in shipping for orders with five or fewer products, set the Condition to `Quantity <= 5.00`, and the Delivery Cost to `$20`.

To restrict shipping to specific destinations on the eCommerce website, in the shipping method form, navigate to the Destination Availability tab and define the Countries, States, and Zip Prefixes. Leave these fields empty if all locations apply.

#### Calculate delivery cost¶

Shipping cost is the Delivery cost specified in the rule that satisfies the Condition, plus any extra charges from the Margin on rate and Additional margin.

\\[Total = Rule's~Delivery~Cost + (Margin~on~rate \times Rule's~Delivery~Cost) + Additional~margin\\]

Example

With the two following rules set up:

  1. If the order contains five or fewer products, shipping is $20

  2. If the order contains more than five products, shipping is $50.




Margin on Rate is `10%` and Additional margin is `$9.00`.

When the first rule is applied, the delivery cost is $31 (20 + (0.1 * 20) + 9). When the second rule is applied, the delivery cost is $64 (50 + (0.1 * 50) + 9).

### Ritira in negozio¶

To configure in-store pickup, select Pickup in store in the Provider field and specify the pickup location in Warehouse.

To invoice the customer for the shipping cost to the pickup location, choose the Get Rate and Create Shipment option in the Integration Level field. Then, pick either the Estimated cost or Real cost radio options in the Invoicing Policy field to decide whether the added shipping charge on the sales order is the precise cost from the shipping carrier.

Vedi anche

[Invoice cost of shipping](setup_configuration/invoicing.html)

### Route on shipping method¶

Optionally, set different warehouse delivery processes for a shipping method by configuring different [routes](daily_operations/use_routes.html) for it.

Example

Configuring multiple routes per shipping method is helpful for adjusting warehouse delivery processes based on:

  * speed (e.g., use [one-step delivery](daily_operations/receipts_delivery_one_step.html) for express shipping, or [two-step](daily_operations/receipts_delivery_two_steps.html) for standard shipping).

  * international shipping (e.g. use [three-step delivery](daily_operations/delivery_three_steps.html) to prepare documents for customs)

  * in-store pickup or home delivery: ship from the central warehouse, or pick from the store’s stock, depending on customer selection.




To set up routes, go to Inventory app ‣ Configuration ‣ Routes. Click New, or select the desired route.

On the route form, in the Applicable On section, tick the Shipping Methods checkbox.

Routes form with the Shipping Methods checkbox ticked.¶

Then, go to Inventory app ‣ Configuration ‣ Shipping Methods, and select the desired shipping method.

On the shipping method form, in the Routes field, select the available fulfillment routes from the drop-down menu.

Nota

If the desired route is not selectable, check that the _Shipping Methods_ option is enabled in the route’s _Applicable On_ section.

By default, most shipping methods are created with two routes available for standard or express delivery.¶

## Aggiungi spedizione¶

Shipping methods can be added to sales orders in the form of delivery products, which appear as individual line items. First, navigate to the desired sales order by going to Sales app ‣ Orders ‣ Orders.

On the sales order, click the Add shipping button, which opens the Add a shipping method pop-up window. Then, choose a Shipping Method from the list.

The Total Order Weight is pre-filled based on product weights (that are defined in the Inventory tab for each product form). Edit the field to specify the exact weight, and then click Add to add the shipping method.

Nota

The amount defined in Total Order Weight overwrites the total product weights defined on the product form.

The shipping cost is added to the _sales order line_ as the Delivery Product detailed on the shipping method form.

Example

`Furniture Delivery`, a delivery product with a fixed rate of `$200`, is added to sales order `S00088`.

> ### Delivery order¶

The shipping method added to the sales order is linked to the shipping carrier details on the delivery order. To add or change the delivery method on the delivery itself, go to the Additional Info tab and modify the Carrier field.

  * [Third-party shipping carriers](setup_configuration/third_party_shipper.html)
  * [Print shipping labels](setup_configuration/labels.html)
  * [Bpost integration](setup_configuration/bpost.html)
  * [DHL integration](setup_configuration/dhl_credentials.html)
  * [FedEx integration](setup_configuration/fedex.html)
  * [Sendcloud integration](setup_configuration/sendcloud_shipping.html)
  * [Starshipit shipping](setup_configuration/starshipit_shipping.html)
  * [UPS integration](setup_configuration/ups_credentials.html)
  * [Zebra label configuration](setup_configuration/zebra.html)
  * [How to cancel a shipping request to a shipper?](setup_configuration/cancel.html)
  * [Shipping cost invoicing](setup_configuration/invoicing.html)
  * [Change shipping label size](setup_configuration/label_type.html)
  * [Multi-package shipments](setup_configuration/multipack.html)
  * [Printable delivery PDFs](setup_configuration/print_on_validation.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](setup_configuration/third_party_shipper.html "Third-party shipping carriers") |
  * [precedente](daily_operations/dropshipping.html "Dropshipping") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Delivery methods


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
  *[API]: Application programming interface
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
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
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