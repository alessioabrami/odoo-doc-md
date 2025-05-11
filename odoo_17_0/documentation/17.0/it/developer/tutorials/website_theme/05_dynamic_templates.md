# Chapter 5 - Dynamic templates — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](06_going_live.html "Chapter 6 - Going live") |
  * [precedente](04_customisation_part2.html "Chapter 4 - Customisation, Part II") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 5 - Dynamic templates



# Chapter 5 - Dynamic templates¶

## Adapt the shop template¶

Now, let’s adapt the dynamic sections of the website. As you may know, some pages such as those for eCommerce are automatically generated. Pages like the shop, product, and checkout are automatically generated when the `website_sale` application is installed. These template pages pull their displayed information from the backend.

To modify these pages, we need to edit the standard Odoo template. This can be done using SCSS, presets, and especially XPath. Locate the standard Odoo template you want to modify and extend it using `XPath`. Following the Airproof design, let’s begin by modifying the shop view.

  1. First, locate the standard template in Odoo : website_sale ‣ templates.xml ‣ id=»products».

  2. Apply all changes in your `website_sale_templates.xml` file. Start by:

     * Add a banner.

     * Adapt the layout of the e-commerce category filtering on the left.

     * Remove the search bar (you can remove it from both the shop and the product pages at the same time).

     * Move the breadcrumb.

     * Hide the list or grid view option.

     * Create the appropriate design and information for the product cards.




Suggerimento

  * Apply your modifications using presets, XPath and SCSS.

  * To enable attribute/variant filtering, activate the [Varianti prodotto](../../../applications/sales/sales/products_prices/products/variants.html) option in the website backend settings and [configure attributes and variants](../../../applications/websites/ecommerce/products.html#ecommerce-products-product-variants) for the products.




Solutions

Find the solution in our Airproof example on [presets.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/presets.xml), [website_sale_templates.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/views/website_sale_templates.xml) part _shop page_ , and [shop.scss](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/scss/pages/shop.scss).

## Adapt the product page template¶

The client is thrilled with the shop modifications. Next, let’s apply our design to the product pages. Based on the Airproof design below, adapt a few elements including:

  * Remove the search bar (if not done with the previous exercise).

  * Remove the quantity selector, Terms and Conditions, and share icons.

  * Update the Add to cart button icon.

  * Insert a title above the product specifications (this section appears only when the product has one variant per attribute).

  * Design the appropriate layout for the carousel.

  * Add a title and apply the previously created product template to the `Alternative products` section (ensure alternative products are assigned on the product in the backend for this section to appear).

  * Implement a new drop zone below product details, visible on all products. As a use case, add an `Text-Image` building block using the Website Builder (e.g.: See Airproof product page screenshot with “ _Six reasons to buy…_ ”).




Vedi anche

See reference documentation on how to create a [Drop zone](../../howtos/website_themes/layout.html#website-themes-layout-dropzone).

Suggerimento

  * Make your modifications using presets, XPath, and SCSS. Be sure to comment your code properly so you can find your way around.

  * The drop zone will be visible on all products. To create a specific dropzone per product, you need to add a new field to the product model.




Solutions

Find the solution in our Airproof example on [presets.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/presets.xml), [website_sale_templates.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/views/website_sale_templates.xml) part _product page_ , and [product_page.scss](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/scss/pages/product_page.scss).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/website_theme/05_dynamic_templates.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](06_going_live.html "Chapter 6 - Going live") |
  * [precedente](04_customisation_part2.html "Chapter 4 - Customisation, Part II") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 5 - Dynamic templates


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration