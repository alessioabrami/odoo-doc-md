# Ingenico — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mercado_pago.html "Mercado Pago") |
  * [precedente](adyen.html "Adyen") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Ingenico



# Ingenico¶

Connecting a payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Importante

  * Ingenico payment terminals require an [IoT system](../../../../general/iot.html).

  * Ingenico is currently only available in Belgium, the Netherlands and Luxembourg.

  * Odoo works with the Ingenico Lane/, Desk/, and Move/ payment terminals as they support the TLV communication protocol through TCP/IP.




## Configurazione¶

### Connect an IoT system¶

Connecting an Ingenico payment terminal to Odoo is a feature that requires an IoT system. For more information on how to connect an IoT system to your database, please refer to the [IoT documentation](../../../../general/iot.html).

### Configure the Lane/Desk/Move 5000 terminals for Ingenico BENELUX¶

  1. Press the function button (F on Lane/5000, ⦿ on Desk/5000 and Move/5000).

  2. Go to Kassa menu ‣ Settings Menu and enter the settings password.

  3. Select Change Connection and press OK on the next screen.

  4. Select TCP/IP and IP-address.

  5. On the next screen, enter the IP address of your IoT system.

  6. Enter `9000` as port number and press OK on the next screen.




At this point, the terminal restarts and should be displayed on the IoT system’s form in Odoo.

### Configure the payment method¶

Enable the payment terminal [in the application settings](../../configuration.html#configuration-settings) and [create the related payment method](../../payment_methods.html). Set the journal type as Bank and select Ingenico in the Use a Payment Terminal field. Then, select your terminal device in the Payment Terminal Device field.

Once the payment method is created, you can select it in your POS settings. To do so, go to the [POS” settings](../../configuration.html#configuration-settings), click Edit, and add the payment method under the Payments section.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/ingenico.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mercado_pago.html "Mercado Pago") |
  * [precedente](adyen.html "Adyen") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Ingenico


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