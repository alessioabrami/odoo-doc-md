# Subscriptions in the eCommerce shop — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](plans.html "Subscription plans") |
  * [precedente](../subscriptions.html "Abbonamenti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Subscriptions in the eCommerce shop



# Subscriptions in the eCommerce shop¶

Subscription products can be sold in the Odoo _eCommerce_ shop just like regular sales products.

However, by default, the eCommerce product page **only** displays the shortest recurrence period listed in the Recurring Prices tab of the product form.

For example, if a subscription product has _monthly_ and _annaul_ recurrence periods configured, then _only_ the monthly price appears on the eCommerce page for that product, by default.

To add more recurrence periods to the eCommerce product page, create a _product variant_ for each recurrence period.

Vedi anche

  * [Configure subscription products](../subscriptions.html)

  * [Product variants](../sales/products_prices/products/variants.html)




## Create recurrence periods as product variants¶

To set up each recurrence period as a product variant, go to Subscriptions app ‣ Products ‣ Products, and select a product. In the Attributes & Variants tab, click Add a line.

Then proceed to create an Attribute called `Billing Period` (or something similar), by typing in the name, and clicking Create from the mini drop-down menu that appears. This attribute name appears as option heading on the product page of the eCommerce shop.

Next, create Values that correspond to the recurrence periods that are configured in the Recurring Prices tab of the product form.

To do that, type in the name of the recurrence period in the Values column, on the same Attribute line, in the Attributes & Variants tab. Then, click Create from the mini drop-down menu that appears.

These value names appear as selectable options on the product page of the eCommerce shop.

With those configurations in place and saved, a Product Variants column appears in the Recurring Prices tab. Proceed to assign the different Product Variants to their corresponding recurrence Period and Price.

After following those aforementioned steps, the product variants are available for selection on the eCommerce product page.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/subscriptions/ecommerce.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](plans.html "Subscription plans") |
  * [precedente](../subscriptions.html "Abbonamenti") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Subscriptions in the eCommerce shop


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