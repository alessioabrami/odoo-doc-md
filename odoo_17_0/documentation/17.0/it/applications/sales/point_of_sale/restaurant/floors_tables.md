# Floors and tables — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kitchen_printing.html "Orders printing") |
  * [precedente](../restaurant.html "Restaurant features") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Restaurant features](../restaurant.html) »
  * Floors and tables



# Floors and tables¶

The **Floor plan view** enables you to manage restaurant floors and table arrangements and monitor table status in real time, including occupancy, reservations, and kitchen orders.

Example

  * Table 1: An order has been placed and sent to the kitchen.

  * Table 3: An order of four items has been placed and needs to be sent to the kitchen.

  * Tables 2, 4, and 5: These tables are available.

  * Tables 2, 4, and 5: These tables” total capacity is, respectively, 2, 4, and 8 people.

  * Table 1: The table of two is full.

  * Table 3: The table of four is taken by one person.

  * Table 5: «Famous Joe» has a reservation for 8 people at 12:00.




## Configurazione¶

### From the POS backend¶

To create floors and tables from the backend, go to Point of Sale ‣ Configuration ‣ Floor Plans, and click New to create a floor. Name it, select the related point(s) of sales, and click Add a line to create a table. Name the table and assign a number of seats. You can also link it to an appointment resource to make the table bookable. Once done, click Save & Close or Save & New to confirm.

Nota

The POS must be opened and edited from the frontend to create a map of your restaurant or bar reflecting your actual floor plan.

Suggerimento

Create floors on the spot: [access your POS settings](../configuration.html#configuration-settings), type your floor name in the Floor field of the Floors & Tables Map category, and press _enter_.

### From the POS frontend¶

To create floors and tables from the frontend, [open a POS session](../../point_of_sale.html#pos-session-start), click the hamburger menu icon ≡ in the upper right corner, then Edit Plan to enter the **edit mode**.

Click \+ Add Floor to add a floor, then enter a name in the pop-up window.

Once a floor is created, add a table by clicking \+ TABLE. To move it, select it and drag and drop it as desired. You can also modify the attributes of the selected table, such as the number of seats by clicking SEATS, the table shape using SHAPE, the table color using FILL, or the table name by clicking RENAME. To duplicate an existing table, select it and click COPY. You can also remove the table by clicking DELETE.

After making all the necessary modifications, click CLOSE to save.

Nota

If no table is selected, the modifications are applied to the floor.

Avvertimento

Removing a table or a floor cannot be undone.

## Table transfer¶

To move customers from one table to another, select a table and click → Transfer on the POS interface. This redirects you to the floor plan view, where you can choose the new table to which you want to transfer the customers.

When you transfer customers, all of the orders they have placed and that are linked to the original table are also transferred.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/restaurant/floors_tables.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kitchen_printing.html "Orders printing") |
  * [precedente](../restaurant.html "Restaurant features") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Restaurant features](../restaurant.html) »
  * Floors and tables


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