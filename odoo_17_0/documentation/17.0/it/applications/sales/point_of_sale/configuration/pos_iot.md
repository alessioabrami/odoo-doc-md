# IoT system connection — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epos_printers.html "ePOS printers") |
  * [precedente](../configuration.html "Configurazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * IoT system connection



# IoT system connection¶

To connect the POS with an [IoT system](../../../general/iot.html):

  1. Make sure both the Point of Sale and Internet of Things (IoT) apps are installed on your database.

  2. Set up the [Box IoT](../../../general/iot/iot_box.html) or [Windows virtual IoT](../../../general/iot/windows_iot.html).

  3. Connect the peripheral devices to the IoT system:

Dispositivo | Istruzioni  
---|---  
Stampante | Connect a supported receipt printer to a USB port or to the network, and power it on. Refer to [Orders printing](../restaurant/kitchen_printing.html).  
Registratore di cassa | Il registratore di cassa deve essere collegato alla stampante con un cavo RJ25.  
Lettore di codici a barre | The barcode scanner must end barcodes with an `ENTER` character (keycode 28) in order for the barcode scanner to be compatible. This is most likely the barcode scanner’s default configuration.  
Scala | Connect the scale and power it on. Refer to [Collegare una bilancia](../../../general/iot/devices/scale.html).  
Schermo cliente | Connect a screen to the IoT box to display the PoS order. Refer to [Collegare uno schermo](../../../general/iot/devices/screen.html).  
Terminale di pagamento | Il processo di connessione dipende dal terminale. Fai riferimento alla [documentazione relativa ai terminali di pagamento](../payment_methods.html).  
  4. [Connect the IoT system to your Odoo database](../../../general/iot/connect.html).

  5. [Access the POS settings](../configuration.html#configuration-settings) and select your POS, or click the vertical ellipsis button (⋮) on a POS card and click Edit. Scroll down to the Connected Devices section, enable IoT Box, then select the devices to be used for the POS. Click Save.




Suggerimento

Click IoT Devices to access the list of [Dispositivi](../../../general/iot/devices.html) for your POS and view their connection status. Click a card to access the device’s form.

Vedi anche

  * [List of supported hardware](https://www.odoo.com/page/point-of-sale-hardware).

  * [IoT documentation](../../../general/iot.html)




## Setup example¶

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/configuration/pos_iot.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epos_printers.html "ePOS printers") |
  * [precedente](../configuration.html "Configurazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * IoT system connection


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