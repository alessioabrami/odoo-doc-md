# Fiscal Position — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_group.html "Account Group") |
  * [precedente](account_account.html "Account") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Fiscal Position



# Fiscal Position¶

## Original definition from `account`¶

_model _odoo.addons.account.models.partner.AccountFiscalPosition(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/partner.py#L18)¶
    

_name _ = account.fiscal.position_¶
    

sequence _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Sequence

name _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Fiscal Position

account_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Account Mapping

Comodel
    

account.fiscal.position.account

tax_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Tax Mapping

Comodel
    

account.fiscal.position.tax

note _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Notes

Legal mentions that have to be printed on the invoices.

auto_apply _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Detect Automatically

Apply tax & account mappings on invoices automatically if the matching criterias (VAT/Country) are met.

vat_required _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

VAT required

Apply only if partner has a VAT number.

country_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Country

Comodel
    

res.country

Possible_values
    

[odoo/addons/base/data/res_country_data.xml](https://github.com/odoo/odoo/blob/17.0/odoo/addons/base/data/res_country_data.xml)

Apply only if delivery country matches.

country_group_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Country Group

Comodel
    

res.country.group

Apply only if delivery country matches the group.

state_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Federal States

Comodel
    

res.country.state

zip_from _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Zip Range From

zip_to _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Zip Range To

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_fiscal_position.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_group.html "Account Group") |
  * [precedente](account_account.html "Account") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Fiscal Position


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases