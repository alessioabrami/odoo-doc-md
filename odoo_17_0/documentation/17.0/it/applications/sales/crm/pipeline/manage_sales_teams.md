# Gestire i team vendite — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../acquire_leads.html "Acquisire nuovi contatti") |
  * [precedente](merge_similar.html "Unire lead e opportunità simili") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Gestire i team vendite



# Gestire i team vendite¶

La funzione _Team vendite_ all’interno dell’applicazione _CRM_ di Odoo consente la creazione e la gestione di più team di vendita, ciascuno con le proprie regole di assegnazione, i propri obiettivi di fatturazione e la propria rosa di addetti alle vendite.

## Creare un team di vendita¶

Per creare un nuovo team di vendita apri l’app CRM ‣ Configurazione ‣ Team vendite e poi fai clic su Nuovo.

Sul modulo vuoto del team di vendita, inserisci un nome nel campo Team di vendita.

In seguito, seleziona un Team leader dal menu a discesa.

Configura un Alias e-mail per generare automaticamente lead/opportunità per questo team di vendita quando un messaggio viene inviato all’indirizzo e-mail unico. Scegli se accettare e-mail da Chiunque, Partner autenticati, Solo follower oppure Dipendenti autenticati.

Scegli una Azienda dal menu a discesa per assegnarla a questo team.

Nota

Il campo Azienda, è visibile solo in database con più aziende e non è richiesto.

Nota

Se l’applicazione _Vendite_ è installata nel database, nel modulo del team vendite appare il campo Obiettivo di fatturazione. Si tratta dell’obiettivo di fatturato per il mese corrente. L’importo inserito in questo campo viene utilizzato per popolare la barra di avanzamento della fatturazione nella dashboard del team vendite.

### Aggiungere membri al team di vendita¶

Per aggiungere membri al team, fai clic su Aggiungi sotto la scheda Membri quando si modifica la pagina di configurazione del team di vendita. In seguito, si aprirà la finestra pop-up Crea membri del team di vendita.

Nota

Se la funzione Assegnazione basata su regole _non_ è stata abilitata nella pagina _Impostazioni_ dell’applicazione _CRM_ , facendo clic su Aggiungi sotto la scheda Membri si apre la finestra pop-up Aggiungi: venditori. Spunta la casella di controllo all’estrema sinistra dell’addetto vendite da aggiungere al team e poi fai clic su Seleziona.

Seleziona un utente dall’elenco a discesa Addetti vendite per aggiungerlo al team. Per evitare che a questo venditore vengano assegnati automaticamente dei lead, seleziona la casella di controllo Salta assegnazione automatica. Se questa funzione è attivata, il venditore può comunque essere assegnato manualmente.

Il campo Lead (30 giorni) tiene traccia di quanti lead sono stati assegnati all’addetto vendite negli ultimi trenta giorni per questo team e del numero massimo di lead che gli possono essere assegnati. Per modificare il numero massimo di lead che possono essere assegnati a questo venditore, inserisci l’importo nel campo Lead (30 giorni).

Suggerimento

Le [regole di assegnazione](../track_leads/lead_scoring.html) possono essere configurate utilizzando la sezione Dominio.

Fai clic su Salva e chiudi una volta finito, oppure Salva e nuovo per aggiungere altri membri.

## Attivare più team¶

Per consentire agli addetti vendite di essere assegnati a più di un team di vendita, è necessario attivare l’impostazione _Team multipli_. Per prima cosa, accedi al modulo CRM ‣ Configurazione ‣ Impostazioni. Nella sezione CRM, seleziona la casella di controllo Team multipli. In seguito, fai clic su Salva in alto a sinistra della pagina.

## Dashboard team vendite¶

Per visualizzare la dashboard del team di vendita, apri l’app CRM ‣ Vendite ‣ Team. Nella dashboard, appare qualsiasi team di cui l’utente è membro.

Ogni scheda kanban fornisce una panoramica delle opportunità, dei preventivi, degli ordini di vendita e dei ricavi previsti del team di vendita così come un grafico a barre delle nuove opportunità per settimana e una barra di avanzamento per la fatturazione.

Fai clic sul pulsante Pipeline per accedere direttamente alla pipeline del _CRM_ di un team specifico.

Fai clic sull’icona __(ellissi verticale) nell’angolo superiore destro della scheda Kanban per aprire un menu a tendina. Successivamente, per visualizzare o modificare le impostazioni del team, fai clic su Configurazione.

Vedi anche

  * [Utilizzare attività per i team di vendita](../optimize/utilize_activities.html)

  * [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/pipeline/manage_sales_teams.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../acquire_leads.html "Acquisire nuovi contatti") |
  * [precedente](merge_similar.html "Unire lead e opportunità simili") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Gestire i team vendite


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