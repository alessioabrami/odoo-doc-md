# Discount and loyalty programs — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../commissions.html "Commissione") |
  * [precedente](ewallets_giftcards.html "Use eWallets and gift cards") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Discount and loyalty programs



# Discount and loyalty programs¶

The Odoo _Sales_ , _eCommerce_ , and _Point of Sale_ applications allow users to create discount and loyalty programs that customers can use for online and in-store shopping. These programs offer more varied, public, and time-sensitive pricing options than [pricelists](prices/pricing.html).

## Configure the settings¶

To begin using discount and loyalty programs, navigate to Sales ‣ Configuration ‣ Settings. Under the Pricing heading, activate the Discounts, Loyalty & Gift Card setting by checking the box next to the feature. Finally, click Save to save the changes.

## Configure discount and loyalty programs¶

To create discount and loyalty programs, go to Sales ‣ Products ‣ Discount & Loyalty.

If no discount or loyalty programs have been created yet, Odoo provides a choice of templates to help create the first program. Choose one of the template cards, or click New to create a new program from scratch.

Or, if there are already existing programs, select an existing program to edit it.

Nota

Templates **only** appear when no programs have been created, and they disappear once the first program is created.

Creating or editing a program opens the program form.

The program form contains the following fields:

  * Program Name: Enter the name of the program in this field. The program name is **not** visible to the customer.

  * Program Type: Select the desired program type from the drop-down menu.

  * Currency: Select the currency used for the program.

  * Pricelist: If desired, select a pricelist from the drop-down menu to have this loyalty program applied to a specific pricelist (and customers attached to the pricelist). More than one pricelist can be selected in this field. When a single loyalty program is linked to several pricelists, it makes it viable for different customer segments to have different pricelists, but the _same_ loyalty programs. If this field is left blank, the program applies to everyone, regardless of pricelist.

  * Points Unit: Enter the name of the points used for the Loyalty Cards program (e.g. `Loyalty Points`). The points unit name _is_ visible to the customer. This field is **only** available when the Program Type is set to Loyalty Cards.

  * Start Date: Select the date on which the program becomes valid. Leave this field blank if the program should always be valid and not expire.

  * End Date: Select the date on which the program stops being valid. Leave this field blank if the program should always be valid and not expire.

  * Limit Usage: If desired, tick this checkbox, and enter a number of usages to limit the number of times the program can be used during the validity period.

  * Company: If working in a multi-company database, choose the one company for which the program is available. If left blank, the program is available to all companies in the database.

  * Available On: Select the apps on which the program is available.

  * Website: Select a website on which the program is available. Leave this field blank to make it available on all websites.

  * Point of Sale: Select the point(s) of sale at which the program is available. Leave this field blank to make it available at all PoS.




Nota

The options available on the program form vary depending on the Program Type selected.

All of the existing cards, codes, coupons, etc. that have been generated for the program are accessible through the smart button located at the top of the form.

Nota

In Odoo 17 (and later), when a loyalty card or coupon is associated with a contact in the database, a Loyalty Cards smart button conditionally appears on the contact form.

This smart button **only** appears if a loyalty card or coupon is associated with the contact.

### Program types¶

The different Program Types available on the program form are:

  * Coupons: Generate and share single-use coupon codes that grant immediate access to rewards.

  * Loyalty Cards: When making purchases, the customer accumulates points to exchange for rewards on current and/or future orders.

  * Promotions: Set conditional rules for ordering products, which, when fulfilled, grant access to rewards for the customer.

  * Discount Code: Set codes which, when entered upon checkout, grant discounts to the customer.

  * Buy X Get Y: for every (X) item bought, the customer is granted 1 credit. After accumulating a specified amount of credits, the customer can trade them in to receive (Y) item.

  * Next Order Coupons: Generate and share single-use coupon codes that grant access to rewards on the customer’s next order.




### Regole condizionali¶

Next, configure the Conditional rules that determine when the program applies to a customer’s order.

In the Rules & Rewards tab, click Add next to Conditional rules to add _conditions_ to the program. This reveals a Create Conditional rules pop-up window.

Nota

The options for Conditional rules vary depending on the selected Program Type.

The following options are available for configuring conditional rules:

  * Discount Code: Enter a custom code to be used for the Discount Code program, or use the default one generated by Odoo. This field is only available when the Program Type is set to Discount Code.

  * Minimum Quantity: Enter the minimum number of products that must be purchased in order to access the reward. Set the minimum quantity to at least `1` to ensure that the customer must make a purchase in order to access the reward.

  * Minimum Purchase: Enter the minimum amount (in currency), with tax Included or tax Excluded, that must be spent in order to access the reward. If both a minimum quantity _and_ minimum purchase amount are entered, then the customer’s order must meet both conditions.

  * Products: Select the specific product(s) for which the program applies. Leave this field blank to apply it to all products.

  * Categories: Select the category of products for which the program applies. Choose All to apply it to all product categories.

  * Product Tag: Select a tag to apply the program to products with that specific tag.

  * Grant: Enter the number of points the customer earns per order, per currency spent, or per unit paid (for the Loyalty Cards and Buy X Get Y programs).




Click Save & Close to save the rule and close the pop-up window, or click Save & New to save the rule and immediately create a new one.

### Premi¶

In the Rules & Rewards tab of the program form, click Add next to Rewards to add _rewards_ to the program. This reveals a Create Rewards pop-up window.

Nota

The options for Rewards vary depending on the selected Program Type.

The following options are available for configuring rewards:

  * Reward Type: Select the reward type among Free Product, Discount, and Free Shipping. The other options for reward configuration depend on the Reward Type selected.

    * Free Product:

      * Quantity Rewarded: Select the number of free products rewarded to the customer.

      * Product: Select the product given for free as a reward. Only one product can be selected.

      * Product Tag: Select a tag to further specify the free product eligible for the reward.

    * Discount:

      * Discount: Enter the discounted amount in either percentage, currency per point, or currency per order. Then, select whether the discount applies to the entire Order, only the Cheapest Product on the order, or only Specific Products.

      * Max Discount: Enter the maximum amount (in currency) that this reward may grant as a discount. Leave this field at `0` for no limit.

    * Free Shipping:

      * Max Discount: Enter the maximum amount (in currency) that this reward may grant as a discount. Leave this field at `0` for no limit.

  * In exchange of: Enter the number of points required to exchange for the reward (for the Loyalty Cards and Buy X Get Y programs).

  * Description on order: Enter the description of the reward, which is displayed to the customer upon checkout.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/products_prices/loyalty_discount.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../commissions.html "Commissione") |
  * [precedente](ewallets_giftcards.html "Use eWallets and gift cards") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Discount and loyalty programs


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