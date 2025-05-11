# Conferma ordine tramite pagamento online — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deadline.html "Date di scadenza per i preventivi") |
  * [precedente](get_signature_to_validate.html "Firme online per confermare gli ordini") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Conferma ordine tramite pagamento online



# Conferma ordine tramite pagamento online¶

L’applicazione Odoo _Vendite_ offre ai clienti la possibilità di confermare gli ordini, tramite un pagamento online, direttamente su un ordine di vendita. Una volta che l’ordine di vendita è stato pagato elettronicamente dal cliente, il venditore collegato all’ordine di vendita riceve immediatamente una notifica di conferma dell’ordine.

## Attivare i pagamenti online¶

Per far sì che i clienti confermino gli ordini con un pagamento online, è **necessario** attivare l’impostazione _Pagamento online_.

Per attivare la funzione _Pagamento online_ , accedi al modulo Vendite ‣ Configurazione ‣ Impostazioni, scorri verso la sezione Preventivi e ordini, seleziona la casella accanto alla funzione Pagamento online e fai clic su Salva.

Sotto l’opzione Pagamento online nella pagina Impostazioni del modulo _Vendite_ c’è il campo Validità predefinita preventivo. In questo campo è possibile aggiungere un numero specifico di giorni per la validità predefinita dei preventivi.

Per attivare questa funzione su un preventivo standard, fai clic sulla casella di controllo dell’opzione Pagamento, situata nel campo Conferma online, nella scheda Altre informazioni.

Per attivare questa funzione su un modello di preventivo, fai clic sulla casella di controllo dell’opzione Pagamento, situata nel campo Conferma online del modulo del modello di preventivo.

## Fornitori di pagamento¶

Dopo aver attivato la funzione Pagamento online, appare un link per configurare i Fornitori di pagamento.

Facendo clic su questo link si apre una pagina separata dal titolo Fornitori di pagamento, in cui è possibile abilitare, personalizzare e pubblicare un’ampia gamma di fornitori di pagamento.

Vedi anche

[Online payments](../../../finance/payment_providers.html)

## Registra un pagamento¶

Dopo aver aperto i preventivi nel portale clienti, i clienti possono cliccare su Accetta e paga per confermare l’ordine con un pagamento online.

Dopo aver fatto clic su Accetta e paga, ai clienti viene presentata la finestra pop-up Convalida ordine contenente diverse opzioni per effettuare il pagamento online, nella sezione Paga con.

Nota

Odoo offrirà **solo** opzioni di pagamento nella finestra pop-up Convalida ordine pubblicate e configurate nella pagina Fornitori di pagamento.

Una volta selezionato il metodo di pagamento desiderato, il cliente farà clic sul pulsante Paga nella finestra pop-up per confermare l’ordine. Odoo notifica immediatamente all’addetto vendite assegnato la conferma dell’ordine con un pagamento online.

Vedi anche

  * [Modelli preventivo](quote_template.html)

  * [Firme online per confermare gli ordini](get_signature_to_validate.html)

  * [Online payments](../../../finance/payment_providers.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/get_paid_to_validate.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](deadline.html "Date di scadenza per i preventivi") |
  * [precedente](get_signature_to_validate.html "Firme online per confermare gli ordini") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Conferma ordine tramite pagamento online


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