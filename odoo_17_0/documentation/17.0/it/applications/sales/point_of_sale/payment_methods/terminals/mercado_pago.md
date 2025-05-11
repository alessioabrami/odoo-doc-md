# Mercado Pago — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](razorpay.html "Razorpay") |
  * [precedente](ingenico.html "Ingenico") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Mercado Pago



# Mercado Pago¶

Connecting a payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Importante

Only **Point Smart** payment terminals in **Argentina** , **Brazil** , and **Mexico** are supported. They can be purchased on [Mercado Pago’s website](https://www.mercadopago.com.mx/herramientas-para-vender/lectores-point).

Vedi anche

[Mercado Pago online payments](https://www.mercadopago.com.mx/herramientas-para-vender/check-out#benefits-checkout)

## Configurazione¶

  1. Create a [Mercado Pago account](https://www.mercadopago.com.mx/).

  2. Associate your Point Smart terminal with a store and a cash drawer by following [Mercado Pago’s documentation](https://vendedores.mercadolibre.com.ar/nota/locales-una-herramienta-para-mejorar-la-gestion-de-tus-puntos-de-venta/).

Nota

All purchased terminals are automatically displayed on your Mercado dashboard.

  3. Set your Point Smart terminal to the Point of Sale operation mode.

Avvertimento

Odoo does not support the Standalone operation mode.

  4. Create a Point Smart application.

  5. Generate your credentials.

  6. Create and configure the related payment method.




### Point Smart application¶

Create a new application from Mercado Pago’s [developer panel](https://www.mercadopago.com/developers) by following [Mercado Pago’s applications documentation](https://www.mercadopago.com.mx/ayuda/20152), making sure you select In person Payments.

### Credenziali¶

Once the Point Smart application is created, three credentials are required:

  * An access token that Odoo uses to call Mercado Pago.

  * A webhook secret key that Odoo uses to authenticate notifications sent by Mercado Pago.

  * The **terminal serial number** at the back of your Point Smart terminal.




Retrieve the access token and webhook secret key by following [Mercado Pago’s credentials documentation](https://www.mercadopago.com.mx/developers/en/docs/your-integrations/credentials). Then, copy and paste them into Odoo when creating the payment method.

Importante

For the webhooks configuration, add the URL of your Odoo database (e.g., `https://mycompany.odoo.com`) followed by `/pos_mercado_pago/notification` (e.g., `https://mycompany.odoo.com/pos_mercado_pago/notification`).

### Metodo di pagamento¶

  1. [Activate the POS Mercado Pago module](../../../../general/apps_modules.html) to enable the payment terminal.

  2. [Create the related payment method](../../payment_methods.html) by going to Point of Sale ‣ Configuration ‣ Payment Methods.

  3. Set the journal type as Bank

  4. Select Mercado Pago in the Use a Payment Terminal field.

  5. Fill in the mandatory fields with the previously generated credentials:

     * Fill in the Production user token field using the access token.

     * Fill in the Production secret key field using the webhook secret key.

     * Fill in the Terminal S/N field using the terminal serial number. You can find it at the back of your terminal.

     * Click the Force PDV button to activate the Point of Sale mode.




Select the payment method by going to the [POS” settings](../../configuration.html#configuration-settings) and adding it to the payment method under the Payment Methods field of the Payment section.

Importante

Any action made on the terminal should trigger a notification on the POS interface. Ensure the webhook secret key is correctly configured if you are not notified.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/mercado_pago.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](razorpay.html "Razorpay") |
  * [precedente](ingenico.html "Ingenico") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Mercado Pago


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