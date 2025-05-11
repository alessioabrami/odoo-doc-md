# ePOS printers — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](https.html "Secure connection \(HTTPS\)") |
  * [precedente](pos_iot.html "IoT system connection") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * ePOS printers



# ePOS printers¶

ePOS printers are designed to work seamlessly with Point of Sale systems. Once connected, these devices automatically share information, allowing for direct printing of tickets from the POS system to the ePOS printer.

## Configurazione¶

To use an ePos printer in Point of Sale:

  1. [Access the POS settings](../configuration.html#configuration-settings).

  2. Activate the ePos Printer feature.

  3. Fill in the field with your ePos IP address.




Nota

When the printer connects to a network, it automatically prints a ticket with its IP address.

## Directly supported ePOS printers¶

The following ePOS printers are directly compatible with Odoo without needing an [IoT system](../../../general/iot/devices/printer.html).

  * Epson TM-m30 i/ii/iii (Wi-Fi/Ethernet models only; Recommended)

  * Epson TM-H6000IV-DT (Receipt printer only)

  * Epson TM-T70II-DT

  * Epson TM-T88V-DT

  * Epson TM-L90-i

  * Epson TM-T70-i

  * Epson TM-T82II-i

  * Epson TM-T83II-i

  * Epson TM-U220-i

  * Epson TM-m10

  * Epson TM-P20 (Wi-Fi® model)

  * Epson TM-P60II (Receipt: Wi-Fi® model)

  * Epson TM-P60II (Peeler: Wi-Fi® model)

  * Epson TM-P80 (Wi-Fi® model)




## ePOS printers with IoT system integration¶

The following printers require an [IoT system](../../../general/iot/devices/printer.html) to be compatible with Odoo:

  * Epson TM-T20 family (incompatible ePOS software)

  * Epson TM-T88 family (incompatible ePOS software)

  * Epson TM-U220 family (incompatible ePOS software)




Importante

  * Epson printers using Wi-Fi/Ethernet connections and following the [EPOS SDK Javascript protocol](https://download4.epson.biz/sec_pubs/pos/reference_en/technology/epson_epos_sdk.html) are compatible with Odoo **without** needing an [IoT system](../../../general/iot/devices/printer.html).

  * Thermal printers using ESC/POS are compatible **with** an [IoT system](../../../general/iot/devices/printer.html).

  * Epson printers using only USB connections are compatible **with** an [IoT system](../../../general/iot/devices/printer.html).

  * Epson printers that connect via Bluetooth are **not compatible**.




Vedi anche

  * [Secure connection (HTTPS)](https.html)

  * [Self-signed certificate for ePOS printers](epos_ssc.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/configuration/epos_printers.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](https.html "Secure connection \(HTTPS\)") |
  * [precedente](pos_iot.html "IoT system connection") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * ePOS printers


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