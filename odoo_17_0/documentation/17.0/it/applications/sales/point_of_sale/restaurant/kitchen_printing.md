# Orders printing — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bill_printing.html "Fatture") |
  * [precedente](floors_tables.html "Floors and tables") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Restaurant features](../restaurant.html) »
  * Orders printing



# Orders printing¶

Integrating printers in a restaurant or bar’s workflow can enhance communication and collaboration between the front-of-house and back-of-house teams, leading to a more streamlined and efficient service.

## Configurazione¶

### Enable and create printers¶

To enable sending orders to a kitchen or bar printer, go to Point of Sale ‣ Configuration ‣ Settings, scroll down to the Restaurant & Bar section, and enable Kitchen Printers. Type in a name for the printer in the Printers field and click Create and edit… to open a setup form.

To get a list of all the printers already created or to modify an already created printer, click –> Printers and select the desired printer to open the setup form.

### Setup form¶

From the setup form, select the Printer Type according to your installation:

  * If your printer is connected to an IoT system, select Use a printer connected to the IoT Box and select the device in the IoT Device field.

  * If you use an Epson printer that does not require an IoT system, select Use an Epson printer and enter the printer’s IP address in the Epson Printer IP Address field.




Vedi anche

  * [Conessione sistema IoT a Odoo](../../../general/iot/connect.html)

  * [Collegare una stampante](../../../general/iot/devices/printer.html)

  * [Self-signed certificate for ePOS printers](../configuration/epos_ssc.html)




Set your printer to print specific products based on their POS category. To do so, click Add a line in the Printed Product Categories field. If you leave this field empty, all products are sent to the printer regardless of their POS category.

## Print orders¶

From an open session, start taking an order and click Order to send it to the bar or the kitchen.

Nota

When products can be printed, they appear in green in the cart, and the order button turns green.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/restaurant/kitchen_printing.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bill_printing.html "Fatture") |
  * [precedente](floors_tables.html "Floors and tables") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Restaurant features](../restaurant.html) »
  * Orders printing


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