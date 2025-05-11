# Australia — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](austria.html "Austria") |
  * [precedente](argentina.html "Argentina") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Australia



# Australia¶

## Configurazione¶

Nome modulo | Module Key | Descrizione  
---|---|---  
Australia - Accounting | `l10n_au` | Installed by default when the Accounting Fiscal Localization package is set to Australia. This module also installs the ABA credit transfer and the Remittance Advice report module.  
Australian Reports - Accounting | `l10n_au_reports` | Includes the Taxable Payments Annual Reports (TPAR) and the BAS report.  
Australia - Payroll | `l10n_au_hr_payroll` | Payroll localisation for Australia.  
Australia - Payroll with Accounting | `l10n_au_hr_payroll_account` | Installs the link between Australian payroll and accounting. The module also installs the modules: Australian - Accounting; Australian Reports - Accounting; and Australia - Payroll.  
Accounting Customer Statements | `l10n_account_customer_statements` | Allows the management and sending of monthly customer statements from the partner ledger and the contact form. Also used in New Zealand.  
Employment Hero Australian Payroll | `l10n_au_keypay` | Synchronises all pay runs from Employment Hero with Odoo’s journal entries.  
  
## Piano dei conti¶

The Australian chart of accounts is included in the **Australia - Accounting** module. Go to Accounting ‣ Configuration ‣ Chart of Accounts to access it.

Vedi anche

[Piano dei conti](../accounting/get_started/chart_of_accounts.html)

## Taxes and GST¶

The default Australian taxes impact the BAS Report, which can be accessed through Accounting ‣ Reporting ‣ BAS Report.

In Australia, the standard **Goods and Services Tax** (GST) rate is 10%, but different rates and exemptions exist for specific categories of goods and services.

### Mappatura imposta¶

Within the Australian localisation package, tax names encompass the tax rate as an integral part of their naming convention.

Despite the high amount of taxes in Odoo, these taxes are pretty similar (mostly 0% and 10%), with different tax grid variations for:

  * Beni

  * Servizi

  * TPAR

  * TPAR without ABN




Vedi anche

[Taxes](../accounting/taxes.html)

Taxes including a **TPAR** mention impact not only the **BAS** report but also the **TPAR** report. Businesses from certain industries need to report payments made to subcontractors from relevant services during the financial year. Odoo combines the use of taxes and fiscal positions to report these payments on the **TPAR** report. Taxes with the mention **TPAR without ABN** are used to record amounts withheld from subcontractors without an **ABN** for the **ATO**.

Vedi anche

TPAR

Here are the taxes for Australia in Odoo 17.

GST Name | Descrizione | GST Scope | GST Type  
---|---|---|---  
10% | GST Purchases | 

  * 
| Acquisti  
10% INC | GST Inclusive Purchases | 

  * 
| Acquisti  
10% C | Capital Purchases | 

  * 
| Acquisti  
0% C | Zero Rated Purch | 

  * 
| Acquisti  
100% T EX | Purchase (Taxable Imports) - Tax Paid Separately | 

  * 
| Acquisti  
10% I | Purchases for Input Taxed Sales | 

  * 
| Acquisti  
10% P | Purchases for Private use or not deductible | 

  * 
| Acquisti  
100% EX | GST Only on Imports | 

  * 
| Acquisti  
10% Adj | Tax Adjustments (Purchases) | 

  * 
| Acquisti  
10% | GST Sales | 

  * 
| Vendite  
10% INC | GST Inclusive Sales | 

  * 
| Vendite  
0% EX | Zero Rated (Export) Sales | 

  * 
| Vendite  
0% EXEMPT | Exempt Sales | 

  * 
| Vendite  
0% I | Input Taxed Sales | 

  * 
| Vendite  
10% Adj | Tax Adjustments (Sales) | 

  * 
| Vendite  
10% TPAR | GST Purchases | Servizi | Acquisti  
10% TPAR NO ABN | GST Purchases | Servizi | Acquisti  
10% INC TPAR | GST Inclusive Purchases | Servizi | Acquisti  
10% INC TPAR N ABN | GST Inclusive Purchases | Servizi | Acquisti  
10% C TPAR | Capital Purchases | Servizi | Acquisti  
10% C TPAR N ABN | Capital Purchases | Servizi | Acquisti  
0% C TPAR | Zero Rated Purch TPAR | Servizi | Acquisti  
0% C TPAR N ABN | Zero Rated Purch TPAR without ABN | Servizi | Acquisti  
100% T EX TPAR | Purchase (Taxable Imports) - Tax Paid Separately | Servizi | Acquisti  
100% T EX TPAR N ABN | Purchase (Taxable Imports) - Tax Paid Separately | Servizi | Acquisti  
10% I TPAR | Purchases for Input Taxed Sales | Servizi | Acquisti  
100% I TPAR N ABN | Purchases for Input Taxed Sales | Servizi | Acquisti  
10% P TPAR | Purchases for Private use or not deductible | Servizi | Acquisti  
10% P TPAR N ABN | Purchases for Private use or not deductible | Servizi | Acquisti  
100% EX TPAR | GST Only on Imports | Servizi | Acquisti  
100% EX TPAR N ABN | GST Only on Imports | Servizi | Acquisti  
10% Adj TPAR | Tax Adjustments (Purchases) | Servizi | Acquisti  
10% Adj TPAR N ABN | Tax Adjustments (Purchases) | Servizi | Acquisti  
47% WH | Tax Withheld for Partners without ABN | Servizi | Acquisti  
  
## BAS report¶

The **Business Activity Statement (BAS)** report is a critical tax reporting requirement for businesses registered for **Goods and Services Tax (GST)** in Australia. The **BAS** is used to report and remit various taxes to the **Australian Taxation Office (ATO)**. With the Odoo **BAS** feature, businesses can report on the following:

  * Goods and Services Tax (GST)

  * PAYG tax withheld




The taxes for GST are collected from the **tax grid** , which is pre-configured in the system. The **tax grid** can also be manually set up for any additional special GST. Once the tax for each account is set up, the system automatically slots journal items into the correct tax category. This ensures the **BAS** report is accurate and reflective of the business’s financial activities.

In addition, the **BAS** report includes the **PAYG** tax withheld components (**W1** to **W5** , then **summary, section 4**). This integration ensures that all payroll-related withholding taxes are accurately captured and reflected within the report.

Il modulo incorpora regole integrate che facilitano il calcolo automatico delle imposte per i tipi da **W1** a **W5**. Per una descrizione dettagliata e maggiori informazioni sul processo di calcolo di queste imposte, consultare la documentazione dell’applicazione Payroll.

Vedi anche

Payroll

### Chiusura del report BAS¶

Quando è il momento di presentare la dichiarazione dei redditi all’ATO, clicca su :guilabel:Registrazione di chiusura. Il periodo della dichiarazione dei redditi può essere configurato in :menuselection:Configurazione –> Impostazioni –> Periodicità della Dichiarazione dei Redditi. Inoltre, la data di inizio del periodo della dichiarazione può essere definita tramite il pulsante periodo (indicato da un’icona calendario 📅).

Vedi anche

:doc:`Chiusura dell’anno <../contabilità/rendicontazione/fine anno>

Nota

Odoo utilizza il _trimestre solare_ piuttosto che il trimestre dell’anno fiscale australiano, il che significa che **luglio-settembre è il Q3 in Odoo**.

Prima di chiudere la voce per la prima volta, è necessario impostare i conti di default **GST da pagare** e **GST da ricevere**. Viene visualizzata una notifica che reindirizza l’utente alle configurazioni dei gruppi fiscali.

Una volta impostati i conti **GST da pagare** e **GST da ricevere** , il report **BAS** genera automaticamente un’accurata registrazione di chiusura del giornale, che bilancia il saldo GST con il conto di compensazione GST.

Il saldo tra **GST da ricevere** e **da pagare** è impostato sul conto di compensazione fiscale definito nel gruppo fiscale. L’importo da pagare o ricevere dalla **ATO** può essere riconciliato con un estratto conto bancario.

Importante

Il rapporto **BAS** non viene presentato direttamente all”**ATO**. Odoo vi aiuta a calcolare automaticamente i valori necessari in ogni sezione, con la possibilità di controllarli per comprendere meglio la storia dietro questi numeri. Le aziende possono copiare questi valori e inserirli nel portale dell’AATO <<https://www.ato.gov.au/newsrooms/small-business-newsroom/lodging-your-next-bas>>`_.

## Rapporto TPAR¶

Odoo consente alle aziende di segnalare i pagamenti effettuati a contraenti o subappaltatori durante l’anno finanziario. Questo viene fatto generando un TPAR. Se non siete sicuri che la vostra azienda abbia bisogno di questo rapporto, consultate la documentazione fornita dall’associazione [ATO](https://www.ato.gov.au/businesses-and-organisations/preparing-lodging-and-paying/reports-and-returns/taxable-payments-annual-report). Questo rapporto si trova in Contabilità ‣ Reporting ‣ Taxable Payments Annual Reports (TPAR).

### Configurazione¶

In Contabilità ‣ Clienti o Contabilità ‣ Fornitori, selezionare un contraente e impostare una Posizione fiscale nella scheda Vendite e acquisti.

Quando si fattura un contatto con una posizione fiscale impostata su TPAR o TPAR senza ABN, il rapporto viene generato automaticamente in Accounting ‣ Reporting ‣ Taxable Payments Annual Reports (TPAR).

Il rapporto include il **ABN** , il **Total GST** , il **Gross Paid** e il **Tax Withheld** dei loro subappaltatori **TPAR**.

  * **Totale GST** : l’imposta totale pagata

  * **Importo lordo pagato** : viene visualizzato dopo aver registrato un pagamento per quelle fatture.

  * **Tax Withheld** : shown if the subcontractor is registered with a fiscal position set to TPAR without ABN




The **TPAR** report can be exported to PDF, XLSX, and TPAR formats.

## Customer statements¶

Customer statements allow customers to see their financial transactions with the company over a certain period, and overdue statement details. These statements can be sent out to customers by email.

There are **two** ways for customers to download these statements.

  1. **From the contact form:** Customer statements are under Customers ‣ Customers. Select a customer, click the **gear icon (⚙)** , and then Print Customer Statements. This prints out the statement from the beginning of the month to today’s date.

  2. **From the partner ledger:** This option allows for more flexibility in selecting a statement’s start and end date. You can access it by going to Accounting ‣ Reporting ‣ Partner Ledger. From here, specify a date range in the **calendar menu (📅)** for the statement, hover over a partner, and click the Customer Statements tab.




## Remittance advice¶

A remittance advice is a document used as proof of payment to a business. In Odoo, it can be accessed by going to Accounting ‣ Vendors ‣ Payments, selecting the payment(s), and clicking Print ‣ Payment Receipt.

## E-Invoicing via Peppol¶

Odoo is compliant with Australia’s and New Zealand’s [PEPPOL requirements](https://peppol.org/learn-more/country-profiles/australia/). You can find and set up **electronic invoicing** settings per partner under Accounting ‣ Customers or Accounting ‣ Vendors, select a partner, and click the Accounting tab.

Importante

Validating an invoice or credit note for a partner on the PEPPOL network will download a compliant XML file that can be manually uploaded to your PEPPOL network.

## ABA files for batch payments¶

### Introduzione¶

An ABA file is a digital format developed by the [Australian Bankers” Association](https://www.ausbanking.org.au/). It is designed for business customers to facilitate bulk payment processing by uploading a single file from their business management software.

The main advantage of using ABA files is to improve payment and matching efficiency. This is achieved by consolidating numerous payments into one file for batch processing, which can be submitted to all Australian banks.

### Configurazione¶

#### Impostazioni¶

To enable **batch payments** , go to Accounting ‣ Configuration ‣ Setting ‣ Batch Payment and enable Allow Batch Payments.

#### Bank journal¶

Then, go to Accounting ‣ Configuration ‣ Journals and select the Bank journal type. In the Journal Entries tab, enter the Account Number and click Create and edit. In the pop-up window, fill in the following fields:

  * Bank

  * Account Holder Name

  * BSB

  * Account Holder




Importante

The Send Money field must be **enabled**.

Nota

The Currency field is optional.

Go back to the Journal Entries tab and fill in the following fields related to the ABA:

  * BSB: This field is auto-formatted from the bank account

  * Financial Institution Code: The official 3-letter abbreviation of the financial institution (e.g., WBC for Westpac)

  * Supplying User Name: 6-digit number provided by your bank. Contact or check your bank website if you need to know.

  * Include Self-Balancing Transactions: Selecting this option adds an additional
    

«self-balancing» transaction to the end of the ABA file, which some financial institutions require when generating ABA files. Check with your bank to see if you need this option.




Then, go to the Outgoing Payments tab on the same Bank type journal. Click Add a line and select ABA Credit Transfer as the **payment method**.

#### Partners’ bank accounts¶

Go to Accounting ‣ Customers ‣ Customers or Accounting ‣ Vendors ‣ Vendors and select a partner for whom you want to add banking information. Once selected, click the Accounting tab, and under the Bank Accounts section, click Add a line to fill in:

  * Account Number of that partner

  * Bank

  * Account Holder Name

  * BSB

  * Accounter Holder

  * Send Money defines the bank account as _trusted_ , which is essential for ABA files and must be enabled if to be used.




### Generate an ABA file¶

To generate an **ABA** file, Create a vendor bill (manually or from a purchase order). Confirm the bill and ensure the vendor’s banking information is set up correctly before registering a payment..

Next, click Register Payment in the pop-up window: select the Bank journal, select ABA Credit Transfer as Payment Method, and select the right Recipient Bank Account.

Once payments are confirmed, they appear in Accounting ‣ Vendors ‣ Payments. Tick the box of the payments to be included in the batch, then click Create Batch. Verify all information is correct and finally Validate. Once validated, the ABA file becomes available in the **chatter** on the right.

After uploading it to your bank’s portal, an ABA transaction line will appear in your bank feed at the following bank feed iteration. You will need to reconcile it against the **batch payment** made in Odoo.

Vedi anche

[Batch Payment](../accounting/payments/batch.html)

## Buy Now, Pay Later solutions¶

Buy Now, Pay Later solutions are popular payment methods for eShops in Australia. Some of these solutions are available via the [Stripe](https://stripe.com/en-au/payments/payment-methods) and [AsiaPay](https://www.asiapay.com.au/payment.html#option) payment providers.

Vedi anche

  * [AsiaPay Payment Provider](../payment_providers/asiapay.html)

  * [Stripe Payment Provider](../payment_providers/stripe.html)




## POS terminals for Australia¶

If you wish to have a direct connection between Odoo and your PoS terminal in Australia, you _must_ have a **Stripe** terminal. Odoo supports the **EFTPOS** payment solution in Australia.

Nota

You do not need a Stripe payment terminal to use Odoo as your main PoS system. The only drawback of not using Stripe is that cashiers must manually enter the final payment amount on the terminal.

Vedi anche

  * [Stripe Odoo Payment Provider](../payment_providers/stripe.html)

  * [Stripe Odoo Payment Terminal](../../sales/point_of_sale/payment_methods/terminals/stripe.html)

  * [Stripe Dashboard](https://dashboard.stripe.com/dashboard)

  * [Stripe Terminal](https://stripe.com/docs/terminal)




## Libro paga¶

Importante

Odoo is currently not compliant with STP Phase 2.

### Create your employees¶

To create an **employee form** and fill in mandatory information, go to the **Employees** app and click Create. In the HR Settings tab, you can input the mandatory information:

  1. TFN Status: if the employee provides a TFN, make sure to add it to the “TFN” field

  2. Non-resident: if the employee is a foreign resident

  3. Tax-free Threshold: if the employee is below or above the threshold

  4. HELP / STSL: for all types of study and training support loans (e.g. HELP, VSL, SSL…)

  5. Medicare levy Deduction

  6. Medicare levy Exemption

  7. Withholding for Extra Pay

  8. …




### Manage Australian contracts¶

Once the employee form has been created, ensure the contract is enabled by clicking the Contracts smart button or by going to Employees ‣ Employees ‣ Contracts.

Nota

Only one contract can be active simultaneously per employee, but an employee can be assigned consecutive contracts during their employment.

Contractual information related to Australia can be found in the following **three** places:

  1. Before assigning a salary amount, pay frequency, and other important details to a contract, defining the **salary structure** , **start date** , and **work entry** source is important. In Australia, a «Salary Structure» is employed to specify the tax schedule applicable to that contract, as defined by the Australian Taxation Office (ATO). Most contracts will fall under the following **three structures** :

>      * **Regular (Schedule 1)** : the great majority of Australian employees will fall in this category; hence, this structure is assigned by default to all contracts.
> 
>      * **Working holiday makers (Schedule 15)**. When employing working holiday makers (WHMs), other taxes apply. For detailed information on these specific tax implications, refer to the documentation provided by the **ATO**.
> 
>      * **No TFN**. Choose this structure if the employee hasn’t provided a **TFN** for over **28** days.




Importante

The structures **Horticulture/Shearing (Schedule 2)** and **Artists and Performers (Schedule 3)** are only partially complete, and proper tests should be performed before using them to pay employees in your production database. Send your feedback to [au-feedback@mail.odoo.com](mailto:au-feedback%40mail.odoo.com).

The field Work Entry Source is also significant and defines how **working hours** and **days** are accounted for in the employee’s payslip.

  * Working Schedule: work entries are automatically generated based on the employee’s working schedule, starting from the contract’s start date.. For example, let’s assume that an employee works 38 hours a week, and their contract’s begins on January 1st. Today is January 16th, and the user generates a pay run from January 14th to 20th. The working hours on the payslip will be automatically calculated to be 38 hours (5 * 7.36 hours) if no leave is taken.

  * Attendances: The default working schedule is ignored, and work entries are only generated after clocking in and out of the attendance app.

  * Planning: The default working schedule is ignored, and work entries are generated from planning shifts only.

Importante

Additional configurations are necessary to ensure that Odoo’s payslips automatically compute various **penalty rates** as defined by an **award (overtime rate, public holiday rate, etc)**. To create these configurations, create new work-entry types for each penalty rate and then assign a penalty rate in % to each. Once this one-time configuration is done, work entries can be manually imported for each period, and Odoo will separate the pay items and rates on the employee’s payslip.

Importante

Timesheets do not impact work entries in Odoo.

  * The Salary Information tab contains a few essential fields impacting the frequency of pay runs and the management of payslip rules in Odoo.

>     * Wage Type: Select the Fixed Wage pay type for full-time and part-time employees. For casual workers and other Hourly Wage type. For employees being paid hourly, make sure to define the correct **casual loading**.
> 
>     * Schedule Pay: In Australia, only the following pay run frequencies are accepted: **daily, weekly, bi-weekly (or fortnightly), monthly, and quarterly**.
> 
>     * Wage (/period): Assign a wage to the contract according to their pay frequency. On payslips, the corresponding annual and hourly rates will be automatically computed.

Nota

For hourly workers, please note that the hourly wage should exclude casual loading.

  * The Australia tab. Most of the fields in this tab are used for **Single Touch Payroll** (or **STP**) reporting, which requires a thorough understanding of several details from an employee’s contract. Review the information on this tab before moving forward with pay runs. This includes the following **four** fields which impact payslip computations:

>     * Withholding Variation: use this field in case the employee’s withholding must be varied upward or downward according to their circumstances. E.g., if employee X benefits from a 25% withholding variation, their percentage of tax withheld will vary from whatever amount they were supposed to pay according to their salary structure and situation to a fixed 25%.
> 
>     * Leave Loading: if the employee benefits from a regular leave loading, the value set in the field Leave Loading Rate (e.g., 17.5%) is added to any amount earned when taking annual or long service leaves.
> 
>     * Salary Sacrifice Superannuation: any amount added to this field is deducted, per pay frequency, from the employee’s basic salary before the computation of the gross salary. Then, this amount is added to the super guarantee line of their payslip. E.g., if employee Y earns 5,000 AUD per month and sacrifices 300 AUD to superannuation, their gross salary will be 4,700 AUD, and 300 AUD will be added on top of their normal super contributions.
> 
>     * Salary Sacrifice Other: any amount added to this field is deducted, per pay frequency, from the employee’s basic salary before the computation of the gross salary.




Once all important information has been entered, ensure the transition of the contract’s status from «New» to «Running» to facilitate its use in pay runs.

### Assign superannuation accounts¶

Upon receipt of superannuation details from a new employee, ensure the creation of a new account in Payroll ‣ Configuration ‣ Super Accounts to link it to the employee. Input the Super Fund, Member Since date, and TFN number of the employee.

Suppose the employee uses a superannuation fund that does not exist in the database yet. In that case Odoo creates a new one and centralises basic information about this fund, such as its **ABN** , **address** , type (**APRA** or **SMSF**), **USI** , and **ESA**. Super funds can be created or imported in Payroll ‣ Configuration ‣ Super Funds.

Importante

Odoo is currently not **SuperStream-compliant**.

### Create pay runs with payslips¶

Odoo can create pay runs in **two** ways: via **batch** or via **individual** payslips.

#### Create a batch of payslips¶

When preparing to generate employees’ draft payslips (e.g., at the end of every week, fortnight, or month), navigate to Payroll ‣ Payslips ‣ Batches and click New. Fill in the necessary info, click Generate Payslips, select the Salary Structure, Department, Employees, and Generate. This method allows the creation of multiple payslips corresponding to each employee in a single batch.

  1. Give the batch a name. (E.g., `2024 – Weekly W1`)

  2. Choose the pay run’s start and end date. (E.g., 01/01/2024 to 07/01/2024)

  3. Click on Generate. A pop-up window asks to confirm which employees should be included in the batch. By default, all active employees are included. You can leave Salary Structure field blank as Odoo automatically selects the structure linked to each employee’s contract.

  4. The batch creates as many payslips as there are employees. There is no limit to the number of payslips created in a batch.

  5. Verify important information on each payslip. After payslips from a batch have been generated, there is no need to manually compute payslip lines; Odoo does it for you.




#### Create an individual payslip¶

In cases where the pay run does not fall into the category of regular payslips, the option exists to create a pay run dedicated to a single employee. Go to Payroll ‣ Payslips ‣ All Payslips and click New. Employ this method when processing **one-time payments** for employees, including **return-to-work** payments (**ATO Schedule 4**), **employment termination** payments (**ATO Schedule 7 and 11**), and **commissions and bonuses** (**ATO Schedule 5**). When generating an individual payslip, make sure to proceed with the following steps:

  1. Select an Employee; their Contract will be filled out automatically

  2. Add a pay Period

  3. Select a salary Structure (e.g., return-to-work payment)

  4. Unlike payslips generated from a batch, the payroll user must click the Compute Sheet button to generate payslip lines




#### Understand payslip features¶

The same features apply no matter how payslips are created (individually or via batch).

Depending on how work entries are created, the Worked Days & Inputs table automatically shows the number of days and hours the employee worked during the payslip period next to the corresponding total gross amount.

Nota

There is one line per work entry type, meaning **paid** and **unpaid time-off** , in addition to custom **hourly penalty rates** (overtime, public holidays, etc.) which are automatically added to the table.

In the Other Inputs section, You can add entries such as **allowances** and **extra pay** items in the Other Inputs section.

  * To incorporate various **allowances** into an employee’s payslip, create **allowances** in Payroll ‣ Configuration ‣ Other Input Types. Once created, tick the Is an Allowance checkbox for the involved allowances.

Importante

Withholding for allowances is not computed automatically. The payroll user has to use the field Withholding for allowance under the other inputs table to manually add the total amount to be withheld across all allowances on that payslip.

  * **Extra pay** items are other inputs added to the **payslip’s gross** and, as a result, to the **withholding amount**. An example lies in regular sales commissions, taxed at the same rate as the regular salary (unlike discretionary bonuses, which fall under the ATO’s Schedule 5 and its corresponding salary structure). To configure such a custom pay item, go to Payroll ‣ Configuration ‣ Other Input Types and create a new entry with the code **EXTRA**.




In the Salary Computation tab, the payroll user can verify whether all the pay rules have been computed correctly as per employee, contract and salary structure. Here are a few guidelines to better understand the data.

  1. **Basic salary:** amount from which tax-deductible lines can be subtracted

  2. **Gross salary:** amount subject to the taxes defined by the salary structure

  3. **Withholding:** tax amount to be paid to the **ATO**

  4. **Net salary:** amount to be paid to the employee’s bank account

  5. **Superannuation Guarantee:** amount to be provisioned for quarterly payments to the employee’s super account

  6. **Allowances & Extra pay items:** these lines will show if other inputs are added to the payslip.

  7. **Other lines:** depending on the employee and contract specifics (Medicare, child support, salary, sacrifice, etc.)




When satisfied with the payslip, click Create Draft entry to generate a draft accounting journal entry that the accountant can review. Note that in the case of a payslip batch, this accounting entry will sum up balances from all payslips.

### Pay employees¶

After a batch or a payslip’s journal entry has been posted, the company can pay their employees. The user can choose between **two** different **payment methods**.

  * Pay the employee in batch via **ABA** files. This is **only** possible from the **payslip batch** level. Ensure the batch’s journal entry has been posted to generate the **ABA** file. From the batch form view, click Create ABA File and choose the desired bank journal. The newly generated **ABA** file becomes available for download in the field ABA File. It is possible to re-generate the ABA file after applying corrections to existing payslips.

Nota

It is always possible to include an individual payslip into an existing batch in an **ABA** file.

Importante

An ABA file can only be generated if both the company’s bank account and each employee’s bank account have been properly configured.

  * From the employee’s payslip (Payroll ‣ Payslips), once the payslip’s journal entry has been posted, click Register Payment. The process is the same as [paying vendor bills](../accounting/payments.html): select the desired bank journal and payment method, then later reconcile the payment with the corresponding bank statement.




#### One-time payments¶

Certain payments, such as **Return-to-Work** payments and **Employment Termination Payments** **(ETP)** , are processed only once and require a slightly different approach.

##### Return-to-Work payments¶

A **Return-to-Work** payment is a payment made to an employee to resume working. To process one, create an individual payslip, select the employee, and modify its **regular structure** to Australia: Return to work. Then, add the **gross amount** of that payment in the Other Inputs section and compute the payslip. Odoo automatically computes the **PAYG withholding** , the **net amount** , and the **super guarantee** corresponding to that payment.

##### Termination payments¶

Before proceeding with the employee’s ETP, make sure that a **Contract End Date** has been set on that employee’s contract so that Odoo can automatically compute the final prorated salary of that employee for the current month.

First, create the final salary for that employee this month. To do so, create an individual payslip. If the contract end date is set correctly, Odoo will automatically compute the prorated salary up to the final payslip date.

Suggerimento

We recommend creating a batch on the fly for that payslip, in which the ETP is added as a second payslip of that same batch.

Create a second individual payslip and include it in the same batch. Change the salary structure on that payslip to Australia: Termination Payments. Before computing the sheet, it is important to provide the payslip with termination details .

  * Genuine or Non-Genuine Redundancy. This choice impacts the amounts and caps defined per **ETP** type.

  * **ETP types** : see the full list of termination payment types in Other Input Types by filtering by `ETP Type is Set`.




Add the relevant **ETP type** in the Other Inputs table of the payslip, then compute the payslip. Odoo computes the **gross ETP** , the **withholding** , the **unused leaves** , and the **net salary** according to the rules defined on the **ETP** , the **employee** , and their **contract**. Once payment for both payslips is ready to be processed, an **ABA** file can be created directly from the batch.

## Retribuzione australiana con Employment Hero¶

If your business is already up and running with [Employment Hero](https://employmenthero.com/), you can use our connector as an alternative payroll solution.

The Employment Hero module synchronises payslip accounting entries (e.g., expenses, social charges, liabilities, taxes) automatically from Employment Hero to Odoo. Payroll administration is still done in Employment Hero. We only record the **journal entries** in Odoo.

Importante

KeyPay was rebranded as **Employment Hero** in March 2023.

### Configurazione¶

  1. [Activate](../../general/apps_modules.html#general-install) the Employment Hero Australian Payroll module (`l10n_au_keypay`).

  2. Configure the **Employment Hero API** by going to Accounting ‣ Configuration ‣ Settings. More fields become visible after clicking on Enable Employment Hero Integration.

     * You can find the API Key in the My Account section of the Employment Hero platform.

     * The **Payroll URL** is pre-filled with `https://keypay.yourpayroll.com.au`.

Avvertimento

Do not change the **pre-filled Payroll URL**

     * You can find the **Business ID** in the Employment Hero URL. (i.e., `189241`)

     * You can choose any Odoo journal to post the payslip entries.

  3. Configure the tax by going to Accounting ‣ Configuration ‣ Taxes. Create the necessary taxes for the Employment Hero payslip entries. Fill in the tax code from **Employment Hero** in the Matching Employment Hero Tax field.




### How does the API work?¶

The API syncs the journal entries from Employment Hero to Odoo and leaves them in draft mode. The reference includes the Employment Hero payslip entry ID in brackets for the user to easily retrieve the same record in Employment Hero and Odoo.

By default, the synchronisation happens once per week. You can fetch the records manually by going to Accounting ‣ Configuration ‣ Settings and, in the Enable Employment Hero Integration option, click on Fetch Payruns Manually.

Employment Hero payslip entries also work based on double-entry bookkeeping.

The accounts used by Employment Hero are defined in the section Payroll settings.

For the API to work, you need to create the same accounts as the default accounts of your Employment Hero business (**same name and same code**) in Odoo. You also need to choose the correct account types in Odoo to generate accurate financial reports.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/australia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](austria.html "Austria") |
  * [precedente](argentina.html "Argentina") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Australia


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
  *[RUT]: Registro único tributario
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
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report