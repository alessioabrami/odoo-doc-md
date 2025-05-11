# Report — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_report_line.html "Report Line") |
  * [precedente](account_group.html "Account Group") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Report



# Report¶

## Original definition from `account`¶

_model _odoo.addons.account.models.account_report.AccountReport(_env_ , _ids_ , _prefetch_ids_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/account/models/account_report.py#L24)¶
    

_name _ = account.report_¶
    

name _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Required
    

Name
    

Name

line_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Lines

Comodel
    

[account.report.line](account_report_line.html#model-account-report-line)

column_ids _: Sequence[[odoo.fields.Command](../../backend/orm.html#odoo.fields.Command "odoo.fields.Command")]_¶
    

Name
    

Columns

Comodel
    

account.report.column

root_report_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Root Report

Comodel
    

account.report

The report this report is a variant of.

country_id _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Country

Comodel
    

res.country

Possible_values
    

[odoo/addons/base/data/res_country_data.xml](https://github.com/odoo/odoo/blob/17.0/odoo/addons/base/data/res_country_data.xml)

only_tax_exigible _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Only Tax Exigible Lines

availability_condition _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Availability

Selection
    

`country`: Country Matches `coa`: Chart of Accounts Matches `always`: Always

load_more_limit _: [int](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")_¶
    

Name
    

Load More Limit

search_bar _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Search Bar

default_opening_date_filter _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Default Opening

Selection
    

`this_year`: This Year `this_quarter`: This Quarter `this_month`: This Month `today`: Today `last_month`: Last Month `last_quarter`: Last Quarter `last_year`: Last Year `this_tax_period`: This Tax Period `last_tax_period`: Last Tax Period

filter_multi_company _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Multi-Company

Selection
    

`disabled`: Disabled `selector`: Use Company Selector `tax_units`: Use Tax Units

filter_date_range _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Date Range

filter_show_draft _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Draft Entries

filter_unreconciled _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Unreconciled Entries

filter_unfold_all _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Unfold All

filter_period_comparison _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Period Comparison

filter_growth_comparison _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Growth Comparison

filter_journals _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Journals

filter_analytic _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Analytic Filter

filter_hierarchy _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Account Groups

Selection
    

`by_default`: Enabled by Default `optional`: Optional `never`: Never

filter_account_type _: [str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")_¶
    

Name
    

Account Types

Selection
    

`both`: Payable and receivable `payable`: Payable `receivable`: Receivable `disabled`: Disabled

filter_partner _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Partners

filter_fiscal_position _: [bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")_¶
    

Name
    

Filter Multivat

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/account/account_report.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](account_report_line.html "Report Line") |
  * [precedente](account_group.html "Account Group") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Accounting](../account.html) »
  * Report


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases