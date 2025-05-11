# Layout — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](navigation.html "Navigation") |
  * [precedente](theming.html "Theming") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Layout



# Layout¶

In this chapter, you will learn how to:

  * Create a custom header.

  * Create a custom footer.

  * Modify a standard template.

  * Add a copyright section.

  * Improve your website’s responsiveness.




## Default¶

An Odoo page combines cross-page and unique elements. Cross-page elements are the same on every page, while unique elements are only related to a specific page. By default, a page has two cross-page elements, the header and the footer, and a unique main element that contains the specific content of that page.
    
    
    <div id="wrapwrap">
       <header/>
          <main>
             <div id="wrap" class="oe_structure">
                <!-- Page Content -->
             </div>
          </main>
       <footer/>
    </div>
    

Any Odoo XML file starts with encoding specifications. After that, you must write your code inside an `<odoo>` tag.
    
    
    <?xml version="1.0" encoding="utf-8" ?>
    <odoo>
       ...
    </odoo>
    

Nota

Using precise template names is important to find information through all modules quickly. Template names should only contain lowercase alphanumerics and underscores.

Always add an empty line at the end of your file. This can be done automatically by configuring your IDE.

## XPath¶

XPath (XML Path Language) is an expression language that enables you to navigate through elements and attributes in an XML document easily. XPath is used to extend standard Odoo templates.

A view is coded the following way.
    
    
    <template id="..." inherit_id="..." name="...">
       <!-- Content -->
    </template>
    

Attribute | Description  
---|---  
id | ID of the modified view  
inherited_id | ID of the standard view (using the following pattern: `module.template`)  
name | Human-readable name of the modified view  
  
For each XPath, you modify two attributes: **expression** and **position**.

Example

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="layout" inherit_id="website.layout" name="Welcome Message">
       <xpath expr="//header" position="before">
          <!-- Content -->
       </xpath>
    </template>
    

This XPath adds a welcome message right before the page content.

Avvertimento

Be careful when replacing default elements” attributes. As your theme extends the default one, your changes will take priority over any future Odoo update.

Nota

  * You should update your module every time you create a new template or record.

  * _XML IDs_ of inheriting views should use the same _ID_ as the original record. It helps to find all inheritance at a glance. As final _XML IDs_ are prefixed by the module that creates them, there is no overlap.




### Expressions¶

XPath uses path expressions to select nodes in an XML document. Selectors are used inside the expression to target the right element. The most useful ones are listed below.

Descendent selectors | Description  
---|---  
/ | Selects from the root node.  
// | Selects nodes in the document from the current node that matches the selection no matter where they are.  
Attribute selectors | Description  
---|---  
* | Selects any XML tag. `*` can be replaced by a specific tag if the selection needs to be more precise.  
*[@id=»id»] | Selects a specific ID.  
*[hasclass(«class»)] | Selects a specific class.  
*[@name=»name»] | Selects a tag with a specific name.  
*[@t-call=»t-call»] | Selects a specific t-call.  
  
### Position¶

The position defines where the code is placed inside the template. The possible values are listed below:

Position | Description  
---|---  
replace | Replaces the targeted node with the XPath content.  
inside | Adds the XPath content inside the targeted node.  
before | Adds the XPath content before the targeted node.  
after | Adds the XPath content after the targeted node.  
attributes | Adds the XPath content inside an attribute.  
  
Example

This XPath removes the first element with a `.breadcrumb` class.
    
    
    <xpath expr="//*[hasclass('breadcrumb')]" position="replace"/>
    

This XPath adds an extra `<li>` element after the last child of the `<ul>` element.
    
    
    <xpath expr="//ul" position="inside">
       <li>Last element of the list</li>
    </xpath>
    

This XPath adds a `<div>` before the `<nav>` that is a direct child of the `<header>`.
    
    
    <xpath expr="//header/nav" position="before">
       <div>Some content before the header</div>
    </xpath>
    

This XPath removes `x_airproof_header` in the class attribute of the header. In this case, you don’t need to use the `separator` attribute.
    
    
    <xpath expr="//header" position="attributes">
       <attribute name="class" remove="x_airproof_header" />
    </xpath>
    

This XPath adds `x_airproof_header` in the class attribute of the header. You also need to define a `separator` attribute to add a space before the class you are adding.
    
    
    <xpath expr="//header" position="attributes">
       <attribute name="class" add="x_airproof_header" separator=" "/>
    </xpath>
    

This XPath moves the element with `.o_footer_scrolltop_wrapper` class before the element with the
    

`footer` ID attribute.
    
    
    <xpath expr="//div[@id='footer']" position="before">
       <xpath expr="//div[@id='o_footer_scrolltop_wrapper']" position="move" />
    </xpath>
    

Suggerimento

Using `move` directives inside an other XPath forces you to use only this kind of directives.

Example

**Good example:**
    
    
    <xpath expr="//*[hasclass('o_wsale_products_main_row')]" position="before">
    <xpath expr="//t[@t-if='opt_wsale_categories_top']" position="move" />
    </xpath>
    <xpath expr="//*[hasclass('o_wsale_products_main_row')]" position="before">
    <div><!-- Content --></div>
    </xpath>
    

**Bad example:**
    
    
    <xpath expr="//*[hasclass('o_wsale_products_main_row')]" position="before">
    <xpath expr="//t[@t-if='opt_wsale_categories_top']" position="move" />
    <div><!-- Content --></div>
    </xpath>
    

Vedi anche

You can find more information about XPath in this [cheat sheet](https://devhints.io/xpath).

## QWeb¶

QWeb is the primary templating engine used by Odoo. It is an XML templating engine mainly used to generate HTML fragments and pages.

Vedi anche

[QWeb templates documentation](../../reference/frontend/qweb.html).

## Custom fields¶

Depending on your needs, you can create custom fields to save data in the database.

### Declaration¶

First, create a record to declare the field. This field has to be linked to an existing model.

`/website_airproof/data/fields.xml`¶
    
    
    <record id="x_post_category" model="ir.model.fields">
       <field name="name">x_post_category</field>
       <field name="field_description">...</field>
       <field name="ttype">html</field>
       <field name="state">manual</field>
       <field name="index">0</field>
       <field name="model_id" ref="website_blog.model_blog_post"/>
    </record>
    

Nota

Fields creation is also possible (and recommended) through [a model using Python](https://www.odoo.com/developer/tutorials/backend).

### Back-end¶

Add the field to the relevant view through an XPath. Therefore, the user can see the field in the interface and fill it afterwards.

`/website_airproof/views/backend/website_blog_views.xml`¶
    
    
    <record id="view_blog_post_form_category" model="ir.ui.view">
       <field name="name">view_blog_post_form_category</field>
       <field name="model">blog.post</field>
       <field name="inherit_id" ref="website_blog.view_blog_post_form"/>
       <field name="arch" type="xml">
          <xpath expr="//field[@name='blog_id']" position="before">
             <field name="x_post_category" string="..." placeholder="..."/>
          </xpath>
       </field>
    </record>
    

### Front-end¶

The field value can be shown somewhere in a page by calling `model_name.field_name` like this:

`/website_airproof/views/website_blog_templates.xml`¶
    
    
    <h1 t-field="blog_post.x_post_category"/>
    

## Background¶

You can define a color or an image as the background of your website.

### Colors¶

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-color-palettes: map-merge($o-color-palettes,
       (
          'airproof': (
             'o-cc1-bg':                     'o-color-5',
             'o-cc5-bg':                     'o-color-1',
          ),
        )
    );
    

### Image/pattern¶

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-website-values-palettes: (
       (
          'body-image': '/website_airproof/static/src/img/background-lines.svg',
          'body-image-type': 'image' or 'pattern'
       )
    );
    

## Header¶

By default, the header contains two distinct templates (desktop and mobile) which display the main navigation, the company’s logo and other optional elements (call-to-action, language selector, etc). Depending on the situation, choose between enabling/disabling existing elements with a standard template or building a brand new custom template.

### Standard¶

The Odoo Website Builder distinguishes between desktop templates and the mobile template in order to facilitate the adaptation of the user experience according to the device.

#### Desktop template¶

Enable one of the header default templates.

Importante

Don’t forget that you may need to disable the active header template first.

Example

`/website_aiproof/data/presets.xml`¶
    
    
    <record id="website.template_header_default" model="ir.ui.view">
       <field name="active" eval="False"/>
    </record>
    

Explicitly set the desired template in the `primary_variables.scss` file.

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-website-values-palettes: (
       (
          'header-template': 'Contact',
       ),
    );
    

`/website_airproof/data/presets.xml`¶
    
    
    <record id="website.template_header_contact" model="ir.ui.view">
       <field name="active" eval="True"/>
    </record>
    

#### Mobile template¶

Each header template comes with the `template_header_mobile` template ensuring a seamless user experience accross every devices.

Vedi anche

[Mobile header template on Odoo’s Git repository](https://github.com/odoo/odoo/blob/43b20e6e52526c415e28c21810cd7023f6feef1e/addons/website/views/website_templates.xml#L354)

### Custom¶

Create your own template and add it to the list.

Importante

Don’t forget that you may need to disable the active header template first.

**Option**

Use the following code to add an option for your new custom header on the Website Builder.

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="template_footer_opt" inherit_id="website.snippet_options" name="Footer Template - Option">
       <xpath expr="//we-select[@data-variable='footer-template']" position="inside">
          <we-button title="airproof"
             data-customize-website-views="website_airproof.footer"
             data-customize-website-variable="'airproof'"  data-img="/website_airproof/static/src/img/wbuilder/template_footer_opt.svg"/>
       </xpath>
    </template>
    

Attribute | Description  
---|---  
data-customize-website-views | The template to enable  
data-customize-website-variable | The name given to the variable  
data-img | The thumbnail of the custom template shown in the templates selection on the Website Builder  
  
Now you have to explicitly define that you want to use your custom template in the Odoo SASS variables.

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-website-values-palettes: (
       (
          'header-template': 'airproof',
       ),
    );
    

**Template**

`/website_airproof/views/website_templates.xml`¶
    
    
    <record id="header" model="ir.ui.view">
       <field name="name">Airproof Header</field>
       <field name="type">qweb</field>
       <field name="key">website_airproof.header</field>
       <field name="inherit_id" ref="website.layout"/>
       <field name="mode">extension</field>
       <field name="arch" type="xml">
          <xpath expr="//header//nav" position="replace">
             <!-- Static Content -->
             <!-- Components -->
             <!-- Editable areas -->
          </xpath>
       </field>
    </record>
    

Don’t forget to adapt the `template_header_mobile` accordingly to keep consistency between desktop and mobile:

`website_airproof/views/website_templates.xml`¶
    
    
    <template id="template_header_mobile" inherit_id="website.template_header_mobile" name="Airproof - Template Header Mobile">
       <!-- Xpaths -->
    </template>
    

### Components¶

In your custom header, you can call several sub-templates using the `t-call` directive from QWeb:

#### Logo¶
    
    
    <t t-call="website.placeholder_header_brand">
       <t t-set="_link_class" t-valuef="..."/>
    </t>
    

Importante

Don’t forget to [create a record of the website logo](media.html#website-themes-media-images-use-logo) logo in the database.

#### Menu¶
    
    
    <t t-foreach="website.menu_id.child_id" t-as="submenu">
       <t t-call="website.submenu">
          <t t-set="item_class" t-valuef="nav-item"/>
          <t t-set="link_class" t-valuef="nav-link"/>
       </t>
    </t>
    

#### Sign in¶
    
    
    <t t-call="portal.placeholder_user_sign_in">
       <t t-set="_item_class" t-valuef="nav-item"/>
       <t t-set="_link_class" t-valuef="nav-link"/>
    </t>
    

#### User dropdown¶
    
    
    <t t-call="portal.user_dropdown">
       <t t-set="_user_name" t-value="true"/>
       <t t-set="_icon" t-value="false"/>
       <t t-set="_avatar" t-value="false"/>
       <t t-set="_item_class" t-valuef="nav-item dropdown"/>
       <t t-set="_link_class" t-valuef="nav-link"/>
       <t t-set="_dropdown_menu_class" t-valuef="..."/>
    </t>
    

#### Language selector¶
    
    
    <t t-call="website.placeholder_header_language_selector">
       <t t-set="_div_classes" t-valuef="..."/>
    </t>
    

#### Call to action¶
    
    
    <t t-call="website.placeholder_header_call_to_action">
       <t t-set="_div_classes" t-valuef="..."/>
    </t>
    

#### Navbar toggler¶
    
    
    <t t-call="website.navbar_toggler">
       <t t-set="_toggler_class" t-valuef="..."/>
    </t>
    

Vedi anche

You can add a [header overlay](pages.html#website-themes-pages-theme-pages-header-overlay) to position your header over the content of your page. It has to be done on each page individually.

## Footer¶

By default, the footer contains a section with some static content. You can easily add new elements or create your own template.

### Standard¶

Enable one of the default footer templates. Don’t forget that you may need to disable the active footer template first.

Importante

Don’t forget that you may need to disable the active footer template first.

Example

`/website_aiproof/data/presets.xml`¶
    
    
    <record id="website.footer_custom" model="ir.ui.view">
       <field name="active" eval="False"/>
    </record>
    

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-website-values-palettes: (
       (
          'footer-template': 'Links',
       ),
    );
    

`/website_airproof/data/presets.xml`¶
    
    
    <record id="website.template_footer_links" model="ir.ui.view">
       <field name="active" eval="True"/>
    </record>
    

### Custom¶

Create your own template and add it to the list. Don’t forget that you may need to disable the active footer template first.

**Option**

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="template_header_opt" inherit_id="website.snippet_options" name="Footer Template - Option">
       <xpath expr="//we-select[@data-variable='footer-template']" position="inside">
          <we-button title="airproof"
             data-customize-website-views="website_airproof.footer"
             data-customize-website-variable="'airproof'"
             data-img="/website_airproof/static/src/img/wbuilder/template_header_opt.svg"/>
       </xpath>
    </template>
    

**Declaration**

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-website-values-palettes: (
       (
          'footer-template': 'airproof',
       ),
    );
    

**Template**

`/website_airproof/views/website_templates.xml`¶
    
    
    <record id="footer" model="ir.ui.view">
       <field name="name">Airproof Footer</field>
       <field name="type">qweb</field>
       <field name="key">website_airproof.footer</field>
       <field name="inherit_id" ref="website.layout"/>
       <field name="mode">extension</field>
       <field name="arch" type="xml">
          <xpath expr="//div[@id='footer']" position="replace">
             <div id="footer" class="oe_structure oe_structure_solo" t-ignore="true" t-if="not no_footer">
                <!-- Content -->
             </div>
          </xpath>
       </field>
    </record>
    

## Copyright¶

There is only one template available at the moment for the copyright bar.

To replace the content or modify its structure, you can add your own code to the following XPath.

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="copyright" inherit_id="website.layout">
       <xpath expr="//div[hasclass('o_footer_copyright')]" position="replace">
          <div class="o_footer_copyright" data-name="Copyright">
             <!-- Content -->
          </div>
       </xpath>
    </template>
    

## Drop zone¶

Instead of defining the complete layout of a page, you can create building blocks (snippets) and let the user choose where to drag and drop them, creating the page layout on their own. We call this _modular design_.

You can define an empty area that the user can fill with snippets.
    
    
    <div id="oe_structure_layout_01" class="oe_structure"/>
    

Class | Description  
---|---  
oe_structure | Define a drag-and-drop area for the user.  
oe_structure_solo | Only one snippet can be dropped in this area.  
oe_structure_not_nearest | If a building block is dropped outside of a Drop zone having this class, the block will be moved in the nearest Drop Zone.  
  
You can also populate an existing drop zone with your content.
    
    
    <template id="oe_structure_layout_01" inherit_id="..." name="...">
       <xpath expr="//*[@id='oe_structure_layout_01']" position="replace">
          <div id="oe_structure_layout_01" class="oe_structure oe_structure_solo">
             <!-- Content -->
          </div>
       </xpath>
    </template>
    

## Responsive¶

Odoo in general relies on the Bootstrap framework which eases the responsiveness of your website on
    

desktop and mobile. On Odoo 16, you can mainly take action on 3 aspects:

  1. Automatic computed font sizes depending on the device

  2. Column sizes on desktop (the columns are automatically stacked on mobile)

  3. Visibility conditions (Show/Hide something on desktop/mobile)




Vedi anche

  * [Bootstrap documentation on display property](https://getbootstrap.com/docs/5.3/utilities/display/)




### Font sizes¶

In Bootstrap 5, responsive font sizes are enabled by default, allowing text to scale more naturally across device and viewport sizes (relying on the `$enable-rfs` variable).

Vedi anche

  * [Bootstrap documentation about responsive font sizes](https://getbootstrap.com/docs/5.3/getting-started/rfs/)




### Column sizes¶

Bootstrap uses a grid made of rows and columns to layout a page. Thanks to this structure, columns can be sized differently on mobile and desktop. In this version, the Website Builder allows to set mobile sizes (`col-12` for example) and desktop ones (`col-lg-4` for example) but not the medium breakpoints (`col-md-4` for example).

Avvertimento

The medium sizes can be set but the end-user is not able to edit them within the Website Builder.

Vedi anche

  * [Bootstrap documentation on responsive breakpoints](https://getbootstrap.com/docs/5.3/layout/breakpoints/)

  * [Bootstrap documentation about the grid](https://getbootstrap.com/docs/5.3/layout/grid/)




### Visibility conditions¶

In the Odoo Website Builder, entire sections or specific columns can be hidden on mobile or desktop.
    

This functionality leverages Bootstrap along with Odoo-specific classes:

  * `o_snippet_mobile_invisible`

  * `o_snippet_desktop_invisible`




Hide a section on desktop:
    
    
    <section class="s_text_block o_cc o_cc1 o_colored_level pt16 pb16 d-lg-none o_snippet_desktop_invisible" data-snippet="s_text_block" name="Text">
        <!-- Content -->
    </section>
    

Hide a column on mobile:
    
    
    <section class="s_text_block o_cc o_cc1 o_colored_level pt16 pb16" data-snippet="s_text_block" name="Text">
       <div class="container s_allow_columns">
          <div class="row">
             <div class="col-12 col-lg-6 d-none d-lg-block o_snippet_mobile_invisible">
                Column 1
             </div>
             <div class="col-12 col-lg-6">
                Column 2
             </div>
          </div>
       </div>
    </section>
    

Class | Description  
---|---  
o_snippet_mobile_invisible | It tells the Website Builder that the element is hidden and is using visibility conditions option.  
o_snippet_desktop_invisible | It tells the Website Builder that the element is hidden **on desktop and** is using visibility conditions option.  
d-none | Hide the element in every situations.  
d-lg-block | Show the element from the «large» breakpoint (on desktop).  
  
Importante

`o_snippet_mobile_invisible` / `o_snippet_desktop_invisible` classes have to be specified to keep
    

the visibility conditions option functional. Even if an element is hidden on desktop, the Website Builder displays a list of these elements allowing the end-user to force show the element and edit it without switching between mobile and desktop mode.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/howtos/website_themes/layout.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](navigation.html "Navigation") |
  * [precedente](theming.html "Theming") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Layout


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Point of Sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format