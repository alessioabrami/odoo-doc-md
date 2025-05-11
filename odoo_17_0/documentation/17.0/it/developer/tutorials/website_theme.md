# Build a website theme — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_theme/01_theming.html "Chapter 1 - Theming") |
  * [precedente](pdf_reports.html "Build PDF Reports") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Build a website theme



# Build a website theme¶

For this project, we’ll collaborate on creating a custom website theme fully integrated with Odoo.

Our client, Airproof, has provided their latest design for their waterproof drone e-commerce, which we’ll replicate.

To start, you must have [installed Odoo locally](../../administration/on_premise/source.html). You will also need some knowledge in:

  * XML

  * JavaScript (not mandatory)

  * Bootstrap 5.1.3

  * SCSS

  * QWeb (Odoo’s own templating system)

  * OWL (JavaScript framework, not mandatory)




**Goal**

Replicate the Airproof design.

In the `README.md` of the [Airproof module](https://github.com/odoo/tutorials/blob/17.0/website_airproof), you can find the various Airproof designs that you will replicate throughout the different exercises in this tutorial.

You can also find all the code necessary for creating the Airproof website there. You should also obtain this by the end of the tutorial. It is recommended to try solving the exercices first without looking at the solution!

**Don’t go too fast!**

Follow the exercises step by step and you will reach the final design at the end of the tutorial.

Throughout this tutorial, you will find «See also» sections leading to parts of the [How-to guide: Website themes](../howtos/website_themes.html) documentation. Be sure to read this documentation thoroughly each time! With it, you will find the solution to every exercise.

Ready? Let’s get started!

  * Chapter 1 - Theming
    * [Setup](website_theme/01_theming.html#setup)
    * [Build your module structure](website_theme/01_theming.html#build-your-module-structure)
    * [Declare Odoo variables](website_theme/01_theming.html#declare-odoo-variables)
    * [Declare Bootstrap variables](website_theme/01_theming.html#declare-bootstrap-variables)
    * [Define presets](website_theme/01_theming.html#define-presets)
  * Chapter 2 - Build your website
    * [Create a page](website_theme/02_build_website.html#create-a-page)
    * [Add a media](website_theme/02_build_website.html#add-a-media)
    * [Add building blocks](website_theme/02_build_website.html#add-building-blocks)
    * [Navigation](website_theme/02_build_website.html#navigation)
  * Chapter 3 - Customisation, Part I
    * [Add custom SCSS](website_theme/03_customisation_part1.html#add-custom-scss)
    * [Add custom JS](website_theme/03_customisation_part1.html#add-custom-js)
    * [Create a custom header](website_theme/03_customisation_part1.html#create-a-custom-header)
    * [Create a custom footer](website_theme/03_customisation_part1.html#create-a-custom-footer)
    * [Create your custom building blocks](website_theme/03_customisation_part1.html#create-your-custom-building-blocks)
    * [Create a new dynamic snippets template](website_theme/03_customisation_part1.html#create-a-new-dynamic-snippets-template)
  * Chapter 4 - Customisation, Part II
    * [Create a custom background shape](website_theme/04_customisation_part2.html#create-a-custom-background-shape)
    * [Add a background gradient](website_theme/04_customisation_part2.html#add-a-background-gradient)
    * [Animations](website_theme/04_customisation_part2.html#animations)
    * [Forms](website_theme/04_customisation_part2.html#forms)
  * Chapter 5 - Dynamic templates
    * [Adapt the shop template](website_theme/05_dynamic_templates.html#adapt-the-shop-template)
    * [Adapt the product page template](website_theme/05_dynamic_templates.html#adapt-the-product-page-template)
  * Chapter 6 - Going live
    * [Translations](website_theme/06_going_live.html#translations)
    * [Module import](website_theme/06_going_live.html#module-import)
    * [Conclusion](website_theme/06_going_live.html#conclusion)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/website_theme.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_theme/01_theming.html "Chapter 1 - Theming") |
  * [precedente](pdf_reports.html "Build PDF Reports") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Build a website theme


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language