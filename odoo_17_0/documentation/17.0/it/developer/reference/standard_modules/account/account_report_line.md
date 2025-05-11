# Report Line — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_tax.html "Taxes") |
  * [precedente](account_report.html "Report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Report Line



# Report Line¶

## Original definition from `account`¶

_model _odoo.addons.account.models.account_report.AccountReportLine(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/account_report.py#L288)¶
    

_name _ = account.report.line_¶
    

name _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Name

expression_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Expressions

Comodel
    

account.report.expression

report_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Parent Report

Comodel
    

[account.report](account_report.html#model-account-report)

hierarchy_level _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Level

parent_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Parent Line

Comodel
    

account.report.line

children_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Child Lines

Comodel
    

account.report.line

foldable _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Foldable

By default, we always unfold the lines that can be. If this is checked, the line won’t be unfolded by default, and a folding button will be displayed.

print_on_new_page _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Print On New Page

When checked this line and everything after it will be printed on a new page.

action_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Action

Comodel
    

ir.actions.actions

Setting this field will turn the line into a link, executing the action when clicked.

hide_if_zero _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Hide if Zero

This line and its children will be hidden when all of their columns are 0.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_report_line.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_tax.html "Taxes") |
  * [precedente](account_report.html "Report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Report Line


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases