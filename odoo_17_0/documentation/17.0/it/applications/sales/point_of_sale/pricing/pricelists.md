# Listini prezzi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fiscal_position.html "Flexible taxes \(fiscal positions\)") |
  * [precedente](loyalty.html "Loyalty programs") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Listini prezzi



# Listini prezzi¶

Pricelists allow you to adjust product prices depending on various criteria automatically. For example, you can set POS-specific prices, create temporary discount periods, reward specific customers, or offer discounts when set quantities are ordered.

## Configurazione¶

Navigate to the [general POS app settings](../configuration.html#configuration-settings) and ensure Flexible Pricelists are enabled under the Pricing section.

Multiple prices per product is the default pricelist option for setting simple fixed price rules per product. Select Advanced price rules (discounts, formulas) to apply price rules to multiple products at once and to compute prices dynamically using percentage discounts or more complex formulas in addition to setting fixed prices.

Nota

The selected pricelist type applies to the entire database, including the [Sales](../../sales/products_prices/prices/pricing.html) and [eCommerce](../../../websites/ecommerce/products/price_management.html#ecommerce-pricelists) apps.

### Create pricelists¶

Go to Point of Sale ‣ Products ‣ Pricelists and click New or select an existing pricelist. The pricelist setup differs depending on the selected pricelist option.

#### Prezzi multipli per prodotto¶

When pricelists are configured to use the Multiple prices per product option, it is possible to use multiple fixed prices for different products or their variants depending, if necessary, on one or several conditions. To add a new price rule to a pricelist:

  1. Click Add a line, and select a **product** and its **variant** if needed.

  2. Add the condition(s):

     * a product quantity to be reached by using the Min. Quantity column;

     * a determined period during which the pricelist is applied by using the Start Date and End Date columns.

  3. Add the Price to be applied when the conditions are met (if any).




#### Advanced price rules¶

When pricelists are configured to use the Advanced price rules (discounts, formulas) option, it is possible to use percentage discounts/mark-ups and formulas in addition to using fixed prices. To add a new price rule to a pricelist, click Add a line. In the pop-up windows:

  1. Select a Computation method:

     * Fixed Price to set a new fixed price (similarly to the Multiple prices per product option).

     * Discount to compute a percentage discount (e.g., `10.00` %) or mark-up (e.g., `-10.00` %).

     * Formula to compute the price according to a formula. It is required to define what the calculation is **based on** (Sales Price, Cost, or Other Pricelist). You can then:

       * Apply a percentage Discount or mark-up.

       * Add an Extra Fee (e.g., $ `5.00`) or subtract a fixed amount (e.g., $ `-5.00`).

       * Define a [Rounding Method](cash_rounding.html) by forcing the price after Discount to be a multiple of the value set. The Extra Fee is applied afterward.

Example

To have the final price end with `.99`, set the Rounding Method to `1.00` and the Extra Fee to `-0.01`.

       * Specify the minimum (e.g., $ `20.00` ) and maximum (e.g., $ `50.00` ) profit Margins for computations based on Cost.

  2. Select on which product(s) the price rule should be **applied** :

     * All Products

     * a Product Category

     * a Product

     * a Product Variant

  3. Add conditions, such as a specific quantity to reach for the price to change by using the Min. Quantity field or a specific period during which the pricelist should be applied by using the Validity fields.




### Select pricelists¶

Go to the [specific POS settings](../configuration.html#configuration-settings) and add all the available pricelists in the Available field. Then, set its **default pricelist** in the Default field.

When you [open a POS session](../../point_of_sale.html#pos-session-start), click the **pricelists** button, and select the desired pricelist from the list.

Nota

  * Multiple pricelists must be selected for the **pricelist button** to be displayed.

  * If a pricelist is selected on a POS order while its conditions are **not** met, the price will **not** be adjusted.




Suggerimento

You can also set a pricelist to be selected automatically once a specific [customer is set](../../point_of_sale.html#pos-customers). To do so, go to the customer form and switch to the preferred pricelist in the Pricelist field of the Sales & Purchase tab.

Vedi anche

  * [Pricelists, discounts, and formulas](../../sales/products_prices/prices/pricing.html)

  * [How to use pricelists in an ecommerce environment](../../../websites/ecommerce/products/price_management.html#ecommerce-pricelists)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/pricing/pricelists.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fiscal_position.html "Flexible taxes \(fiscal positions\)") |
  * [precedente](loyalty.html "Loyalty programs") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Listini prezzi


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