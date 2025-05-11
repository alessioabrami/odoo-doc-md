# Amazon Connector features — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](setup.html "Amazon Connector configuration") |
  * [precedente](../amazon_connector.html "Integrazione con Amazon") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon Connector features



# Amazon Connector features¶

The _Amazon Connector_ synchronizes orders between Amazon and Odoo, which considerably reduces the amount of time spent manually entering Amazon orders (from the Amazon Seller account) into Odoo. It also allows users to accurately keep track of Amazon sales in Odoo.

## Supported features¶

The Amazon Connector is able to:

  * Synchronize (Amazon to Odoo) all confirmed orders (both FBA and FBM), and their order items, which include:

    * product name, description, and quantity

    * shipping costs for the product

    * gift wrapping charges

  * Create any missing partner related to an order in Odoo (contact types supported: contact and delivery address).

  * Notify Amazon of confirmed shipment in Odoo (FBM) to get paid.

  * Synchronize (Odoo to Amazon) all available quantities of your products (FBM).

  * Support multiple seller accounts.

  * Support multiple marketplaces per seller account.




The following table lists capabilities provided by Odoo when using the Amazon Connector:

| Fulfilled By Amazon (FBA) | Fulfilled By Merchant (FBM)  
---|---|---  
**Orders** | Synchronize shipped and canceled orders. | Synchronize unshipped and canceled orders.  
**Shipping** | Shipping cost is computed by Amazon, and included in the synchronized order. | Shipping cost is computed by Amazon and included in the synchronized orders.  
Shipping done by Amazon. | A delivery order is automatically created in Odoo for each new order. Once it has been processed in Odoo, the status is then synchronized in Amazon.  
**Gift Wrapping** | Handled by Amazon. | Cost is computed by Amazon, and included in the synchronized order. Gift message is added on a line of the order and on the delivery order. Then it is up to the user.  
**Stock Management** | Managed by Amazon, and synchronized with a virtual location to follow it in Odoo. | Managed in Odoo Inventory app, and synchronized with Amazon.  
**Delivery Notifications** | Handled by Amazon. | Send by Amazon, based on delivery status synchronized from Odoo.  
  
Importante

The stock synchronization does **not** currently support selling the same product as FBM _and_ FBA.

At times, when stock is sent for all products, it triggers a stock problem with Amazon, where Amazon incorrectly thinks the FBM product has some quantity in FBM.

As a result, Amazon then sells it as FBM, instead of taking from their own warehouse. Odoo developers are currently working on resolving this issue to avoid future discrepancies.

Nota

The Amazon Connector is designed to synchronize the data of sales orders. Other actions, such as downloading monthly fees reports, handling disputes, or issuing refunds, **must** be managed from the _Amazon Seller Central_ , as usual.

Avvertimento

As of February 19, 2024, in North American marketplaces, FBA orders created with the _Amazon Connector_ , do not get the customer’s name passed onto the sales/delivery order in Odoo. This is due to the fact that Amazon now calculates, and remits, sales tax on behalf of sellers. In other words, personally identifiable customer information is not transmitted to the seller any longer, after a FBA order.

## Supported marketplaces¶

If a marketplace is not listed in your Amazon marketplaces, it’s possible to [add a new marketplace](setup.html#amazon-add-new-marketplace).

**North America region**  
---  
Canada | Amazon.ca  
Messico | Amazon.com.mx  
US | Amazon.com  
**Europe region**  
---  
Germania | Amazon.de  
Spagna | Amazon.es  
Francia | Amazon.fr  
Regno Unito | Amazon.co.uk  
Italia | Amazon.it  
Olanda | Amazon.nl  
  
Vedi anche

  * [Amazon Connector configuration](setup.html)

  * [Amazon order management](manage.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/amazon_connector/features.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](setup.html "Amazon Connector configuration") |
  * [precedente](../amazon_connector.html "Integrazione con Amazon") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon Connector features


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