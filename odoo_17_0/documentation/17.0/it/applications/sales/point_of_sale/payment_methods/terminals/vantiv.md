# Vantiv — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](viva_wallet.html "Viva Wallet") |
  * [precedente](stripe.html "Stripe") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Vantiv



# Vantiv¶

Connecting a Vantiv payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Nota

Please note MercuryPay only operates with US and Canadian banks, making this procedure only suitable for North American businesses.

Avvertimento

Vantiv card readers should be purchased exclusively from Vantiv, as certain Vantiv terminals bought on Amazon do not include the correct encryption needed to be used with an Odoo database.

## Configurazione¶

### Configure the payment method¶

Enable the payment terminal in the Payment Terminals section [of the application settings](../../configuration.html#configuration-settings).

Then, go to Point of Sale ‣ Configuration ‣ Payment Methods, and [create the related payment method](../../payment_methods.html). Set the journal type as Bank and select Vantiv in the Use a Payment Terminal field.

Type the name you want to give to your Vantiv Credentials and click Create and edit. Enter your Merchant ID and Merchant Password, then click Save & Close.

Once the payment method is created, you can select it in your POS settings. To do so, go to the [POS” settings](../../configuration.html#configuration-settings) and add the payment method under the Payment section.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/vantiv.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](viva_wallet.html "Viva Wallet") |
  * [precedente](stripe.html "Stripe") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Vantiv


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