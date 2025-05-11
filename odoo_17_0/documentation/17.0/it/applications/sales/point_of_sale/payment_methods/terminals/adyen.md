# Adyen — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ingenico.html "Ingenico") |
  * [precedente](../terminals.html "Payment terminals") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Adyen



# Adyen¶

Connecting an **Adyen payment terminal** allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Importante

  * Adyen payment terminals do not require an [IoT Box](../../../../general/iot.html).

  * Adyen terminals can be used in many countries, but not worldwide. Check the [List of countries supported by Adyen](https://docs.adyen.com/point-of-sale/what-we-support/supported-languages/).

  * Adyen works only with businesses processing more than **$10 million annually** or invoicing a minimum of **1,000 transactions per month**.




Vedi anche

  * [List of payment methods supported by Adyen](https://docs.adyen.com/point-of-sale/what-we-support/payment-methods/)

  * [List of Adyen terminals](https://docs.adyen.com/point-of-sale/what-we-support/select-your-terminals/)




## Configurazione¶

Start by creating your Adyen account on [Adyen’s website](https://www.adyen.com/). Then, board your terminal following the steps described on your terminal’s screen.

Vedi anche

[Adyen Docs - Payment terminal quickstart guides](https://docs.adyen.com/point-of-sale/user-manuals)

### Generate an Adyen API key¶

The **Adyen API key** is used to authenticate requests from your Adyen terminal. To generate an API key, go to your Adyen account ‣ Developers ‣ API credentials, and **create** new credentials or select **existing** ones. Click Generate an API key and save the key to paste it into the Odoo Adyen API key field at the payment method creation.

Vedi anche

  * [Adyen Docs - API credentials](https://docs.adyen.com/development-resources/api-credentials#generate-api-key).




### Locate the Adyen terminal identifier¶

The **Adyen Terminal Identifier** is the terminal’s serial number, which is used to identify the hardware.

To find this number, go to your Adyen account ‣ Point of Sale ‣ Terminals, select the terminal to link with, and save its serial number to paste it into the Odoo Adyen Terminal Identifier field at the payment method creation.

### Set the Event URLs¶

For Odoo to know when a payment is made, you must configure the terminal **Event URLs**. To do so,

  1. Log in to [Adyen’s website](https://www.adyen.com/);

  2. Go to Adyen’s dashboard ‣ Point of Sale ‣ Terminals and select the connected terminal;

  3. From the terminal settings, click Integrations;

  4. Set the Switch to decrypted mode to edit this setting field as Decrypted;

  5. Click the **pencil icon** button and enter your server address, followed by `/pos_adyen/notification` in the Event URLs field;

  6. Click Save at the bottom of the screen to save changes.




### Configure the payment method¶

Enable the payment terminal [in the application settings](../../configuration.html#configuration-settings) and [create the related payment method](../../payment_methods.html). Set the journal type as Bank and select Adyen in the Use a Payment Terminal field.

Finally, fill in the mandatory fields with your Adyen API key, Adyen Terminal Identifier, and Adyen Merchant Account.

Once the payment method is created, you can select it in your POS settings. To do so, go to the [POS” settings](../../configuration.html#configuration-settings), click Edit, and add the payment method under the Payments section.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/adyen.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ingenico.html "Ingenico") |
  * [precedente](../terminals.html "Payment terminals") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Adyen


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