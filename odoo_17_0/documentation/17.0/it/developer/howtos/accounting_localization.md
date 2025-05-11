# Accounting localization — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](translations.html "Translating Modules") |
  * [precedente](create_reports.html "Create customized reports") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Accounting localization



# Accounting localization¶

Avvertimento

This tutorial requires knowledge about how to build a module in Odoo (see [Server framework 101](../tutorials/server_framework_101.html)).

## Installation procedure¶

On installing the [account](https://github.com/odoo/odoo/blob/17.0/addons/account) module, the localization module corresponding to the country code of the company is installed automatically. In case of no country code set or no localization module found, the [l10n_generic_coa](https://github.com/odoo/odoo/blob/17.0/addons/l10n_generic_coa) (US) localization module is installed by default. Check [post init hook](https://github.com/odoo/odoo/blob/17.0/addons/account/__init__.py) for details.

For example, [l10n_ch](https://github.com/odoo/odoo/blob/17.0/addons/l10n_ch) will be installed if the company has `Switzerland` as country.

## Building a localization module¶

The structure of a basic `l10n_XX` module may be described with the following `__manifest__.py` file:
    
    
    {
        "name": "COUNTRY - Accounting",
        "version": "1.0.0",
        "category": "Accounting/Localizations/Account Charts",
        "license": "LGPL-3",
        "depends": [
            "account",
        ],
        "data": [
            "data/other_data.xml",
            "views/xxxmodel_views.xml",
        ],
        "demo": [
            "demo/demo_company.xml",
        ]
    }
    

Your worktree should look like this
    
    
    l10n_xx
    ├── data
    │   ├── template
    │   │   ├── account.account-xx.csv
    │   │   ├── account.group-xx.csv
    │   │   └── account.tax.group-xx.csv
    │   └── other_data.xml
    ├── views
    │   └── xxxmodel_views.xml
    ├── demo
    │   └── demo_company.xml
    ├── models
    │   ├── template_xx.py
    │   └── __init__.py
    ├── __init__.py
    └── __manifest__.py
    

In the first file `models/template_xx.py`, we set the name for the chart of accounts along with some basic fields.

Vedi anche

[Chart Template References](../reference/standard_modules/account.html)

Example

[addons/l10n_be/models/template_be.py](https://github.com/odoo/odoo/blob/17.0/addons/l10n_be/models/template_be.py)
    
    
        def _get_be_template_data(self):
            return {
                'name': _('Base'),
                'visible': False,
                'code_digits': '6',
                'property_account_receivable_id': 'a400',
                'property_account_payable_id': 'a440',
                'property_account_expense_categ_id': 'a600',
                'property_account_income_categ_id': 'a7000',
            }
    
        @template('be', 'res.company')
        def _get_be_res_company(self):
            return {
                self.env.company.id: {
                    'account_fiscal_country_id': 'base.be',
                    'bank_account_code_prefix': '550',
                    'cash_account_code_prefix': '570',
                    'transfer_account_code_prefix': '580',
                    'account_default_pos_receivable_account_id': 'a4001',
                    'income_currency_exchange_account_id': 'a754',
                    'expense_currency_exchange_account_id': 'a654',
                    'account_journal_suspense_account_id': 'a499',
                    'account_journal_early_pay_discount_loss_account_id': 'a657000',
                    'account_journal_early_pay_discount_gain_account_id': 'a757000',
                    'account_sale_tax_id': 'attn_VAT-OUT-21-L',
                    'account_purchase_tax_id': 'attn_VAT-IN-V81-21',
                    'default_cash_difference_income_account_id': 'a757100',
                    'default_cash_difference_expense_account_id': 'a657100',
                    'transfer_account_id': 'a58',
                },
            }
    
        @template('be', 'account.journal')
        def _get_be_account_journal(self):
            return {
                'sale': {'refund_sequence': True},
                'purchase': {'refund_sequence': True},
            }
    
        @template('be', 'account.reconcile.model')
    

## Chart of Accounts¶

### Account tags¶

Vedi anche

[Account Tag References](../reference/standard_modules/account/account_account_tag.html#reference-account-account-tag)

Tags are a way to sort accounts. For example, imagine you want to create a financial report having multiple lines but you have no way to find a rule to dispatch the accounts according to their `code`. The solution is the usage of tags, one for each report line, to filter accounts like you want.

Put the tags in the `data/account_account_tag_data.xml` file.

Example

[addons/l10n_lt/data/template/account.account-lt.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_lt/data/template/account.account-lt.csv)
    
    
    "id","name","code","account_type","tag_ids","reconcile","name@lt"
    "account_account_template_1130","Software Acquisition Cost","1130","asset_non_current","l10n_lt.account_account_tag_a_1_3","False","Programinės įrangos įsigijimo savikaina"
    "account_account_template_1138","Amortization of Software Value (-)","1138","asset_non_current","l10n_lt.account_account_tag_a_1_3","False","Programinės įrangos vertės amortizacija (−)"
    "account_account_template_1200","Land Acquisition Cost","1200","asset_fixed","l10n_lt.account_account_tag_a_2_1","False","Žemės įsigijimo savikaina"
    "account_account_template_1201","Change of Land Value after Revaluation","1201","asset_fixed","l10n_lt.account_account_tag_a_2_1","False","Žemės vertės pokytis dėl perkainojimo"
    

### Accounts¶

Vedi anche

  * [Account References](../reference/standard_modules/account/account_account.html#reference-account-account)

  * [Piano dei conti](../../applications/finance/accounting/get_started/chart_of_accounts.html)




Obviously, Chart of Accounts cannot exist without Accounts. You need to specify them in `data/account.account.template.csv`.

Example

[addons/l10n_ch/data/template/account.account-ch.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_ch/data/template/account.account-ch.csv)
    
    
    "id","name","code","account_type","reconcile","name@de","name@it","name@fr","name@ar","name@zh_CN","name@nl"
    "ch_coa_1060","Securities (with stock exchange price)","1060","asset_current","False","Wertpapiere (mit Börsenkurs)","Titoli","Titres","","",""
    "ch_coa_1069","Accumulated depreciation on securities","1069","asset_current","False","Kumulierte Abschreibungen auf Wertpapiere","Rettifica valore titoli","Ajustement de la valeur des titres","","",""
    "ch_coa_1090","Salary-Pass-Through Account","1090","asset_current","True","Gehaltsdurchlaufkonto","Conto di trasferimento dello stipendio","Compte de transfert de salaire","","",""
    "ch_coa_1091","Transfer account: Salaries","1091","asset_current","True","Transferkonto: Gehälter","Conto d'attesa - Salari","Compte d'attente pour salaires","","",""
    "ch_coa_1099","Transfer account: miscellaneous","1099","asset_current","True","Transferkonto: Verschiedenes","Conto d'attesa - altro","Compte d'attente autre","","",""
    "ch_coa_1100","Accounts receivable from goods and services (Debtors)","1100","asset_receivable","True","Forderungen aus Lieferungen und Leistungen (Debitoren)","Crediti da forniture e prestazioni (debitori)","Débiteurs","","",""
    "ch_coa_1101","Receivable (PoS)","1101","asset_receivable","True","Forderungen (PoS)","Crediti (Punti Vendita)","Débiteurs (PoS)","","",""
    "ch_coa_1109","Del credere (Acc. depr. on debtors)","1109","asset_current","False","Delkredere (Akontoabzug für Schuldner)","Delcredere","Ducroire","","",""
    "ch_coa_1140","Advances and loans","1140","asset_current","False","Vorschüsse und Darlehen","Anticipi e prestiti","Avances et prêts","","",""
    "ch_coa_1149","Advances and loans adjustments","1149","asset_current","False","Anpassungen von Vorschüssen und Darlehen","Rettifica valore anticipi e prestiti","Ajustement de la valeur des avances et des prêts","","",""
    "ch_coa_1170","Input Tax (VAT) receivable on material, goods, services, energy","1170","asset_current","False","Vorsteuer (MwSt.) auf Material, Waren, Dienstleistungen, Energie","IVA, Imposta precedente su materiale, merce, servizi e energia","Impôt préalable: TVA s/matériel, marchandises, prestations et énergie","","",""
    "ch_coa_1171","Input Tax (VAT) receivable on investments, other operating expenses","1171","asset_current","False","Vorsteuer (MwSt.) auf Investitionen, sonstige betriebliche Aufwendungen","IVA, imposta precedente su investimenti e altri costi d’esercizio","Impôt préalable: TVA s/investissements et autres charges d’exploitation","","",""
    

Avvertimento

  * Avoid the usage of `asset_cash` `account_type`! Indeed, the bank & cash accounts are created directly at the installation of the localization module and then, are linked to an `account.journal`.

  * Only one account of type payable/receivable is enough for the generic case. We need to define a PoS receivable account as well however. (linked in the CoA)

  * Don’t create too many accounts: 200-300 is enough. But mostly, we try to find a good balance where the CoA needs minimal adapting for most companies afterwards.




### Account groups¶

Vedi anche

[Account Group References](../reference/standard_modules/account/account_group.html#reference-account-group)

Account groups allow describing the hierarchical structure of the chart of accounts. The filter needs to be activated in the report and then when you decollapse into journal entries it will show the parents of the account.

It works with the prefix _start_ /_end_ , so every account where the code starts with something between _start_ and _end_ will have this `account.group` as the parent group. Furthermore, the account groups can have a parent account group as well to form the hierarchy.

Example

[addons/l10n_il/data/template/account.group-il.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_il/data/template/account.group-il.csv)

id | code_prefix_start | code_prefix_end | name | [name@he_IL](mailto:name%40he_IL)  
---|---|---|---|---  
il_group_100100 | 100100 | 100499 | Fixed Assets | רכוש קבוע  
il_group_101110 | 101110 | 101400 | Current Assets | רכוש שוטף  
il_group_101401 | 101401 | 101799 | Bank And Cash | בנק ומזומנים  
il_group_111000 | 111000 | 111999 | Current Liabilities | התחייבויות שוטפות  
il_group_112000 | 112000 | 112210 | Non-current Liabilities | התחייבויות לא שוטפות  
il_group_200000 | 200000 | 200199 | Sales Income | הכנסות ממכירות  
il_group_200200 | 200200 | 200300 | Other Income | הכנסות אחרות  
il_group_201000 | 201000 | 201299 | Cost of Goods | עלות המכר  
il_group_202000 | 202000 | 220900 | Expenses | הוצאות  
il_group_300000 | 300000 | 399999 | Capital And Shares | הון ומניות  
  
### Taxes¶

Vedi anche

  * [Tax References](../reference/standard_modules/account/account_tax.html#reference-account-tax)

  * [Imposte](../../applications/finance/accounting/taxes.html)




To add taxes you first need to specify tax groups. You normally need just one tax group for every tax rate, except for the 0% as you need to often distinguish between exempt, 0%, not subject, … taxes. This model only has two required fields: `name` and `country`. Create the file `data/template/account.tax.group-xx.csv` and list the groups.

Example

[addons/l10n_uk/data/template/account.tax.group-uk.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_uk/data/template/account.tax.group-uk.csv)
    
    
    "id","name","country_id","tax_payable_account_id","tax_receivable_account_id"
    "tax_group_0","TAX 0%","base.uk","2202","2202"
    "tax_group_5","TAX 5%","base.uk","2202","2202"
    "tax_group_175","TAX 17.5%","base.uk","2202","2202"
    "tax_group_20","TAX 20%","base.uk","2202","2202"
    

Now you can add the taxes via `data/template/account.tax-xx.csv` file. The first tax you define that is purchase/sale also becomes the default purchase/sale tax for your products.

Example

[addons/l10n_ae/data/template/account.tax-ae.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_ae/data/template/account.tax-ae.csv)
    
    
    "id","name","type_tax_use","amount","amount_type","description","invoice_label","tax_group_id","repartition_line_ids/repartition_type","repartition_line_ids/document_type","repartition_line_ids/tag_ids","repartition_line_ids/account_id","repartition_line_ids/factor_percent"
    "uae_sale_tax_5_dubai","5% DB","sale","5.0","percent","Vat 5% Dubai","VAT 5%","ae_tax_group_5","base","invoice","+b. Dubai (Base)","",""
    "","","","","","","","","tax","invoice","+b. Dubai (Tax)","uae_account_201017",""
    "","","","","","","","","base","refund","-b. Dubai (Base)","",""
    "","","","","","","","","tax","refund","-b. Dubai (Tax)","uae_account_201017",""
    "uae_sale_tax_5_abu_dhabi","5% AD","sale","5.0","percent","VAT 5% Abu Dhabi","VAT 5%","ae_tax_group_5","base","invoice","+a. Abu Dhabi (Base)","",""
    "","","","","","","","","tax","invoice","+a. Abu Dhabi (Tax)","uae_account_201017",""
    "","","","","","","","","base","refund","-a. Abu Dhabi (Base)","",""
    "","","","","","","","","tax","refund","-a. Abu Dhabi (Tax)","uae_account_201017",""
    "uae_sale_tax_5_sharjah","5% S","sale","5.0","percent","VAT 5% Sharjah","VAT 5%","ae_tax_group_5","base","invoice","+c. Sharjah (Base)","",""
    "","","","","","","","","tax","invoice","+c. Sharjah (Tax)","uae_account_201017",""
    "","","","","","","","","base","refund","-c. Sharjah (Base)","",""
    "","","","","","","","","tax","refund","-c. Sharjah (Tax)","uae_account_201017",""
    "uae_sale_tax_5_ajman","5% A","sale","5.0","percent","VAT 5% Ajman","VAT 5%","ae_tax_group_5","base","invoice","+d. Ajman (Base)","",""
    "","","","","","","","","tax","invoice","+d. Ajman (Tax)","uae_account_201017",""
    "","","","","","","","","base","refund","-d. Ajman (Base)","",""
    "","","","","","","","","tax","refund","-d. Ajman (Tax)","uae_account_201017",""
    "uae_sale_tax_5_umm_al_quwain","5% UAQ","sale","5.0","percent","VAT 5% Umm Al Quwain","VAT 5%","ae_tax_group_5","base","invoice","+e. Umm Al Quwain (Base)","",""
    "","","","","","","","","tax","invoice","+e. Umm Al Quwain (Tax)","uae_account_201017",""
    "","","","","","","","","base","refund","-e. Umm Al Quwain (Base)","",""
    "","","","","","","","","tax","refund","-e. Umm Al Quwain (Tax)","uae_account_201017",""
    "uae_sale_tax_5_ras_al_khaima","5% RAK","sale","5.0","percent","VAT 5% Ras Al-Khaima","VAT 5%","ae_tax_group_5","base","invoice","+f. Ras Al-Khaima (Base)","",""
    

### Tax Report¶

Enterprise feature

The tax report is declared in the Invoicing (`account`) app, but the report is only accessible when Accounting (`account_accountant`) is installed.

Vedi anche

  * [Report Line](../reference/standard_modules/account/account_report_line.html)

  * [Tax return (VAT declaration)](../../applications/finance/accounting/reporting/tax_returns.html)




In the previous section, you noticed the fields `invoice_repartition_line_ids` or `refund_repartition_line_ids` and probably understood nothing about them. Good news: you are not alone on this incomprehension. Bad news: you have to figure it out a bit. The topic is complicated. Indeed:

The simple version is that, in the tax template, you indicate in the invoice/refund repartition lines whether the base or a percentage of the tax needs to be reported in which report line (through the _minus/plus_report_line_ids_ fields). It becomes clear also when you check the tax configuration in the Odoo interface (or check the docs [Tax References](../reference/standard_modules/account/account_tax.html#reference-account-tax), [Tax Repartition References](../reference/standard_modules/account/account_tax_repartition.html#reference-account-tax-repartition)).

So, once you have properly configured taxes, you just need to add the `data/account_tax_report_data.xml` file with a record for your `account.report`. For it to be considered as a tax report, you need to provide it with the right `root_report_id`.
    
    
    <odoo>
        <record id="tax_report" model="account.report">
            <field name="name">Tax Report</field>
            <field name="root_report_id" ref="account.generic_tax_report"/>
            <field name="country_id" ref="base.XX"/>
        </record>
    
        ...
    </odoo>
    

… followed by the declaration of its lines, as `account.report.line` records.

Example

[addons/l10n_au/data/account_tax_report_data.xml](https://github.com/odoo/odoo/blob/17.0/addons/l10n_au/data/account_tax_report_data.xml)
    
    
        <record id="tax_report" model="account.report">
            <field name="name">BAS Report</field>
            <field name="root_report_id" ref="account.generic_tax_report"/>
            <field name="country_id" ref="base.au"/>
            <field name="filter_fiscal_position" eval="True"/>
            <field name="availability_condition">country</field>
            <field name="column_ids">
                <record id="tax_report_balance" model="account.report.column">
                    <field name="name">Balance</field>
                    <field name="expression_label">balance</field>
                </record>
            </field>
            <field name="line_ids">
                <record id="account_tax_report_gstrpt_sale_total" model="account.report.line">
                    <field name="name">GST amounts you owe the Tax Office from sales</field>
                    <field name="hierarchy_level">0</field>
                    <field name="children_ids">
                        <record id="account_tax_report_gstrpt_g1" model="account.report.line">
                            <field name="name">G1: Total Sales (including any GST)</field>
                            <field name="code">G1</field>
                            <field name="expression_ids">
                                <record id="account_tax_report_gstrpt_g1_tag" model="account.report.expression">
                                    <field name="label">balance</field>
                                    <field name="engine">tax_tags</field>
                                    <field name="formula">G1</field>
                                </record>
                            </field>
                            <field name="children_ids">
                                <record id="account_tax_report_gstrpt_g2" model="account.report.line">
                                    <field name="name">G2: Export sales</field>
                                    <field name="code">G2</field>
                                    <field name="expression_ids">
                                        <record id="account_tax_report_gstrpt_g2_tag" model="account.report.expression">
                                            <field name="label">balance</field>
                                            <field name="engine">tax_tags</field>
                                            <field name="formula">G2</field>
                                        </record>
                                    </field>
                                </record>
    

### Fiscal positions¶

Vedi anche

  * [Fiscal Position References](../reference/standard_modules/account/account_fiscal_position.html#reference-account-fiscal-position)

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../../applications/finance/accounting/taxes/fiscal_positions.html)




Specify fiscal positions in the `data/template/account.fiscal.position-xx.csv` file.

Example

[addons/l10n_es/data/template/account.fiscal.position-es_common.csv](https://github.com/odoo/odoo/blob/17.0/addons/l10n_es/data/template/account.fiscal.position-es_common.csv)
    
    
    "id","sequence","name","name@es","name@ca","auto_apply","vat_required","country_id","country_group_id","tax_ids/tax_src_id","tax_ids/tax_dest_id","account_ids/account_src_id","account_ids/account_dest_id"
    "fp_nacional","1","Domestic","Régimen Nacional","Règim nacional","1","1","base.es","","","","",""
    "fp_intra_private","2","EU private","EU privado","EU privat","1","","","base.europe","","","",""
    "fp_intra","3","Intra-community","Régimen Intracomunitario","Règim intracomunitari","1","1","","base.europe","account_tax_template_p_iva0_s_bc","account_tax_template_p_iva0_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva0_s_sc","account_tax_template_p_iva0_ic_sc","",""
    "","","","","","","","","","account_tax_template_p_iva2_bc","account_tax_template_p_iva2_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva2_sc","account_tax_template_p_iva2_ic_sc","",""
    "","","","","","","","","","account_tax_template_p_iva4_bc","account_tax_template_p_iva4_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva4_sc","account_tax_template_p_iva4_sp_in","",""
    "","","","","","","","","","account_tax_template_p_iva4_bi","account_tax_template_p_iva4_ic_bi","",""
    "","","","","","","","","","account_tax_template_p_iva5_bc","account_tax_template_p_iva5_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva5_sc","account_tax_template_p_iva5_ic_sc","",""
    "","","","","","","","","","account_tax_template_p_iva7-5_bc","account_tax_template_p_iva7-5_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva7-5_sc","account_tax_template_p_iva7-5_ic_sc","",""
    "","","","","","","","","","account_tax_template_p_iva10_bc","account_tax_template_p_iva10_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva10_sc","account_tax_template_p_iva10_sp_in","",""
    "","","","","","","","","","account_tax_template_p_iva10_bi","account_tax_template_p_iva10_ic_bi","",""
    "","","","","","","","","","account_tax_template_p_iva21_bc","account_tax_template_p_iva21_ic_bc","",""
    "","","","","","","","","","account_tax_template_p_iva21_sc","account_tax_template_p_iva21_sp_in","",""
    "","","","","","","","","","account_tax_template_p_iva21_bi","account_tax_template_p_iva21_ic_bi","",""
    "","","","","","","","","","account_tax_template_s_iva0b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva0s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva2b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva2s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva4b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva4s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva5b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva5s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva7-5b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva7-5s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva10b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva10s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","account_tax_template_s_iva21b","account_tax_template_s_iva0_g_i","",""
    "","","","","","","","","","account_tax_template_s_iva21s","account_tax_template_s_iva0_sp_i","",""
    "","","","","","","","","","","","account_common_7000","account_common_7001"
    "","","","","","","","","","","","account_common_7010","account_common_7011"
    "","","","","","","","","","","","account_common_7020","account_common_7021"
    "","","","","","","","","","","","account_common_7030","account_common_7031"
    "","","","","","","","","","","","account_common_7040","account_common_7041"
    "","","","","","","","","","","","account_common_7050","account_common_7051"
    "fp_extra","4","Extra-community","Régimen Extracomunitario","Règim extracomunitari","1","","","","account_tax_template_p_iva0_s_bc","account_tax_template_p_iva0_ibc","",""
    "","","","","","","","","","account_tax_template_p_iva0_s_sc","account_tax_template_p_iva0_isc","",""
    "","","","","","","","","","account_tax_template_p_iva2_bc","account_tax_template_p_iva2_ibc","",""
    "","","","","","","","","","account_tax_template_p_iva2_sc","account_tax_template_p_iva2_isc","",""
    "","","","","","","","","","account_tax_template_p_iva4_bc","account_tax_template_p_dua_exempt","",""
    "","","","","","","","","","account_tax_template_p_iva4_sc","account_tax_template_p_iva4_sp_ex","",""
    "","","","","","","","","","account_tax_template_p_iva4_bi","account_tax_template_p_iva4_ibi","",""
    "","","","","","","","","","account_tax_template_p_iva5_bc","account_tax_template_p_dua_exempt","",""
    "","","","","","","","","","account_tax_template_p_iva5_sc","account_tax_template_p_iva5_isc","",""
    "","","","","","","","","","account_tax_template_p_iva7-5_bc","account_tax_template_p_iva7-5_ibc","",""
    "","","","","","","","","","account_tax_template_p_iva7-5_sc","account_tax_template_p_iva7-5_isc","",""
    "","","","","","","","","","account_tax_template_p_iva10_bc","account_tax_template_p_dua_exempt","",""
    "","","","","","","","","","account_tax_template_p_iva10_sc","account_tax_template_p_iva10_sp_ex","",""
    

## Final steps¶

Finally, you may add a demo company, so the localization can easily be tested in demo mode.

Example

[addons/l10n_ch/demo/demo_company.xml](https://github.com/odoo/odoo/blob/17.0/addons/l10n_ch/demo/demo_company.xml)
    
    
        <record id="partner_demo_company_ch" model="res.partner">
            <field name="name">CH Company</field>
            <field name="vat">CHE-530781296TVA</field>
            <field name="street">14 Meierskappelerstrasse</field>
            <field name="city">Risch-Rotkreuz</field>
            <field name="country_id" ref="base.ch"/>
            
            <field name="zip">6343</field>
            <field name="phone">+41 78 123 45 67</field>
            <field name="email">info@company.chexample.com</field>
            <field name="website">www.chexample.com</field>
        </record>
    
        <record id="partner_demo_company_bank_account" model="res.partner.bank">
            <field name="acc_type">iban</field>
            <field name="acc_number">CH4431999123000889012</field>
            <field name="partner_id" ref="l10n_ch.partner_demo_company_ch"/>
        </record>
    
        <record id="demo_company_ch" model="res.company">
            <field name="name">CH Company</field>
            <field name="partner_id" ref="partner_demo_company_ch"/>
        </record>
    
        <function model="res.company" name="_onchange_country_id">
            <value eval="[ref('demo_company_ch')]"/>
        </function>
    
        <function model="res.users" name="write">
            <value eval="[ref('base.user_root'), ref('base.user_admin'), ref('base.user_demo')]"/>
            <value eval="{'company_ids': [(4, ref('l10n_ch.demo_company_ch'))]}"/>
        </function>
    
        <function model="account.chart.template" name="try_loading">
            <value eval="[]"/>
            <value>ch</value>
            <value model="res.company" eval="obj().env.ref('l10n_ch.demo_company_ch')"/>
        </function>
    

## Accounting reports¶

Enterprise feature

Vedi anche

[Rendiconto](../../applications/finance/accounting/reporting.html)

Accounting reports should be added via a separate module `l10n_XX_reports` that should go to the [enterprise repository](https://github.com/odoo/enterprise/blob/17.0).

Basic `__manifest__.py` file for such a module looks as following:
    
    
    {
        "name": "COUNTRY - Accounting Reports",
        "category": "Accounting/Localizations/Reporting",
        "version": "1.0.0",
        "license": "OEEL-1",
        "depends": [
            "l10n_XX", "account_reports"
        ],
        "data": [
            "data/balance_sheet.xml",
            "data/profit_and_loss.xml",
        ],
        "auto_install": True,
    }
    

Functional overview of financial reports is here: [Rendiconto](../../applications/finance/accounting/reporting.html).

Some good examples:

  * [l10n_ch_reports/data/account_financial_html_report_data.xml](https://github.com/odoo/enterprise/blob/17.0/l10n_ch_reports/data/account_financial_html_report_data.xml)

  * [l10n_be_reports/data/account_financial_html_report_data.xml](https://github.com/odoo/enterprise/blob/17.0/l10n_be_reports/data/account_financial_html_report_data.xml)




You can check the meaning of the fields here:

  * [Report](../reference/standard_modules/account/account_report.html)

  * [Report Line](../reference/standard_modules/account/account_report_line.html)




If you gave a `root_report_id` to your report, it is now available in its variant selector. If not, you still need to add a menu item for it. A default menu item can be created from the form view of the report by clicking on Actions ‣ Create Menu Item. You will then need to refresh the page to see it. Alternatively, to create a dedicated section for a totally new report in the Reporting menu, you need to create a new `ir.ui.menu` record (usually in the main `l10n_XX` module) and a new `ir.actions.client` (usually in the new report XML file) that calls the `account.report` with the new **report id**. Then, set the new menu as `parent_id` field in the action model.

Example

  * [ir.ui.menu creation](https://github.com/odoo/odoo/blob/17.0/addons/l10n_be/data/menuitem_data.xml)

  * [ir.actions.client and menu item creation](https://github.com/odoo/enterprise/blob/17.0/l10n_be_reports/data/partner_vat_listing.xml)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos/accounting_localization.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](translations.html "Translating Modules") |
  * [precedente](create_reports.html "Create customized reports") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Accounting localization


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration