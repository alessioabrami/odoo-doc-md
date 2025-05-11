# Assegnare lead con calcolo previsionale — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](unattended_leads_report.html "Resoconto lead non seguiti") |
  * [precedente](../track_leads.html "Assegnare e tracciare i contatti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Assegnare lead con calcolo previsionale



# Assegnare lead con calcolo previsionale¶

L’applicazione _CRM_ di Odoo può assegnare automaticamente i lead/opportunità ai team di vendita e agli addetti alle vendite. Una pratica standard è quella di assegnare i lead in base alla probabilità di vincita di ciascuno. Le aziende possono dare priorità ai lead che hanno maggiori probabilità di portare a buon fine gli affari, assegnandoli rapidamente ai venditori appropriati.

Odoo calcola automaticamente la probabilità di aggiudicarsi ogni lead utilizzando un metodo chiamato _calcolo previsionale lead_.

## Calcolo previsionale dei lead¶

Il calcolo previsionale dei lead è un modello di apprendimento automatico che utilizza i dati storici di Odoo _CRM_ per assegnare un punteggio ai lead/opportunità aperti.

Quando un’azienda elabora le opportunità attraverso la pipeline del CRM, Odoo raccoglie dati sulle opportunità vinte e perse. Il calcolo previsionale dei lead utilizza questi dati per prevedere la probabilità di vincita di ogni nuovo lead od opportunità.

Più opportunità vengono inviate attraverso la pipeline del CRM, più dati Odoo raccoglie, con conseguenti probabilità più accurate.

Nello specifico, il calcolo previsionale di lead di Odoo usa il classificatore _naive Bayes_ :

\\[\begin{equation} P(A | B) = \frac{P(A) \times P(B | A)}{P(B)} \end{equation}\\]

Scomposizione dell’equazione:

  * P(A|B) = la probabilità di un lead di successp _in questo caso_

  * P(A) = la probabilità complessiva di successo di un lead indipendentemente dalle condizioni

  * P(B|A) = la probabilità che ciò si verifichi in presenza di un lead di successo

  * P(B) = la probabilità che ciò avvenga




Il termine _in questo caso_ si riferisce alle variabili che possono influenzare il successo di un lead in Odoo. Queste possono includere variabili come l’addetto alle vendite assegnato, la fonte del lead, la lingua del lead e altri dati storici e demografici.

Le variabili da considerare nel calcolo possono essere configurate per adattare il calcolo ai bisogni di ogni business.

La probabilità di successo di ogni opportunità viene visualizzata nel modulo dell’opportunità e si aggiorna automaticamente man mano che l’opportunità avanza nella pipeline del CRM.

Quando un’opportunità passa alla fase successiva, la sua probabilità di successo aumenta automaticamente in base all’algoritmo del calcolo previsionale dei lead.

### Configurazione¶

Il calcolo previsionale di lead è sempre attivo in Odoo _CRM_. Tuttavia, le variabili utilizzate per calcolare la probabilità di successo possono essere personalizzate nelle impostazioni.

Per personalizzare le variabili utilizzate dal calcolo previsionale di lead, accedi al modulo CRM ‣ Configurazione ‣ Impostazioni. Nella sezione Calcolo previsionale lead, fai clic sul pulsante Aggiorna probabilità.

In seguito, fai clic sul menu a discesa per scegliere le variabili che la funzione di calcolo previsionale di lead prenderà in considerazione.

È possibile attivare un numero qualsiasi delle seguenti variabili:

  * Stato: lo stato geografico da cui deriva l’opportunità

  * Paese: lo stato geografico da cui deriva l’opportunità

  * Qualità telefono: se esiste o meno un numero di telefono per l’opportunità

  * Qualità e-mail: se è presente o meno un indirizzo e-mail per l’opportunità

  * Origine: l’origine di un’opportunità (ad es. motore di ricerca, social media)

  * Lingua: la lingua parlata specificata per l’opportunità

  * Tag: i tag assegnati all’opportunità




Nota

Le variabili `Fase` e `Team` sono sempre attive. `Fase` si riferisce alla fase della pipeline CRM in cui si trova un’opportunità. Il `Team` si riferisce al team di vendita assegnato a un’opportunità. Il calcolo previsionale dei lead tiene _sempre_ conto di queste due variabili, indipendentemente dalle variabili opzionali selezionate.

In seguito, fai clic sul campo della data accanto all’opzione Considera i lead creati a partire dal: per selezionare la data a partire dalla quale inizierà il calcolo previsionale di lead.

Infine, fai clic su Conferma per salvare le modifiche.

### Modificare la probabilità manualmente¶

La probabilità di successo di un’opportunità può essere modificata manualmente nel modulo dell’opportunità. Fai clic sul numero della probabilità per modificarlo.

Importante

La modifica manuale della probabilità elimina gli aggiornamenti automatici della probabilità per quell’opportunità. La probabilità non si aggiornerà più automaticamente man mano che l’opportunità passa attraverso ogni fase della pipeline.

Per riattivare la probabilità automatica, fai clic sull’icona dell’ingranaggio accanto alla percentuale di probabilità.

## Assegnare lead in base alla probabilità¶

Odoo _CRM_ può assegnare lead/opportunità ai team di vendita e agli addetti vendite in base a regole specifiche. Crea regole di assegnazione basate sulla probabilità di successo dei lead per dare priorità a quelli che hanno maggiori probabilità di diventare veri e propri affari.

### Configurare assegnazioni basate su regole¶

Per attivare le _assegnazioni basate su regole_ , accedi al modulo CRM ‣ Configurazione ‣ Impostazioni e attiva la funzione Assegnazione basata su regole.

La funzione di assegnazione basata su regole può essere impostata per funzionare Manualmente, ovvero un utente di Odoo deve attivare manualmente l’assegnazione, oppure Ripetutamente, ovvero Odoo attiverà automaticamente l’assegnazione in base al periodo di tempo scelto.

Per impostare l’assegnazione automatica dei lead, seleziona Ripetutamente per la sezione In esecuzione. In seguito, personalizza la frequenza con cui Odoo attiverà l’assegnazione automatica nella sezione Ripeti ogni.

Se l’assegnazione basata su regole è impostata per essere eseguita Ripetutamente, l’assegnazione può ancora essere attivata manualmente usando l’icona della freccia circolare nelle impostazioni Assegnazione basata su regole (o usando il pulsante Assegna lead nella pagina di configurazione del team di vendita).

### Configurare regole di assegnazione¶

Successivamente, configura le _regole di assegnazione_ per ciascun team di vendita e/o venditore. Queste regole determinano quali lead Odoo assegna a quali persone. Per iniziare, apri il modulo CRM ‣ Configurazione ‣ Team di vendita e seleziona un team di vendita.

Nel modulo di configurazione del team di vendita, sotto la sezione Regole di assegnazione, fai clic su Modifica dominio per configurare le regole che Odoo utilizza per determinare l’assegnazione dei lead per questo team di vendita. Le regole possono includere tutto ciò che può essere rilevante per l’azienda o il team in questione e si può aggiungere un numero qualsiasi di regole.

Fai clic su Aggiungi filtro per iniziare a creare regole di assegnazione. Fai clic sul simbolo + a destra della regola di assegnazione per aggiungere un’altra riga. Fai clic sul simbolo x per rimuovere la riga.

Per creare una regola di assegnazione basata sulla probabilità di successo di un’opportunità, fai clic sul menu a discesa all’estrema sinistra di una riga della regola di assegnazione e seleziona Probabilità.

Dal menu a tendina centrale, seleziona il simbolo dell’equazione desiderata, probabilmente il simbolo per _maggiore di_ , _inferiore a_ , _maggiore o uguale a_ , o _inferiore o uguale a_.

Nello spazio all’estrema destra, inserisci il valore numerico desiderato della probabilità. Infine, fai clic su Salva per salvare le modifiche.

Example

Per configurare una regola di assegnazione in modo che un team di vendita riceva lead con una probabilità di successo pari o superiore al 20%, crea una riga Dominio che reciti: `Probabilità >= 20`.

È possibile configurare regole di assegnazione separate per i singoli membri del team. Dalla pagina di configurazione del team di vendita, fai clic su un membro del team nella scheda Membri, quindi modifica la sezione Dominio. Fai clic su Salva per salvare le modifiche.

Se l’assegnazione automatica dei contatti è configurata nelle impostazioni, sia il team di vendita che i singoli membri del team hanno la possibilità di Saltare l’assegnazione automatica. Seleziona questa casella per escludere un particolare team di vendita o un addetto vendite dall’assegnazione automatica di lead da parte della funzione di assegnazione basata su regole di Odoo. Se l’opzione Salta assegnazione automatica è attivata, il team di vendita o l’addetto vendite possono comunque essere assegnati manualmente.

Per assegnare manualmente lead a questo team di vendita, fai clic sul pulsante Assegna lead nella parte superiore della pagina di configurazione del team di vendita. In questo modo verranno assegnate tutti i lead attualmente non assegnati e che corrispondono al dominio specificato del team.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/track_leads/lead_scoring.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](unattended_leads_report.html "Resoconto lead non seguiti") |
  * [precedente](../track_leads.html "Assegnare e tracciare i contatti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Assegnare e tracciare i contatti](../track_leads.html) »
  * Assegnare lead con calcolo previsionale


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