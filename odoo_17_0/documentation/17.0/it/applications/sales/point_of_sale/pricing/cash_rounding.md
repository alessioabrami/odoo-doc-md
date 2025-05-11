# Arrotondamento di cassa — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](electronic_labels.html "Electronic shelf labels") |
  * [precedente](fiscal_position.html "Flexible taxes \(fiscal positions\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Arrotondamento di cassa



# Arrotondamento di cassa¶

**L’arrotondamento di cassa** è necessario quando il taglio fisico più basso della valuta, o la moneta più piccola, è superiore all’unità minima di conto.

Ad esempio, alcuni Paesi richiedono alle aziende di arrotondare l’importo totale di una fattura ai cinque centesimi più vicini, quando il pagamento viene effettuato in contanti.

Each point of sale in Odoo can be configured to apply cash rounding to the totals of its bills or receipts.

## Configurazione¶

Go to Point of Sale ‣ Configuration ‣ Settings and enable _Cash Rounding_ , then click on _Save_.

Go to Point of Sale ‣ Configuration ‣ Point of Sale, open the point of sale you want to configure, and enable the _Cash Rounding_ option.

To define the **Rounding Method** , open the drop-down list and click on _Create and Edit…_.

Define here your _Rounding Precision_ , _Profit Account_ , and _Loss Account_ , then save both the Rounding Method and your Point of Sale settings.

All total amounts of this point of sale now add a line to apply the rounding according to your settings.

Nota

Odoo Point of Sale only supports the Add a rounding line rounding strategy.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/pricing/cash_rounding.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](electronic_labels.html "Electronic shelf labels") |
  * [precedente](fiscal_position.html "Flexible taxes \(fiscal positions\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Arrotondamento di cassa


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