# Belgio — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](brazil.html "Brasile") |
  * [precedente](austria.html "Austria") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Belgio



# Belgio¶

## Configurazione¶

Install the 🇧🇪 Belgium [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) to get all the default accounting features of the Belgian localization, following the IFRS rules.

## Piano dei conti¶

You can reach the Chart of accounts by going to Accounting ‣ Configuration ‣ Accounting: Chart of Accounts.

The Belgian chart of accounts includes pre-configured accounts as described in the PCMN. To add a new account, click New. A new line appears. Fill it in, click Save, and then Setup to configure it further.

Vedi anche

[Piano dei conti](../accounting/get_started/chart_of_accounts.html)

## Imposte¶

Default Belgian taxes are created automatically when the Belgium - Accounting and the Belgium - Accounting Reports modules are installed. Each tax impacts the Belgian Tax Report, available by going to Accounting ‣ Reporting ‣ Statements Reports: Tax Report.

In Belgium, the standard VAT rate is **21%** , but there are lower rates for some categories of goods and services. An intermediate rate of **12%** is applied on social housing and food served in restaurants, while a reduced rate of **6%** applies to most basic goods, such as food, water supply, books, and medicine. A **0%** rate applies to some exceptional goods and services, such as some daily and weekly publications, as well as recycled goods.

### Non-deductible taxes¶

In Belgium, some taxes are not fully deductible, such as taxes on the maintenance of cars. This means a part of these taxes is considered as an expense.

In Odoo, you can configure non-deductible taxes by creating tax rules for these taxes and linking them to the corresponding accounts. This way, the system automatically calculates the taxes and allocates them to the appropriate accounts.

To configure a new non-deductible tax, go to Accounting ‣ Configuration ‣ Accounting: Taxes, and click New:

  1. Add a line and select Base in the Based On column;

  2. Add a line, then select on tax in the Based on column and enter the **non-deductible** percentage in the % column;

  3. On the of tax line, select the Tax Grid(s) related to your tax;

  4. Add a line with the **deductible** percentage in the % column;

  5. Set of tax in Based On;

  6. Select 411000 VAT recoverable as account, and select the related tax grid.




Once you have created a non-deductible tax, you can apply it to your transactions by selecting the appropriate tax during the encoding of bills and credit notes. The system automatically calculates the tax amount and allocates it to the corresponding accounts based on the tax rules configured.

Example

With the Belgian localization, the **21% car** tax is created by default (50% non-deductible).

Vedi anche

  * [Taxes](../accounting/taxes.html)

  * [Tax return (VAT declaration)](../accounting/reporting/tax_returns.html)




## Report¶

Here is the list of Belgian-specific reports available:

  * Balance sheet;

  * Profit & loss;

  * Tax report;

  * Partner VAT Listing;

  * EC Sales List;

  * Intrastat.




You can access Belgian-specific versions of reports by clicking on the **book** icon when on a report and selecting its Belgian version: **(BE)**.

Vedi anche

[Rendiconto](../accounting/reporting.html)

### Disallowed expenses report¶

**Disallowed expenses** are expenses that can be deducted from your accounting result but not from your fiscal result.

The **disallowed expenses report** is available by going to Accounting ‣ Reporting ‣ Management: Disallowed Expenses. It allows financial results in real-time, and periodic changes. This report is generated based on the **disallowed expenses categories** that you can reach by going to Accounting ‣ Configuration ‣ Management: Disallowed Expenses Categories. Some categories already exist by default but do not have any rates. Click on Set Rates to update a specific category.

Suggerimento

  * You can add multiple rates for various dates. In that case, the rate used to calculate the expense depends on the date at which it is calculated, and the rate set for that date.

  * If you have the **Fleet** app installed, tick the Car Category box when applicable. This makes the vehicle mandatory while booking a vendor bill.




To link a disallowed expenses category with a specific account, go to Accounting ‣ Configuration ‣ Accounting: Chart of Accounts. Find the account you want, and click on Setup. Add the Disallowed Expense category in the Disallowed Expenses field. From now, when an expense is created with this account, the disallowed expense is calculated based on the rate mentioned in the Disallowed Expense category.

Let’s take an example reflecting **restaurant** and **car expenses**.

#### Restaurant expenses¶

In Belgium, 31% of **restaurant** expenses are non-deductible. Create a new **disallowed expenses category** and set both Related Account(s) and Current Rate.

#### Car expenses: vehicle split¶

In Belgium, the deductible percentage varies from car to car and, therefore, should be indicated for each vehicle. To do so, open Fleet and select a vehicle. In the Tax info tab, go to the Disallowed Expenses Rate section and click on Add a line. Add a Start Date and a %. The amounts go in the same account for all car expenses.

When you create a bill for car expenses, you can link each expense to a specific car by filling the Vehicle column, so the right percentage is applied.

The vehicle split option available in the disallowed expenses report allows you to see the rate and disallowed amount for each car.

## Fee form 281.50 and form 325¶

### Fee form 281.50¶

Annually, a **281.50 fee form** must be reported to the fiscal authorities. To do so, the tag `281.50` must be added on the **contact form** of the entities concerned by the **281.50** fee. To add the tag, open Contacts, select the person or company you want to create a **281.50 fee form** for, and add the `281.50` tag in the Tags field.

Nota

Make sure the **street, zip code, country** , and **VAT number** are also informed on the **Contact form**.

Then, depending on the nature of the expense, add the corresponding `281.50` tag on the impact accounts. To do so, go to Accounting ‣ Configuration ‣ Accounting: Chart of Accounts, and click on Setup to add the corresponding `281.50` tag on the impacted accounts, i.e., 281.50 - Commissions, depending on the nature of the expense.

### Form 325¶

You can create a **325 form** by going to Accounting ‣ Reporting ‣ Belgium: Create 325 form. A new page pops up: select the right options and click Generate 325 form. To open an already generated **325 form** , go to Accounting ‣ Reporting ‣ Belgium: Open 325 forms.

## CODA and SODA statements¶

### CODA¶

**CODA** is an electronic XML format used to import Belgian bank statements. You can download CODA files from your bank and import them directly into Odoo by clicking Import file from your Bank journal on your dashboard.

Vedi anche

[Import bank files](../accounting/bank/transactions.html#transactions-import)

### SODA¶

**SODA** is an electronic XML format used to import accounting entries related to salaries. SODA files can be imported into the journal you use to record salaries by going to your Accounting **dashboard** and clicking Upload in the related journal card form.

Once your **SODA** files are imported, the entries are created automatically in your salary journal.

### CodaBox¶

**CodaBox** is a service that allows Belgian companies and accounting firms to access bank information and statements. Odoo provides a way to import such statements automatically.

#### Configurazione¶

To configure and use Codabox, first [install](../../general/apps_modules.html#general-install) the CodaBox module.

##### Configure the Connection¶

For companiesFor accounting firms

Importante

Make sure the [company settings](../../general/companies.html) are correctly configured, i.e., the country is set to Belgium and the Tax ID or Company ID field is filled.

  1. Go to Accounting ‣ Configuration ‣ Settings, then go to the CodaBox & SODA section.

  2. Click on Manage Connection to open the connection wizard, which shows the Company VAT/ID number that will be used for the connection.

  3. If this is your **first connection** , click on Create connection. The wizard confirms that the connection has been created on **Odoo’s side**. Follow the steps to validate the connection on **CodaBox’s side** too.

If this is **not your first connection** , the Password provided by Odoo during the first connection will be requested to create a new connection.

> Nota
> 
> This Password is unique to Odoo and must be stored securely on your side.




Nota

Accounting firms must manage their clients on separate databases and configure them individually to avoid mixing up their data. The connection must be made by an accounting firm with valid CodaBox Connect credentials. In the following instructions, we will refer to your client’s company as _Company_ and to your accounting firm as _Accounting Firm_.

Importante

Make sure the [company settings](../../general/companies.html) are correctly configured, i.e., the country is set to Belgium, the Tax ID or Company ID and Accounting Firm fields are filled, as well as the Tax ID of the Accounting Firm.

  1. Go to Accounting ‣ Configuration ‣ Settings, then go to the CodaBox & SODA section.

  2. Click on Manage Connection to open the connection wizard, which shows the Accounting Firm VAT number and the Company VAT/ID number that will be used for the connection.

  3. If this is your **first connection** , click on Create connection. The wizard confirms that the connection has been created on **Odoo’s side**. Follow the steps to validate the connection on **CodaBox’s side** , too.

If this is **not your first connection** , the Accounting Firm Password provided by Odoo during the first connection will be requested to create a new connection.

> Nota
> 
> This Accounting Firm Password is unique to Odoo and must be stored securely on your side.




The Status should have now switched to Connected.

##### Configure the journals¶

For CODA filesFor SODA files

  1. [Create a new bank journal](../accounting/bank.html).

  2. Set the right IBAN in the Account Number field.

  3. Select CodaBox synchronization as the Bank Feed.




Suggerimento

When working with bank transactions that use different currencies, it is recommended to create multiple journals with the same bank account but different currencies.

  1. Create a new miscellaneous journal.

  2. Go to Accounting ‣ Configuration ‣ Settings, then go to the CodaBox section.

  3. Select the journal you just created in the SODA journal field.




#### Sincronizzazione¶

Once the connection is established, Odoo can be synchronized with CodaBox.

For CODA filesFor SODA files

CODA files are automatically imported from CodaBox every 12 hours. You do not have to do anything. However, if you wish, it can also be done manually, by clicking on Fetch from CodaBox in the Accounting Dashboard.

SODA files are automatically imported from CodaBox once a day as a draft. You do not have to do anything. However, if you wish, it can also be done manually by clicking on Fetch from CodaBox in the Accounting Dashboard.

By default, if an account in the SODA file is not mapped to an account in Odoo, the Suspense Account (499000) is used, and a note is added to the created journal entry.

Nota

You can access the mapping between the SODA and Odoo accounts by going to Accounting ‣ Configuration ‣ Settings and clicking on the Open SODA Mapping button in the CodaBox section.

#### Potenziali problemi¶

  * **CodaBox is not configured. Please check your configuration.**

Either the Company VAT or the Accounting Firm VAT is not set.

  * **No connection exists with these accounting firms and company VAT numbers.** **Please check your configuration.**

> This can happen when checking the connection status, and the Accounting Firm VAT and Company VAT combination still needs to be registered. This may happen if you have changed the Company VAT after the connection was established. For security reasons, you have to recreate a connection for this Company VAT.

  * **It seems that your CodaBox connection is not valid anymore. Please connect again.**

> This can happen if you revoke Odoo’s access to your CodaBox account or still need to complete the configuration process. In this case, you must revoke the connection and create a new one.

  * **The provided password is not valid for this accounting firm.** **You must reuse the password you received from Odoo during your first connection.**

> The password you provided is different from the one you received from Odoo during your first connection. You must use the password you received from Odoo during your first connection to create a new connection for this accounting firm. If you have lost your password, you must first revoke the Odoo connection on CodaBox’s side (i.e., on your myCodaBox portal). Then, you can revoke the connection on Odoo’s side and create a new one.

  * **It seems that the company or accounting firm VAT number you provided is not valid.** **Please check your configuration.**

> Either the Company VAT or the Accounting Firm VAT is not in a valid Belgian format.

  * **It seems that the accounting firm VAT number you provided does not exist in CodaBox.** **Please check your configuration.**

> The Accounting Firm VAT number you provided is not registered in CodaBox. You may not have a valid CodaBox license linked to this VAT number.

  * **It seems you have already created a connection to CodaBox with this accounting firm.** **To create a new connection, you must first revoke the old one on myCodaBox portal.**

> You must go to your myCodaBox portal and revoke Odoo’s access to your CodaBox account. Then, you can create a new connection on Odoo’s side.




Suggerimento

To revoke the connection between Odoo and CodaBox, go to Accounting ‣ Configuration ‣ Settings, scroll down to the CodaBox section, click on Manage Connection, then click on Revoke.

## Fatturazione elettronica¶

Odoo supports the **Peppol BIS Billing 3.0 (UBL)** electronic invoicing format. To enable it for a customer, go to Accounting ‣ Customers ‣ Customers, open their contact form, and under the Accounting tab, select the Peppol BIS Billing 3.0 format.

Vedi anche

[Fatturazione elettronica (EDI)](../accounting/customer_invoices/electronic_invoicing.html)

## Cash discount¶

In Belgium, if an early payment discount is offered on an invoice, the tax is calculated based on the discounted total amount, whether the customer benefits from the discount or not.

To apply the right tax amount and report it correctly in your VAT return, set the tax reduction as Always (upon invoice).

Vedi anche

[Sconti di cassa e riduzioni fiscali](../accounting/customer_invoices/cash_discounts.html)

## Fiscal certification: POS restaurant¶

In Belgium, the owner of a cooking business such as a restaurant or food truck is required by law to use a government-certified **Cash Register System** for their receipts. This applies if their yearly earnings (excluding VAT, drinks, and take-away food) exceed 25,000 euros.

This government-certified system entails the use of a certified POS system, along with a device called a Fiscal Data Module (or **black box**) and a VAT Signing Card.

Importante

Do not forget to register as _foodservice industry manager_ on the [Federal Public Service Finance registration form](https://www.systemedecaisseenregistreuse.be/fr/enregistrement).

### Certified POS system¶

The Odoo POS system is certified for the major versions of databases hosted on **Odoo Online** , **Odoo.sh** , and **On-Premise**. Please refer to the following table to ensure that your POS system is certified.

| Odoo Online | Odoo.sh | On-Premise  
---|---|---|---  
Odoo 18.0 | Certificati | Certificati | Certificati  
Odoo 17.0 | Certificati | Certificati | Certificati  
Odoo 16.0 | Certificati | Certificati | Certificati  
Odoo 15.0 | Certificati | Certificati | Certificati  
Odoo 14.0 | Certificati | Certificati | Certificati  
  
Vedi anche

[Versioni supportate](../../../administration/supported_versions.html)

A [certified POS system](https://www.systemedecaisseenregistreuse.be/systemes-certifies) must adhere to rigorous government regulations, which means it operates differently from a non-certified POS.

  * On a certified POS, you cannot:

    * Set up and use the **global discounts** feature (the `pos_discount` module is blacklisted and cannot be activated).

    * Set up and use the **loyalty programs** feature (the `pos_loyalty` module is blacklisted and cannot be activated).

    * Reprint receipts (the `pos_reprint` module is blacklisted and cannot be activated).

    * Modify prices in order lines.

    * Modify or delete order lines in POS orders.

    * Sell products without a valid VAT number.

    * Use a POS that is not connected to an IoT box.

  * The [cash rounding](../../sales/point_of_sale/pricing/cash_rounding.html) feature must be activated and set to a Rounding Precision of `0,05` and a Rounding Method set as Half-Up.

  * Taxes must be set as included in the price. To set it up, go to Point of Sale ‣ Configuration ‣ Settings, and from the Accounting section, open the Default Sales Tax form by clicking the arrow next to the default sales tax field. There, click Advanced Options and enable Included in Price.

  * At the start of a POS session, users must click Work in to clock in. Doing so allows the registration of POS orders. If users are not clocked in, they cannot make POS orders. Likewise, they must click Work Out to clock out at the end of the session.




Avvertimento

If you configure a POS to work with a FDM, you cannot use it again without it.

### Fiscal Data Module (FDM)¶

An FDM, or **black box** , is a government-certified device that works together with the Point of Sale application and saves your POS orders information. Concretely, a **hash** (unique code) is generated for each POS order and added to its receipt. This allows the government to verify that all revenue is declared.

Avvertimento

Only the FDM from **Boîtenoire.be** with the [FDM certificate number BMC04](https://www.systemedecaisseenregistreuse.be/fr/systemes-certifies#FDM%20certifiés) is supported by Odoo. [Contact the manufacturer (GCV BMC)](https://www.xn--botenoire-hna4u.be/contact) to order one.

#### Configurazione¶

Before setting up your database to work with an FDM, ensure you have the following hardware:

  * a **Boîtenoire.be** (certificate number BMC04) FDM;

  * an RS-232 serial null modem cable per FDM;

  * an RS-232 serial-to-USB adapter per FDM;

  * an IoT Box (one IoT box per FDM); and

  * a receipt printer.




##### Black box module¶

As a pre-requisite, [activate](../../general/apps_modules.html#general-install) the `Belgian Registered Cash Register` module (technical name: `pos_blackbox_be`).

Once the module is activated, add your VAT number to your company information. To set it up, go to Settings ‣ Companies ‣ Update Info, and fill in the VAT field. Then, enter a national registration number for every staff member who operates the POS system. To do so, go to the Employees app and open an employee form. There, go to HR settings tab ‣ Attendance/Point of Sale, and fill in the INSZ or BIS number field.

Suggerimento

To input your information, click on your avatar, go to My Profile ‣ Preference tab, and enter your INSZ or BIS number in the designated field.

Avvertimento

You must configure the FDM directly in the production database. Utilizing it in a testing environment may result in incorrect data being stored within the FDM.

##### Box IoT¶

In order to use an FDM, you need a registered IoT Box. To register your IoT box, you must contact us through our [support contact form](https://www.odoo.com/help) and provide the following information:

  * your VAT number;

  * your company’s name, address, and legal structure; and

  * the Mac address of your IoT Box.




Once your IoT box is certified, [connect](../../general/iot/connect.html) it to your database. To verify that the IoT Box recognizes the FDM, go to the IoT homepage and scroll down the IOT Device section, which should display the FDM.

Then, add the IoT to your POS. To do so, go to Point of Sale ‣ Configuration ‣ Point of Sale, select your POS, scroll down to the Connected Device section, and enable IoT Box. Lastly, add the FMD in the Fiscal Data Module field.

Nota

To be able to use an FDM, you must at least connect one Receipt Printer.

### VAT signing card¶

When you open a POS session and make your initial transaction, you are prompted to enter the PIN provided with your VSC. The card is delivered by the FPS upon [registration](https://www.systemedecaisseenregistreuse.be/fr/enregistrement).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/belgium.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](brazil.html "Brasile") |
  * [precedente](austria.html "Austria") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Belgio


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
  *[EDI]: electronic data interchange
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