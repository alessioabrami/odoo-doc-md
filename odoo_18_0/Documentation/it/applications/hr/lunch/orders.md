# Ordini — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](user-accounts.html "Manage user accounts") |
  * [precedente](products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Ordini



# Ordini¶

When the _Lunch_ application is opened, the Order Your Lunch dashboard loads. This view is also accessed by navigating to Lunch app ‣ My Lunch ‣ New Order.

The Order Your Lunch dashboard provides a summary of lunch offerings, the user’s account information, and the current day’s orders, along with their statuses.

## Ordina il pranzo¶

On the main Order Your Lunch dashboard, all the necessary information needed to place an order is visible. The default filter for the products is Available Today, which is present in the Search… bar. This filter shows only products that can be purchased that day, based on the [vendor’s availability](vendors.html#lunch-availability).

The left-side of the dashboard displays the various Categories of products available, along with the Vendors supplying the products. To the right of each line is a number, which indicates how many products are associated with that respective category or vendor.

To filter the products by categories or vendors, tick the checkbox next to the desired category or vendor to only view items related to those selections. Multiple selections can be made in each section.

Nota

If multiple selections are made, **only** products that fall under **all** the selected options are shown.

The top portion of the dashboard, which serves as an order summary, displays the user’s account information, and the order details for today, if any orders have been placed.

The main section, beneath the user’s information, displays all the products in a default Kanban view. Each product card displays the name, cost, vendor, photo, and description of the product. If the product is configured as new, it also displays a New tag.

Nota

Anywhere a vendor’s name is listed in the _Lunch_ app, such as on Kanban product cards, their phone number is listed, as well.

The products can also be displayed in a list view, by clicking the ≣ (four parallel lines) icon in the top-right corner of the dashboard.

## Placing orders¶

To place a lunch order, navigate to the main Order Your Lunch dashboard, by either opening the _Lunch_ app, or by navigating to Lunch app ‣ My Lunch ‣ New Order.

### Add products to an order¶

From the Order Your Lunch dashboard, click on a desired product to add to an order, and the product appears in a Configure Your Order pop-up window.

At the top of the pop-up window is the product image, name, and price. Beneath that, there is a potential Extras field, showcasing any [extra items or options](vendors.html#lunch-extras). Tick the checkbox next to any desired extras present in the Extras field to add them to the order.

Each extra option is organized by a category, complete with its name and price. As extras are selected, the displayed price at the top of the pop-up window updates to reflect all current selections.

Beneath the Extras field is the Description of the product, followed by a Notes field. The Notes field is used to enter any vital information, which is then sent to the vendor regarding the order, such as any special requests or food allergies.

When all selections for the product have been made, click the Add To Cart button in the lower-left of the pop-up window. To cancel the order, click the Discard button.

#### Errori¶

Depending on how the various [extras](vendors.html#lunch-configure-extras) are configured for a vendor, it is possible to receive an error when attempting to add products to the cart.

An error can occur when a configured product **requires** the user to select an option in the Extras field, but the user neglects to make one.

When this occurs, a Validation Error pop-up window appears. The error is briefly explained in the pop-up window. Click Close to close the window, and make any necessary changes to the Configure Your Order pop-up window.

Example

The vendor, The Pizza Palace, provides a free beverage with any purchase. Their products are configured so that a beverage selection is **required** in the Extras field _before_ adding one of their products to the cart.

If a selection is **not** made, an error occurs. The message that appears is `You have to order one and only one Free Beverage with Purchase`.

### Your Order summary¶

When at least one item is added to an order, the items appear at the top of the dashboard in the Your Order summary. In addition to the products, users can view the account information, in addition to all the information related to orders placed during the current calendar day.

As products are added to an order, they appear at the top center of the summary box. Each product is listed beneath the words Your Order, with the product name, quantity, and a status tag.

The available tags that can be displayed for each item are:

  * To Order: the product has been added to the cart, but has not been purchased yet by the user.

  * Ordered: the product has been purchased by the user, and is waiting to be sent to the vendor by a _Lunch_ app manager.

  * Sent: the order for the product has been sent to the vendor by a _Lunch_ app manager.

  * Received: the product has been delivered by the vendor to the user’s location, and has been verified as received by a _Lunch_ app manager.




Product quantities can be adjusted by clicking the ➕ (plus sign) or ➖ (minus sign) to the left of the listed product. The product price adjusts in real-time to display the cost for the currently selected quantity of the product.

The right side of the Your Order summary displays the purchasing information. The Total amount for the entire day’s lunch order is displayed. The Already Paid field indicates how much has been paid that day towards the Total amount. The To Pay field displays how much of the remaining Total amount must be paid, in order to place the currently configured order.

Suggerimento

Users can place multiple orders throughout the day, and are not restricted to only placing one lunch order each day. Multiple orders might need to be placed, due to users forgetting to add items to an order, or if there are multiple meals that are available to be purchased for the office ()not just lunch), and so on.

Depending on the various vendors, and how the vendors and products are configured, it is possible to order breakfast, lunch, dinner, coffee, and/or snacks.

### Submit an order¶

To place the order, click the Order Now button on the right-side of the Your Order summary. The user is charged the amount that is displayed in the To Pay field, and the cost is deducted from their _Lunch_ account balance.

Once the order is placed, the tags for the items just purchased in the Your Order field change from orange To Order tags to red Ordered tags.

### Track an order¶

When orders have been sent to the vendors, the tags for the items in the Your Order summary change from red Ordered tags to blue Sent tags.

Once orders have been received and verified, the tags change from blue Sent tags to green Received tags.

### Receive an order¶

When orders are received at the delivery location, they are confirmed by a _Lunch_ app manager, and a notification is sent to the employee who ordered the food.

## Ordini¶

To view a full list of all orders placed in the _Lunch_ app for the currently signed-in user, navigate to Lunch app ‣ My Lunch ‣ My Order History. This navigates to the My Orders dashboard. The data is filtered by My Orders and grouped by Order Date: Day, by default, both of which are located in the Search… bar.

All products appear in a list view, organized by date. The list displays the Order Date, Vendor, Product, Extras, Notes, User, Lunch Location, Price, and Status information. If in a multi-company database, a Company column also appears.

The total cost for each order is displayed on the line containing the order date. At the bottom of the list, beneath all the lines, the overall total amount paid for all the orders appears, under the Price column.

At the end of each product line with a status of Ordered or Sent, an X Cancel button appears. Click X Cancel to cancel that product order. Once a product order has been cancelled, the money paid for that product is refunded, and appears in the user’s account.

At the end of each product line with a status of Received, a Re-order button appears. Click Re-order to instantly reorder that same product, with the same extras, if applicable. The new order appears in the list, under the current date, and the product is paid for, with money deducted from the user’s account.

## Il mio account¶

To view a summary of all transactions in the user’s account, navigate to Lunch app ‣ My Lunch ‣ My Account History. Doing so reveals the My Account dashboard.

The default presentation of the My Account dashboard displays all entries, from newest to oldest. The Date, Description, and Amount are the only fields displayed in the list.

Entries with a negative figure listed in the Amount column represent products purchased in the _Lunch_ app. These appear in a `$-XX.XX` format.

Entries with a positive balance either represent funds added to the user’s lunch account, or cancelled orders that were eventually refunded to the user. These appear in a `$XX.XX` format.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/lunch/orders.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](user-accounts.html "Manage user accounts") |
  * [precedente](products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Ordini


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