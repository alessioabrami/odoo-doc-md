# Chapter 2 - Build your website — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [precedente](01_theming.html "Chapter 1 - Theming") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 2 - Build your website



# Chapter 2 - Build your website¶

## Create a page¶

Now that the theme has been set up, let’s move on to creating the content.

First of all, start by creating your first theme page: the home page. For now, only indicate “Hello” as content in the page.

Suggerimento

You will need to deactivate the default homepage.

Vedi anche

See reference documentation on how to [desactivate a default page](../../howtos/website_themes/pages.html#website-themes-pages-default) and how to [start a new page](../../howtos/website_themes/pages.html#website-themes-pages-theme-pages).

Solutions

`/website_airproof/__manifest__.py`¶
    
    
    'data': [
       # Pages
       'data/pages/home.xml',
    ]
    

`/website_airproof/data/pages/home.xml`¶
    
    
    <?xml version="1.0" encoding="utf-8"?>
    <odoo>
       <data noupdate="1">
          <!-- Deactivate default homepage -->
          <record id="website.homepage" model="ir.ui.view">
             <field name="active" eval="False"/>
          </record>
          <!-- Home -->
          <record id="page_home" model="website.page">
             <field name="name">Home</field>
             <field name="is_published" eval="True"/>
             <field name="key">website_airproof.page_home</field>
             <field name="url">/</field>
             <field name="type">qweb</field>
             <field name="arch" type="xml">
                <t t-name="website_airproof.page_home">
                   <t t-call="website.layout">
                      <!-- Title -->
                      <t t-set="additional_title">One step beyond the horizon | Airproof</t>
                      <!-- Content -->
                      <div id="wrap" class="oe_structure">
                         <p>Hello</p>
                      </div>
                   </t>
                </t>
             </field>
          </record>
       </data>
    </odoo>
    

## Add a media¶

If you want the client to be able to reuse certain pictures that you are going to add on the website, they must be added to the image library.

To do the test, declare the drone image to add it to the library. You will find the [drone picture here](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/img/content/drone-robin.png).

Vedi anche

See reference documentation on how to [add a media](../../howtos/website_themes/media.html#website-themes-media-images).

Go to the Website Builder, double-click on the logo, and you will see the drone image in the library.

Solutions

To complete this exercise, you need to:

  1. Put your PNG in the right image folder.

  2. Create your `images.xml` file. You can find all the necessary information in the [images.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/images.xml) file from our example module.

  3. Declare your file in the `__manifest__.py`.




## Add building blocks¶

Now, let’s get into the real work. Start adding content to the pages.

In an Odoo website, we create the content of a page using building blocks. These can be compared to snippets editable by the user in the Website Builder. The standard main container for any snippet is a `section`.

Based on the Airproof design, add the following elements to the homepage :

  * Create a section with the 3 boxes using the Big boxes building block.

    * For this section, you don’t want the future user to be able to edit it via the Website Builder.

    * Put an opacity filter on the background image of the 3 boxes.

  * Create another section containing the title and icons.




You can use these [images](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/img/content) and [icons](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/img/content/icons).

Vedi anche

See reference documentation on how to [write standard snippets](../../howtos/website_themes/building_blocks.html#website-themes-building-blocks-layout).

Suggerimento

To determine the code needed to create your building blocks :

  * Create a test page via the website builder.

Drag & drop the building block that interests you and apply the right design.

Use the code generated via Editor HTML/SCSS in the menu.

  * You can also find the original building block code in Odoo : `odoo/addons/website/views/snippets/**.xml`.




Solutions

Find the solution in our Airproof example on [home.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/pages/home.xml).

## Navigation¶

For now, the client is fine with the default header but has requested some navigation adjustments.

The client has requested the following changes:

  * Remove the link to the homepage and the shop.

  * Add a link to the future “About us” page.

  * Replace the default blog item with a dropdown to display the different blogs: “Our latest news” and “Tutorials”.

  * Add a mega-menu “Waterproof drones” to display the different products.




Vedi anche

  * You can find the original mega-menu templates code in Odoo : [odoo/addons/website/views/snippets/s_mega_menu_**.xml](https://github.com/odoo/odoo/blob/17.0/addons/website/views/snippets)

  * See reference documentation on how to modifiy the [Navigation](../../howtos/website_themes/navigation.html).




Suggerimento

  * Make sure the Blog app is installed and create the two different blogs in the backend.

  * Create the different products via the backend. You can use these [product pictures](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/img/content).




Solutions

Find the solution in our Airproof example on [menu.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/menu.xml).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/website_theme/02_build_website.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [precedente](01_theming.html "Chapter 1 - Theming") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 2 - Build your website


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration