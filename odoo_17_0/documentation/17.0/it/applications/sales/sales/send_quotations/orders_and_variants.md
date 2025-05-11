# Varianti prodotto su preventivi e ordini di vendita — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pdf_quote_builder.html "Creazione preventivi in PDF") |
  * [precedente](different_addresses.html "Consegne e fatture a indirizzi diversi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Varianti prodotto su preventivi e ordini di vendita



# Varianti prodotto su preventivi e ordini di vendita¶

Prima di spiegare come utilizzare le varianti prodotto su preventivi e ordini di vendita, ti consigliamo di scoprire cosa sono le about [Varianti prodotto](../products_prices/products/variants.html) in Odoo.

Una volta acquisite le nozioni di base sulle varianti prodotto, nella seguente sezione imparerai come aggiungere le varianti prodotto ai preventivi e agli ordini di vendita utilizzando il _configuratore prodotto_ o la _griglia di inserimento ordini_.

Nota

Nota che l’impostazione si chiama _Voce griglia per variante_ nella pagina delle impostazioni dell’applicazione _Vendite_ e _Voce griglia per ordine_ nei moduli prodotto. Pertanto, è bene tenerlo presente.

## Impostazioni¶

Quando si lavora con le varianti prodotto, Odoo utilizza il configuratore prodotto per impostazione predefinita. Per aggiungere l’opzione di inserimento di una griglia con voci di varianti, la funzione deve essere abilitata nell’applicazione _Vendite_ di Odoo. L’opzione di inserimento della griglia delle varianti fornisce una finestra a comparsa sul preventivo/ordine di vendita per semplificare il processo di selezione delle varianti stesse.

Per attivare questa impostazione, accedi al modulo Vendite ‣ Configurazione ‣ Impostazioni e scorri fino alla sezione Catalogo prodotti. In seguito, seleziona la casella accanto all’opzione Voce griglia per variante e fai clic su Salva.

Nota

Per poter utilizzare le varianti di prodotto su preventivi e ordini di vendita, deve essere attivata anche la funzione Varianti.

## Configurazione prodotto¶

Una volta attivata l’impostazione Voce griglia per variante, entrambe le opzioni (_Configurazione prodotto_ e _Voce griglia per ordine_) diventano disponibili in ogni modulo prodotto.

Per configurare un modulo prodotto da usare con il configuratore prodotto o con la voce griglia per ordine, apri l’app Vendite ‣ Prodotti ‣ Prodotti per visualizzare tutti i prodotti nel database.

In seguito, seleziona il prodotto che vuoi configurare o fai clic su Nuovo, per creare un nuovo prodotto da zero. Una volta nel modulo del prodotto, fai clic sulla scheda Attributi e varianti, dove si possono visualizzare, modificare e aggiungere le varianti del prodotto.

In fondo alla scheda Attributi e varianti, c’è una sezione Selezione variante vendite con due opzioni: Configuratore prodotto e Voce griglia per ordine.

Nota

Nota che queste opzioni appaiono **solo** se al record sono stati aggiunti almeno due valori di un attributo.

Queste opzioni determinano il metodo da utilizzare per aggiungere varianti di prodotto ai preventivi o agli ordini di vendita.

Il Configuratore prodotto fornisce una finestra pop-up che mostra in modo ordinato tutte le varianti di prodotto disponibili per quel particolare prodotto quando viene aggiunto a un preventivo. Tuttavia, è possibile selezionare/aggiungere solo una variante alla volta.

L’opzione Voce griglia per ordine fornisce le stesse informazioni dell’opzione Configuratore prodotto in un layout a tabella, consentendo all’utente di selezionare un numero maggiore di varianti di prodotto uniche e di aggiungerle a un preventivo/ordine di vendita in un’unica vista.

## Configuratore prodotto¶

Il configuratore prodotto appare come finestra pop-up Configura, non appena un prodotto con (almeno due) varianti viene aggiunto a un preventivo o a un ordine di vendita, ma **solo** se l’opzione Configuratore prodotto è selezionata nella sua scheda prodotto.

Nota

La finestra pop-up Configura appare anche se l’impostazione Voce griglia per ordine **non** è attivata, in quanto è l’opzione predefinita che Odoo utilizza quando tratta le varianti di prodotto sui preventivi e/o sugli ordini di vendita.

L’opzione Configuratore prodotto consente agli addetti vendite di scegliere esattamente la variante di prodotto da aggiungere al preventivo o all’ordine di vendita, utilizzando un formato simile a quello degli acquisti online.

## Voce griglia ordine¶

La funzione voce griglia ordine appare come finestra pop-up Scegli le varianti del prodotto, non appena un prodotto con (almeno due) varianti viene aggiunto a un preventivo o a un ordine di vendita, ma **solo** se l’opzione Voce griglia ordine è selezionata nella rispettiva scheda prodotto.

La finestra pop-up Scelta varianti prodotto presenta tutte le opzioni di variante per quel particolare prodotto. Da questa finestra pop-up, l’addetto alle vendite può indicare quante varianti desidera aggiungere al preventivo/ordine di vendita in una sola volta.

Una volta selezionate tutte le quantità e le varianti desiderate, l’addetto alle vendite deve semplicemente fare clic su Conferma e gli ordini vengono immediatamente aggiunti al preventivo/ordine di vendita nella scheda Righe ordine.

Vedi anche

[Varianti prodotto](../products_prices/products/variants.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/orders_and_variants.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pdf_quote_builder.html "Creazione preventivi in PDF") |
  * [precedente](different_addresses.html "Consegne e fatture a indirizzi diversi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Varianti prodotto su preventivi e ordini di vendita


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