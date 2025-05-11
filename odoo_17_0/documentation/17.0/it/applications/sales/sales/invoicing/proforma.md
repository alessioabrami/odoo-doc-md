# Fatture proforma — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](time_materials.html "Fatture basate su tempo e materiali") |
  * [precedente](down_payment.html "Acconti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture proforma



# Fatture proforma¶

Una _fattura proforma_ è una fattura abbreviata o stimata inviata in anticipo rispetto alla consegna della merce. Essa riporta il tipo e la quantità di merci, il loro valore e altre informazioni importanti, come il peso e le spese di trasporto.

Le fatture proforma sono comunemente utilizzate come fatture preliminari con un preventivo. Vengono utilizzate anche durante l’importazione per scopi doganali. Si differenziano da una normale fattura in quanto _non_ sono una richiesta di pagamento.

## Configurazione¶

Per utilizzare le fatture proforma, **bisogna** attivare la funzione _Fattura proforma_.

Per attivare la funzionalità, accedi al modulo Vendite ‣ Configurazione ‣ Impostazioni e nella sezione Preventivi e ordini, fai clic sulla casella accanto a Fattura proforma. In seguito, fai clic su Salva per salvare tutte le modifiche.

## Inviare una fattura proforma¶

Con la funzione Fattura proforma attivata, l’opzione di invio di una fattura proforma è ora disponibile su qualsiasi preventivo od ordine di vendita, tramite il pulsante Invia fattura proforma.

Nota

Le fatture proforma **non** possono essere inviate per un ordine di vendita o un preventivo se è già stata inviata una fattura di acconto o per un abbonamento ricorrente.

In entrambi i casi, il pulsante Invia fattura proforma **non** appare.

Tuttavia, le fatture proforma **possono** essere inviate per servizi, iscrizioni a eventi, corsi e/o nuovi abbonamenti. Le fatture proforma non sono limitate a beni fisici, consumabili o conservabili.

Quando fai clic sul pulsante Invia fattura proforma, appare una finestra pop-up dalla quale è possibile inviare un’e-mail.

Nella finestra a comparsa, il campo Destinatari viene popolato automaticamente con il cliente dell’ordine di vendita o del preventivo. Il campo Oggetto e il corpo dell’e-mail possono essere modificati, se necessario.

La fattura proforma viene aggiunta automaticamente come allegato all’e-mail.

Una volta pronti, fai clic su Invia e Odoo invierà immediatamente l’e-mail al cliente, con la fattura proforma allegata.

Suggerimento

Per avere un’anteprima dell’aspetto della fattura proforma, fai clic sul PDF in fondo alla finestra pop-up dell’e-mail _prima_ di fare clic su Invia. Una volta fatto clic, la fattura proforma viene scaricata immediatamente. Apri il PDF per visualizzare (e rivedere) la fattura proforma.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/invoicing/proforma.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](time_materials.html "Fatture basate su tempo e materiali") |
  * [precedente](down_payment.html "Acconti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture proforma


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