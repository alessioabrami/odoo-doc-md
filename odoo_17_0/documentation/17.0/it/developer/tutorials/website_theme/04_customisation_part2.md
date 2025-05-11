# Chapter 4 - Customisation, Part II — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](05_dynamic_templates.html "Chapter 5 - Dynamic templates") |
  * [precedente](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 4 - Customisation, Part II



# Chapter 4 - Customisation, Part II¶

## Create a custom background shape¶

Shapes are decorative elements that can be applied to backgrounds or images. They are SVG files that can be animated and customized with different colors.

  1. To better align with the website’s desired atmosphere, create a custom background shape that the client can reuse on different blocks.

Create your custom shape using the following setup:

     * Declare your shape. You can find the original [SVG shape here](https://github.com/odoo/tutorials/blob/17.0/website_airproof/shape-waves.svg).

     * Set the base color of the shape to the theme’s green, and add it to the list of available shapes.




Vedi anche

See reference documentation on how to add a [custom background shapes](../../howtos/website_themes/shapes.html#website-themes-shapes-bg-custom).

Suggerimento

**Be careful,** there is a trick!

In your shape SVG file, you have to use the colors from the default Odoo palette.

Here, I want it to match my primary color 3 (`#CEF8A1`). Therefore, in the SVG file, you must use color 3 from Odoo’s default palette (`#F6F6F6`).

Solutions

Find the solution in our Airproof example for:

  * the shape declaration on [shapes.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/shapes.xml).

  * adding the shape to the list thanks to [primary_variable.scss](https://github.com/odoo/tutorials/blob/17.0/website_airproof/static/src/scss/primary_variables.scss) and [option.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/views/snippets/options.xml).




  2. Based on the Airproof design, apply the shape you just added to a `Text-Image` building block on the homepage:

     * Ensure the shape is in the right position.

     * Set its color to the theme’s light blue.




Vedi anche

See reference documentation on how to use [background shapes](../../howtos/website_themes/shapes.html#website-themes-shapes-bg-custom-use).

Suggerimento

Unlike a standard Odoo shapes, when applying a custom shape to a section, replace `web_editor` with `illustration` in the shape class.

Solutions

`/website_airproof/data/pages/home.xml`¶
    
    
    <!-- Text-image block & Background shape -->
    <section class="s_text_image o_cc o_cc5 o_colored_level pt120 pb96"
    data-snippet="s_image_text" data-name="Image - Text" style="background-color: rgb(41, 128,
    187);" data-oe-shape-data="{'shape': 'illustration/airproof/waves', 'colors': {'c3': '#BBE1FA'},
    'flip': ['x']}">
       <div class="o_we_shape o_illustration_airproof_waves o_we_flip_x" style="background-image:
       url('/web_editor/shape/illustration%2Fairproof%2Fwaves.svg?c2=%23BBE1FA');
       background-position: 100% 100%;"/>
       [...]
    </section>
    

## Add a background gradient¶

Apply a custom background gradient to your ” _Latest products_ ” block, transitioning from blue `rgb(11, 142, 230)` to dark blue `rgb(41, 128, 187)`.

Vedi anche

See reference documentation on how to use [Gradients](../../howtos/website_themes/gradients.html).

Solutions

`/website_airproof/data/pages/home.xml`¶
    
    
    <!-- Latest products section -->
    <section class="s_parallax o_colored_level o_cc o_cc5 s_parallax_no_overflow_hidden pt40 pb32"
    data-scroll-background-ratio="0" data-snippet="s_parallax" data-name="Parallax"
    style="background-image: linear-gradient(0deg, rgb(41, 128, 187) 0%, rgb(11, 142, 230) 100%)
    !important;">
       [...]
    </section>
    

## Animations¶

The client loves the overall design but finds the page a bit static. Enhance page interactivity with animations such as `fade-in`, `rotate`, `bounce`, etc. These can be applied to columns, images, texts, buttons…

Based on the airproof design, animate the following elements:

  * the text of the first slide of the carousel.

  * the sticker and the photo of the drone from the first slide.

  * the 4 columns with icons.




Adjust animation delays for smoother transitions.

Vedi anche

See reference documentation on how to apply [Animations](../../howtos/website_themes/animations.html).

Solutions

Find the solution in our Airproof example on [home.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/pages/home.xml).

Image animation¶
    
    
    <img src="/web/image/website_airproof.img_sticker" class="img img-fluid position-absolute
    x_sticker o_animate o_anim_rotate_in o_visible" style="animation-delay: 0.8s;
    --wanim-intensity: 30;"/>
    
    <img src="/web/image/website_airproof.img_drone" class="img img-fluid o_animate
    o_anim_zoom_out o_visible" alt="Drone"/>
    

Text animation¶
    
    
    <span class="o_animated_text o_animate o_anim_fade_in o_anim_from_bottom o_visible">One
    step</span>
    

Columns animation¶
    
    
    <div class="o_grid_item o_colored_level g-height-7 g-col-lg-3 col-lg-3 text-center
    o_anim_fade_in o_animate o_anim_from_bottom o_visible" style="z-index: 2;
    grid-area: 6 / 1 / 12 / 4; --wanim-intensity: 15;">
    </div>
    

## Forms¶

The forms in Odoo are very powerful. They can send emails directly to a personal inbox or integrate directly with other Odoo applications. This is great, as one of your client’s main priorities is after-sales service. Therefore, the contact form must be properly configured.

Based on the airproof design, create a contact page. Remember to disable the default one and add the new page link to the menu. The client has the following requests for their contact form:

  * _Name_ and _email address_ field.

  * _Company name_ field.

  * _Conditional VAT_ field displayed only if _Company name_ is filled in.

  * All fields should be mandatory, except for _Company name_.

  * Form submission must trigger an email.

  * After form submission, the `thank-you message` should remain visible on the contact page.




Vedi anche

See reference documentation on how to:

>   * [deactivate default pages](../../howtos/website_themes/pages.html#website-themes-pages-default),
> 
>   * [create a new page](../../howtos/website_themes/pages.html#website-themes-pages-theme-pages),
> 
>   * [add a menu item](../../howtos/website_themes/navigation.html#website-themes-navigation-menu),
> 
>   * [create a form](../../howtos/website_themes/forms.html).
> 
> 


Suggerimento

To determine the correct code for your form:

  * Create a test page via the Website Builder.

Drag & drop the building block that interests you and apply the right design.

Use the code generated through Editor HTML/SCSS.

  * You can also find the original building block code in Odoo: [odoo/addons/website/views/snippets/s_website_form.xml](https://github.com/odoo/odoo/blob/17.0/addons/website/views/snippets/s_website_form.xml).




Solutions

Find the solution in our Airproof example on [contact.xml](https://github.com/odoo/tutorials/blob/17.0/website_airproof/data/pages/contact.xml).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/website_theme/04_customisation_part2.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](05_dynamic_templates.html "Chapter 5 - Dynamic templates") |
  * [precedente](03_customisation_part1.html "Chapter 3 - Customisation, Part I") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 4 - Customisation, Part II


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration