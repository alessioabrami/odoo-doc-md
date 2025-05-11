# Stati Uniti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uruguay.html "Uruguay") |
  * [precedente](united_kingdom.html "Regno Unito") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Stati Uniti



# Stati Uniti¶

The Odoo fiscal localization package for the United States follows the Generally Acceptable Accounting Principles (GAAP) accounting standards and rules used to prepare financial statements, as outlined by the Financial Accounting Standards Board (FASB) and adopted by the Securities and Exchange Commission (SEC).

Vedi anche

  * [Financial Accounting Standards Board (FASB)](https://asc.fasb.org/Home)

  * [Securities and Exchange Commission (SEC)](https://www.sec.gov/)




In addition, a series of videos on the subject of Accounting are available through Odoo’s eLearning platform. These videos cover how to start from scratch, set up configurations, complete common workflows, and provide in-depth looks at some specific use cases, as well.

Vedi anche

  * [Odoo Tutorials: Accounting & Invoicing](https://www.odoo.com/slides/accounting-and-invoicing-19)

  * [Odoo SmartClass: Accounting](https://www.odoo.com/slides/smartclass-accounting-121)




## Configurazione¶

Below are the available modules in Odoo for accounting use in the United States.

Nota

The modules listed below are either for reference only or are optional, as the core requirements to operate under the US fiscal localization in Odoo are already included under the default package that came installed during database initialization.

Verify the default package is in use by navigating to Accounting App ‣ Settings and under the Fiscal Localization section at the top, look for the `Generic Chart Template` selection to be listed next to the Package field label. This chart template includes the necessary settings for the US localization for the Odoo _Accounting_ app.

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the United States localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
United States - Accounting | `l10n_us` | Base accounting module for United States localization.  
US - Accounting Reports | `l10n_us_reports` | Adds United States accounting reports.  
US Checks Layout | `l10n_us_check_printing` | Enables the printing of payments on pre-printed check paper. Supports the three most common check formats and will work out of the box with the linked checks from [checkdepot.net](https://checkdepot.net/collections/computer-checks/Odoo).

  * [Check on top: Quicken / QuickBooks standard](https://checkdepot.net/collections/computer-checks/odoo+top-check)
  * [Check on middle: Peachtree standard](https://checkdepot.net/collections/computer-checks/odoo+middle-check)
  * [Check on bottom: ADP standard](https://checkdepot.net/collections/computer-checks/odoo+Bottom-Check)

  
NACHA Payments | `l10n_us_payment_nacha` | Export payments as NACHA files for use in the United States.  
1099 Reporting | `l10n_us_1099` | Export 1099 data for e-filing with a 3rd party.  
Avatax | `account_avatax` | Module for the [AvaTax integration](../accounting/taxes/avatax.html) with Odoo.  
United States - Payroll | `l10n_us_hr_payroll` | Includes the necessary rules for United States payroll, including:

  * Employee Details
  * Contratti dipendente
  * Passport-based Contracts
  * Allowances/Deductions
  * Allow Configurations for Basic/Gross/Net Salary
  * Employee Payslip
  * Integration with Leaves Management

  
United States - Payroll with Accounting | `l10n_us_hr_payroll_account` | Contains the necessary accounting data for the United States payroll rules.  
United States - Payroll - Export to ADP | `l10n_us_hr_payroll_adp` | Export Work Entries to the ADP payroll software.  
  
## Piano dei conti¶

The [chart of accounts (COA)](../accounting/get_started/chart_of_accounts.html) for the United States localization, in Odoo, follows the standard GAAP structure, with accounts grouped into seven main categories, with corresponding numeric values that prefix individual journal entries:

  * **Receivable** : the balance of money (or credit) due to the business for goods or services delivered or used, but not yet paid for by customers. AR is indicated by the journal code labeled (or beginning) with 1.

  * **Payable** : the business’s short-term obligations owed to its creditors or suppliers, which have not yet been paid. AP is indicated by the journal code labeled (or beginning) with 2.

  * **Equity** : the amount of money that would be returned to a company’s shareholders if all of the assets were liquidated and all of the company’s debt was paid off in the case of liquidation. Equity is indicated by the journal code labeled (or beginning) with 3 or 9.

  * **Assets** : items listed on the balance sheet that contains economic value or have the ability to generate cash flows in the future, such as a piece of machinery, a financial security, or a patent. Assets are indicated by the journal code labeled (or beginning) with 1.

  * **Liability** : refers to a company’s financial debts or obligations that arise during the course of business operations. Liabilities are indicated by the journal code labeled (or beginning) with 2.

  * **Income** : synonymous with _net income_ , this is the profit a company retains after paying off all relevant expenses from sales revenue earned. Income is indicated by the journal code labeled (or beginning) with 4 or 6.

  * **Expenses** : the cost of operations that a company incurs to generate revenue. Expenses are indicated by the journal code labeled (or beginning) with a 6.




Suggerimento

Predefined accounts are included in Odoo, as part of the CoA that’s installed with the US localization package. The accounts listed below are preconfigured to perform certain operations within Odoo. It is recommended to **not** delete these accounts; however, if changes are needed, rename the accounts instead.

Type | Account Name  
---|---  
Current Assets |  Bank Suspense Account Outstanding Receipts Outstanding Payments Liquidity Transfer Stock Valuation Stock Interim (Received) Stock Interim (Delivered) Cost of Production  
Income |  Foreign Exchange Gain Cash Difference Gain Cash Discount Gain  
Expenses |  Cash Discount Loss Foreign Exchange Loss Cash Difference Loss  
Current Year Earnings | Undistributed Profits/Losses  
Receivable | Account Receivable  
Payable | Account Payable  
  
Vedi anche

  * [Piano dei conti](../accounting/get_started/chart_of_accounts.html)

  * [Promemoria contabile](../accounting/get_started/cheat_sheet.html)




### View, edit, and sort accounts¶

Access the _Chart of Accounts_ dashboard in Odoo by navigating to Accounting app ‣ Configuration ‣ Accounting: Chart of Accounts.

From the Chart of Accounts dashboard, create new accounts by clicking the New button in the top-left corner of the dashboard and [filling in the corresponding form](../accounting/get_started/chart_of_accounts.html#chart-of-account-create). Search and sort through existing accounts by using specific Filters and Group By criteria, which are available in the search drop-down menu.

To filter accounts by category, click the __(caret down) icon to access the drop-down menu and look under the Filters column for individual selections. Clicking on a specific category will only show accounts that match that particular filter.

To view all the available account types, remove all of the filters in the search bar, and then click the __(caret down) icon to access the drop-down menu. From there, select Account Type under the Group By column heading to list all of the account types in the table.

Besides structure, there are other key differences in the chart of accounts in the United States, compared to other countries:

  * **Specificity** : US GAAP often requires more detailed accounts compared to some other countries. This can include separate accounts for various types of revenue, expenses, and assets, providing more granular information in financial reports.

  * **Regulatory Requirements** : In the United States, there are specific regulatory requirements set by bodies such as the SEC for publicly traded companies. These requirements may influence the structure and content of the CoA to ensure compliance with reporting standards.

  * **Industry Practices** : Certain industries in the United States may have unique accounting requirements or specialized CoA structures. For example, financial institutions often have specific accounts related to loans, investments, and interest income.

  * **Tax Considerations** : The CoA may also reflect tax considerations, such as accounts for deductible expenses, deferred tax assets, and liabilities, to ensure compliance with tax laws and facilitate tax reporting.




These differences, ultimately, should be reflected in the CoA structure itself, with the addition of new accounts, as needed, in order to meet the demands of US accounting reporting requirements.

Vedi anche

  * [Create a new account](../accounting/get_started/chart_of_accounts.html#chart-of-account-create)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




## Imposte¶

In the United States, tax rates and what is considered taxable vary by jurisdiction. Default _Sales_ and _Purchase_ taxes are created automatically when the Odoo _Accounting_ application is installed. To manage existing or configure additional taxes, navigate to Accounting ‣ Configuration ‣ Taxes.

### AvaTax¶

**Avalara AvaTax** is a cloud-based tax calculation and compliance software that integrates with Odoo for several localizations. Integrating AvaTax with Odoo provides real-time and region-specific tax calculations when items are sold, purchased, and invoiced in the database.

Importante

AvaTax is available for integration with databases/companies that have locations in the United States and Canada. Reference the [Paese fiscale](../accounting/taxes/avatax.html#avatax-fiscal-country) documentation for more information.

Vedi anche

Refer to the documentation articles below to integrate and configure an AvaTax account with an Odoo database:

  * [AvaTax integration](../accounting/taxes/avatax.html)

  * [Avalara management portal](../accounting/taxes/avatax/avalara_portal.html)

  * [Calculate taxes with AvaTax](../accounting/taxes/avatax/avatax_use.html)

  * [US Tax Compliance: AvaTax elearning video](https://www.odoo.com/slides/slide/us-tax-compliance-avatax-2858?fullscreen=1)

  * Avalara’s support documents: [About AvaTax](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=dqa1657870670369_dqa1657870670369&topicId=About_AvaTax.html&_LANG=enus)




## Report¶

A number of [report selections](../accounting/reporting.html) are readily available for the US localization, under the Accounting app ‣ Reporting drop-down menu:

  * [Balance Sheet](../accounting/reporting.html#accounting-reporting-balance-sheet): a «snapshot» of a company’s financial position at a specific point in time, which contains an overview of a company’s assets, liabilities, and equity.

  * [Profit & Loss](../accounting/reporting.html#accounting-reporting-balance-sheet): otherwise known as a _P &L statement_ or _income statement_ , provides a summary of a company’s revenues, expenses, and profits/losses over a given period of time.

  * Cash Flow Statement: shows how much cash and cash equivalents a company has received and spent in a given period.

  * [Executive Summary](../accounting/reporting.html#accounting-reporting-executive-summary): an overview report that covers the key performance indicators of a company’s financial position, such as revenue, profit, and debt.

  * [Tax Report](../accounting/reporting.html#accounting-reporting-tax-report): an official form filed for a tax authority that reports income, expenses, and other pertinent tax information. Tax reports allow taxpayers to calculate their tax liability, schedule tax payments, or request refunds for the overpayment of taxes. In Odoo, the tax report can be made monthly, every two months, quarterly, every 4 months, semi-annually, and annually.

  * Check Register: a report that displays cash transactions (regardless of the journal) with their running balance after the transaction. Only visible with the _US - Accounting Reports_ (`l10n_us_reports`) module installed.

  * 1099 Report: a CSV download of payments made to non-employees in a period to file electronically in a third-party service. Only visible with the _1099 Reporting_ (`l10n_us_1099`) module installed.




Depending on the type of report, certain filters are available at the top of the dashboard:

  * a _date_ filter, indicated by a __(calendar) icon that precedes a date in _MM/DD/YYYY_ format. Use this to select a specific date or date range for the report.

  * a __ Comparison filter, to compare reporting periods against each other

  * a _journal_ filter, as indicated by a __(book) icon and the default setting of All Journals. Use this filter to specify which journals should be included in the report.

  * an _entries type_ filter, as indicated by a __(filter) icon, with the default setting of Posted Entries Only, Accrual Basis. Use this filter to determine which type of journal entries should be included in the report (e.g. posted or draft), along with the type of accounting method (e.g. accrual or cash basis).

    * There are view options in this filter, as well, one that will Hide lines at 0 for more relevant viewing, along with a Split Horizontally option to keep the report above the screen’s fold, removing the need to scroll.

  * a _decimal_ filter, that by default, includes figures with cents, as indicated by the In .$ setting. Use the other options in the drop-down menu to change figures in the report to whole numbers (In $), thousands (In K$), or millions (In M$) formats.

  * a report _customization_ filter, indicated by the __(gears) icon. Use this filter to customize the current report’s sections and line items, or build new reports, as desired.




Vedi anche

  * [Accounting reporting](../accounting/reporting.html)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




### Rapporto 1099¶

The 1099 report, available by [installing](../../general/apps_modules.html#general-install) the _1099 Reporting_ (`l10n_us_1099`) module, includes payments that are made to non-employees across a given reporting period. Use the available CSV download from the report in Odoo to file 1099 payments electronically via a third-party service.

To generate a 1099 report, navigate to Accounting app ‣ Reporting ‣ Management: 1099 Report to open a 1099 Report wizard.

First, enter the date range of the transactions to report in the Start Date and End Date fields.

Then, edit the journal items that appear on the wizard. Click Add a line to add any items that are missing. Be sure to remove any items that should not be included in the report by clicking __(delete) on the row.

Finally, once all necessary items are included in the 1099 report, click on the Generate button. Doing so downloads a CSV file that groups transactions by the partner that received the payments.

### Rendiconto finanziario¶

Navigate to the _Cash Flow Statement_ (CFS) dashboard by going to Accounting app ‣ Reporting ‣ Statement Reports: Cash Flow Statement. From here, CFS reports can be generated using the various filters that are available at the top of the dashboard.

Odoo uses the _direct_ cash flow method to compile cash flow statements, which measures actual cash inflows and outflows from the company’s operations, such as when cash is received from customers or when cash payments are made to suppliers.

By default, an account labeled with any of the three default Tags on the Chart of Accounts dashboard will be included in the report, which includes: Operating Activities, Financing Activities, and Investing & Extraordinary Activities.

Additionally, the cash flow statement in Odoo:

  * is limited to the _Bank_ and _Cash_ journals to reflect money coming in or out; and

  * also contains _Expenses_ accounts, to show the counterpart transactions versus _Bank_ or _Cash_ journal entries, while excluding AR and AP activity.




Example

Create a vendor bill for $100, as an operating expense (not AP). Doing so will **not** reflect a transaction on the cash flow statement. However, register a corresponding payment for $100, and the transaction **will** reflect on the cash flow statement as Cash paid for operating activities.

## Cash discount¶

Cash discounts can be configured from Accounting app ‣ Payment Terms. Each payment term can be set up with a cash discount and reduced tax.

Vedi anche

[Sconti di cassa e riduzioni fiscali](../accounting/customer_invoices/cash_discounts.html)

## Writing checks¶

Using checks is still a common payment practice in the US. Be sure the _US Checks Layout_ (`l10n_us_check_printing`) module for the US localization is [installed](../../general/apps_modules.html#general-install).

To enable check printing from Odoo, navigate to Accounting ‣ Configuration ‣ Settings and find the Vendor Payments section. From here, tick the Checks checkbox to reveal several fields for check configuration.

Select a Check Layout from the drop-down menu:

  * Print Check (Top) - US

  * Print Check (Middle) - US

  * Print Check (Bottom) - US




Next, choose whether or not to enable the Multi-Pages Check Stub checkbox.

Optionally set a Check Top Margin and Check Left Margin, if required.

Once all check configurations are complete, Save the settings.

Suggerimento

Some of the check formats may require pre-printed paper from a third party vendor, <https://checkdepot.net/collections/odoo-checks> is recommended.

Vedi anche

[Pay by checks](../accounting/payments/pay_checks.html)

## Libro paga¶

The _Payroll_ application is responsible for calculating an employee’s pay, taking into account all work, vacation, and sick time, benefits, and deductions. The _Payroll_ app pulls information from the _Attendances_ , _Timesheets_ , _Time Off_ , _Employees_ and _Expenses_ applications, to calculate the worked hours and compensation for each employee.

When using an external payroll provider, such as _ADP_ , it is necessary to export the various payroll-related data, such as work entries, repayment of expenses, taxes, commissions, and any other relevant data, so the data can be uploaded into the payroll provider, who then issues the actual paychecks or directly deposits the funds into an employee’s bank account.

In order to export the payroll data, the work entries must first be validated and correct. Refer to the [work entries](../../hr/payroll/work_entries.html) documentation for more information regarding validating work entries.

Once work entries are validated, the information can be exported to ADP.

After payments have been issued to employees, payslips can be processed into batches, validated, and posted to the corresponding accounting journals to keep all financial records in Odoo current.

### Required information¶

It is important to have the _Employees_ application installed, and all employee information populated. Several fields in both the employee records, as well as in an employee contracts, are necessary to properly process the employee’s pay. Ensure the following fields are filled out in their respective places.

#### Employee records¶

In each employee record, there is various information the _Payroll_ application requires to properly process payslips, including various banking, tax, and work information.

Navigate to the Employees app and select an employee record to view the sections of the employee form that directly affect _Payroll_ :

  * Work Information tab:

    * Work Address: indicates where the employee is located, including the state, which affects the tax calculations.

    * Working Hours: determines how pay is calculated, and determines if an employee earns overtime.

  * Private Information tab:

    * SSN No: the last four digits of the employee’s Social Security Number (SSN) appears on payslips.

    * Bank Account Number: the bank account associated with the NACHA payment file.

  * HR Settings tab:

    * Federal Tax Filing Status: the tax status an employee uses for Payroll tax calculations, which can be different from their state status.

    * State Tax Filing Status: the tax status an employee uses for their state portion of the Payroll tax calculation.

    * W-2 Form: a US tax form indicating the summary of wages, taxes, and benefits paid to an employee during a tax period (typically one year).

    * W-4 Form: an IRS form that helps outline the amount of federal taxes to withhold for an employee, which is paid to the IRS by the company.




#### Employee contracts¶

Additionally, there is information that is found in an employee contract that also affects the _Payroll_ application.

Navigate to the Employees app ‣ Employees ‣ Contracts and select a contract record to view the sections of a contract that directly affect _Payroll_ :

  * General Information:

    * Salary Structure Type: United States: Employee: defines when the employee is paid, their working schedule, and the work entry type.

    * Work Entry source: determines how work entries are calculated.

  * Salary Information tab:

    * SSN No: the last four digits of the employee’s Social Security Number (SSN) appears on payslips.

    * Wage type: determines how the employee is paid, wether a Fixed wage (salary) or Hourly wage.

    * Schedule Pay: defines how often the employee is paid, either Annually, Semi-annually, Quarterly, Bi-monthly, Monthly, Semi-monthly, Bi-weekly, Weekly, or Daily. In the US, Semi-monthly (24 payments a year) or bi-weekly (26 payments a year) are the most common.

    * Wage, Yearly, and Monthly cost: used to show the total cost of an employee. It is recommended to populate the Yearly wage first, as it auto-populates the other fields.

    * Pre-tax benefits: populate this section according to the employee’s selections. Pre-tax benefits decrease the gross wage, which lowers the base amount that is taxed. These are displayed at the beginning of the payslip.

    * Post-tax benefits: these benefits are deductions made _after_ taxes are calculated. These appear towards the end of the payslip before the net amount is displayed.




Vedi anche

[Employees documentation](../../hr/employees/new_employee.html)

### Export work entries to ADP¶

#### Requisiti¶

In order to create a report that can be uploaded to ADP, there are some initial configuration steps that must be completed first.

First, ensure the _United States - Payroll - Export to ADP_ (`l10n_us_hr_payroll_adp`) module is [installed](../../general/apps_modules.html#general-install).

Then, the company **must** have an _ADP Code_ entered in the company settings. To do so, navigate to Payroll app ‣ Configuration ‣ Settings. Enter the ADP Code in the US Localization section.

Next, work entry types **must** have the correct ADP code listed in the _External Code_ field for each work entry type that is being referenced.

Lastly, every employee **must** have an _ADP Code_ entered on their employee form. To do so, navigate to Employees app, select an employee record, and open the HR Settings tab. Enter the ADP Code in the ADP Information section.

The ADP Code code is how ADP identifies that particular employee, and is typically a six-digit number.

Vedi anche

  * [Add a new work entry](../../hr/payroll/work_entries.html#payroll-new-work-entry)

  * [Nuovi dipendenti](../../hr/employees/new_employee.html)




#### Export data¶

Once [work entries](../../hr/payroll/work_entries.html) have been verified, the information can be exported to a CSV file, which can then be uploaded into ADP.

To export the data, navigate to Payroll app ‣ Reporting ‣ United States: ADP Export, then click New. Next, enter the Start Date and End Date for the work entries using the calendar pop-over.

Then, enter a Batch ID in the corresponding field. The recommendation for this field is to enter the date in a `YY-MM-DD` format, followed by any other characters to distinguish that specific batch, such as a department name, or any other defining characteristics for the batch.

Enter a Batch Description in the corresponding field. This should be short and descriptive, but distinct from the Batch Name.

Ensure the correct company populates the Company field. Change the selected company with the drop-down menu, if needed.

Lastly, add the employee’s work entry information to the list. Click Add a line and an Add: Employee pop-up window loads. The list can be [filtered](../../essentials/search.html) to more easily find the employees to add to the list.

Suggerimento

Process the data export in multiple groups instead of in one large group that contains all employees. This helps to meaningfully differentiate the batches and makes processing more tenable, overall. The most common ways to group employees is by department, or by wage type (hourly or salaried).

Select the employees to add to the list by ticking the box to the left of their name. Once all desired employees have been selected, click the Select button in the lower-left corner, and the employees appear in the list.

To create the CSV file, click the Generate button in the top-left corner.

## ACH - electronic transfers¶

Automated Clearing House (ACH) payments are a modern way to transfer funds electronically between bank accounts, replacing traditional paper-based methods. ACH payments are commonly used for direct deposits, bill payments, and business transactions.

### Receive ACH payments: payment provider integration¶

ACH payments are supported by _Authorize.net_ and _Stripe_ payment integrations in Odoo.

Vedi anche

  * [Setting up Authorize.net for ACH payments (Odoo)](../payment_providers/authorize.html#authorize-ach-payments)

  * [Authorize.net’s ACH payment processing for small businesses documentation](https://www.authorize.net/resources/blog/2021/ach-payments-for-small-businesses.html)

  * [Setting up Stripe for ACH payments (Odoo)](../payment_providers/stripe.html)

  * [Stripe’s ACH Direct Debit documentation](https://docs.stripe.com/payments/ach-debit)




### Send payments: NACHA files¶

Odoo can generate a National Automated Clearing House Association (NACHA) compatible ACH file to send to a company’s bank. For each individual _Bank_ journal that the company wishes to pay vendors with, a NACHA configuration section needs to be filled out on the Odoo database.

#### Configurazione¶

First, navigate to the Accounting app ‣ Configuration ‣ Journals. Open the bank journal and click into the Outgoing Payments tab.

Nota

The following NACHA configuration information is normally provided by the company’s financial institution once they have been approved to send payments via their account.

Under the section labeled, NACHA configuration are the fields required to generate a NACHA compatible ACH file to send to a company’s bank. First, enter the routing number of the financial institution in the field labeled, Immediate Destination. This information is widely available on the Internet and generally varies by bank location. This number is usually provided during the initial account setup.

Next, enter the registered name of the financial institution in the field called, Destination. This information will be provided by the bank or credit union.

Following the Destination field is the Immediate Origin field. Enter the 9-digit company ID or Employer Identification Number (EIN) into this field. This information is provided by the financial institution.

Next, enter the Company Identification number, which is a 10-digit number made from combining the 9-digit company ID or Employer Identification Number (EIN), along with an additional number at the start of the sequence. This number is often a `1`. Check with the financial institution should this first number differ to verify that it is correct, as this number is provided for ACH approved accounts.

Enter the Originating DFI Identification number next, which should contain an assigned 8-digit number from the financial institution.

Importante

Enter the numerical values in this section _exactly_ as the company’s financial institution (e.g. bank or credit union) has provided them, otherwise risk failing a successful NACHA configuration in Odoo.

There are two options for the next field: Standard Entry Class Code. Select the drop-down menu to the right of the field and pick either Corporate Credit or Debit (CCD) or Prearranged Payment and Deposit (PPD). Again, this information will be provided by the financial institution. By default Corporate Credit or Debit (CCD) is selected.

Finally, the last option is for Generated Balanced Files. Tick the checkbox to the right of the field to enable Generated Balanced Files. Consult the company’s accountant or financial advisor to make an informed decision for this field.

Manually save the configuration by clicking the __(cloud upload) icon, or navigate away from this screen to auto-save. The configuration is now complete.

#### Crea pagamento raggruppato¶

Now, record each payment in Odoo using the NACHA payment method.

Vedi anche

[Register Payments in Odoo](../accounting/payments.html#accounting-payments-from-invoice-bill)

Importante

Be aware of the cut-off time for same-day payments. Either the file needs to have a future date associated with each payment or the file needs to be sent prior to the cut-off, if the dates included in it match today’s date. Consult the financial institution for the exact cut-off time for their processing of same-day payments.

Once all the payments to be included in the NACHA ACH file have been made, a batch payment needs to be made from the __ Action menu.

To create the batch payments, access the payments page, by navigating to Accounting ‣ Vendors ‣ Payments. Select all the payments that should be included in the NACHA ACH file, by ticking the checkboxes to the far-left of the rows.

Importante

All payments in the batch **must** share the same NACHA payment method.

Next, navigate to the batched payment (Accounting ‣ Vendors ‣ Batch Payments). Click into the payment just created and then click into the Exported File tab. The generated file is listed with the Generation Date. Click the __(download) button to download the file.

If any adjustments need to be made, click the Re-generate Export File button to recreate a new NACHA ACH file.

Vedi anche

  * [Pagamenti raggruppati](../accounting/payments/batch.html)

  * [Europe’s direct debiting](../accounting/payments/batch_sdd.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/united_states.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uruguay.html "Uruguay") |
  * [precedente](united_kingdom.html "Regno Unito") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Stati Uniti


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Point of Sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Order
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Rol Único Tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: one-time password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: Chart of Accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: Automated Clearing House
  *[NACHA]: National Automated Clearing House Association