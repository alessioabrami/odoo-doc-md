# Listini prezzi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](currencies.html "Foreign currencies") |
  * [precedente](../prices.html "Manage your pricing") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your pricing](../prices.html) »
  * Listini prezzi



# Listini prezzi¶

A _pricelist_ is a method of dynamic pricing that applies a list of prices (or price rules) to adjust sales prices. This adjustment can apply to specific customers, customer groups, sales orders, time periods, etc., and is useful for creating pricing strategies and optimizing sales margins.

Odoo **Sales** has a useful pricelist feature that can be tailored to fit any unique pricing strategy. Pricelists suggest certain prices, but they can always be overridden on the sales order.

## Configurazione¶

To enable pricelists in the Odoo **Sales** app, first navigate to Sales app ‣ Configuration ‣ Settings. In the Pricing section, tick the checkbox next to the Pricelists feature, and click Save to save all changes.

After activating and saving the Pricelists feature, the Settings page reloads. From here, either select the __ Pricelists link (beneath the Pricelists feature on the Settings page), or navigate to Sales app ‣ Products ‣ Pricelists.

Either option reveals the Pricelists page, in which pricelists can be created and/or modified at any time.

Importante

If there is no specific pricelist configured on a sales quotation, the Default pricelist is applied.

Nota

The Selectable column is only applicable to Odoo **eCommerce**. This option allows website visitors to choose a pricelist when shopping in your **eCommerce** website.

Nota

In Odoo 17 (and above), you are _not required_ to enter a pricelist in the Pricelist field on a sales quotation form in order to confirm it (i.e. turn it into a sales order).

The chatter section is available on pricelist forms, which allows you to add notes and communications on each pricelist page.

### Creating and editing pricelists¶

From the Pricelists page, either select the pricelist to edit, or click New to create a new pricelist, which reveals a blank pricelist form that can be configured in a number of different ways.

When creating a new pricelist, start by adding a name for the pricelist at the blank field at top of the form. Next, select which Currency should be used.

If working in a multi-company environment, select which company this pricelist should apply to in the Company field. If this field is left blank, the pricelist is automatically applied to all companies in the database.

If working in a multinational company, select the countries where this pricelist will apply under the Country Groups column.

### Price Rules tab¶

In the Price Rules tab, each line creates a new record that will implement customized pricing to the sales order where the pricelist is applied. To create a new price rule, click on Add a line, which opens a new pricelist rules form.

Then, select whether to apply this set of rules to a Product or Category.

From here, there are several configuration options:

  * Product: If selected in the Apply To field, use this field to choose one or more products to which this pricelist will apply.

  * Category: Select one or more product categories to which this pricelist will apply.

  * Price Type: Select whether the specialized pricing will fall under Discount, Formula, or Fixed Price. Depending on the price type, there will be additional configurations on how to apply the pricelist.

    * Discount: Enter the percentage to be discounted. A mark-up can be configured by using a negative value in this field.

Importante

If a pricelist is applied to a sales quotation with the discount Price Type set as Discount, the discount will visible to the customer.

    * Formula: Calculate the pricelist rules based the following configuration:

      * Discount: Percentage discount to be applied. Negative values can be entered to increase prices.

Importante

If a pricelist is applied to a sales quotation with the discount Price Type set as Formula, the discount will _not_ be visible to the customer.

      * Round off to: Numerical value to act as round-off multiple, to be applied after discount. The rounding method sets the price so that it is a multiple of the value in this field.

Nota

Rounding is applied _after_ the discount and _before_ the extra fee.

        * Extra Fee: Fixed amount to be added or subtracted once Discount and Round off to have been applied.

        * Fixed Price: Enter fixed price for this pricelist. When applied, all product lines in the quotation form will be updated to this price.

  * Min Qty: Specify the minimum quantity of selected products for this pricelist to apply.

  * Validity Period: Specify the start and end date during which this pricelist can be applied to quotations.




Example

To formulate a 100% markup (or two times the price of the product), with a $5 minimum margin, set the Based price field to Sales Price and the Discount to `-100`. This is often seen in retail situations.

Example

To apply 20% discounts, with prices rounded up to 9.99, set the Based on field to Sales Price, the Discount field to `20`, the Extra Fee field to `-0.01`, and the Rounding Method field to `10`.

Suggerimento

To have prices that end in 9.99, set the Rounding Method to `10` and the Extra Fee to `-0.01`.

### Recurring Prices tab¶

Time-based rules are used specifically with subscription products. Be sure to check out the Odoo [Subscriptions](../../../subscriptions.html) documentation for more information.

In the Recurring Prices tab, pricelists are configured with the same options as in the Price Rules tab, with additional columns for Product Variants add Recurring Plan.

Product Variants are configured under products that have one or more values, such as color, size, etc. Once a product has been selected under the Products Tab, if applicable, select the desired product variants to be included in the price rule.

Then, select the blank field in the Recurring Plan column to reveal a drop-down menu of pre-designated recurrence periods (e.g. `Monthly`, `Quarterly`, `Weekly`, etc.).

New recurrence periods can also be created from this column. To do so, type in the name for the new Recurring Plan, then select Create from the resulting drop-down menu to create the time period, which can be edited later. Alternatively, select Create and edit… to reveal a Create Recurring Plan pop-up form. From this pop-up form, the new recurrence period can be configured, with specific Details, Self-Service, and Pricing options. When the configurations are complete, click the Save & Close button.

Lastly, add the desired price for this recurring price rule in the Recurring Price column.

Vedi anche

[Abbonamenti](../../../subscriptions.html)

### Rental rules tab¶

Price rules can be configured for [rental products](../../../rental.html) under the Rental rules tab, using the same methodology as the Price Rules and Recurring Prices tabs.

To add a rental rule, click Add a line, and select a desired product in the Products column. Then, select any specific Variants, if necessary.

Next, designate a Period of time for the rental rule (e.g. `Daily`, `Hourly`, etc.).

Lastly, configure a Price for the rental rule in the respective column.

### Ecommerce Tab¶

Under the Ecommerce tab, price rules can be configured for products sold on an [Ecommerce website](../../../../websites/ecommerce/products.html).

To enable the pricelist to be visible, select the target website in the Website field.

The Selectable can be enabled to allow the customer to choose this pricelist.

Finally, promotional and loyalty codes can be added to the E-commerce Promotional Code field.

Tick the Selectable checkbox to have this pricelist as a selectable option for customers to choose as they shop. If the Selectable box is left unticked, customers **cannot** select this pricelist for themselves.

Lastly, there is the option to add an E-commerce Promotional Code. To add a code, type in the desired promo code that, when entered during the checkout process, applies the pricelist to the customer, even if the customer does not fall into the previously-specified criteria.

## Customer pricelist application¶

While the default pricelist applied to any customer is the Public Pricelist, Odoo provides the opportunity to directly apply a different pricelist to customers on their contact form.

To do that, open the desired customer’s contact form, either by navigating to Sales app ‣ Orders ‣ Customers and selecting the customer from the main Customers page, or by clicking on the customer’s name on a sales order.

On the desired customer’s contact form, under the Sales & Purchase tab, in the Sales section, designate what pricelist should be applied to this specific customer from the drop-down menu in the Pricelist field.

Nota

When a customer is added to the database, the default pricelist is automatically applied to them. There is **no way** to have a blank _Pricelist_ field on a contact form. Even if that field is left blank, the default pricelist appears when that contact form is opened again.

However, when that contact is added to a quotation, and the _Pricelist_ field is auto-populated (based on the information from their contact form), that predetermined pricelist can be removed from the _Pricelist_ field, and the quotation can still be confirmed, and subsequently, turned into a sales order.

### Condizioni¶

At the bottom of the Create Pricelist Rules pop-up form is the Conditions section.

Here, start by selecting one of the options in the Apply On field:

  * All Products: the advanced pricelist rule will be applied to all products.

  * Product Category: the advanced pricelist rule will be applied to a specific category of products.

  * Product: the advanced pricelist rule will be applied to a specific product.

  * Product Variant: the advanced pricelist rule will be applied to a specific product variant.




If any of those options, apart from All Products, are selected, a new option-specific field appears, in which the specific Product Category, Product, or Product Variant must be chosen.

Then, select a minimum quantity to be applied to the advanced pricelist rule in the Min. Quantity field. Lastly, select a range of dates for the pricelist item validation in the Validity field.

Once all configurations are complete, either click Save & Close to save the advanced pricelist rule, or click Save & New to immediately create another advanced pricelist rule on a fresh form.

Nota

If a price rule is set for a particular product, and another one for its product category, Odoo takes the rule of the product itself.

Vedi anche

  * [Foreign currencies](currencies.html)

  * [Price management](../../../../websites/ecommerce/products/price_management.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/products_prices/prices/pricing.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](currencies.html "Foreign currencies") |
  * [precedente](../prices.html "Manage your pricing") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your pricing](../prices.html) »
  * Listini prezzi


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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