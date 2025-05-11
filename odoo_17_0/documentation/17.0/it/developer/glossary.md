# Glossary — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * Glossary



# Glossary¶

external id¶
external identifier¶
external identifiers¶
    

string identifier stored in `ir.model.data`, can be used to refer to a record regardless of its database identifier during data imports or export/import roundtrips.

External identifiers are in the form `_module_._id_` (e.g. `account.invoice_graph`). From within a module, the `_module_.` prefix can be left out.

Sometimes referred to as «xml id» or `xml_id` as XML-based [Data Files](reference/backend/data.html#reference-data) make extensive use of them.

format string¶
    

inspired by [jinja variables](http://jinja.pocoo.org/docs/dev/templates/#variables), format strings allow more easily mixing literal content and computed content (expressions): content between `{{` and `}}` is interpreted as an expression and evaluated, other content is interpreted as literal strings and displayed as-is

GIS¶
Geographic Information System¶
    

any computer system or subsystem to capture, store, manipulate, analyze, manage or present spatial and geographical data.

minified¶
minification¶
    

process of removing extraneous/non-necessary sections of files (comments, whitespace) and possibly recompiling them using equivalent but shorter structures ([ternary operator](http://en.wikipedia.org/wiki/%3F:) instead of `if/else`) in order to reduce network traffic

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/glossary.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * Glossary