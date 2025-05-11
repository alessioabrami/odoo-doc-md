# Problemi e-mail comuni e soluzioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../integrations.html "Integrazioni") |
  * [precedente](mailjet_api.html "API Mailjet") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Problemi e-mail comuni e soluzioni



# Problemi e-mail comuni e soluzioni¶

La presente pagina elenca i problemi più comuni relativi all’invio di e-mail e alcune possibili soluzioni.

## Odoo non è un fornitore di servizi e-mail¶

Odoo non funziona come una casella di posta classica ovvero Gmail, Outlook, Yahoo, ecc.

Sebbene Odoo utilizzi le e-mail come mezzo per notificare e comunicare con gli utenti/clienti, per sua stessa concezione non sostituisce un server e-mail dedicato. Pertanto, potrebbe non comportarsi nel modo previsto rispetto a una casella di posta elettronica tradizionale.

Le differenze principali sono le seguenti:

  * Per impostazione predefinita, una volta che un’e-mail di notifica o di transazione (preventivo, fattura, messaggio diretto a un contatto) è stata inviata con successo, l’oggetto e-mail viene eliminato. Il contenuto del messaggio di posta elettronica rimane nella chat del record correlato. In questo modo si evita di ingombrare il database con più copie del contenuto della stessa e-mail (se inviata a più destinatari), se il contenuto è già presente nel chatter.

  * Non esiste il concetto di copia per conoscenza nascosta (CCN). Odoo utilizza il concetto di _follower_ aggiunti al chatter per decidere automaticamente quando e come un [contatto viene notificato](email_servers_outbound.html#email-outbound-notifications) o riceve la copia di un’e-mail.

  * Le e-mail in entrata vengono gestite controllando se l’indirizzo e-mail _A_ è un indirizzo e-mail valido nel database di Odoo o, in caso di e-mail di risposta, se nell’intestazione dell’e-mail c’è un riferimento che corrisponde a un messaggio inviato dal database di Odoo. Tutte le altre e-mail saranno rimbalzate e **non** parcheggiate temporaneamente in una cartella spam o di quarantena. In altre parole, qualsiasi e-mail non correlata a un database Odoo viene persa.




## E-mail in uscita¶

### Modificare l’indirizzo e-mail dell’account utente amministratore¶

Al momento della creazione di un database Odoo, all’account admin principale viene assegnato un indirizzo e-mail segnaposto. È consigliato **sostituire l’indirizzo e-mail admin** con un indirizzo e-mail valido per evitare problemi con le e-mail in uscita.

Per farlo, nell’account admin, fai clic sull’icona utente, Il mio profilo (o Preferenze) e aggiorna il campo E-mail nella scheda Preferenze. Puoi utilizzare qualsiasi altro indirizzo e-mail oppure il tuo sottodominio Odoo (ad es., `company-name.odoo.com`) e `admin` per la parte locale (ad es., `admin@company-name.odoo.com`).

### Errore nella consegna¶

Quando invii un messaggio, nel chatter appare l’icona __(lettera). L’icona diventa rossa quando la consegna non è riuscita per almeno un destinatario.

Fai clic con il tasto destro del mouse sulla busta per visualizzare le informazioni sulla consegna e, se possibile, i messaggi di errore rilevanti.

Fai clic su Vedi dettagli errore per ottenere più informazioni sulle ragioni del fallimento, **se** Odoo è stato in grado di elaborare l’errore originale o l’e-mail di rimbalzo.

Fai clic su Invia e chiudi per provare a inviare di nuovo l’e-mail a tutti i destinatari **selezionati** (__) nella colonna Prova di nuovo.Tutti i destinatari **non selezionati** (__) verranno ignorati.

Fai clic su Ignora tutti per ignorare tutte le e-mail non riuscite e l’icona della busta diventerà bianca.

Le e-mail non inviate appaiono nella lista di attesa di Odoo. Per accedervi, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode) e vai su Impostazioni ‣ Funzioni tecniche ‣ E-mail: E-mail.

Le e-mail non riuscite hanno come stato Consegna non riuscita. Fai clic su Riprova per inserire di nuovo un’e-mail nella coda. In seguito, lo stato diventerà In uscita. L’e-mail verrà inviata di nuovo quando verrà eseguita l’azione programmata per la coda e-mail.

In alternativa, le e-mail in coda possono essere inviate immediatamente facendo clic su Invia ora. Fai clic su Annulla e-mail per eliminarla dalla coda.

Nota

Le e-mail inviate vengono eliminate periodicamente dalla coda. Questo viene eseguito dall’azione programmata _Pulizia automatica_ che elimina i dati ridondanti dal database Odoo.

#### Messaggi di errore comuni¶

##### Limite giornaliero raggiunto¶

Odoo limita il numero di e-mail che possono essere inviate da un database di Odoo online. La maggior parte dei fornitori di servizi di posta elettronica (ad esempio, Google, Yahoo, ecc.) inserisce l’IP del server di Odoo nella lista nera se il server e-mail di Odoo invia troppe e-mail a indirizzi inesistenti o non più validi. Questo vale anche per le e-mail di spam non richieste inviate attraverso un database di Odoo.

Il limite di e-mail giornaliero predefinito varia da **5 a 200**. Il limite esatto dipende da vari fattori (soggetti a modifiche):

  * tipo di abbonamento database (una app gratuita, prova, abbonamento a pagamento)

  * App installate (ad es., E-mail marketing, Automazione marketing)

  * Se è in corso la migrazione di un database.




Se raggiungi il limite giornaliero, puoi:

  * contattare il supporto Odoo per aumentare la quota di e-mail. Verranno presi in considerazione i seguenti fattori:

    1. numero di utenti del database;

    2. App installate;

    3. Tasso di rimbalzo (percentuale degli indirizzi e-mail che non hanno ricevuto e-mail perché rispedite al mittente da un server e-mail nel percorso verso il destinatario finale);

    4. [Alias e-mail configurati correttamente e utilizzo dei domini personalizzati appropriati](email_servers_outbound.html#email-outbound-alias-domain).

Suggerimento

Quando utilizzi un dominio personalizzato, verifica che i parametri [SPF](email_domain.html#email-domain-spf), [DKIM](email_domain.html#email-domain-dkim) e [DMARC](email_domain.html#email-domain-dmarc) siano configurati correttamente in modo da [permettere ai server e-mail di Odoo di inviare e-mail a nome del tuo dominio personalizzato](email_servers_outbound.html#email-outbound-custom-domain-odoo-server).

  * [Utilizza un server e-mail in uscita esterno](../email_communication.html) per non dipendere dal limite di e-mail di Odoo.

  * Aspetta fino al giorno successivo e prova a inviare di nuovo l’e-mail. Per farlo, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode), vai su Impostazioni ‣ Funzioni tecniche ‣ E-mail: E-mail e fai clic su Riprova accanto all’e-mail non inviata.




Importante

Il limite giornaliero di e-mail conta ogni e-mail inviata dal tuo database Odoo, manualmente o automaticamente. Per impostazione predefinita, qualsiasi messaggio interno, notifica, nota, ecc. conta come e-mail se notifica qualcuno via e-mail. Questo può essere mitigato ricevendo [notifiche in Odoo](../../productivity/discuss.html#discuss-app-notification-preferences) e non via e-mail.

##### Errore SMTP¶

Il [Simple Mail Transport Protocol (SMTP)](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) è uno standard utilizzato per trasmettere e-mail tra server e-mail e/o client e-mail.

Se utilizzi [un server STMP esterno per inviare e-mail](email_servers_outbound.html#email-outbound-custom-domain-smtp-server), esiste un set standard di [codici errore SMTP](https://en.wikipedia.org/wiki/List_of_SMTP_server_return_codes#Common_status_codes). Mentre i numeri dei codici non sono specifici per Odoo, il contenuto esatto del messaggio di errore potrebbe variare da un server e-mail all’altro.

Example

Un errore di consegna permanente SMTP 550 da sendgrid.com:
    
    
    Mail Delivery Failed
    Mail delivery failed via SMTP server 'None'.
    SMTPDataError: 550
    The from address does not match a verified Sender Identity. Mail cannot be sent until this
    error is resolved. Visit https://sendgrid.com/docs/for-developers/sending-email/sender-identity/
    to see the Sender Identity requirements
    

Il messaggio di errore indica che si è tentato di inviare un’e-mail da un indirizzo e-mail non verificato. Un buon punto di partenza per risolvere il problema è indagare sulla configurazione del server e-mail in uscita o sull’indirizzo _Da_ predefinito del database e verificare che l’indirizzo e-mail sia stato inserito nella whitelist di sendgrid.com.

Di solito, inserendo il contenuto del messaggio di errore in una ricerca su Google si possono ottenere informazioni sulla causa principale e su come correggere il problema.

Se il problema non può essere risolto e continua a verificarsi, contatta il supporto Odoo.

##### Nessun errore popolato¶

Odoo non è sempre in grado di fornire informazioni sul motivo per cui una consegna non è andata a buon fine. I diversi fornitori di posta elettronica implementano la propria politica sulle e-mail respinte e non sempre Odoo è in grado di interpretarla correttamente.

Se esiste un problema ricorrente con lo stesso cliente o dominio, contatta il supporto Odoo.

Nota

Una delle ragioni più comuni dietro il mancato invio di un’e-mail senza messaggi di errore è collegata alla configurazione dello [SPF](email_domain.html#email-domain-spf) o del [DKIM](email_domain.html#email-domain-dkim). Inoltre, verifica che la configurazione delle notifiche e-mail venga adattata ai tuoi bisogni aziendali. Consulta la sezione della documentazione [Comunicare in Odoo via e-mail](../email_communication.html).

### Tempo di esecuzione¶

Il momento esatto dell’invio di un’e-mail è gestito da un’utilità di sistema _cron_ (azione pianificata) che può essere utilizzata per pianificare attività da eseguire automaticamente a intervalli predeterminati. Odoo utilizza questo approccio per l’invio di e-mail considerate “non urgenti” (ad esempio, formati di newsletter come mailing di massa, automazione del marketing ed eventi). In questo modo si evita di ingombrare i server e-mail e si dà invece priorità alle comunicazioni individuali.

What is a cron?

Un cron è un’azione che Odoo esegue in background per eseguire un particolare codice per completare un’attività. Odoo crea anche trigger cron in alcuni flussi di lavoro che possono attivare un’azione pianificata prima della data prevista. L’esecuzione manuale di un’azione pianificata o la modifica della sua frequenza è generalmente sconsigliata, in quanto potrebbe creare errori o interrompere flussi di lavoro specifici.

Per impostazione predefinita, per la normale coda di e-mail, il cron E-mail: gestore coda e-mail viene eseguito ogni 60 minuti. L’intervallo minimo di esecuzione di un cron è di 5 minuti. Odoo raccomanda un intervallo di 15 minuti per garantire un funzionamento corretto. Se l’intervallo è troppo breve, è possibile che non tutte le e-mail vengano elaborate e che il cron vada in timeout.

Le e-mail considerate urgenti (da una persona a un’altra, come ordini di vendita, fatture, ordini di acquisto, ecc.) vengono inviate immediatamente. Non appaiono in Impostazioni ‣ Funzioni tecniche ‣ E-mail: E-mail, a meno che la consegna fallisca.

Le campagne e-mail vengono inviate il prima possibile (dopo aver fatto clic sul pulsante Invia) o quando programmate (dopo aver fatto clic sul pulsante Pianifica).

Per la coda e-mail marketing, il cron E-mail marketing: elabora coda viene eseguito una volta al giorno ma viene **attivato automaticamente** se una campagna è programmata al di fuori della frequenza predefinita. Se una mailing list contiene un gran numero di destinatari, l’attivazione manuale del cron ripetuta **non è consigliata** in quanto non accelererà il tempo di elaborazione e potrebbe causare errori.

Suggerimento

Per modificare i cron, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode) e vai su Impostazioni ‣ Funzioni tecniche ‣ Automazione: Azioni programmate.

Vedi anche

Per maggiori informazioni sui cron utilizzati in Odoo.sh, consulta la sezione [Domande tecniche frequenti Odoo.sh](../../../administration/odoo_sh/advanced/frequent_technical_questions.html).

#### Campagne E-mail marketing bloccate nella coda¶

Se nella coda vengono messe varie campagne e-mail marketing, quest’ultime vengono elaborate in ordine cronologico in base alla data di creazione.

Example

Se ci sono tre campagne: Campagna_1 (creata il primo gennaio), Campagna_2 (creata il 2 gennaio) e Campagna_3 (creata il 3 gennaio), tutte e tre vengono inserite nella coda facendo clic sul pulsante Invia.

Il cron proverà a elaborare Campagna_1, poi Campagna_2 e infine Campagna_3. Non inizierà a elaborare Campagna_2 fino a quando l’elaborazione di Campagna_1 non sarà terminata.

Se una campagna e-mail non scompare dalla coda, significa che potrebbe esserci un problema con la prima campagna della coda. Per individuare il problema, potremmo eliminare Campagna_1 dalla coda facendo clic sul pulsante Annulla e vedere se le due altre campagne vengono inviate. In seguito, potremmo provare a sistemare la Campagna_1 o contattare il supporto Odoo.

## E-mail in arrivo¶

Quando c’è un problema con le e-mail in arrivo, potrebbe non esserci un’indicazione, di per sé, in Odoo. È il client e-mail di invio, che cerca di contattare un database, a ricevere un messaggio di rimbalzo (il più delle volte un messaggio di errore 550: casella di posta non disponibile).

### E-mail non ricevuta¶

Odoo OnlineOdoo.sh

Contatta il supporto Odoo se si verifica sempre lo stesso problema con lo stesso cliente o dominio.

È possibile utilizzare i registri del database per comprendere e risolvere i problemi. I registri sono una raccolta di tutte le attività completate in un database. Sono una rappresentazione di solo testo, completa di timestamp di ogni azione eseguita sul database Odoo. Questo può essere utile per tenere traccia delle e-mail che lasciano il database. I registri possono anche mostrare i fallimenti dell’invio, quando indicano che il messaggio ha tentato di essere inviato ripetutamente. I registri mostrano ogni azione verso i server e-mail dal database.

I registri in tempo reale si trovano nella cartella `~/logs/` (accessibile dalla riga di comando o dalla dashboard Odoo.sh). I file di log vengono creati ogni giorno alle 5:00 AM (UTC).

Suggerimento

I due file più recenti, per il giorno corrente e quello precedente, sono denominati `odoo.log` e `odoo.log.1`.

I file di registro per le date più vecchie vengono nominate utilizzando le rispettive date e vengono compresse. Utilizza i comandi **grep** e **zgrep** (per quelle compresse) per cercare nei file,

Vedi anche

Per maggiori informazioni sui registri e su come accedervi tramite la dashboard Odoo.sh, consulta la documentazione [Registri Odoo.sh](../../../administration/odoo_sh/getting_started/branches.html#odoosh-logs).

Per maggiori informazioni su come accedere ai registri tramite la riga di comando, fai riferimento alla documentazione [accesso sviluppatore](../../../developer/reference/cli.html#reference-cmdline-server-logging).

## Informazioni per il supporto Odoo¶

Di seguito, un elenco di informazioni utili da includere se si contatta il [supporto Odoo](https://www.odoo.com/help):

  1. un’esportazione dell’intera e-mail dalla casella di posta. Di solito, si presentano nel formato file `.eml` o `.msg` e contengono le informazioni tecniche richieste per l’analisi. Il procedimento esatto per scaricare il file dipende al fornitore e-mail di terzi.

Vedi anche

     * [Gmail Help Center: tracciare un’e-mail con l’intestazione completa](https://support.google.com/mail/answer/29436)

     * [Supporto Microsoft: visualizza le intestazioni dei messaggi internet in Outlook](https://support.microsoft.com/en-us/office/view-internet-message-headers-in-outlook-cd039382-dc6e-4264-ac74-c048563d212c#tab=Web)

Quando si utilizza un software di posta elettronica locale (ad esempio, Thunderbird, Apple Mail, Outlook, ecc.) per sincronizzare le e-mail, di solito è possibile esportare le copie locali delle e-mail come file EML/MSG. Per ulteriori informazioni, consultare la documentazione del software utilizzato.

Suggerimento

Se possibile, il file EML/MSG deve essere basato sull’e-mail originale che è stata inviata e che non funziona o che causa problemi.

Per le **e-mail in entrata** : se possibile contattare il mittente dell’e-mail originale e richiederne una copia in EML/MSG. L’invio di una copia dell’e-mail originale (inoltrata) contiene solo informazioni parziali relative alla risoluzione dei problemi.

Per le **e-mail in uscita** : fornisci l’EML/MSG dell’e-mail o specifica il record del database interessato (ad esempio, il numero dell’ordine di vendita, il nome del contatto, il numero della fattura) e la data e l’ora di invio dell’e-mail (ad esempio, l’e-mail è stata inviata il 10 gennaio 2024 alle 11:45 ora dell’Europa centrale).

  2. Una spiegazione del flusso esatto che viene seguito per ricevere normalmente queste e-mail in Odoo. Cerca di rispondere alle seguenti domande:

     * Si tratta di un messaggio di notifica da una risposta ricevuta in Odoo?

     * Si tratta di un messaggio inviato dal database Odoo?

     * Stai usando un server e-mail in entrata o l’e-mail viene reindirizzata/inoltrata tramite un server e-mail personalizzato o un fornitore?

     * Hai un esempio di e-mail inoltrata correttamente?

     * Hai modificato le impostazioni relative alle e-mail di recente? Ha smesso di funzionare dopo aver apportato le modifiche?

  3. Una risposta alle seguenti domande:

     * Si tratta di un problema generico o di un caso d’uso specifico? Se specifico, di cosa si tratta?

     * Funziona come previsto? In caso l’e-mail venga inviata utilizzando Odoo, l’e-mail di rimbalzo dovrebbe raggiungere il database Odoo e mostrare la busta rossa.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/email_communication/faq.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../integrations.html "Integrazioni") |
  * [precedente](mailjet_api.html "API Mailjet") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Problemi e-mail comuni e soluzioni


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
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone