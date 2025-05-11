# Abbonamenti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subscriptions/ecommerce.html "Subscriptions in the eCommerce shop") |
  * [precedente](point_of_sale/reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Abbonamenti



# Abbonamenti¶

The Odoo **Subscriptions** app is designed to manage recurring revenue through subscription-based products or services. It supports automated invoicing, renewal management, and customer lifecycle tracking.

Subscriptions can be created manually or automatically through online sales, with varying options for recurring billing. The app integrates with other Odoo modules such as **Invoicing** , **CRM** , **Sales** , and **Helpdesk** to support end-to-end subscription workflows.

#### [Subscription plansCustomize subscription plan templates tailored to various product offerings ](subscriptions/plans.html)#### [Renew a subscriptionUnderstand the core management activity for subscriptions ](subscriptions/plans.html)#### [Upsell a subscriptionOffer more value for current subscribers on the same sales order ](subscriptions/plans.html)#### [Integrate subscriptions with eCommerceOffer subscription products with an Odoo **eCommerce** app integration ](subscriptions/plans.html)

Vedi anche

  * [Odoo Tutorials: Subscriptions](https://www.odoo.com/slides/subscription-20)




## Set up recurring plans¶

To get started with subscription products in Odoo, _recurring plans_ (previously known as _recurrence periods_) must first be configured.

Recurring plans are the time windows in which subscriptions are active before they renew again. While a subscription is active, customers receive products or services, and may also have access to additional benefits such as support desk triage. In terms of payment, these recurring plans designate how often the customer is charged in order to maintain the benefits of their subscription.

To configure recurring plans, go to Subscriptions app ‣ Configuration ‣ Recurring Plans.

By default, the **Subscriptions** app includes a number of common recurring plans already available, such as Monthly and Yearly.

Create a new recurring plan by clicking New on the Recurring Plans dashboard, to reveal a blank form where the plan Name, DETAILS, SELF-SERVICE and Pricing field values are specified.

Importante

The `Days` unit of measure _cannot_ be used as a Billing Period for subscription products. The daily recurrence period in Odoo is designated for rentals, and **cannot** be added to subscription-based sales orders.

This limitation is there to avoid sales orders that would generate daily invoices.

### DETAILS section¶

After giving the recurring plan a suitable Name (e.g. `Monthly`, `Bi-weekly`, `Quarterly`, etc.), proceed to the form’s DETAILS section to fill out the following configuration fields:

  * Billing Period: determines the recurrence period of the recurring plan. Set the numerical value in the text field and contextualize the quantity with a unit of time in the corresponding drop-down menu, in Weeks, Months, or Years.

  * Automatic Closing: a numerical value, in days, where the subscription is set to close automatically if payment is not made.

Example

If a subscription is set to renew on the 1st of every month, and the Automatic Closing value is set to `15` Days, then the subscription will close on the 16th of that month if payment is not received.

  * Company: optional assignment, if the database has [Multi-company](../general/multi_company.html) functionality enabled. Assigning this value will make the recurring plan available for that company’s location, specifically.

  * Invoice Email Template: assigns a specific email template to be used in subscriptions invoicing communications. The default assignment here is `Invoice: Sending` which contains various dynamic fields that autopopulate specific variables across the Subject field and Content tab, such as the customer’s name, invoice number, total amount invoiced, etc.

Suggerimento

Although this field is optional, it is recommended to use it since this type of communication fulfills good business practices around price transparency, regular customer communication (especially as it relates to charged amounts), and helps build contextual financial documentation around recurring revenues.

The `Invoice: Sending` email template is accessible by clicking the __( Internal link) that appears after hovering over the Invoice Email Template drop-down field in the Recurring Plans form.¶




### SELF-SERVICE section¶

The following optional fields enable customers to take administrative actions on their own subscriptions. Enabling any of these options may decrease customer service request volume or increase customer lifetime value (LTV).

  * Closable: checking this box will give customers the power to close their own subscriptions. Consider enabling this option to reduce customer service requests and improve the overall customer experience; customers that can manage their own subscriptions in this way helps offload tedious tasks for sales and support teams, and reduces the likelihood of negative reviews.

Suggerimento

Although this option is generally advisable to enable, sales teams with strong customer offboarding processes may consider leaving this option unchecked in order to force an interaction that might save the subscription or a different form of recurring revenue (such as in the case of a lesser subscription or a new trial period with an alternative plan).

  * Add Products: allows customers to add new products or edit existing product quantities to their recurring sales orders, thereby enabling customer-driven upselling. When enabled, [Upsell quotations](subscriptions/upselling.html) are generated in Odoo whenever a customer performs a quantitative adjustment on their sales order product lines.

  * Renew: enabling this allows customers to manually create a [Renewal quotation](subscriptions/renewals.html) for their subscription.

  * Optional Plans: adding values here from the drop-down field menu enables customers to switch their subscription plans, in which case a new subscription quotation or renewal quote is created to accommodate the change request.




### Pricing tab¶

Make product-specific pricing adjustments, as part of the recurring plan, by adding them to the Pricing tab order lines. Sequentially add the Products, along with any respective Product Variants, and then assign a Pricelist (if available) and a Recurring Price.

Nota

Price rules that are added here take precedent over the default pricing information on the subscription product’s form. This is meant to accommodate deals, discounts, and similar pricing adjustment strategies that would incentivize customers to purchase the recurring plan.

## Product form configuration¶

With recurring plans set up, create a subscription product by navigating to Subscriptions app ‣ Products ‣ Products, and click either an existing product to edit, or make a new one by clicking New to open up the subscription product’s form.

Nota

By default, the Recurring option is already enabled, prompting Odoo to recognize it as a subscription product. Be sure to leave the Recurring and Can be Sold options enabled.

On the product form, configure the following items in the General Information tab so the subscription product will function correctly:

  * Product type: this value is typically set to a Service, however other product types may be used depending on the purpose of the subscription (e.g., physical product box subscriptions, eLearning course, etc.).

  * [Invoicing policy](sales/invoicing/invoicing_policy.html): set this value to when the customer should be charged for their subscription.

  * Unit of Measure: how the product should be counted in Odoo, for stock purposes. For most subscriptions, the UoM will be Units.

  * Sales Price: enter the recurring cost of the subscription that the customer will pay per recurrence period.




Optionally set up information on the [Attributes & Variants](sales/products_prices/products/variants.html) tab if the subscription contains multiple choices for customers (i.e. food delivery, tailored fashion boxes, etc.).

In the Recurring Prices tab, clarify the pricing options for the subscription. For each option available, click Add a price rule to add a new row.

Suggerimento

Longer time Recurring Plan time periods are typically incentivized with cost savings. Consider dropping the total Recurring Price values to offer customers a discount while supporting the business’s financial runway.

Last, if the subscription is meant to be purchased on the **eCommerce** website, click the __ Go To Website smart button and in the product page header, click the gray slider from Unpublished to the green Published status.

## Create a subscriptions quotation¶

Manually create a new customer subscription by navigating to either the Sales or Subscriptions app dashboards, and then clicking New.

Nota

Products that have been marked as Recurring on their product forms, and are also sold on the **eCommerce** website will _automatically_ create and confirm subscription quotations in the backend of Odoo.

Importante

Sales orders with a defined recurring plan automatically become subscriptions.

On the quotation form, fill in the necessary fields such as Customer and Recurring Plan, as well as the Order Lines tab.

Optionally, specify a:

  * [Quotation Template](sales/send_quotations/quote_template.html), if one is readily available to help populate the form fields.

  * Expiration date, to indicate when the subscription offer is no longer valid.

Suggerimento

Expiration dates pair well with [discounts](sales/products_prices/prices/pricing.html#sales-products-prices-discounts) to incentivize faster purchases, since the discount will expire with the quotation if it’s not turned into a sales order within the specified date range.

  * [Pricelist](sales/products_prices/prices/pricing.html#sales-product-prices-pricelist), if one is available and appropriate to use (i.e., summer sale discount, VIP customer, etc.).

  * Payment Terms, to set a specified time window for when the subscription must be paid. This is not to be confused for when the quotation is _confirmed_ and becomes a sales order, to where, payment may then be obtained immediately or within a certain amount of days, weeks, months, etc.




Suggerimento

Define different invoice and delivery addresses by enabling the [Customer Addresses](../finance/accounting/customer_invoices/customer_addresses.html) feature.

## Conferma¶

Send the quotation to the customer for confirmation by clicking on Send By Email, or confirm it immediately by clicking on Confirm.

Suggerimento

Click on Preview to preview the customer portal where the customer can view their quotation, sign and pay it, and communicate with you.

If an Online signature or Online payment is required to confirm the quotation, set the checkboxes next to either (or both) of these labels in the Other Info tab, under the :SALES section.

Vedi anche

  * [Online payments](../finance/accounting/payments/online.html)

  * [Payment providers and payment methods](../finance/payment_providers.html)




  * [Subscriptions in the eCommerce shop](subscriptions/ecommerce.html)
  * [Subscription plans](subscriptions/plans.html)
  * [Upsell subscriptions](subscriptions/upselling.html)
  * [Renew subscriptions](subscriptions/renewals.html)
  * [Close subscriptions](subscriptions/closing.html)
  * [Regole di automazione](subscriptions/automatic_alerts.html)
  * [Scheduled actions](subscriptions/scheduled_actions.html)
  * [Subscription reports](subscriptions/reports.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/subscriptions.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subscriptions/ecommerce.html "Subscriptions in the eCommerce shop") |
  * [precedente](point_of_sale/reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Abbonamenti


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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