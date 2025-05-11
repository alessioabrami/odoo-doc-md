# Secure connection (HTTPS) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epos_ssc.html "Self-signed certificate for ePOS printers") |
  * [precedente](epos_printers.html "ePOS printers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * Secure connection (HTTPS)



# Secure connection (HTTPS)¶

If **Direct Devices** is enabled in a Point of Sale settings (for example, if you use an [ePos printer](epos_printers.html)), HTTP becomes the default protocol.

## Force your Point of Sale to use a secure connection (HTTPS)¶

Add a new **key** in the **System Parameters** to force your Point of Sale to use a secure connection with the HTTPS protocol.

To do so, activate the [developer mode](../../../general/developer_mode.html#developer-mode), go to Settings ‣ Technical ‣ Parameters ‣ System Parameters, then create a new parameter, add the following values and click on _Save_.

  * **Key** : `point_of_sale.enforce_https`

  * **Value** : `True`




Vedi anche

  * [Self-signed certificate for ePOS printers](epos_ssc.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/configuration/https.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epos_ssc.html "Self-signed certificate for ePOS printers") |
  * [precedente](epos_printers.html "ePOS printers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * Secure connection (HTTPS)


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