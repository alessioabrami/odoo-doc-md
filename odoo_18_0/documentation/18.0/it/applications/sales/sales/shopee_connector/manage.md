# Shopee order management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../gelato.html "Gelato") |
  * [precedente](setup.html "Shopee Connector configuration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Connettore Shopee](../shopee_connector.html) »
  * Shopee order management



# Shopee order management¶

## Product catalog mapping¶

### New Odoo customers with no existing products¶

If you are starting a new Odoo database and your products are only on Shopee, you can import your Shopee product catalog into Odoo.

  1. **Export Shopee catalog:** Use the _Mass Function_ drop-down to export the product catalog from Shopee, ensuring it includes the Shopee SKUs.

  2. **Import into Odoo:** [Import](../../../essentials/export_import_data.html) the exported catalog into Odoo. During the import process, it is _crucial_ to map the Shopee SKU to the _Internal Reference_ field in Odoo. This field will serve as the link between your Shopee and Odoo products.




### Existing Odoo customers with products already in Odoo¶

If you already have products in your Odoo database, you’ll need to map your Shopee listings to your existing Odoo products.

  1. **Export Shopee catalogs:** Use the _Mass Function_ drop-down to export the product catalog from Shopee (including Shopee SKUs) and [export](../../../essentials/export_import_data.html) your product catalog from Odoo (including _Internal References_).

  2. **Map in a spreadsheet:** Use a spreadsheet to map the products. Match the Shopee SKU from the Shopee export with the corresponding _Internal Reference_ from the Odoo export. Create a column that links the Shopee SKU with the Odoo _Internal Reference_.

  3. **Update Odoo products:** Import the updated spreadsheet back into Odoo. Use the mapping you created in the spreadsheet to update the _Internal Reference_ field of your existing Odoo products with the corresponding Shopee SKU. This establishes the link between your Odoo and Shopee products.




Importante

Product catalog synchronization between Odoo and Shopee is **not automatic**. It is a **manual operation** that you must initiate. The process differs depending on whether your products already exist in Odoo.

## Order synchronization¶

Orders are automatically fetched from Shopee, and synchronized in Odoo, at **regular intervals**.

The synchronization is based on the Shopee orders status: only orders whose status has changed since the last synchronization are fetched from Shopee. This includes changes on Shopee only.

When an order is canceled on Shopee, it will update the order’s status in Odoo. On the other hand, if an order is canceled on Odoo, the change won’t be reflected on Shopee.

For every synchronized order, Odoo creates a sales order and a customer (contact), as long as the customer hasn’t been previously imported from Shopee or doesn’t already exist in the database.

Nota

The principal of the synchronization is to _only fetch orders that needs to be shipped_ (i.e., `SHIPPED`, `CANCEL`, `UNPAID`, `COMPLETED`).

## Force synchronization¶

In order to force the synchronization of an order, whose status has **not** changed since the previous synchronization:

Then, navigate to the Shopee account in Odoo Sales app ‣ Configuration ‣ Shopee ‣ Account ‣ Shop. Modify the date for Last Order Sync under Orders Follow-up.

Be sure to pick a date that occurs prior to the last status change of the desired order to synchronize and save. This will ensure synchronization occurs correctly.

## Manage deliveries in FBM¶

Whenever an FBM (Fulfilled by Merchant) order is synchronized in Odoo, a picking is instantly created in the **Inventory** app, along with a sales order and customer record.

When a picking related to the order is confirmed, you also have to click on Arrange Shipment in your Shopee Seller Account in order to be able to generate and fetch the Shipping Label and Tracking Number.

### Shopee delivery statuses¶

Understanding the different Shopee delivery statuses is crucial for managing your orders effectively. Here’s a breakdown:

  * **Ready to ship:** The seller can now arrange shipment for this order.

  * **Shipment arranged:** The seller has arranged shipment online and received a tracking number from the third-party logistics (3PL) provider.

  * **Shipped:** The parcel has been dropped off at the 3PL location or picked up by the 3PL provider.

  * **Cancelled:** The order has been canceled.

  * **Pickup failed:** The 3PL parcel pickup attempt failed. The seller needs to rearrange shipment, and the rest of the order fulfillment content.




Importante

Unsupported for Non-Shopee Supported Logistics (NSSL)

This feature is not available for NSSL, you have to manually create shipping label and tracking number via the logistics provider’s website/app. Check your region for list of supported logistics (e.g. [Malaysia](https://seller.shopee.com.my/edu/article/388)).

Shopee requires users to provide a tracking reference with each delivery. This is needed to assign a carrier.

If the carrier doesn’t automatically provide a tracking reference, one must be set manually. This rule applies to all Shopee marketplaces.

## Follow deliveries in Odoo¶

For FBM orders, the stock move is automatically created in Odoo by the Shopee connector, thanks to the shipping status of Shopee.

### Order fulfillment process¶

This section describes the process of fulfilling Shopee orders within Odoo, from order creation to inventory updates.

  1. **New order creation:** When a new order is placed on Shopee, it is automatically created in Odoo.

  2. **Arrange shipment on Shopee:** Before the order can be shipped, you **must** arrange the shipment through the Shopee platform itself. This usually involves selecting a shipping provider, generating a shipping label, and scheduling pickup or drop-off. Odoo does _not_ handle the physical shipping arrangements; this is managed entirely within Shopee.

  3. **Fetch Shopee shipping label (delivery note):** Once the shipment is arranged on Shopee, Odoo fetches the generated shipping label (which serves as the delivery note). This label contains crucial information like the tracking number and is essential for printing and attaching to the package. The shipping label is imported into Odoo and associated with the corresponding sales order.

  4. **Validate stock out in Odoo:** After the shipping label is retrieved, you need to validate the stock movement in Odoo. This confirms that the ordered items have left your warehouse or inventory. Validating the stock out will decrease the stock levels in Odoo.

  5. **Inventory update on Shopee:** Finally, Odoo pushes the updated stock levels back to Shopee. This ensures that your Shopee listings reflect the current inventory, preventing overselling and keeping your product availability accurate. This synchronization keeps your Shopee storefront up-to-date with your Odoo inventory.




## Register payments¶

Since customers pay Shopee as an intermediary, creating a dedicated _Bank_ journal (e.g. named `Shopee Payments`), with a dedicated _Bank and Cash_ intermediary account is recommended.

Additionally, as Shopee makes a single weekly or monthly payment, selecting all the invoices linked to a single payment is necessary when registering payments.

To do that, use the appropriate Journal dedicated to Shopee payments, and select Batch Deposit as the Payment Method.

Then, select all the generated payments, and click Actions ‣ Create batch payment ‣ Validate.

Suggerimento

This same action can be performed with vendor bills from Shopee dedicated to fees/commissions.

When the balance is received in the bank account at the end of the week/month, and the bank statements are recorded, credit the Shopee intermediary account by the amount received.

## Analyzing Shopee sales with Odoo’s reporting¶

Odoo’s dashboard consolidates sales data from all your connected sales channels, providing a comprehensive overview of your business performance. To specifically analyze your Shopee sales, you will need to configure sales teams for your Shopee shops. This setup enables you to filter and isolate Shopee sales data within the Odoo dashboard.

### Setting up sales teams for Shopee reporting¶

By default, the Shopee account’s sales team is shared across all of your company’s accounts. To generate separate reports for specific Shopee shops or marketplaces, you’ll need to assign dedicated sales teams.

  1. **Assign a sales team to your Shopee shop:** Navigate to the Shopee account configuration (typically found under Sales ‣ Configuration ‣ Accounts). Within the account details, assign a specific sales team to your Shopee shop.

  2. **Filtering Shopee sales on the dashboard:** Once sales teams are assigned, you can use the dashboard filters to view sales data specifically for your Shopee shops. Select the appropriate sales team to isolate and analyze your Shopee performance.




Vedi anche

  * [Shopee supported features and marketplaces](../shopee_connector.html)

  * [Shopee Connector configuration](setup.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/shopee_connector/manage.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../gelato.html "Gelato") |
  * [precedente](setup.html "Shopee Connector configuration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Connettore Shopee](../shopee_connector.html) »
  * Shopee order management


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
  *[NSSL]: Non-Shopee Supported Logistics