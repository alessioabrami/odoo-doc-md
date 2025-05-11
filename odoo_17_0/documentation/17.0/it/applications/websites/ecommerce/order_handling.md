# Order handling — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_accounts.html "Customer accounts") |
  * [precedente](shipping.html "Spedizione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Order handling



# Order handling¶

When a customer orders on your eCommerce, there are **three** record types required to be handle in Odoo:

  * Sales orders;

  * Delivery orders;

  * Invoices & legal requirements.




## Sales orders¶

### Order and payment status¶

The first step when a customer adds a product to his cart is the creation of a quotation. Orders can be managed either from the **Website** or [Sales](../../sales/sales.html) app. eCommerce orders can automatically be assigned to a specific sales team by going to Website ‣ Configuration ‣ Settings. In the **Shop - Checkout Process** section, select a Sales Team or Salesperson to handle eCommerce orders.

Orders can be found under Website ‣ eCommerce ‣ Orders/Unpaid Orders. Each order goes through a different status:

  * **Quotation** : a new product is added to the cart, but the customer has _not_ gone through the checkout process yet;

  * **Quotation sent** : the customer has gone through the checkout process and confirmed the order, but the payment is not yet confirmed;

  * **Order** : the customer has gone through the checkout process, confirmed the order, and the payment is received.




### Abandoned cart¶

An **abandoned cart** represents an order for which the customer did **not finish** the checkout confirmation process. For these orders, it is possible to send an **email reminder** to the customer automatically. To enable that feature, go to Website ‣ Configuration ‣ Settings and in the Email & Marketing section, enable Automatically send abandoned checkout emails. Once enabled, you can set the **time-lapse** after which the email is sent and customize the **email template** used.

Nota

For abandoned cart emails, the customer must either have entered their contact details during the checkout process; or be logged-in when they added the product to their cart.

## Delivery orders¶

### Delivery flow¶

Once a quotation has been confirmed, a delivery order is automatically created. The next step is to process this delivery.

Packing eCommerce orders usually requires picking the product, preparing the packaging, printing the shipping label(s) and shipping to the customer. Depending on the number of orders, strategy, or resources, those steps can be considered as one or multiple actions in Odoo.

An automatic email can be sent to the customer when the transfer status in Odoo is “done”. To do so, enable the feature in the settings of the [Inventory](../../inventory_and_mrp/inventory.html) app.

Nota

If customers are allowed to pay when picking up their order in stores or by wire transfer, the quotation is **not** be confirmed and the stock is **not** be reserved. Orders must be confirmed manually to reserve products in stock.

Vedi anche

  * [Shipping cost invoicing](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/invoicing.html)

  * [Print shipping labels](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/labels.html)

  * [Multi-package shipments](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/multipack.html)




### Returns and refunds¶

Customers can only return an order through an online form. It may not be possible to return products depending on the return strategy or type of product.

Full refunds can be directly sent to customers from within the order interface. A refund-compatible payment provider needs to be enabled first.

Vedi anche

  * [Returns and refunds](../../sales/sales/products_prices/returns.html)

  * [After-Sales services](../../services/helpdesk/advanced/after_sales.html)

  * [Online payments](../../finance/payment_providers.html)




## Invoice and legal requirements¶

The final step of an ecommerce order is to generate the invoice and send it to the customer. Depending on the type of business (B2B or B2C), an invoice can either be generated automatically (B2B) or on demand of the customer (B2C). This process can be automated if (and when) the online payment is confirmed.

To automate invoicing, go to Website ‣ Configuration ‣ Settings and in the Invoicing section, enable Automatic Invoice.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/ecommerce/order_handling.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_accounts.html "Customer accounts") |
  * [precedente](shipping.html "Spedizione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Order handling


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[CSV]: Valori separati da virgola
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement