# Close subscriptions — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automatic_alerts.html "Regole di automazione") |
  * [precedente](renewals.html "Renew subscriptions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Close subscriptions



# Close subscriptions¶

Odoo _Subscriptions_ provides flexibility for businesses to decide whether customers can self-manage their subscriptions, or restrict that ability entirely.

## Configurazione¶

Start by navigating to Subscriptions app ‣ Configuration ‣ Recurring Plans. From there, either create a new plan by clicking New or select an existing one to modify it.

Once on the Recurring Plans form, enable the Closable option, in the Self-Service section, to allow customers to close their own subscriptions using the customer portal.

Vedi anche

[Configure recurring plans](plans.html)

## Close a subscription¶

### Administrator view¶

After a quotation for a subscription product has been confirmed, it becomes a sales order, and the subscription status changes to In Progress.

At that point, the ability to close the subscription becomes available, via the Close button at the top of the subscription order, near the row that contains In Progress and other stages. This option is also available after the order has been invoiced and the payment has been registered.

Clicking the Close button prompts a Close Reason pop-up window to appear, allowing administrators to input the reason for closing the subscription, or choose from the drop-down menu of options in the Reason field.

When the desired Reason is entered, click the Submit button.

Clicking Submit on the Close Reason pop-up window updates the subscription sales order to show Churned status tag, along with the specified Close Reason.

That same close reason can be found in the _Chatter_ of the sales order, as well.

### Customer view¶

Nota

As an administrator, the ability to visualize what customers see when managing their subscriptions is accessible via the Preview button, located at the top of the subscription sales order.

From the customer’s point of view, in the customer portal, the Close Subscription button is located on the left side of the sales order.

When the customer clicks the Close Subscription button, a Close Subscription pop-up window appears, in which the customer has to choose from a select list of reasons why they are choosing to close the subscription.

Nota

Customers can _only_ chose a pre-configured reason why the subscription is being closed. They can _not_ enter a custom reason from the customer portal. These selections can be adjusted by navigating to Subscriptions ‣ Configuration ‣ Close Reasons.

Once the customer has chosen a close reason, they would click the Submit button on the pop-up window.

Upon closure, the subscription order in the customer portal is tagged as Closed.

In addition, the specified Close Reason appears on the subscription order in the _Subscriptions_ app in the backend (Administrator’s view).

Vedi anche

  * [Abbonamenti](../subscriptions.html)

  * [Subscription plans](plans.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/subscriptions/closing.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](automatic_alerts.html "Regole di automazione") |
  * [precedente](renewals.html "Renew subscriptions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Close subscriptions


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