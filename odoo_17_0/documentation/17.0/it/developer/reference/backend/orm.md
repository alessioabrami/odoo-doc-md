# ORM API — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](orm/changelog.html "Changelog") |
  * [precedente](../backend.html "Server framework") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * ORM API



# ORM API¶

  * [Changelog](orm/changelog.html)



Object Relational Mapping module:
    

  * Hierarchical structure

  * Constraints consistency and validation

  * Object metadata depends on its status

  * Optimised processing by complex query (multiple actions at once)

  * Default field values

  * Permissions optimisation

  * Persistent object: DB postgresql

  * Data conversion

  * Multi-level caching system

  * Two different inheritance mechanisms

  * Rich set of field types:
    
    * classical (varchar, integer, boolean, …)

    * relational (one2many, many2one, many2many)

    * functional




## Models¶

Model fields are defined as attributes on the model itself:
    
    
    from odoo import models, fields
    class AModel(models.Model):
        _name = 'a.model.name'
    
        field1 = fields.Char()
    

Avvertimento

this means you cannot define a field and a method with the same name, the last one will silently overwrite the former ones.

By default, the field’s label (user-visible name) is a capitalized version of the field name, this can be overridden with the `string` parameter.
    
    
    field2 = fields.Integer(string="Field Label")
    

For the list of field types and parameters, see the fields reference.

Default values are defined as parameters on fields, either as a value:
    
    
    name = fields.Char(default="a value")
    

or as a function called to compute the default value, which should return that value:
    
    
    def _default_name(self):
        return self.get_value()
    
    name = fields.Char(default=lambda self: self._default_name())
    

API

_class _odoo.models.BaseModel[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L504)¶
    

Base class for Odoo models.

Odoo models are created by inheriting one of the following:

  * `Model` for regular database-persisted models

  * `TransientModel` for temporary data, stored in the database but automatically vacuumed every so often

  * `AbstractModel` for abstract super classes meant to be shared by multiple inheriting models




The system automatically instantiates every model once per database. Those instances represent the available models on each database, and depend on which modules are installed on that database. The actual class of each instance is built from the Python classes that create and inherit from the corresponding model.

Every model instance is a «recordset», i.e., an ordered collection of records of the model. Recordsets are returned by methods like `browse()`, `search()`, or field accesses. Records have no explicit representation: a record is represented as a recordset of one record.

To create a class that should not be instantiated, the `_register` attribute may be set to False.

_auto _ = False_¶
    

Whether a database table should be created. If set to `False`, override `init()` to create the database table.

Automatically defaults to `True` for `Model` and `TransientModel`, `False` for `AbstractModel`.

Suggerimento

To create a model without any table, inherit from `AbstractModel`.

_log_access¶
    

Whether the ORM should automatically generate and update the Access Log fields.

Defaults to whatever value was set for `_auto`.

_table _ = None_¶
    

SQL table name used by model if `_auto`

_sql_constraints _ = []_¶
    

SQL constraints [(name, sql_def, message)]

_register _ = False_¶
    

registry visibility

_abstract _ = True_¶
    

Whether the model is _abstract_.

Vedi anche

`AbstractModel`

_transient _ = False_¶
    

Whether the model is _transient_.

Vedi anche

`TransientModel`

_name _ = None_¶
    

the model name (in dot-notation, module namespace)

_description _ = None_¶
    

the model’s informal name

_inherit _ = ()_¶
    

Python-inherited models:

Type
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") or [list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")([str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)"))

Nota

  * If `_name` is set, name(s) of parent models to inherit from

  * If `_name` is unset, name of a single model to extend in-place




_inherits _ = {}_¶
    

dictionary {“parent_model”: “m2o_field”} mapping the _name of the parent business objects to the names of the corresponding foreign key fields to use:
    
    
    _inherits = {
        'a.model': 'a_field_id',
        'b.model': 'b_field_id'
    }
    

implements composition-based inheritance: the new model exposes all the fields of the inherited models but stores none of them: the values themselves remain stored on the linked record.

Avvertimento

if multiple fields with the same name are defined in the `_inherits`-ed models, the inherited field will correspond to the last one (in the inherits list order).

_rec_name _ = None_¶
    

field to use for labeling records, default: `name`

_order _ = 'id'_¶
    

default order field for searching results

_check_company_auto _ = False_¶
    

On write and create, call `_check_company` to ensure companies consistency on the relational fields having `check_company=True` as attribute.

_parent_name _ = 'parent_id'_¶
    

the many2one field used as parent field

_parent_store _ = False_¶
    

set to True to compute parent_path field.

Alongside a `parent_path` field, sets up an indexed storage of the tree structure of records, to enable faster hierarchical queries on the records of the current model using the `child_of` and `parent_of` domain operators.

_fold_name _ = 'fold'_¶
    

field to determine folded groups in kanban views

### AbstractModel¶

odoo.models.AbstractModel[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L504)¶
    

alias of `odoo.models.BaseModel`

### Model¶

_class _odoo.models.Model(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L7149)¶
    

Main super-class for regular database-persisted Odoo models.

Odoo models are created by inheriting from this class:
    
    
    class user(Model):
        ...
    

The system will later instantiate the class once per database (on which the class” module is installed).

_auto _ = True_¶
    

Whether a database table should be created. If set to `False`, override `init()` to create the database table.

Automatically defaults to `True` for `Model` and `TransientModel`, `False` for `AbstractModel`.

Suggerimento

To create a model without any table, inherit from `AbstractModel`.

_abstract _ = False_¶
    

Whether the model is _abstract_.

Vedi anche

`AbstractModel`

### TransientModel¶

_class _odoo.models.TransientModel(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L7165)¶
    

Model super-class for transient records, meant to be temporarily persistent, and regularly vacuum-cleaned.

A TransientModel has a simplified access rights management, all users can create new records, and may only access the records they created. The superuser has unrestricted access to all TransientModel records.

_transient_max_count _ = 0_¶
    

maximum number of transient records, unlimited if `0`

_transient_max_hours _ = 1.0_¶
    

maximum idle lifetime (in hours), unlimited if `0`

_transient_vacuum()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L7178)¶
    

Clean the transient records.

This unlinks old records from the transient model tables whenever the `_transient_max_count` or `_transient_max_hours` conditions (if any) are reached.

Actual cleaning will happen only once every 5 minutes. This means this method can be called frequently (e.g. whenever a new record is created).

Example with both max_hours and max_count active:

Suppose max_hours = 0.2 (aka 12 minutes), max_count = 20, there are 55 rows in the table, 10 created/changed in the last 5 minutes, an additional 12 created/changed between 5 and 10 minutes ago, the rest created/changed more than 12 minutes ago.

  * age based vacuum will leave the 22 rows created/changed in the last 12 minutes

  * count based vacuum will wipe out another 12 rows. Not just 2, otherwise each addition would immediately cause the maximum to be reached again.

  * the 10 rows that have been created/changed the last 5 minutes will NOT be deleted




## Fields¶

_class _odoo.fields.Field[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L135)¶
    

The field descriptor contains the field definition, and manages accesses and assignments of the corresponding field on records. The following attributes may be provided when instantiating a field:

Parametri
    

  * **string** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – the label of the field seen by users; if not set, the ORM takes the field name in the class (capitalized).

  * **help** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – the tooltip of the field seen by users

  * **readonly** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – 

whether the field is readonly (default: `False`)

This only has an impact on the UI. Any field assignation in code will work (if the field is a stored field or an inversable one).

  * **required** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the value of the field is required (default: `False`)

  * **index** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

whether the field is indexed in database, and the kind of index. Note: this has no effect on non-stored and virtual fields. The possible values are:

    * `"btree"` or `True`: standard index, good for many2one

    * `"btree_not_null"`: BTREE index without NULL values (useful when most
    

values are NULL, or when NULL is never searched for)

    * `"trigram"`: Generalized Inverted Index (GIN) with trigrams (good for full-text search)

    * `None` or `False`: no index (default)

  * **default** (_value_ _or_ _callable_) – the default value for the field; this is either a static value, or a function taking a recordset and returning a value; use `default=None` to discard default values for the field

  * **groups** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – comma-separated list of group xml ids (string); this restricts the field access to the users of the given groups only

  * **company_dependent** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – 

whether the field value is dependent of the current company;

The value isn’t stored on the model table. It is registered as `ir.property`. When the value of the company_dependent field is needed, an `ir.property` is searched, linked to the current company (and current record if one property exists).

If the value is changed on the record, it either modifies the existing property for the current record (if one exists), or creates a new one for the current company and res_id.

If the value is changed on the company side, it will impact all records on which the value hasn’t been changed.

  * **copy** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field value should be copied when the record is duplicated (default: `True` for normal fields, `False` for `one2many` and computed fields, including property fields and related fields)

  * **store** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field is stored in database (default:`True`, `False` for computed fields)

  * **group_operator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

aggregate function used by `read_group()` when grouping on this field.

Supported aggregate functions are:

    * `array_agg` : values, including nulls, concatenated into an array

    * `count` : number of rows

    * `count_distinct` : number of distinct rows

    * `bool_and` : true if all values are true, otherwise false

    * `bool_or` : true if at least one value is true, otherwise false

    * `max` : maximum value of all values

    * `min` : minimum value of all values

    * `avg` : the average (arithmetic mean) of all values

    * `sum` : sum of all values

  * **group_expand** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

function used to expand read_group results when grouping on the current field.
        
        @api.model
        def _read_group_selection_field(self, values, domain, order):
            return ['choice1', 'choice2', ...] # available selection choices.
        
        @api.model
        def _read_group_many2one_field(self, records, domain, order):
            return records + self.search([custom_domain])
        




Computed Fields

Parametri
    

  * **compute** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

name of a method that computes the field

Vedi anche

Advanced Fields/Compute fields

  * **precompute** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – 

whether the field should be computed before record insertion in database. Should be used to specify manually some fields as precompute=True when the field can be computed before record insertion. (e.g. avoid statistics fields based on search/read_group), many2one linking to the previous record, … (default: `False`)

Avvertimento

Precomputation only happens when no explicit value and no default value is provided to create(). This means that a default value disables the precomputation, even if the field is specified as precompute=True.

Precomputing a field can be counterproductive if the records of the given model are not created in batch. Consider the situation were many records are created one by one. If the field is not precomputed, it will normally be computed in batch at the flush(), and the prefetching mechanism will help making the computation efficient. On the other hand, if the field is precomputed, the computation will be made one by one, and will therefore not be able to take advantage of the prefetching mechanism.

Following the remark above, precomputed fields can be interesting on the lines of a one2many, which are usually created in batch by the ORM itself, provided that they are created by writing on the record that contains them.

  * **compute_sudo** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field should be recomputed as superuser to bypass access rights (by default `True` for stored fields, `False` for non stored fields)

  * **recursive** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field has recursive dependencies (the field `X` has a dependency like `parent_id.X`); declaring a field recursive must be explicit to guarantee that recomputation is correct

  * **inverse** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of a method that inverses the field (optional)

  * **search** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of a method that implement search on the field (optional)

  * **related** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – sequence of field names

  * **default_export_compatible** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – 

whether the field must be exported by default in an import-compatible export

Vedi anche

Advanced fields/Related fields




### Basic Fields¶

_class _odoo.fields.Boolean[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1417)¶
    

Encapsulates a [`bool`](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)").

_class _odoo.fields.Char[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1911)¶
    

Basic string field, can be length-limited, usually displayed as a single-line string in clients.

Parametri
    

  * **size** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – the maximum size of values stored for that field

  * **trim** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – states whether the value is trimmed or not (by default, `True`). Note that the trim operation is applied only by the web client.

  * **translate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _or_ _callable_) – enable the translation of the field’s values; use `translate=True` to translate field values as a whole; `translate` may also be a callable such that `translate(callback, value)` translates `value` by using `callback(term)` to retrieve the translation of terms.




_class _odoo.fields.Float[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1476)¶
    

Encapsulates a [`float`](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)").

The precision digits are given by the (optional) `digits` attribute.

Parametri
    

**digits** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _(_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _,_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – a pair (total, decimal) or a string referencing a `DecimalPrecision` record name.

When a float is a quantity associated with an unit of measure, it is important to use the right tool to compare or round values with the correct precision.

The Float class provides some static methods for this purpose:

`round()` to round a float with the given precision. `is_zero()` to check if a float equals zero at the given precision. `compare()` to compare two floats at the given precision.

Example

To round a quantity with the precision of the unit of measure:
    
    
    fields.Float.round(self.product_uom_qty, precision_rounding=self.product_uom_id.rounding)
    

To check if the quantity is zero with the precision of the unit of measure:
    
    
    fields.Float.is_zero(self.product_uom_qty, precision_rounding=self.product_uom_id.rounding)
    

To compare two quantities:
    
    
    field.Float.compare(self.product_uom_qty, self.qty_done, precision_rounding=self.product_uom_id.rounding)
    

The compare helper uses the __cmp__ semantics for historic purposes, therefore the proper, idiomatic way to use this helper is like so:

> if result == 0, the first and second floats are equal if result < 0, the first float is lower than the second if result > 0, the first float is greater than the second

_class _odoo.fields.Integer[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1432)¶
    

Encapsulates an [`int`](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)").

### Advanced Fields¶

_class _odoo.fields.Binary[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2334)¶
    

Encapsulates a binary content (e.g. a file).

Parametri
    

**attachment** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field should be stored as `ir_attachment` or in a column of the model’s table (default: `True`).

_class _odoo.fields.Html[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1991)¶
    

Encapsulates an html code content.

Parametri
    

  * **sanitize** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether value must be sanitized (default: `True`)

  * **sanitize_overridable** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the sanitation can be bypassed by the users part of the `base.group_sanitize_override` group (default: `False`)

  * **sanitize_tags** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to sanitize tags (only a white list of attributes is accepted, default: `True`)

  * **sanitize_attributes** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to sanitize attributes (only a white list of attributes is accepted, default: `True`)

  * **sanitize_style** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to sanitize style attributes (default: `False`)

  * **strip_style** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to strip style attributes (removed and therefore not sanitized, default: `False`)

  * **strip_classes** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to strip classes attributes (default: `False`)




_class _odoo.fields.Image[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2528)¶
    

Encapsulates an image, extending `Binary`.

If image size is greater than the `max_width`/`max_height` limit of pixels, the image will be resized to the limit by keeping aspect ratio.

Parametri
    

  * **max_width** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – the maximum width of the image (default: `0`, no limit)

  * **max_height** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – the maximum height of the image (default: `0`, no limit)

  * **verify_resolution** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the image resolution should be verified to ensure it doesn’t go over the maximum image resolution (default: `True`). See `odoo.tools.image.ImageProcess` for maximum image resolution (default: `50e6`).




Nota

If no `max_width`/`max_height` is specified (or is set to 0) and `verify_resolution` is False, the field content won’t be verified at all and a `Binary` field should be used.

_class _odoo.fields.Monetary[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1572)¶
    

Encapsulates a [`float`](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)") expressed in a given `res_currency`.

The decimal precision and currency symbol are taken from the `currency_field` attribute.

Parametri
    

**currency_field** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the `Many2one` field holding the `res_currency` this monetary field is expressed in (default: `'currency_id'`)

_class _odoo.fields.Selection[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2642)¶
    

Encapsulates an exclusive choice between different values.

Parametri
    

  * **selection** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _,_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)__) or_ _callable_ _or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – specifies the possible values for this field. It is given as either a list of pairs `(value, label)`, or a model method, or a method name.

  * **selection_add** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _,_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)__)_) – 

provides an extension of the selection in the case of an overridden field. It is a list of pairs `(value, label)` or singletons `(value,)`, where singleton values must appear in the overridden selection. The new values are inserted in an order that is consistent with the overridden selection and this list:
        
        selection = [('a', 'A'), ('b', 'B')]
        selection_add = [('c', 'C'), ('b',)]
        > result = [('a', 'A'), ('c', 'C'), ('b', 'B')]
        

  * **ondelete** – 

provides a fallback mechanism for any overridden field with a selection_add. It is a dict that maps every option from the selection_add to a fallback action.

This fallback action will be applied to all records whose selection_add option maps to it.

The actions can be any of the following:
    
    * ”set null” – the default, all records with this option will have their selection value set to False.

    * ”cascade” – all records with this option will be deleted along with the option itself.

    * ”set default” – all records with this option will be set to the default of the field definition

    * ’set VALUE” – all records with this option will be set to the given value

    * <callable> – a callable whose first and only argument will be the set of records containing the specified Selection option, for custom processing




The attribute `selection` is mandatory except in the case of `related` or extended fields.

_class _odoo.fields.Text[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L1968)¶
    

Very similar to `Char` but used for longer contents, does not have a size and usually displayed as a multiline text box.

Parametri
    

**translate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _or_ _callable_) – enable the translation of the field’s values; use `translate=True` to translate field values as a whole; `translate` may also be a callable such that `translate(callback, value)` translates `value` by using `callback(term)` to retrieve the translation of terms.

#### Date(time) Fields¶

`Dates` and `Datetimes` are very important fields in any kind of business application. Their misuse can create invisible yet painful bugs, this section aims to provide Odoo developers with the knowledge required to avoid misusing these fields.

When assigning a value to a Date/Datetime field, the following options are valid:

  * A `date` or `datetime` object.

  * A string in the proper server format:

    * `YYYY-MM-DD` for `Date` fields,

    * `YYYY-MM-DD HH:MM:SS` for `Datetime` fields.

  * `False` or `None`.




The Date and Datetime fields class have helper methods to attempt conversion into a compatible type:

  * `to_date()` will convert to a [`datetime.date`](https://docs.python.org/3/library/datetime.html#datetime.date "\(in Python v3.13\)")

  * `to_datetime()` will convert to a [`datetime.datetime`](https://docs.python.org/3/library/datetime.html#datetime.datetime "\(in Python v3.13\)").




Example

To parse date/datetimes coming from external sources:
    
    
    fields.Date.to_date(self._context.get('date_from'))
    

Date / Datetime comparison best practices:

  * Date fields can **only** be compared to date objects.

  * Datetime fields can **only** be compared to datetime objects.




Avvertimento

Strings representing dates and datetimes can be compared between each other, however the result may not be the expected result, as a datetime string will always be greater than a date string, therefore this practice is **heavily** discouraged.

Common operations with dates and datetimes such as addition, subtraction or fetching the start/end of a period are exposed through both `Date` and `Datetime`. These helpers are also available by importing `odoo.tools.date_utils`.

Nota

Timezones

Datetime fields are stored as `timestamp without timezone` columns in the database and are stored in the UTC timezone. This is by design, as it makes the Odoo database independent from the timezone of the hosting server system. Timezone conversion is managed entirely by the client side.

_class _odoo.fields.Date[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2127)¶
    

Encapsulates a python [`date`](https://docs.python.org/3/library/datetime.html#datetime.date "\(in Python v3.13\)") object.

_static _start_of(_value_ , _granularity_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L108)¶
    

Get start of a time period from a date or a datetime.

Parametri
    

  * **value** – initial date or datetime.

  * **granularity** – type of period in string, can be year, quarter, month, week, day or hour.



Ritorna
    

a date/datetime object corresponding to the start of the specified period.

_static _end_of(_value_ , _granularity_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L147)¶
    

Get end of a time period from a date or a datetime.

Parametri
    

  * **value** – initial date or datetime.

  * **granularity** – Type of period in string, can be year, quarter, month, week, day or hour.



Ritorna
    

A date/datetime object corresponding to the start of the specified period.

_static _add(_value_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L186)¶
    

Return the sum of `value` and a `relativedelta`.

Parametri
    

  * **value** – initial date or datetime.

  * **args** – positional args to pass directly to `relativedelta`.

  * **kwargs** – keyword args to pass directly to `relativedelta`.



Ritorna
    

the resulting date/datetime.

_static _subtract(_value_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L198)¶
    

Return the difference between `value` and a `relativedelta`.

Parametri
    

  * **value** – initial date or datetime.

  * **args** – positional args to pass directly to `relativedelta`.

  * **kwargs** – keyword args to pass directly to `relativedelta`.



Ritorna
    

the resulting date/datetime.

_static _today(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2137)¶
    

Return the current day in the format expected by the ORM.

Nota

This function may be used to compute default values.

_static _context_today(_record_ , _timestamp =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2145)¶
    

Return the current date as seen in the client’s timezone in a format fit for date fields.

Nota

This method may be used to compute default values.

Parametri
    

  * **record** – recordset from which the timezone will be obtained.

  * **timestamp** (_datetime_) – optional datetime value to use instead of the current date and time (must be a datetime, regular dates can’t be converted between timezones).



Tipo di ritorno
    

date

_static _to_date(_value_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2170)¶
    

Attempt to convert `value` to a `date` object.

Avvertimento

If a datetime object is given as value, it will be converted to a date object and all datetime-specific information will be lost (HMS, TZ, …).

Parametri
    

**value** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_ _date_ _or_ _datetime_) – value to convert.

Ritorna
    

an object representing `value`.

Tipo di ritorno
    

date or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

_static _to_string(_value_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2198)¶
    

Convert a `date` or `datetime` object to a string.

Parametri
    

**value** – value to convert.

Ritorna
    

a string representing `value` in the server’s date format, if `value` is of type `datetime`, the hours, minute, seconds, tzinfo will be truncated.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_class _odoo.fields.Datetime[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2225)¶
    

Encapsulates a python [`datetime`](https://docs.python.org/3/library/datetime.html#datetime.datetime "\(in Python v3.13\)") object.

_static _start_of(_value_ , _granularity_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L108)¶
    

Get start of a time period from a date or a datetime.

Parametri
    

  * **value** – initial date or datetime.

  * **granularity** – type of period in string, can be year, quarter, month, week, day or hour.



Ritorna
    

a date/datetime object corresponding to the start of the specified period.

_static _end_of(_value_ , _granularity_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L147)¶
    

Get end of a time period from a date or a datetime.

Parametri
    

  * **value** – initial date or datetime.

  * **granularity** – Type of period in string, can be year, quarter, month, week, day or hour.



Ritorna
    

A date/datetime object corresponding to the start of the specified period.

_static _add(_value_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L186)¶
    

Return the sum of `value` and a `relativedelta`.

Parametri
    

  * **value** – initial date or datetime.

  * **args** – positional args to pass directly to `relativedelta`.

  * **kwargs** – keyword args to pass directly to `relativedelta`.



Ritorna
    

the resulting date/datetime.

_static _subtract(_value_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/date_utils.py#L198)¶
    

Return the difference between `value` and a `relativedelta`.

Parametri
    

  * **value** – initial date or datetime.

  * **args** – positional args to pass directly to `relativedelta`.

  * **kwargs** – keyword args to pass directly to `relativedelta`.



Ritorna
    

the resulting date/datetime.

_static _now(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2235)¶
    

Return the current day and time in the format expected by the ORM.

Nota

This function may be used to compute default values.

_static _today(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2244)¶
    

Return the current day, at midnight (00:00:00).

_static _context_timestamp(_record_ , _timestamp_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2249)¶
    

Return the given timestamp converted to the client’s timezone.

Nota

This method is _not_ meant for use as a default initializer, because datetime fields are automatically converted upon display on client side. For default values, `now()` should be used instead.

Parametri
    

  * **record** – recordset from which the timezone will be obtained.

  * **timestamp** (_datetime_) – naive datetime value (expressed in UTC) to be converted to the client timezone.



Ritorna
    

timestamp converted to timezone-aware datetime in context timezone.

Tipo di ritorno
    

datetime

_static _to_datetime(_value_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2277)¶
    

Convert an ORM `value` into a `datetime` value.

Parametri
    

**value** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_ _date_ _or_ _datetime_) – value to convert.

Ritorna
    

an object representing `value`.

Tipo di ritorno
    

datetime or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

_static _to_string(_value_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2302)¶
    

Convert a `datetime` or `date` object to a string.

Parametri
    

**value** (_datetime_ _or_ _date_) – value to convert.

Ritorna
    

a string representing `value` in the server’s datetime format, if `value` is of type `date`, the time portion will be midnight (00:00:00).

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

#### Relational Fields¶

_class _odoo.fields.Many2one[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2969)¶
    

The value of such a field is a recordset of size 0 (no record) or 1 (a single record).

Parametri
    

  * **comodel_name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the target model `Mandatory` except for related or extended fields.

  * **domain** – an optional domain to set on candidate values on the client side (domain or a python expression that will be evaluated to provide domain)

  * **context** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – an optional context to use on the client side when handling that field

  * **ondelete** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – what to do when the referred record is deleted; possible values are: `'set null'`, `'restrict'`, `'cascade'`

  * **auto_join** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether JOINs are generated upon search through that field (default: `False`)

  * **delegate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – set it to `True` to make fields of the target model accessible from the current model (corresponds to `_inherits`)

  * **check_company** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Mark the field to be verified in [`_check_company()`](../../howtos/company.html#odoo.models.Model._check_company "odoo.models.Model._check_company"). Add a default company domain depending on the field attributes.




_class _odoo.fields.One2many[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4387)¶
    

One2many field; the value of such a field is the recordset of all the records in `comodel_name` such that the field `inverse_name` is equal to the current record.

Parametri
    

  * **comodel_name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the target model

  * **inverse_name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the inverse `Many2one` field in `comodel_name`

  * **domain** – an optional domain to set on candidate values on the client side (domain or a python expression that will be evaluated to provide domain)

  * **context** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – an optional context to use on the client side when handling that field

  * **auto_join** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether JOINs are generated upon search through that field (default: `False`)




The attributes `comodel_name` and `inverse_name` are mandatory except in the case of related fields or field extensions.

_class _odoo.fields.Many2many[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4676)¶
    

Many2many field; the value of such a field is the recordset.

Parametri
    

  * **comodel_name** – name of the target model (string) mandatory except in the case of related or extended fields

  * **relation** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional name of the table that stores the relation in the database

  * **column1** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional name of the column referring to «these» records in the table `relation`

  * **column2** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional name of the column referring to «those» records in the table `relation`




The attributes `relation`, `column1` and `column2` are optional. If not given, names are automatically generated from model names, provided `model_name` and `comodel_name` are different!

Note that having several fields with implicit relation parameters on a given model with the same comodel is not accepted by the ORM, since those field would use the same table. The ORM prevents two many2many fields to use the same relation parameters, except if

  * both fields use the same model, comodel, and relation parameters are explicit; or

  * at least one field belongs to a model with `_auto = False`.




Parametri
    

  * **domain** – an optional domain to set on candidate values on the client side (domain or a python expression that will be evaluated to provide domain)

  * **context** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – an optional context to use on the client side when handling that field

  * **check_company** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Mark the field to be verified in [`_check_company()`](../../howtos/company.html#odoo.models.Model._check_company "odoo.models.Model._check_company"). Add a default company domain depending on the field attributes.




_class _odoo.fields.Command[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4072)¶
    

`One2many` and `Many2many` fields expect a special command to manipulate the relation they implement.

Internally, each command is a 3-elements tuple where the first element is a mandatory integer that identifies the command, the second element is either the related record id to apply the command on (commands update, delete, unlink and link) either 0 (commands create, clear and set), the third element is either the `values` to write on the record (commands create and update) either the new `ids` list of related records (command set), either 0 (commands delete, unlink, link, and clear).

Via Python, we encourage developers craft new commands via the various functions of this namespace. We also encourage developers to use the command identifier constant names when comparing the 1st element of existing commands.

Via RPC, it is impossible nor to use the functions nor the command constant names. It is required to instead write the literal 3-elements tuple where the first element is the integer identifier of the command.

CREATE _ = 0_¶
    

UPDATE _ = 1_¶
    

DELETE _ = 2_¶
    

UNLINK _ = 3_¶
    

LINK _ = 4_¶
    

CLEAR _ = 5_¶
    

SET _ = 6_¶
    

_classmethod _create(_values : [dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4103)¶
    

Create new records in the comodel using `values`, link the created records to `self`.

In case of a `Many2many` relation, one unique new record is created in the comodel such that all records in `self` are linked to the new record.

In case of a `One2many` relation, one new record is created in the comodel for every record in `self` such that every record in `self` is linked to exactly one of the new records.

Return the command triple `(CREATE, 0, _values_)`

_classmethod _update(_id : [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_, _values : [dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4121)¶
    

Write `values` on the related record.

Return the command triple `(UPDATE, _id_ , _values_)`

_classmethod _delete(_id : [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4130)¶
    

Remove the related record from the database and remove its relation with `self`.

In case of a `Many2many` relation, removing the record from the database may be prevented if it is still linked to other records.

Return the command triple `(DELETE, _id_ , 0)`

_classmethod _unlink(_id : [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4144)¶
    

Remove the relation between `self` and the related record.

In case of a `One2many` relation, the given record is deleted from the database if the inverse field is set as `ondelete='cascade'`. Otherwise, the value of the inverse field is set to False and the record is kept.

Return the command triple `(UNLINK, _id_ , 0)`

_classmethod _link(_id : [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4158)¶
    

Add a relation between `self` and the related record.

Return the command triple `(LINK, _id_ , 0)`

_classmethod _clear()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4167)¶
    

Remove all records from the relation with `self`. It behaves like executing the `unlink` command on every record.

Return the command triple `(CLEAR, 0, 0)`

_classmethod _set(_ids : [list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L4177)¶
    

Replace the current relations of `self` by the given ones. It behaves like executing the `unlink` command on every removed relation then executing the `link` command on every new relation.

Return the command triple `(SET, 0, _ids_)`

#### Pseudo-relational fields¶

_class _odoo.fields.Reference[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L2866)¶
    

Pseudo-relational field (no FK in database).

The field value is stored as a [`string`](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") following the pattern `"res_model,res_id"` in database.

_class _odoo.fields.Many2oneReference[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/fields.py#L3210)¶
    

Pseudo-relational field (no FK in database).

The field value is stored as an [`integer`](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") id in database.

Contrary to `Reference` fields, the model has to be specified in a `Char` field, whose name has to be specified in the `model_field` attribute for the current `Many2oneReference` field.

Parametri
    

**model_field** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the `Char` where the model name is stored.

#### Computed Fields¶

Fields can be computed (instead of read straight from the database) using the `compute` parameter. **It must assign the computed value to the field**. If it uses the values of other _fields_ , it should specify those fields using `depends()`.
    
    
    from odoo import api
    total = fields.Float(compute='_compute_total')
    
    @api.depends('value', 'tax')
    def _compute_total(self):
        for record in self:
            record.total = record.value + record.value * record.tax
    

  * dependencies can be dotted paths when using sub-fields:
        
        @api.depends('line_ids.value')
        def _compute_total(self):
            for record in self:
                record.total = sum(line.value for line in record.line_ids)
        

  * computed fields are not stored by default, they are computed and returned when requested. Setting `store=True` will store them in the database and automatically enable searching.

  * searching on a computed field can also be enabled by setting the `search` parameter. The value is a method name returning a Search domains.
        
        upper_name = field.Char(compute='_compute_upper', search='_search_upper')
        
        def _search_upper(self, operator, value):
            if operator == 'like':
                operator = 'ilike'
            return [('name', operator, value)]
        

The search method is invoked when processing domains before doing an actual search on the model. It must return a domain equivalent to the condition: `field operator value`.



  * Computed fields are readonly by default. To allow _setting_ values on a computed field, use the `inverse` parameter. It is the name of a function reversing the computation and setting the relevant fields:
        
        document = fields.Char(compute='_get_document', inverse='_set_document')
        
        def _get_document(self):
            for record in self:
                with open(record.get_document_path) as f:
                    record.document = f.read()
        def _set_document(self):
            for record in self:
                if not record.document: continue
                with open(record.get_document_path()) as f:
                    f.write(record.document)
        

  * multiple fields can be computed at the same time by the same method, just use the same method on all fields and set all of them:
        
        discount_value = fields.Float(compute='_apply_discount')
        total = fields.Float(compute='_apply_discount')
        
        @api.depends('value', 'discount')
        def _apply_discount(self):
            for record in self:
                # compute actual discount from discount percentage
                discount = record.value * record.discount
                record.discount_value = discount
                record.total = record.value - discount
        




Avvertimento

While it is possible to use the same compute method for multiple fields, it is not recommended to do the same for the inverse method.

During the computation of the inverse, **all** fields that use said inverse are protected, meaning that they can’t be computed, even if their value is not in the cache.

If any of those fields is accessed and its value is not in cache, the ORM will simply return a default value of `False` for these fields. This means that the value of the inverse fields (other than the one triggering the inverse method) may not give their correct value and this will probably break the expected behavior of the inverse method.

#### Related fields¶

A special case of computed fields are _related_ (proxy) fields, which provide the value of a sub-field on the current record. They are defined by setting the `related` parameter and like regular computed fields they can be stored:
    
    
    nickname = fields.Char(related='user_id.partner_id.name', store=True)
    

The value of a related field is given by following a sequence of relational fields and reading a field on the reached model. The complete sequence of fields to traverse is specified by the `related` attribute.

Some field attributes are automatically copied from the source field if they are not redefined: `string`, `help`, `required` (only if all fields in the sequence are required), `groups`, `digits`, `size`, `translate`, `sanitize`, `selection`, `comodel_name`, `domain`, `context`. All semantic-free attributes are copied from the source field.

By default, related fields are:

  * not stored

  * not copied

  * readonly

  * computed in superuser mode




Add the attribute `store=True` to make it stored, just like computed fields. Related fields are automatically recomputed when their dependencies are modified.

Suggerimento

You can specify precise field dependencies if you don’t want the related field to be recomputed on any dependency change:
    
    
    nickname = fields.Char(
        related='partner_id.name', store=True,
        depends=['partner_id'])
    # The nickname will only be recomputed when the partner_id
    # is modified, not when the name is modified on the partner.
    

Avvertimento

You cannot chain `Many2many` or `One2many` fields in `related` fields dependencies.

`related` can be used to refer to a `One2many` or `Many2many` field on another model on the condition that it’s done through a `Many2one` relation on the current model. `One2many` and `Many2many` are not supported and the results will not be aggregated correctly:
    
    
    m2o_id = fields.Many2one()
    m2m_ids = fields.Many2many()
    o2m_ids = fields.One2many()
    
    # Supported
    d_ids = fields.Many2many(related="m2o_id.m2m_ids")
    e_ids = fields.One2many(related="m2o_id.o2m_ids")
    
    # Won't work: use a custom Many2many computed field instead
    f_ids = fields.Many2many(related="m2m_ids.m2m_ids")
    g_ids = fields.One2many(related="o2m_ids.o2m_ids")
    

### Automatic fields¶

Model.id¶
    

Identifier `field`

If length of current recordset is 1, return id of unique record in it.

Raise an Error otherwise.

Model.display_name¶
    

Name `field` displayed by default in the web client

By default, it equals to `_rec_name` value field but the behavior can be customized by overriding `_compute_display_name`

#### Access Log fields¶

These fields are automatically set and updated if `_log_access` is enabled. It can be disabled to avoid creating or updating those fields on tables for which they are not useful.

By default, `_log_access` is set to the same value as `_auto`

Model.create_date¶
    

Stores when the record was created, `Datetime`

Model.create_uid¶
    

Stores _who_ created the record, `Many2one` to a `res.users`.

Model.write_date¶
    

Stores when the record was last updated, `Datetime`

Model.write_uid¶
    

Stores who last updated the record, `Many2one` to a `res.users`.

Avvertimento

`_log_access` _must_ be enabled on `TransientModel`.

### Reserved Field names¶

A few field names are reserved for pre-defined behaviors beyond that of automated fields. They should be defined on a model when the related behavior is desired:

Model.name¶
    

default value for `_rec_name`, used to display records in context where a representative «naming» is necessary.

`Char`

Model.active¶
    

toggles the global visibility of the record, if `active` is set to `False` the record is invisible in most searches and listing.

`Boolean`

Special methods:

toggle_active()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5797)¶
    

Inverses the value of `active` on the records in `self`.

Model.action_archive()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5803)¶
    

Sets `active` to `False` on a recordset, by calling `toggle_active()` on its currently active records.

Model.action_unarchive()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5809)¶
    

Sets `active` to `True` on a recordset, by calling `toggle_active()` on its currently inactive records.

Model.state¶
    

lifecycle stages of the object, used by the `states` attribute on `fields`.

`Selection`

Model.parent_id¶
    

default_value of `_parent_name`, used to organize records in a tree structure and enables the `child_of` and `parent_of` operators in domains.

`Many2one`

Model.parent_path¶
    

When `_parent_store` is set to True, used to store a value reflecting the tree structure of `_parent_name`, and to optimize the operators `child_of` and `parent_of` in search domains. It must be declared with `index=True` for proper operation.

`Char`

Model.company_id¶
    

Main field name used for Odoo multi-company behavior.

Used by `:meth:~odoo.models._check_company` to check multi company consistency. Defines whether a record is shared between companies (no value) or only accessible by the users of a given company.

`Many2one` :type: `res_company`

## Recordsets¶

Interactions with models and records are performed through recordsets, an ordered collection of records of the same model.

Avvertimento

Contrary to what the name implies, it is currently possible for recordsets to contain duplicates. This may change in the future.

Methods defined on a model are executed on a recordset, and their `self` is a recordset:
    
    
    class AModel(models.Model):
        _name = 'a.model'
        def a_method(self):
            # self can be anything between 0 records and all records in the
            # database
            self.do_operation()
    

Iterating on a recordset will yield new sets of _a single record_ («singletons»), much like iterating on a Python string yields strings of a single characters:
    
    
    def do_operation(self):
        print(self) # => a.model(1, 2, 3, 4, 5)
        for record in self:
            print(record) # => a.model(1), then a.model(2), then a.model(3), ...
    

### Field access¶

Recordsets provide an «Active Record» interface: model fields can be read and written directly from the record as attributes.

Nota

When accessing non-relational fields on a recordset of potentially multiple records, use `mapped()`:
    
    
    total_qty = sum(self.mapped('qty'))
    

Field values can also be accessed like dict items, which is more elegant and safer than `getattr()` for dynamic field names. Setting a field’s value triggers an update to the database:
    
    
    >>> record.name
    Example Name
    >>> record.company_id.name
    Company Name
    >>> record.name = "Bob"
    >>> field = "name"
    >>> record[field]
    Bob
    

Avvertimento

Trying to read a field on multiple records will raise an error for non relational fields.

Accessing a relational field (`Many2one`, `One2many`, `Many2many`) _always_ returns a recordset, empty if the field is not set.

### Record cache and prefetching¶

Odoo maintains a cache for the fields of the records, so that not every field access issues a database request, which would be terrible for performance. The following example queries the database only for the first statement:
    
    
    record.name             # first access reads value from database
    record.name             # second access gets value from cache
    

To avoid reading one field on one record at a time, Odoo _prefetches_ records and fields following some heuristics to get good performance. Once a field must be read on a given record, the ORM actually reads that field on a larger recordset, and stores the returned values in cache for later use. The prefetched recordset is usually the recordset from which the record comes by iteration. Moreover, all simple stored fields (boolean, integer, float, char, text, date, datetime, selection, many2one) are fetched altogether; they correspond to the columns of the model’s table, and are fetched efficiently in the same query.

Consider the following example, where `partners` is a recordset of 1000 records. Without prefetching, the loop would make 2000 queries to the database. With prefetching, only one query is made:
    
    
    for partner in partners:
        print partner.name          # first pass prefetches 'name' and 'lang'
                                    # (and other fields) on all 'partners'
        print partner.lang
    

The prefetching also works on _secondary records_ : when relational fields are read, their values (which are records) are subscribed for future prefetching. Accessing one of those secondary records prefetches all secondary records from the same model. This makes the following example generate only two queries, one for partners and one for countries:
    
    
    countries = set()
    for partner in partners:
        country = partner.country_id        # first pass prefetches all partners
        countries.add(country.name)         # first pass prefetches all countries
    

Vedi anche

The methods `search_fetch()` and `fetch()` can be used to populate the cache of records, typically in cases where the prefetching mechanism does not work well.

## Method decorators¶

The Odoo API module defines Odoo Environments and method decorators.

odoo.api.model(_method_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L369)¶
    

Decorate a record-style method where `self` is a recordset, but its contents is not relevant, only the model is. Such a method:
    
    
    @api.model
    def method(self, args):
        ...
    

odoo.api.constrains(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L100)¶
    

Decorate a constraint checker.

Each argument must be a field name used in the check:
    
    
    @api.constrains('name', 'description')
    def _check_description(self):
        for record in self:
            if record.name == record.description:
                raise ValidationError("Fields name and description must be different")
    

Invoked on the records on which one of the named fields has been modified.

Should raise `ValidationError` if the validation failed.

Avvertimento

`@constrains` only supports simple field names, dotted names (fields of relational fields e.g. `partner_id.customer`) are not supported and will be ignored.

`@constrains` will be triggered only if the declared fields in the decorated method are included in the `create` or `write` call. It implies that fields not present in a view will not trigger a call during a record creation. A override of `create` is necessary to make sure a constraint will always be triggered (e.g. to test the absence of value).

One may also pass a single function as argument. In that case, the field names are given by calling the function with a model instance.

odoo.api.depends(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L246)¶
    

Return a decorator that specifies the field dependencies of a «compute» method (for new-style function fields). Each argument must be a string that consists in a dot-separated sequence of field names:
    
    
    pname = fields.Char(compute='_compute_pname')
    
    @api.depends('partner_id.name', 'partner_id.is_company')
    def _compute_pname(self):
        for record in self:
            if record.partner_id.is_company:
                record.pname = (record.partner_id.name or "").upper()
            else:
                record.pname = record.partner_id.name
    

One may also pass a single function as argument. In that case, the dependencies are given by calling the function with the field’s model.

odoo.api.onchange(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L197)¶
    

Return a decorator to decorate an onchange method for given fields.

In the form views where the field appears, the method will be called when one of the given fields is modified. The method is invoked on a pseudo-record that contains the values present in the form. Field assignments on that record are automatically sent back to the client.

Each argument must be a field name:
    
    
    @api.onchange('partner_id')
    def _onchange_partner(self):
        self.message = "Dear %s" % (self.partner_id.name or "")
    
    
    
    return {
        'warning': {'title': "Warning", 'message': "What is this?", 'type': 'notification'},
    }
    

If the type is set to notification, the warning will be displayed in a notification. Otherwise it will be displayed in a dialog as default.

Avvertimento

`@onchange` only supports simple field names, dotted names (fields of relational fields e.g. `partner_id.tz`) are not supported and will be ignored

Pericolo

Since `@onchange` returns a recordset of pseudo-records, calling any one of the CRUD methods (`create()`, `read()`, `write()`, `unlink()`) on the aforementioned recordset is undefined behaviour, as they potentially do not exist in the database yet.

Instead, simply set the record’s field like shown in the example above or call the `update()` method.

Avvertimento

It is not possible for a `one2many` or `many2many` field to modify itself via onchange. This is a webclient limitation - see [#2693](https://github.com/odoo/odoo/issues/2693).

odoo.api.returns(_model_ , _downgrade =None_, _upgrade =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L297)¶
    

Return a decorator for methods that return instances of `model`.

Parametri
    

  * **model** – a model name, or `'self'` for the current model

  * **downgrade** – a function `downgrade(self, value, *args, **kwargs)` to convert the record-style `value` to a traditional-style output

  * **upgrade** – a function `upgrade(self, value, *args, **kwargs)` to convert the traditional-style `value` to a record-style output




The arguments `self`, `*args` and `**kwargs` are the ones passed to the method in the record-style.

The decorator adapts the method output to the api style: `id`, `ids` or `False` for the traditional style, and recordset for the record style:
    
    
    @model
    @returns('res.partner')
    def find_partner(self, arg):
        ...     # return some record
    
    # output depends on call style: traditional vs record style
    partner_id = model.find_partner(cr, uid, arg, context=context)
    
    # recs = model.browse(cr, uid, ids, context)
    partner_record = recs.find_partner(arg)
    

Note that the decorated method must satisfy that convention.

Those decorators are automatically _inherited_ : a method that overrides a decorated existing method will be decorated with the same `@returns(model)`.

odoo.api.autovacuum(_method_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L358)¶
    

Decorate a method so that it is called by the daily vacuum cron job (model `ir.autovacuum`). This is typically used for garbage-collection-like tasks that do not deserve a specific cron job.

odoo.api.depends_context(_* args_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L271)¶
    

Return a decorator that specifies the context dependencies of a non-stored «compute» method. Each argument is a key in the context’s dictionary:
    
    
    price = fields.Float(compute='_compute_product_price')
    
    @api.depends_context('pricelist')
    def _compute_product_price(self):
        for product in self:
            if product.env.context.get('pricelist'):
                pricelist = self.env['product.pricelist'].browse(product.env.context['pricelist'])
            else:
                pricelist = self.env['product.pricelist'].get_default_pricelist()
            product.price = pricelist._get_products_price(product).get(product.id, 0.0)
    

All dependencies must be hashable. The following keys have special support:

  * `company` (value in context or current company id),

  * `uid` (current user id and superuser flag),

  * `active_test` (value in env.context or value in field.context).




odoo.api.model_create_multi(_method_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L434)¶
    

Decorate a method that takes a list of dictionaries and creates multiple records. The method may be called with either a single dict or a list of dicts:
    
    
    record = model.create(vals)
    records = model.create([vals, ...])
    

odoo.api.ondelete(_*_ , _at_uninstall_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L138)¶
    

Mark a method to be executed during `unlink()`.

The goal of this decorator is to allow client-side errors when unlinking records if, from a business point of view, it does not make sense to delete such records. For instance, a user should not be able to delete a validated sales order.

While this could be implemented by simply overriding the method `unlink` on the model, it has the drawback of not being compatible with module uninstallation. When uninstalling the module, the override could raise user errors, but we shouldn’t care because the module is being uninstalled, and thus **all** records related to the module should be removed anyway.

This means that by overriding `unlink`, there is a big chance that some tables/records may remain as leftover data from the uninstalled module. This leaves the database in an inconsistent state. Moreover, there is a risk of conflicts if the module is ever reinstalled on that database.

Methods decorated with `@ondelete` should raise an error following some conditions, and by convention, the method should be named either `_unlink_if_<condition>` or `_unlink_except_<not_condition>`.
    
    
    @api.ondelete(at_uninstall=False)
    def _unlink_if_user_inactive(self):
        if any(user.active for user in self):
            raise UserError("Can't delete an active user!")
    
    # same as above but with _unlink_except_* as method name
    @api.ondelete(at_uninstall=False)
    def _unlink_except_active_user(self):
        if any(user.active for user in self):
            raise UserError("Can't delete an active user!")
    

Parametri
    

**at_uninstall** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the decorated method should be called if the module that implements said method is being uninstalled. Should almost always be `False`, so that module uninstallation does not trigger those errors.

Pericolo

The parameter `at_uninstall` should only be set to `True` if the check you are implementing also applies when uninstalling the module.

For instance, it doesn’t matter if when uninstalling `sale`, validated sales orders are being deleted because all data pertaining to `sale` should be deleted anyway, in that case `at_uninstall` should be set to `False`.

However, it makes sense to prevent the removal of the default language if no other languages are installed, since deleting the default language will break a lot of basic behavior. In this case, `at_uninstall` should be set to `True`.

## Environment¶

_class _odoo.api.Environment(_cr_ , _uid_ , _context_ , _su =False_, _uid_origin =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L489)¶
    

The environment stores various contextual data used by the ORM:

  * `cr`: the current database cursor (for database queries);

  * `uid`: the current user id (for access rights checks);

  * `context`: the current context dictionary (arbitrary metadata);

  * `su`: whether in superuser mode.




It provides access to the registry by implementing a mapping from model names to models. It also holds a cache for records, and a data structure to manage recomputations.
    
    
    >>> records.env
    <Environment object ...>
    >>> records.env.uid
    3
    >>> records.env.user
    res.user(3)
    >>> records.env.cr
    <Cursor object ...>
    

When creating a recordset from an other recordset, the environment is inherited. The environment can be used to get an empty recordset in an other model, and query that model:
    
    
    >>> self.env['res.partner']
    res.partner()
    >>> self.env['res.partner'].search([('is_company', '=', True), ('customer', '=', True)])
    res.partner(7, 18, 12, 14, 17, 19, 8, 31, 26, 16, 13, 20, 30, 22, 29, 15, 23, 28, 74)
    

Some lazy properties are available to access the environment (contextual) data:

Environment.lang¶
    

Return the current language code.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

Environment.user¶
    

Return the current user (as an instance).

Ritorna
    

current user - sudoed

Tipo di ritorno
    

`res.users record`

Environment.company¶
    

Return the current company (as an instance).

If not specified in the context (`allowed_company_ids`), fallback on current user main company.

Solleva
    

**AccessError** – invalid or unauthorized `allowed_company_ids` context key content.

Ritorna
    

current company (default=`self.user.company_id`), with the current environment

Tipo di ritorno
    

`res.company record`

Avvertimento

No sanity checks applied in sudo mode! When in sudo mode, a user can access any company, even if not in his allowed companies.

This allows to trigger inter-company modifications, even if the current user doesn’t have access to the targeted company.

Environment.companies¶
    

Return a recordset of the enabled companies by the user.

If not specified in the context(`allowed_company_ids`), fallback on current user companies.

Solleva
    

**AccessError** – invalid or unauthorized `allowed_company_ids` context key content.

Ritorna
    

current companies (default=`self.user.company_ids`), with the current environment

Tipo di ritorno
    

`res.company recordset`

Avvertimento

No sanity checks applied in sudo mode ! When in sudo mode, a user can access any company, even if not in his allowed companies.

This allows to trigger inter-company modifications, even if the current user doesn’t have access to the targeted company.

### Useful environment methods¶

Environment.ref(_xml_id_ , _raise_if_not_found =True_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L588)¶
    

Return the record corresponding to the given `xml_id`.

Parametri
    

  * **xml_id** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `<module.id>`

  * **raise_if_not_found** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the method should raise if record is not found



Ritorna
    

Found record or None

Solleva
    

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "\(in Python v3.13\)") – if record wasn’t found and `raise_if_not_found` is True

Environment.is_superuser()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L608)¶
    

Return whether the environment is in superuser mode.

Environment.is_admin()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L612)¶
    

Return whether the current user has group «Access Rights», or is in superuser mode.

Environment.is_system()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L617)¶
    

Return whether the current user has group «Settings», or is in superuser mode.

### Altering the environment¶

Model.with_context(_[context][, **overrides]_) → Model[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5988)¶
    

Returns a new version of this recordset attached to an extended context.

The extended context is either the provided `context` in which `overrides` are merged or the _current_ context in which `overrides` are merged e.g.:
    
    
    # current context is {'key1': True}
    r2 = records.with_context({}, key2=True)
    # -> r2._context is {'key2': True}
    r2 = records.with_context(key2=True)
    # -> r2._context is {'key1': True, 'key2': True}
    

Model.with_user(_user_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5941)¶
    

Return a new version of this recordset attached to the given user, in non-superuser mode, unless `user` is the superuser (by convention, the superuser is always in superuser mode.)

Model.with_company(_company_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5953)¶
    

Return a new version of this recordset with a modified context, such that:
    
    
    result.env.company = company
    result.env.companies = self.env.companies | company
    

Parametri
    

**company** (`res_company` or int) – main company of the new environment.

Avvertimento

When using an unauthorized company for current user, accessing the company(ies) on the environment may trigger an AccessError if not done in a sudoed environment.

Model.with_env(_env_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5901)¶
    

Return a new version of this recordset attached to the provided environment.

Parametri
    

**env** (`Environment`) – 

Nota

The returned recordset has the same prefetch object as `self`.

Model.sudo([_flag=True_])[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5913)¶
    

Returns a new version of this recordset with superuser mode enabled or disabled, depending on `flag`. The superuser mode does not change the current user, and simply bypasses access rights checks.

Avvertimento

Using `sudo` could cause data access to cross the boundaries of record rules, possibly mixing records that are meant to be isolated (e.g. records from different companies in multi-company environments).

It may lead to un-intuitive results in methods which select one record among many - for example getting the default company, or selecting a Bill of Materials.

Nota

The returned recordset has the same prefetch object as `self`.

### SQL Execution¶

The `cr` attribute on environments is the cursor for the current database transaction and allows executing SQL directly, either for queries which are difficult to express using the ORM (e.g. complex joins) or for performance reasons:
    
    
    self.env.cr.execute("some_sql", params)
    

Avvertimento

Executing raw SQL bypasses the ORM and, by consequent, Odoo security rules. Please make sure your queries are sanitized when using user input and prefer using ORM utilities if you don’t really need to use SQL queries.

The recommended way to build SQL queries is to use the wrapper object

_class _odoo.tools.SQL(_code : [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") | odoo.tools.sql.SQL = ''_, _/_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/sql.py#L31)¶
    

An object that wraps SQL code with its parameters, like:
    
    
    sql = SQL("UPDATE TABLE foo SET a = %s, b = %s", 'hello', 42)
    cr.execute(sql)
    

The code is given as a `%`-format string, and supports either positional arguments (with `%s`) or named arguments (with `%(name)s`). Escaped characters (like `"%%"`) are not supported, though. The arguments are meant to be merged into the code using the `%` formatting operator.

The SQL wrapper is designed to be composable: the arguments can be either actual parameters, or SQL objects themselves:
    
    
    sql = SQL(
        "UPDATE TABLE %s SET %s",
        SQL.identifier(tablename),
        SQL("%s = %s", SQL.identifier(columnname), value),
    )
    

The combined SQL code is given by `sql.code`, while the corresponding combined parameters are given by the list `sql.params`. This allows to combine any number of SQL terms without having to separately combine their parameters, which can be tedious, bug-prone, and is the main downside of `psycopg2.sql <https://www.psycopg.org/docs/sql.html>`.

The second purpose of the wrapper is to discourage SQL injections. Indeed, if `code` is a string literal (not a dynamic string), then the SQL object made with `code` is guaranteed to be safe, provided the SQL objects within its parameters are themselves safe.

join(_args : Iterable_) → odoo.tools.sql.SQL[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/sql.py#L131)¶
    

Join SQL objects or parameters with `self` as a separator.

_classmethod _identifier(_name : [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_, _subname : Optional[[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")] = None_) → odoo.tools.sql.SQL[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/tools/sql.py#L147)¶
    

Return an SQL object that represents an identifier.

One important thing to know about models is that they don’t necessarily perform database updates right away. Indeed, for performance reasons, the framework delays the recomputation of fields after modifying records. And some database updates are delayed, too. Therefore, before querying the database, one has to make sure that it contains the relevant data for the query. This operation is called _flushing_ and performs the expected database updates.

Example
    
    
    # make sure that 'partner_id' is up-to-date in database
    self.env['model'].flush_model(['partner_id'])
    
    self.env.cr.execute(SQL("SELECT id FROM model WHERE partner_id IN %s", ids))
    ids = [row[0] for row in self.env.cr.fetchall()]
    

Before every SQL query, one has to flush the data needed for that query. There are three levels for flushing, each with its own API. One can flush either everything, all the records of a model, or some specific records. Because delaying updates improves performance in general, we recommend to be _specific_ when flushing.

Environment.flush_all()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L735)¶
    

Flush all pending computations and updates to the database.

Model.flush_model(_fnames =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6352)¶
    

Process the pending computations and database updates on `self`’s model. When the parameter is given, the method guarantees that at least the given fields are flushed to the database. More fields can be flushed, though.

Parametri
    

**fnames** – optional iterable of field names to flush

Model.flush_recordset(_fnames =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6364)¶
    

Process the pending computations and database updates on the records `self`. When the parameter is given, the method guarantees that at least the given fields on records `self` are flushed to the database. More fields and records can be flushed, though.

Parametri
    

**fnames** – optional iterable of field names to flush

Because models use the same cursor and the `Environment` holds various caches, these caches must be invalidated when _altering_ the database in raw SQL, or further uses of models may become incoherent. It is necessary to clear caches when using `CREATE`, `UPDATE` or `DELETE` in SQL, but not `SELECT` (which simply reads the database).

Example
    
    
    # make sure 'state' is up-to-date in database
    self.env['model'].flush_model(['state'])
    
    self.env.cr.execute("UPDATE model SET state=%s WHERE state=%s", ['new', 'old'])
    
    # invalidate 'state' from the cache
    self.env['model'].invalidate_model(['state'])
    

Just like flushing, one can invalidate either the whole cache, the cache of all the records of a model, or the cache of specific records. One can even invalidate specific fields on some records or all records of a model. As the cache improves performance in general, we recommend to be _specific_ when invalidating.

Environment.invalidate_all(_flush =True_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L719)¶
    

Invalidate the cache of all records.

Parametri
    

**flush** – whether pending updates should be flushed before invalidation. It is `True` by default, which ensures cache consistency. Do not use this parameter unless you know what you are doing.

Model.invalidate_model(_fnames =None_, _flush =True_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6729)¶
    

Invalidate the cache of all records of `self`’s model, when the cached values no longer correspond to the database values. If the parameter is given, only the given fields are invalidated from cache.

Parametri
    

  * **fnames** – optional iterable of field names to invalidate

  * **flush** – whether pending updates should be flushed before invalidation. It is `True` by default, which ensures cache consistency. Do not use this parameter unless you know what you are doing.




Model.invalidate_recordset(_fnames =None_, _flush =True_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6744)¶
    

Invalidate the cache of the records in `self`, when the cached values no longer correspond to the database values. If the parameter is given, only the given fields on `self` are invalidated from cache.

Parametri
    

  * **fnames** – optional iterable of field names to invalidate

  * **flush** – whether pending updates should be flushed before invalidation. It is `True` by default, which ensures cache consistency. Do not use this parameter unless you know what you are doing.




The methods above keep the caches and the database consistent with each other. However, if computed field dependencies have been modified in the database, one has to inform the models for the computed fields to be recomputed. The only thing the framework needs to know is _what_ fields have changed on _which_ records.

Example
    
    
    # make sure 'state' is up-to-date in database
    self.env['model'].flush_model(['state'])
    
    # use the RETURNING clause to retrieve which rows have changed
    self.env.cr.execute("UPDATE model SET state=%s WHERE state=%s RETURNING id", ['new', 'old'])
    ids = [row[0] for row in self.env.cr.fetchall()]
    
    # invalidate the cache, and notify the update to the framework
    records = self.env['model'].browse(ids)
    records.invalidate_recordset(['state'])
    records.modified(['state'])
    

One has to figure out which records have been modified. There are many ways to do this, possibly involving extra SQL queries. In the example above, we take advantage of the `RETURNING` clause of PostgreSQL to retrieve the information without an extra query. After making the cache consistent by invalidation, invoke the method `modified` on the modified records with the fields that have been updated.

Model.modified(_fnames_ , _create =False_, _before =False_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6773)¶
    

Notify that fields will be or have been modified on `self`. This invalidates the cache where necessary, and prepares the recomputation of dependent stored fields.

Parametri
    

  * **fnames** – iterable of field names modified on records `self`

  * **create** – whether called in the context of record creation

  * **before** – whether called before modifying records `self`




## Common ORM methods¶

### Create/update¶

Model.create(_vals_list_) → records[[sorgente]](https://github.com/odoo/odoo/blob/documentation-user/<decorator-gen-12>#L4559)¶
    

Creates new records for the model.

The new records are initialized using the values from the list of dicts `vals_list`, and if necessary those from `default_get()`.

Parametri
    

**vals_list** (_Union_ _[_[_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _[_[_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)") _]__,_[_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)") _]_) – 

values for the model’s fields, as a list of dictionaries:
    
    
    [{'field_name': field_value, ...}, ...]
    

For backward compatibility, `vals_list` may be a dictionary. It is treated as a singleton list `[vals]`, and a single record is returned.

see `write()` for details

Ritorna
    

the created records

Solleva
    

  * **AccessError** – if the current user is not allowed to create records of the specified model

  * **ValidationError** – if user tries to enter invalid value for a selection field

  * [**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "\(in Python v3.13\)") – if a field name specified in the create values does not exist.

  * **UserError** – if a loop would be created in a hierarchy of objects a result of the operation (such as setting an object as its own parent)




Model.copy(_default =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5586)¶
    

Duplicate record `self` updating it with default values

Parametri
    

**default** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – dictionary of field values to override in the original values of the copied record, e.g: `{'field_name': overridden_value, ...}`

Ritorna
    

new record

Model.default_get(_fields_list_) → default_values[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1470)¶
    

Return default values for the fields in `fields_list`. Default values are determined by the context, user defaults, and the model itself.

Parametri
    

**fields_list** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – names of field whose default is requested

Ritorna
    

a dictionary mapping field names to their corresponding default values, if they have a default value.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

Nota

Unrequested defaults won’t be considered, there is no need to return a value for fields whose names are not in `fields_list`.

Model.name_create(_name_) → record[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1697)¶
    

Create a new record by calling `create()` with only one value provided: the display name of the new record.

The new record will be initialized with any default values applicable to this model, or provided through the context. The usual behavior of `create()` applies.

Parametri
    

**name** – display name of the record to create

Tipo di ritorno
    

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)")

Ritorna
    

the (id, display_name) pair value of the created record

Model.write(_vals_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L4315)¶
    

Updates all records in `self` with the provided values.

Parametri
    

**vals** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – fields to update and the value to set on them

Solleva
    

  * **AccessError** – if user is not allowed to modify the specified records/fields

  * **ValidationError** – if invalid values are specified for selection fields

  * **UserError** – if a loop would be created in a hierarchy of objects a result of the operation (such as setting an object as its own parent)




  * For numeric fields (`Integer`, `Float`) the value should be of the corresponding type

  * For `Boolean`, the value should be a [`bool`](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

  * For `Selection`, the value should match the selection values (generally [`str`](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)"), sometimes [`int`](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)"))

  * For `Many2one`, the value should be the database identifier of the record to set

  * The expected value of a `One2many` or `Many2many` relational field is a list of `Command` that manipulate the relation the implement. There are a total of 7 commands: `create()`, `update()`, `delete()`, `unlink()`, `link()`, `clear()`, and `set()`.

  * For `Date` and `~odoo.fields.Datetime`, the value should be either a date(time), or a string.

Avvertimento

If a string is provided for Date(time) fields, it must be UTC-only and formatted according to `odoo.tools.misc.DEFAULT_SERVER_DATE_FORMAT` and `odoo.tools.misc.DEFAULT_SERVER_DATETIME_FORMAT`

  * Other non-relational fields use a string for value




### Search/Read¶

Model.browse([_ids_]) → records[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5846)¶
    

Returns a recordset for the ids provided as parameter in the current environment.
    
    
    self.browse([7, 18, 12])
    res.partner(7, 18, 12)
    

Parametri
    

**ids** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _or_ _iterable_ _(_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _) or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – id(s)

Ritorna
    

recordset

Model.search(_domain[, offset=0][, limit=None][, order=None]_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1604)¶
    

Search for the records that satisfy the given `domain` search domain.

Parametri
    

  * **domain** – A search domain. Use an empty list to match all records.

  * **offset** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – number of results to ignore (default: none)

  * **limit** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – maximum number of records to return (default: all)

  * **order** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – sort string



Ritorna
    

at most `limit` records matching the search criteria

Solleva
    

**AccessError** – if user is not allowed to access requested information

This is a high-level method, which should not be overridden. Its actual implementation is done by method `_search()`.

Model.search_count(_domain_[, _limit=None_]) → [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1587)¶
    

Returns the number of records in the current model matching the provided domain.

Parametri
    

  * **domain** – A search domain. Use an empty list to match all records.

  * **limit** – maximum number of record to count (upperbound) (default: all)




This is a high-level method, which should not be overridden. Its actual implementation is done by method `_search()`.

Model.search_fetch(_domain, field_names[, offset=0][, limit=None][, order=None]_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1625)¶
    

Search for the records that satisfy the given `domain` search domain, and fetch the given fields to the cache. This method is like a combination of methods `search()` and `fetch()`, but it performs both tasks with a minimal number of SQL queries.

Parametri
    

  * **domain** – A search domain. Use an empty list to match all records.

  * **field_names** – a collection of field names to fetch

  * **offset** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – number of results to ignore (default: none)

  * **limit** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – maximum number of records to return (default: all)

  * **order** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – sort string



Ritorna
    

at most `limit` records matching the search criteria

Solleva
    

**AccessError** – if user is not allowed to access requested information

Model.name_search(_name =''_, _args =None_, _operator ='ilike'_, _limit =100_) → records[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1719)¶
    

Search for records that have a display name matching the given `name` pattern when compared with the given `operator`, while also matching the optional search domain (`args`).

This is used for example to provide suggestions based on a partial value for a relational field. Should usually behave as the reverse of `display_name`, but that is not guaranteed.

This method is equivalent to calling `search()` with a search domain based on `display_name` and mapping id and display_name on the resulting search.

Parametri
    

  * **name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – the name pattern to match

  * **args** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – optional search domain (see `search()` for syntax), specifying further restrictions

  * **operator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – domain operator for matching `name`, such as `'like'` or `'='`.

  * **limit** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional max number of records to return



Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")

Ritorna
    

list of pairs `(id, display_name)` for all matching records.

Model.fetch(_field_names_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L3825)¶
    

Make sure the given fields are in memory for the records in `self`, by fetching what is necessary from the database. Non-stored fields are mostly ignored, except for their stored dependencies. This method should be called to optimize code.

Parametri
    

**field_names** – a collection of field names to fetch

Solleva
    

**AccessError** – if user is not allowed to access requested information

This method is implemented thanks to methods `_search()` and `_fetch_query()`, and should not be overridden.

Model.read([_fields_])[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L3563)¶
    

Read the requested fields for the records in `self`, and return their values as a list of dicts.

Parametri
    

  * **fields** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – field names to return (default is all fields)

  * **load** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – loading mode, currently the only option is to set to `None` to avoid loading the `display_name` of m2o fields



Ritorna
    

a list of dictionaries mapping field names to their values, with one dictionary per record

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")

Solleva
    

  * **AccessError** – if user is not allowed to access requested information

  * [**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "\(in Python v3.13\)") – if a requested field does not exist




This is a high-level method that is not supposed to be overridden. In order to modify how fields are read from database, see methods `_fetch_query()` and `_read_format()`.

Model._read_group(_domain_ , _groupby =()_, _aggregates =()_, _having =()_, _offset =0_, _limit =None_, _order =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L1856)¶
    

Get fields aggregations specified by `aggregates` grouped by the given `groupby` fields where record are filtered by the `domain`.

Parametri
    

  * **domain** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – A search domain. Use an empty list to match all records.

  * **groupby** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – list of groupby descriptions by which the records will be grouped. A groupby description is either a field (then it will be grouped by that field) or a string `'field:granularity'`. Right now, the only supported granularities are `'day'`, `'week'`, `'month'`, `'quarter'` or `'year'`, and they only make sense for date/datetime fields.

  * **aggregates** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – list of aggregates specification. Each element is `'field:agg'` (aggregate field with aggregation function `'agg'`). The possible aggregation functions are the ones provided by [PostgreSQL](https://www.postgresql.org/docs/current/static/functions-aggregate.html), `'count_distinct'` with the expected meaning and `'recordset'` to act like `'array_agg'` converted into a recordset.

  * **having** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – A domain where the valid «fields» are the aggregates.

  * **offset** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional number of groups to skip

  * **limit** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional max number of groups to return

  * **order** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional `order by` specification, for overriding the natural sort ordering of the groups, see also `search()`.



Ritorna
    

list of tuple containing in the order the groups values and aggregates values (flatten): `[(groupby_1_value, ... , aggregate_1_value_aggregate, ...), ...]`. If group is related field, the value of it will be a recordset (with a correct prefetch set).

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")

Solleva
    

**AccessError** – if user is not allowed to access requested information

Model.read_group(_domain_ , _fields_ , _groupby_ , _offset =0_, _limit =None_, _orderby =False_, _lazy =True_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L2681)¶
    

Get the list of records in list view grouped by the given `groupby` fields.

Parametri
    

  * **domain** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – A search domain. Use an empty list to match all records.

  * **fields** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – 

list of fields present in the list view specified on the object. Each element is either “field” (field name, using the default aggregation), or “field:agg” (aggregate field with aggregation function “agg”), or “name:agg(field)” (aggregate field with “agg” and return it as “name”). The possible aggregation functions are the ones provided by [PostgreSQL](https://www.postgresql.org/docs/current/static/functions-aggregate.html) and “count_distinct”, with the expected meaning.

  * **groupby** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – list of groupby descriptions by which the records will be grouped. A groupby description is either a field (then it will be grouped by that field) or a string “field:granularity”. Right now, the only supported granularities are “day”, “week”, “month”, “quarter” or “year”, and they only make sense for date/datetime fields.

  * **offset** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional number of groups to skip

  * **limit** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional max number of groups to return

  * **orderby** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional `order by` specification, for overriding the natural sort ordering of the groups, see also `search()` (supported only for many2one fields currently)

  * **lazy** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – if true, the results are only grouped by the first groupby and the remaining groupbys are put in the __context key. If false, all the groupbys are done in one call.



Ritorna
    

list of dictionaries(one dictionary for each record) containing:

  * the values of fields grouped by the fields in `groupby` argument

  * __domain: list of tuples specifying the search criteria

  * __context: dictionary with argument like `groupby`

  * __range: (date/datetime only) dictionary with field_name:granularity as keys
    

mapping to a dictionary with keys: «from» (inclusive) and «to» (exclusive) mapping to a string representation of the temporal bounds of the group




Tipo di ritorno
    

[{“field_name_1”: value, …}, …]

Solleva
    

**AccessError** – if user is not allowed to access requested information

#### Fields¶

Model.fields_get(_[allfields][, attributes]_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L3442)¶
    

Return the definition of each field.

The returned value is a dictionary (indexed by field name) of dictionaries. The _inherits’d fields are included. The string, help, and selection (if present) attributes are translated.

Parametri
    

  * **allfields** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – fields to document, all if empty or not provided

  * **attributes** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – attributes to return for each field, all if empty or not provided



Ritorna
    

dictionary mapping field names to a dictionary mapping attributes to values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

#### Search domains¶

A domain is a list of criteria, each criterion being a triple (either a `list` or a `tuple`) of `(field_name, operator, value)` where:

  * `field_name` (`str`)
    

a field name of the current model, or a relationship traversal through a `Many2one` using dot-notation e.g. `'street'` or `'partner_id.country'`

  * `operator` (`str`)
    

an operator used to compare the `field_name` with the `value`. Valid operators are:

`=`
    

equals to

`!=`
    

not equals to

`>`
    

greater than

`>=`
    

greater than or equal to

`<`
    

less than

`<=`
    

less than or equal to

`=?`
    

unset or equals to (returns true if `value` is either `None` or `False`, otherwise behaves like `=`)

`=like`
    

matches `field_name` against the `value` pattern. An underscore `_` in the pattern stands for (matches) any single character; a percent sign `%` matches any string of zero or more characters.

`like`
    

matches `field_name` against the `%value%` pattern. Similar to `=like` but wraps `value` with “%” before matching

`not like`
    

doesn’t match against the `%value%` pattern

`ilike`
    

case insensitive `like`

`not ilike`
    

case insensitive `not like`

`=ilike`
    

case insensitive `=like`

`in`
    

is equal to any of the items from `value`, `value` should be a list of items

`not in`
    

is unequal to all of the items from `value`

`child_of`
    

is a child (descendant) of a `value` record (value can be either one item or a list of items).

Takes the semantics of the model into account (i.e following the relationship field named by `_parent_name`).

`parent_of`
    

is a parent (ascendant) of a `value` record (value can be either one item or a list of items).

Takes the semantics of the model into account (i.e following the relationship field named by `_parent_name`).

`any`
    

matches if any record in the relationship traversal through `field_name` (`Many2one`, `One2many`, or `Many2many`) satisfies the provided domain `value`.

`not any`
    

matches if no record in the relationship traversal through `field_name` (`Many2one`, `One2many`, or `Many2many`) satisfies the provided domain `value`.

  * `value`
    

variable type, must be comparable (through `operator`) to the named field.




Domain criteria can be combined using logical operators in _prefix_ form:

`'&'`
    

logical _AND_ , default operation to combine criteria following one another. Arity 2 (uses the next 2 criteria or combinations).

`'|'`
    

logical _OR_ , arity 2.

`'!'`
    

logical _NOT_ , arity 1.

Nota

Mostly to negate combinations of criteria Individual criterion generally have a negative form (e.g. `=` -> `!=`, `<` -> `>=`) which is simpler than negating the positive.

Example

To search for partners named _ABC_ , with a phone or mobile number containing _7620_ :
    
    
    [('name', '=', 'ABC'),
     '|', ('phone','ilike','7620'), ('mobile', 'ilike', '7620')]
    

To search sales orders to invoice that have at least one line with a product that is out of stock:
    
    
    [('invoice_status', '=', 'to invoice'),
     ('order_line', 'any', [('product_id.qty_available', '<=', 0)])]
    

### Unlink¶

Model.unlink()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L4214)¶
    

Deletes the records in `self`.

Solleva
    

  * **AccessError** – if the user is not allowed to delete all the given records

  * **UserError** – if the record is default property for other records




### Record(set) information¶

Model.ids¶
    

Return the list of actual record ids corresponding to `self`.

odoo.models.env¶
    

Returns the environment of the given recordset.

Type
    

`Environment`

Model.exists() → records[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5617)¶
    

Returns the subset of records in `self` that exist. It can be used as a test on records:
    
    
    if record.exists():
        ...
    

By convention, new records are returned as existing.

Model.ensure_one()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L5887)¶
    

Verify that the current recordset holds a single record.

Solleva
    

**odoo.exceptions.ValueError** – `len(self) != 1`

Model.get_metadata()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L3995)¶
    

Return some metadata about the given records.

Ritorna
    

list of ownership dictionaries for each requested record

Tipo di ritorno
    

list of dictionaries with the following keys:

  * id: object id

  * create_uid: user who created the record

  * create_date: date when the record was created

  * write_uid: last user who changed the record

  * write_date: date of the last change to the record

  * xmlid: XML ID to use to refer to this record (if there is one), in format `module.name`

  * xmlids: list of dict with xmlid in format `module.name`, and noupdate as boolean

  * noupdate: A boolean telling if the record will be updated or not




### Operations¶

Recordsets are immutable, but sets of the same model can be combined using various set operations, returning new recordsets.

  * `record in set` returns whether `record` (which must be a 1-element recordset) is present in `set`. `record not in set` is the inverse operation

  * `set1 <= set2` and `set1 < set2` return whether `set1` is a subset of `set2` (resp. strict)

  * `set1 >= set2` and `set1 > set2` return whether `set1` is a superset of `set2` (resp. strict)

  * `set1 | set2` returns the union of the two recordsets, a new recordset containing all records present in either source

  * `set1 & set2` returns the intersection of two recordsets, a new recordset containing only records present in both sources

  * `set1 - set2` returns a new recordset containing only records of `set1` which are _not_ in `set2`




Recordsets are iterable so the usual Python tools are available for transformation ([`map()`](https://docs.python.org/3/library/functions.html#map "\(in Python v3.13\)"), [`sorted()`](https://docs.python.org/3/library/functions.html#sorted "\(in Python v3.13\)"), `ifilter()`, …) however these return either a [`list`](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") or an [iterator](https://docs.python.org/3/glossary.html#term-iterator "\(in Python v3.13\)"), removing the ability to call methods on their result, or to use set operations.

Recordsets therefore provide the following operations returning recordsets themselves (when possible):

#### Filter¶

Model.filtered(_func_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6145)¶
    

Return the records in `self` satisfying `func`.

Parametri
    

**func** (_callable_ _or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – a function or a dot-separated sequence of field names

Ritorna
    

recordset of records satisfying func, may be empty.
    
    
    # only keep records whose company is the current user's
    records.filtered(lambda r: r.company_id == user.company_id)
    
    # only keep records whose partner is a company
    records.filtered("partner_id.is_company")
    

Model.filtered_domain(_domain_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6194)¶
    

Return the records in `self` satisfying the domain and keeping the same order.

Parametri
    

**domain** – A search domain.

#### Map¶

Model.mapped(_func_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6106)¶
    

Apply `func` on all records in `self`, and return the result as a list or a recordset (if `func` return recordsets). In the latter case, the order of the returned recordset is arbitrary.

Parametri
    

**func** (_callable_ _or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – a function or a dot-separated sequence of field names

Ritorna
    

self if func is falsy, result of func applied to all `self` records.

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") or recordset
    
    
    # returns a list of summing two fields for each record in the set
    records.mapped(lambda r: r.field1 + r.field2)
    

The provided function can be a string to get field values:
    
    
    # returns a list of names
    records.mapped('name')
    
    # returns a recordset of partners
    records.mapped('partner_id')
    
    # returns the union of all partner banks, with duplicates removed
    records.mapped('partner_id.bank_ids')
    

Nota

Since V13, multi-relational field access is supported and works like a mapped call:
    
    
    records.partner_id  # == records.mapped('partner_id')
    records.partner_id.bank_ids  # == records.mapped('partner_id.bank_ids')
    records.partner_id.mapped('name')  # == records.mapped('partner_id.name')
    

#### Sort¶

Model.sorted(_key =None_, _reverse =False_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6320)¶
    

Return the recordset `self` ordered by `key`.

Parametri
    

  * **key** (_callable_ _or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – either a function of one argument that returns a comparison key for each record, or a field name, or `None`, in which case records are ordered according the default model’s order

  * **reverse** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – if `True`, return the result in reverse order



    
    
    # sort records by name
    records.sorted(key=lambda r: r.name)
    

#### Grouping¶

Model.grouped(_key_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/models.py#L6166)¶
    

Eagerly groups the records of `self` by the `key`, returning a dict from the `key`’s result to recordsets. All the resulting recordsets are guaranteed to be part of the same prefetch-set.

Provides a convenience method to partition existing recordsets without the overhead of a `read_group()`, but performs no aggregation.

Nota

unlike [`itertools.groupby()`](https://docs.python.org/3/library/itertools.html#itertools.groupby "\(in Python v3.13\)"), does not care about input ordering, however the tradeoff is that it can not be lazy

Parametri
    

**key** (_callable_ _|_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – either a callable from a `Model` to a (hashable) value, or a field name. In the latter case, it is equivalent to `itemgetter(key)` (aka the named field’s value)

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

## Inheritance and extension¶

Odoo provides three different mechanisms to extend models in a modular way:

  * creating a new model from an existing one, adding new information to the copy but leaving the original module as-is

  * extending models defined in other modules in-place, replacing the previous version

  * delegating some of the model’s fields to records it contains




### Classical inheritance¶

When using the `_inherit` and `_name` attributes together, Odoo creates a new model using the existing one (provided via `_inherit`) as a base. The new model gets all the fields, methods and meta-information (defaults & al) from its base.
    
    
    class Inheritance0(models.Model):
        _name = 'inheritance.0'
        _description = 'Inheritance Zero'
    
        name = fields.Char()
    
        def call(self):
            return self.check("model 0")
    
        def check(self, s):
            return "This is {} record {}".format(s, self.name)
    
    class Inheritance1(models.Model):
        _name = 'inheritance.1'
        _inherit = 'inheritance.0'
        _description = 'Inheritance One'
    
        def call(self):
            return self.check("model 1")
    

and using them:
    
    
    a = env['inheritance.0'].create({'name': 'A'})
    b = env['inheritance.1'].create({'name': 'B'})
    
    a.call()
    b.call()
    

will yield:

> «This is model 0 record A» «This is model 1 record B»

the second model has inherited from the first model’s `check` method and its `name` field, but overridden the `call` method, as when using standard [Python inheritance](https://docs.python.org/3/tutorial/classes.html#tut-inheritance "\(in Python v3.13\)").

### Extension¶

When using `_inherit` but leaving out `_name`, the new model replaces the existing one, essentially extending it in-place. This is useful to add new fields or methods to existing models (created in other modules), or to customize or reconfigure them (e.g. to change their default sort order):
    
    
    class Extension0(models.Model):
    _name = 'extension.0'
    _description = 'Extension zero'
    
    name = fields.Char(default="A")
    
    class Extension1(models.Model):
    _inherit = 'extension.0'
    
    description = fields.Char(default="Extended")
    
    
    
    record = env['extension.0'].create({})
    record.read()[0]
    

will yield:
    
    
    {'name': "A", 'description': "Extended"}
    

Nota

It will also yield the various automatic fields unless they’ve been disabled

### Delegation¶

The third inheritance mechanism provides more flexibility (it can be altered at runtime) but less power: using the `_inherits` a model _delegates_ the lookup of any field not found on the current model to «children» models. The delegation is performed via `Reference` fields automatically set up on the parent model.

The main difference is in the meaning. When using Delegation, the model **has one** instead of **is one** , turning the relationship in a composition instead of inheritance:
    
    
    class Screen(models.Model):
        _name = 'delegation.screen'
        _description = 'Screen'
    
        size = fields.Float(string='Screen Size in inches')
    
    class Keyboard(models.Model):
        _name = 'delegation.keyboard'
        _description = 'Keyboard'
    
        layout = fields.Char(string='Layout')
    
    class Laptop(models.Model):
        _name = 'delegation.laptop'
        _description = 'Laptop'
    
        _inherits = {
            'delegation.screen': 'screen_id',
            'delegation.keyboard': 'keyboard_id',
        }
    
        name = fields.Char(string='Name')
        maker = fields.Char(string='Maker')
    
        # a Laptop has a screen
        screen_id = fields.Many2one('delegation.screen', required=True, ondelete="cascade")
        # a Laptop has a keyboard
        keyboard_id = fields.Many2one('delegation.keyboard', required=True, ondelete="cascade")
    
    
    
    record = env['delegation.laptop'].create({
        'screen_id': env['delegation.screen'].create({'size': 13.0}).id,
        'keyboard_id': env['delegation.keyboard'].create({'layout': 'QWERTY'}).id,
    })
    record.size
    record.layout
    

will result in:
    
    
    13.0
    'QWERTY'
    

and it’s possible to write directly on the delegated field:
    
    
    record.write({'size': 14.0})
    

Avvertimento

when using delegation inheritance, methods are _not_ inherited, only fields

Avvertimento

  * `_inherits` is more or less implemented, avoid it if you can;

  * chained `_inherits` is essentially not implemented, we cannot guarantee anything on the final behavior.




### Fields Incremental Definition¶

A field is defined as class attribute on a model class. If the model is extended, one can also extend the field definition by redefining a field with the same name and same type on the subclass. In that case, the attributes of the field are taken from the parent class and overridden by the ones given in subclasses.

For instance, the second class below only adds a tooltip on the field `state`:
    
    
    class First(models.Model):
        _name = 'foo'
        state = fields.Selection([...], required=True)
    
    class Second(models.Model):
        _inherit = 'foo'
        state = fields.Selection(help="Blah blah blah")
    

## Error management¶

The Odoo Exceptions module defines a few core exception types.

Those types are understood by the RPC layer. Any other exception type bubbling until the RPC layer will be treated as a “Server error”.

Nota

If you consider introducing new exceptions, check out the `odoo.addons.test_exceptions` module.

_exception _odoo.exceptions.UserError(_message_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L18)¶
    

Generic error managed by the client.

Typically when the user tries to do something that has no sense given the current state of a record. Semantically comparable to the generic 400 HTTP status codes.

_exception _odoo.exceptions.RedirectWarning(_message_ , _action_ , _button_text_ , _additional_context =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L32)¶
    

Warning with a possibility to redirect the user instead of simply displaying the warning message.

Parametri
    

  * **message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – exception message and frontend modal content

  * **action_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – id of the action where to perform the redirection

  * **button_text** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – text to put on the button that will trigger the redirection.

  * **additional_context** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – parameter passed to action_id. Can be used to limit a view to active_ids for example.




_exception _odoo.exceptions.AccessDenied(_message ='Access Denied'_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L55)¶
    

Login/password error.

Nota

No traceback.

Example

When you try to log with a wrong password.

_exception _odoo.exceptions.AccessError(_message_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L74)¶
    

Access rights error.

Example

When you try to read a record that you are not allowed to.

_exception _odoo.exceptions.CacheMiss(_record_ , _field_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L83)¶
    

Missing value(s) in cache.

Example

When you try to read a value in a flushed cache.

_exception _odoo.exceptions.MissingError(_message_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L95)¶
    

Missing record(s).

Example

When you try to write on a deleted record.

_exception _odoo.exceptions.ValidationError(_message_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/odoo/exceptions.py#L104)¶
    

Violation of python constraints.

Example

When you try to create a new user with a login which already exist in the db.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/backend/orm.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](orm/changelog.html "Changelog") |
  * [precedente](../backend.html "Server framework") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * ORM API


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases