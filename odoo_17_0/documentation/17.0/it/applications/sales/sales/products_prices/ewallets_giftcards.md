# Use eWallets and gift cards — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](loyalty_discount.html "Discount and loyalty programs") |
  * [precedente](returns.html "Returns and refunds") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Use eWallets and gift cards



# Use eWallets and gift cards¶

With Odoo, customers can use **eWallets** and **gift cards** for online and in-store shopping.

To enable eWallets and gift cards for eCommerce and Point of Sale (PoS), first enable Discounts, Loyalty & Gift Card under Sales app ‣ Configuration ‣ Settings ‣ Pricing section. Once enabled, go to Sales app ‣ Products ‣ Gift cards & eWallet and Create a new eWallet or gift card program.

## Portafoglio elettronico¶

eWallets allow customers to save credits on their online account and use these credits as a payment method when buying items in an online store or a brick-and-mortar store. eWallets can also be used to centralize multiple gift cards.

Before creating an eWallet program, it is necessary to create an eWallet **top-up** product. Top-ups are pre-defined digital credit values added to an eWallet in exchange for its equivalent in real currency. These credits can then be used as a payment method in the eCommerce shop or PoS. Top-up values can be of different amounts.

Example

A $50 top-up can be bought for $50, and adds that same amount of credits to the eWallet.

To create a top-up product, go to Sales app ‣ Products ‣ Products and Create a new product. On the product template, configure the options as follows:

  * Product Name: enter a name for the top-up product (for example, `$50 Top-Up`)

  * Can be Sold: enabled

  * Product Type: select Service

  * Invoicing Policy: select Prepaid/Fixed Price

  * Create on Order: select Nothing

  * Sales Price: enter the amount of the top-up




Nota

In order to have eWallet top-ups of different amounts, create multiple top-up products and modify the Sales Price accordingly.

Once the top-up is created, go to Sales app ‣ Products ‣ Gift cards & eWallet to Create an eWallet program. The following configuration options are available:

  * Program Name: enter a name for the eWallet program

  * Program Type: select eWallet

  * eWallet Products: select the eWallet top-up created earlier. Repeat the process if you created top-ups of different amounts.

  * Email template: select the email template used for the email sent to the customer. To create a new template, click on the field, select Search More, and then click Create.

  * Currency: select the currency to use for the eWallet program

  * Company: select the company for which the program is valid and available

  * Available On: select the applications on which the program is valid and available

  * Website: select the website on which the program is valid and available. Leave this field empty to include all websites.

  * Point of Sale: select the PoS in which the program is valid and available. Leave this field empty to include all PoS.




Once the program is configured, click the Generate eWallet button in the upper-left corner to generate eWallets. eWallets can be generated based on Customers and/or Customer Tags. The quantity is automatically adapted according to the Customers and Customer Tags selected. Then, set the eWallet value. Finally, set the Valid Until period if applicable.

Generated eWallets can be accessed through the eWallets smart button in the upper-right corner. From there, Send or Share the eWallets via email or a URL link.

Click on an eWallet to change the Expiration Date, Partner, or Balance. The Code of an eWallet _cannot_ be changed, deleted, or duplicated.

## Gift cards¶

Gift cards can be purchased by customers, and in turn used as a payment method upon checkout at an eCommerce shop or PoS.

Before creating a new gift card program, it is necessary to first create gift cards as products. To do so, go to Sales app ‣ Products ‣ Products and Create a product. On the product template, configure the options as follows:

  * Product Name: enter a name for the gift card product

  * Can be Sold: enabled

  * Product Type: select Service

  * Invoicing Policy: select Prepaid/Fixed Price

  * Create on Order: select Nothing

  * Sales Price: enter the amount of the gift card




Nota

In order to have gift cards of different amounts, create multiple gift card products and modify the Sales Price accordingly.

Once the gift card product is created, go to Sales app ‣ Products ‣ Gift cards & eWallet to Create a gift card program. The following configuration options are available:

  * Program Name: enter a name for the gift card program

  * Program Type: select Gift Card

  * Gift Card Products: select the gift card product created earlier. Repeat the process if you created gift card products of different amounts.

  * Email template: select the default Gift Card: Gift Card Information template, or create a new template by clicking on the field, selecting Search More, and then clicking Create.

  * Print Report: select Gift Card

  * Currency: select the currency to use for the gift card program

  * Company: select the company for which the program is valid and available

  * Available On: select the applications on which the program is valid and available

  * Website: select the website on which the program is valid and available. Leave this field empty to include all websites.

  * Point of Sale: select the PoS in which the program is valid and available. Leave this field empty to include all PoS.




Once the program is configured, click the Generate Gift Cards button in the upper-left corner to generate gift cards. Gift cards can be generated either for Anonymous Customers or Selected Customers. Set the Quantity to generate for Anonymous Customers, or select the Customers and/or Customer Tags for Selected Customers. Then, set the Gift Card value. Finally, set the Valid Until period if applicable.

Generated gift cards can be accessed through the Gift Cards smart button in the upper-right corner. From there, Send or Share the gift cards via email or a URL link.

Click on a gift card to change the Expiration Date, Partner, or Balance. The Code of a gift card _cannot_ be changed, deleted, or duplicated.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/products_prices/ewallets_giftcards.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](loyalty_discount.html "Discount and loyalty programs") |
  * [precedente](returns.html "Returns and refunds") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Products & Prices](../products_prices.html) »
  * Use eWallets and gift cards


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