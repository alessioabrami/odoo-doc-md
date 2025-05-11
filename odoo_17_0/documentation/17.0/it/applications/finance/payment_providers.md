# Online payments — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_providers/wire_transfer.html "Wire transfers") |
  * [precedente](expenses/reinvoice_expenses.html "Re-invoice expenses") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Online payments



# Online payments¶

  * [Wire transfers](payment_providers/wire_transfer.html)
  * [Addebito Diretto SEPA](payment_providers/sdd.html)
  * [Adyen](payment_providers/adyen.html)
  * [Alipay](payment_providers/alipay.html)
  * [Servizi di pagamento Amazon](payment_providers/amazon_payment_services.html)
  * [AsiaPay](payment_providers/asiapay.html)
  * [Authorize.Net](payment_providers/authorize.html)
  * [Buckaroo](payment_providers/buckaroo.html)
  * [Demo](payment_providers/demo.html)
  * [Flutterwave](payment_providers/flutterwave.html)
  * [Mercado Pago](payment_providers/mercado_pago.html)
  * [Mollie](payment_providers/mollie.html)
  * [Ogone](payment_providers/ogone.html)
  * [PayPal](payment_providers/paypal.html)
  * [Razorpay](payment_providers/razorpay.html)
  * [SIPS](payment_providers/sips.html)
  * [Stripe](payment_providers/stripe.html)
  * [Xendit](payment_providers/xendit.html)



Odoo embeds several **payment providers** that allow your customers to pay online, on their _customer portals_ , or on your _eCommerce website_. They can pay sales orders, invoices, or subscriptions with recurring payments using their favorite payment methods, such as **credit cards**.

Each payment provider is linked to a list of supported payment methods that can be (de)activated based on your needs.

Nota

Odoo apps delegate the handling of sensitive information to the certified payment provider so that you don’t ever have to worry about PCI compliance. No sensitive information (such as credit card numbers) is stored on Odoo servers or Odoo databases hosted elsewhere. Instead, Odoo apps use a unique reference number for the data stored safely in the payment providers” systems.

## Supported payment providers¶

To access the supported payment providers, go to Accounting ‣ Configuration ‣ Payment Providers, Website ‣ Configuration ‣ Payment Providers, or Sales ‣ Configuration ‣ Payment Providers.

### Online payment providers¶

| Payment flow from | Tokenization | Manual capture | Refunds | Express checkout  
---|---|---|---|---|---  
[Adyen](payment_providers/adyen.html) | Odoo | ✔ | Full and partial | Full and partial |   
[Amazon Payment Services](payment_providers/amazon_payment_services.html) | The provider’s website |  |  |  |   
[AsiaPay](payment_providers/asiapay.html) | The provider’s website |  |  |  |   
[Authorize.Net](payment_providers/authorize.html) | Odoo | ✔ | Full only | Full only |   
[Buckaroo](payment_providers/buckaroo.html) | The provider’s website |  |  |  |   
[Flutterwave](payment_providers/flutterwave.html) | The provider’s website | ✔ |  |  |   
[Mercado Pago](payment_providers/mercado_pago.html) | The provider’s website |  |  |  |   
[Mollie](payment_providers/mollie.html) | The provider’s website |  |  |  |   
[PayPal](payment_providers/paypal.html) | The provider’s website |  |  |  |   
[Razorpay](payment_providers/razorpay.html) | Odoo | ✔ | Full only | Full and partial |   
[SIPS](payment_providers/sips.html) | The provider’s website |  |  |  |   
[Stripe](payment_providers/stripe.html) | Odoo | ✔ | Full only | Full and partial | ✔  
[Xendit](payment_providers/xendit.html) | The provider’s website |  |  |  |   
  
Nota

  * Each provider has its own specific configuration flow, depending on which feature is available.

  * Some of these online payment providers can also be added as [bank accounts](accounting/bank.html), but this is **not** the same process as adding them as payment providers. Payment providers allow customers to pay online, and bank accounts are added and configured in the Accounting app to do a [bank reconciliation](accounting/bank/reconciliation.html).




Suggerimento

In addition to the regular payment providers that integrate with an API, such as Stripe, PayPal, or Adyen, Odoo bundles the [Demo payment provider](payment_providers/demo.html). This payment provider allows you to test business flows involving online payments. No credentials are required as the demo payments are dummy payments.

### Bank payments¶

  * [Wire Transfer](payment_providers/wire_transfer.html)

When selected, Odoo displays your payment information with a payment reference. You have to approve the payment manually once you have received it in your bank account.

  * [SEPA Direct Debit](payment_providers/sdd.html)

Your customers can make a bank transfer to register a SEPA Direct Debit mandate and get their bank account charged directly.




## Enabling a payment provider¶

To add a new payment provider and make its related payment methods available to your customers, proceed as follows:

  1. Go to the payment provider’s website, create an account, and make sure you have the API credentials requested for third-party use. These are necessary for Odoo to communicate with the payment provider.

  2. In Odoo, navigate to the Payment providers by going to Accounting ‣ Configuration ‣ Payment Providers, Website ‣ Configuration ‣ Payment Providers, or Sales ‣ Configuration ‣ Payment Providers.

  3. Select the provider and configure the Credentials tab.

  4. Set the State field to Enabled.




Nota

  * The fields available in the Credentials tab depend on the payment provider. Refer to the related documentation for more information.

  * Once you have enabled the payment provider, it is automatically published on your website. If you wish to unpublish it, click the Published button. Customers cannot make payments through an unpublished provider, but they can still manage (delete and assign to a subscription) their existing tokens linked to such a provider.




### Modalità di prova¶

If you wish to try the payment provider as a test, set the State field in the payment provider form to Test mode, then enter your provider’s test/sandbox credentials in the Credentials tab.

Nota

By default, the payment provider remains **unpublished** in test mode so that it’s not visible to visitors.

Avvertimento

We recommend using the test mode on a duplicate or a test database to avoid potential issues with your invoice numbering.

## Metodo di pagamento¶

Each payment provider is related to a list of supported payment methods; the methods listed in the Payment methods field in the Configuration tab of the payment provider form are the ones that have been activated. To activate or deactivate a payment method for a provider, click Enable Payment Methods, then click the toggle button of the related method.

Suggerimento

Payment methods are displayed on your website based on their sequence order. To reorder them, click Enable Payment Methods in the payment provider form, then, in the Payment Methods list, drag and drop the payment methods in the desired order.

### Icons and brands¶

The icons displayed next to the payment method on your website are either the icons of the brands activated for the payment method or, if there aren’t any, the icons of the payment methods themselves. To modify them, go to Accounting ‣ Configuration ‣ Payment Methods, Website ‣ Configuration ‣ Payment Methods or Sales ‣ Configuration ‣ Payment Methods, then click on the payment method.

To modify a payment method’s icon, hover your mouse over the image in the upper-right corner of the payment method’s form and click the pencil icon (✎).

Select the Brands tab to view the brands that have been activated for the payment method. The brands and their related icons are displayed based on their sequence order; to reorder them, drag and drop them in the desired order. To modify a brand’s icon, select the brand, then, in the popup window that opens, hover the mouse over the image in the upper-right corner and click the pencil icon (✎).

### Configurazione avanzata¶

To configure payment methods further, go to Accounting ‣ Configuration ‣ Payment Methods, Website ‣ Configuration ‣ Payment Methods or Sales ‣ Configuration ‣ Payment Methods. Click on the payment method, then activate the [developer mode](../general/developer_mode.html#developer-mode). Click the Configuration tab to adapt the features.

Pericolo

  * Each payment method is preconfigured in a way that aligns with the payment providers” behavior and their integration with Odoo. Any change to this configuration may result in errors and should be tested on a duplicate or test database first.

  * Modifications to the payment method’s configuration only work to the extent of the method’s and provider’s capabilities. For example, adding countries for a payment method only supported in one country or enabling tokenization for a method linked to a provider that does not support it will not produce the intended results.




## Tokenizzazione¶

If the payment provider supports this feature, customers can save their payment method details for later. To enable this feature, go to the Configuration tab of the selected payment provider and enable Allow Saving Payment Methods.

In this case, a **payment token** is created in Odoo to be used as a payment method for subsequent payments without the customer having to enter their payment method details again. This is particularly useful for the eCommerce conversion rate and subscriptions that use recurring payments.

Suggerimento

To add or delete their saved payment method details, customers can click Manage payment methods in the [customer portal](../general/users/portal.html#users-portal-payment-methods).

PCI DSS and Attestation of Compliance

Odoo is not [PCI](https://www.pcisecuritystandards.org/) DSS-certified because it does not store cardholder data or process payments. Instead, it outsources tokenization and payment to external payment providers, which means that as an Odoo customer, you only need to complete the minimal Self-Assessment Questionnaire (SAQ) with the provider to obtain the Attestation of Compliance (AoC) and achieve PCI compliance. Odoo should not be mentioned as a payment processor or a third-party service provider in the SAQ.

## Manual capture¶

If the payment provider supports this feature, you can authorize and capture payments in two steps instead of one. To enable this feature, go to the Configuration tab of the selected payment provider and enable Capture Amount Manually.

When you authorize a payment, the funds are reserved on the customer’s payment method but not immediately charged. They are charged when you manually capture the payment later on. You can also void the authorization to cancel it and release the reserved funds. Capturing payments manually is helpful in many situations:

  * Receive the payment confirmation and wait until the order is shipped to capture the payment.

  * Review and verify that orders are legitimate before the payment is completed and the fulfillment process starts.

  * Avoid potentially high refund fees for refunded payments: payment providers will not charge you for voiding an authorization.

  * Hold a security deposit to return later, minus any deductions (e.g., in case of damages).




To capture the payment after it was authorized, go to the related sales order or invoice and click the Capture Transaction button. To release the funds, click the Void Transaction button.

Nota

  * Some payment providers support capturing only part of the authorized amount. The remaining amount can then be either captured or voided. These providers have the value **Full and partial** in the table above. The providers that only support capturing or voiding the total amount have the value **Full only**.

  * The funds are likely not reserved forever. After a certain time, they may be automatically released back to the customer’s payment method. Refer to your payment provider’s documentation for the exact reservation duration.

  * Odoo does not support this feature for all payment providers, but some allow the manual capture from their website interface.




## Rimborsi¶

If your payment provider supports this feature, you can refund payments directly from Odoo. It does not need to be enabled first. To refund a customer payment, navigate to it and click the Refund button.

Nota

  * Some payment providers support refunding only part of the amount. The remaining amount can then optionally be refunded, too. These providers have the value **Full and partial** in the table above. The providers that only support refunding the total amount have the value **Full only**.

  * Odoo does not support this feature for all payment providers, but some allow to refund payments from their website interface.




## Express checkout¶

If the payment provider supports this feature, you can allow customers to use the Google Pay and Apple Pay buttons and pay their eCommerce orders in one click. When they use one of these buttons, customers go straight from the cart to the confirmation page without filling out the contact form. They just have to validate the payment on Google’s or Apple’s payment form.

To enable this feature, go to the Configuration tab of the selected payment provider and enable Allow Express Checkout.

Nota

All prices shown on the express checkout payment form always include taxes.

## Disponibilità¶

You can adapt the payment provider’s availability by specifying the Maximum amount allowed and modifying the Currencies and Countries in the Configuration tab.

### Currencies and countries¶

All payment providers have a different list of available currencies and countries. They serve as a first filter during payment operations, i.e., the payment methods linked to the payment provider are not available for selection if the customer’s currency or country is not in the supported list. As there might be errors, updates, and unknowns in the lists of available currencies and countries, adding or removing a payment provider’s supported currencies or countries is possible.

Nota

  * Payment methods also have their own list of available currencies and countries that serves as another filter during payment operations.

  * If the list of supported currencies or countries is empty, it means the list is too long to be displayed, or Odoo does not have information on that payment provider. The payment provider remains available, even though it is possible the payment will be refused at a later stage should the country or currency not be supported.




### Maximum amount¶

You can restrict the Maximum Amount that can be paid with the selected provider. Leave the field to `0.00` to make the payment provider available regardless of the payment amount.

Importante

This feature is not intended to work on pages that allow the customer to update the payment amount, e.g., the **Donation** snippet and the **Checkout** page when paid [shipping methods](../websites/ecommerce/shipping.html) are enabled.

## Payment journal¶

A [payment journal](accounting/bank.html) must be defined for the payment provider to record the payments on an **outstanding account**. By default, the Bank journal is added as the payment journal for all payment providers. To modify it, go to the Configuration tab of the selected payment provider and select another Payment journal.

Nota

  * The payment journal must be a Bank journal.

  * The same journal can be used for several payment providers.

  * Payment journals must only be configured if the [Invoicing or Accounting app](accounting.html) is installed.




### Accounting perspective¶

From an accounting perspective, there are two types of online payment workflows: the payments that are directly deposited into your bank account and follow the usual [reconciliation](accounting/bank/reconciliation.html) workflow, and those coming from third-party online payment providers and require you to follow another accounting workflow. For these payments, you need to consider how you want to record your payments” journal entries. We recommend you ask your accountant for advice.

By default, the Bank Account defined for the payment journal is used, but you can also specify an [outstanding account](accounting/bank.html#bank-outstanding-accounts) for each payment provider to separate the provider’s payments from other payments.

Vedi anche

  * [Wire transfers](payment_providers/wire_transfer.html)

  * [Addebito Diretto SEPA](payment_providers/sdd.html)

  * [Adyen](payment_providers/adyen.html)

  * [Alipay](payment_providers/alipay.html)

  * [Authorize.Net](payment_providers/authorize.html)

  * [AsiaPay](payment_providers/asiapay.html)

  * [Buckaroo](payment_providers/buckaroo.html)

  * [Demo](payment_providers/demo.html)

  * [Mercado Pago](payment_providers/mercado_pago.html)

  * [Mollie](payment_providers/mollie.html)

  * [Ogone](payment_providers/ogone.html)

  * [PayPal](payment_providers/paypal.html)

  * [Razorpay](payment_providers/razorpay.html)

  * [SIPS](payment_providers/sips.html)

  * [Stripe](payment_providers/stripe.html)

  * [Xendit](payment_providers/xendit.html)

  * [Conti bancari e di cassa](accounting/bank.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_providers/wire_transfer.html "Wire transfers") |
  * [precedente](expenses/reinvoice_expenses.html "Re-invoice expenses") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Online payments


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
  *[POS]: Point Of Sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire