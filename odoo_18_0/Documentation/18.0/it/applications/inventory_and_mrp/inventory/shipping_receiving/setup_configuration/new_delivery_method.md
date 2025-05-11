# Add a new delivery method — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](third_party_shipper.html "Third-party shipping carriers") |
  * [precedente](../setup_configuration.html "Delivery methods") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Add a new delivery method



# Add a new delivery method¶

The _Delivery Methods_ setting adds the option of calculating the cost of shipping on sales orders and e-commerce shopping carts. The shipping cost can then be added to a sales order as a delivery product, and the shipping details can be added to the delivery order.

Vedi anche

[Delivery methods](../setup_configuration.html)

## Configurazione¶

To configure delivery methods, go to Inventory app ‣ Configuration ‣ Delivery Methods.

Nota

If the Delivery Methods option is not available from the Configuration drop-down menu, verify whether the feature is enabled by following these steps:

  1. Go to Inventory app ‣ Configuration ‣ Settings.

  2. Scroll to the Shipping section and enable the Delivery Methods feature by checking the corresponding checkbox.




On the Delivery Methods page, add a method by clicking New. Doing so opens a form to provide details about the shipping provider, including:

  * Delivery Method (_Required field_): the name of the delivery method (e.g. `flat-rate shipping`, `same day delivery`, etc.).

  * Website: configure shipping methods for an **eCommerce** page. Select the applicable website from the drop-down menu, or leave it blank to apply the method to all web pages.

  * Provider (_Required field_): choose the delivery service, like FedEx, if using a [third-party carrier](third_party_shipper.html#inventory-shipping-third-party). Ensure the integration with the shipping carrier is properly installed and select the provider from the drop-down menu. For more details on configuring custom shipping methods, such as fixed price or based on rules options, refer to their respective sections below.

  * Company: If the shipping method should apply to a specific company, select it from the drop-down menu. Leave the field blank to apply the method to all companies.

  * Routes: select the applicable routes to define different delivery methods, such as standard or express shipping, based on varying lead times. For more information, jump to the Set routes on shipping method section.

  * Delivery Product (_Required field_): the product listed on the [sales order line](../setup_configuration.html#inventory-shipping-sales-order) as the delivery charge.

  * Free if order amount is above: checking this box enables free shipping if the customer spends above the specified amount.

  * Tracking Link: This option adds a link to the portal so the customer can track their delivery. When a custom carrier is added in a delivery order, the tracking button is enabled, and the link directs to the tracking portal with that URL.




Use the Availability tab to define conditions for the delivery method based on the order’s content or destination:

  * Countries: Specify one or more countries where the method is available.

  * Max Weight: Set a maximum weight; the method is only available for orders below this limit.

  * Max Volume: Set a maximum volume; the method is only available for orders below this limit.

  * Must Have Tags: The method is available only if at least one product in the order has one of these tags.

  * Excluded Tags: The method is unavailable if at least one product in the order has one of these tags.




For examples on how to configure specific shipping methods, refer to the sections below.

## Prezzo fisso¶

To configure a shipping price that is the same for all orders, go to Inventory app ‣ Configuration ‣ Delivery Methods. Then, click New, and on the shipping method form, set the Provider to the Fixed Price option. Selecting this option makes the Fixed Price field become available, which is where the fixed rate shipping amount is defined.

To enable free shipping if the amount of the order exceeds a specified amount, check the box Free if order amount is above and fill in the amount.

Example

To set up `$20` flat-rate shipping that becomes free if the customer spends over `$100`, fill in the following fields:

  * Delivery Method: `Flat-rate shipping`

  * Provider: Fixed Price

  * Fixed Price: `$20.00`

  * Free if order amount is above: `$100.00`

  * Delivery Product: `[SHIP] Flat`




## Based on rules¶

To calculate the price of shipping based on pricing rules, set the Provider field to the Based on Rules option. Optionally, adjust Margin on Rate and Additional margin to include additional shipping costs.

### Create pricing rules¶

Navigate to the Pricing tab and click Add a line. Doing so opens the Create Pricing Rules window, where the Condition related to the product weight, volume, price, or quantity is compared to a defined amount to calculate the Delivery Cost.

Once finished, click either Save & New to add another rule, or Save & Close.

Example

To charge customers $20 in shipping for orders with five or fewer products, set the Condition to `Quantity <= 5.00`, and the Delivery Cost to `$20`.

To restrict shipping to specific destinations on the **eCommerce** website, in the shipping method form, navigate to the Destination Availability tab and define the Countries, States, and Zip Prefixes. Leave these fields empty if all locations apply.

### Calculate delivery cost¶

Shipping cost is the Delivery cost specified in the rule that satisfies the Condition, plus any extra charges from the Margin on rate and Additional margin.

\\[Total = Rule's~Delivery~Cost + (Margin~on~rate \times Rule's~Delivery~Cost) + Additional~margin\\]

Example

With the two following rules set up:

  1. If the order contains five or fewer products, shipping is $20

  2. If the order contains more than five products, shipping is $50.




Margin on Rate is `10%` and Additional margin is `$9.00`.

When the first rule is applied, the delivery cost is $31 (20 + (0.1 * 20) + 9). When the second rule is applied, the delivery cost is $64 (50 + (0.1 * 50) + 9).

## Route on shipping method¶

Optionally, set different warehouse delivery processes for a shipping method by configuring different [routes](../daily_operations/use_routes.html) for it.

Example

Configuring multiple routes per shipping method is helpful for adjusting warehouse delivery processes based on:

  * speed (e.g., use [one-step delivery](../daily_operations/receipts_delivery_one_step.html) for express shipping, or [two-step](../daily_operations/receipts_delivery_two_steps.html) for standard shipping).

  * international shipping (e.g. use [three-step delivery](../daily_operations/delivery_three_steps.html) to prepare documents for customs)

  * in-store pickup or home delivery: ship from the central warehouse, or pick from the store’s stock, depending on customer selection.




To set up routes, go to Inventory app ‣ Configuration ‣ Routes. Click New, or select the desired route.

On the route form, in the Applicable On section, tick the Shipping Methods checkbox.

Routes form with the Shipping Method checkbox ticked.¶

Then, go to Inventory app ‣ Configuration ‣ Delivery Methods, and select the desired shipping method.

On the shipping method form, in the Routes field, select the available fulfillment routes from the drop-down menu.

Nota

If the desired route is not selectable, check that the _Shipping Methods_ option is enabled in the route’s _Applicable On_ section.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](third_party_shipper.html "Third-party shipping carriers") |
  * [precedente](../setup_configuration.html "Delivery methods") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Add a new delivery method


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
  *[RfQ]: request for quotation
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