# SIX — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](stripe.html "Stripe") |
  * [precedente](razorpay.html "Razorpay") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * SIX



# SIX¶

Connecting a SIX payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Avvertimento

Even though Worldline has recently acquired SIX Payment Services and both companies use Yomani payment terminals, the firmware they run is different. Terminals received from Worldline are therefore not compatible with this integration.

## Configurazione¶

### Install the POS IoT Six module¶

To activate the POS IoT Six module, go to Apps, remove the Apps filter, and search for **POS IoT Six**. This module adds the necessary driver and interface to your database to detect Six terminals.

Nota

This module replaces the **POS Six** module.

### Connect an IoT system¶

Connecting a Six payment terminal to Odoo is requires [using an IoT system](../../../../general/iot.html).

### Configure the terminal ID¶

Navigate to the IoT system’s homepage, where you can find the Six payment terminal field once your database server is connected to the IoT system. Click Configure, fill in the Terminal ID field with the ID received from Six, and click Connect. Your Six terminal ID should appear in the Current Terminal Id section.

Odoo automatically restarts the IoT system when the Six terminal ID is configured. If your Six terminal is online, it will be automatically detected and connected to the database. Check the IoT system’s homepage under the Payments section to confirm the connection.

### Configure the payment method¶

Enable the payment terminal [in the application settings](../../configuration.html#configuration-settings) and [create the related payment method](../../payment_methods.html). Set the journal type as Bank and select SIX IOT in the Use a Payment Terminal field. Then, select your terminal device in the Payment Terminal Device field.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/six.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](stripe.html "Stripe") |
  * [precedente](razorpay.html "Razorpay") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * SIX


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
  *[SO]: sales order