# Returns and refunds — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ewallets_giftcards.html "Use eWallets and gift cards") |
  * [precedente](prices/currencies.html "Foreign currencies") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Returns and refunds



# Returns and refunds¶

The Odoo _Sales_ app provides two different ways to process returns. The method used depends on whether or not an invoice has been sent.

## Before invoicing¶

Returns are completed using _Reverse Transfers_ when a customer decides to return a product **before** an invoice has been sent or validated.

Nota

In order to use _Reverse Transfers_ , the _Inventory_ app **must** be installed.

To start a return before invoicing, navigate to the Sales app, select the desired sales order, and click on the Delivery smart button to open the associated delivery order.

On the validated delivery order, click Return.

This opens a Reverse Transfer pop-up window.

By default, the Quantity matches the validated quantities from the delivery order. Update the quantities, if necessary. Click on the 🗑️ (trash) icon next to a line item to remove it from the return.

Next, click Return to confirm the return. This generates a new warehouse operation for the incoming returned product(s).

Upon receiving the return, the warehouse team validates the warehouse operation by clicking Validate. Then, on the original sales order, the Delivered quantity updates to reflect the difference between the initial validated quantities and the returned quantities.

When an invoice is created, the customer receives an invoice **only** for the products they are keeping, if any.

## After invoicing¶

Sometimes, customers return an item after they receive and/or pay for their invoice. In these cases, a return using only _Reverse Transfers_ is insufficient since validated, or sent, invoices cannot be changed.

However, _Reverse Transfers_ can be used in conjunction with _Credit Notes_ to complete the customer’s return.

To start a return after invoicing, navigate to the relevant sales order in the Sales app.

If there is a payment registered on the sales order, the payment details appear in the chatter, and the invoice (accessible through the Invoices smart button) has a green In Payment banner.

From the sales order, click on the Delivery smart button to view the validated delivery order. Then, click Return to open the Reverse Transfer pop-up window.

Next, edit the Product and/or Quantity, as needed for the return. Then, click Return. This generates a new warehouse operation for the incoming returned product(s), which is validated by the warehouse team once the return is received by clicking Validate.

Then, on the sales order, the Delivered quantity updates to reflect the difference between the initial validated quantities and the returned quantities.

To process a refund, navigate to the relevant invoice (from the sales order, click on the Invoices smart button). Then, click the Credit Note button at the top of the validated invoice.

Doing so reveals a Credit Note pop-up form.

Start by entering a Reason displayed on Credit Note and a specific Journal to process the credit. Then, select a specific Reversal Date.

After the information is filled in, click Reverse or Reverse and Create Invoice. Then, edit the draft, if needed.

Lastly, click Confirm to confirm the credit note.

When complete, a blue banner reading: You have outstanding credits for this customer. You can allocate them to mark this invoice as paid. appears at the top of the page.

Vedi anche

[Note di credito e rimborsi](../../../finance/accounting/customer_invoices/credit_notes.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/products_prices/returns.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ewallets_giftcards.html "Use eWallets and gift cards") |
  * [precedente](prices/currencies.html "Foreign currencies") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Returns and refunds


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
  *[PoS]: Point of Sale