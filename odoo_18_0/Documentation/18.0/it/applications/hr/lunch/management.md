# Lunch management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../marketing.html "Marketing") |
  * [precedente](user-accounts.html "Manage user accounts") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Lunch management



# Lunch management¶

In Odoo’s _Lunch_ application, it is required to have someone manage the orders, vendors, and products. In addition, someone must be responsible for the orders, and notifying employees when their orders have arrived. This can be the same person.

Orders can be cancelled, sent to the vendor, confirmed upon arrival, and employees can be notified, either from the Today’s Orders dashboard, or the Control Vendors dashboard.

To manage the _Lunch_ app, users need the appropriate Administrator rights. These can be set by navigating to the Settings app and selecting Manage Users. Then, click on the desired user to view their access rights.

For more information on access rights, refer to the [Access rights](../../general/users/access_rights.html) documentation.

Nota

Only users with administration rights are able to view the Manager and Configuration menus in the _Lunch_ application.

## Ordini di Oggi¶

To view and manage the orders for the day, navigate to Lunch app ‣ Manager ‣ Today’s Orders. All orders for the day are presented in a list view on the Today’s Orders dashboard, with a filter for Today, and grouped by Vendor, by default.

The following information appears in the list:

  * Order Date: the date the order was placed.

  * Vendor: the vendor the product is being ordered from.

  * Product: the specific product ordered.

  * Extras: any extras selected for the product.

  * Notes: any information needed to be sent to the vendor.

  * User: the user who ordered the product.

  * Lunch Location: where the product is set to be delivered.

  * Price: the total price for the product, including all extras.

  * Status: the current status of the product.

  * Company: the company under which the order was placed. This only appears in a multi-company database.




### Cancel orders¶

All users can cancel an order, not just managers of the _Lunch_ app.

To cancel an order from a vendor, individual products **must** be cancelled one at a time.

On the Today’s Orders dashboard, a ✖️ Cancel button is shown at the far-right of each product line that can be cancelled. Click the ✖️ Cancel button to cancel the order for that individual product.

Nota

Only products with a red Status tag of Ordered can be cancelled.

### Send orders¶

The first step in managing the _Lunch_ app is to send the orders to the vendors.

When orders are ready to be sent, the manager responsible for sending orders **must** send the orders to the vendor, outside of the database (call, online order, etc.).

Once orders have been placed with the vendors, click the Send Orders button that appears next to each vendor’s name and phone number.

Once sent, the Send Orders button changes to a Confirm Orders button, and the Status column is updated from red Ordered tags to blue Sent tags, indicating the order has been sent to the vendor. Users who have placed orders in the _Lunch_ app rely on the Status tags to track their orders.

### Confirm orders¶

After orders have been sent to the vendor, the next step is to confirm the orders after they have been delivered.

On the Today’s Orders dashboard, click the Confirm Orders button that appears next to the vendor’s name and phone number.

Once confirmed, the Confirm Orders button disappears, and the Status column is updated from blue Sent tags to green Received tags, indicating the vendor has delivered the orders.

In addition, the ✖️ Cancel button at the end of each product line changes to a ✉️ Send Notification button.

If needed, instead of confirming all of the individual products from a vendor, individual products can be confirmed one at a time. To confirm an individual product, click the ✔️ Confirm button at the end of the individual product line. When confirming individual products with this method, the Confirm Orders button remains on the vendor line.

Example

A vendor receives an order for three pizzas, and an order of garlic knots. When the delivery is made to the company, the _Lunch_ manager notices the garlic knots are missing.

The manager first marks the three pizzas as received, by individually confirming the products with the ✔️ Confirm button at the end of each product line.

Later, when the vendor delivers the garlic knots, the manager can either click the ✔️ Confirm button at the end of the line for the garlic knots, or click the Confirm Orders button that appears next to the vendor’s name and phone number.

### Notify employees¶

After products are received, and the orders are confirmed, the employees **must** be informed that their orders have been delivered, and are ready to be picked up.

Unlike sending and confirming orders, notifications must be sent individually, and cannot be sent in a batch.

To notify the user their product has arrived, click the ✉️ Send Notification button at the end of each product line. An email is sent to the user informing them their products have been delivered.

## Controlla fornitori¶

All orders for all vendors, both past and present, can be found in the _Control Vendors_ dashboard. To access these records, navigate to Lunch app ‣ Manager ‣ Control Vendors.

All orders appear in a list view, grouped alphabetically by Vendor. The list loads with all vendors expanded to show all order lines for every vendor, by default.

The following information appears in the list:

  * Order Date: the date the order was placed.

  * Vendor: the vendor the product is being ordered from.

  * Product: the specific product ordered.

  * Extras: any extras selected for the product.

  * Notes: any information needed to be sent to the vendor.

  * User: the user who ordered the product.

  * Lunch Location: where the product is set to be delivered.

  * Price: the total price for the product, including all extras.

  * Status: the current status of the product.

  * Company: the company under which the order was placed. This only appears in a multi-company database.




Orders can be cancelled, sent to the vendor, confirmed upon arrival, and employees can be notified using the same method as on the Today’s Orders dashboard.

Nota

The difference between the Today’s Orders dashboard and the Control Vendors dashboard is that the _Today’s Orders_ dashboard **only** displays orders for the current day, while the Control Vendors dashboard displays **all** orders made in the _Lunch_ app.

Vedi anche

  * [Mensa](../lunch.html)

  * [Manage user accounts](user-accounts.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/lunch/management.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../marketing.html "Marketing") |
  * [precedente](user-accounts.html "Manage user accounts") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Lunch management


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[API]: application programming interfaces
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
  *[POS]: Punto vendita
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
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number