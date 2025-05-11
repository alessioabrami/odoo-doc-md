# Partner — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_attribution.html "Resoconti attribuzione attività marketing") |
  * [precedente](quality_leads_report.html "Resoconto lead di qualità") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Partner



# Partner¶

All’interno dell’applicazione _CRM_ di Odoo, i lead possono essere inoltrati ai rivenditori (o partner). I lead possono essere assegnati manualmente o automaticamente, in base al _livello_ e alla posizione del rivenditore.

## Configurazione¶

Per utilizzare le funzioni di rivenditore, è necessario installare il modulo _Rivenditori_. Accedi al modulo Applicazioni e rimuovi il filtro App dalla barra Cerca…. In seguito, cerca `Rivenditori`.

Fai clic su Attiva nella scheda del modulo Rivenditori che appare. In questo modo installerai il modulo per poi tornare alla dashboard principale di Odoo.

Dopo aver installato il modulo, accedi all’app CRM. Sotto il menu Configurazione appare una nuova sezione chiamata Rivenditori, con tre opzioni disponibili: Livelli partner, Attivazioni partner e Piani di provvigione.

## Livelli partner¶

I livelli di partner sono utilizzati per differenziare i vari rivenditori. Per visualizzare i livelli dei partner, apri l’applicazione CRM ‣ Configurazione ‣ Rivenditori: livelli partner.

Nella pagina Livelli partner, troverai tre livelli predefiniti:

  * Gold

  * Silver

  * Bronze




È possibile aggiungere nuovi livelli, se necessario, facendo clic su Nuovo e compilando il modulo del livello risultante.

Inoltre, è possibile modificare e rinominare anche i livelli esistenti. Per modificare un livello, selezionalo dall’elenco e procedi alle modifiche desideri applicare dalla pagina modulo del livello che appare.

Il peso del livello viene utilizzato per decidere la probabilità che a un partner venga assegnato un lead o un’opportunità. Nel modulo del livello, assegna un valore numerico (maggiore di zero) al campo Peso del livello. Se il peso è zero, non vengono assegnati lead.

Suggerimento

 _Il peso del livello_ può essere assegnato a un singolo record di contatto. Il peso assegnato al singolo record sovrascrive il peso predefinito assegnato nel modulo di configurazione del livello.

## Attivazioni partner¶

Le _attivazioni_ dei partner sono utilizzate per identificare lo stato di un partner. Le attivazioni sono assegnate a un singolo record di contatto e possono essere utilizzate per raggruppare o filtrare il resoconto _Analisi collaborazioni_ (Applicazione CRM ‣ Rendicontazione ‣ Collaborazioni).

Per visualizzare i livelli di partner, accedi al modulo CRM ‣ Configurazione ‣ Attivazioni partner.

Nell’app _CRM_ vengono creati tre tipi di attivazione per impostazione predefinita:

  * Completamente operativo

  * Incremento

  * Primo contatto




È possibile aggiungere nuovi tipi di attivazione di partner, se necessario, facendo clic su Nuovo e inserendo un Nome nella nuova riga visualizzata. Successivamente, seleziona lo stato desiderato nella colonna Attivo.

Anche le attivazioni dei partner esistenti possono essere modificate e rinominate. Per rinominare uno stato, fai clic sul campo Nome del livello desiderato e inseriscine uno nuovo.

Per cambiare lo stato attivo di un’attivazione, fai scorrere il pulsante toggle nella colonna Attivo dell’attivazione desiderata alla posizione _non attivo_.

L’elenco di Attivazioni partner predefinite nell’app CRM. Il pulsante toggle relativo a Primo contatto è in posizione non attivo mentre il resto è attivo.¶

## Assegnazioni partner¶

I livelli partner e le attivazioni partner ora sono configurati.

Per aggiornare il record di un singolo partner, accedi al modulo CRM ‣ Vendite ‣ Clienti e fai clic sulla scheda Kanban del partner desiderato per aprire il record del cliente.

Sul record del cliente, fai clic sulla scheda Assegnazione partner.

Fai clic sul campo Livello partner e seleziona un’opzione dal menu a discesa per assegnare un livello. Fai clic sul campo Attivazione e seleziona un tipo di attivazione del partner dall’elenco a tendina, se lo desideri. Successivamente, fai clic sul campo Peso livello per assegnare un peso diverso al livello, se necessario.

## Pubblicare i partner¶

Con le applicazioni Odoo _Sito web_ e _Rivenditori_ installate, viene creata una nuova pagina web (`/partners`) per visualizzare un elenco di tutti i partner attivi dall’applicazione _CRM_.

Successivamente, torna all’applicazione CRM ‣ Vendite ‣ Clienti e fai clic sulla scheda Kanban di un partner. Dal modulo di contatto del partner, fai clic sul pulsante Vai al sito web nella parte superiore della pagina per aprire la pagina web del partner.

In seguito, fai clic su Modifica nella parte in alto a destra della pagina web e usa i [blocchi di costruzione](../../../websites/website/web_design/building_blocks.html) per aggiungere qualsiasi elemento di design aggiuntivo o informazione sul partner.

Suggerimento

Una sintesi dell’azienda è un’utile aggiunta a questa pagina.

Dopo aver apportato tutte le modifiche necessarie alla pagina, fai clic su Salva. Nella parte alta della pagina, fai scorrere il pulsante Non pubblicato per attivarlo e passare a Pubblicato, se necessario.

Ripeti gli step per tutti i partner.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/resellers.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_attribution.html "Resoconti attribuzione attività marketing") |
  * [precedente](quality_leads_report.html "Resoconto lead di qualità") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Partner


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