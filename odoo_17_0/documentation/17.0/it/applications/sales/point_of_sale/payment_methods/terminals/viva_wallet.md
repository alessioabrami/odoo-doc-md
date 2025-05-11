# Viva Wallet — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](worldline.html "Worldline") |
  * [precedente](vantiv.html "Vantiv") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Viva Wallet



# Viva Wallet¶

Connecting a **Viva Wallet** [payment terminal](../terminals.html) allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Nota

Viva Wallet lets you turn your phone into a mobile card reader: [Tap On Phone](https://www.vivawallet.com/gb_en/blog-tap-on-phone-gb).

## Configurazione¶

Start by creating your Viva Wallet account on [Viva Wallet’s website](https://www.vivawallet.com/).

### Locate your Viva Wallet credentials¶

When configuring Viva Wallet in Point of Sale, you need to use specific credentials that are available in your Viva Wallet account. These credentials include your Merchant ID, API key, POS API credentials, and Terminal ID number.

#### Merchant ID and API key¶

Locate your [Merchant ID and API key following the Viva documentation](https://developer.vivawallet.com/getting-started/find-your-account-credentials/merchant-id-and-api-key/). Then, save the keys and paste them into the Odoo Merchant ID and API Key fields when creating the payment method.

Nota

These credentials are used for APIs that authenticate with Basic Auth.

#### POS API credentials¶

Locate and generate your [POS API credentials following the Viva documentation](https://developer.vivawallet.com/getting-started/find-your-account-credentials/pos-api-credentials/). Then, save the keys and paste them in the Odoo Client secret and Client ID fields when creating the payment method.

Avvertimento

These credentials are only displayed once. Ensure you keep a copy to secure them.

Nota

These credentials are used for Android and iOS POS Activation requests, as well as the Cloud Terminal API.

#### ID terminale¶

Your terminal ID number is used to identify your terminal. To find it:

  1. Go to your Viva Wallet account and select the relevant account.

  2. Go to Sales ‣ Physical payments ‣ Card terminals in the navigation menu.




The terminal ID number is located under the Terminal ID (TID) column. Save it to paste it into the Terminal ID field when creating the payment method.

### Configure the payment method¶

  1. [Activate the POS Viva Wallet module](../../../../general/apps_modules.html) to enable the payment terminal.

  2. [Create the related payment method](../../payment_methods.html) by going to Point of Sale ‣ Configuration ‣ Payment Methods and clicking New.

  3. Set the journal type as Bank.

  4. Select Viva Wallet in the Use a Payment Terminal field.

  5. Fill in the mandatory fields with your:

     * Merchant ID and API key

     * Client ID and Client secret

     * Terminal ID

  6. Save the form and copy the generated webhook URL from the Viva Wallet Webhook Endpoint field. This URL is necessary when configuring the webhook.




### Configure the webhook¶

Webhooks allow you to receive real-time notifications whenever a transaction occurs within your Viva Wallet account. Set them up for [payment transactions following the Viva documentation](https://developer.vivawallet.com/webhooks-for-payments/transaction-payment-created/).

Vedi anche

[Setting up webhooks](https://developer.viva.com/webhooks-for-payments/#setting-up-webhooks)

### Link the payment method to a POS¶

You can select the payment method in your POS settings once the payment method is created. To do so, go to the [POS” settings](../../configuration.html#configuration-settings) and add the payment method under the Payment methods field of the Payment section.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/viva_wallet.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](worldline.html "Worldline") |
  * [precedente](vantiv.html "Vantiv") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Viva Wallet


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