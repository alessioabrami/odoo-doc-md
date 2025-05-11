# Account — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_fiscal_position.html "Fiscal Position") |
  * [precedente](account_account_tag.html "Account Tag") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Account



# Account¶

## Original definition from `account`¶

_model _odoo.addons.account.models.account_account.AccountAccount(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/account_account.py#L18)¶
    

_name _ = account.account_¶
    

name _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Account Name

currency_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Account Currency

Comodel
    

res.currency

Possible_values
    

[odoo/addons/base/data/res_currency_data.xml](https://github.com/odoo/odoo/blob/17.0/odoo/addons/base/data/res_currency_data.xml)

Forces all journal items in this account to have a specific currency (i.e. bank journals). If no currency is set, entries can use any currency.

code _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Code

account_type _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Type

Selection
    

`asset_receivable`: Receivable `asset_cash`: Bank and Cash `asset_current`: Current Assets `asset_non_current`: Non-current Assets `asset_prepayments`: Prepayments `asset_fixed`: Fixed Assets `liability_payable`: Payable `liability_credit_card`: Credit Card `liability_current`: Current Liabilities `liability_non_current`: Non-current Liabilities `equity`: Equity `equity_unaffected`: Current Year Earnings `income`: Income `income_other`: Other Income `expense`: Expenses `expense_depreciation`: Depreciation `expense_direct_cost`: Cost of Revenue `off_balance`: Off-Balance Sheet

Account Type is used for information purpose, to generate country-specific legal reports, and set the rules to close a fiscal year and generate opening entries.

reconcile _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Allow Reconciliation

Check this box if this account allows invoices & payments matching of journal items.

note _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Internal Notes

tax_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Default Taxes

Comodel
    

[account.tax](account_tax.html#model-account-tax)

tag_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Tags

Comodel
    

[account.account.tag](account_account_tag.html#model-account-account-tag)

Optional tags you may want to assign for custom reporting

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_account.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_fiscal_position.html "Fiscal Position") |
  * [precedente](account_account_tag.html "Account Tag") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Account


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases