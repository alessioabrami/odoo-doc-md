# Product combos — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shop.html "Shop features") |
  * [precedente](self_order.html "Self-ordering") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Product combos



# Product combos¶

The **Product Combos** feature allows users to define and manage combination options for a single product.

In the context of a restaurant, the feature enables users to create multiple-choice menus. For example, a user can define a main dish and specify various options for sides, drinks, or desserts that customers can combine with the main dish.

In retail, this feature allows you to create a product set with multiple products to choose from and combine.

## Configurazione¶

First, you need to create combination choices. To do so:

  1. Go to Point of Sale ‣ Products ‣ Product Combos and click New.

  2. Name your combo and add the products you want customers to choose from by clicking Add a line. You can also include an extra price for each option in the Extra Price column.




Nota

As a reference, the selected product’s original price is displayed in the Original Price column.

Second, you need to create a specific product to gather combo choices. To do this:

  1. Go to Point of Sale ‣ Products ‣ Products and click New.

  2. Set the Product Type to Combo and fill in the General Information tab.

Nota

The sales price of the combo product is fixed and does not vary based on the individual prices of included items or the quantity of items in the combo. The combo product price is only affected by the extra price optionally defined at the combo choice creation or if a variant of one of the items has a specified extra price.

  3. Go to the Combo Choices tab, click Add a line, and select the combinations to add. You can also create a new combination at this step by clicking New on the popup window.




Once you have created and added the combo choices into a product, you can sell combos in your retail store or restaurant.

## Practical application¶

[Open a POS session](../point_of_sale.html#pos-session-start) and select the combo product. Choose the options and click Add to order. As a reminder, the extra price appears under the related choices.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/combos.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shop.html "Shop features") |
  * [precedente](self_order.html "Self-ordering") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Product combos


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