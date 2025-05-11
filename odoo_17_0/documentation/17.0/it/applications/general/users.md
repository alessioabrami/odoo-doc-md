# Utenti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](users/language.html "Modificare la lingua") |
  * [precedente](apps_modules.html "App e Moduli") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Utenti



# Utenti¶

Odoo definisce un _utente_ come una persona che ha accesso a un database. Un amministratore può aggiungere tutti gli utenti di cui l’azienda ha bisogno e, per limitare il tipo di informazioni a cui ciascun utente può accedere, può applicare delle regole a ciascun utente. Gli utenti e i diritti di accesso possono essere aggiunti e modificati in qualsiasi momento.

Vedi anche

  * [Modificare la lingua](users/language.html)

  * [Diritti di accesso](users/access_rights.html)

  * [Modalità superutente](users/access_rights.html#access-rights-superuser)

  * [Creare e modificare gruppi](users/access_rights.html#access-rights-groups)




## Aggiungere utenti¶

Per aggiungere nuovi utenti apri l’app Impostazioni ‣ Sezione Utenti ‣ Gestisci utenti e fai clic su Nuovo.

Compila il modulo con tutte le informazioni richieste. Nella sezione [Diritti di accesso](users/access_rights.html), scegli il gruppo in ogni applicazione a cui l’utente può avere accesso.

L’elenco di applicazioni mostrate in base alle app installate sul database.

Dopo aver compilato tutti i campi necessari sulla pagina, Salva manualmente. All’utente verrà inviata automaticamente un’e-mail di invito utilizzando l’indirizzo inserito nel campo Indirizzo e-mail. L’utente deve fare clic sul link nell’e-mail per accettare l’invito e creare un accesso al database.

Avvertimento

Se l’azienda ha un piano di abbonamento mensile, il database si aggiorna automaticamente per riflettere gli utenti aggiunti. Se l’azienda ha un piano annuale o pluriennale, nel database appare un banner di scadenza. È possibile creare un preventivo di upselling facendo clic sul banner per aggiornare l’abbonamento. In alternativa, puoi `inviare un ticket di supporto <<https://www.odoo.com/help>> ` per risolvere il problema.

### Tipo di utente¶

Il Tipo di utente può essere selezionato dalla scheda Diritti di accesso sul modulo dell’utente, accessibile dall’app Impostazioni ‣ Sezione utenti ‣ Gestisci utenti.

Esistono tre tipi di utente: Utente interno, Portale e Pubblico.

Suggerimento

Gli utenti sono considerati utenti interni del database. Gli utenti del portale sono utenti esterni, che hanno accesso al portale del database solo per visualizzare i record. Consulta la documentazione [Accedere al portale](users/portal.html).

Gli utenti pubblici sono quelli che visitano i siti web dal frontend.

Le opzioni utente Portale e Pubblico **non** consentono all’amministratore di scegliere i diritti di accesso. Questi utenti hanno diritti di accesso specifici preimpostati (come regole di registrazione e menu riservati) e di solito non appartengono ai normali gruppi Odoo.

## Disattivare utenti¶

Per disattivare (ovvero archiviare) un utente, apri l’app Impostazioni ‣ Sezione utenti ‣ Gestisci utenti. In seguito, spunta la casella a sinistra dell’utente per disattivarlo.

Dopo aver selezionato l’utente da archiviare, fai clic sull’icona ⚙️ Azioni e seleziona Archivia dal menu a tendina. Successivamente, fai clic su OK dalla finestra pop-up di Conferma che appare.

Pericolo

**Non** disattivare mai l’utente principale/amministratore (admin). Le modifiche apportate agli utenti admin possono avere un impatto negativo sul database. Questo include _amministratore impotente_ , il che significa che nessun utente del database può apportare modifiche ai diritti di accesso. Per questo motivo, Odoo consiglia di contattare un Business Analyst o il nostro team di assistenza prima di apportare modifiche.

### Errore: troppi utenti¶

Se in un database Odoo ci sono più utenti di quelli previsti nell’abbonamento a Odoo Enterprise, verrà visualizzato il seguente messaggio.

Quando appare il messaggio, l’amministratore del database ha 30 giorni per agire prima che il database scada. Il conto alla rovescia viene aggiornato ogni giorno.

Per risolvere il problema puoi:

  * aggiungere più utenti all’abbonamento facendo clic sul link Aggiorna abbonamento visualizzato nel messaggio per la convalida del preventivo di upsell e paga per gli utenti aggiuntivi.

  * Disattivare gli utenti e rifiutare il preventivo di upsell.




Avvertimento

Se l’azienda ha un piano di abbonamento mensile, il database si aggiorna automaticamente per riflettere gli utenti aggiunti. Se l’azienda ha un piano annuale o pluriennale, nel database appare un banner di scadenza. È possibile creare un preventivo di upselling facendo clic sul banner per aggiornare l’abbonamento. In alternativa, gli utenti possono `inviare un ticket di supporto <<https://www.odoo.com/help>> ` per risolvere il problema.

Una volta che il database ha il numero corretto di utenti, il messaggio di scadenza scompare automaticamente dopo pochi giorni, al momento della verifica successiva.

## Gestione password¶

La gestione delle password è una parte importante per garantire agli utenti un accesso autonomo al database in qualsiasi momento. Odoo offre alcuni metodi diversi per reimpostare la password di un utente.

Suggerimento

Odoo ha un’impostazione per specificare la lunghezza di una password. È possibile accedere all’impostazione aprendo l’app Impostazioni ‣ Permessi e inserire la lunghezza desiderata nel campo Lunghezza minima della password. Per impostazione predefinitia, il valore è impostato su `8`.

### Reset della password¶

A volte gli utenti possono desiderare di reimpostare la propria password personale per maggiore sicurezza, in modo da essere gli unici ad avere accesso alla password. Odoo offre due opzioni per farlo: una avviata dall’utente per reimpostare la password e un’altra in cui l’amministratore attiva la reimpostazione.

#### Abilitare la reimpostazione della password dalla pagina di login¶

È possibile attivare/disattivare la reimpostazione della password direttamente dalla pagina di accesso. L’azione viene eseguita dal singolo utente e l’impostazione è attivata per impostazione predefinita.

Per modificare l’impostazione, apri l’app Impostazioni ‣ Permessi, attiva Reimposta password e poi fai clic su Salva.

Nella pagina di accesso, fai clic su Reimposta password per avviare il processo di reimpostazione della password e ricevere un token per il reset all’e-mail registrata.

#### Inviare istruzioni reimpostazione password¶

Apri l’app Impostazioni ‣ Utenti e aziende ‣ Utenti, seleziona l’utente dall’elenco e fai clic su Invia istruzioni ripristino password sul modulo dell’utente. Viene inviata automaticamente un’e-mail con le istruzioni per la reimpostazione della password.

Nota

Il pulsante Invia istruzioni ripristino password appare **solamente** se l’e-mail di invito di Odoo è stata già confermata dall’utente. Altrimenti, apparirà il pulsante Invia di nuovo l’e-mail di invito.

Questa e-mail contiene tutte le istruzioni necessarie per reimpostare la password, insieme a un link che reindirizza l’utente a una pagina di login di Odoo.

### Modificare password utente¶

Apri l’app Impostazioni ‣ Utenti e aziende ‣ Utenti e seleziona un utente per accedere al suo profilo. Fai clic sull’icona ⚙️ Azioni e seleziona Modifica password dal menu a tendina. Inserisci una nuova password nella colonna Nuova password della finestra pop-up Modifica password che appare e conferma la modifica facendo clic su Modifica password.

Nota

L’operazione modifica solamente la password degli utenti localmente e **non** impatta il loro account odoo.com.

Se la password di odoo.com deve essere cambiata, consulta la sezione inviare istruzioni per reimpostare la password. Le password di odoo.com consentono l’accesso alla pagina _I miei database_ e ad altre funzioni del portale.

Dopo aver fatto clic su Modifica password, la pagina viene reindirizzata a una pagina di accesso Odoo dove è possibile eseguire di nuovo l’accesso al database utilizzando la nuova password.

## Multi azienda¶

Il campo Multi azienda sul modulo di un utente permette all’amministratore di fornire accesso a più aziende. Per configurare un ambiente con aziende multiple per un utente, apri il profilo dell’utente desiderato andando su: Impostazioni ‣ sezione Utenti ‣ Gestisci utenti. In seguito, seleziona l’utente per aprirne il modulo e configura l’accesso multi azienda.

Sotto il campo guilabel:`Multi azienda` nella scheda Diritti di accesso, configura i campi chiamati Aziende consentite e Azienda predefinita.

Il campo Aziende consentite può contenere più aziende. Queste sono le aziende a cui l’utente può accedere e che può modificare, in base ai diritti di accesso impostati. Il campo Azienda predefinita è l’azienda a cui l’utente accede per default, ogni volta che esegue l’accesso. Questo campo può contenere **una** sola azienda.

Avvertimento

Se l’accesso a più aziende non è configurato correttamente potrebbe causare comportamenti anomali. Per questo motivo, solo gli utenti Odoo con esperienza dovrebbero apportare modifiche ai diritti di accesso di utenti di un database con più aziende. Per spiegazioni più tecniche, consulta la documentazione [Multi-company Guidelines](../../developer/howtos/company.html).

Vedi anche

[Aziende](companies.html)

  * [Modificare la lingua](users/language.html)
  * [Autenticazione a due fattori](users/2fa.html)
  * [Diritti di accesso](users/access_rights.html)
  * [Accedere al portale](users/portal.html)
  * [Autenticazione accesso Facebook](users/facebook.html)
  * [Autenticazione accesso Google](users/google.html)
  * [Autenticazione accesso Microsoft Azure](users/azure.html)
  * [Autenticazione LDAP](users/ldap.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/users.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](users/language.html "Modificare la lingua") |
  * [precedente](apps_modules.html "App e Moduli") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Utenti


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