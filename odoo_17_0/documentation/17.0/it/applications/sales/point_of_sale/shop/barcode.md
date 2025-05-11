# Codici a barre — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](serial_numbers.html "Serial numbers and lots") |
  * [precedente](sales_order.html "Sales orders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Shop features](../shop.html) »
  * Codici a barre



# Codici a barre¶

Using a barcode scanner to process point-of-sale orders improves your efficiency in providing quicker customer service. Barcode scanners can be used both to scan products or to log employees into a POS session.

## Configurazione¶

To use a barcode scanner, you must enable the feature in the Inventory app. Go to Inventory ‣ Configuration ‣ Settings, in the Barcode section, tick Barcode Scanner and save.

Vedi anche

  * [Set up a barcode scanner](../../../inventory_and_mrp/barcode/setup/hardware.html)

  * [Activate barcode scanners](../../../inventory_and_mrp/barcode/setup/software.html)




Once enabled in **Inventory** , you can use the barcode feature in **Point of Sale** with products that have a barcode number assigned.

## Assign barcodes¶

### To your products¶

To use this feature in POS, your products must have barcodes assigned. To do so, go to Point of Sale ‣ Products ‣ Products and open a **product form**. Add a barcode number in the Barcode field in the General Information tab.

### To your employees¶

To add an identification number to an employee, go to the **Employees** app and open an **employee form**. Choose an identification number for your employee and fill in the PIN Code field in the HR Settings tab.

## Use barcodes¶

### Scansiona prodotti¶

Scan a product’s barcode using a barcode scanner. Doing so adds it directly to the cart. To change the quantity, scan a product as many times as needed, or click Qty and enter the number of products using the keypad.

You can also enter the barcode number manually in the search bar to look for the product. Then, click it to add it to the cart.

### Log employees¶

You can also use a barcode scanner to log your employees. To do so, [restrict access](../employee_login.html#pos-employee-login-configuration) to the POS and [use barcodes to log your employees in](../employee_login.html#pos-employee-login-badge) your POS.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/shop/barcode.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](serial_numbers.html "Serial numbers and lots") |
  * [precedente](sales_order.html "Sales orders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Shop features](../shop.html) »
  * Codici a barre


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
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System