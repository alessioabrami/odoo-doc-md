# Collegare Gmail a Odoo utilizzando Google OAuth — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mailjet_api.html "API Mailjet") |
  * [precedente](azure_oauth.html "Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Collegare Gmail a Odoo utilizzando Google OAuth



# Collegare Gmail a Odoo utilizzando Google OAuth¶

Odoo è compatibile con l’OAuth di Google per Gmail. Per inviare e-mail sicure da un dominio personalizzato, tutto ciò di cui hai bisogno è configurare alcune impostazioni nella piattaforma _Workspace_ di Google e nel backend del database Odoo. La configurazione funziona sia con un indirizzo e-mail personale che un indirizzo creato da un dominio personalizzato.

Suggerimento

Per maggiori informazioni, consulta la `documentazione Google <https://support.google.com/cloud/answer/6158849>` sulla configurazione dell’OAuth.

Vedi anche

  * [Autenticazione accesso Google](../users/google.html)

  * [Google Calendar synchronization](../../productivity/calendar/google.html)




## Installazione in Google¶

### Creare un nuovo progetto¶

Per iniziare, apri la [Google API Console](https://console.developers.google.com/). Accedi con il tuo account _Google Workspace_ se ne hai uno, altrimenti accedi con l’account Gmail personale (che dovrebbe corrispondere all’indirizzo e-mail che desideri configurare in Odoo).

In seguito, fai clic su Crea progetto, a destra della schermata di consenso OAuth. Se hai già creato un progetto con lo stesso account, in alto a destra, sotto il menu a tendina Seleziona un progetto apparirà l’opzione Nuovo progetto.

Nella schermata Nuovo progetto, cambia il Nome progetto in `Odoo` e scegli la Posizione. Imposta la Posizione su _Organizzazione Google Workspace_. Se stai utilizzando un account Gmail personale, la Posizione può restare Nessuna organizzazione.

Fai clic su Crea per terminare questo step.

### Schermata di consenso OAuth¶

Se la pagina non reindirizza alle opzioni per il Tipo utente, fai clic su schermata di consenso OAuth nel menu a sinistra.

Tra le opzioni relative al Tipo di utente, seleziona il Tipo utente appropriato e poi fai di nuovo clic su Crea per accedere alla pagina Modifica registrazione app.

Avvertimento

Gli account Gmail _personali_ possono essere utilizzati solo con il tipo di utente **esterno** , il che significa che Google potrebbe richiedere l’approvazione o di aggiungere degli _Ambiti_. Tuttavia, l’uso di un account _Google WorkSpace_ consente di utilizzare il tipo di utente **interno**.

Si noti inoltre che quando la connessione API è in modalità di test _esterna_ , non è necessaria l’approvazione di Google. Il limite di utenti in questa modalità di test è impostato su 100 utenti.

### Modificare la registrazione dell’applicazione¶

In seguito, configureremo la registrazione dell’applicazione del progetto.

Nella schermata di consenso OAuth, nella sezione Informazioni app, scrivi `Odoo` nel campo Nome app. Seleziona l’indirizzo e-mail dell’organizzazione nel campo e-mail Supporto utente.

In seguito, accedi a Dominio app ‣ Domini autorizzati, fai clic su Aggiungi dominio e scrivi `odoo.com`.

Successivamente, nella sezione Informazioni di contatto sviluppatore, inserisci l’indirizzo e-mail dell’organizzazione. Google usa questo indirizzo e-mail per notificare l’organizzazione sulle modifiche apportate al progetto.

Fai clic sul pulsante Salva e continua. In seguito, salta la pagina Ambiti scorrendo verso il basso e facendo clic su Salva e continua.

Se continui in modalità di prova (esterno), aggiungi gli indirizzi e-mail configurati nella fase Utenti test, facendo clic su Aggiungi utenti e poi sul pulsante Salva e continua. Verrà visualizzato un riepilogo della registrazione dell’applicazione.

Infine, scorri fino in fondo e fai clic su Torna a dashboard per terminare la configurazione del progetto.

### Creare credenziali¶

Ora che il progetto è impostato, è necessario creare le credenziali, che comprendono lo _ID client_ e il _Client segreto_. Per prima cosa, fai clic su Credenziali nel menu della barra laterale sinistra.

Quindi, fai clic su Crea credenziali nel menu superiore e seleziona ID client OAuth dal menu a discesa.

  * Sotto Tipo di applicazione, seleziona Applicazione web dal menu a discesa.

  * Nel campo Nome scrivi `Odoo`.

  * Sotto l’etichetta URL reindirizzamento autorizzati, fai clic sul pulsante Aggiungi URL per poi inserire `https://yourdbname.odoo.com/google_gmail/confirm` nel campo URL 1. Assicurati di sostituire la parte _nomedb_ dell’URL con il nome corrente del database Odoo.

  * In seguito, fai clic su Crea per generare un ID client e un Client Segreto OAuth. Infine, copia ogni valore generato per utilizzarlo in seguito durante la configurazione in Odoo, quindi apri il database di Odoo.




## Installazione in Odoo¶

### Inserire le credenziali Google¶

Per prima cosa, apri il database Odoo e accedi al modulo Applicazioni. In seguito, elimina il filtro App dalla barra di ricerca e digita `Google`. Infine, installa il modulo chiamato Google Gmail.

Quindi, vai su Impostazioni ‣ Impostazioni generali e nella sezione Comunicazioni, assicurati che la casella di controllo per Server e-mail personalizzati o Server e-mail esterni sia selezionata. In questo modo si popola una nuova opzione per Credenziali Gmail o Usa un server Gmail. Quindi, copia e incolla i rispettivi valori nei campi ID client e Client segreto e Salva le impostazioni.

### Configurare server e-mail in uscita¶

Per configurare l’account Gmail esterno, torna all’inizio dell’impostazione Server e-mail personalizzati e fai clic sul collegamento Server e-mail in uscita.

Successivamente, fai clic su Nuovo o Crea per creare un nuovo server e-mail e compilare i campi Nome, Descrizione e il Nome utente dell’e-mail (se richiesto).

Poi fai clic su Autenticazione OAuth Gmail o Gmail (sotto la sezione Autenticazione con o Connessione). Infine, fai clic su Connetti il tuo account Gmail.

Si aprirà una nuova finestra Google per completare il processo di autorizzazione. Seleziona l’indirizzo e-mail appropriato che stai configurando in Odoo.

Se l’indirizzo e-mail è un account personale, viene visualizzato un passaggio in più, quindi fai clic su Continua per consentire la verifica e collegare l’account Gmail a Odoo.

In seguito, consenti a Odoo di accedere all’account Google facendo clic su Continua o Consenti. Dopodiché, la pagina torna al server e-mail in uscita appena configurato in Odoo. La configurazione carica automaticamente il token in Odoo e viene visualizzato in verde il tag Token Gmail valido.

Infine, prova la connessione. Dovrebbe apparire un messaggio di conferma. Ora è possibile inviare e-mail sicure dal database Odoo attraverso Google utilizzando l’autenticazione OAuth.

## FAQ Google OAuth¶

### Produzione vs test stato pubblicazione¶

Scegliendo Produzione come Stato di pubblicazione (invece di Prova) viene visualizzato il seguente messaggio di avviso:

Per correggere l’avviso, accedi a [Google API Platform](https://console.cloud.google.com/apis/credentials/consent). Se lo Stato di pubblicazione è In produzione, fai clic su Torna al test per correggere il problema.

### Nessun utente di prova aggiunto¶

Se non vengono aggiunti utenti di prova alla schermata di consenso OAuth, verrà visualizzato un errore 403 accesso negato.

Per correggere l’errore, torna alla schermata di consenso OAuth sotto API e servizi e aggiungi uno o più utenti di prova all’applicazione. Aggiungi l’e-mail che stai configurando in Odoo.

### Modulo Gmail non aggiornato¶

Se il modulo _Google Gmail_ di Odoo non è stato aggiornato all’ultima versione, viene visualizzato un messaggio di errore Forbidden.

Per correggere questo errore, accedi al modulo Applicazioni e cancella i termini di ricerca. Quindi, cerca `Gmail` o `Google` e aggiorna il modulo Google Gmail. Infine, fai clic sui tre punti in alto a destra del modulo e seleziona Aggiorna.

### Tipo di applicazione¶

Al momento della creazione delle credenziali (_ID client_ e _Secret client_), se viene selezionato App desktop per il Tipo di applicazione, apparirà un Errore di autorizzazione.

Per correggere questo errore, elimina le credenziali che sono già state create e creane di nuove, selezionando Applicazione web per il Tipo di applicazione. In seguito, nella sezione URI reindirizzamento autorizzati, fai clic su AGGIUNGI URI e scrivi: `https://yourdbname.odoo.com/google_gmail/confirm` nel campo, assicurandoti di sostituire _yourdbname_ nell’URL con il nome del database Odoo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/email_communication/google_oauth.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mailjet_api.html "API Mailjet") |
  * [precedente](azure_oauth.html "Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Collegare Gmail a Odoo utilizzando Google OAuth


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
  *[DKIM]: DomainKeys Identified Mail) da inserire nel provider :abbr:`DNS (Domain Name System
  *[DMARC]: Domain-based Message Authentication, Reporting, and Conformance