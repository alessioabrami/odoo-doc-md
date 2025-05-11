# Metodo di pagamento — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_methods/terminals.html "Payment terminals") |
  * [precedente](pricing/electronic_labels.html "Electronic shelf labels") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Metodo di pagamento



# Metodo di pagamento¶

To add a payment method, you first need to create it. Go to Point of Sale ‣ Configuration ‣ Payment Methods ‣ New, and set a name. Check Identify Customer to allow this payment method _exclusively_ for registered customers.

Then, select the Journal. Choose Cash to use this payment method for cash payments, or Bank to use it for card payments.

Nota

Selecting a bank journal automatically adds the Use a Payment Terminal field in which you can add your [payment terminal’s information](payment_methods/terminals.html).

Vedi anche

[Payment terminals](payment_methods/terminals.html).

Once the payment method is created, you can select it in your POS settings. To do so, go to the [POS” settings](configuration.html#configuration-settings), click Edit, and add the payment method under the Payments section.

  * [Payment terminals](payment_methods/terminals.html)
    * [Adyen](payment_methods/terminals/adyen.html)
    * [Ingenico](payment_methods/terminals/ingenico.html)
    * [Mercado Pago](payment_methods/terminals/mercado_pago.html)
    * [Razorpay](payment_methods/terminals/razorpay.html)
    * [SIX](payment_methods/terminals/six.html)
    * [Stripe](payment_methods/terminals/stripe.html)
    * [Vantiv](payment_methods/terminals/vantiv.html)
    * [Viva Wallet](payment_methods/terminals/viva_wallet.html)
    * [Worldline](payment_methods/terminals/worldline.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_methods/terminals.html "Payment terminals") |
  * [precedente](pricing/electronic_labels.html "Electronic shelf labels") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Metodo di pagamento


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