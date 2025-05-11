# Upgrade scripts — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](upgrade_utils.html "Upgrade utils") |
  * [precedente](../upgrades.html "Upgrades") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Upgrades](../upgrades.html) »
  * Upgrade scripts



# Upgrade scripts¶

An upgrade script is a Python file containing a function called `migrate()`, which the upgrade process invokes during the update of a module.

migrate(_cr_ , _version_)¶
    

Parametri
    

  * **cr** (`Cursor`) – current database cursor

  * **version** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – installed version of the module




Typically, this function executes one or multiple SQL queries and can also access Odoo’s ORM, as well as the [Upgrade utils](upgrade_utils.html).

## Writing upgrade scripts¶

Upgrade scripts follow a specific tree structure with a naming convention which determines when they are executed.

The structure of an upgrade script path is `$module/migrations/$version/_pre,post,end_ -*.py`, where `$module` is the module for which the script will run, `$version` is the full version of the module (including Odoo’s major version and the module’s minor version) and `{pre|post|end}-*.py` is the file that needs to be executed. The file’s name will determine the phase and order in which it is executed for that module and version.

Nota

From Odoo 13 the top-level directory for the upgrade scripts can also be named `upgrades`. This naming is preferred since it has the correct meaning: _migrate_ can be confused with _moving out of Odoo_. Thus `$module/upgrades/$version/` is also valid.

Nota

Upgrade scripts are only executed when the module is being updated. Therefore, the module’s minor version set in the `$version` directory needs to be higher than the module’s installed version and equal or lower to the updated version of the module.

Example

Directory structure of an upgrade script for a custom module named `awesome_partner` upgraded to version `2.0` on Odoo 17.
    
    
    awesome_partner/
    |-- migrations/
    |   |-- 17.0.2.0/
    |   |   |-- pre-exclamation.py
    

Two upgrade scripts examples with the content of the `pre-exclamation.py`, file adding «!» at the end of partners” names:
    
    
    import logging
    
    _logger = logging.getLogger(__name__)
    
    
    def migrate(cr, version):
        cr.execute("UPDATE res_partner SET name = name || '!'")
        _logger.info("Updated %s partners", cr.rowcount)
    
    
    
    import logging
    from odoo.upgrade import util
    
    _logger = logging.getLogger(__name__)
    
    
    def migrate(cr, version):
        env = util.env(cr)
    
        partners = env["res.partner"].search([])
        for partner in partners:
            partner.name += "!"
    
        _logger.info("Updated %s partners", len(partners))
    

Note that in the second example, the script takes advantage of the [Upgrade utils](upgrade_utils.html) to access the ORM. Check the documentation to find out more about this library.

## Phases of upgrade scripts¶

The upgrade process consists of three phases for each version of each module:

>   1. The pre-phase, before the module is loaded.
> 
>   2. The post-phase, after the module and its dependencies are loaded and updated.
> 
>   3. The end-phase, after all modules have been loaded and updated for that version.
> 
> 


Upgrade scripts are grouped according to the first part of their filenames into the corresponding phase. Within each phase, the files are executed according to their lexical order.

Execution order of example scripts for one module in one version

  1. `pre-10-do_something.py`

  2. `pre-20-something_else.py`

  3. `post-do_something.py`

  4. `post-something.py`

  5. `end-01-migrate.py`

  6. `end-migrate.py`




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/upgrades/upgrade_scripts.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](upgrade_utils.html "Upgrade utils") |
  * [precedente](../upgrades.html "Upgrades") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Upgrades](../upgrades.html) »
  * Upgrade scripts


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left