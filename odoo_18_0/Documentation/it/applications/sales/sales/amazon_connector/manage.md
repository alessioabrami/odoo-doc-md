# Amazon order management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shopee_connector.html "Connettore Shopee") |
  * [precedente](setup.html "Amazon Connector configuration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon order management



# Amazon order management¶

## Order synchronization¶

Orders are automatically fetched from Amazon, and synchronized in Odoo, at regular intervals.

The synchronization is based on the Amazon status: only orders whose status has changed since the last synchronization are fetched from Amazon. This includes changes on either end (Amazon or Odoo).

For _FBA_ (Fulfilled by Amazon), only _Shipped_ and _Cancelled_ orders are fetched.

For _FBM_ (Fulfilled by Merchant), the same is done for _Unshipped_ and _Cancelled_ orders. For each synchronized order, a sales order and customer are created in Odoo (if the customer is not already registered in the database).

Nota

When an order is cancelled in Amazon, and was already synchronized in Odoo, the corresponding sales order is automatically cancelled in Odoo.

## Force synchronization¶

In order to force the synchronization of an order, whose status has **not** changed since the previous synchronization, start by activating the [developer mode](../../../general/developer_mode.html#developer-mode). This includes changes on either end (Amazon or Odoo).

Then, navigate to the Amazon account in Odoo (Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Accounts), and modify the date under Orders Follow-up ‣ Last Order Sync.

Be sure to pick a date that occurs prior to the last status change of the desired order to synchronize and save. This will ensure synchronization occurs correctly.

Suggerimento

To immediately synchronize the orders of an Amazon account, switch to [developer mode](../../../general/developer_mode.html#developer-mode), head to the Amazon account in Odoo, and click Sync Orders. The same can be done with pickings by clicking Sync Pickings.

## Manage deliveries in FBM¶

Whenever an FBM (Fulfilled by Merchant) order is synchronized in Odoo, a picking is instantly created in the _Inventory_ app, along with a sales order and customer record. Then, decide to either ship all the ordered products to the customer at once, or ship products partially using backorders.

When a picking related to the order is confirmed, a notification is then sent to Amazon, who, in turn, notifies the customer that the order (or a part of it) is on its way.

Importante

Amazon requires users to provide a tracking reference with each delivery. This is needed to assign a carrier.

If the carrier doesn’t automatically provide a tracking reference, one must be set manually. This rule applies to all Amazon marketplaces.

Suggerimento

If the chosen carrier isn’t supported by Odoo, a carrier with the same name can still be created (e.g. create a carrier named `easyship`). The name used is **not** case sensitive, but be mindful to avoid typos. If there are typos, Amazon will **not** recognize them. Next, create a delivery carrier named `Self Delivery` to inform Amazon that the user will make the deliveries. Even with this route, a tracking reference still **must** be entered. Remember, the customer is notified by email about the delivery, and the carrier, along with the tracking reference, are displayed in the email to the customer.

Vedi anche

[Third-party shipping carriers](../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html)

### Manage errors when synchronizing deliveries¶

Sometimes, Amazon can fail to correctly process all the information sent by Odoo. In this case, Odoo sends an email listing all the shipments that failed and the errors Amazon sent with them. In addition, these shipments are flagged with a Synchronization with Amazon failed tag.

Usually, the error can be corrected directly in the Amazon backend or in Odoo. If the problem is corrected in Odoo, synchronize the shipment again using the Retry Amazon Sync button.

Nota

It might happen that Odoo receives a notification from Amazon saying that some delivery information was not processed, but without specifying which shipments were affected. In that case, all the shipments in an unknown state will be treated as if they failed to synchronize. Once Odoo receives a notification from Amazon saying that a shipment was processed, its tag will change to Synchronized with Amazon. To speed up this process, on your Amazon account, click on Sync Orders to manually synchronize these orders, or click on Recover Order and enter the relevant Amazon Order Reference.

## Follow deliveries in FBA¶

When an FBA (Fulfilled by Amazon) order is synchronized in Odoo, a stock move is recorded in the _Inventory_ app for each sales order item. That way, it’s saved in the system.

Inventory managers can access these stock moves by navigating to Inventory app ‣ Reporting ‣ Moves History.

For FBA orders, the stock move is automatically created in Odoo by the Amazon connector, thanks to the shipping status of Amazon. When sending new products to Amazon, the user should manually create a picking (delivery order) to transfer these products from their warehouse to the Amazon location.

Suggerimento

To follow _Amazon (FBA)_ stock in Odoo, make an inventory adjustment after replenishing stock. An automated replenishment from reordering rules can also be triggered on the Amazon location.

The Amazon location is configurable by accessing the Amazon account managed in Odoo. To access Amazon accounts in Odoo navigate to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Accounts.

All accounts of the same company use the same Amazon location, by default. However, it is possible to follow the stock filtered by marketplace.

To do that, first remove the marketplace, where the desired stock to follow separately can be found, from the list of synchronized marketplaces, which can be found by navigating to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Accounts.

Next, create another registration for this account, and remove all marketplaces— **except** the marketplace this is desired to be isolated from the others.

Lastly, assign another stock location to the second registration of the account.

## Invoice and register payments¶

### Emetti fatture¶

Due to Amazon’s policy of not sharing customer email addresses, it is **not** possible to send invoices directly to Amazon customers from Odoo. However, it **is** possible to manually upload the generated invoices from Odoo to the Amazon back-end.

Additionally, for B2B clients, it is currently required to manually retrieve VAT numbers from the Amazon back-end **before** creating an invoice in Odoo.

### Register payments¶

Since customers pay Amazon as an intermediary, creating a dedicated _Bank_ journal (e.g. named `Amazon Payments`), with a dedicated _Bank and Cash_ intermediary account is recommended.

Additionally, as Amazon makes a single monthly payment, selecting all the invoices linked to a single payment is necessary when registering payments.

To do that, use the appropriate Journal dedicated to Amazon payments, and select Batch Deposit as the Payment Method.

Then, select all the generated payments, and click Actions ‣ Create batch payment ‣ Validate.

Suggerimento

This same action can be performed with vendor bills from Amazon dedicated to commissions.

When the balance is received in the bank account at the end of the month, and the bank statements are recorded, credit the Amazon intermediary account by the amount received.

## Follow Amazon sales in sales reporting¶

On the Amazon account profile in Odoo, a sales team is set under the Order Follow-up tab.

This gives quick access to important metrics related to sales reporting. By default, the Amazon account’s sales team is shared between all of the company’s accounts.

If desired, the sales team on the account can be changed for another, in order to perform a separate reporting for the sales of this account.

Suggerimento

It is also possible to perform reporting on a per-marketplace basis.

First, remove the desired marketplace from the list of synchronized marketplaces.

To access the list of synchronized marketplaces in Odoo, navigate to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Accounts.

Then, create another registration for this account, and remove all other marketplaces **except** the one to isolate.

Lastly, assign another sales team to one of the two registrations of the account.

Vedi anche

  * [Amazon Connector features](features.html)

  * [Amazon Connector configuration](setup.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/amazon_connector/manage.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shopee_connector.html "Connettore Shopee") |
  * [precedente](setup.html "Amazon Connector configuration") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon order management


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