# Fatture basate su quantità ordinate o consegnate — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](down_payment.html "Acconti") |
  * [precedente](../invoicing.html "Invoicing Method") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su quantità ordinate o consegnate



# Fatture basate su quantità ordinate o consegnate¶

Politiche aziendali diverse potrebbero richiedere opzioni di fatturazione differenti:

  * La regola _Fatturare ciò che viene ordinato_ viene usata come modalità predefinita in Odoo _Vendite_ , il che significa che i clienti vengono fatturati una volta confermato l’ordine di vendita.

  * Con la regola _Fatturare ciò che viene consegnato_ le fatture vengono emesse una volta effettuata la consegna. Questa regola viene spesso usata per aziende che vendono materiali, liquidi o cibo in grandi quantità. In questi casi, La quantità ordinata potrebbe differire leggermente dalla quantità consegnata così da preferire la fatturazione della quantità effettivamente consegnata.




Avere più opzioni di fatturazione permette di avere maggiore flessibilità.

## Funzionalità politica di fatturazione¶

Per attivare le funzionalità di cui hai bisogno, accedi al modulo Vendite ‣ Configurazione ‣ Impostazioni e sotto la sezione Fatturazione, selezione una regola per la politica di fatturazione: Fatturare ciò che viene ordinato oppure Fatturare ciò che viene consegnato.

Importante

Se scegli la regola Fatturare ciò che viene consegnato, **non** è possibile attivare la funzionalità Fattura automatica che genera fatture automaticamente al momento della conferma di un pagamento online.

## Politica di fatturazione su modulo prodotto¶

Su qualsiasi pagina prodotto, attraverso l’app Vendite ‣ Prodotti ‣ Dashboard prodotti, trova l’opzione Politica di fatturazione nella scheda Informazioni generali. È possibile modificarla manualmente usando il menu a discesa.

## Impatto sui flussi di vendita¶

Nel modulo Odoo _Vendite_ , un flusso di vendita di base inizia dalla creazione di un preventivo. In seguito, il preventivo viene inviato al cliente. Successivamente, deve essere confermato e il preventivo diventa un ordine di vendita. Infine, verrà creata una fattura.

Le regole per la politica di fatturazione impattano il flusso di vendita in due modi distinti:

  * Fatturare ciò che viene ordinato: nessun impatto sul flusso di vendita di base. Una fattura viene creata non appena viene confermata la vendita.

  * Fatturare ciò che viene consegnato: impatto minore sul flusso di vendita perché la quantità consegnata deve essere aggiunta manualmente all’ordine di vendita. In alternativa, è possibile installare l’app _Magazzino_ e utilizzarla per confermare la quantità consegnata prima di creare una fattura con l’app _Vendite_.




Avvertimento

Se un utente prova a creare una fattura senza convalidare la quantità consegnata, apparirà il seguente messaggio di errore: Nessuna riga fatturabile. Se un prodotto ha una politica di fatturazione basata sulla quantità consegnata, controllare che la quantità stessa sia stata consegnata.

Nota

Una volta confermato un preventivo e lo stato passa da Preventivo inviato a Ordine di vendita, le quantità consegnate e fatturate sono disponibili per la visualizzazione direttamente dall’ordine di vendita, indipendentemente dalla regola di fatturazione applicata.

Odoo aggiunge automaticamente le quantità alla fattura, sia quelle Consegnate che Fatturate, anche se si tratta di una consegna parziale, una volta confermato il preventivo.

Infine, esistono alcune opzioni per creare una fattura: Fattura regolare, Acconto (percentuale) o Acconto (importo fisso).

Vedi anche

Assicurati di consultare la documentazione che spiega come funzionano gli acconti per scoprire di più: [Acconti](down_payment.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/invoicing/invoicing_policy.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](down_payment.html "Acconti") |
  * [precedente](../invoicing.html "Invoicing Method") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su quantità ordinate o consegnate


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