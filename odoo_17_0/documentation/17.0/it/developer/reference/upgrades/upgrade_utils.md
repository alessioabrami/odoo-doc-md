# Upgrade utils — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../external_api.html "External API") |
  * [precedente](upgrade_scripts.html "Upgrade scripts") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Upgrades](../upgrades.html) »
  * Upgrade utils



# Upgrade utils¶

[Upgrade utils](https://github.com/odoo/upgrade-util/) is a library that contains helper functions to facilitate the writing of upgrade scripts. This library, used by Odoo for the upgrade scripts of standard modules, provides reliability and helps speed up the upgrade process:

  * The helper functions help make sure the data is consistent in the database.

  * It takes care of indirect references of the updated records.

  * Allows calling functions and avoid writing code, saving time and reducing development risks.

  * Helpers allow to focus on what is important for the upgrade and not think of details.




## Installation¶

Clone the [Upgrade utils repository](https://github.com/odoo/upgrade-util/) locally and start `odoo` with the `src` directory prepended to the `--upgrade-path` option.
    
    
    $ ./odoo-bin --upgrade-path=/path/to/upgrade-util/src,/path/to/other/upgrade/script/directory [...]
    

On platforms where you do not manage Odoo yourself, you can install this library via `pip`:
    
    
    $ python3 -m pip install git+https://github.com/odoo/upgrade-util@master
    

On [Odoo.sh](https://www.odoo.sh/) it is recommended to add it to the `requirements.txt` of the custom repository. For this, add the following line inside the file:
    
    
    odoo_upgrade @ git+https://github.com/odoo/upgrade-util@master
    

## Using upgrade utils¶

Once installed, the following packages are available for the upgrade scripts:

  * `odoo.upgrade.util`: the helper itself.

  * `odoo.upgrade.testing`: base TestCase classes.




To use it in upgrade scripts, simply import it:
    
    
    from odoo.upgrade import util
    
    
    def migrate(cr, version):
       # Rest of the script
    

Now, the helper functions are available to be called through `util`.

## Util functions¶

Upgrade utils provides many useful functions to ease the upgrade process. Here, we describe some of the most useful ones. Refer to the [util folder](https://github.com/odoo/upgrade-util/tree/master/src/util) for the comprehensive declaration of helper functions.

Nota

The `cr` parameter in util functions always refers to the database cursor. Pass the one received as a parameter in [`migrate()`](upgrade_scripts.html#migrate "migrate"). Not all functions need this parameter.

### Modules¶

Utility functions for module-level operations.

In most cases module operations (rename, merge, remove, …) should be performed in a `base` script. The reason is that once the `base` module is upgraded, all the information regarding modules should be already set in the DB for the upgrade process to function correctly. The command line option `--pre-upgrade-scripts` (available from Odoo 16) allows to run upgrade scripts _before_ loading base. This is the recommended way to perform module operations after a major upgrade.

odoo.upgrade.util.modules.modules_installed(_cr_ , _* modules_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L88)¶
    

Return whether _all_ given modules are installed.

Parametri
    

**modules** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – names of the modules to check

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

Nota

In the context of upgrades a module is considered as installed if it is marked for upgrade, or for installation; even if they are not yet fully installed.

odoo.upgrade.util.modules.module_installed(_cr_ , _module_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L113)¶
    

Return whether a module is installed.

Parametri
    

**module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to check

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

See `modules_installed()`.

odoo.upgrade.util.modules.uninstall_module(_cr_ , _module_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L125)¶
    

Uninstall and remove all records owned by a module.

Parametri
    

**module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to uninstall

odoo.upgrade.util.modules.uninstall_theme(_cr_ , _theme_ , _base_theme =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L254)¶
    

Uninstall a theme module and remove it from websites.

Parametri
    

  * **theme** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the theme module to uninstall

  * **base_theme** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – if not `None`, unload first this base theme




Avvertimento

This function can only be used in `post-` scripts of `website` module as it relies on the ORM.

See `remove_theme()` and `uninstall_module()`.

odoo.upgrade.util.modules.remove_module(_cr_ , _module_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L289)¶
    

Completely remove a module.

This operation is equivalent to uninstall and removal of _all_ references to the module - no trace of it is left in the database.

Parametri
    

**module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to remove

Avvertimento

Since this function removes _all_ data associated to the module. Ensure to reassign records before calling this function.

odoo.upgrade.util.modules.remove_theme(_cr_ , _theme_ , _base_theme =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L314)¶
    

Uninstall a theme module.

Avvertimento

This function can only be used in `post-` scripts.

See `remove_module()` and `uninstall_theme()`.

odoo.upgrade.util.modules.rename_module(_cr_ , _old_ , _new_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L348)¶
    

Rename a module and all references to it.

Parametri
    

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – current name of the module to rename

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new name of the module to rename




odoo.upgrade.util.modules.merge_module(_cr_ , _old_ , _into_ , _update_dependers =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L376)¶
    

Merge a module into another.

This function moves all references and records from the source module to the destination module.

Avvertimento

This functions does not remove any record, but it removes xml_ids from the source module with a conflicting name in the destination module.

Parametri
    

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to be merged

  * **into** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to merge into

  * **update_dependers** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the dependencies of modules that depend on `old` are updated




odoo.upgrade.util.modules.force_install_module(_cr_ , _module_ , _if_installed =None_, _reason ='it has been explicitly asked for'_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L512)¶
    

Force the ORM to install a module.

Parametri
    

  * **module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module to install

  * **if_installed** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – only force the install when these modules are already installed



Return str
    

the _new_ state of the module

odoo.upgrade.util.modules.force_upgrade_of_fresh_module(_cr_ , _module_ , _init =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L870)¶
    

Force the execution of upgrade scripts for a module that is being installed.

Standard Odoo doesn’t run upgrade scripts when a module is being installed. This makes sense because, technically speaking, the module is not being upgraded. Still, it happens that a (new) module needs to perform some operations for it to be correctly installed, like grabbing data from another module. This is common when a module is functionally _split_ into several ones.

Parametri
    

  * **module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module for which to force the execution of upgrade scripts

  * **init** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to set the module to be in _init_ mode




Being in init mode has the side effect of not respecting noupdate flags, in XML file nor in `ir_model_data`.

odoo.upgrade.util.modules.move_model(_cr_ , _model_ , _from_module_ , _to_module_ , _move_data =False_, _keep =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/modules.py#L990)¶
    

Move a model from one module to another.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model to move

  * **from_module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module where the model is originally defined

  * **to_module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the destination module where the model is to be moved

  * **move_data** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to also update `ir_model_data` for records of the model

  * **keep** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of XML ids to keep - not move




This function can be called for moving overrides of a model to another module. As it cannot distinguish between source model or inherited model, it raises an exception if the destination module isn’t installed.

### Models¶

Utility functions for modifying models.

Model operations are best done in `pre-` script of the involved modules.

odoo.upgrade.util.models.remove_model(_cr_ , _model_ , _drop_table =True_, _ignore_m2m =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/models.py#L61)¶
    

Remove a model and its references from the database.

Some required indirect references to the model are replaced by the _unknown model_ \- an empty model that serves as placeholder for gone models.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model to remove

  * **drop_table** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to drop the table of this model

  * **ignore_m2m** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of m2m tables to ignore - not removed, use `"*"` to ignore (keep) all m2m tables




odoo.upgrade.util.models.delete_model(_cr_ , _model_ , _drop_table =True_, _ignore_m2m =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/models.py#L61)¶
    

Remove a model and its references from the database.

Some required indirect references to the model are replaced by the _unknown model_ \- an empty model that serves as placeholder for gone models.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model to remove

  * **drop_table** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to drop the table of this model

  * **ignore_m2m** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of m2m tables to ignore - not removed, use `"*"` to ignore (keep) all m2m tables




odoo.upgrade.util.models.rename_model(_cr_ , _old_ , _new_ , _rename_table =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/models.py#L271)¶
    

Rename a model.

Parametri
    

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – current name of the model to rename

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new name of the model to rename

  * **rename_table** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to also rename the table of the model




odoo.upgrade.util.models.merge_model(_cr_ , _source_ , _target_ , _drop_table =True_, _fields_mapping =None_, _ignore_m2m =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/models.py#L399)¶
    

Merge a model into another one.

This function moves all the references from `source` model into `target` model and _removes_ `source` model and its references. By default, only the fields with the same name in both models are moved from source to target, optionally a mapping with differently named fields can be provided.

Avvertimento

This function does not move the records from `source` model to `target` model.

Parametri
    

  * **source** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model to be merged

  * **target** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the destination model to merge into

  * **drop_table** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to drop the table of the source model

  * **fields_mapping** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – mapping of field names from source to target model, when `None` only fields with same name are moved

  * **ignore_m2m** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of m2m tables ignored to remove from source model.




odoo.upgrade.util.models.remove_inherit_from_model(_cr_ , _model_ , _inherit_ , _keep =()_, _skip_inherit =()_, _with_inherit_parents =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/models.py#L541)¶
    

Remove `inherit` from `model`.

This function removes all fields inherited via `inherit` from a `model` and all its descendant models. All fields from the inherit, including those from its parent models are also removed, unless `with_inherit_parents` mode is unset. In such case only fields from `inherit` are removed, excluding fields in its parents. Fields listed in `keep` are never removed. If some descendants from `model` are listed in `skip_inherit` they will keep the fields from `inherit`.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model from which to remove the inherit

  * **inherit** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the inherited model (or mixin) to remove

  * **keep** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – tuple with field names to keep

  * **skip_inherit** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of descendant models of `model` to not process

  * **with_inherit_parents** (_boolean_) – if unset, remove fields coming from `inherit` only, keeping all fields from its parents




### Fields¶

Utility functions for modifying model fields.

Field operations are best done in `pre-` script of the involved modules. In some cases a preliminary operation could be done in pre and finished in post. A common example is to remove a field in pre- keeping its column, later used in post when the column is finally dropped.

odoo.upgrade.util.fields.remove_field(_cr_ , _model_ , _fieldname_ , _cascade =False_, _drop_column =True_, _skip_inherit =()_, _keep_as_attachments =False_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L186)¶
    

Remove a field and its references from the database.

This function also removes the field from inheriting models, unless exceptions are specified in `skip_inherit`. When the field is stored we can choose to not drop the column.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the field to remove

  * **fieldname** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the field to remove

  * **cascade** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field column(s) are removed in `CASCADE` mode

  * **drop_column** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field’s column is dropped

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of inheriting models to skip the removal of the field, use `"*"` to skip all

  * **keep_as_attachments** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – for binary fields, whether the data should be kept as attachments




odoo.upgrade.util.fields.make_field_non_stored(_cr_ , _model_ , _field_ , _selectable =False_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L401)¶
    

Convert field to non-stored.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the field to convert

  * **fieldname** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the field to convert

  * **selectable** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the field is still selectable, if True custom `ir.filters` are not updated




odoo.upgrade.util.fields.move_field_to_module(_cr_ , _model_ , _fieldname_ , _old_module_ , _new_module_ , _skip_inherit =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L442)¶
    

Move a field from one module to another.

This functions updates all references to a specific field, switching from the source module to the destination module. It avoid data removal after the registry is fully loaded. The field in inheriting models are also moved unless skipped.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the owner model of the field to move

  * **fieldname** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the field to move

  * **old_module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – source module name from which the field is moved

  * **new_module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – target module name into which the field is moved

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of inheriting models for which the field is not to be moved, use `"*"` to skip all




odoo.upgrade.util.fields.rename_field(_cr_ , _model_ , _old_ , _new_ , _update_references =True_, _domain_adapter =None_, _skip_inherit =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L481)¶
    

Rename a field and its references from `old` to `new` on the given `model`.

The field is updated in all inheriting models, except for models specified in `skip_inherit`.

This functions also updates references, indirect or direct ones, including filters, server actions, related fields, emails, dashboards, domains, and many more. See `update_field_usage()`

For the update of domains a special adapter function can be used. The default adapter just replaces `old` by `new` in each domain leaf. Refer to `adapt_domains()` for information about domain adapters.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the field to rename

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – current name of the field to rename

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new name of the field to rename

  * **update_references** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to update all references

  * **domain_adapter** (_function_) – adapter to use for domains, see `adapt_domains()`

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – models to skip when renaming the field in inheriting models, use `"*"` to skip all




odoo.upgrade.util.fields.invert_boolean_field(_cr_ , _model_ , _old_ , _new_ , _skip_inherit =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L631)¶
    

Rename a boolean field and invert its value.

odoo.upgrade.util.fields.change_field_selection_values(_cr_ , _model_ , _field_ , _mapping_ , _skip_inherit =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L1005)¶
    

Replace references of values of a selection field.

This function replaces all references to selection values according to a mapping. Domains are also updated.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the selection field to update

  * **field** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the selection field to update

  * **mapping** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – selection values to update, key values are replaced by their corresponding values in the mapping

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – list of inheriting models to skip in the update of the selection values, use `"*"` to skip all




odoo.upgrade.util.fields.update_field_usage(_cr_ , _model_ , _old_ , _new_ , _domain_adapter =None_, _skip_inherit =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/fields.py#L1092)¶
    

Replace all references to the field `old` by `new` in different places.

Search in:
    

  * ir_filters

  * ir_exports_line

  * ir_act_server

  * mail_alias

  * ir_ui_view_custom (dashboard)

  * domains (using `domain_adapter`)

  * related fields




This function can be used to replace the usage of a field by another. Domains are updated using the `domain_adapter`. By default the domain adapter just replaces `old` by `new` in domain leaves. See `adapt_domains()` for more information about domain adapters.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the field

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – source name of the field to replace

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – target name of the field to set

  * **domain_adapter** (_function_) – adapter to use for domains, see `adapt_domains()`

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – models to skip when renaming the field in inheriting models, use `"*"` to skip all




### Records¶

Utility functions for record-level operations.

odoo.upgrade.util.records.remove_view(_cr_ , _xml_id =None_, _view_id =None_, _silent =False_, _key =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L67)¶
    

Remove a view and all its descendants.

This function recursively deletes the given view and its inherited views, as long as they are part of a module. It will fail as soon as a custom view exists anywhere in the hierarchy. It also removes multi-website COWed views.

Parametri
    

  * **xml_id** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional, the xml_id of the view to remove

  * **view_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional, the ID of the view to remove

  * **silent** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to show in the logs disabled custom views

  * **key** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – key used to detect multi-website COWed views, if `None` then set to `xml_id` if provided, otherwise set to the xml_id referencing the view with ID `view_id` if any




Avvertimento

Either `xml_id` or `view_id` must be set. Specifying both will raise an error.

odoo.upgrade.util.records.edit_view(_cr_ , _xmlid =None_, _view_id =None_, _skip_if_not_noupdate =True_, _active ='auto'_)[[sorgente]](https://github.com/usr/lib/python3.10/contextlib.py#L179)¶
    

Context manager to edit a view’s arch.

This function returns a context manager that may yield a parsed arch of a view as an [etree Element](https://lxml.de/tutorial.html#the-element-class). Any changes done in the returned object will be written back to the database upon exit of the context manager, updating also the translated versions of the arch. Since the function may not yield, use `skippable_cm()` to avoid errors.
    
    
    with util.skippable_cm(), util.edit_view(cr, "xml.id") as arch:
        arch.attrib["string"] = "My Form"
    

To select the target view to edit use either `xmlid` or `view_id`, not both.

When the view is identified by `view_id`, the arch is always yielded if the view exists, with disregard to any `noupdate` flag it may have associated. When `xmlid` is set, if the view `noupdate` flag is `False` then the arch will not be yielded _unless_ `skip_if_not_noupdate` is set to `False`. If `noupdate` is `True`, the view will be yielded for edit.

If the `active` argument is `True` or `False`, the `active` flag of the view will be set accordingly.

Nota

If `active` is «auto» (default value), the view will be activated if selected via `xmlid` and left untouched if selected via `view_id`.

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – optional, xml_id of the view edit

  * **view_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – optional, ID of the view to edit

  * **skip_if_not_noupdate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to force the edit of views requested via `xmlid` parameter even if they are flagged as `noupdate=True`, ignored if `view_id` is set

  * **active** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)") _or_ _"auto"_) – active flag value to set. Unchanged when `None`.



Ritorna
    

a context manager that yields the parsed arch, upon exit the context manager writes back the changes.

odoo.upgrade.util.records.remove_record(_cr_ , _name_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L342)¶
    

Remove a record and its references corresponding to the given [xml_id](../../glossary.html#term-external-identifier).

Parametri
    

**name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `module.name`

odoo.upgrade.util.records.is_changed(_cr_ , _xmlid_ , _interval ='1 minute'_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L572)¶
    

Return whether a record was changed.

This function checks if a record was changed before the current upgrade start time. See `upgrade-util/src/base/0.0.0/pre-00-upgrade-start.py`

This utility will return a false positive on xmlids of records that match the following conditions:

>   * Have been updated in an upgrade preceding the current one
> 
>   * Have not been updated in the current upgrade
> 
> 


If the `xmlid` doesn’t exist in the DB this function returns `None`.

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – `xmlid` of the record to check

  * **interval** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – SQL interval, a record is considered as changed if `write_date > create_date + interval`



Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

odoo.upgrade.util.records.if_unchanged(_cr_ , _xmlid_ , _callback_ , _interval ='1 minute'_, _** kwargs_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L616)¶
    

Run `callback` if a record is unchanged.

This function will run a `callback` when the referred record is unchanged. The `xmlid` and any extra parameter, but not `interval`, will be passed to the `callback`. In case the record was changed it will be marked as `noupdate=True`. See also `is_changed()` and `force_noupdate()`.

This function is useful to take an action _only_ when a record hasn’t been updated, a common example is to force an update from XML even if the record was `noupdate=True`
    
    
    util.if_unchanged(cr, "mymodule.myrecord", util.update_record_from_xml)
    

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – xml_id of the record to check

  * **callback** (_function_) – callback to execute in case the record was _not_ changed, all extra parameters to this function are passed to the callback

  * **interval** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – interval after `create_date` on which a record is considered as _changed_, see `is_changed()`




odoo.upgrade.util.records.rename_xmlid(_cr_ , _old_ , _new_ , _noupdate =None_, _on_collision ='fail'_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L735)¶
    

Rename an [external identifier](../../glossary.html#term-external-identifier) (`xml_id`) of a record.

A rename cannot happen when the target name already exists on the database. In such cases there are two options to control how this function behaves:

  * `fail`: raise an exception and prevent renaming

  * `merge`: rename the external identifier, remove the old one, and _replace_ references. See `replace_record_references_batch()`




Nota

This function does not remove records, it only updates xml_ids.

Parametri
    

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – current xml_id of the record, under the format `module.name`

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new xml_id of the record, under the format `module.name`

  * **noupdate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – value to set on the `noupdate` flag of the xml_id, ignored if `None`

  * **on_collision** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – how to proceed if the xml_id already exists, the options are `merge` or `fail` (default)



Ritorna
    

the ID of the record referenced by the _new_ xml_id, `None` when the record doesn’t exist

Tipo di ritorno
    

[int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

odoo.upgrade.util.records.ref(_cr_ , _xmlid_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L858)¶
    

Return the id corresponding to the given [xml_id](../../glossary.html#term-external-identifier).

Parametri
    

**xml_id** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `module.name`

Ritorna
    

ID of the referenced record, `None` if not found.

Tipo di ritorno
    

[int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

odoo.upgrade.util.records.force_noupdate(_cr_ , _xmlid_ , _noupdate =True_, _warn =False_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L885)¶
    

Update the `noupdate` flag of a record.

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `module.name`

  * **noupdate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – value to set on the `noupdate` flag

  * **warn** – whether to output a warning in the logs when the flag was switched from `True` to `False`




odoo.upgrade.util.records.ensure_xmlid_match_record(_cr_ , _xmlid_ , _model_ , _values_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L913)¶
    

Ensure an xml_id references a record with specific values.

This function ensures the record pointed by an xml_id matches the values for the fields specified in the `values` parameter. When the xmlid exist but it points to a record that doesn’t match the values, the xmlid is updated to point to a record that matches the values if one is found. If the xmlid doesn’t exist, it is created with the found record. When no matching record is found, nothing is done. In all cases the referenced record, after a possible update, of the xml_id is returned.

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `module.name`

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – model name of the record

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – 

mapping of field names to values the record must fulfill

Example
        
        values = {"id": 123}
        values = {"name": "INV/2024/0001", "company_id": 1}
        



Ritorna
    

the ID of the matched record, `None` if no record found

Tipo di ritorno
    

[int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") or [None](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")

Suggerimento

This function is useful when migrating in-database records into a custom module, to create the xml_ids before the module is updated and avoid duplication.

odoo.upgrade.util.records.update_record_from_xml(_cr_ , _xmlid_ , _reset_write_metadata =True_, _force_create =AUTOMATIC_, _from_module =None_, _reset_translations =()_, _ensure_references =False_, _fields =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L1012)¶
    

Update a record based on its definition in the [Data Files](../backend/data.html).

This function ignores the `noupdate` flag on the record. It searches in all XML files from the manifest of the module in the xmlid, or the `from_module` parameter if set, for a matching definition. When found, it forces the ORM to update the record as in the specs in the data file.

Optionally this function can reset the translations of some fields.

Parametri
    

  * **xmlid** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – record xml_id, under the format `module.name`

  * **reset_write_metadata** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to update the `write_date` of the record

  * **force_create** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the record is created if it does not exist. `True` by default, unless `fields` is not None.

  * **from_module** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the module from which to update the record, necessary only when the specs are in a different module than the one in the xml_id

  * **reset_translations** ([_set_](https://docs.python.org/3/library/stdtypes.html#set "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – field names whose translations get reset

  * **ensure_references** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether referred records via `ref` XML attributes should also be updated.

  * **fields** ([_set_](https://docs.python.org/3/library/stdtypes.html#set "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _) or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – optional list of fields to include in the XML declaration. If set, all other fields will be ignored. When set, record won’t be created if missing.




Avvertimento

This functions uses the ORM, therefore it can only be used after **all** models referenced in the data specs of the record are already **loaded**. In practice this means that this function should be used in `post-` or `end-` scripts.

Nota

The standard behavior of ORM is to create the record if it doesn’t exist, including its xml_id. That will happen on this function as well, unless `force_create` is set to `False`.

odoo.upgrade.util.records.delete_unused(_cr_ , _* xmlids_, _** kwargs_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L1266)¶
    

Remove unused records.

This function will remove records pointed by `xmlids` only if they are not referenced from any table. For hierarchical records (like product categories), it verifies if the children marked as cascade removal are also not referenced. In which case the record and its children are all removed.

Nota

The records that cannot be removed are set as `noupdate=True`.

Parametri
    

  * **xmlids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of xml_ids to check for removal

  * **deactivate** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to deactivate records that cannot be removed because they are referenced, `False` by default

  * **keep_xmlids** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to keep the xml_ids of records that cannot be removed. By default `True` for versions up to 18.0, `False` from `saas~18.1` on.



Ritorna
    

list of ids of removed records, if any

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")([int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)"))

odoo.upgrade.util.records.replace_record_references_batch(_cr_ , _id_mapping_ , _model_src_ , _model_dst =None_, _replace_xmlid =True_, _ignores =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L1443)¶
    

Replace all references to records.

This functions replaces _all_ references, direct or indirect to records of `model_src` by the corresponding records in the mapping. If the target model of the mapping is not the same as the source one, then `model_dst` parameter must be set.

Parametri
    

  * **id_mapping** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)") _(_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _,_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _)_) – mapping of IDs to replace, key value is replaced by the mapped value

  * **model_src** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the source model of the records to replace

  * **model_dst** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the target model of the records to replace, if `None` the target is assumed the same as the source

  * **replace_xmlid** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to replace the references in xml_ids pointing to the source records

  * **ignores** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of **table** names to skip when updating the referenced values




odoo.upgrade.util.records.replace_in_all_jsonb_values(_cr_ , _table_ , _column_ , _old_ , _new_ , _extra_filter =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/records.py#L1787)¶
    

Replace values in JSONB columns.

This function replaces `old` by `new` in JSONB values. It is useful for replacing values in _all_ translations of translated fields.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table name where the values are to be replaced

  * **column** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – column name where the values are to be replaced

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – original value to replace, can be a simple term (str) or a Postgres regular expression wrapped by `PGRegexp`

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new value to set, can be a simple term or a expression using `<number>` notation to refer to _captured groups_ if `old` is a regexp expression

  * **extra_filter** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – extra `WHERE` compatible clause to filter the values to update, must use the `t` alias for the table, it can also include `{parallel_filter}` to execute the query in parallel, see `explode_execute()`




### ORM¶

Utility functions to perform operations via the ORM.

The functions on this module allow to use the ORM safely during upgrades. They enhance or patch the ORM such that it can handle high volumes of data in a performant way. In some cases totally different alternatives to the ORM’s own functions are provided. The functions on this module work along the ORM of _all_ supported versions.

odoo.upgrade.util.orm.env(_cr_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/orm.py#L56)¶
    

Create a new environment.

Avvertimento

This function does _not_ empty the cache maintained on the cursor for superuser with an empty environment. A call to `invalidate_cache` may be necessary every time data is modified directly in the database.

Ritorna
    

the new environment

Tipo di ritorno
    

[`Environment`](../backend/orm.html#odoo.api.Environment "odoo.api.Environment")

odoo.upgrade.util.orm.recompute_fields(_cr_ , _model_ , _fields_ , _ids=None_ , _logger= <Logger odoo.upgrade.util.orm (WARNING)>_, _chunk_size=256_ , _strategy='auto'_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/orm.py#L253)¶
    

Recompute field values.

This function will recompute fields of a model restricted to a set of records - or all. The re-computation is not done on all records at the same time. It is split in batches (chunks). This avoids performance issues, and, in the worse cases, failures due to `MemoryError`. After each chunk is processed the data is sent back to the database according to one of the following strategies:

  * _flush_ : use the `flush` method of the ORM

  * _commit_ : `commit` the cursor - also flush

  * _auto_ : pick the best alternative between the two above given the number of records to compute and the presence of tracked fields.




The _commit_ strategy is less prone to cause a `MemoryError` for a huge volume of data.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model to recompute

  * **fields** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of the name of the fields to recompute

  * **ids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _) or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – list of the IDs of the records to recompute, when `None` recompute _all_ records

  * **logger** ([`logging.Logger`](https://docs.python.org/3/library/logging.html#logging.Logger "\(in Python v3.13\)")) – logger used to report the progress

  * **chunk_size** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – number of records per chunk - used to split the processing

  * **strategy** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – strategy used to process the re-computation




_class _odoo.upgrade.util.orm.iter_browse(_model_ , _* args_, _** kw_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/orm.py#L314)¶
    

Iterate over recordsets.

The `callable` object returned by this class can be used as an iterator that loads records by chunks (into a `recordset`). After each chunk is exhausted their data is sent back to the database - flushed or committed - and a new chunk is loaded.

This class allows to run code like:
    
    
    for record in env['my.model'].browse(ids):
        record.field1 = val
    
    env['my.model'].browse(ids)._compute_field2()
    env['my.model'].create(values)
    

in a performant way while also avoiding `MemoryError`, even when `ids` or `values` have millions of entries. The alternative using this class would be:

Example
    
    
    MyModel = util.env(cr)['my.model']
    for record in util.iter_browse(MyModel, ids):
        record.field1 = val
    
    util.iter_browse(MyModel, ids)._compute_field2()
    util.iter_browse(MyModel, ids).create(values)
    

Parametri
    

  * **model** (`odoo.model.Model`) – the model to iterate

  * **ids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _)_) – list of IDs of the records to iterate

  * **chunk_size** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – number of records to load in each iteration chunk, `200` by default

  * **logger** ([`logging.Logger`](https://docs.python.org/3/library/logging.html#logging.Logger "\(in Python v3.13\)")) – logger used to report the progress, by default `_logger`

  * **strategy** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – whether to `flush` or `commit` on each chunk, default is `flush`



Ritorna
    

the object returned by this class can be used to iterate, or call any model method, safely on millions of records.

See also `env()`

create(_values_ , _** kw_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/orm.py#L428)¶
    

Create records.

An alternative to the default `create` method of the ORM that is safe to use to create millions of records.

Parametri
    

  * **values** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)") _)_) – list of values of the records to create

  * **multi** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to use the multi version of `create`, by default is `True` from Odoo 12 and above




odoo.upgrade.util.domains.adapt_domains(_cr_ , _model_ , _old_ , _new_ , _adapter =None_, _skip_inherit =()_, _force_adapt =False_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/domains.py#L405)¶
    

Replace `old` by `new` in domains using `model` and inheriting models.

`adapter` is a callback function to adapt leaves. Adapter functions must take three arguments and return a [domain](reference/orm/domains.html) that substitutes the original leaf. The arguments are:

  * `leaf`: a domain leaf which is a `tuple` of the form `(left, op, right)`

  * `in_or`: a boolean, when `True` it means the leaf is part of an OR (`"|"`) domain, otherwise it is part of an AND (`"&"`) domain

  * `negated`: a boolean, when `True` it means that the leaf is negated (`"!"`)




Example
    
    
    def adapter(leaf, in_or, negated):
        left, op, right = leaf
        ok, ko = (1, 2) if not negated else (2, 1)
        if op == "="
            return [(left, "=", ok)]
        elif op == "!=":
            return [(left, "=", ko)]
        return [leaf]
    

`adapter` is called only on leaves that use the `old` field of `model` as **last** part of the `left` part of leaves, unless `force_adapt` is `True`. In the latter case the adapter is called if the field appears anywhere in the path, useful for relational fields only.

The domains returned by an adapter do not need to have the `old` field replaced by `new` in the `left` part of the input leaf. The replace will be done anyway to the whole domain returned by the adapter. The usual purpose of the `adapter` is to modify the operator and the `right` part of the input leaf. When `adapter` is not set only the replacement takes place.

Example

When replacing `"field1"` by `"field2"`, the following happens:

  * `("foo.bar.baz.field1", "=", 1)` gets adapted _only_ if the record pointed to by `foo.bar.baz` is of the requested `model`.

  * `("foo.field1.baz", "=", 1)` is _not_ adapted _even_ if `foo` points to `model`, unless `force_adapt` is `True`, because `field1` is not the last part of `left` in this leaf.




Nota

This function will replace domains in all _standard_ domain fields. Including filters, dashboards, and standard fields known to represent a domain.

Parametri
    

  * **model** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the model for which to adapt the domains

  * **old** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the field to be adapted

  * **new** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the field that should replace `old`

  * **adapter** (_function_) – adapter for leaves

  * **skip_inherit** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of inheriting model names to don’t adapt (skip)

  * **force_adapt** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – when `True`, run the `adapter` on all leaves having `new` in `left` part of the leaf (path), useful when deleting a field (in which case `new` is ignored).




### SQL¶

Utility functions for interacting with PostgreSQL.

_class _odoo.upgrade.util.pg.PGRegexp[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L54)¶
    

Wrapper for semantic meaning of parameters: this string is a Postgres regular expression.

See `replace_in_all_jsonb_values()`

_class _odoo.upgrade.util.pg.SQLStr[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L62)¶
    

Wrapper for semantic meaning of parameters: this string is a valid SQL snippet.

See `format_query()`

odoo.upgrade.util.pg.parallel_execute(_cr_ , _queries_ , _logger= <Logger odoo.upgrade.util.pg (WARNING)>_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L155)¶
    

Execute queries in parallel.

Example
    
    
    util.parallel_execute(cr, [util.format_query(cr, "REINDEX TABLE {}", t) for t in tables])
    

Suggerimento

If looking to speedup a single query, see `explode_execute()`.

Parametri
    

  * **queries** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of queries to execute concurrently

  * **logger** ([_Logger_](https://docs.python.org/3/library/logging.html#logging.Logger "\(in Python v3.13\)")) – logger used to report the progress



Ritorna
    

the sum of `cr.rowcount` for each query run

Tipo di ritorno
    

[int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")

Avvertimento

  * Due to the nature of `cr.rowcount`, the return value of this function may represent an underestimate of the real number of affected records. For instance, when some records are deleted/updated as a result of an `ondelete` clause, they won’t be taken into account.

  * As a side effect, the cursor will be committed.




Nota

If a concurrency issue occurs, the _failing_ queries will be retried sequentially.

odoo.upgrade.util.pg.format_query(_cr_ , _query_ , _* args_, _** kwargs_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L191)¶
    

Safely format a query.

The `str` arguments to this function are assumed to be SQL identifiers. They are wrapped in double quotes before being expanded using [`str.format()`](https://docs.python.org/3/library/stdtypes.html#str.format "\(in Python v3.13\)"). Any other [psycopg2.sql.Composable](https://www.psycopg.org/docs/sql.html#psycopg2.sql.Composable) are also allowed. This includes `ColumnList`, see also `get_columns()`

Example
    
    
    >>> util.format_query(cr, "SELECT {0} FROM {table}", "id", table="res_users")
    SELECT "id" FROM "res_users"
    

Parametri
    

**query** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – query to format, can use brackets `{}` as in `str.format()`

odoo.upgrade.util.pg.explode_execute(_cr_ , _query_ , _table_ , _alias=None_ , _bucket_size=10000_ , _logger= <Logger odoo.upgrade.util.pg (WARNING)>_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L339)¶
    

Execute a query in parallel.

The query is split by buckets of ids, then processed in parallel by workers. If the query does not include the special `{parallel_filter}` value, it is added to the last `WHERE` clause, possibly also adding it if none found. When the query already has the filter nothing is done. The filter always expands to the splitting strategy. The split is done into buckets where no more than `bucket_size` IDs are updated on each individual query.

Example
    
    
    util.explode_execute(
        cr,
        '''
        UPDATE res_users u
           SET active = False
         WHERE (u.login LIKE 'dummy' OR u.login = 'bob')
           AND {parallel_filter}
        ''',
        table="res_users"
        alias="u",
    )
    

Parametri
    

  * **query** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – the query to execute.

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the _main_ table of the query, used to split the processing

  * **alias** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – alias used for the main table in the query

  * **bucket_size** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – size of the buckets of ids to split the processing

  * **logger** ([`logging.Logger`](https://docs.python.org/3/library/logging.html#logging.Logger "\(in Python v3.13\)")) – logger used to report the progress



Ritorna
    

the sum of `cr.rowcount` for each query run

Tipo di ritorno
    

[int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")

Avvertimento

It’s up to the caller to ensure the queries do not update the same records in different buckets. It is advised to never use this function for `DELETE` queries on tables with self references due to the potential `ON DELETE` effects. For more details see `parallel_execute()`.

odoo.upgrade.util.pg.column_exists(_cr_ , _table_ , _column_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L476)¶
    

Return whether a column exists.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table to check

  * **column** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – column to check



Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

odoo.upgrade.util.pg.column_type(_cr_ , _table_ , _column_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L487)¶
    

Return the type of a column, if it exists.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table to check

  * **column** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – column to check



Tipo di ritorno
    

SQL type of the column

odoo.upgrade.util.pg.create_column(_cr_ , _table_ , _column_ , _definition_ , _** kwargs_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L524)¶
    

Create a column.

This function will create the column only if it _doesn’t_ exist. It will log an error if the existing column has different type. If `fk_table` is set, it will ensure the foreign key is setup, updating if necessary, with the right `on_delete_action` if any is set.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table of the new column

  * **column** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the new column

  * **definition** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – column type of the new column

  * **default** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – default value to set on the new column

  * **fk_table** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – if the new column if a foreign key, name of the foreign table

  * **on_delete_action** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – `ON DELETE` clause, default `NO ACTION`, only valid if the column is a foreign key.



Ritorna
    

whether the column was created

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

odoo.upgrade.util.pg.alter_column_type(_cr_ , _table_ , _column_ , _type_ , _using=None_ , _where=None_ , _logger= <Logger odoo.upgrade.util.pg (WARNING)>_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L617)¶
    

Alter the type of a column.

Do it efficiently using a temporary column and parallel UPDATE queries.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the affected table.

  * **column** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the column to alter type.

  * **type** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new type of the column.

  * **using** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – SQL expression that define how to convert the value to the new type. The `{0}` placeholder will be replaced by the column name.

  * **where** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – used to restrict the values converted via `using`.

  * **logger** ([`logging.Logger`](https://docs.python.org/3/library/logging.html#logging.Logger "\(in Python v3.13\)")) – logger used to report the progress.




odoo.upgrade.util.pg.remove_constraint(_cr_ , _table_ , _name_ , _cascade =False_, _warn =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L719)¶
    

Remove a table constraint.

This function removes the constraint `name` from `table`. It also removes records from `ir_model_constraint` and its xml_ids. It logs not found constraints.

Nota

If there is no constraint `name`, this function will attempt to remove `{table}_{name}`, the latter is the default name the ORM uses for constraints created from `_sql_constraints`.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table from where to remove the constraint

  * **name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the constraint to remove

  * **cascade** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – cascade the constraint removal

  * **warn** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – use warning level when logging not found constraints, otherwise use info level



Ritorna
    

whether the constraint was removed

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

_class _odoo.upgrade.util.pg.ColumnList(_list_ =()_, _quoted =()_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L967)¶
    

Encapsulate a list of elements that represent column names.

The resulting object can be rendered as string with leading/trailing comma or an alias.

Parametri
    

  * **list** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of column names

  * **quoted** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of quoted column names, it must correspond with the `list_` parameter




Example
    
    
    >>> columns = ColumnList(["id", "field_Yx"], ["id", '"field_Yx"'])
    
    
    
    >>> list(columns)
    ['id', '"field_Yx"']
    
    
    
    >>> columns.using(alias="t").as_string(cr._cnx)
    '"t"."id", "t"."field_Yx"'
    
    
    
    >>> columns.using(leading_comma=True).as_string(cr._cnx)
    ', "id", "field_Yx"'
    
    
    
    >>> util.format_query(cr, "SELECT {} t.name FROM table t", columns.using(alias="t", trailing_comma=True))
    'SELECT "t"."id", "t"."field_Yx", t.name FROM table t'
    
    
    
    >>> columns = ColumnList.from_unquoted(cr, ["foo", "BAR"])
    
    
    
    >>> list(columns)
    ['"foo"', '"BAR"']
    
    
    
    >>> list(columns.iter_unquoted())
    ['foo', 'BAR']
    

Nota

This class is better used via `get_columns()`

_classmethod _from_unquoted(_cr_ , _list__)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1022)¶
    

Build a ColumnList from a list of column names that may need quoting.

Parametri
    

**list** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of unquoted column names

using(_leading_comma =KEEP_CURRENT_, _trailing_comma =KEEP_CURRENT_, _alias =KEEP_CURRENT_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1032)¶
    

Set up parameters to render this list as a string.

Parametri
    

  * **leading_comma** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to render a leading comma in front of this list

  * **trailing_comma** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether to render a trailing comma

  * **alias** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – alias of the table of the columns, no alias is added if set to `None`



Ritorna
    

a copy of the list with the parameters set

Tipo di ritorno
    

`ColumnList`

iter_unquoted()[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1071)¶
    

Iterate over the raw column names, non quoted.

This is useful if the quoting is done outside this object. Also to get access to raw column names as in Postgres catalog.

Ritorna
    

an iterator for the raw column names

odoo.upgrade.util.pg.get_columns(_cr_ , _table_ , _ignore =('id',)_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1083)¶
    

Return a list of columns in a table.

Parametri
    

  * **table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – table name whose columns are retrieved

  * **ignore** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of column names to ignore in the returning list



Ritorna
    

a list of column names present in the table

Tipo di ritorno
    

`ColumnList`

odoo.upgrade.util.pg.get_common_columns(_cr_ , _table1_ , _table2_ , _ignore =('id',)_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1108)¶
    

Return a list of columns present in both tables.

Parametri
    

  * **table1** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – first table name whose columns are retrieved

  * **table2** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – second table name whose columns are retrieved

  * **ignore** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)") _(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)_) – list of column names to ignore in the returning list



Ritorna
    

a list of column names present in both tables

Tipo di ritorno
    

`ColumnList`

odoo.upgrade.util.pg.rename_table(_cr_ , _old_table_ , _new_table_ , _remove_constraints =True_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/pg.py#L1141)¶
    

Rename a table.

This function renames the table `old_table` into `new_table`, as well as its primary key (and sequence), indexes, and foreign keys.

Parametri
    

  * **old_table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the table to rename

  * **new_table** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – new name of the table



Para bool remove_constraints
    

whether to remove the table constraints

### Misc¶

Miscellaneous standalone functions.

odoo.upgrade.util.misc.version_gte(_version_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/misc.py#L85)¶
    

Return whether currently running Odoo version is greater or equal to `version`.

This function is useful for conditional execution in an upgrade script that applies to multiple versions, e.g. `0.0.0` scripts.

Parametri
    

**version** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – Odoo version, must follow the format `[saas~]X.Y` where `X` is the major Odoo version, `saas~` is necessary only when `Y` is nonzero

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

odoo.upgrade.util.misc.version_between(_a_ , _b_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/misc.py#L101)¶
    

Return whether currently running Odoo version is in the range `[a,b]`.

See also `version_gte()`

Nota

The bounds are inclusive.

Parametri
    

  * **a** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – Odoo version, lower bound

  * **b** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – Odoo version, upper bound



Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

odoo.upgrade.util.misc.expand_braces(_s_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/misc.py#L164)¶
    

Expand braces in the input.

Example
    
    
    >>> util.expand_braces("a_{this,that}_b")
    ['a_this_b', 'a_that_b']
    

Parametri
    

**s** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – string to expand, must contain precisely one pair of braces.

Ritorna
    

expanded input

odoo.upgrade.util.misc.import_script(_path_ , _name =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/misc.py#L204)¶
    

Import an upgrade script.

This function allows to import functions from other upgrade scripts into the current one.

Example

In `mymodule/15.0.1.0/pre-migrate.py`
    
    
    def my_util(cr):
        # do stuff
    

In `myothermodule/16.0.1.0/post-migrate.py`
    
    
    from odoo.upgrade import util
    
    script = util.import_script("mymodule/15.0.1.0/pre-migrate.py")
    
    def migrate(cr, version):
        script.my_util(cr)  # reuse the function
    

This function returns a Python `module`.
    
    
    >>> util.import_script("base/0.0.0/end-moved0.py", name="my-moved0")
    <module 'my-moved0' from '/home/odoo/src/upgrade-util/src/base/0.0.0/end-moved0.py'>
    

Parametri
    

  * **path** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

relative path to the script to import in the form `$module/$version/$script-name`

Nota

The script must be available in the upgrade path.

  * **name** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _or_[ _None_](https://docs.python.org/3/library/constants.html#None "\(in Python v3.13\)")) – name to assign to the returned module, take the name from the imported file if `None`



Ritorna
    

a module created from the imported upgrade script

odoo.upgrade.util.misc.skippable_cm()[[sorgente]](https://github.com/usr/lib/python3.10/contextlib.py#L271)¶
    

Return a context manager to allow another context manager to not yield.

See `edit_view()` for an example usage.

odoo.upgrade.util.misc.chunks(_iterable_ , _size_ , _fmt =None_)[[sorgente]](https://github.com/odoo/upgrade-util/blob/master/src/util/misc.py#L297)¶
    

Split `iterable` into chunks of `size` and wrap each chunk using `fmt` function.

This function is useful for splitting huge input data into smaller chunks that can be processed independently.

Example
    
    
    >>> list(chunks(range(10), 4, fmt=tuple))
    [(0, 1, 2, 3), (4, 5, 6, 7), (8, 9)]
    >>> ' '.join(chunks('abcdefghijklm', 3))
    'abc def ghi jkl m'
    

Parametri
    

  * **iterable** (_iterable_) – iterable object to split

  * **size** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – chunk size

  * **fmt** (_function_) – function to apply to each chunk, when `None` is passed `fmt` becomes `"".join` if `iterable` is a string, otherwise `iter`



Ritorna
    

a generator that iterates over the result of `fmt` applied to each chunk

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/upgrades/upgrade_utils.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../external_api.html "External API") |
  * [precedente](upgrade_scripts.html "Upgrade scripts") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Upgrades](../upgrades.html) »
  * Upgrade utils


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left