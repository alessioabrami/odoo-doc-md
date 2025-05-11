# Flexible taxes (fiscal positions) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](pricelists.html "Listini prezzi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Flexible taxes (fiscal positions)



# Flexible taxes (fiscal positions)¶

When running a business, you may need to apply different taxes and record transactions on various accounts based on the location and type of business of your customers and providers.

The **fiscal positions** feature enables you to establish rules that automatically select the right taxes and accounts used for each transaction.

Vedi anche

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../../../finance/accounting/taxes/fiscal_positions.html)

  * [Imposte](../../../finance/accounting/taxes.html)




## Configurazione¶

To enable the feature, go to Point of Sale ‣ Configuration ‣ Settings, scroll down to the Accounting section, and enable Flexible Taxes.

Then, set a default fiscal position that should be applied to all sales in the selected POS in the Default field. You can also add more fiscal positions to choose from in the Allowed field.

According to the [fiscal localization package](../../../finance/fiscal_localizations.html) activated, several fiscal positions are preconfigured and can be set and used in POS. However, you can also [create new fiscal positions](../../../finance/accounting/taxes/fiscal_positions.html#fiscal-positions-mapping).

Nota

If you do not set a fiscal position, the tax remains as defined in the **customer taxes** field on the product form.

## Use fiscal positions¶

Open a [POS session](../../point_of_sale.html#pos-session-start) to use one of the allowed fiscal positions. Then, click the Tax button next to the **book-shaped** icon and select a fiscal position from the list. Doing so applies the defined rules automatically to all the products subject to the chosen fiscal position’s regulations.

Nota

If a default fiscal position is set, the tax button displays the name of the fiscal position.

Vedi anche

[Posizioni di bilancio (mappatura fiscale e contabile)](../../../finance/accounting/taxes/fiscal_positions.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/point_of_sale/pricing/fiscal_position.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](pricelists.html "Listini prezzi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Flexible taxes (fiscal positions)


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