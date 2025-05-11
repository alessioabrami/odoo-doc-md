# Richieste di preventivo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blanket_orders.html "Blanket orders") |
  * [precedente](../manage_deals.html "Manage deals") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Richieste di preventivo



# Richieste di preventivo¶

Odoo’s requests for quotation (RFQs) feature in the **Purchase** app standardizes ordering products from multiple vendors with varying prices and delivery times.

RFQs are documents companies send to vendors requesting product pricing. In Odoo, once the vendor approves the RFQ, the purchase order (PO) is confirmed to align on lead times and pricing.

## Configurazione¶

### Prodotto¶

To auto-populate product information and prices on an RFQ, configure products by going to Purchase app ‣ Products ‣ Products. Select an existing product, or create a new one by selecting New. Doing so opens the product form, where various sales and purchasing data can be configured.

To configure purchasable products, tick the Can be purchased checkbox, under the product name. Then, go to the Inventory tab, and enable the Buy route.

### Vendor pricelist¶

In the Purchase tab of the product form, input the vendor and their price, to have this information auto-populate on an RFQ each time the product is listed.

Vedi anche

[Import vendor pricelist](../products/pricelist.html)

Default columns include Quantity, Price, and Delivery Lead Time, but other columns like, Product Variant or Discounts, can also be enabled.

To enable or disable columns, click the __(additional options) icon on the right side of the header row to reveal a drop-down menu of additional columns that can be added (or removed) from the Purchase tab.

Nota

Alternatively, prices and delivery lead times for existing products can be added in bulk by going to Purchase app ‣ Configuration ‣ Vendor Pricelists. Click New in the top-left corner. In the Vendor section of the pricelist form that appears, add the product information as it pertains to the vendor.

## Order products¶

With products and prices configured, follow these steps to create and send RFQs to make purchases for the company.

### RFQ dashboard¶

To get started, navigate to Purchase app ‣ Orders ‣ Requests for Quotation.

The Requests for Quotation dashboard displays an overview of the company’s RFQs, POs, and their status. The top of the screen breaks down all RFQs in the company, as well as individual ones (where the user is the buyer) with a summary of their status.

The top-right corner also provides a quick report of the company’s recent purchases by total value, lead times, and number of RFQs sent.

Additionally, the dashboard includes buttons for:

  * To Send: orders in the RFQ stage that have not been sent to the vendor.

  * Waiting: RFQs that have been sent by email, and are waiting on vendor confirmation.

  * Late: RFQs or POs where the Order Deadline has passed.




In addition to various view options, the Requests for Quotation dashboard provides Filters and Group By options, accessible via the search bar drop-down menu.

Vedi anche

[Cercare, filtrare e raggruppare i record](../../../essentials/search.html)

### Create new RFQ¶

To create a new RFQ, click the New button on the top-left corner of the Requests for Quotation dashboard to reveal a new PO form.

Start by assigning a Vendor.

The Vendor Reference field points to the sales and delivery order numbers sent by the vendor. This comes in handy once products are received, and the PO needs to be matched to the delivery order.

The Blanket Order field refers to long-term purchase agreements on recurring orders with set pricing. To view and configure blanket orders, head to Purchase app ‣ Orders ‣ Purchase agreements.

The Currency can be changed, if purchasing products from a vendor in another country.

Next, configure an Order Deadline, which is the date by which the vendor must confirm their agreement to supply the products.

Nota

After the Order Deadline is exceeded, the RFQ is marked as late, but the products can still be ordered.

Expected Arrival is automatically calculated based on the Order Deadline and vendor lead time. Tick the checkbox for Ask confirmation to ask for signage at delivery.

With the [Storage Locations feature](../../inventory/warehouses_storage/inventory_management/use_locations.html) activated, the Deliver to field appears, with options for the order shipment.

Select the receiving warehouse address here, or select Dropship to indicate that this order is to be shipped directly to the end customer. When Dropship is selected, the Dropship address field is enabled. Contact names auto-populate here from the **Contacts** app.

#### Products tab¶

In the Products tab, add the products to be ordered. Click Add a product, and type in the product name, or select the item from the drop-down menu.

To create a new product and add it, type the new product name in the Product column, select Create [product name] from the resulting drop-down menu, and manually add the unit price. Or, select Create and edit… to be taken to the product form for that new item.

Catalog can also be selected to navigate to a product menu from the chosen vendor. From here, products can be added to the cart.

Nota

To make adjustments to products and prices, access the product form by clicking the __(right arrow) icon that becomes available upon hovering over the Product name.

### Send RFQ¶

Clicking Send by Email reveals a Compose Email pop-up window, with a Purchase: Request for Quotation template loaded, ready to send to the vendor’s email address (configured in the **Contacts** app).

After crafting the desired message, click Send. Once sent, the RFQ moves to the RFQ Sent stage.

Clicking Print RFQ downloads a PDF of the RFQ.

### Conferma ordine¶

Clicking Confirm Order directly transforms the RFQ into an active PO.

Suggerimento

Odoo tracks communications on each order through the chatter of the PO form. This shows the emails sent between the user and the contact, as well as any internal notes and activities. Messages, notes, and activities can also be logged on the chatter.

Once an RFQ is confirmed, it creates a PO.

On the new PO, the Order Deadline field changes to Confirmation Date, which displays the date and time the user confirmed the order.

Depending on the user’s chosen configuration in the **Purchase** app settings, a _vendor bill_ is created once products have been ordered or received. For more information, refer to the documentation on [managing vendor bills](manage.html).

Nota

After an order is placed, clicking Receive Products records the reception of new products into the database.

Nota

With the **Inventory** app installed, confirming a PO automatically creates a receipt document, with the product information and expected arrival dates automatically populated.

Vedi anche

[Manage vendor bills](manage.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/manage_deals/rfq.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blanket_orders.html "Blanket orders") |
  * [precedente](../manage_deals.html "Manage deals") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Richieste di preventivo


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
  *[MO]: manufacturing order
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