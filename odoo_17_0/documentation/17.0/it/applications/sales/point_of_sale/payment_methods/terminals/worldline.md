# Worldline — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../reporting.html "Rendiconto") |
  * [precedente](viva_wallet.html "Viva Wallet") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Worldline



# Worldline¶

Connecting a payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Importante

  * Worldline payment terminals require an [IoT Box](../../../../general/iot.html).

  * Worldline is currently only available in Belgium, the Netherlands and Luxembourg.

  * Odoo is compatible with Worldline terminals that use the CTEP protocol (e.g., the Yomani XR and Yoximo terminals). If you have any doubts, contact your payment provider to ensure your terminal’s compatibility.




## Configurazione¶

### Connect an IoT system¶

Connecting a Worldline Payment Terminal to Odoo is a feature that requires an IoT system. For more information on how to connect one to your database, please refer to the [IoT documentation](../../../../general/iot.html).

### Configure the protocol¶

From your terminal, click on «.» ‣ 3 ‣ stop ‣ 3 ‣ 0 ‣ 9. Enter the technician password **«1235789»** and click on OK ‣ 4 ‣ 2. Then, click on Change ‣ CTEP (as Protocole ECR) ‣ OK. Click on **OK** thrice on the subsequent screens (_CTEP ticket ECR_ , _ECR ticket width_ , and _Character set_). Finally, press **Stop** three times; the terminal automatically restarts.

### Set the IP address¶

From your terminal, click on «.» ‣ 3 ‣ stop ‣ 3 ‣ 0 ‣ 9. Enter the technician password **«1235789»** and click on OK ‣ 4 ‣ 9. Then, click on Change ‣ TCP/IP (_TCP physical configuration_ screen) ‣ OK ‣ OK (_TCP Configuration client_ screen).

Finally, set up the hostname and port number.

#### Hostname¶

To set up the hostname, enter your IoT system’s IP address” sequence numbers and press **OK** at each «.» until you reach the colon symbol.

Then, press **OK** twice.

Example

Here’s an IP address sequence: `10.30.19.4:8069`.

On the _Hostname screen_ , type 10 ‣ OK ‣ 30 ‣ OK ‣ 19 ‣ OK ‣ 4 ‣ OK ‣ OK.

Suggerimento

Your IoT system’s IP address is available on the [IoT system’s card in the IoT app](../../../../general/iot/connect.html#iot-connect-iot-form).

#### Port number¶

On the _Port number_ screen, enter **9001** (or **9050** for Windows) and click on OK (_ECR protocol SSL no_) ‣ OK. Click on **Stop** three times; the terminal automatically restarts.

Avvertimento

For the [Windows virtual IoT](../../../../general/iot.html), the `9050` port must be added as a [Windows Firewall exception](../../../../general/iot/windows_iot.html#iot-windows-iot-firewall).

### Configure the payment method¶

Enable the payment terminal [in the application settings](../../configuration.html#configuration-settings) and [create the related payment method](../../payment_methods.html). Set the journal type as Bank and select Worldline in the Use a Payment Terminal field. Then, select your terminal device in the Payment Terminal Device field.

Once the payment method is created, you can select it in your POS settings. To do so, go to the [POS” settings](../../configuration.html#configuration-settings), click Edit, and add the payment method under the Payments section.

Suggerimento

  * Technician password: `1235789`

  * To reach Wordline’s technical assistance, call `02 727 61 11` and choose «merchant». Your call is automatically transferred to the desired service.

  * Configure the cashier terminal if you have both a customer and a cashier terminal.

  * To avoid blocking the terminal, check the initial configuration beforehand.

  * Set a fixed IP to your IoT Box’s router to prevent losing the connexion.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/payment_methods/terminals/worldline.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../reporting.html "Rendiconto") |
  * [precedente](viva_wallet.html "Viva Wallet") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Worldline


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
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order