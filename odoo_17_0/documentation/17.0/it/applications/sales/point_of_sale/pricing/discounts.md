# Sconti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](discount_tags.html "Discount tags \(barcode scanner\)") |
  * [precedente](../pricing.html "Pricing features") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Sconti



# Sconti¶

By offering discounts, you can entice your customers and drastically increase your revenue. It is vital to offer discounts, whether they are time-limited, seasonal or manually given.

To manage discounts, Odoo has powerful features that help set up a pricing strategy tailored to every business.

## Apply manual discounts¶

If you seldom use discounts, applying manual ones might be the easiest solution for your Point of Sale.

You can either apply a discount on the whole order or on specific products inside an order.

### Apply a discount on a product¶

From your PoS session interface, use the _Disc_ button.

Then, you can input a discount over the product that is currently selected.

### Apply a global discount¶

To apply a discount on the whole order, go to Point of Sales ‣ Configuration ‣ Point of Sale and select your PoS.

Once on your PoS form, select _Global Discounts_ , under the _Pricing_ category.

Now, you have a new _Discount_ button appearing on your PoS interface.

Click on it and enter the wanted discount.

Nota

On this example, there is a global discount of 50% as well as a specific 50% discount on oranges.

## Apply time-limited discounts¶

To activate time-limited discounts, you must activate the _Pricelists_ feature. To do so, go to Point of Sales ‣ Configuration ‣ Point of Sale and open your PoS. Then, enable the pricelist feature.

Once activated, you must choose the pricelists you want to make available in the PoS and define a default one.

### Create a pricelist¶

By default, Odoo has a _Public Pricelist_ configured. To create more, go to Point of Sale ‣ Products ‣ Pricelists. Then click on create.

When creating a pricelist, you can set several criteria to use a specific price: period, min. quantity, etc. You can also decide to apply that pricelist on specific products or on the whole range.

### Using a pricelist with the PoS interface¶

On the PoS interface, a new button appears. Use it to select a pricelist.

Click on it to instantly update the prices with the selected pricelist. Then, you can finalize the order.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/pricing/discounts.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](discount_tags.html "Discount tags \(barcode scanner\)") |
  * [precedente](../pricing.html "Pricing features") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Sconti


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