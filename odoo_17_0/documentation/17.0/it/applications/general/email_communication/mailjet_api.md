# API Mailjet — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](faq.html "Problemi e-mail comuni e soluzioni") |
  * [precedente](google_oauth.html "Collegare Gmail a Odoo utilizzando Google OAuth") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * API Mailjet



# API Mailjet¶

Odoo è compatibile con la API di Mailjet per le e-mail di massa. Configura un server per e-mail di massa dedicato tramite Mailjet, configurando le impostazioni nell’account Mailjet e nel database di Odoo. In alcuni casi, è necessario configurare anche le impostazioni del DNS del dominio personalizzato.

## Configurazione in Mailjet¶

### Creare credenziali API¶

Per iniziare, accedi alla pagina [Informazioni account Mailjet](https://app.mailjet.com/account) page. In seguito, apri la sezione Mittenti e domini e fai clic su Impostazioni SMTP e SEND API.

Successivamente, copia le impostazioni di configurazione dello SMTP negli appunti. È possibile trovarle nella sezione Configurazione (solo SMTP). Le impostazioni di configurazione dello SMTP includono l’indirizzo del server, le opzioni di sicurezza necessarie (usa SSL/TLS) e il numero di port. Le impostazioni sono necessarie per la configurazione di Mailjet in Odoo, spiegata nell”ultima sezione.

Vedi anche

[Mailjet: come posso configurare i miei parametri SMTP?](https://documentation.mailjet.com/hc/articles/360043229473)

Importante

Odoo [blocca il port 25](email_servers_outbound.html#email-outbound-port-restriction) sui database Odoo online e Odoo.sh.

Quindi, faI clic sul pulsante Recupera credenziali API per recuperare le credenziali API di Mailjet.

Successivamente, fai clic sull’icona a forma di occhio per svelare la chiave API. Copia la chiave in una nota, perché servirà come nome utente nella configurazione Odoo. Poi fai clic sul pulsante Genera chiave privata per generare la chiave privata. Copia la chiave in una nota perché sarà la password nella configurazione Odoo.

### Aggiungere indirizzi mittente verificati¶

Il passo successivo è aggiungere un indirizzo mittente o un dominio alle impostazioni dell’account Mailjet così l’indirizzo e-mail o il dominio verrà approvato per inviare e-mail utilizzando server di Mailjet. Per prima cosa, accedi alla pagina [Informazioni account Mailjet](https://app.mailjet.com/account). In seguito, fai clic sul link Aggiungi un dominio o indirizzo mittente nella sezione Mittenti e domini.

Stabilisci se è necessario aggiungere alle impostazioni di Mailjet l’indirizzo e-mail di un mittente o l’intero dominio. Può essere più facile configurare l’intero dominio se l’accesso DNS è disponibile. Passa alla sezione Aggiungi un dominio per i passaggi relativi all’aggiunta del dominio.

Nota

È necessario configurare tutti gli indirizzi e-mail degli utenti del database di Odoo che inviano e-mail utilizzando i server di Mailjet, oppure è possibile configurare i domini degli indirizzi e-mail degli utenti.

Per impostazione predefinita, l’indirizzo e-mail originariamente impostato nell’account Mailjet viene aggiunto come mittente attendibile. Per aggiungere un altro indirizzo e-mail, fai clic sul pulsante Aggiungi un indirizzo mittente. Quindi, aggiungi l’indirizzo e-mail configurato per l’invio dal dominio personalizzato.

Almeno i seguenti indirizzi e-mail devono essere impostati nel provider e verificati in Mailjet:

  * notifications@yourdomain.com

  * bounce@yourdomain.com

  * catchall@yourdomain.com




Nota

Sostituisci `yourdomain` con il dominio personalizzato del database Odoo. Se non ce n’è uno, utilizza il parametro di sistema mail.catchall.domain.

Successivamente, compila il modulo Informazioni e-mail, assicurandoti di selezionare il tipo di e-mail appropriato: e-mail transazionale o e-mail di massa. Dopo aver completato il modulo, viene inviata un’e-mail di attivazione all’indirizzo e-mail e il mittente attendibile può essere attivato.

È consigliato configurare le impostazioni SPF/DKIM/DMARC sul dominio del mittente.

Vedi anche

[Documentazione Mailjet’s SPF/DKIM/DMARC](https://documentation.mailjet.com/hc/articles/360042412734-Authenticating-Domains-with-SPF-DKIM)

Importante

Se il database non utilizza un dominio personalizzato, per verificare l’indirizzo del mittente è necessario impostare un alias temporaneo (dei tre indirizzi e-mail sopra menzionati) in Odoo CRM per creare un lead. Quindi, il database è in grado di ricevere l’e-mail di verifica e di verificare gli account.

### Aggiungere un dominio¶

Aggiungendo un intero dominio all’account Mailjet, tutti gli indirizzi del mittente correlati a quel dominio vengono convalidati automaticamente per l’invio di e-mail utilizzando i server Mailjet. Per prima cosa, accedi alla pagina [Informazioni account Mailjet](https://app.mailjet.com/account). In seguito, fai clic sul link Aggiungi indirizzo o dominio mittente nella sezione Mittenti e domini. In seguito, fai clic su:guilabel:`Aggiungi dominio` per aggiungere il dominio personalizzato.

Nota

È necessario aggiungere il dominio all’account Mailjet e poi convalidarlo attraverso il DNS.

Successivamente, completa la pagina Aggiungi un nuovo dominio su Mailjet e fai clic su Continua.

Dopo aver aggiunto il dominio, verrà visualizzata una pagina di convalida. A meno che il database di Odoo non sia on-premise (in tal caso, scegli Opzione 1), scegli Opzione 2: Crea un record DNS. Copia le informazioni del record TXT in un blocco note e poi naviga verso il provider DNS del dominio per completare la convalida.

#### Configurazione nel DNS del dominio¶

Dopo aver ottenuto le informazioni sul record TXT dall’account Mailjet, aggiungi un record TXT al DNS del dominio. Questo processo varia a seconda del provider DNS. Consulta il provider per i processi di configurazione specifici. Le informazioni del record TXT sono costituite da Host e Valore. Incollali nei campi corrispondenti del record TXT.

#### Tornare alle informazioni dell’account Mailjet¶

Dopo aver aggiunto il record TXT al DNS del dominio, torna all’account Mailjet. Quindi, vai su Informazioni account ‣ Aggiungi un dominio o indirizzo mittente, fai clic sull’icona dell’ingranaggio accanto a Dominio e seleziona Convalida.

Quest’azione può essere eseguita anche andando alla pagina [Domini e indirizzi mittente](https://app.mailjet.com/account/mittente) nelle informazioni sull’account Mailjet e cliccando su Gestione.

Quindi, fai clic su Controlla ora per convalidare il record TXT aggiunto al dominio. Se il dominio è configurato correttamente, apparirà una schermata di successo.

Dopo aver configurato con successo il dominio, è disponibile l’opzione Autentica questo dominio (SPF/DKIM). Questo pulsante popola i record SPF e DKIM.

Vedi anche

[Documentazione Mailjet’s SPF/DKIM/DMARC](https://documentation.mailjet.com/hc/articles/360042412734-Authenticating-Domains-with-SPF-DKIM)

## Configurazione in Odoo¶

Per completare la configurazione, apri il database Odoo e accedi alle Impostazioni. Attiva la modalità sviluppatore, vai su Menu tecnico ‣ E-mail ‣ Server e-mail in uscita. In seguito, crea una nuova configurazione per il server in uscita facendo clic sul pulsante Crea.

Successivamente, aggiungi il `server SMTP` (in-v3.mailjet.com), il `numero di port` (587 o 465) e il `Security (SSL/TLS)` che è stato copiato precedentemente dall’account Mailjet. Possono anche essere trovati [qui](https://app.mailjet.com/account/setup). È consigliato utilizzare lo SSL/TLS anche se Mailjet potrebbe non richiederlo.

Per il campo Nome utente, inserisci la CHIAVE API. Per la Password, inserisci la CHIAVE PRIVATA copiata dall’account Mailjet in precedenza. È possibile accedere alle impostazioni andando su Mailjet ‣ Impostazioni account ‣ Impostazioni SMTP e SEND.

In seguito, se il server Mailjet viene utilizzato per inviare e-mail di massa, il valore Priorità deve essere maggiore di qualsiasi server e-mail di transazione. Infine, salva le impostazioni e Prova la connessione.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/email_communication/mailjet_api.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](faq.html "Problemi e-mail comuni e soluzioni") |
  * [precedente](google_oauth.html "Collegare Gmail a Odoo utilizzando Google OAuth") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * API Mailjet


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