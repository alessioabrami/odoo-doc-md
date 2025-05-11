# Costi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expenses/approve_expenses.html "Approve expenses") |
  * [precedente](accounting/reporting/year_end.html "Year-end closing") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Costi



# Costi¶

Odoo **Expenses** streamlines the management of expenses. After an employee submits their expenses in Odoo, they are reviewed by management and accounting teams. Once approved, payments can then be processed, and disbursed back to the employee for reimbursement.

Vedi anche

[Odoo Expenses: product page](https://www.odoo.com/app/expenses)

## Set expense categories¶

The first step to track expenses is to configure the different types of expenses for the company (managed as _expense categories_ in Odoo). Each category can be as specific or generalized as needed. Go to Expenses app ‣ Configuration ‣ Expense Categories to view the current expensable categories in a default list view.

To create a new expense category, click New. A product form will appear, with the description field labeled Product Name.

Nota

Expense categories are managed like products in Odoo. The expense category form follows the standard product form in Odoo, and the information entered is similar. Expense products will be referred to as expense categories throughout this document since the main menu refers to these as Expense Categories.

Only two fields are required, the Product Name and the Unit of Measure. Enter the Product Name in the field, and select the Unit of Measure from the drop-down menu (most products will be set to Units).

Suggerimento

The _Sales_ app is where specification on the units of measure are created and edited (e.g. units, miles, nights, etc.). Go to Sales app ‣ Configuration ‣ Settings and ensure `Units of Measure` is enabled in the `Product Catalog` section. Click on the Units of Measure internal link to [view, create, and edit the units of measure](../inventory_and_mrp/inventory/product_management/configure/uom.html).

The Cost field on the product form is populated with a value of `0.00` by default. When a specific expense should always be reimbursed for a particular price, enter that amount in the Cost field. Otherwise, leave the Cost set to `0.00`, and employees will report the actual cost when submitting an expense report.

Nota

The Cost field is always visible on the expense category form, but the Sales Price field is _only_ visible if the Sales Price is selected under the Re-Invoice Expenses section. Otherwise, the Sales Price field is hidden.

Example

Here are some examples for when to set a specific Cost on a product vs. leaving the Cost at `0.00`:

  * **Meals** : set the Cost to `0.00`. When an employee logs an expense for a meal, they enter the actual amount of the bill and will be reimbursed for that amount. An expense for a meal costing $95.23 would equal a reimbursement for $95.23.

  * **Mileage** : set the Cost to `0.30`. When an employee logs an expense for «mileage», they enter the number of miles driven in the Quantity field, and are reimbursed 0.30 per mile they entered. An expense for 100 miles would equal a reimbursement for $30.00.

  * **Monthly Parking** : set the Cost to `75.00`. When an employee logs an expense for «monthly parking», the reimbursement would be for $75.00.

  * **Expenses** : set the Cost to `0.00`. When an employee logs an expense that is not a meal, mileage, or monthly parking, they use the generic Expenses product. An expense for a laptop costing $350.00 would be logged as an Expenses product, and the reimbursement would be for $350.00.




Select an Expense Account if using the Odoo _Accounting_ app. It is recommended to check with the accounting department to determine the correct account to reference in this field as it will affect reports.

Set a tax on each product in the Vendor Taxes and Customer Taxes fields, if applicable. It is considered good practice to use a tax that is configured with [Tax Included in Price](accounting/taxes.html#taxes-included-in-price). Taxes will be automatically configured if this is set.

Vedi anche

  * [Log expenses](expenses/log_expenses.html)

  * [Expense reports](expenses/expense_reports.html)

  * [Registra spese](expenses/post_expenses.html)

  * [Reimburse employees](expenses/reimburse.html)

  * [Re-invoice expenses](expenses/reinvoice_expenses.html)




  * [Approve expenses](expenses/approve_expenses.html)
  * [Log expenses](expenses/log_expenses.html)
  * [Expense reports](expenses/expense_reports.html)
  * [Registra spese](expenses/post_expenses.html)
  * [Reimburse employees](expenses/reimburse.html)
  * [Re-invoice expenses](expenses/reinvoice_expenses.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/expenses.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](expenses/approve_expenses.html "Approve expenses") |
  * [precedente](accounting/reporting/year_end.html "Year-end closing") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Costi


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[API]: application programming interfaces
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
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
  *[POS]: Point Of Sale
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