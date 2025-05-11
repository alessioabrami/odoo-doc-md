# Taxes — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_tax_repartition.html "Tax Repartitions") |
  * [precedente](account_report_line.html "Report Line") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Taxes



# Taxes¶

## Original definition from `account`¶

_model _odoo.addons.account.models.account_tax.AccountTax(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/account_tax.py#L84)¶
    

_name _ = account.tax_¶
    

name _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Tax Name

type_tax_use _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Tax Type

Selection
    

`sale`: Sales `purchase`: Purchases `none`: None

Default
    

sale

Determines where the tax is selectable. Note: “None” means a tax can’t be used by itself, however it can still be used in a group. “adjustment” is used to perform tax adjustment.

tax_scope _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Tax Scope

Selection
    

`service`: Services `consu`: Goods

Restrict the use of taxes to a type of product.

amount_type _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Tax Computation

Selection
    

`group`: Group of Taxes `fixed`: Fixed `percent`: Percentage of Price `division`: Percentage of Price Tax Included

Default
    

percent

  * Group of Taxes: The tax is a set of sub taxes.
    
    * Fixed: The tax amount stays the same whatever the price.

    * Percentage of Price: The tax amount is a % of the price:
    

e.g 100 * (1 + 10%) = 110 (not price included) e.g 110 / (1 + 10%) = 100 (price included)

    * Percentage of Price Tax Included: The tax amount is a division of the price:
    

e.g 180 / (1 - 10%) = 200 (not price included) e.g 200 * (1 - 10%) = 180 (price included)




active _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Active

Default
    

True

Set active to false to hide the tax without removing it.

children_tax_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Children Taxes

Comodel
    

account.tax

sequence _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Sequence

Default
    

1

The sequence field is used to define order in which the tax lines are applied.

amount _: [float](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Amount

Default
    

0.0

description _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Description

price_include _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Included in Price

Default
    

False

Check this if the price you use on the product and invoices includes this tax.

include_base_amount _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Affect Base of Subsequent Taxes

Default
    

False

If set, taxes with a higher sequence than this one will be affected by it, provided they accept it.

is_base_affected _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Base Affected by Previous Taxes

Default
    

True

If set, taxes with a lower sequence might affect this one, provided they try to do it.

analytic _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Include in Analytic Cost

If set, the amount computed by this tax will be assigned to the same analytic account as the invoice line (if any)

invoice_repartition_line_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Distribution for Invoices

Comodel
    

[account.tax.repartition.line](account_tax_repartition.html#model-account-tax-repartition-line)

Distribution when the tax is used on an invoice

refund_repartition_line_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Distribution for Refund Invoices

Comodel
    

[account.tax.repartition.line](account_tax_repartition.html#model-account-tax-repartition-line)

Distribution when the tax is used on a refund

tax_group_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Tax Group

Comodel
    

account.tax.group

tax_exigibility _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Tax Exigibility

Selection
    

`on_invoice`: Based on Invoice `on_payment`: Based on Payment

Default
    

on_invoice

Based on Invoice: the tax is due as soon as the invoice is validated. Based on Payment: the tax is due as soon as the payment of the invoice is received.

cash_basis_transition_account_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Cash Basis Transition Account

Comodel
    

[account.account](account_account.html#model-account-account)

Account used to transition the tax amount for cash basis taxes. It will contain the tax amount as long as the original invoice has not been reconciled ; at reconciliation, this amount cancelled on this account and put on the regular tax account.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_tax.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_tax_repartition.html "Tax Repartitions") |
  * [precedente](account_report_line.html "Report Line") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Taxes


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases