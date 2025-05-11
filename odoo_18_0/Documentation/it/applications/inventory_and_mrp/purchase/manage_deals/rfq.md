# Richieste di preventivo — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blanket_orders.html "Blanket orders") |
  * [precedente](../manage_deals.html "Manage deals") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Richieste di preventivo



# Richieste di preventivo¶

Odoo’s requests for quotation (RFQs) feature in the **Purchase** app standardizes ordering products from multiple vendors with varying prices and delivery times.

RFQs are documents companies send to vendors requesting product pricing. In Odoo, once the vendor approves the RFQ, the purchase order (PO) is confirmed to align on lead times and pricing.

## Configurazione¶

### Prodotto¶

To auto-populate product information and prices on an RFQ, configure products by going to Purchase app ‣ Products ‣ Products. Select an existing product, or create a new one by selecting New. Doing so opens the product form, where sales and purchasing data can be configured.

To configure purchasable products, tick the Purchase checkbox, under the product name. Next, go to the Inventory tab, and enable the Buy route.

Importante

The Inventory tab and routes are only visible if using the [Inventory app](../../inventory.html).

Vedi anche

[Configure product types and track quantities](../../inventory/product_management/configure.html)

### Vendor pricelist¶

In the Purchase tab of the product form, click Add a line to input the vendor and their price, to have this information auto-populate on an RFQ each time the product is listed.

Vedi anche

[Import vendor pricelist](../products/pricelist.html)

Default columns include Quantity, Unit Price, and Delivery Lead Time, but other columns like, Vendor Product Code or Discount (%), can also be enabled.

To enable or disable columns, click the __(additional options) icon on the right side of the header row to reveal a drop-down menu of additional columns that can be added (or removed) from the Purchase tab.

Nota

Alternatively, prices and delivery lead times for existing products can be added by going to Purchase app ‣ Configuration ‣ Vendor Pricelists. Click New in the top-left corner. In the Vendor section of the pricelist form that appears, add the product information as it pertains to the vendor.

## Order products¶

With products and prices configured, follow these steps to create and send RFQs to make purchases for the company.

### RFQ dashboard¶

To get started, navigate to Purchase app ‣ Orders ‣ Requests for Quotation.

The Requests for Quotation dashboard displays an overview of the company’s RFQs, POs, and their status. The top of the screen breaks down all RFQs in the company, as well as individual ones (where the user is the buyer) with a summary of their status.

The top-right corner also provides a report of the company’s recent purchases by total value, lead times, and number of RFQs sent.

Additionally, the dashboard includes buttons for:

  * To Send: orders in the RFQ stage that have not been sent to the vendor.

  * Waiting: RFQs that have been sent by email, and are waiting on vendor confirmation.

  * Late: RFQs or POs where the Order Deadline has passed.




In addition to view options, the Requests for Quotation dashboard provides Filters and Group By options, accessible via the search bar drop-down menu.

Vedi anche

[Cercare, filtrare e raggruppare i record](../../../essentials/search.html)

### Create a new RFQ¶

To create a new RFQ, click the New button on the top-left corner of the Requests for Quotation dashboard to reveal a new PO form.

Start by assigning a Vendor.

The Vendor Reference field points to the sales and delivery order numbers sent by the vendor. This comes in handy once products are received, and the PO needs to be matched to the delivery order.

With the [Purchase Agreements feature](blanket_orders.html) activated, the Blanket Order field appears, referring to long-term purchase agreements on recurring orders with set pricing. To view and configure blanket orders, head to Purchase app ‣ Orders ‣ Purchase agreements.

Importante

The Purchase agreements view only appears if the Blanket Order setting is enabled. To do so, navigate to Purchase app ‣ Configuration ‣ Settings, then tick the Blanket Orders checkbox.

Next, configure an Order Deadline, which is the date by which the vendor must confirm their agreement to supply the products.

Nota

After the Order Deadline is exceeded, the RFQ is marked as late, but the products can still be ordered.

Expected Arrival is automatically calculated based on the Order Deadline and vendor lead time. Tick the checkbox for Ask confirmation to ask the vendor to confirm the shipping date by email.

With the [Storage Locations feature](../../inventory/warehouses_storage/inventory_management/use_locations.html) activated, the Deliver to field appears, which specifies which warehouse operation (set in the **Inventory** app) is used to receive the shipment.

Select the receiving warehouse address here, or select Dropship to indicate that this order is to be shipped directly to the end customer. When Dropship is selected, the Dropship address field is enabled. Contact names auto-populate here from the **Contacts** app.

Importante

The Dropship options only appear if the Dropshipping setting is enabled in the **Inventory** app. To do so, navigate to Inventory app ‣ Configuration ‣ Settings, then tick the Dropshipping checkbox.

Suggerimento

To create RFQs using different currencies, each currency needs to be enabled in the **Invoicing** app settings. See [Foreign currencies](../../../sales/sales/products_prices/prices/currencies.html) to learn more.

#### Products tab¶

In the Products tab, add the products to be ordered. Click Add a product, and type in the product name, or select the item from the drop-down menu.

To create a new product and add it, type the new product name in the Product column, select Create [product name] from the resulting drop-down menu and manually add the unit price. Alternatively, select Create and edit… to be taken to the product form for that new item.

Catalog can also be selected to navigate to a product menu from the chosen vendor. From here, products can be added to the cart.

Nota

To make adjustments to products and prices, access the product form by clicking the __(right arrow) icon that becomes available upon hovering over the Product name.

### Send the RFQ¶

Clicking Send by Email reveals a Compose Email pop-up window, with a Purchase: Request for Quotation template loaded, ready to send to the vendor’s email address (configured in the **Contacts** app).

After crafting the desired message, click Send. Once sent, the RFQ moves to the RFQ Sent stage.

Clicking Print RFQ downloads a PDF of the RFQ.

Vedi anche

[Contatti](../../../essentials/contacts.html)

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

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/purchase/manage_deals/rfq.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blanket_orders.html "Blanket orders") |
  * [precedente](../manage_deals.html "Manage deals") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
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
  *[EDI]: Electronic Data Exchange
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
  *[FBM]: Fulfilled by Merchant
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