# Razorpay — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](six.html "SIX") |
  * [precedente](mercado_pago.html "Mercado Pago") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Razorpay



# Razorpay¶

Connecting a Razorpay payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Vedi anche

[Use Razorpay as apayment provider.](../../../../finance/payment_providers/razorpay.html)

## Configurazione¶

### Locate your Razorpay credentials¶

[Create a Razorpay account](https://razorpay.com/docs/payments/easy-create-account/) and set it up on their website.

You need the following credentials to set up the payment method in Odoo:

  * [API key](https://razorpay.com/docs/payments/dashboard/account-settings/api-keys/)

  * Razorpay username

  * Razorpay device serial number, which can be found underneath the device or on [Razorpay’s dashboard](https://dashboard.razorpay.com/).




### Configure the payment method¶

  1. [Activate the POS Razorpay module](../../../../general/apps_modules.html) to enable the payment terminal.

  2. [Create the related payment method](../../payment_methods.html) by going to Point of Sale ‣ Configuration ‣ Payment Methods.

     1. Set the Journal type as Bank.

     2. Select Razorpay in the Use a Payment Terminal field.

     3. Enter your username in the Razorpay Username field and your device’s serial number in the Razorpay Device Serial No field.

     4. Fill in the Razorpay API Key field with the Razorpay API key.

     5. Set the Razorpay Allowed Payment Modes according to your needs.

Nota

You can enable the Razorpay Test Mode field while testing or keep it unchecked for production.




Once the payment method is created, you can enable it for your POS. To do so, go to the [POS” settings](../../configuration.html#configuration-settings) and add the payment method under the Payment section.

Nota

The terminal must have at least a 10% battery level to use it.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/razorpay.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](six.html "SIX") |
  * [precedente](mercado_pago.html "Mercado Pago") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Razorpay


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