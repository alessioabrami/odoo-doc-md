# How to list a product? — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](troubleshooting.html "Troubleshooting eBay connector") |
  * [precedente](setup.html "eBay connector setup") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con eBay](../ebay_connector.html) »
  * How to list a product?



# How to list a product?¶

In order to list a product on eBay and Odoo there are two methods in Odoo to do so:

  1. (_Preferred method_) Make a product in Odoo and list the item eBay.

     * Click List Item on eBay in the top menu of the product template. The product template can be accessed by navigating to Sales app ‣ Products ‣ Product and selecting the individual product.

  2. (_Less preferred method_) List the item on eBay, then create the product in Odoo, and finally link product to the item on eBay.

     * Click Link With Existing eBay Listing in the top menu on the product template.The product template can be accessed by navigating to Sales app ‣ Product ‣ Product and selecting the individual product.




Nota

If an order comes in and the listing from the order is not linked to a product, eBay will create a consumable product.product in its place. These consumables should be altered on the _sales order_ while in draft state to represent a storable product, and then the user can link to the listing as they come in.

Vedi anche

To learn more about the eBay connector visit these pages as well:

  * [eBay connector setup](setup.html)

  * [Linking existing listings](linking_listings.html)

  * [Troubleshooting eBay connector](troubleshooting.html)




## Listing without variation¶

Access the product template by navigating to Sales app ‣ Products ‣ Product and selecting the individual product.

In order to list a product, select the Sell on eBay field on a product template. Sell on eBay is either in an eBay tab or under the Product name. Click Save if necessary.

When the Use Stock Quantity field is checked, the quantity set on eBay is the Odoo _Forecast Quantity_ (Odoo _Inventory_ app).

The policies need to be set in order to be able to list on eBay. A value must be selected for the following fields Payment Policy, Return Policy, and Shipping Policy. The options are imported from the eBay database. If no option appears, they can be imported by navigating to Sales app ‣ Configuration ‣ Settings ‣ eBay, and clicking on the Policies button in the Synchronization field. This button **only** appears once the production and sandbox credentials have been set.

The Description Template allows the administrator to use templates in listings. The default template only uses the eBay Description field of the product. HTML can be used inside the Description Template, and in the eBay Description in Odoo 14. Starting in Odoo 15, the powerbox feature is available to use in the template and description. Simply type a forward slash `/` to reveal a menu with formatting, layout, and text options. To add an image, type `/image`.

To use images in the listing, an image needs to be added as one of the _Attachments_ on the product template.

Vedi anche

For more information on template configuration in Odoo visit: [Modelli e-mail](../../../general/companies/email_template.html).

## Listing with variations¶

When the Sell on eBay is checked on a product containing variations with Fixed Price as Listing Type, the eBay form is slightly different. Go to the Variants tab to or click Configure Variants in the top menu to configure the variant settings. Pricing can be configured for each variation.

When the Listing Type is changed to Fixed Price, Odoo presents a variant table at the bottom of the eBay tab, in which the Fixed Price can be entered, and the decision to Publish on eBay can be made for specific variants, along with other options.

## Product identifiers¶

Products identifiers such as EAN, UPC, Brand or MPN are required in most of the eBay categories.

### EAN and UPC identifiers¶

The module manages the EAN and UPC identifiers with the Barcode field of the product variant. If the Barcode field is empty or is value is not valid, the EAN and UPC values will be set as “Does not apply” as recommended by eBay.

Barcodes can be found on the product template, under the the General Information tab. Access the product template, first, by navigating to Sales app ‣ Products ‣ Product and selecting the individual product.

### Listing with item specifics¶

In order to add item specifics, one should create a product attribute with a single value in the Attributes & Variants tab on the product form. Examples of item specifics include: `MPN` or `Brand`. The Brand and MPN values are working as item specifics and should be defined in the Attributes & Variants tab on the product form. If these values are not set, “Does not apply” will be used for the eBay listing.

## Process invoices and payments¶

### Posting payment¶

When eBay orders are placed they are always paid for up front, via the eBay site. At no point will users pay for items on eBay through Odoo. Therefore, once orders are synced into Odoo from eBay they are already paid for. Odoo’s invoicing and payment functionalities are not utilized. However, invoices need to be created and marked as Paid to “close” the _Sales Order_.

Users can opt to mass create and post invoices in batches. To do so, navigate to Quotations in the list view by going to Sales app ‣ Orders ‣ Quotations. In the upper right corner, select the list view icon. Hover over the icons to reveal the name of each. Then check the boxes on the left that invoices should be made for and go to the Action menu or ⚙️ [Gear icon] . Click on Create Invoices.

A pop-up will appear and click on the Create and view invoice button. A new screen will populate with the newly created invoices. Next, select all of them by clicking on the box icon next to Number in the header row of the list, this will select all the records. Then navigate to the Action menu and click Post entries. Following this step, a pop-up will appear and click on Post journal entries. This will take the invoices out of _draft_ and set them to _posted_.

### Reconciling payments¶

Users typically utilize PayPal to receive payment from eBay, and then send lump sums from PayPal into their bank account. To reconcile this income, users can reconcile the one PayPal transfer with all related invoices.

First navigate to the Accounting Dashboard by going to the Accounting app ‣ Dashboard ‣ Bank. Create a new transaction and enter the Label as `eBay Sales`. Fill out the Amount and enter a Statement date in. Click on Create and edit.

For the Ending Balance field, enter the same account that was entered for the Amount above. Click on Save. Next, open the new balance that needs to be reconciled. Under the tab marked: Match Existing Entries select the entries that are included in this balance.

After adding all the necessary entries, click Validate to complete the reconciliation. To verify the payment, navigate to Customers ‣ Invoices and select the desired customer invoice. The _Paid_ label should appear under the Payment Status column.

Vedi anche

  * [Troubleshooting eBay connector](troubleshooting.html)

  * [Linking existing listings](linking_listings.html)

  * [eBay connector setup](setup.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/ebay_connector/manage.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](troubleshooting.html "Troubleshooting eBay connector") |
  * [precedente](setup.html "eBay connector setup") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con eBay](../ebay_connector.html) »
  * How to list a product?


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