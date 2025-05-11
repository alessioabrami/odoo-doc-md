# Modelli preventivo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](optional_products.html "Prodotti opzionali") |
  * [precedente](create_quotations.html "Creare preventivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Modelli preventivo



# Modelli preventivo¶

In Odoo _Sales_ , salespeople have the ability to create reusable quotation templates for common products or services that the business offers.

By using these templates, quotations can be tailored and sent to customers at a much faster pace, without having to create new quotations from scratch every time a sales negotiation occurs.

## Configurazione¶

Begin by activating the setting in Sales app ‣ Configuration ‣ Settings, and scroll to the Quotations & Orders heading.

In that section, check the box beside the Quotation Templates option. Doing so reveals a new Default Template field, in which a default quotation template can be chosen from a drop-down menu.

Also, upon activating the Quotation Template feature, an internal ➡️ Quotation Templates link appears beneath the Default Template field.

Clicking that link reveals the Quotation Templates page, from which templates can be created, viewed, and edited.

Before leaving the Settings page, don’t forget to click the Save button to save all changes made during the session.

## Create quotation templates¶

Click the Quotation Templates link on the Settings page, or navigate to Sales app ‣ Configuration ‣ Quotation Templates. Both options reveal the Quotation Templates page, where quotation templates can be created, viewed, and edited.

To create a new quotation template, click the New button, located in the upper-left corner. Doing so reveals a blank quotation template form that can be customized in a number of ways.

Start by entering a name for the template in the Quotation Template field.

Then, in the Quotation Validity field, designate how many days the quotation template will remain valid for, or leave the field on the default `0` to keep the template valid indefinitely.

Next, in the Confirmation Mail field, click the blank field to reveal a drop-down menu. From the drop-down menu, select a pre-configured email template to be sent to customers upon confirmation of an order.

Suggerimento

To create a new email template directly from the Confirmation Mail field, start typing the name of the new email template in the field, and select either: Create or Create and edit… from the drop-down menu that appears.

Selecting Create creates the email template, which can be edited later.

Selecting Create and edit… creates the email template, and a Create Confirmation Mail pop-up window appears, in which the email template can be customized and configured right away.

When all modifications are complete, click Save & Close to save the email template and return to the quotation form.

If working in a multi-company environment, use the Company field to designate to which company this quotation template applies.

If a journal is set in the Invoicing Journal field, all sales orders with this template will invoice in that specified journal. If no journal is set in this field, the sales journal with the lowest sequence is used.

If the Online Signature and/or Online Payment features are activated in the Settings (Sales app ‣ Configuration ‣ Settings), those options are available on quotation template forms.

Check the box beside Online Signature to request an online signature from the customer to confirm an order.

Check the box beside Online Payment to request an online payment from the customer to confirm an order. When Online Payment is checked, a new percentage field appears, in which a specific percentage of payment can be entered.

Both options, Online Signature and Online Payment can be enabled simultaneously, in which case the customer must provide **both** a signature **and** a payment to confirm an order.

In the Recurring Plan field, choose from a variety of pre-configured amounts of time (e.g. Monthly, Quarterly, etc.) to designate how often this quotation template should occur.

Nota

The Recurring Plan field **only** applies to subscription plans. For more information, check out the documentation on [Subscription plans](../../subscriptions/plans.html).

### Lines tab¶

In the Lines tab, products can be added to the quotation template by clicking Add a product, organized by clicking Add a section (and dragging/dropping section headers), and further explained with discretionary information (such as warranty details, terms, etc.) by clicking Add a note.

To add a product to a quotation template, click Add a product in the Lines tab of a quotation template form. Doing so reveals a blank field in the Product column.

When clicked, a drop-down menu with existing products in the database appear. Select the desired product from the drop-down menu to add it to the quotation template.

If the desired product isn’t readily visible, type the name of the desired product in the Product field, and the option appears in the drop-down menu. Products can also be found by clicking Search More… from the drop-down menu.

Suggerimento

In Odoo 17, it is now possible to add event-related products (booths and registrations) to quotation templates. To do so, click the Product field, type in `Event`, and select the desired event-related product from the resulting drop-down menu.

Nota

When a product is added to a quotation template, the default Quantity is `1`, but that can be edited at any time.

Then, drag-and-drop the product to the desired position, via the six squares icon, located to the left of each line item.

To add a _section_ , which serves as a header to organize the lines of a sales order, click Add a section in the Lines tab. When clicked, a blank field appears, in which the desired name of the section can be typed. When the name has been entered, click away to secure the section name.

Then, drag-and-drop the section name to the desired position, via the six squares icon, located to the left of each line item.

To add a note, which would appear as a piece of text for the customer on the quotation, click Add a note in the Lines tab. When clicked, a blank field appears, in which the desired note can be typed. When the note has been entered, click away to secure the note.

Then, drag-and-drop the note to the desired position, via the six squares icon.

To delete any line item from the Lines tab (product, section, and/or note), click the 🗑️ (trash can) icon on the far-right side of the line.

### Scheda prodotti opzionali¶

The use of _optional products_ is a marketing strategy that involves the cross-selling of products along with a core product. The aim is to offer useful and related products to customers, which may result in an increased sale.

Ad esempio, se un cliente vuole acquistare un’auto, può scegliere se ordinare anche i sedili massaggianti o ignorare l’offerta e acquistare semplicemente l’auto. La scelta di acquistare prodotti opzionali migliora l’esperienza del cliente.

Optional products appear as a section on the bottom of sales orders and eCommerce pages. Customers can immediately add them to their online sales orders themselves, if desired.

In the Optional Products tab, Add a line for each cross-selling product related to the original items in the Lines tab, if applicable. The products added here ideally complement the original offering as added value for the prospective buyer.

Clicking Add a line reveals a blank field in the Product column.

Una volta fatto clic, appare un menu a tendina con i prodotti del database. Seleziona il prodotto desiderato dal menu a discesa per aggiungerlo come prodotto opzionale al modello di preventivo.

Per eliminare qualsiasi riga con articoli dalla scheda Prodotti opzionali, fai clic sull’icona 🗑️ (cestino).

Nota

Optional products are **not** required to create a quotation template.

### Terms & Conditions tab¶

The Terms & Conditions tab provides the opportunity to add terms and conditions to the quotation template. To add terms and conditions, simply type (or copy/paste) the desired terms and conditions in this tab.

Vedi anche

[Termini e condizioni predefiniti](../../../finance/accounting/customer_invoices/terms_conditions.html)

Nota

Terms and conditions are **not** required to create a quotation template.

### PDF Quote Builder tab¶

The PDF Quote Builder tab provides options to compose an attractive quotation, with more information and visually-pleasing elements, to highlight products and/or services.

To upload customer Header pages and Footer pages, click the ✏️ (pencil) icon to the right of the respective pages. Click the 🗑️ (trash) icon to delete an uploaded PDF.

Vedi anche

[Creazione preventivi in PDF](pdf_quote_builder.html)

## Use quotation templates¶

When creating a quotation (Sales app ‣ New), choose a pre-configured template in the Quotation Template field.

To view what the customer will see, click the Preview button at the top of the page to see how the quotation template appears on the front-end of the website through Odoo’s customer portal.

Suggerimento

Quotation template design uses the same methodology and functionality with design building blocks as a typical web page design with Odoo _Website_. Be sure to check out the [Sito web](../../../websites/website.html) documentation to learn more.

When all blocks and customizations are complete, click the Save button to put those configurations into place.

There is also a blue banner at the top of the quotation template design with a link to quickly return Back to edit mode. When clicked, Odoo returns to the quotation form in the back-end of the _Sales_ application.

## Mass cancel quotations/sales orders¶

Cancel multiple quotations (or sales orders) by navigating to the Sales app ‣ Orders ‣ Quotations dashboard, landing, by default, in the list view. Then, on the left side of the table, tick the preferred checkboxes for removal.

Suggerimento

Select all records in the table by selecting the checkbox column header at the top-left of the table; the total number of selected items are displayed at the top of the page.

Then, with the desired quotations (or sales orders) selected from the list view on the Quotations page, click the __ Actions button to reveal a drop-down menu.

From this drop-down menu, select Cancel quotations.

Nota

This action can be performed for quotations in _any_ stage, even if it is confirmed as a sales order.

Upon selecting the Cancel quotations option, a Cancel quotations confirmation pop-up window appears. To complete the cancellation, click the Cancel quotations button.

Nota

An error pop-up message appears when attempting to cancel an order for an ongoing subscription that has an invoice.

Vedi anche

  * [Firme online per confermare gli ordini](get_signature_to_validate.html)

  * [Conferma ordine tramite pagamento online](get_paid_to_validate.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/quote_template.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](optional_products.html "Prodotti opzionali") |
  * [precedente](create_quotations.html "Creare preventivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Modelli preventivo


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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface