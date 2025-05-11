# Firme online per confermare gli ordini — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_paid_to_validate.html "Conferma ordine tramite pagamento online") |
  * [precedente](optional_products.html "Prodotti opzionali") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Firme online per confermare gli ordini



# Firme online per confermare gli ordini¶

L’applicazione Odoo _Vendite_ offre ai clienti la possibilità di confermare gli ordini, tramite una firma online, direttamente su un ordine di vendita. Una volta che l’ordine di vendita è stato firmato digitalmente dal cliente, il venditore collegato all’ordine di vendita riceve immediatamente una notifica di conferma dell’ordine.

## Attivare firme online¶

Per far sì che i clienti confermino gli ordini con una firma online, **bisogna** attivare la funzione _Firma online_.

Per attivare la funzionalità _Firma online_ , apri l’app Vendite ‣ Configurazione ‣ Impostazioni, scorri fino alla sezione Preventivi e ordini e attiva la funzionalità Firma online selezionando la casella corrispondente.

In seguito, fai clic sul pulsante Salva nell’angolo in alto a destra.

Nota

Quando si crea un modello di preventivo, la funzione di firma online è l’opzione Firma, situata nel campo Conferma online del modulo del modello di preventivo.

Nei preventivi standard, la funzione di firma online è l’opzione Firma, situata nella scheda Altre informazioni del modulo di preventivo.

## Conferme ordini con firme online¶

Quando i clienti accedono ai preventivi online attraverso il loro portale clienti, sul preventivo ci sarà il pulsante Firma e paga.

Quando fai clic, viene visualizzata la finestra pop-up Convalida ordine. In questa finestra a comparsa, il campo Nome completo viene popolato automaticamente, in base alle informazioni di contatto presenti nel database.

I clienti possono quindi inserire una firma online con una delle seguenti opzioni: Automatica, Disegna o Carica.

L’opzione Automatica consente a Odoo di generare automaticamente una firma online in base alle informazioni contenute nel campo Nome completo. Disegna consente al cliente di utilizzare il cursore per creare una firma personalizzata direttamente nella finestra pop-up. Infine, Carica consente al cliente di caricare dal proprio computer un file di firma precedentemente creato.

Dopo aver scelto una delle tre opzioni di firma precedentemente menzionate (Automatica, Disegna o Carica), il cliente farà clic sul pulsante Accetta e firma.

Quando fai clic su Accetta e firma, vengono rese disponibili le varie opzioni di pagamento tra cui scegliere (se l’opzione _pagamento online_ è applicabile al preventivo).

Successivamente, quando il preventivo viene pagato e confermato, viene creato automaticamente un ordine di consegna (se è installata l’applicazione Odoo _Magazzino_).

Vedi anche

  * [Modelli preventivo](quote_template.html)

  * [Conferma ordine tramite pagamento online](get_paid_to_validate.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/get_signature_to_validate.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_paid_to_validate.html "Conferma ordine tramite pagamento online") |
  * [precedente](optional_products.html "Prodotti opzionali") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Firme online per confermare gli ordini


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