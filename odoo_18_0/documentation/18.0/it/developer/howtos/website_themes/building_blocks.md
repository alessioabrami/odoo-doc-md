# Building blocks — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shapes.html "Shapes") |
  * [precedente](media.html "Media") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Building blocks



# Building blocks¶

Building blocks, also known as snippets, are how users design and layout pages. They are important XML elements of your design.

The building blocks are classified into two types:

  1. **Structure blocks** : visually used as «whole rows» and distributed into multiples categories (Intro, Columns, Content, Images, People, etc)

  2. **Inner Content blocks** : used inside other building blocks




At the end of this chapter, you will be able to create custom snippets and to add them into a dedicated category.

## File structure¶

The layout’s file structure is the following.
    
    
    views
    ├── snippets
    │   └── options.xml
    │   └── s_snippet_name.xml
    

The styles” file structure is the following.
    
    
    static
    ├── src
    │   └── snippets
    │       └── s_snippet_name
    │           └── 000.js
    │           └── 000.scss
    │           └── 000.xml
    │           └── options.js
    

Vedi anche

[XML templates of the different snippets](https://github.com/odoo/odoo/blob/ccb78f7af2a4413836a969ff8009dc3df6c2df33/addons/website/views/snippets/snippets.xml)

Demo page

Demo data have to be installed to access this page:
    
    
    https://your-database.com/website/demo/snippets
    

## Layout¶

Snippets are editable by the user using the Website Builder. Some Bootstrap classes are important as **they trigger some Website Builder options**.

### Wrapper¶

The standard main container of any snippet is a `section`. Any section element can be edited like a block of content that you can move or duplicate.
    
    
    <section class="s_snippet_name" data-name="..." data-snippet="...">
        <!-- Content -->
    </section>
    

For inner content snippets, any other HTML tag can be used.
    
    
    <div class="s_snippet_name" data-name="..." data-snippet="...">
        <!-- Content -->
    </div>
    

Attribute | Description  
---|---  
class | Unique class name for this snippet  
data-name | Displayed in the right panel as the name of the snippet. If not found, it will fall back to _Block_.  
data-snippet | Used by the system to identify the snippet  
  
The system automatically adds the `data-name` and `data-snippet` attributes during the drag and drop based on the template’s name.

Avvertimento

Those attributes should be specifically added when a snippet is declared on a theme page.

Avvertimento

Avoid adding a `section` tag inside another `section` tag: this will trigger twice the Website Builder’s options. You can use inner content snippets instead.

Suggerimento

To write the content of a static page with standard snippets, there are two possible approaches:

  * **Pre-build the custom static pages with the Website Builder:** Drag & drop snippets, then
    

copy/paste the code into your file and clean it up.




**OR**

  * **Code everything directly:** But beware of compatibility with the Website Builder. It
    

requires certain classes, names, id, data, etc. to work properly. A good practice is to seek out the snippets code created in standard code in the Odoo source files. Pay attention that the Website Builder sometimes adds classes to the snippets after dropped in the page.




### Elements¶

There is a list of «features» we can enable/disable by using specific CSS classes.

#### Sizing¶

Any large Bootstrap columns directly descending from a `.row` element (respecting Bootstrap structure) will be triggered by the Website Builder to make them resizable.
    
    
    .row > .col-lg-*
    

Add padding on columns and `<section>`.
    
    
    class="pt80 pb80"
    

Nota

`pb*` and `pt*` are the Odoo classes used to control the handlers. Their values are increased by **multiples of 8** , till a **max of 256** (0, 8, 16, 24, 32, 40, 48, …).

Enable the columns selector.
    
    
    <div class="container s_allow_columns">
    

Disable the columns amount option.
    
    
    <div class="row s_nb_column_fixed">
    

Disable the size option for all child columns.
    
    
    <div class="row s_col_no_resize">
    

Disable the size option for one specific column.
    
    
    <div class="col-lg-* s_col_no_resize">
    

#### Colors¶

Add a background based on the color palette for columns and `<section>`.
    
    
    class="o_cc o_cc*"
    

Disable the background color option for all columns.
    
    
    <div class="row s_col_no_bgcolor">
    

Disable the background color option of one specific column.
    
    
    <div class="col-lg-* s_col_no_bgcolor">
    

Add a black color filter with an opacity of 50%.
    
    
    <section>
        <div class="o_we_bg_filter bg-black-50"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

Add a white color filter with an opacity of 85%.
    
    
    <section>
        <div class="o_we_bg_filter bg-white-85"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

Add a custom color filter.
    
    
    <section>
        <div class="o_we_bg_filter" style="background-color: rgba(39, 110, 114, 0.54) !important;"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

Add a custom gradient filter.
    
    
    <section>
        <div class="o_we_bg_filter" style="background-image: linear-gradient(135deg, rgba(255, 204, 51, 0.5) 0%, rgba(226, 51, 255, 0.5) 100%) !important;"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

#### Features¶

##### Non-editable areas¶

Make an element not editable.
    
    
    <div class="o_not_editable">
    

Make an element not removable.
    
    
    <div class="oe_unremovable">
    

##### Backgrounds¶

Add a background image and have it centered.
    
    
    <div class="oe_img_bg o_bg_img_center" style="background-image: url('...')">
    

Add parallax effect.
    
    
    <section class="parallax s_parallax_is_fixed s_parallax_no_overflow_hidden" data-scroll-background-ratio="1">
        <span class="s_parallax_bg oe_img_bg o_bg_img_center" style="background-image: url('...'); background-position: 50% 75%;"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

Nota

A video background can be set on a section. Refer to the «[Media](media.html)» chapter of this documentation.

##### Text highlights¶

Text highlights are SVG files that can be incorporated onto specific words or phrases to emphasize them. Text highlights offer customizable options for colors and thickness.
    
    
    <h2>
       Title with
       <span class="o_text_highlight o_text_highlight_fill" style="--text-highlight-width: 10px !important; --text-highlight-color: #FFFF00;">
          <span class="o_text_highlight_item">
             highlighted text
             <svg fill="none" class="o_text_highlight_svg o_content_no_merge position-absolute overflow-visible top-0 start-0 w-100 h-100 pe-none">
                <!-- SVG path -->
             </svg>
          </span>
       </span>
    </h2>
    

CSS custom property | Description  
---|---  
`--text-highlight-width` | Thickness of the SVG borders  
`--text-highlight-color` | Color of the SVG object  
  
### Grid layout¶

Grid Layout is a powerful and flexible layout system in CSS that enables users to design complex building block layouts with ease.

#### Use¶

Enable the Grid Layout by adding the `o_grid_mode` CSS class on the `row`. The number of rows in your grid is defined by the `data-row-count` attribute. The grid always contains 12 columns. The grid gap, specified in the `style` attribute, determines the gaps (or gutters) between rows and columns.
    
    
    <div class="row o_grid_mode" data-row-count="13" style="gap: 20px 10px">
       <!-- Content -->
    </div>
    

#### Items in a grid¶

Add items in the grid with the `o_grid_item` class. If the grid item contains an image, use the `o_grid_item_image` class.
    
    
    <div class="row o_grid_mode" data-row-count="13">
       <div class="o_grid_item g-height-* g-col-lg-*" style="grid-area: 2 / 1 / 7 / 8; z-index: 3;">
          <!-- Content -->
       </div>
       <div class="o_grid_item o_grid_item_image g-height-* g-col-lg-*" style="grid-area: 1 / 6 / 9 / 13; z-index: 2;">
          <img src="..." alt="..." >
       </div>
    </div>
    

The dimensions and position of a grid item are defined by the grid-area that can be explicitly set in the `style` attribute along with the z-index.

The `g-height-*` and `g-col-lg-*` classes are generated by the Website Builder for editing purposes.

#### Grid item padding¶
    
    
    <div class="row o_grid_mode" data-row-count="13" style="gap: 20px 10px;">
       <div class="o_grid_item g-height-* g-col-lg-*" style="--grid-item-padding-y: 20px; --grid-item-padding-x: 15px; grid-area: 2 / 1 / 7 / 8; z-index: 3;">
          <!-- Content -->
       </div>
    </div>
    

CSS custom property | Description  
---|---  
`--grid-item-padding-y` | Vertical paddings (Y axis)  
`--grid-item-padding-x` | Horizontal paddings (X axis)  
  
## Compatibility system¶

When a snippet has a `data-vcss`, `data-vjs` and/or `data-vxml` attribute, it means it is an updated
    

version, not the original one.
    
    
    <section class="s_snippet_name" data-vcss="001" data-vxml="001" data-js="001">
        <!-- Content -->
    </section>
    

These data attributes indicate to the system which file version to load for that snippet (e.g., `001.js`, `002.scss`).

## Custom snippet¶

Some more specific needs will require the creation of custom snippets. Here is how to create a custom snippet/

### Template¶

Create first the snippet template. Then, add it to the list and make it available via the Website Builder.

#### 1\. Declaration¶

First, create the template of the custom snippet:

`/website_airproof/views/snippets/s_airproof_snippet.xml`¶
    
    
    <?xml version="1.0" encoding="utf-8"?>
    <odoo>
    
        <template id="s_airproof_snippet" name="...">
            <section class="s_airproof_snippet">
                <!-- Content -->
            </section>
        </template>
    
    </odoo>
    

Avvertimento

`data-name` and `data-snippet` attributes have to be specified when a snippet is declared on a theme page. Otherwise, the snippet won’t be recognised by the Website Builder and issues might occur whenever a database upgrade is done. Additionally, remember that the name attribute is shown as the name of your custom snippet in the Blocks section of the options panel.

Suggerimento

  * Use Bootstrap native classes as much as possible.

  * Prefix all your custom classes.

  * Use underscore lowercase notation to name classes, e.g., `.x_nav`, `.x_nav_item`.

  * Avoid using ID attribute within your `section` as several instances of a snippet may appear throughout the page (An ID attribute has to be unique on a page).




Add the custom snippet to the list of standard snippets, so the user can drag and drop it on the page, directly from the edit panel.

#### 2\. Group creation¶

Add a group at the top of the list (feel free to the put it where needed in this list).

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="snippets" inherit_id="website.snippets" name="Airproof - Snippets">
       <!-- Create the group -->
       <xpath expr="//snippets[@id='snippet_groups']/*[1]" position="before">
          <t snippet-group="airproof" t-snippet="website.s_snippet_group" string="Airproof" t-thumbnail="/website_airproof/static/src/img/wbuilder/s_airproof_group_thumbnail.svg"/>
       </xpath>
    </template>
    

Attribute | Description  
---|---  
snippet-group | ID of the group  
t-snippet | Inherited template ID  
string | Group name displayed to the users  
t-thumbnail | The path to the thumbnail of the group  
  
#### 3\. Snippet addition¶

Then add the custom snippet into the `<snippets id="snippet_structure">` which contains all existing ones on the same level. The Website Builder will split them automatically into categories by reading the `group` attribute on the `<t t-snippet="">`

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="snippets" inherit_id="website.snippets" name="Airproof - Snippets">
       <!-- Create the group -->
       <xpath expr="//snippets[@id='snippet_groups']/*[1]" position="before">
          <t snippet-group="airproof" t-snippet="website.s_snippet_group" string="Airproof" t-thumbnail="/website_airproof/static/src/img/wbuilder/s_airproof_group_thumbnail.svg"/>
       </xpath>
    
       <!-- Add the custom snippet to the group -->
       <xpath expr="//snippets[@id='snippet_structure']/*[1]" position="before">
          <t t-snippet="website_airproof.s_airproof_snippet" string="Custom snippet" group="airproof">
             <keywords>Snippet</keywords>
          </t>
       </xpath>
    </template>
    

Attribute | Description  
---|---  
t-snippet | The snippet template to use  
group | The group in which the snippet is added.  
<keywords> | Keywords entered by the user in the search field in the Snippets panel  
  
#### Inner content snippet¶

To make a custom snippet appearing in the Inner content list, add it to the `snippet_content` instead:

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="snippets" inherit_id="website.snippets" name="Airproof - Snippets">
       <!-- Add the custom snippet to the group -->
       <xpath expr="//snippets[@id='snippet_content']/*[1]" position="before">
          <t t-snippet="website_airproof.s_airproof_snippet" string="Custom snippet" t-thumbnail="/website_airproof/static/src/img/wbuilder/s_airproof_snippet.svg" />
       </xpath>
    </template>
    

Importante

  * Don’t forget to add a `t-thumbnail` and remove the `group` attribute as this kind of building blocks is directly available in the right options panel of the Website Builder.

  * Don’t forget to add the snippet to the list of all available «Inner content» snippets.




### Options¶

Options allow users to edit a snippet’s appearance/behavior using the Website Builder. You can create snippet options easily and automatically add them to the Website Builder.

Vedi anche

[Standard snippet options](https://github.com/odoo/odoo/blob/247f28fdec788c7eb7c4288db29b931c73a23757/addons/website/views/snippets/snippets.xml)

#### Template¶

There are a bunch of commands to set the options of a custom snippet. These options can be created into `/website_airproof/views/snippets/s_airproof_snippet.xml`.

`/website_airproof/views/snippets/s_airproof_snippet.xml`¶
    
    
    <template id="s_airproof_snippet_options" inherit_id="website.snippet_options" name="Airproof - Snippets Options">
       <xpath expr="." position="inside">
          <!-- Options -->
       </xpath>
    </template>
    

Then insert the different available options:

`/website_airproof/views/snippets/s_airproof_snippet.xml`¶
    
    
    <template id="s_airproof_snippet_options" inherit_id="website.snippet_options" name="Airproof - Snippets Options">
       <xpath expr="." position="inside">
          <div data-selector=".s_airproof_snippet">
             <we-select string="Layout">
                <we-button data-select-class="">Default</we-button>
                <we-button data-select-class="s_airproof_snippet_portrait">Portrait</we-button>
                <we-button data-select-class="s_airproof_snippet_square">Square</we-button>
                <we-button data-select-class="s_airproof_snippet_landscape">Landscape</we-button>
             </we-select>
             <we-title>Space</we-title>
             <we-button-group string="Before">
                <we-button data-select-class="mt-0">1</we-button>
                <we-button data-select-class="mt-3">2</we-button>
                <we-button data-select-class="mt-5">3</we-button>
             </we-button-group>
          </div>
       </xpath>
    </template>
    

**Inner content**

Make a custom snippet «inner content» (droppable in an other building block) by extending the `so_content_addition_selector` variable which contains all CSS selectors referring to the existing inner content building blocks:

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="snippet_options" inherit_id="website.snippet_options" name="Airproof - Snippets Options">
       <xpath expr="//t[@t-set='so_content_addition_selector']" position="after">
          <t t-set="so_content_addition_selector"
             t-value="so_content_addition_selector + ', .s_airproof_snippet'" />
       </xpath>
    </template>
    

Vedi anche

[Standard «inner content» snippets declaration on Odoo’s GitHub repository](https://github.com/odoo/odoo/blob/cc05d9d50ac668eaa26363e1127f914897a4b125/addons/website/views/snippets/snippets.xml#L988)

#### Binding¶

These options use CSS selectors (class, XML tag, id, etc).

##### data-selector¶

Options are wrapped in groups. Groups can have properties that define how the included options interact with the user interface.

`data-selector` binds all the options included in the group to a particular element matching the selector value (CSS class, ID, etc). The option will appear when the matching selector is selected.
    
    
    <div data-selector="section, h1, .custom_class, #custom_id">
    

It can be used in combination with other attributes like `data-target`, `data-exclude` or `data-apply-to`.

##### data-target¶

`data-target=""` allows to apply the option to a child element of the `data-selector=""`.
    
    
    <div
       data-selector=".s_airproof_snippet"
       data-target=".row">
    

##### data-exclude¶

`data-exclude=""` allows to exclude some particular selectors from the rule.

The option appears if an `<ul>` tag (without `.navbar-nav` class) is selected¶
    
    
    <div
       data-selector="ul"
       data-exclude=".navbar-nav">
    

##### data-drop-in¶

`data-drop-in` defines the list of elements where the snippet can be dropped into.
    
    
    <div data-selector=".s_airproof_snippet" data-drop-in=".x_custom_location">
    

##### data-drop-near¶

`data-drop-near` defines the list of elements where the snippet can be dropped beside.
    
    
    <div data-selector=".s_airproof_snippet_card" data-drop-near=".card">
    

##### data-js¶

`data-js` binds a custom JavaScript methods.
    
    
    <div data-selector=".s_airproof_snippet" data-js="CustomMethodName">
    

#### Layout & fields¶

##### `<we-title>`¶

Add titles between options to categorize them.
    
    
    <we-title>Option subtitle 1</we-title>
    

##### `<we-row>`¶

Create a row in which elements is displayed next to each other.
    
    
    <we-row string="My option">
       <we-select>...</we-select>
       <we-button-group>...</we-button-group>
    </we-row>
    

The perfect example for this case is the Animation row:

##### `<we-button>`¶

This tag is used inside `<we-select>` and `<we-button-group>`.
    
    
    <we-button-group string="Before">
       <we-button data-select-class="mt-0">1</we-button>
       <we-button data-select-class="mt-3">2</we-button>
       <we-button data-select-class="mt-5">3</we-button>
    </we-button-group>
    

Add `data-select-class=""` to indicate which class is added to the targeted element when this choice is selected. Like any XML node, add other attributes allows to improve the style and/or the user experience.
    
    
    <we-button
       class="fa fa-fw fa-angle-double-right"
       title="Move to last"
       data-position="last" />
    

##### `<we-select>`¶

Formats the option as a dropdown list. Add `string=""` to indicate the field name.
    
    
    <we-select string="Layout">...</we-select>
    

##### `<we-button-group>`¶

Formats the option as buttons next to each other.
    
    
    <we-button-group string="Before">...</we-button-group>
    

##### `<we-checkbox>`¶

Formats the option as a toggle switch.
    
    
    <we-checkbox
       string="Tooltip"
       data-select-class="s_airproof_snippet_tooltip" />
    

##### `<we-range>`¶

Formats the option as a slider.
    
    
    <we-range
       string="Images Spacing"
       data-select-class="o_spc-none|o_spc-small|o_spc-medium|o_spc-big" />
    

Each step of the range is separated by a `|`. Here, each class name corresponds to a step.

##### `<we-input>`¶

Formats the option as a text field.

`data-unit`, `data-save-unit` and `data-step` are optional¶
    
    
    <we-input
       string="Speed"
       data-unit="s"
       data-save-unit="ms"
       data-step="0.1" />
    

`<we-input>` comes with optional attributes particularly useful in specific case:

Attribute | Description  
---|---  
`data-unit` | Shows the expected unit of measure.  
`data-save-unit` | Set the unit of measure to which the value entered by the user is converted and saved.  
`data-step` | Set the numerical value by which the field can be incremented.  
  
##### `<we-colorpicker>`¶

Formats the option as a color/gradient to choose from.
    
    
    <we-colorpicker
       string="Color filter"
       data-select-style="true"
       data-css-property="background-color"
       data-color-prefix="bg-"
       data-apply-to=".s_map_color_filter" />
    

Attribute | Description  
---|---  
`data-select-style` | Refers to `selectStyle` JavaScript method. Matchs the value of the `style=""` attribute applied on the target to thick the right option choice.  
`data-css-property` | Define the CSS property targeted by the colorpicker.  
`data-color-prefix` | Define the prefix applied to the CSS class returned.  
`data-apply-to` | Set the element on which the color is applied.  
  
#### Methods¶

Beside _binding options_ allowing to select, target or exclude an element. Option fields have several useful data attributes refering to standard JavaScript methods.

For example, `data-select-class` refers to the JavaScript method named `selectClass`.

##### Built-in methods¶

###### Selection¶

There are several built-in methods available. They are callable by using the related data attribute directly into the XML template.

Data attributes | Description  
---|---  
`data-select-class` | Allows to select one and only one class in the option classes set and set it on the associated snippet.  
`data-select-data-attribute` \+ `data-attribute-name` | Allows to select a value and set it on the associated snippet as an attribute. The attribute name is given by the `data-attribute-name` attribute.  
`data-select-property` \+ `data-property-name` | Allows to select a value and set it on the associated snippet as a property. The attribute name is given by the `data-property-name` attribute.  
`data-select-style` \+ `data-css-property` | Allows to select a value and set it on the associated snippet as a CSS style. The attribute name is given by the `data-css-property` attribute.  
`data-select-color-combination` | Enable the selection of a color palette. **Only for** `<we-colorpicker>`  
  
###### Events¶

There are also built-in methods directly linked to events the Website Builder listens to:

Name | Description  
---|---  
start | Occurs when the publisher selects the snippet for the first time in an editing session or when the snippet is drag-and-dropped on the page.  
destroy | Occurs after the publisher has saved the page.  
onFocus | Occurs each time the snippet is selected by the user or when the snippet is drag-and-dropped on the page.  
onBlur | Occurs when a snippet loses focus.  
onClone | Occurs just after a snippet is duplicated.  
onRemove | Occurs just before the snippet is removed.  
onBuilt | Occurs just after the snippet is drag-and-dropped on a drop zone. When this event is triggered, the content is already inserted in the page.  
cleanForSave | Occurs before the publisher saves the page.  
  
Vedi anche

  * [Web Editor - JavaScript methods related to snippet options on GitHub](https://github.com/odoo/odoo/blob/cc05d9d50ac668eaa26363e1127f914897a4b125/addons/web_editor/static/src/js/editor/snippets.options.js#L3512)

  * [XML templates of the different standard snippets](https://github.com/odoo/odoo/blob/cc05d9d50ac668eaa26363e1127f914897a4b125/addons/website/views/snippets/snippets.xml)




##### Custom methods¶

To create custom JavaScript methods, a link between the options group and the custom methods has to be created. To do so, a JavaScript class has to be created and called in the XML template with `data-js`.

Add the `data-js` attribute to your options group:
    
    
    <template id="s_airproof_snippet_options" inherit_id="website.snippet_options" name="Airproof - Snippets Options">
       <xpath expr="." position="inside">
          <div data-selector=".s_airproof_snippet" data-js="airproofSnippet">
             // Options
          </div>
       </xpath>
    </template>
    

Then, the class can be created in a JavaScript file:

`/website_airproof/static/src/s_airproof_snippet/options.js`¶
    
    
    /** @odoo-module */
    
    import options from 'web_editor.snippets.options';
    
    const AirproofSnippet = options.Class.extend({
       // Built-in method example
       start: function() {
          //...
       }
       // Custom method example
       customMethodName: function() {
          //...
       }
    });
    
    options.registry.AirproofSnippet = AirproofSnippet;
    
    export default AirproofSnippet;
    

Finally, the custom method can be called on your custom option through the XML template:
    
    
    <template id="s_airproof_snippet_options" inherit_id="website.snippet_options" name="Airproof - Snippets Options">
       <xpath expr="." position="inside">
          <div data-selector=".s_airproof_snippet" data-js="airproofSnippet">
             <we-checkbox data-custom-method-name="" />
          </div>
       </xpath>
    </template>
    

### Dynamic Content templates¶

By default, Dynamic Content blocks have a selection of templates available in the Website Builder. Custom templates can also be added to the list automatically by use the same naming convention for the template id attribute.

#### Call the template¶

The selected dynamic snippet replace the `<div class="dynamic_snippet_template"/>` placeholder by the right template based on the `data-template-key` and the custom CSS class:
    
    
    <section
       data-snippet="s_blog_posts"
       data-name="Blog Posts"
       class="s_blog_post_airproof s_dynamic_snippet_blog_posts s_blog_posts_effect_marley s_dynamic pb32 o_cc o_cc2 o_dynamic_empty"
       data-template-key="website_airproof.dynamic_filter_template_blog_post_airproof"
       data-filter-by-blog-id="-1"
       data-number-of-records="3"
       data-number-of-elements="3"
    >
       <div class="container o_not_editable">
          <div class="css_non_editable_mode_hidden">
                <div class="missing_option_warning alert alert-info rounded-0 fade show d-none d-print-none">
                   Your Dynamic Snippet will be displayed here... This message is displayed because you did not provided both a filter and a template to use.<br/>
                </div>
          </div>
          <div class="dynamic_snippet_template"/>
       </div>
    </section>
    

#### Examples¶

Blog postsProductsEvents

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="dynamic_filter_template_blog_post_airproof" name="...">
       <div t-foreach="records" t-as="data" class="s_blog_posts_post">
          <t t-set="record" t-value="data['_record']"/>
          <!-- Content -->
       </div>
    </template>
    

Attribute | Description  
---|---  
id | The ID of the template. Has to start with `dynamic_filter_template_blog_post_`  
name | Human-readable name of the template  
  
`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="dynamic_filter_template_product_product_airproof" name="...">
       <t t-foreach="records" t-as="data" data-number-of-elements="4" data-number-of-elements-sm="1" data-number-of-elements-fetch="8">
          <t t-set="record" t-value="data['_record']"/>
          <!-- Content -->
       </t>
    </template>
    

Attribute | Description  
---|---  
id | The ID of the template. Has to start with `dynamic_filter_template_product_product_`  
name | Human-readable name of the template  
data-number-of-elements | Number of products per slide on desktop  
data-number-of-elements-sm | Number of products per slide on mobile  
data-number-of-elements-fetch | The total amount of fetched products  
  
`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="dynamic_filter_template_event_event_airproof" name="...">
       <div t-foreach="records" t-as="data" class="s_events_event">
          <t t-set="record" t-value="data['_record']._set_tz_context()"/>
          <!-- Content -->
       </div>
    </template>
    

Attribute | Description  
---|---  
id | The ID of the template. Has to start with `dynamic_filter_template_event_event_`  
name | Human-readable name of the template  
  
[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/howtos/website_themes/building_blocks.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](shapes.html "Shapes") |
  * [precedente](media.html "Media") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Building blocks


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