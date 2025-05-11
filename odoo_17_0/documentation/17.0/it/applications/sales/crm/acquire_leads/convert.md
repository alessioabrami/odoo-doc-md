# Convertire i Lead in opportunità — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [precedente](../acquire_leads.html "Acquisire nuovi contatti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Convertire i Lead in opportunità



# Convertire i Lead in opportunità¶

I _lead_ rappresentano la fase di qualifica che precede la creazione di un’opportunità. Questo permette di avere più tempo per scoprirne il potenziale e valutarne la fattibilità prima che l’opportunità venga assegnata a un addetto alle vendite.

## Configurazione¶

Per attivare le impostazioni relative ai _lead_ , accedi all’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. Infine, fai clic su Salva.

L’attivazione di questa funzionalità comporta l’aggiuna della nuova opzione Lead nella barra d’intestazione situata nella parte alta dello schermo.

Una volta attivata, la funzione _Lead_ si applica a tutti i team di vendita. Per disattivarla per un team specifico, accedi all’app CRM ‣ Configurazione ‣ Team vendite. Successivamente, seleziona un team dall’elenco per aprire la pagina di configurazione del team stesso. Deseleziona la casella Lead, situata sotto al campo Team vendite e poi fai clic su Salva.

## Convertire un Contatto in Opportunità¶

Per convertire un lead in _opportunità_ , accedi all’app CRM ‣ Lead e fai clic sul lead dall’elenco che si apre.

Avvertimento

Se appare i lpulsante Lead simile nella parte alta della pagina del lead, significa che esiste già un lead/opportunità simile nel database. Prima di convertire questo lead, fai clic sul pulsante per confermare o meno l’unione.

Fai clic sul pulsante Converti opportunità, nella parte in alto a sinistra della pagina.

Si aprirà la finestra pop-up dal nome Converti in opportunità. Qui, nel campo Azione conversione, seleziona l’opzione Converti in opportunità.

Nota

Per unire questo lead a un lead simile esistente o a un’opportunità, seleziona Unisci a opportunità esistente nel campo Azione conversione. Verrà generato un elenco di lead/opportunità simili da unire.

Durante l’unione, Odoo dà la priorità al lead/opportunità che è stato creato per primo nel sistema, unendo le informazioni nel primo lead/opportunità creato. Tuttavia, se vengono uniti un lead e un’opportunità, il record risultante viene definito opportunità, indipendentemente dal record creato per primo.

In seguito, seleziona un Addetto vendite e un Team vendite a cui assegnare l’opportunità. Nessuno dei due campi è obbligatorio ma se viene completato il campo Addetto vendite, il campo Team vendite viene popolato automaticamente in base alle assegnazioni del team dell’addetto vendite.

Se il lead è già stato assegnato a un addetto vendite o a un team, vengono popolati automaticamente con le informazioni.

Nella sezione Cliente, scegli una delle seguenti opzioni:

  * Crea un nuovo cliente: scegli quest’opzione per utilizzare le informazioni contenute nel lead per creare un nuovo record cliente

  * Collega a un cliente esistente: scegli quest’opzione e poi seleziona un cliente dal menu a discesa risultante, per collegare l’opportunità a un record cliente esistente

  * Non collegare a un cliente: scegli l’opzione per convertire il lead, ma non collegarlo a un cliente nuovo o esistente.




Infine, quando tutte le impostazioni sono state configurate, fai clic su Crea opportunità.

Per visualizzare l’opportunità appena creata, apri l’app CRM ‣ La mia pipeline.

Nota

Potrebbe essere necessario rimuovere alcuni filtri dalla barra Cerca… nella parte alta della pagina della Pipeline per visualizzare tutte le opportunità-

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/acquire_leads/convert.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](opportunities_form.html "Creare opportunità dai moduli di contatto online") |
  * [precedente](../acquire_leads.html "Acquisire nuovi contatti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Convertire i Lead in opportunità


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