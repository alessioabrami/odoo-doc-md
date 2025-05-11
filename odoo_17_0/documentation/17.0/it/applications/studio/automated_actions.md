# Regole di automazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pdf_reports.html "Reportistica in PDF") |
  * [precedente](models_modules_apps.html "Modelli, moduli e app") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di automazione



# Regole di automazione¶

Le regole di automazione vengono utilizzare per attivare modifiche automatiche in base alle azioni dell’utente (ad es. applicare una modifica quando un campo è impostato su un valore specifico), eventi e-mail, condizioni di tempo (ad es. archiviare un record 7 giorni dopo l’ultimo aggiornamento) oppure eventi esterni.

Per creare una regola di automazione con Studio, procedere come segue:

  1. [apri Studio](../studio.html#studio-access) e fai clic su Automazioni e poi Nuova

  2. seleziona il Attivazione e, se necessario, completa i campi che appaiono sullo schermo in base al trigger scelto

  3. fai clic su Aggiungi un’azione, per poi selezionare il Tipo di action e compila i campi che appaiono sullo schermo in base all’azione selezionata

  4. fai clic su Salva e chiudi oppure su Salva e nuova.




Example

Suggerimento

  * Per modificare il [modello](models_modules_apps.html) della regola di automazione, cambia modelli prima di fare clic su Automazioni in Studio oppure [attiva la modalità sviluppatore](../general/developer_mode.html#developer-mode), crea o modifica la regola di automazione e seleziona il Modello nel modulo Regole di automazione.

  * Inoltre, puoi creare regole di automazione da qualsiasi fase kanban facendo clic sull’icona a forma di ingranaggio (⚙ ) accanto al nome della fase kanban per poi selezionare Automazioni. In questo caso, il trigger è impostato su La fase è impostata su per impostazione predefinita ma puoi modificarlo se necessario.




## Attivazione¶

Il Trigger viene utilizzato per indicare quale regola di automazione applicare. I trigger disponibili dipendono dal [modello](models_modules_apps.html). In totale, sono disponibili cinque categorie di trigger:

  * studio/automated-actions/trigger/valori-aggiornati

  * studio/automated-actions/trigger/eventi-e-mail

  * studio/automated-actions/trigger/condizioni-temporali

  * studio/automated-actions/trigger/personalizzato

  * studio/automated-actions/trigger/esterno




Suggerimento

È possibile indicare un Dominio prima dell’aggiornamento per specificare le condizione che devono essere rispettate _prima_ di attivare la regola di automazione. Al contrario, le condizioni definite utilizzando i filtri Condizioni extra e Applica a vengono verificate _durante_ l’esecuzione della regola di automazione.

Per indicare un Dominio prima dell’aggiornamento, [attiva la modalità sviluppatore](../general/developer_mode.html#developer-mode), crea o modifica una regola di automazione, fai clic su Modifica dominio e poi su Nuova regola.

Ad esempio, se vuoi che l’azione automatizzata si attivi quando un indirizzo e-mail viene aggiunto a un contatto che non aveva un indirizzo in precedenza (a differenza della modifica dell’indirizzo esistente), imposta il Dominio prima dell’aggiornamento su E-mail non configurata e il dominio Applica a su E-mail configurata.

### Valori aggiornati¶

I trigger disponibili in questa categoria dipendono dal modello e si basano sulle modifiche dei campi comuni come l’aggiunta di tag specifici (ad es., ad un lavoro) oppure la configurazione del campo Utente. Seleziona il trigger e poi un valore se necessario,

### E-mail eventi¶

Attiva azioni automatizzate dopo aver ricevuto o inviato e-mail.

### Condizioni di tempo¶

Attiva azioni automatizzate in base al campo data. Sono disponibili i seguenti trigger:

  * In base al campo data: seleziona il campo da utilizzare accanto al campo Ritardo

  * Dopo la creazione: l’azione viene attivata quando un record viene creato e salvato

  * Dopo l’ultimo aggiornamento: l’azione viene attivata quando un record esistente viene modificato e salvato.




In seguito, puoi indicare:

  * un Ritardo: specifica il numero di minuti, ore, giorni o mesi. Per attivare l’azione prima della data trigger, indica un numero negativo. Se scegli il trigger In base al campo data, devi anche selezionare il campo data da usare per determinare il ritardo.

  * Condizioni extra: fai clic su Aggiungi condizione per poi specificare le condizioni da rispettare per attivare la regola di automazione. Fai clic su Nuova regola per aggiungere un’altra condizione.




L’azione viene attivata una volta raggiunto il ritardo e rispettate le condizioni.

Example

Se vuoi inviare un promemoria via e-mail 30 minuti prima dell’inizio di un evento nel calendario, seleziona Inizio (evento calendario) sotto la Data trigger e imposta il Ritardo a **-30** Minuti.

Nota

Per impostazione predefinita, il pianificatore controlla le date trigger ogni 4 ore, ciò significa che la granularità inferiore nelle automazioni basate sul tempo potrebbe non essere sempre rispettata.

### Personalizzata¶

Azioni automatizzate trigger:

  * Al salvataggio: quando il record viene salvato

  * Al momento dell’eliminazione: quando un record viene eliminato

  * Al momento della modifica IU: quando il valore di un campo viene modificato nella [vista modulo](views.html#studio-views-general-form), anche prima di aver salvato il record.




Per i trigger Al momento del salvataggio e Al momento della modifica IU, **devi** selezionare i campi da utilizzare per attivare la regola di automazione nel campo Quando si aggiorna.

Avvertimento

Se non viene selezionata nessuna opzione per il campo Quando si aggiorna, l’azione automatizzata potrebbe essere eseguita più volte per record.

In alternativa, puoi anche indicare condizioni aggiuntive da rispettare per attivare la regola di automazione nel campo Applica a.

Nota

Il trigger Al momento della modifica IU può essere utilizzato solamente con l’azione Esegui codice e funziona solo quando viene effettuata una modifica manualmente. L’azione non viene eseguita se il campo viene modificato attraverso un’altra regola automatizzata.

### Esterno¶

Trigger per azioni automatizzate in base a un evento esterno utilizzando un webhook. Un webhook è un metodo di comunicazione tra due sistemi in cui il sistema di origine invia una richiesta HTTP(S) al sistema di destinazione in base a un evento specifico. Di solito include un carico di dati contenente informazioni sull’evento che si è verificato.

Per configurare il trigger Con il webhook, copia l”URL generato da Odoo nel sistema di destinazione (ad es., il sistema che riceve la richiesta). In seguito, nel campo Record di destinazione, inserisci il codice da eseguire per indicare i record da aggiornare usando la regola di automazione.

Avvertimento

L’URL deve essere **segreto** , la condivisione online o senza attenzione potrebbe esporre il tuo sistema a soggetti malintenzionati. Fai clic sul pulsante Ruota secret per modificare il secret dell’URL se necessario.

Nota

  * Il codice predefinito indicato nel campo Record di destinazione funziona per webhook provenienti da un altro database Odoo. Viene utilizzato per indicare i record da aggiornare utilizzando l’informazione nel payload.

  * Se desideri utilizzare il contenuto del webhook per un altro motivo diverso dal trovare il record (ad es., _creare_ un record), l’unica opzione è utilizzare un’azione Esegui codice. In questo caso, il campo Record di destinazione deve contenere un codice valido ma il risultato non ha nessun effetto sull’azione automatizzata.

  * Il contenuto del webhook è disponibile nel contesto dell’azione server come una variabile `payload` (ad es., un dizionario che contiene i parametri GET o il corpo POST JSON della richiesta in entrata).




Puoi anche scegliere l’opzione Registra chiamate per registrare i payload ricevuti, ad es., per assicurarti che i dati inviati dal sistema di origine corrispondano al formato e al contenuto previsti. . To access the logs, click the Logs smart button at the top of the Automation rules form.

## Azioni da eseguire¶

Una volta indicato il trigger delle regole di automazione, fai clic su Aggiungi azione per definire l’azione da eseguire.

Suggerimento

È possibile indicare più azioni per lo stesso trigger o regola di automazione. Le azioni vengono eseguite nell’ordine in cui sono indicate. Ciò significa, ad esempio, che se indichi un’azione Aggiorna record e poi un’azione Invia e-mail, l’e-mail utilizzerà i valori aggiornati. Tuttavia, se l’azione Invia e-mail viene definita prima dell’azione Aggiorna record, l’e-mail utilizzerà i valori impostati _prima_ dell’esecuzione dell’azione aggiornata.

### Aggiorna record¶

L’azione permette di aggiornare uno dei campi del record. Fai clic sul campo Aggiorna e, nell’elenco che si apre, seleziona o cerca il campo da aggiornare. Fai clic sulla freccia a destra accanto al nome del campo per accedere all’elenco di campi correlati se necessario.

If you selected a [many2many field](fields.html#studio-fields-relational-fields-many2many), choose whether the field must be updated by Adding, Removing, or Setting it to the selected value or by Clearing it.

Example

Se vuoi che l’azione automatizzata elimini un tag dal record di un cliente, imposta il campo Aggiorna su Cliente > Tag, seleziona Rimuovendo per poi scegliere il tag.

Suggerimento

Alternatively, you can also set a record’s field dynamically using Python code. To do so, select Compute instead of Update, then enter the code to be used for computing the field’s value. For example, if you want the automation rule to compute a custom [datetime field](fields.html#studio-fields-simple-fields-date-time) when a task’s priority is set to `High` (by starring the task), you can define the trigger Priority is set to to `High` and define the Update Record action as follows:

### Crea attività¶

Quest’azione viene utilizzata per programmare una nuova attività collegata al record. Seleziona un Tipo di attività, inserisci un Titolo e una descrizione per poi specificare quando vuoi che l’attività venga programmata nel campo Data di scadenza tra e seleziona un Tipo di utente:

  * per assegnare sempre l’attività allo stesso utente, seleziona Utente specifico e aggiungi l’utente nel campo Responsabile;

  * per raggiungere un utente collegato al record in modo dinamico, seleziona Utente dinamico (in base al record) e modifica il Campo utente se necessario.




Example

Dopo aver convertito un lead in opportunità, vuoi che l’azione automatizzata programmi una chiamata per l’utente responsabile del lead. Per farlo, configura il Tipo di attività su Utente dinamico (in base al record).

### Inviare e-mail e SMS¶

Queste azioni vengono utilizzate per inviare un’e-mail o un messaggio di testo a un contatto collegato a un record specifico. Per farlo, seleziona o crea un Modello e-mail o un Modello SMS, e poi nel campo Invia e-mail come o Invia SMS come, scegli come vuoi inviare l’e-mail o il messaggio di testo:

  * E-mail: per inviare il messaggio come e-mail ai destinatari del Modello e-mail

  * Messaggio: per registrare il messaggio sul record e notificare i follower.

  * Nota: per inviare il messaggio come nota interna visibile agli utenti interni nel chatter

  * SMS (senza nota): per inviare il messaggio come messaggio di testo ai destinatari del modello SMS.

  * SMS (con nota): per inviare il messaggio come messaggio di testo ai destinatari del modello SMS e registrarlo come nota interna nel chatter.

  * Solo nota: per registrare il messaggio solo come nota interna nel chatter.




### Aggiungere ed eliminare follower¶

Utilizza queste azioni per iscrivere o annullare l’iscrizione di contatti esistenti al/dal record.

### Crea record¶

L’azione viene utilizzata per creare un nuovo record su ogni modello.

Seleziona il modello richiesto per il campo Record da creare che contiene il modello attuale per impostazione predefinita. Specifica un Nome per il record e poi, se vuoi creare il record su un altro modello, seleziona un campo nel Campo link per collegare il record che ha attivato l’azione del nuovo record.

Nota

The dropdown list related to the Link Field field only contains [one2many fields](fields.html#studio-fields-relational-fields-one2many) existing on the current model that are linked to a [many2one field](fields.html#studio-fields-relational-fields-many2one) on the target model.

Suggerimento

È possibile creare un’altra regola di automazione con azioni Aggiorna record per aggiornare i campi del nuovo record se necessario. Ad esempio, puoi utilizzare un’azione Crea record per creare un nuovo lavoro e assegnarlo a un utente specifico utilizzando l’azione Aggiorna record.

### Esegui codice¶

L’azione viene utilizzata per eseguire il codice Python. Puoi inserire il codice nella scheda Codice utilizzando le seguenti variabili:

  * `env`: ambiente in cui viene attivata l’azione

  * `model`: modello del record su cui l’azione viene attivata, è un recordset vuoto

  * `record`: record su cui l’azione viene attivata, potrebbe essere vuoto

  * `più record`: recordset di tutti i record su cui l’azione viene attivata in modalità multipla, questo potrebbe restare vuoto

  * `time`, `datetime`, `dateutil`, `timezone`: librerie Python utili

  * `float_compare`: funzione di utilità per confrontare i float in base a una precisione specifica

  * `log(message, level='info')`: funzione di logging per registrare le informazioni di debug nella tabella ir.logging

  * `_logger.info(message)`: logger per emettere messaggi nei log del server

  * `UserError`: classe di eccezione per visualizzare messaggi di avviso per gli utenti

  * `Command`: x2many spazio nome comando

  * `action = {...}`: per restituire un’azione




Suggerimento

Le variabili disponibili vengono descritte nelle schede Codice e Aiuto

### Invia notifica Webhook¶

Quest’azione permette di inviare una richiesta POST con i valori dei Campi all’URL specificato nel campo URL.

Il Payload campione fornisce un’anteprima dei dati inclusi nella richiesta utilizzando i dati di un record a caso o dati campione se non ci sono record disponibili.

### Esegui azioni esistenti¶

L’azione viene utilizzata per attivare più azioni (collegate al modello attuale) nello stesso momento. Per farlo, fai clic su Aggiungi una riga, poi nella finestra pop-up Aggiungi: azioni figlie e seleziona un’azione esistente oppure fai clic su Nuova per crearne una nuova.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/studio/automated_actions.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pdf_reports.html "Reportistica in PDF") |
  * [precedente](models_modules_apps.html "Modelli, moduli e app") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di automazione


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