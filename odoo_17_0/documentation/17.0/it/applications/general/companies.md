# Aziende — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](companies/digest_emails.html "E-mail di riepilogo") |
  * [precedente](users/ldap.html "Autenticazione LDAP") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Aziende



# Aziende¶

Un ambiente di gestione centralizzato consente ad un amministratore di selezionare più aziende contemporaneamente così da configurare magazzini, clienti, attrezzature e contatti specifici. Fornisce la possibilità di generare rendiconti di cifre aggregate senza cambiare interfaccia facilitando le attività giornaliere e valorizzando l’intero processo di gestione.

Avvertimento

L’attivazione della funzionalità multi aziendale in un database Odoo con un piano _Standard_ attiva automaticamente un upsell al piano _Personalizzato_. Questo non si applica ai database del piano _Un’app gratuita_.

  * **Per contratti annuali o pluriennali** : viene creato un ordine di upselling con una scadenza di 30 giorni.

  * **Per contratti mensili** : l’abbonamento passa automaticamente al piano _Personalizzato_ e la nuova tariffa viene applicata al momento della creazione della fattura successiva.




Per maggiori informazioni, consulta la pagina [di Odoo con i vari prezzi](https://www.odoo.com/pricing-plan) o contatta il tuo account manager.

Per creare una nuova azienda, vai sulla app Impostazioni ‣ sezione Aziende e fai clic su Gestisci aziende. In seguito, fai clic su Nuova per creare una nuova azienda.

Prosegui per compilare il modulo relativo alla nuova azienda.

Suggerimento

Per archiviare un’azienda, vai sull” app Impostazioni ‣ sezione Aziende ‣ Gestisci aziende. In seguito, spunta la casella a sinistra dell’azienda per archiviarla. Se la pagina Aziende non si trova nella vista elenco, fai clic sull’icona ≣ (quattro barre), situata nell’angolo in alto a destra della pagina.

Dopo aver selezionato l’azienda corretta, fai clic sull’icona ⚙️ Azioni e seleziona Archivia dal menu a discesa che appare.

Per assicurarti che tutti i record relativi all’azienda archiviata siano stati a loro volta archiviati, contatta il [team di assistenza di Odoo](https://www.odoo.com/help).

Se un record non deve essere archiviato, c’è il rischio di riattivare l’azienda archiviata in precedenza e di creare di nuovo l’attività di upsell.

## Gestire aziende e record¶

Vai sull” app Impostazioni ‣ sezione Aziende ‣ Gestisci aziende. In seguito, fai clic su Nuova e riempi il modulo con le informazioni relative all’azienda o seleziona un’azienda già esistente per modificarla.

Suggerimento

Attiva la [modalità sviluppatore](developer_mode.html#developer-mode) per configurare gli account dei social network e i parametri di posta elettronica specifici dell’azienda. Consulta la documentazione [Marketing social](../marketing/social_marketing.html) and [Comunicazione in Odoo via e-mail](email_communication.html).

Le aziende hanno anche una Azienda principale configurata nel modulo dell’azienda in [modalità sviluppatore](developer_mode.html#developer-mode).

### Passare da un’azienda all’altra¶

Passa da un’azienda all’altra (o selezionane diverse) facendo clic sul nome dell’azienda, situato nell’angolo a destra del menu di intestazione, in qualsiasi punto del database. Spunta le caselle accanto ai nomi delle aziende desiderate per attivarle. L’azienda evidenziata rappresenta l’ambiente attualmente in uso. Per passare ad un altro ambiente, fai clic sul nome dell’azienda desiderata.

Example

Nell’esempio in basso, l’utente ha accesso a otto aziende, due sono attive e l’ambiente del database appartiene a: _My Company (San Francisco)_.

### Condividere record¶

I dati (come prodotti, contatti e attrezzatura) possono essere condivisi o configurati per essere mostrati solo per un’azienda specifica. Per farlo, nei vari moduli, scegli tra:

  * _Un campo vuoto_ : il record viene condiviso in tutte le aziende.

  * _Aggiungere un’azienda_ : il record è visibile agli utenti che hanno eseguito l’accesso per l’azienda specifica.




Quando viene selezionato un ambiente dal menu in alto, insieme ad un’altra azienda, i record vengono condivisi tra le due.

## Filiali¶

È possibile aggiungere filiali ad un’azienda. Vai su Impostazioni ‣ Sezione aziende ‣ Gestisci aziende. In seguito, seleziona l’azienda desiderata dall’elenco. Dal modulo contenente i dettagli dell’azienda, apri la scheda Filiali. Per aggiungere una filiale, fai clic su Aggiungi riga e completa il modulo pop-up Crea filiali che appare.

Suggerimento

Attiva la [modalità sviluppatore](developer_mode.html#developer-mode) per configurare gli account dei social network e i parametri del sistema di posta elettronica specifici dell’azienda. Consulta la documentazione [Marketing social](../marketing/social_marketing.html) and [Comunicazione in Odoo via e-mail](email_communication.html).

Le filiali hanno anche una Azienda principale configurata nel modulo della filiale stessa in [modalità sviluppatore](developer_mode.html#developer-mode). Le localizzazioni contabile e fiscale della filiale vengono impostate per l”Azienda principale. Per farlo, seleziona l’azienda dal _selettore di azeinde_ nel menu in alto e vai su Impostazioni ‣ Contabilità ‣ Posizioni di bilancio.

Pericolo

Se il database è stato acquistato con il piano _a pagamento_ standard, l’aggiunta di un branch a un’azienda comporta l’upselling. Dato che l’aggiunta di uno o più branch trasforma il database in un ambiente con aziende multiple, sarà necessario passare al piano «Personalizzato*. Questo non riguarda i database e i piani _Un’app gratuita_.

Per maggiori informazioni sui prezzi, consulta la pagina ` <<https://www.odoo.com/pricing-plan>>`

## Accesso dipendenti¶

Una volta che le aziende sono state create, gestisci i [Diritti di accesso](users/access_rights.html) per _Aziende multiple_ dei dipendenti.

Per accedere ai _Diritti di accesso_ , vai su Impostazioni ‣ sezione Utenti ‣ Gestisci utenti.

Dalla pagina Utenti, seleziona un utente dall’elenco per apportare modifiche. In seguito, modifica i campi delle Aziende consentite o Azienda predefinita.

È possibile configurare più aziende per le Aziende consentite e _solo una_ può essere configurata come Azienda predefinita.

Se un amministratore presenta più aziende attivate nel database e sta modificando un record, la modifica avviene nel record collegato all’azienda.

Example

Se si modifica un ordine di vendita prodotto in `JS Store US` mentre si lavora nell’ambiente `JS Store Belgium` , le modifiche vengono applicate a `JS Store US` (ovvero l’azienda che ha emesso l’ordine di vendita).

Quando si crea un record, l’azienda presa in considerazione è:

  * l’azienda attualmente selezionata nel selettore, nella parte superiore a destra dello schermo (quella evidenziata/attiva)




**OPPURE**

  * nessuna azienda configurata (perché nessuna è configurata nei moduli relativi a prodotti o contatti, ad esempio);




**OPPURE**

  * L’azienda configurata è collegata al documento (stessa cosa se si sta modificando un record).




## Formato documenti¶

Per configurare i formati dei documenti per ogni azienda, _attiva_ e _selezionane_ una per poi andare su Impostazioni ‣ sezione Aziende, fai clic su Configura struttura documento e modifica le informazioni.

I Dettagli azienda possono essere modificati nella struttura del documento. Per impostazione predefinita, il campo è popolato dalle informazioni elencate dell’azienda quando vai su: Impostazioni ‣ sezione Aziende ‣ Gestisci aziende e seleziona un’azienda dall’elenco.

## Transazioni interaziendali¶

Per prima cosa, attiva la [modalità sviluppatore](developer_mode.html#developer-mode). In seguito, assicurati che ogni azienda sia configurata nel modo giusto rispetto a:

  * [Piano dei conti](../finance/accounting/get_started/chart_of_accounts.html)

  * [Imposte](../finance/accounting/taxes.html)

  * [Posizioni di bilancio](../finance/accounting/taxes/fiscal_positions.html)

  * [Registri](../finance/accounting/bank.html)

  * [Localizzazione fiscale](../finance/fiscal_localizations.html)

  * [Listini prezzo](../sales/sales/products_prices/prices/pricing.html)




In seguito, vai su Impostazioni ‣ sezione Aziende ‣ Gestisci aziende. Successivamente, seleziona l’azienda desiderata dall’elenco. Nel modulo aziendale, seleziona la scheda Transazioni interaziendali, nel modulo con i dettagli della singola azienda.

Dopo aver attivato e selezionato la rispettiva azienda, scegli una delle seguenti opzioni Regola:

  * Non sincronizzare: non sincronizza nessuna transazione interaziendale.

  * Sincronizzazione fatture fornitore/cliente: genera una fattura quando un’azienda ne conferma una per l’azienda selezionata.

  * Synchronize Sales Order: generates a drafted sales order using the selected company warehouse, when a sales order is confirmed for the selected company. If, instead of a drafted sales order, it should be validated, enable Automatic Validation.*

  * Synchronize Purchase Order: generates a drafted purchase order using the selected company warehouse, when a purchase order is confirmed for the selected company. If, instead of a drafted purchase order, it should be validated, enable Automatic Validation.*

  * Synchronize Sales and Purchase Order: generates a drafted purchase/sales order using the selected company warehouse, when a sales/purchase order is confirmed for the selected company. If, instead of a drafted purchase/sales order, it should be validated, enable Automatic Validation.*

* È necessario selezionare l’opzione per far sì che la Convalida automatica appaia nella configurazione.




Nota

I prodotti **devono** essere configurati come Può essere venduto e condivisi tra le aziende. Consulta la documentazione [Product type](../inventory_and_mrp/inventory/product_management/configure/type.html).

Example

Sincronizzazione fatture: una fattura registrata su `JS Store Belgium` per `JS Store US`, crea automaticamente una fattura fornitore e genera un ordine di vendita/acquisto in stato di bozza utilizzando il magazzino dell’azienda selezionata, quando un ordine di vendita/acquisto viene confermato per l’azienda selezionata. Se, invece di essere nello stato di bozza un ordine di acquisto/vendita deve essere convalidato abilita la Convalida automatica.

Synchronize sales/purchase order: when a sale order for `JS Store US` is confirmed on `JS Store Belgium`, a purchase order on `JS Store Belgium` is automatically created (and confirmed, if the Automatic Validation feature was enabled).

Suggerimento

Ricordati di provare tutti i flussi di lavoro come utente _diverso_ dall’amministratore.

Vedi anche

  * [Linee guida aziende multiple](../../developer/howtos/company.html)

  * [Sistema multi valuta](../finance/accounting/get_started/multi_currency.html)




  * [E-mail di riepilogo](companies/digest_emails.html)
  * [Modelli e-mail](companies/email_template.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/companies.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](companies/digest_emails.html "E-mail di riepilogo") |
  * [precedente](users/ldap.html "Autenticazione LDAP") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Aziende


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
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning