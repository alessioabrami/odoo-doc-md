# Punto vendita — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](point_of_sale/configuration.html "Configurazione") |
  * [precedente](sales/ebay_connector/linking_listings.html "Linking existing listings") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Punto vendita



# Punto vendita¶

With **Odoo Point of Sale** , run your shops and restaurants easily. The app works on any device with a web browser, even if you are temporarily offline. Product moves are automatically registered in your stock, you get real-time statistics, and your data is consolidated across all shops.

Vedi anche

  * [Odoo Tutorials: Point of Sale Tutorials](https://www.odoo.com/slides/point-of-sale-28)

  * [IoT Boxes Documentations](../general/iot.html)




## Start a session¶

From the **POS dashboard** , click New Session, and at the Opening Cash Control screen, click Open Session to start a POS session, or click Continue Selling if the session is already opened.

Nota

[Multiple users](point_of_sale/employee_login.html) can be logged into the same session at the same time. However, the session can only be opened once on the same browser.

## Sell products¶

Click on products to add them to the cart. To change the **quantity** , click Qty and enter the number of products using the keypad. To add a **discount** or modify the product **price** , click respectively % Disc or Price and enter the amounts.

Once an order is completed, proceed to checkout by clicking Payment. Select the **payment method** , enter the received amount, and click Validate. Click New Order to move on to the next customer.

Suggerimento

  * You can use both `,` and `.` on your keyboard as decimal separators.

  * **Cash** is selected by default if you enter the amount without choosing a payment method.




Nota

The system can only load a limited number of products for effective opening. Click Search more if the desired product is not loaded automatically.

## Set customers¶

Registering your customer is necessary to [collect their loyalty points and grant them rewards](point_of_sale/pricing/loyalty.html), automatically apply the [attributed pricelist](point_of_sale/pricing/pricelists.html), or [generate and print an invoice](point_of_sale/receipts_invoices.html#receipts-invoices-invoices).

You can create customers from an open POS session by clicking Customer ‣ Create, and filling in the contact information. You can also create customers from the backend by going to Point of Sale ‣ Orders ‣ Customers and clicking New. Then, fill in the information and save.

To set a customer during an order, access the list of customers by clicking Customer on the POS interface. You can also set a customer at the payment screen by clicking Customer.

## Customer notes¶

You can add **customer notes** about specific products directly from an open POS session. For instance, to provide cleaning and maintenance tips. They can also be used to track a customer’s particular request, such as not wanting the product to be assembled for them.

To do so, select a product and click Customer Note on the pad. Doing so opens a pop-up window in which you can add or modify content for the note.

Nota

Product notes from an [imported SO](point_of_sale/shop/sales_order.html) are displayed identically in the cart.

Customer notes appear on customers” receipts and invoices similarly to how they appear in the cart, under the related product.

## Return and refund products¶

To return and refund a product,

  1. start a session from the **POS dashboard** ;

  2. click Refund and select the corresponding order;

  3. select the product and the quantity to refund using the keypad;

  4. click Refund to go back to the previous screen;

  5. once the order is completed, click Payment to proceed to the refund;

  6. click Validate and New Order to move on to the next customer.




Nota

  * You can filter the **orders list** by Receipt Number, Date or Customer using the search bar.

  * You can also refund a product by selecting the returned product from an open session, and setting a negative quantity that equals the number of returned products. To do so, click Qty and +/-, followed by the quantity of returned products.




Once the return payment is validated, Odoo generates the required credit note, referencing the original receipt or invoice and partially or fully canceling the document.

## Manage the cash register¶

To add or take out cash from the register, click the **menu icon** in the upper right corner of your screen and Cash In/Out.

Doing so opens a pop-up window on which you can select Cash In or Cash Out, enter the amount and the reason, and click Confirm.

## Close the POS session¶

To close your session, click the **menu icon** in the upper right corner of your screen and Close Session.

Doing so opens the Closing Control pop-up screen. From this screen, you can retrieve various information:

  * the number of orders made and the total amount made during the session;

  * the expected amounts grouped by payment method.




Before closing this window, count your cash using the calculator icon. Doing so opens a pop-up window that computes the total amount in the cash drawer depending on the coins and bills counted and added manually. Then, click Confirm or Discard to close the window. The computed amount is set in the Counted column, and the Money Details are specified in the **Notes** section.

Once you are done controlling the amounts, click Close Session to close and go back to the **POS dashboard**.

Nota

  * To reach the backend without closing the session, click Backend on the dropdown menu.

  * To abort, click Discard on the pop-up window.

  * Depending on your setup, you might only be allowed to close a session if the expected cash revenue equals the counted cash. To close it anyway, click Ok on the Payments Difference screen.




Suggerimento

  * It is strongly advised to close your POS session at the end of each day.

  * To look at all your previous sessions, go to Point of Sale ‣ Orders ‣ Sessions.




## Analitiche¶

Once you close and post the POS session, access the comprehensive report to review all session activities, including who initiated the session and who handled specific orders. To access the session’s report:

  1. Click __( vertical ellipsis) on the POS card.

  2. Click Sessions under the View section.

  3. From that list view, you can see all the sessions and who initiated them under the Opened By column.

  4. Select a POS session to open a detailed session report.

  5. Click the Orders smart button to display a list of all orders placed during that session.

  6. From that view, you can retrieve the following information:

     * The Order Ref

     * The Date of the order.

     * The Point of Sale where that order was made.

     * The Receipt Number.

     * The Customer.

     * The Employee that placed this order.

     * The Total paid amount.

     * The order Status.




To get an overview of all orders, regardless of the session, click the vertical ellipsis button (⋮) on the POS card and select Orders from the View section.

  * [Configurazione](point_of_sale/configuration.html)
    * [IoT system connection](point_of_sale/configuration/pos_iot.html)
    * [ePOS printers](point_of_sale/configuration/epos_printers.html)
    * [Secure connection (HTTPS)](point_of_sale/configuration/https.html)
    * [Self-signed certificate for ePOS printers](point_of_sale/configuration/epos_ssc.html)
  * [Multi-employee management](point_of_sale/employee_login.html)
  * [Receipts and invoices](point_of_sale/receipts_invoices.html)
  * [Schermo di preparazione](point_of_sale/preparation.html)
  * [Self-ordering](point_of_sale/self_order.html)
  * [Product combos](point_of_sale/combos.html)
  * Shop features
    * [Sales orders](point_of_sale/shop/sales_order.html)
    * [Codici a barre](point_of_sale/shop/barcode.html)
    * [Serial numbers and lots](point_of_sale/shop/serial_numbers.html)
    * [Ship later](point_of_sale/shop/ship_later.html)
    * [Schermo cliente](point_of_sale/shop/customer_display.html)
  * [Restaurant features](point_of_sale/restaurant.html)
    * [Floors and tables](point_of_sale/restaurant/floors_tables.html)
    * [Orders printing](point_of_sale/restaurant/kitchen_printing.html)
    * [Fatture](point_of_sale/restaurant/bill_printing.html)
    * [Mance](point_of_sale/restaurant/tips.html)
  * Pricing features
    * [Sconti](point_of_sale/pricing/discounts.html)
    * [Discount tags (barcode scanner)](point_of_sale/pricing/discount_tags.html)
    * [Loyalty programs](point_of_sale/pricing/loyalty.html)
    * [Listini prezzi](point_of_sale/pricing/pricelists.html)
    * [Flexible taxes (fiscal positions)](point_of_sale/pricing/fiscal_position.html)
    * [Arrotondamento di cassa](point_of_sale/pricing/cash_rounding.html)
    * [Electronic shelf labels](point_of_sale/pricing/electronic_labels.html)
  * [Metodo di pagamento](point_of_sale/payment_methods.html)
    * [Payment terminals](point_of_sale/payment_methods/terminals.html)
      * [Adyen](point_of_sale/payment_methods/terminals/adyen.html)
      * [Ingenico](point_of_sale/payment_methods/terminals/ingenico.html)
      * [Mercado Pago](point_of_sale/payment_methods/terminals/mercado_pago.html)
      * [Razorpay](point_of_sale/payment_methods/terminals/razorpay.html)
      * [SIX](point_of_sale/payment_methods/terminals/six.html)
      * [Stripe](point_of_sale/payment_methods/terminals/stripe.html)
      * [Vantiv](point_of_sale/payment_methods/terminals/vantiv.html)
      * [Viva Wallet](point_of_sale/payment_methods/terminals/viva_wallet.html)
      * [Worldline](point_of_sale/payment_methods/terminals/worldline.html)
  * [Rendiconto](point_of_sale/reporting.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](point_of_sale/configuration.html "Configurazione") |
  * [precedente](sales/ebay_connector/linking_listings.html "Linking existing listings") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Punto vendita


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