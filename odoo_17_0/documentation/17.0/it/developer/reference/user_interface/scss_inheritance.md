# SCSS inheritance — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](icons.html "UI icons") |
  * [precedente](view_architectures.html "View architectures") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [User interface](../user_interface.html) »
  * SCSS inheritance



# SCSS inheritance¶

## Overview¶

Managing SCSS assets in Odoo is not as straightforward as it is in some other environments, but it’s highly efficient.

Modularity is key. The inheritance scheme described further allows Odoo to:

  * customize the Bootstrap CSS framework;

  * handle two different webclient designs (Community and Enterprise);

  * handle backend and frontend bundles separately (including the user’s website design);

  * contextually load only necessary assets;

  * handle multiple color-schemes (e.g.: dark-mode);




## SCSS’s `!default` directive¶

«Direct variables’ overrides» are technically possible in SCSS but may lead to inconsistent results in complex environments like Odoo.

Example

`library.scss`¶
    
    
    $foo: red;
    

`customization_layer.scss`¶
    
    
    $foo: blue; // -> Don't!
    

Indeed, since the compilation process acts across different interdependent bundles, re-assigning a variable in the «wrong spot» may lead to unexpected cascading results.

SCSS provides several techniques to overcome these issues (e.g.: [shadowing](https://sass-lang.com/documentation/variables#shadowing)), but the most critical procedure in Odoo is the use of the `!default` flag.

When using the `!default` flag, the compiler assigns a value **only** if that variable is not yet defined.

As a result of this technique, the priority in which variables are assigned matches the assets” loading order.

Example

`customization_layer.scss`¶
    
    
    $foo: red !default;
    

`library.scss`¶
    
    
    $foo: blue !default; // -> Already defined, line ignored.
    $bar: black !default; // -> Not defined yet, value assigned.
    

`component.scss`¶
    
    
    .component {
       color: $foo; // -> 'color: red;'
       background: $bar; // -> 'background: black;'
    }
    

Vedi anche

`!default` flag on the [SASS Documentation](https://sass-lang.com/documentation/variables#default-values)

## Odoo’s SCSS inheritance system¶

The following diagram conceptually illustrates the compilation order in which the CSS and SCSS variables are defined.
    
    
    ↓ [Compilation starts]
    ⏐
    ↓ web.dark_mode_variables
    ⏐   ├─ Primary Variables
    ⏐   └─ Components Variables
    ⏐
    ↓ web._assets_primary_variables
    ⏐   ├─ Primary Variables (enterprise)
    ⏐   ├─ Components Variables (enterprise)
    ⏐   ├─ Primary Variables (community)
    ⏐   └─ Components Variables (community)
    ⏐
    ↓ web._assets_bootstrap
    ⏐
    ↓ web.assets_backend
    ⏐   ├─ ...
    ⏐   ├─ CSS variables definition
    ⏐   └─ CSS variables contextual adaptations
    ⏐
    ● [Visual result on screen]
    

Importante

This diagram is incomplete and does not match the current bundles” organization. Read more on [asset bundles](../frontend/assets.html#reference-assets-bundle).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/user_interface/scss_inheritance.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](icons.html "UI icons") |
  * [precedente](view_architectures.html "View architectures") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [User interface](../user_interface.html) »
  * SCSS inheritance


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases