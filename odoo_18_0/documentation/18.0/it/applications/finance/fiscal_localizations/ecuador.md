# Ecuador — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](egypt.html "Egitto") |
  * [precedente](denmark.html "Danimarca") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Ecuador



# Ecuador¶

With the Ecuadorian localization, it is possible to generate electronic documents using XML, fiscal folio, electronic signature, and direct connection to tax authority SRI.

The supported documents are invoices, credit notes, debit notes, purchase liquidations, and withholdings.

The localization also includes automation to easily predict the withholding tax to be applied to each purchase invoice.

Vedi anche

  * [App Tour - Localización de Ecuador](https://www.youtube.com/watch?v=BQOXVSDeeK8)

  * [Smart Tutorial - Localización de Ecuador](https://www.odoo.com/slides/smart-tutorial-localizacion-de-ecuador-170)

  * [Documentation on e-invoicing’s legality and compliance in Ecuador](../accounting/customer_invoices/electronic_invoicing/ecuador.html)




## Glossary¶

Here are some terms that are essential to the Ecuadorian localization:

  * **SRI** : Stands for _Servicio de Rentas Internas_ , which is the government organization that enforces the payment of taxes in Ecuador.

  * **SRI certificate** : Document or digital credential issued by the _SRI_ that is crucial for compliance with Ecuadorian tax laws.

  * **EDI** : Stands for _Electronic Data Interchange_ , which refers to the electronic transmission of documents.

  * **RIMPE** : Stands for _Regimen Simplificado para Emprendedores y Negocios_ , which is the type of taxpayer qualified for SRI.




## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Ecuadorian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Ecuadorian - Accounting | `l10n_ec` | The default [fiscal localization package](../fiscal_localizations.html), adds accounting characteristics for the Ecuadorian localization, which represent the minimum configuration required for a company to operate in Ecuador according to the guidelines set by the SRI. The module’s installation automatically loads: Chart of Accounts, taxes, documents types, tax support types. Additionally, the generation of forms 103 and 104 are automatic.  
Ecuadorian Accounting EDI | `l10n_ec_edi` | Includes all the technical and functional requirements to generate and validate [Electronics Documents](../accounting/customer_invoices/electronic_invoicing.html), based on the technical documentation published by the SRI. The authorized documents are: Invoices, Credit Notes, Debit Notes, Withholdings and Purchase liquidations.  
Ecuadorian Accounting Reports | `l10n_ec_reports` | Includes all the technical and functional requirements to generate forms 103 and 104.  
Ecuador - ATS Report | `l10n_ec_reports_ats` | Includes all the technical and functional requirements to generate the ATS report XML file ready to be uploaded to the _DIMM Formularios_.  
Ecuadorian Website | `l10n_ec_website_sale` | Includes all the technical and functional requirements to generate automatic electronic invoices from a Website sale.  
Ecuadorian Point of Sale | `l10n_ec_edi_pos` | Includes all the technical and functional requirements to generate automatic electronic invoices from a POS sale.  
  
Nota

In some cases, such as when upgrading to a version with additional modules, it is possible that those modules may not be installed automatically. Any missing modules can be manually installed.

### Configure a company or individual contact¶

Vedi anche

[Configure a company or individual contact](../../essentials/contacts.html)

The following fields should be completed for localization purposes on the contact form:

  * Name: Enter the company or individual’s name.

  * Address: The Street sub-field is required to confirm electronic invoices.

  * Identification Number: For a company, enter the Ruc. For individuals, enter the Cedula or Passport number.

  * SRI Taxpayer Type: Select the contact’s SRI taxpayer type.

  * Phone: Enter the company or individual’s phone number.

  * Email: Enter the company or individual’s email. This email is used to send electronic documents, such as invoices.




Nota

The SRI Taxpayer Type indicated on the contact form determines which VAT and profit withholding taxes apply when using this contact on a vendor bill.

### Electronic documents¶

To upload information for electronic documents, go to Accounting ‣ Configuration ‣ Settings, and scroll to the Ecuadorian Localization section.

Configure the following information, starting with the Electronic Invoicing section:

  * Company legal name

  * Regime: Select whether the company is in the Regular Regime (without additional messages in the RIDE) or is qualified as in the RIMPE Regime.

  * Special Taxpayer Number: If the company is qualified as a special taxpayer, complete this field with the company’s corresponding tax contributor number.

  * Forced to Keep Accounting Books: Enable this option if needed.




Withholding section:

  * Consumables: Enter the code of the default withholding tax used when purchasing goods.

  * Services: Enter the code of the default withholding tax used when purchasing services.

  * Credit Card: Enter the code of the default withholding tax used when purchasing with credit cards.

  * Withhold Agent Number: Enter the company’s withholding agent resolution number, if applicable.




SRI Connection section:

  * Certificate file for SRI: Select the company’s SRI certificate. Click __ SRI Certificates to upload one, if necessary.

  * Use production servers: Enable this option if electronic documents are used in the production environment; leave it disabled if the testing environment is used instead.




Withholding accounts section:

  * Sales Tax Base Account: Enter the company’s sales tax base account.

  * Purchase Tax Base Account: Enter the company’s sales tax purchase account.




Importante

When using the testing environment, EDI data is sent to test servers.

Nota

  * The values entered in the Consumables and Services withholding fields are used as default values for domestic **only when** no withholdings are set up on the _SRI Taxpayer Type_.

  * The entered Credit Card withholding value is always applied when a credit or debit card SRI payment method is used.




### VAT withholding¶

Nota

This configuration applies only if the SRI recognizes the company as a withholding agent. If not, skip this step.

To configure a VAT withholding, go to Accounting ‣ Configuration ‣ Taxpayer Type SRI.

Configure the Name of the taxpayer type, the Goods VAT Withholding, and the Services VAT Withholding.

Suggerimento

If the Taxpayer Type is Rimpe, configure the Profit Withhold percentage.

### Printer points¶

_Printer points_ need to be configured for each type of electronic document used, such as customer invoices, credit notes, and debit notes.

To configure printer points, navigate to Accounting ‣ Configuration ‣ Journals.

For each electronic document, click New, and enter the following information on the journal form:

  * Journal Name: Enter in this format: `[Emission Entity]-[Emission Point] [Document Type]`, e.g., `001-001 Sales Documents`.

  * Type: Refers to the journal type; select Sales.




Once the Type is selected, complete the following fields:

  * Use Documents?: Enable this option if legal invoicing (invoices, debit/credit notes) is used, as this is the standard configuration. If not, select the option to record accounting entries unrelated to legal invoicing documents, such as receipts, tax payments, or journal entries.

  * Emission Entity: Enter the facility number.

  * Emission Point: Enter the printer point.

  * Emission address: Enter the address of the facility.




In the Journal Entries tab, under the Accounting information section, fill in the following fields:

  * Default Income Account: Enter the default income account.

  * Dedicated Credit Note Sequence: Enable this option if _credit notes_ should be generated from this printer point (i.e., the journal).

  * Dedicated Debit Note Sequence: Enable this option if _debit notes_ should be generated from this printer point (i.e., the journal).

  * Short Code: Enter a unique 5-digit code for the accounting entry sequence (e.g., VT001).




Customer invoices, credit notes, and debit notes need to use the same journal as the Emission Point, whereas the Entity Point should be unique per journal.

Finally, in the Advanced Settings tab, check the Electronic invoicing checkbox to enable sending XML/EDI invoices.

Vedi anche

[Fatturazione elettronica (EDI)](../accounting/customer_invoices/electronic_invoicing.html)

### Withholding¶

To define a _withholding journal_ , go to Accounting ‣ Configuration ‣ Journals. For each withholding journal, click New, and enter the following information:

  * Journal Name: Enter this format: `[Emission Entity]-[Emission Point] [Document Type]`, e.g.,`001-001 Withholding`.

  * Type: Refers to the journal type. Select Miscellaneous.

  * Withhold Type: Select Purchase Withhold.




Once the Type and Withhold Type are selected, complete the following fields:

  * Emission Entity: Enter the facility number.

  * Emission Point: Enter the printer point.

  * Emission address: Enter the address of the facility.




In the Journal Entries tab, under the Accounting information section, fill in the following fields:

  * Default Account: Configure the default income account.

  * Short Code: Enter a unique 5-digit code for the accounting entry sequence (e.g., `WT001`).




Finally, in the Advanced Settings tab, check the Electronic invoicing checkbox to enable sending XML/EDI invoices.

### Purchase liquidations¶

A specific journal must be created for _purchase liquidations_. Go to Accounting ‣ Configuration ‣ Journals. Click New, and enter the following information:

  * Journal Name: Enter this format: `[Emission Entity]-[Emission Point] [Document Type]`, e.g., `001-001 Purchase Liquidations`.

  * Type: Refers to the journal type. Select Purchase.




Once the Type is selected, complete the following fields:

  * Purchase Liquidations: Tick this checkbox to enable purchase liquidations.

  * Use Documents?: Enable this option if legal invoicing (invoices, debit/credit notes) is used, as this is the standard configuration. If not, select the option to record accounting entries unrelated to legal invoicing documents, such as receipts, tax payments, or journal entries.

  * Emission Entity: Enter the facility number.

  * Emission Point: Enter the printer point.

  * Emission address: Enter the address of the facility.

  * Short Code: Enter a unique 5-digit code for the accounting entry sequence (e.g., `PT001`).




Finally, in the Advanced Settings tab, check the Electronic invoicing checkbox to enable sending XML/EDI invoices.

### Configure master data¶

#### Piano dei conti¶

The [chart of accounts](../accounting/get_started/chart_of_accounts.html) is installed by default as part of the set of data included in the localization module. The accounts are mapped automatically in _Taxes_ , _Default Account Payable_ , _Default Account Receivable_.

Ecuador’s chart of accounts is based on the most updated version of the _Superintendency of Companies_ , which is grouped into several categories and is compatible with NIIF accounting.

Accounts can be added or deleted according to the company’s needs.

#### Prodotti¶

If products have any withholding taxes, they must be configured on the product form.

Go to Accounting ‣ Vendors ‣ Products. On the General Information tab, specify both Purchase Taxes and Profit Withhold.

#### Imposte¶

The localization module automatically creates and configures taxes. If new taxes need to be created, it is recommended to base them on the configuration of the existing ones.

To manage taxes, navigate to Accounting ‣ Configuration ‣ Taxes. Depending on the tax type, the following options may be required for additional configuration:

  * Tax Name: Follows a specific format depending on the tax type:

    * **For IVA (Value-Added Tax)** :

`IVA [percent] (104, [form code] [tax support code] [tax support short name])`

Example: `IVA 12% (104, RUC [tax support code] IVA)`

    * **For Income Tax Withholding codes** :

`Code ATS [percent of withhold] [withhold name]`

Example: `Code ATS 10% Retención a la Fuente`

  * Tax Support: Configure only for the IVA tax. This option is used to register purchase withholdings.

  * Code ATS: Configure only for income tax withholding codes, as it is necessary to register a withholding.




In the Definition tab:

  * Tax Grids: Configure the code of a 104 form if it is an IVA tax, and the code of a 103 form if it is an income tax withholding code.




Vedi anche

[Configuring taxes](../accounting/taxes.html)

#### Document types¶

Some accounting transactions like _customer invoices_ and _vendor bills_ are classified by _document types_. These are defined by the government fiscal authorities, which in this case is the SRI.

To access or configure document types, go to Accounting ‣ Configuration ‣ Document Types.

Each document type can have a unique sequence per journal where it is assigned. As part of the localization, the document type includes the country in which the document is applicable; also the data is created automatically when the localization module is installed.

The information required for the document types is included by default and doesn’t need to be changed.

## Workflow¶

Once a company’s database is configured, documents can be registered to enable workflows across Odoo’s applications, such as **Accounting** , **Inventory** , and **Sales**.

### Sales documents¶

#### Fatture cliente¶

Customer invoices are electronic documents that, when validated, are sent to SRI. These documents can be [created from your sales order or manually](../accounting/customer_invoices/overview.html).

They must contain the following data:

  * Journal: Select the option matching the customer invoice’s printer point.

  * Document Type: Type the document type in this format: `(01) Invoice`.

  * Payment Method (SRI): Select how the invoice will be paid.




Vedi anche

[Manage customer invoices](../accounting/customer_invoices/overview.html)

#### Customer credit note¶

The [customer credit note](../accounting/customer_invoices/credit_notes.html) is an electronic document that, when validated, is sent to SRI. A validated (posted) invoice is necessary to register a credit note.

On the invoice, click Credit note and complete the following information in the Credit note window:

  * Reason: Type the reason for the credit note.

  * Journal: Select the journal for the reversal.

  * Document Type: By default, (04) Credit Note is selected.

  * Reversal date: Set the date for the reversal.




Then, click Reverse to first review the invoice or click Reverse and Create Invoice.

Nota

When creating the first credit note, select Reverse and assign the first credit note number or by default Odoo assigns `NotCr 001-001-000000001` as the first credit note number.

Once the credit note is created, modify Product and Quantity if needed. Make sure the correct Customer, Journal, and Document Type are specified, and the products listed on the Invoice Lines tab are configured with the correct taxes.

To validate, click Confirm.

#### Customer debit note¶

The [customer debit note](../accounting/customer_invoices/credit_notes.html#accounting-credit-notes-issue-debit-note) is an electronic document that, when validated, is sent to SRI.

A validated (posted) invoice is necessary to register a debit note. Select the related invoice to issue a debit note in the Invoices list view, click __ Actions and select Create Debit Note. Then, complete the following information in the Create Debit Note window.

  * Reason: Enter the reason for the debit note.

  * Debit note date: Set the debit note date.

  * Copy lines: Select this option to register a debit note with the same lines of invoice.

  * Use Specific Journal: Select the printer point for your credit note, or leave it empty to use the same journal as the original invoice.




Then, click Create Debit Note.

The debit note amount can be changed, if desired.

#### Customer withholding¶

The Customer withholding is a non-electronic document issued by the client in order to apply a withholding to a sale.

A validated (posted) invoice is necessary to register a customer withholding. On the invoice, click Add Withhold and complete the following information in the Customer withholding window:

  * Document Number: Enter the withholding number.

  * Withhold Lines: Select the taxes that the customer is withholding.




Before validating the withholding, review that the amounts for each tax are the same as the original document.

### Purchase Documents¶

#### Fattura fornitore¶

[Vendor bills](../accounting/vendor_bills.html) are non-electronic documents issued by vendors when a company generates a purchase. Vendor bills can be created from purchase orders or manually.

Importante

A vendor bill journal must be created to create vendor bill documents.

##### Create a vendor bill journal¶

To create a new journal, go to Accounting ‣ Configuration ‣ Journals, and click New.

Then, configure the following:

  * Select Purchase as the Type.

  * **Do not** tick the Purchase Liquidations checkbox.

  * Add a Default Expense Account.




##### Configure a vendor bill¶

To configure a vendor bill, make sure also to complete the following Ecuador specific fields:

  * Document Type: Enter this document type: `(01) Invoice`.

  * Document number: Enter the document number.

  * Payment Method (SRI): Select how the vendor bill will be paid.




Importante

When creating the purchase withholding, verify that the bases (base amounts) are correct. If you need to edit the amount of the tax in the Vendor bill, click Edit. Or, from the Journal Items tab, click Edit and set the adjustment as desired.

#### Purchase liquidation¶

The _purchase liquidation_ is an electronic document that, when validated, is sent to SRI.

Companies issue them when they make a purchase but the vendor does not provide an invoice, due to one or more of the following reasons:

  * Non-residents of Ecuador provided services.

  * Foreign companies provided services without residency or facility in Ecuador.

  * Purchase of goods or services from natural persons not registered with a RUC, who cannot issue sales receipts or customer invoices.

  * Reimbursement for purchasing goods or services must be given to employees in a dependency relationship (full-time employee).

  * Members of collegiate bodies have provided services in the exercise of their function.




In these cases, a purchase liquidation journal must be created.

##### Create a purchase liquidation journal¶

To create a new journal, go to Accounting ‣ Configuration ‣ Journals, and click New.

Then, configure the following:

  * Select Purchase as the Type.

  * Tick the Purchase Liquidations checkbox.

  * Add a Default Expense Account.




##### Create a purchase liquidation¶

These types of electronic documents can be created from the _purchase order_ or manually from the _vendor bills_ form. Purchase liquidations must contain the following data:

  * Vendor: Enter the vendor’s information.

  * Journal: Select the Purchase Liquidation journal with the correct printer point.

  * Document Type: Enter this document type: `(03) Purchase Liquidation`

  * Document number: Enter the document number (sequence). This must only be entered once, and the sequence will automatically be assigned to the subsequent documents.

  * Payment Method (SRI): Select how the invoice is going to be paid.

  * Products: Specify the product with the correct taxes.




Once the information has been reviewed, validate the Purchase Liquidation.

#### Purchase withholding¶

The _Purchase withholding_ is an electronic document that, when validated, is sent to SRI.

An invoice in a validated state is necessary before registering a Purchase withholding. On the invoice, click Add Withhold and complete the following fields in the Withholding window:

  * Document number: Enter the document number (sequence). This must only be entered once, and the sequence will automatically be assigned for the next documents.

  * Withhold lines: The taxes appear automatically according to the configuration of products and vendors. Review if the taxes and tax support are correct. If not, edit and select the correct taxes and tax support.




Then, validate the Withholding.

Nota

Tax support types must be configured on the Vendor Bill. To do so, go to the tax applied on the Vendor Bill and change the Tax Support there.

A withholding tax can be divided into two or more lines, depending on whether two or more withholdings percentages apply.

Example

The system suggests a VAT withholding of 30% with tax support 01. VAT withholding of 70% can be added in a new line with the same tax support. Odoo allows it if the base total matches the Vendor Bill’s total.

### Expense reimbursement¶

Expense reimbursements apply to the following cases:

  * Individual: reimbursement to an employee for miscellaneous expenses (e.g. purchase liquidations)

  * Legal Entity: reimbursement for incurred expenses, such as representation expenses (e.g. hiring a lawyer)




To enable an expense reimbursement, make sure a purchase liquidation journal has been created for an individual or a vendor bills journal for a legal entity.

Nota

In the vendor bills journal, be sure the following necessary configurations are set for a legal entity:

  * Select Purchase as the Type.

  * **Do not** tick the Purchase Liquidations checkbox.

  * Add a Default Expense Account.




Next, to create a reimbursement, create a vendor bill using the _purchase liquidation_ or _vendor bills_ journal. On the vendor bill, configure the following fields:

  * Vendor: This field should be an employee.

  * Document Type: Verify that this field is accurately populated from the journal.

  * Payment Method (SRI): Select a payment method.

  * Reimbursement Lines tab: Click Auto Fill Invoice Lines to automatically populate the invoice lines or add the expenses line by line, and provide the following details for each expense:

    * Partner or authorization number

    * Date

    * Document Type

    * Document Number

    * Tax Base

    * Tax




Then, click Confirm Vendor Bill and Process Now. The XML and authorization number for the purchase liquidation are recorded, and the purchase withholding created from this vendor bill includes the reimbursement information.

### E-commerce¶

The ATS Report module enables the following:

  * Choose the _SRI Payment Method_ for each payment method’s configuration.

  * Customers can manually input their identification type and number during eCommerce checkout.

  * Automatically generate a valid electronic invoice for Ecuador at the end of the checkout process.




Vedi anche

[eCommerce documentation](../../websites/ecommerce.html)

#### Online payments¶

To enable online payments, add the relevant [payment provider(s)](../payment_providers.html) and configure the necessary [payment methods](../payment_providers.html#payment-providers-payment-methods). It is mandatory to set the SRI Payment Method for each method.

Nota

Adding the SRI Payment Method is necessary to correctly generate the electronic invoice from an eCommerce sale. Select a **payment method** to access its configuration menu and field.

#### Automatic invoice¶

To generate an invoice after the checkout process, navigate to Website ‣ Configuration ‣ Settings and activate the Automatic Invoice option found under the Invoicing section.

Suggerimento

The invoice’s email template can be modified from the Invoice Email Template field under the Automatic Invoice option.

Importante

The sales journal used for invoicing is the first in the sequence of priority in the Journal menu.

#### eCommerce workflow¶

##### Identification type and number¶

The client who is making a purchase will have the option to indicate their identification type and number during the checkout process. This information is required to correctly generate the electronic invoice after the checkout is completed.

Nota

Verification is done to ensure the Identification Number field is completed and has the correct number of digits. For RUC identification, 13 digits are required. For Cédula, 9 digits are required.

After finishing the checkout process, a confirmed invoice is generated, ready to be sent manually or asynchronously to the SRI.

### Point of sale electronic invoicing¶

Make sure the _Ecuadorian module for Point of Sale_ (`l10n_ec_edi_pos`) is installed to enable the following features and configurations:

  * Choose the SRI payment method in each payment method configuration.

  * Manually input the customer’s identification type and identification number when creating a new contact on _POS_.

  * Automatically generate a valid electronic invoice for Ecuador at the end of the checkout process.




#### Payment method configuration¶

To [create a payment method for a point of sale](../../sales/point_of_sale/payment_methods.html), go to Point of Sale ‣ Configuration ‣ Payment Methods. Then, set the SRI Payment Method in the payment method form.

#### Invoicing flows¶

##### Identification type and number¶

The P0S cashier can [create a new contact for a customer](../../sales/point_of_sale.html#pos-customers) who requests an invoice from an open POS session.

The _Ecuadorian Module for Point of Sale_ adds two new fields to the contact creation form: Identification Type and Tax ID.

Nota

As the identification number length differs depending on the identification type, Odoo automatically checks the Tax ID field upon saving the contact form. To manually ensure the length is correct, know that the RUC and Citizenship types require 13 and 10 digits, respectively.

##### Electronic invoice: anonymous end consumer¶

When clients do not request an electronic invoice for their purchase, Odoo automatically sets the customer as Consumidor Final and generates an electronic invoice anyway.

Nota

If the client requests a credit note due to a return of this type of purchase, the credit note should be made using the client’s real contact information. Credit notes cannot be created to _Consumidor Final_ and can be managed [directly from the POS session](../../sales/point_of_sale.html#pos-refund).

##### Electronic invoice: specific customer¶

If a customer requests an invoice for their purchase, it is possible to select or create a contact with their fiscal information. This ensures the invoice is generated with accurate customer details.

Nota

If the client requests a credit note due to a return of this type of purchase, the credit note and return process can be managed [directly from the POS session](../../sales/point_of_sale.html#pos-refund).

## Rapporti finanziari¶

In Ecuador, there are fiscal reports that the company presents to SRI. Odoo supports two of the main financial reports used by companies: **reports 103** and **104**.

To get these reports, go to Accounting ‣ Reporting ‣ Tax Return. Click the __ Report: icon and select `103 (EC)` or `104 (EC)`.

### Report 103¶

This report provides details on income tax withholdings in a given period and can be reported monthly or semi-annually. It includes information about base, tax amounts, and tax codes, and can be used for SRI reporting.

### Report 104¶

This report provides details on VAT tax and VAT withholding for a given period and can be generated monthly or semi-annually. It includes information about base, tax amounts, and tax codes, and can be used for SRI reporting.

### ATS report¶

[Install](../../general/apps_modules.html#general-install) the _ATS Report_ (`l10n_ec_reports_ats`) module to enable downloading the ATS report in XML format.

Nota

The Ecuadorian _ATS Report_ module depends on the previous installation of the _Accounting_ app and the _Ecuadorian EDI module_.

#### Configurazione¶

To issue electronic documents, ensure the company is configured as explained in the electronic invoice section.

In the ATS, every document generated in Odoo (invoices, vendor bills, sales and purchases withholdings, credit notes, and debit notes) will be included.

##### Fatture fornitore¶

When generating a vendor bill, it is necessary to register the authorization number from the vendor’s invoice. To do so, go to Accounting ‣ Vendors ‣ Bills and select the bill. Then, enter the number from the vendor’s invoice in the Authorization Number field.

##### Credit and debit notes¶

When generating a credit note or debit note manually or through an import, it is necessary to link this note to the sales invoice that is being modified by it.

Nota

Remember to add all required information to the documents before downloading the ATS file. For example, add the _Authorization Number_ and the _SRI Payment Method_ on documents, when needed.

#### XML generation¶

To generate the ATS report, go to Accounting ‣ Reporting ‣ Tax Return. Choose a time period for the desired ATS report, then click ATS.

The downloaded XML file is ready to be uploaded to _DIMM Formularios_.

Nota

When downloading the ATS report, Odoo generates a warning pop-up alerting the user if a document(s) has missing or incorrect data. Nevertheless, the XML file can still be downloaded.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/ecuador.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](egypt.html "Egitto") |
  * [precedente](denmark.html "Danimarca") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Ecuador


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
  *[POS]: point of sale
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
  *[SII]: Fornitura Immediata di Informazioni
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
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
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