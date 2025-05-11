# Self-ordering — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](combos.html "Product combos") |
  * [precedente](preparation.html "Schermo di preparazione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Self-ordering



# Self-ordering¶

The self-ordering feature allows customers to browse your menu or product catalog, place an order, and complete payment using their mobile device or a self-ordering kiosk.

## Configurazione¶

### Feature activation¶

To enable this feature and select a self-ordering type, access the [POS settings](configuration.html#configuration-settings), scroll down to the Mobile self-order & Kiosk section, and select a Self Ordering type under the QR menu & Kiosk activation section.

You can choose from:

QR menuKiosk

Select QR menu or QR menu + Ordering to give customers access to your menu or product catalog by scanning a QR code on their personal device. The latter also allows them to place an order and make a payment.

  * Click __ Print QR Codes to download a .pdf document with the generated QR codes.

  * Click __ Download QR Codes to download a compressed file with the generated QR codes.




Nota

In **restaurants** , printing or downloading QR codes generates as many QR codes as the number of available tables. In **shops** , it generates only one generic QR code.

Suggerimento

To customize QR codes,

  1. Scan the relevant QR code to acquire its URL.

  2. Use a QR code generator (e.g., [QR code monkey](https://www.qrcode-monkey.com/) or [QR code generator](https://www.qr-code-generator.com/)) to create a custom QR code.




When Kiosk is selected, customers can access the menu or product catalog, place orders, and pay from a self-ordering kiosk.

Once a self-ordering type is selected, the additional settings update to fit the selected type’s needs.

### Additional settings¶

Home buttonsService location and payment optionsLanguageSplash screensEat in/ Take out

The Home buttons are displayed on the kiosk or mobile device interfaces when customers are self-ordering. To set them up, click __ Home buttons. Then,

  1. Click New to add a new button.

  2. Set the Label.

  3. Enter a URL preceded by `https://` to redirect customers to a specific URL when clicking the button. For instance, you might want to redirect them to a campaign video for a new product or to a contest page.

  4. In the same URL column, enter `/products` to create a button that redirects customers to the product catalog.

  5. Select the Points of Sale to ensure this button only appears on the selected POS” self-ordering interface.

  6. Select a predefined Style from the dropdown menu.




Nota

  * Leaving the Points of Sale field empty shares the button with all POS.

  * The Preview column automatically updates, giving you a glimpse of the button’s appearance based on its configuration.




  * Set where the service occurs by selecting Table or Pickup zone under the Service field.

  * Define when and how customers pay in the Pay after field. Customers can pay after Each meal or for Each order.

  * The service location and payment options available depend on the type of self-ordering service and POS:

    * **QR menu + Ordering** :

      * **Restaurants** : Customers can be served at their table or the pickup zone.

        * When served at their table, they can pay after each meal or each order.

        * When served at the pickup zone, they can only pay after each order.

      * **Shops** : Customers can only be served at the pickup zone and pay after each order.

      * Regardless of the type of POS, customers can pay [online](../../finance/payment_providers.html) or using any configured [payment method](payment_methods.html).

    * **Kiosk** :

      * Regardless of the type of POS, customers can either be served at their table or in the pickup zone, but they must pay after each order.

      * The kiosk self-ordering only works with [Adyen](payment_methods/terminals/adyen.html) and [Stripe](payment_methods/terminals/stripe.html) terminals.

      * The Online Payment feature is not supported.




Vedi anche

  * [Online payments](../../finance/payment_providers.html)

  * [Metodo di pagamento](payment_methods.html)




This option allows you to enable multiple languages for the self-ordering interface. The suggested languages are those already installed in Odoo. To expand the selection, add more languages:

  1. Click __ Add Languages.

  2. Add as many languages as needed to the Languages field.

  3. Fai clic su Aggiungi.

  4. Add those languages to the Available field.




Vedi anche

[Modificare la lingua](../../general/users/language.html)

Splash screens are introductory screens displayed when the self-ordering interface or kiosk is launched. They typically contain branding, welcome messages, or usage instructions.

  * To add a splash screen image, click __ Add images, select and open an image.

  * To remove a splash screen image, hover over the image and click __( Delete).




Nota

You can add multiple splash screen images at once.

Activate this setting to [adjust the tax rate](pricing/fiscal_position.html) based on whether customers dine in or take their order to go. Then,

  * Fill in the field with an existing Alternative Fiscal Position;

  * Create and set up a new fiscal position by filling in the field and clicking Create & Edit; or

  * Create and set up a new fiscal position by clicking __ Fiscal Positions.




Vedi anche

[Flexible taxes (fiscal positions)](pricing/fiscal_position.html)

### Anteprima¶

Review the interface before making the self-ordering feature available to customers to ensure all settings are applied correctly. Click __ Preview Web interface under the Self Ordering field to ensure all additional settings are correctly applied.

## Usage guidelines¶

QR menuKiosk

On the POS user’s end, access the self-ordering interface by

  * Scanning a downloaded or printed QR code; or

  * Clicking the __( vertical ellipsis) icon on the POS card, then Mobile Menu.




On the customers” end,

  1. Access the self-ordering interface by scanning a downloaded or printed QR code.

  2. Click the home button to reach the menu or catalog.

  3. Select the items and click Order to place an order.

  4. Follow the instructions on-screen to assign a table and pay for the order.




On the POS user’s end,

  1. Click Start Kiosk.

  2. Open the provided URL on the self-ordering kiosk(s).

     * Copy and paste it; or

     * Click Open in New Tab.




Nota

  * Once a session is open, Start Kiosk switches to Open Kiosk on the POS card.

  * Click Open Kiosk on the POS card to reopen the popup window and access the self-ordering interface.




On the customers” end,

  1. Click the home button from a self-ordering kiosk to reach the menu or product catalog.

  2. Select the items and click Order to place an order.

  3. Follow the instructions on-screen to assign a table and pay for the order.




Importante

  * A POS session must be open for customers to place an order.

  * Once an order is placed, it is automatically sent to [the preparation screen](preparation.html) and added to the list of POS orders.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/self_order.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](combos.html "Product combos") |
  * [precedente](preparation.html "Schermo di preparazione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Self-ordering


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