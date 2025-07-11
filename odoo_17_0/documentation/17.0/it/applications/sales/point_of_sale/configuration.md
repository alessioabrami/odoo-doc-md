# Configurazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](configuration/pos_iot.html "IoT system connection") |
  * [precedente](../point_of_sale.html "Punto vendita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Configurazione



# Configurazione¶

## Access the POS settings¶

To access the general POS settings, go to Point of Sale ‣ Configuration ‣ Settings. Then, open the dropdown menu in the Point of Sale field and select the POS to configure.

Nota

These settings are available to users with the [access rights](../../general/users.html) Administration set as Settings.

You can also configure some settings from the dashboard by clicking the vertical ellipsis button (⋮) on a POS card. Doing so opens a popup window, from which you can:

  * [Enable multiple employees to log in.](employee_login.html)

  * [Connect and set up an IoT sytem.](configuration/pos_iot.html)

  * [Connect and set up an ePOS printer.](configuration/epos_ssc.html)




Nota

These settings are available to users with the [access rights](../../general/users.html) Point of Sale set as Administrator.

## Make products available¶

To make products available for sale, go to Point of Sale ‣ Products ‣ Products, and select a product to open the product form. In the Sales tab, enable Available in POS.

## PoS product categories¶

### Configurazione¶

POS product categories allow users to categorize products and get a more structured and clean POS interface.

To manage PoS categories, go to Point of Sale ‣ Configuration ‣ PoS Product Categories. To add a new category, click Create. Then, name it in the Category Name field.

To associate a category with a parent category, fill in the Parent Category field. A parent category groups one or more child categories.

Example

### Assign PoS product categories¶

Go to Point of Sale ‣ Products ‣ Products and open a product form. Then, go to the Sales tab and fill in the Category field under the Point of Sale section.

### Adapt the POS interface¶

#### Start category¶

You can select one product category to display when [opening a POS session](../point_of_sale.html#pos-session-start). To configure it, go to your POS settings and select a PoS category from the dropdown menu of the Start Category field within the PoS Interface section.

#### Restrict categories¶

You can also limit the categories displayed on your POS interface. To achieve this, go to your POS settings and choose the specific categories to display in the Restrict Categories field within the PoS Interface section.

  * [IoT system connection](configuration/pos_iot.html)
  * [ePOS printers](configuration/epos_printers.html)
  * [Secure connection (HTTPS)](configuration/https.html)
  * [Self-signed certificate for ePOS printers](configuration/epos_ssc.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/configuration.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](configuration/pos_iot.html "IoT system connection") |
  * [precedente](../point_of_sale.html "Punto vendita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Configurazione


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