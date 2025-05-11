# Multi-employee management — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_invoices.html "Receipts and invoices") |
  * [precedente](configuration/epos_ssc.html "Self-signed certificate for ePOS printers") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Multi-employee management



# Multi-employee management¶

Odoo Point of Sale (POS) offers a **Multi Employees per Session** feature, allowing multiple users to log into a POS session. Activating this feature enables the following actions:

  * Select specific users who can log into the POS.

  * Assign basic or advanced permissions to these users.

  * [Track the employees involved in each order for enhanced analytics](../point_of_sale.html#pos-analytics).




## Configurazione¶

Access the multi-employee setting from the PoS Interface section of the [POS settings](configuration.html#configuration-settings). Then,

  1. Activate the Multi Employees per Session feature.

  2. Add the employees with **basic POS functionality** access in the Basic rights field.

  3. Add the employees with **extended POS functionalities** in the Advanced rights field.




Nota

  * Leaving the Basic rights field empty allows all employees to log in.

  * Leaving the Advanced rights field empty grants extended rights to Odoo users only.




Suggerimento

Click the __( vertical ellipsis) button on the top right corner of a POS card and Edit to access the setting from the main POS dashboard.

Vedi anche

[Diritti di accesso](../../general/users/access_rights.html)

Basic rightsAdvanced rights

Employees with basic rights can perform the following actions within the POS:

**Session management:**

  * [Open a POS session](../point_of_sale.html#pos-session-start).

  * Lock the current POS session.

  * Toggle the visibility of product and category images.




**Sales transactions:**

  * [Process standard sales transactions](../point_of_sale.html#pos-sell).

  * [Process refunds](../point_of_sale.html#pos-refund).

  * [Access and handle sales orders](shop/sales_order.html).

  * [Set customers](../point_of_sale.html#pos-customers).

  * Access past and current order history.




**Pricing and discounts:**

  * Manually select another [pricelist](pricing/pricelists.html).

  * Enter promotional codes.

  * [Manually apply discounts](pricing/discounts.html).

  * Manually [change a product’s price](../point_of_sale.html#pos-sell).




In addition to the basic rights, employees with advanced rights can also:

  * [Perform cash-in and cash-out operations](../point_of_sale.html#pos-cash-register).

  * Access the Odoo backend interface.

  * [Close the current POS session](../point_of_sale.html#pos-session-close).




## Usage guidelines¶

### Accedere¶

Once the **Multi Employees per Session** feature is enabled, employees must log in to [open a POS session](../point_of_sale.html#pos-session-start) and access the POS interface. They can scan their employee badge or click Select Cashier to select their name from the list of authorized users.

To switch between users during an [active session](../point_of_sale.html#pos-session-start), click on the currently logged-in employee’s name at the top right of the POS screen and select the user to switch to.

### Logging in with badges¶

Employees can log in using their badge. To configure badge-based login, assign a unique badge ID to the employee’s profile in the **Employees** module:

  1. Navigate to the **Employees** module.

  2. Open the form view of the specific employee.

  3. Go to the HR Settings tab.

  4. The Attendance/Point of Sale category offers two options:

     * Manually enter any badge ID in the Badge ID field.

     * Click Generate to create a unique badge ID automatically.

  5. Click Print Badge to generate a barcode representation of the assigned badge ID.




To switch users within an open POS session using a badge, you must first lock the session. To do so, click the __icon ( hamburger menu) and Lock to return to the login screen. Then, the new employee can scan their badge to log in.

### Adding a PIN Code¶

For enhanced security, employees may be forced to enter a PIN code each time they log into a POS session. To set up a PIN code for an employee:

  1. Navigate to the **Employees** module.

  2. Open the form view of the relevant employee.

  3. Go to the HR Settings tab.

  4. Enter a desired numerical code in the PIN Code field of the Attendance/Point of Sale category.




Nota

The PIN code must consist of a sequence of digits only.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/employee_login.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_invoices.html "Receipts and invoices") |
  * [precedente](configuration/epos_ssc.html "Self-signed certificate for ePOS printers") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Multi-employee management


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue