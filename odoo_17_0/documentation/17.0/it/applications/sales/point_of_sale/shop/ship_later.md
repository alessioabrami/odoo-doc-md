# Ship later — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_display.html "Schermo cliente") |
  * [precedente](serial_numbers.html "Serial numbers and lots") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Shop features](../shop.html) »
  * Ship later



# Ship later¶

The **Ship Later** feature allows you to sell products and schedule delivery at a later date. It is useful, for example, when a product is out of stock or so voluminous that it requires to be shipped, or if, for any reason, the customer needs their order to be shipped later, etc.

## Configurazione¶

[Go to the POS settings](../configuration.html#configuration-settings), scroll down to the Inventory section, and enable Allow Ship Later.

Once activated, you can:

  * Choose the location from where the products are shipped by selecting a Warehouse.

  * Define a Specific route, or leave this field empty to use the default route.

  * Define the Shipping Policy; select As soon as possible if the products can be delivered separately or When all products are ready to ship all the products at once.




Vedi anche

  * [Delivery methods](../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html)

  * [Magazzini](../../../inventory_and_mrp/inventory/warehouses_storage/inventory_management/warehouses.html)




## Practical application¶

  1. [Open a session](../../point_of_sale.html#pos-session-start) and make a sale.

  2. On the payment screen, set a customer and select Ship Later.

  3. On the popup window, set a shipping date and click Confirm to proceed to payment.




The system instantly creates a delivery order from the warehouse to the shipping address.

Nota

The selected customer must have referenced an address in the system for products to be shipped.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/shop/ship_later.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_display.html "Schermo cliente") |
  * [precedente](serial_numbers.html "Serial numbers and lots") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Shop features](../shop.html) »
  * Ship later


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order