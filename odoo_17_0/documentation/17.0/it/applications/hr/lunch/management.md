# Lunch management — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../marketing.html "Marketing") |
  * [precedente](user-accounts.html "Manage user accounts") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Lunch management



# Lunch management¶

In Odoo’s _Lunch_ application, it is required to have someone manage the orders, vendors, and products. In addition, someone must be responsible for the orders, and notifying employees when their orders have arrived. This can be the same person.

Orders can be canceled, sent to the vendor, confirmed upon arrival, and employees can be notified, either from the Today’s Orders dashboard, or the Control Vendors dashboard.

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

To cancel an order from a vendor, individual products **must** be canceled one at a time.

On the Today’s Orders dashboard, a ✖️ Cancel button is shown at the far-right of each product line that can be canceled. Click the ✖️ Cancel button to cancel the order for that individual product.

Nota

Only products with a red Status tag of Ordered can be canceled.

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




Orders can be canceled, sent to the vendor, confirmed upon arrival, and employees can be notified using the same method as on the Today’s Orders dashboard.

Nota

The difference between the Today’s Orders dashboard and the Control Vendors dashboard is that the _Today’s Orders_ dashboard **only** displays orders for the current day, while the Control Vendors dashboard displays **all** orders made in the _Lunch_ app.

Vedi anche

  * [Mensa](../lunch.html)

  * [Ordini](orders.html)

  * [Manage user accounts](user-accounts.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/lunch/management.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../marketing.html "Marketing") |
  * [precedente](user-accounts.html "Manage user accounts") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
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
  *[FBM]: Fulfilled By Merchant
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