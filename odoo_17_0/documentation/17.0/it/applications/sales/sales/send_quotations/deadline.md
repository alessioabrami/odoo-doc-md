# Date di scadenza per i preventivi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](different_addresses.html "Consegne e fatture a indirizzi diversi") |
  * [precedente](get_paid_to_validate.html "Conferma ordine tramite pagamento online") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Date di scadenza per i preventivi



# Date di scadenza per i preventivi¶

Nell’applicazione Odoo _Vendite_ è possibile impostare delle scadenze per i preventivi di vendita. In questo modo, si incoraggiano i clienti ad agire rapidamente durante le trattative, perché potrebbero temere di perdere un buon affare. Inoltre, le scadenze possono anche fungere da protezione per un’azienda nel caso in cui un ordine debba essere evaso a un prezzo che non è più redditizio per l’azienda.

## Scadenza del preventivo¶

In Odoo _Vendite_ è presente un’opzione per aggiungere una data di scadenza a un preventivo.

Per aggiungere una data di scadenza al preventivo, apri l’app Vendite e seleziona il preventivo desiderato oppure creane uno nuovo facendo clic su Nuovo.

Nel modulo di preventivo, fai clic sul campo Scadenza per visualizzare un calendario a comparsa. Da questo calendario, seleziona il mese e la data desiderati come data di scadenza del preventivo.

Suggerimento

Facendo clic sul pulsante Anteprima di un preventivo, Odoo mostra chiaramente la data di scadenza dell’offerta.

## Scadenza modello di preventivo¶

L’applicazione Odoo _Vendite_ consente anche di aggiungere una data di scadenza ai modelli di preventivo.

Per aggiungere una data di scadenza a un modello di preventivo, accedi all’app Vendite ‣ Configurazione ‣ Modelli di preventivo e seleziona il modello al quale aggiungere una data di scadenza oppure fai clic su Nuovo per creare un nuovo modello da capo.

Nel modulo del modello di preventivo, aggiungi un numero specifico di giorni al campo Preventivo scade dopo, situato sotto il nome del modello di preventivo. Il numero di giorni rappresenta il periodo di validità dell’offerta prima della sua scadenza.

In seguito, ogni volta che il modello di preventivo specifico viene utilizzato in un preventivo, viene calcolata automaticamente una data di scadenza, basata sul numero di giorni indicato sopra. Tuttavia, questa data può essere sostituita prima di inviare il preventivo al cliente.

Vedi anche

[Modelli preventivo](quote_template.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/deadline.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](different_addresses.html "Consegne e fatture a indirizzi diversi") |
  * [precedente](get_paid_to_validate.html "Conferma ordine tramite pagamento online") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Date di scadenza per i preventivi


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