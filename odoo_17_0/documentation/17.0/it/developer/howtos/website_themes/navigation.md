# Navigation — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages.html "Pages") |
  * [precedente](layout.html "Layout") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Navigation



# Navigation¶

You can easily modify the navigation with the Website Builder to fit your needs.

In this chapter, you will learn how to:

  * Delete and create menu items.

  * Create a dropdown menu.

  * Create a mega menu.




## Default¶

Odoo automatically generates some basic menu items depending on the apps you installed. For example, the Website app adds two items to the main menu. These items are linked to pages, which are also automatically created.

Delete default menu items.

`/website_airproof/data/menu.xml`¶
    
    
    <!-- Contact us -->
    <delete model="website.menu" search="[('url','in', ['/', '/contactus']),
    ('website_id', '=', 1)]"/>
    
    <!-- Shop -->
    <delete model="website.menu" search="[('url','in', ['/', '/shop']),
    ('website_id', '=', 1)]"/>
    

## Menu item¶

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
    <record id="menu_about_us" model="website.menu">
        <field name="name">About us</field>
        <field name="url">/about-us</field>
        <field name="parent_id" search="[
            ('url', '=', '/default-main-menu'),
            ('website_id', '=', 1)]"/>
        <field name="website_id">1</field>
        <field name="sequence" type="int">10</field>
    </record>
    

Field | Description  
---|---  
name | Link text  
url | Value of the href attribute  
parent_id | The menu in which the item will be added.  
website_id | The website on which the item will be added.  
sequence | Defines the link’s position in the top menu.  
  
### New window¶

Open the link’s URL in a new tab.
    
    
    <record id="..." model="website.menu">
        <field name="new_window" eval="True"/>
    </record>
    

### External Links¶

Add a link to an external website.
    
    
    <record id="..." model="website.menu">
        <field name="url">https://www.odoo.com</field>
    </record>
    

### Anchor¶

Link to a specific section of a page.
    
    
    <record id="..." model="website.menu">
        <field name="url">/about-us#our-team</field>
    </record>
    

## Dropdown menu¶

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
    <record id="menu_services" model="website.menu">
        <field name="name">Services</field>
        <field name="website_id">1</field>
        <field name="parent_id" search="[
            ('url', '=', '/default-main-menu'),
            ('website_id', '=', 1)]"/>
        <field name="sequence" type="int">...</field>
    </record>
    

Add an item to a dropdown menu.
    
    
    <record id="menu_services_item_1" model="website.menu">
        <field name="name">Item 1</field>
        <field name="url">/dropdown/item-1</field>
        <field name="website_id">1</field>
        <field name="parent_id" ref="website_airproof.menu_services"/>
        <field name="sequence" type="int">...</field>
    </record>
    

Field | Description  
---|---  
parent_id | The dropdown in which the item will be added.  
  
## Mega menu¶

A mega menu is a dropdown menu with additional possibilities and not just a list of links. In a mega menu, you can use any kind of content (text, images, icons, …).

In Odoo, you can select a mega-menu template in the list. If you don’t need a custom layout, you can re-use the template structure in the `mega_menu_content` field like any static content.

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
     <record id="menu_mega_menu" model="website.menu">
         <field name="name">Mega Menu</field>
         <field name="parent_id" search="[
             ('url', '=', '/default-main-menu'),
             ('website_id', '=', 1)]"/>
         <field name="website_id">1</field>
         <field name="sequence" type="int">..</field>
         <field name="is_mega_menu" eval="True"/>
         <field name="mega_menu_classes">...</field>
         <field name="mega_menu_content" type="html">
             <section class="s_mega_menu_multi_menus py-4 o_colored_level o_cc o_cc1">
                 <div class="container">
                     <div class="row">
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">First Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Second Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Third Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Last Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                     </div>
                 </div>
             </section>
         </field>
     </record>
    

Field | Description  
---|---  
is_mega_menu | Enable the mega menu feature.  
mega_menu_classes | Custom classes to be added to the main element  
mega_menu_content | The default content of the mega menu  
  
Beside that, you might need to create something more visually advanced with a custom template. Feel free to check how the [standard templates](https://github.com/odoo/odoo/blob/17.0/addons/website/views/snippets/s_mega_menu_odoo_menu.xml) are built in the Odoo source code.

### Custom template¶

Create your own template and add it to the list.

**Layout**

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="s_mega_menu_airproof" name="Airproof" groups="base.group_user">
        <section class="s_mega_menu_airproof o_cc o_cc1 pt40">
            <!-- Content -->
        </section>
    </template>
    

**Option**

Use the following code to add an option for your new custom mega menu on the Website Builder.

`/website_airproof/data/presets.xml`¶
    
    
    <template id="snippet_options" inherit_id="website.snippet_options" name="Airproof - Mega Menu Options">
        <xpath expr="//*[@data-name='mega_menu_template_opt']/*" position="before">
            <t t-set="_label">Airproof</t>
            <we-button t-att-data-select-label="_label"
                data-select-template="website_airproof.s_mega_menu_airproof"
                data-img="/website_airproof/static/src/img/builder/header_opt.svg"
                t-out="_label"/>
        </xpath>
    </template>
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos/website_themes/navigation.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages.html "Pages") |
  * [precedente](layout.html "Layout") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Navigation


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration