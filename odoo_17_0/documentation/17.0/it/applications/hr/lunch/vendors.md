# Fornitori — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products.html "Prodotti") |
  * [precedente](../lunch.html "Mensa") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Fornitori



# Fornitori¶

Before [products can be added](products.html) to the _Lunch_ app, the restaurants that provide the food **must** be configured.

To add a new vendor, first navigate to Lunch app ‣ Configuration ‣ Vendors. Here, all currently configured vendors for the _Lunch_ app appear in a default Kanban view. To change to a list view, click the __(list) icon in the top-right corner.

Nota

No vendors are preconfigured in the _Lunch_ app, so all vendors **must** be added to the database.

To add a new vendor, click the New button in the top-left corner, and a new lunch supplier form loads.

Fill out the following fields on the vendor form:

  * Vendor information

  * Availability

  * Orders

  * Extras




## Vendor information¶

  * Vendor: enter a name for the vendor.

  * Vendor (beneath the line for vendor name): select the vendor from the drop-down menu. If the vendor has not already been entered in the system, type in the vendor name, and click either Create «new vendor name» to add them. Alternatively, click Create and edit… to create the vendor, and edit the vendor form. The vendor form allows for more detail, aside from the name, to be entered, such as contact information.

Nota

If a selection is made to the drop-down Vendor field, the Vendor text field (above, for the vendor’s name) updates with the name of the vendor chosen from the drop-down menu.

The list of vendors that is presented in the drop-down menu is pulled from the _Contacts_ application.

  * Address: enter the vendor’s address in the various fields.

  * Email: enter the vendor’s email.

  * Phone: enter the vendor’s phone number.

  * Company: if this vendor is only available to a specific company, select the company from the drop-down menu. If this field is left blank, the vendor’s items are available to **all** companies.




## Disponibilità¶

The AVAILABILITY section presents a table with two rows. The days of the week populate the top row, and the bottom row has checkboxes. Tick the corresponding checkbox for each day of the week the vendor is available.

By default, Monday through Friday are ticked.

## Ordini¶

The ORDERS section of the vendor form details which locations the vendor is available for, in addition to how and when orders are placed and received.

  * Delivery: using the drop-down menu, select Delivery if the vendor delivers to the office, or select No Delivery if orders must be picked up.

  * Location: select which locations are able to order from this vendor. Multiple locations can be selected. If this field is left blank, **all** locations can order from the vendor.

Nota

An `HQ Office` location is created by default when creating a database, and is available to select from the list.

  * Send Order By: click the radio button to select how orders are sent to the vendor. The available options are Phone or Email.

  * Order Time: this field **only** appears if Email is selected in the Send Order By field. Enter the time that an order must be emailed for it to be accepted. Enter the time in the following format: `HH:MM`. Then select either AM or PM from the drop-down menu, next to the time field.




## Aggiunte¶

When ordering an item in the _Lunch_ app, optional extra items, sometimes referred to as _add-ons_ , can be shown. These can be configured in any manner that suits the products being offered.

By default, Odoo allows for three types of extra items, which can be thought of as _categories_. By default, the first type (or _category_) of add-ons is labeled `Extras`, the second is labeled `Beverages`, and the third is labeled `Extra Label 3`.

Importante

When configuring the extras, it is important to keep in mind that all the extras configured appear for **every item** offered by the vendor. That means that only items which apply to **all** products from the vendor should be added.

### Configure extras¶

Enter the following information for each of the three available extra sections:

  * Extra (#) Label: enter a name for the type of extra, such as `Toppings`. This can be thought of as a _category_.

  * Extra (#) Quantity: select how the extras are selected. The options are:

    * None or More: select this if the user is not required to make a selection.

    * One or More: select this to **require** the user to make **at least one** selection.

    * Only One: select this to **require** the user to **make only one** selection.




### Add extras¶

After the labels and quantities have been configured for an extra category, the individual extra items must be added for each category.

Click Add a line at the bottom of the list that appears on the right-hand side of the extra category. Enter the Name and Price for each item being added. The price can remain at `$0.00` if there is no cost. This is common for items like disposable silverware or condiments.

Example

For a pizzeria that only offers personal pizzas, see their extras configured as follows:

The first extra is configured for the various toppings they offer. The Extra 1 Label is set to `Toppings`, and the Extra 1 Quantity is set to None or More. The various toppings are then added, with their corresponding costs.

The pizzeria also offers a free beverage with any purchase. To set this up, the Extra 2 Label is set to `Beverages`, and the Extra 2 Quantity is set to Only One. The various beverage choices are added, and the cost for each remains zero.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/lunch/vendors.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products.html "Prodotti") |
  * [precedente](../lunch.html "Mensa") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Fornitori


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
  *[POS]: Punto vendita
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte