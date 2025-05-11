# Linking existing listings — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../point_of_sale.html "Punto vendita") |
  * [precedente](troubleshooting.html "Troubleshooting eBay connector") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con eBay](../ebay_connector.html) »
  * Linking existing listings



# Linking existing listings¶

Once the eBay account is linked existing listings from within the eBay seller account need to be added manually to the Odoo product listings.

The process will be as follows: \- Turn off eBay scheduled actions \- Add products and link listings \- Turn on eBay scheduled actions

Vedi anche

To learn more about the eBay connector visit these pages as well:

  * [eBay connector setup](setup.html)

  * [How to list a product?](manage.html)

  * [Troubleshooting eBay connector](troubleshooting.html)




## Turn off eBay scheduled actions¶

To start linking existing listings in eBay, first turn off the eBay notifications in the scheduled actions in Odoo. The reason for this is so that no orders or eBay data syncs during this process. The Scheduled Actions can be accessed by first activating [developer mode](../../../general/developer_mode.html#developer-mode). After doing so, go to Settings ‣ Technical ‣ Automation ‣ Scheduled Actions.

Avvertimento

[Modalità sviluppatore (modalità di debug)](../../../general/developer_mode.html) must be activated to ensure the technical menu appears for the user.

Disabling scheduled actions enables users to sync and validate eBay data before receiving orders. The following are descriptions of scheduled actions that need to be temporarily deactivated:

  * eBay: get new orders: eBay pushes new orders not already in Odoo (based on client_order_reference, or sales order reference field). This command also updates existing orders, where changes we made in eBay. New and updated orders are then placed in draft mode. Customers will be created if they are not already in Odoo.

  * eBay: synchronize stock: eBay displays Odoo’s stock on hand.

  * eBay: update categories: eBay will push updated monthly categories (only up to fourth layer; a manual update required for the rest).




To toggle off the eBay notification, select the entry from the Scheduled Actions list. Then, on the page, click the Active toggle button to turn it off.

### Sync eBay categories¶

To ensure that Odoo’s eBay products have all the categories available on eBay, the eBay categories should be synced to Odoo next.

Navigate to Settings ‣ Technical ‣ Automation ‣ Scheduled Actions. Click into the scheduled action labeled: Ebay: update categories and then click Run Manually.

Importante

Odoo only recognizes eBay category paths up to four layers deep. If a product has a listing of more than four, the category field will only populate up to the fourth layer.

If product categories beyond four paths are required, users need to manually add those paths. This has historically been done by getting a list of all product categories beyond 4 paths, manually importing them into the Product Category model in Odoo, then linking them individually to the product.

Users can import the remaining product categories into the eBay product categories manually using using the Action menu and Import feature.

## Link eBay listings¶

To add eBay listings in Odoo, either manually add products, using a listing ID, or establish an automatic listing link between Odoo and eBay.

Suggerimento

For more information on listing a product from scratch visit: [How to list a product?](manage.html#ebay-connector-listing)

### Manual listing link¶

To add an eBay listing to products in Odoo, begin by going to Sales app ‣ Products ‣ Products and selecting the desired product. Click on Sell on eBay (either in the eBay tab or under the Product name). Select Save if necessary.

Still the product form, click link to listing in the top menu and enter in listing ID from eBay in the pop up (the listing ID is in the eBay product URL).

Example

An example URL would be as such: `www.ebay.com/itm/272222656444?hash=item3f61bc17bb:g:vJ0AAOSwslJizv8u`. The listing ID is `272222656444` in this case. Once the listing ID has been entered the eBay listing information will sync into Odoo.

## Turn on eBay scheduled Actions¶

The next step is to turn on the eBay notifications in the scheduled actions in Odoo so that orders and data are exchanged. The Scheduled Actions can be accessed by first activating [developer mode](../../../general/developer_mode.html#developer-mode) and go to Settings ‣ Technical ‣ Automation ‣ Scheduled Actions.

Turning on the following scheduled actions allows users to sync and validate eBay data automatically.

  * eBay: get new orders: eBay will push all new orders not already in Odoo (based on client_order_reference, or sales order reference field), and will update orders if there has been a change from eBay. Orders will be put in draft mode. Customers will be created if they are not already in Odoo.

  * eBay: synchronize stock: eBay will display the stock on hand in Odoo.

  * eBay: update categories: eBay will push updated monthly categories (only up to fourth layer, will need to manually update the rest).




Nota

If an order comes in and the listing from the order is not linked to a product, eBay will create a consumable product.product in its place. These consumables should be altered on the _Sales Order_ while in draft state to represent a storable product, and then the user can link to the listing as they come in.

Vedi anche

  * [How to list a product?](manage.html)

  * [Troubleshooting eBay connector](troubleshooting.html)

  * [eBay connector setup](setup.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/ebay_connector/linking_listings.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../point_of_sale.html "Punto vendita") |
  * [precedente](troubleshooting.html "Troubleshooting eBay connector") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con eBay](../ebay_connector.html) »
  * Linking existing listings


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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon