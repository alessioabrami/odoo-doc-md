# Tax Repartitions — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment.html "Payment") |
  * [precedente](account_tax.html "Taxes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Tax Repartitions



# Tax Repartitions¶

## Original definition from `account`¶

_model _odoo.addons.account.models.account_tax.AccountTaxRepartitionLine(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/account_tax.py#L1707)¶
    

_name _ = account.tax.repartition.line_¶
    

factor_percent _: [float](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")_¶
    

Required
    

Name
    

%

Default
    

100

Factor to apply on the account move lines generated from this distribution line, in percents

repartition_type _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Based On

Selection
    

`base`: Base `tax`: of tax

Default
    

tax

Base on which the factor will be applied.

document_type _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Related to

Selection
    

`invoice`: Invoice `refund`: Refund

account_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Account

Comodel
    

[account.account](account_account.html#model-account-account)

Account on which to post the tax amount

tax_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Tax

Comodel
    

[account.tax](account_tax.html#model-account-tax)

tag_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Tax Grids

Comodel
    

[account.account.tag](account_account_tag.html#model-account-account-tag)

use_in_tax_closing _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Tax Closing Entry

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_tax_repartition.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment.html "Payment") |
  * [precedente](account_tax.html "Taxes") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Tax Repartitions


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases