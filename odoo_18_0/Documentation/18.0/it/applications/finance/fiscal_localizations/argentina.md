# Argentina — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](australia.html "Australia") |
  * [precedente](../fiscal_localizations.html "Fiscal localizations") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Argentina



# Argentina¶

## Webinars¶

Below you can find videos with a general description of the localization, and how to configure it.

  * [Webinar - Localización de Argentina](https://www.youtube.com/watch?v=_H1HbU-wKVg).

  * [eCommerce - Localización de Argentina](https://www.youtube.com/watch?v=5gUi2WWfRuI).




Vedi anche

  * [Smart Tutorial - Localización de Argentina](https://www.odoo.com/slides/smart-tutorial-localizacion-de-argentina-130)

  * [Documentation on e-invoicing’s legality and compliance in Argentina](../accounting/customer_invoices/electronic_invoicing/argentina.html)




## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Argentinean localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Argentina - Accounting | `l10n_ar` | Default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages), which represents the minimal configuration to operate in Argentina under the AFIP regulations and guidelines.  
Argentinean Accounting Reports | `l10n_ar_reports` | VAT Book report and VAT summary report.  
Argentinean Electronic Invoicing | `l10n_ar_edi` | Includes all technical and functional requirements to generate electronic invoices via web service, based on the AFIP regulations.  
Argentinean eCommerce | `l10n_ar_website_sale` | (optional) Allows the user to see Identification Type and AFIP Responsibility in the eCommerce checkout form in order to create electronic invoices.  
Argentina - Payment Withholdings | `l10n_ar_withholding` | Allows registering withholdings during the payment of an invoice.  
  
### Configure your company¶

Once the localization modules are installed, the first step is to set up the company’s data. In addition to the basic information, a key field to fill in is the AFIP Responsibility Type, which represents the fiscal obligation and structure of the company.

### Piano dei conti¶

In Accounting, there are three different Chart of Accounts packages to choose from. They are based on a company’s AFIP responsibility type, and consider the difference between companies that do not require as many accounts as the companies that have more complex fiscal requirements:

  * Monotributista (227 accounts);

  * IVA Exento (290 accounts);

  * Responsable Inscripto (298 Accounts).




### Configure master data¶

#### Electronic Invoice Credentials¶

##### Ambiente¶

The AFIP infrastructure is replicated in two separate environments, **testing** and **production**.

Testing is provided so that the companies can test their databases until they are ready to move into the **Production** environment. As these two environments are completely isolated from each other, the digital certificates of one instance are not valid in the other one.

To select a database environment, go to Accounting ‣ Settings ‣ Argentinean Localization and choose either Prueba (Testing) or Produccion (Production).

##### AFIP certificates¶

The electronic invoice and other AFIP services work with Web Services (WS) provided by the AFIP.

In order to enable communication with the AFIP, the first step is to request a Digital Certificate if you do not have one already.

  1. Generate Certificate Sign Request (Odoo). When this option is selected, a file with extension `.csr` (certificate signing request) is generated to be used in the AFIP portal to request the certificate.

  2. Generate Certificate (AFIP). Access the AFIP portal and follow the instructions described in [this document](https://drive.google.com/file/d/17OKX2lNWd1bjUt3NxfqcCKBkBh-Xlpo-/view) to get a certificate.

  3. Upload Certificate and Private Key (Odoo). Once the certificate is generated, upload it to Odoo using the Pencil icon next to the field Certificado and select the corresponding file.




Suggerimento

In case you need to configure the Homologation Certificate, please refer to the AFIP official documentation: [Homologation Certificate](http://www.afip.gob.ar/ws/documentacion/certificados.asp). Furthermore, Odoo allows the user to test electronic invoicing locally without a Homologation Certificate. The following message will be in the chatter when testing locally:

#### Partner¶

##### Identification type and VAT¶

As part of the Argentinean localization, document types defined by the AFIP are now available in the **Partner form**. Information is essential for most transactions. There are six Identification Types available by default, as well as 32 inactive types.

Nota

The complete list of Identification Types defined by the AFIP is included in Odoo, but only the common ones are active.

##### AFIP responsibility type¶

In Argentina, the document type and corresponding transactions associated with customers and vendors is defined by the AFIP Responsibility type. This field should be defined in the **Partner form**.

#### Imposte¶

As part of the localization module, the taxes are created automatically with their related financial account and configuration, e.g., 73 taxes for Responsable Inscripto.

##### Taxes types¶

Argentina has several tax types, the most common ones are:

  * VAT: this is the regular VAT and can have various percentages;

  * Perception: advance payment of a tax that is applied on invoices;

  * Retention: advance payment of a tax that is applied on payments.




##### Special taxes¶

Some Argentinean taxes are not commonly used for all companies, and those less common options are labeled as inactive in Odoo by default. Before creating a new tax, be sure to check if that tax is not already included as inactive.

#### Document types¶

In some Latin American countries, like Argentina, some accounting transactions such as invoices and vendor bills are classified by document types defined by the governmental fiscal authorities. In Argentina, the [AFIP](https://www.afip.gob.ar/) is the governmental fiscal authority that defines such transactions.

The document type is an essential piece of information that needs to be clearly displayed in printed reports, invoices, and journal entries that list account moves.

Each document type can have a unique sequence per journal where it is assigned. As part of the localization, the document type includes the country in which the document is applicable (this data is created automatically when the localization module is installed).

The information required for the Document Types is included by default so the user does not need to fill anything on this view:

Nota

There are several Document Types types that are inactive by default, but can be activated as needed.

##### Lettere¶

For Argentina, the Document Types include a letter that helps indicate the type of transaction or operation. For example, when an invoice is related to a(n):

  * B2B transaction, a document type A must be used;

  * B2C transaction, a document type B must be used;

  * Exportation Transaction, a document type E must be used.




The documents included in the localization already have the proper letter associated with each Document Type, so there is no further configuration necessary.

##### Use on invoices¶

The Document Type on each transaction will be determined by:

  * The journal entry related to the invoice (if the journal uses documents);

  * The onditions applied based on the type of issuer and receiver (e.g., the type of fiscal regime of the buyer and the type of fiscal regime of the vendor).




### Registri¶

In the Argentinean localization, the journal can have a different approach depending on its usage and internal type. To configure journals, go to Accounting ‣ Configuration ‣ Journals.

For sales and purchase journals, it’s possible to activate the option Use Documents, which enables a list of Document Types that can be related to the invoices and vendor bills. For more detail on invoices, please refer to the section 2.3 document types.

If the sales or purchase journals do not have the Use Documents option activated, they will not be able to generate fiscal invoices, meaning, their use case will be mostly limited to monitoring account moves related to internal control processes.

#### AFIP information (also known as AFIP Point of Sale)¶

The AFIP POS System is a field only visible for the **Sales** journals and defines the type of AFIP POS that will be used to manage the transactions for which the journal is created.

The AFIP POS defines the following:

  1. the sequences of document types related to the web service;

  2. the structure and data of the electronic invoice file.




##### Web services¶

**Web services** help generate invoices for different purposes. Below are a few options to choose from:

  * wsfev1: Electronic Invoice: is the most common service, which is used to generate invoices for document types A, B, C, M with no detail per item;

  * wsbfev1: Electronic Fiscal Bond: is for those who invoice capital goods and wish to access the benefit of the Electronic Tax Bonds granted by the Ministry of Economy. For more details go to: [Fiscal Bond](https://www.argentina.gob.ar/acceder-un-bono-por-fabricar-bienes-de-capital);

  * wsfexv1: Electronic Exportation Invoice: is used to generate invoices for international customers and transactions that involve exportation processes, the document type related is type «E».




Here are some useful fields to know when working with web services:

  * AFIP POS Number: is the number configured in the AFIP to identify the operations related to this AFIP POS;

  * AFIP POS Address: is the field related to the commercial address registered for the POS, which is usually the same address as the company. For example, if a company has multiple stores (fiscal locations) then the AFIP will require the company to have one AFIP POS per location. This location will be printed in the invoice report;

  * Unified Book: when the AFIP POS System is Preimpresa, then the document types (applicable to the journal) with the same letter will share the same sequence. For example:

    * Invoice: FA-A 0001-00000002;

    * Credit Note: NC-A 0001-00000003;

    * Debit Note: ND-A 0001-00000004.




#### Sequenze¶

For the first invoice, Odoo synchronizes with the AFIP automatically and displays the last sequence used.

Nota

When creating Purchase Journals, it’s possible to define whether they are related to document types or not. In the case where the option to use documents is selected, there would be no need to manually associate the document type sequences, since the document number is provided by the vendor.

## Usage and testing¶

### Fattura¶

The information below applies to invoice creation once the partners and journals are created and properly configured.

#### Document type assignation¶

When the partner is selected, the Document Type field will be filled in automatically based on the AFIP document type:

  * **Invoice for a customer IVA Responsable Inscripto, prefix A** is the type of document that shows all the taxes in detail along with the customer’s information.

  * **Invoice for an end customer, prefix B** is the type of document that does not detail the taxes, since the taxes are included in the total amount.

  * **Exportation Invoice, prefix E** is the type of document used when exporting goods that shows the incoterm.




Even though some invoices use the same journal, the prefix and sequence are given by the Document Type field.

The most common Document Type will be defined automatically for the different combinations of AFIP responsibility type but it can be updated manually by the user before confirming the invoice.

#### Electronic invoice elements¶

When using electronic invoices, if all the information is correct then the invoice is posted in the standard way unless there is an error that needs to be addressed. When error messages pop up, they indicate both the issue that needs attention along with a proposed solution. If an error persists, the invoice remains in draft until the issue is resolved.

Once the invoice is posted, the information related to the AFIP validation and status is displayed in the AFIP tab, including:

  * AFIP Autorisation: CAE number;

  * Expiration Date: deadline to deliver the invoice to the customers (normally 10 days after the CAE is generated);

  * Result: indicates if the invoice has been Aceptado en AFIP and/or Aceptado con Observaciones.




#### Invoice taxes¶

Based on the AFIP Responsibility type, the VAT tax can apply differently on the PDF report:

  * A. Tax excluded: in this case the taxed amount needs to be clearly identified in the report. This condition applies when the customer has the following AFIP Responsibility type of **Responsable Inscripto** ;

  * B. Tax amount included: this means that the taxed amount is included as part of the product price, subtotal, and totals. This condition applies when the customer has the following AFIP Responsibility types:

    * IVA Sujeto Exento;

    * Consumidor Final;

    * Responsable Monotributo;

    * IVA liberado.




#### Special use cases¶

##### Invoices for services¶

For electronic invoices that include Services, the AFIP requires to report the service starting and ending date, this information can be filled in the tab Other Info.

If the dates are not selected manually before the invoice is validated, the values will be filled automatically with the first and last day of the invoice’s month.

##### Exportation invoices¶

Invoices related to Exportation Transactions require that a journal uses the AFIP POS System **Expo Voucher - Web Service** so that the proper document type(s) can be associated.

When the customer selected in the invoice is configured with an AFIP responsibility type Cliente / Proveedor del Exterior \- Ley N° 19.640, Odoo automatically assigns the:

  * Journal related to the exportation Web Service;

  * Exportation document type;

  * Fiscal position: Compras/Ventas al exterior;

  * Concepto AFIP: Products / Definitive export of goods;

  * Exempt Taxes.




Nota

The Exportation Documents require Incoterms to be enabled and configured, which can be found in Other Info ‣ Accounting.

##### Fiscal bond¶

The Electronic Fiscal Bond is used for those who invoice capital goods and wish to access the benefit of the Electronic Tax Bonds granted by the Ministry of Economy.

For these transactions, it is important to consider the following requirements:

  * Currency (according to the parameter table) and invoice quotation;

  * Taxes;

  * Zone;

  * Detail each item;

    * Code according to the Common Nomenclator of Mercosur (NCM);

    * Complete description;

    * Unit Net Price;

    * Quantity;

    * Unit of measurement;

    * Bonus;

    * VAT rate.




##### Electronic credit invoice MiPyme (FCE)¶

For SME invoices, there are several document types that are classified as **MiPyME** , which are also known as **Electronic Credit Invoice** (or **FCE** in Spanish). This classification develops a mechanism that improves the financing conditions for small and medium-sized businesses, and allows them to increase their productivity, through the early collection of credits and receivables issued to their clients and/or vendors.

For these transactions it’s important to consider the following requirements:

  * specific document types (201, 202, 206, etc);

  * the emitter should be eligible by the AFIP to MiPyME transactions;

  * the amount should be bigger than 100,000 ARS;

  * A bank account type CBU must be related to the emisor, otherwise the invoice cannot be validated, having an error message such as the following.




To set up the Transmission Mode, go to settings and select either SDC or ADC.

To change the Transmission Mode for a specific invoice, go to the Other Info tab and change it before confirming.

Nota

Changing the Transmission Mode will not change the mode selected in Settings.

When creating a Credit/Debit note related to a FCE document:

  * use the Credit and Debit Note buttons, so all the information from the invoice is transferred to the new Credit and Debit Note;

  * the document letter should be the same as than the originator document (either A or B);

  * the same currency as the source document must be used. When using a secondary currency there is an exchange difference if the currency rate is different between the emission day and the payment date. It is possible to create a credit/debit note to decrease/increase the amount to pay in ARS.




When creating a Credit Note we can have two scenarios:

  1. the FCE is rejected so the Credit Note should have the field FCE, is Cancellation? as _True_ ; or;

  2. the Credit Note, is created to annulate the FCE document, in this case the field FCE, is Cancellation? must be _empty_ (false).




#### Invoice printed report¶

The PDF Report related to electronic invoices that have been validated by the AFIP includes a barcode at the bottom of the format which represents the CAE number. The expiration date is also displayed as it is a legal requirement.

#### Troubleshooting and auditing¶

For auditing and troubleshooting purposes, it is possible to obtain detailed information of an invoice number that has been previously sent to the AFIP. To retrieve this information, activate the [developer mode](../../general/developer_mode.html#developer-mode), then go to the Accounting menu and click on the button Consult Invoice button in AFIP.

It is also possible to retrieve the last number used in AFIP for a specific document type and POS Number as a reference for any possible issues on the sequence synchronization between Odoo and AFIP.

### Fatture fornitore¶

Based on the purchase journal selected for the vendor bill, the Document Type is now a required field. This value is auto-populated based on the AFIP Responsibility type of Issuer and Customer, but the value can be changed if necessary.

The Document Number field needs to be registered manually and the format will be validated automatically. However, in case the format is invalid, a user error will be displayed indicating the correct format that is expected.

The vendor bill number is structured in the same way as the customer invoices, excepted that the document sequence is entered by the user using the following format: _Document Prefix - Letter - Document Number_.

#### Validate vendor bill number in AFIP¶

As most companies have internal controls to verify that the vendor bill is related to an AFIP valid document, an automatic validation can be set in Accounting ‣ Settings ‣ Argentinean Localization ‣ Validate document in the AFIP, considering the following levels:

  * Not available: the verification is not done (this is the default value);

  * Available: the verification is done. In case the number is not valid, it only displays a warning but still allows the vendor bill to be posted;

  * Required: the verification is done, and it does not allow the user to post the vendor bill if the document number is not valid.




##### Validate vendor bills in Odoo¶

With the vendor validation settings enabled, a new button shows up on the vendor bills inside of Odoo, labeled Verify on AFIP, which is located next to the AFIP Authorization code field.

In case the vendor bill cannot be validated in AFIP, a value of Rejected will be displayed on the dashboard and the details of the invalidation will be added to the chatter.

#### Special use cases¶

##### Untaxed concepts¶

There are some transactions that include items that are not a part of the VAT base amount, such as fuel and gasoline invoices.

The vendor bill will be registered using one item for each product that is part of the VAT base amount, and an additional item to register the amount of the exempt concept.

##### Perception taxes¶

The vendor bill will be registered using one item for each product that is part of the VAT base amount, and the perception tax can be added in any of the product lines. As a result, there will be one tax group for the VAT and another for the perception. The perception default value is always 0.10.

To edit the VAT perception and set the correct amount, you should use the Pencil icon that is the next to the Perception amount. After the VAT perception amount has been set, the invoice can then be validated.

### Withholding management¶

The Argentinean fiscal localization module is already loaded with the necessary withholdings records, which can be seen by navigating to Accounting app ‣ Configuration ‣ Taxes and removing the default Sale or Purchase filter. To verify these records, the **Argentina Payment Withholdings** (`l10n_ar_withholding`) module must be [installed](../../general/apps_modules.html#general-install):

Journal entries are _not_ created when payments are posted unless [outstanding accounts](../accounting/bank.html#accounting-bank-outstanding-accounts) are set up. Thus, for this feature to work properly, it is important to verify that _all_ payment methods within the bank journals have an outstanding payment and receipt account set.

This configuration is crucial for the proper accounting of withholding transactions with clients and vendors.

Nota

In Argentina, withholdings represent the cancellation of a specific portion of the total debt owed to a supplier or a reduction in the total payment to be collected from a customer. Therefore, one or multiple withholdings can be recorded for each payment applied to an invoice.

#### Configurazione¶

While Odoo already creates most of the required withholdings inside the Taxes menu, in several cases, it is necessary to apply or modify certain configurations to correctly calculate the withholding amount on vendor payments. The following withholding types are available:

  * Earnings

  * Earnings Scale

  * IIBB Total Amount

  * IIBB Non-Taxable




##### Guadagni¶

For Earnings withholdings, Odoo already has a record for each regime group, which is stated under the name of the tax and the AFIP code.

Each of these records are ready to be used. As a good practice, the configuration should be double checked to make sure the configuration is updated and well-applied. The fields to validate are:

  * Amount: This is the percentage of the total payment amount which is withheld.

  * Non-Taxable Amount: Up to this amount, the withholding does not apply.

  * Minimum Withholding: If the calculated withholding amount is smaller than this value, the total withholding amount is set to `0.0`.

  * Withholding Sequence: This field helps to automate the capture of a withholding number under the payment line. If this field is not set, a number is manually captured while adding a withholding to a payment.




##### Earnings Scale¶

In this particular case, a percentage does not need to be set. Instead, this withholding is calculated based on the value of the Scale field.

To view, modify, or create new scales, navigate to Accounting app ‣ Configuration ‣ Earnings Scale. By default, the Argentinian localization is preconfigured with two main scales. However, scales should be created and updated as necessary to suit a business’s needs.

Nota

Earnings scales are cumulative, which means that Odoo keeps track of the different records created for a bill and automatically calculates the proper withholding amount.

##### IIBB Total Amount¶

In this case, the necessary records related to the applicable province need to be created. The withholding amount is calculated based on the percentage Amount set on the tax configuration. Since Odoo does not automatically synchronize the percentages applicable to each province, this information needs to be manually updated.

The recommendation, in this case, is to always duplicate and apply the different configurations for each record to safeguard any technical configurations that allow the proper calculation and accounting of the withholding.

##### IIBB Untaxed¶

The configuration of non-taxable gross income withholdings is very similar to that of a total amount withholding, so the percentage Amount in each of the records needs to be maintained. However, Odoo comes preconfigured with several records that apply to different provinces. The difference, in this case, is that it is not necessary to establish a non-taxable amount or minimum withholding for this record type.

#### Partner withholding assignation¶

Once the proper configuration is set on each possible withholding for partners, the applicable withholdings need to be assigned to each contact. To do this, open the Contacts app and select the desired partner. In the Accounting tab, find the Purchase Withholdings table.

By using the additional fields From Date and To Date, the applicability of multiple withholdings can be automated across different date ranges. The ref field allows you to apply an internal control number to each withholding line, which is just for internal reference, so it does not affect any transactions and is not visible on them. These fields are accessible from the __(adjust settings) menu.

  * From Date: the start of the withholding date range.

  * To Date: the end of the withholding date range.

  * ref: apply an internal control number to each withholding line that is only visible for internal reference and does not affect any transactions.




#### Automatic withholding calculation and application per payment¶

By applying new payments to vendor bills, Odoo automatically applies and calculates the proper withholding into the payment. Based on the record’s configuration, it may be necessary to use a reference number for each withholding line.

More withholdings can be added, or computed withholdings can be edited if necessary.

Importante

The total amount of the debt to be canceled is the total amount of the payment. However, Odoo still captures the net amount (i.e. the amount to be reconciled with the bank), which will be represented as the payment amount after the withholding application.

### Check management¶

To install the _Third Party and Deferred/Electronic Checks Management_ module, go to Apps and search for the module by its technical name `l10n_latam_check` and click the Activate button.

This module enables the required configuration for journals and payments to:

  * Create, manage, and control your different types of checks

  * Optimize the management of _own checks_ and _third party checks_

  * Have an easy and effective way to manage expiration dates from your own and third party checks




Once all the configurations are made for the Argentinian electronic invoice flow, it is also needed to complete certain configurations for the own checks and the third party checks flows.

#### Own checks¶

Configure the bank journal used to create your own checks by going to Accounting ‣ Configuration ‣ Journals, selecting the bank journal, and opening the Outgoing Payments tab.

  * Checks should be available as a Payment Method. If not, click Add a line and type `Checks` under Payment Method to add them

  * Enable the Use electronic and deferred checks setting.




Nota

This last configuration **disables** the printing ability but enables to:

  * Enter check numbers manually

  * Adds a field to allocate the payment date of the check




##### Management of own checks¶

Own checks can be created directly from the vendor bill. For this process, click on the Register Payment button.

On the payment registration modal, select the bank journal from which the payment is to be made and set the Check Cash-In Date, and the Amount.

Nota

To manage current checks, the Check Cash-In Date field must be left blank or filled in with the current date. To manage deferred checks, the Check Cash-In Date must be set in the future.

To manage your existing own checks, navigate to Accounting ‣ Vendors ‣ Own Checks. This window shows critical information such as the dates when checks need to be paid, the total quantity of checks, and the total amount paid in checks.

It is important to note that the list is pre-filtered by checks that are still _not reconciled_ with a bank statement - that were not yet debited from the bank - which can be verified with the Is Matched with a Bank Statement field. If you want to see all of your own checks, delete the No Bank Matching filter by clicking on the X symbol.

##### Cancel an own check¶

To cancel an own check created in Odoo, navigate to Accounting ‣ Vendors ‣ Own Checks and select the check to be cancelled, then click on the Void Check button. This will break the reconciliation with the vendor bills and the bank statements and leave the check in a **cancelled** state.

#### Third party checks¶

In order to register payments using third party checks, two specific journals need to be configured. To do so, navigate to Accounting ‣ Configuration ‣ Journals and create two new journals:

  * `Third Party Checks`

  * `Rejected Third Party Checks`




Nota

You can manually create more journals if you have multiple points of sale and need journals for those.

To create the _Third Party Checks_ journal, click the New button and configure the following:

  * Type `Third Party Checks` as the Journal Name

  * Select Cash as Type

  * In the Journal Entries tab, set Cash Account: to `1.1.1.02.010 Cheques de Terceros`, input a Short Code of your choice, and select a Currency




The available payment methods are listed in the _payments_ tabs:

  * For new incoming third party checks, go to Incoming Payments tab ‣ Add a line and select New Third Party Checks. This method is used to create _new_ third party checks.

  * For incoming and outgoing existing third party checks, go to Incoming Payments tab ‣ Add a line and select Existing Third Party Checks. Repeat the same step for the Outgoing Payments tab. This method is used to receive and/or pay vendor bills using already _existing_ checks, as well as for internal transfers.




Suggerimento

You can delete pre-existing payment methods appearing by default when configuring the third party checks journals.

The _Rejected Third Party Checks_ journal also needs to be created and/or configured. This journal is used to manage rejected third party checks and can be utilized to send checks rejected at the moment of collection or when coming from vendors when rejected.

To create the _Rejected Third Party Checks_ journal, click the New button and configure the following:

  * Type `Rejected Third Party Checks` as the Journal Name

  * Select Cash as Type

  * In the Journal Entries tab, set Cash Account: to `1.1.1.01.002 Rejected Third Party Checks`, input a Short Code of your choice, and select a Currency




Use the same payment methods as the _Third Party Checks_ journal.

##### New third party checks¶

To register a _new_ third party check for a customer invoice, click the Register Payment button. In the pop-up window, you must select Third Party Checks as journal for the payment registration.

Select New Third Party Checks as Payment Method, and fill in the Check Number, Payment Date, and Check Bank. Optionally, you can manually add the Check Issuer Vat, but this is automatically filled by the customer’s VAT number related to the invoice.

##### Existing third party checks¶

To pay a vendor bill with an _existing_ check, click the Register Payment button. In the pop-up window, you must select Third Party Checks as journal for the payment registration.

Select Existing Third Party Checks as Payment Method, and select a check from the Check field. The field shows all **available existing checks** to be used as payment for vendor bills.

When an **existing third party check** is used, you can review the operations related to it. For example, you can see if a third party check made to pay a customer invoice was later used as an existing third party check to pay a vendor bill.

To do so, either go to Accounting ‣ Customers ‣ Third Party Checks or Accounting ‣ Vendors ‣ Own Checks depending on the case, and click on a check. In the Check Current Journal field, click on => Check Operations to bring up the check’s history and movements.

The menu also displays critical information related to these operations, such as:

  * The Payment Type, allowing to classify whether it is a payment _sent_ to a vendor or a payment _received_ from a customer

  * The Journal in which the check is currently registered

  * The **partner** associated with the operation (either customer or vendor).




### Ecommerce electronic invoicing¶

[Install](../../general/apps_modules.html#general-install) the _Argentinian eCommerce_ (`l10n_ar_website_sale`) module to enable the following features and configurations:

  * Clients being able to create online accounts for eCommerce purposes.

  * Support for required fiscal fields in the eCommerce application.

  * Receive payments for sale orders online.

  * Generate electronic documents from the eCommerce application.




#### Configurazione¶

Once all of the configurations are made for the Argentinian electronic invoice flow, it is also necessary to complete certain configurations to integrate the eCommerce flow.

##### Client account registration¶

To configure your website for client accounts, follow the instructions in the [checkout](../../websites/ecommerce/checkout.html) documentation.

##### Automatic invoice¶

Configure your website to generate electronic documents in the sales process by navigating to Website ‣ Configuration ‣ Settings and activating the Automatic Invoice feature in the Invoicing section to automatically generate the required electronic documents when the online payment is confirmed.

Since an online payment needs to be confirmed for the Automatic Invoice feature to generate the document, a [payment provider](../payment_providers.html) **must** be configured for the related website.

##### Prodotti¶

To allow your products to be invoiced when an online payment is confirmed, navigate to the desired product from Website ‣ eCommerce ‣ Products. In the General Information tab, set the Invoicing Policy to Ordered quantities and define the desired Customer Taxes.

#### Invoicing flow for eCommerce¶

Once the configurations mentioned above are all set, clients can complete the following required steps in the _Argentinian eCommerce_ flow to input fiscal fields in the checkout process.

Fiscal fields are available for input in the checkout process once the Country field is set as `Argentina`. Inputting the fiscal data enables the purchase to conclude in the corresponding electronic document.

When the client makes a successful purchase and payment, the necessary invoice is generated with the corresponding layout and fiscal stamps stated in the Invoice printed report.

Vedi anche

[Client account creation](../../websites/ecommerce/checkout.html)

### Liquidity product direct sales¶

Liquidity product direct sales are used for sales involving third parties. For such sales, the seller and the proprietary company of the goods can each register their corresponding sales and purchases.

Nota

[Install](../../general/apps_modules.html#general-install) the _Argentinian Electronic Invoicing_ module (`l10n_ar_edi`) to use this feature.

#### Configurazione¶

##### Purchase journal¶

A purchase journal is needed to generate an electronic vendor bill with a document type _Liquidity Product_. This journal needs to be synchronized with the AFIP as it will be used to generate the liquidity product electronic document.

To modify the existing purchase journal or create a new one, navigate to Accounting ‣ Configuration ‣ Journals. Then, select the existing purchase journal or click the New button, and fill in the following required information:

  * Type: select Purchase.

  * Use Documents: check this field to to be able select the electronic document type.

  * Is AFIP POS: check this field to be able to generate electronic documents.

  * AFIP POS System: select Electronic Invoice - Web Service from the drop-down menu in order to send the electronic document to AFIP via web service.

  * AFIP POS Number: is the number configured in the AFIP to identify the operations related to this AFIP POS.

  * AFIP POS Address: is the field related to the commercial address registered for the POS, which is usually the same address as the company. For example, if a company has multiple stores (fiscal locations) then the AFIP will require the company to have one AFIP POS per location. This location will be printed in the invoice report.




##### Sales journal¶

A sales journal is needed to register the invoice when a product is sold to a third party that will then sell the same product. This journal will not be synced with AFIP as the invoice will not be electronic.

To modify the existing sales journal or create a new one, navigate to Accounting ‣ Configuration ‣ Journals. Then, selecting the sales journal or click the New button, and fill in the following required information:

  * Type: select Sales.

  * Use Documents: check this field on the journal to select the electronic document type (in this case the electronic invoice).




#### Invoicing flow¶

Once the configurations are all set, the _Liquidity Product Vendor Bill_ will be generated by the company that is selling the product on behalf of another party. For example, a distributor of a specific product.

## Report¶

As part of the localization installation, financial reporting for Argentina is available in the Accounting dashboard. To access these reports, navigate to Accounting ‣ Reporting ‣ Argentinean Statements.

To access the VAT book report, go to Accounting ‣ Reporting ‣ Tax Report, click the __( book), and select Argentinean VAT book (AR).

Nota

The VAT book report can be exported as a `.zip` file by selecting it in the dropdown menu in the top-left corner.

### VAT summary¶

This pivot table is designed to check the monthly VAT totals. This report is for internal use and is not sent to the AFIP.

### IIBB - Sales by jurisdiction¶

This pivot table allows you to validate the gross income in each jurisdiction. It serves as an affidavit for the corresponding taxes due but is not submitted to the AFIP.

### IIBB - Purchases by jurisdiction¶

This pivot table allows you to validate the gross purchases in each jurisdiction. It serves as an affidavit for the corresponding taxes due but is not submitted to the AFIP.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/argentina.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](australia.html "Australia") |
  * [precedente](../fiscal_localizations.html "Fiscal localizations") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Argentina


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
  *[FBM]: Fulfilled by Merchant
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
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: fornitori autorizzati
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria