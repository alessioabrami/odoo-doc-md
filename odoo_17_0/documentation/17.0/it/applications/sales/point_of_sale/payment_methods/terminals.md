# Payment terminals — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](terminals/adyen.html "Adyen") |
  * [precedente](../payment_methods.html "Metodo di pagamento") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Metodo di pagamento](../payment_methods.html) »
  * Payment terminals



# Payment terminals¶

Connecting and integrating a payment terminal with your POS system allows you to accept multiple payment options, including credit and debit cards, making the payment process more efficient.

## Configurazione¶

Go to the [application settings](../configuration.html#configuration-settings), scroll down to the Payment Terminals section, and tick your terminal’s checkbox.

Then, follow the corresponding documentation to configure your device:

  * [Adyen configuration](terminals/adyen.html)

  * [Ingenico configuration](terminals/ingenico.html)

  * [Mercado Pago configuration](terminals/mercado_pago.html)

  * [Razorpay configuration](terminals/razorpay.html)

  * [SIX configuration](terminals/six.html)

  * [Stripe configuration](terminals/stripe.html)

  * [Vantiv configuration](terminals/vantiv.html)

  * [Viva Wallet configuration](terminals/viva_wallet.html)

  * [Worldline configuration](terminals/worldline.html)




Once the terminal is configured, you can [create the corresponding payment method and add it to the POS](../payment_methods.html).

## Pay with a payment terminal¶

When processing a payment, select the terminal’s payment method. Check the amount and click on Send. Once the payment is successful, the status changes to Payment Successful.

Nota

  * In case of connection issues between Odoo and the payment terminal, force the payment by clicking on Force Done, which allows you to validate the order.

This option is only available after receiving an error message informing you that the connection failed.

  * To cancel the payment request, click on Cancel.




  * [Adyen](terminals/adyen.html)
  * [Ingenico](terminals/ingenico.html)
  * [Mercado Pago](terminals/mercado_pago.html)
  * [Razorpay](terminals/razorpay.html)
  * [SIX](terminals/six.html)
  * [Stripe](terminals/stripe.html)
  * [Vantiv](terminals/vantiv.html)
  * [Viva Wallet](terminals/viva_wallet.html)
  * [Worldline](terminals/worldline.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](terminals/adyen.html "Adyen") |
  * [precedente](../payment_methods.html "Metodo di pagamento") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Metodo di pagamento](../payment_methods.html) »
  * Payment terminals


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