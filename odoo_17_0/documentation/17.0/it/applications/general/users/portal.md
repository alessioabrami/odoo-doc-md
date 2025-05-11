# Accedere al portale — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](facebook.html "Autenticazione accesso Facebook") |
  * [precedente](access_rights.html "Diritti di accesso") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Accedere al portale



# Accedere al portale¶

L’accesso al portale viene concesso agli utenti che devono poter visualizzare determinati documenti o informazioni all’interno di un database Odoo.

Alcuni casi d’uso comuni per fornire l’accesso al portale includono la possibilità per i clienti di leggere/visualizzare uno o tutti i seguenti elementi in Odoo:

  * lead/opportunità

  * preventivi/ordini di vendita

  * ordini di acquisto

  * fatture cliente e fornitore

  * progetti

  * lavori

  * fogli ore

  * ticket

  * firme

  * abbonamenti




Nota

Gli utenti del portale hanno solo accesso in lettura/visione e non possono modificare i documenti del database.

## Fornire ai clienti l’accesso al portale¶

Dalla dashboard principale di Odoo, seleziona l’applicazione Contatti. Se il contatto non è ancora stato creato nel database, fai clic sul pulsante Crea, inserisci i dettagli del contatto e poi fai clic su Salva. Altrimenti, scegli un contatto esistente e fai clic sul menu a discesa Azione situato in alto al centro dell’interfaccia.

In seguito, seleziona Concedi accesso al portale. Apparirà una finestra pop-up che elenca tre campi:

  * Contatto: il nome del contatto registrato nel database Odoo

  * E-mail: l’indirizzo e-mail del contatto utilizzato per accedere al portale

  * Nel portale: se l’utente ha accesso o meno al portale




Per fornire l’accesso al portale, inserisci l’indirizzo e-mail del contatto che verrà utilizzato per l’accesso. In seguito, spunta la casella nella colonna Nel portale. In via facoltativa, aggiungi del testo al messaggio di invito che riceverà il contatto. Poi fai clic su Applica per terminare.

All’indirizzo e-mail specificato verrà inviata un’e-mail che indica che il contatto è ora un utente del portale per quel database Odoo.

Suggerimento

Per concedere l’accesso al portale a più utenti in una sola volta, accedi a un contatto dell’azienda, poi fai clic su Azioni ‣ Concedi accesso al portale per visualizzare un elenco di tutti i contatti legati all’azienda. Spunta la casella nella colonna Nel portale per tutti i contatti che hanno bisogno dell’accesso e poi fai clic su Applica.

Nota

È possibile revocare l’accesso in qualsiasi momento accedendo al contatto per poi fare clic su Azioni ‣ Concedi accesso al portale e poi deseleziona la casella nella colonna Nel portale e fai clic su Applica.

## Modificare il nome utente nel portale¶

Può capitare che un utente del portale voglia modificare il proprio accesso. Quest’operazione può essere eseguita da qualsiasi utente del database con diritti di accesso come amministratore. La seguente procedura illustra i passaggi necessari per modificare il login dell’utente del portale.

Vedi anche

[Consulta la documentazione sulla configurazione dei diritti di accesso](access_rights.html).

Per prima cosa, apri l’app Impostazioni ‣ Utenti. In seguito, in Filtri, seleziona Utenti portale oppure Aggiungi filtro personalizzato e configura le seguenti impostazioni Gruppi > contiene > `portale`. Dopo aver effettuato la selezione, cerca (e apri) l’utente del portale da modificare.

Successivamente, fai clic su Modifica (se necessario), poi sul campo Indirizzo e-mail e apporta tutte le modifiche necessarie al campo. Il campo Indirizzo e-mail viene utilizzato per accedere al portale Odoo.

Nota

La modifica del campo Indirizzo e-mail (o del login) comporta solo la modifica del _nome utente_ sul login del cliente al portale.

Per modificare l’e-mail del contatto, la modifica deve avvenire sul modello di contatto nell’applicazione _Contatti_. In alternativa, il cliente può modificare l’e-mail direttamente dal portale, ma il login non può essere modificato. Vedi la sezione sulla modifica delle informazioni del cliente.

## Modificare il portale clienti¶

Può capitare che il cliente desideri modificare le informazioni di contatto, la password/sicurezza o le informazioni di pagamento collegate all’account del portale. Quest’operazione può essere eseguita dal cliente dal proprio portale. Di seguito viene illustrata la procedura di modifica delle informazioni di contatto da parte del cliente.

### Modificare le informazioni del cliente¶

Per prima cosa, è necessario inserire il nome utente e la password (login) nella pagina di accesso del database per accedere all’account utente del portale. Una volta effettuato l’accesso, apparirà una dashboard. I documenti del portale delle varie applicazioni Odoo installate appariranno con il numero corrispondente.

Vedi anche

Documentazione sull’accesso al portale.

Successivamente, spostati nell’angolo superiore destro del portale e fai clic sul pulsante Modifica, accanto alla sezione Dettagli. Modifica le informazioni pertinenti e fai clic su Conferma.

### Modifica password¶

Per prima cosa, è necessario inserire il nome utente e la password (login) nella pagina di accesso del database per accedere all’account utente del portale. Una volta effettuato l’accesso, apparirà una dashboard.

Se il cliente vuole modificare la propria password per l’accesso al portale, fai clic sul link Modifica impostazioni sicurezza, nella sezione Sicurezza account. Successivamente, apporta le modifiche necessarie digitando la Password attuale, la Nuova password e verificala. Come ultima cosa, fai clic su Modifica password per completare la modifica.

Nota

Se un cliente vuole modificare il login, come descritto precedentemente, contatta il punto di contatto Odoo per il database. Consulta la documentazione sulla modifica del nome utente nel portale.

Nota

Le password per gli utenti del portale e di Odoo.com restano separate anche se viene utilizzato lo stesso indirizzo e-mail.

### Aggiungere l’autenticazione a due fattori¶

Per prima cosa, è necessario inserire il nome utente e la password (login) nella pagina di accesso del database per accedere all’account utente del portale. Una volta effettuato l’accesso, apparirà una dashboard.

Se il cliente vuole attivare l’autenticazione a due fattori (2FA) per l’accesso al portale, fai clic sul link Modifica impostazioni sicurezza sotto la sezione Sicurezza account.

Fai clic su Abilita autenticazione a due fattori per abilitare la 2FA. Conferma la password attuale per il portale nel campo Password. Successivamente, fai clic su Conferma password e attiva la 2FA in un’app 2FA (Google Authenticator, Authy, etc.), scansionando il codice QR o inserendo un Codice di verifica.

Infine, fai clic su Abilita autenticazione due fattori per completare la configurazione.

### Modificare le informazioni di pagamento¶

Per prima cosa, è necessario inserire il nome utente e la password (login) nella pagina di accesso del database per accedere all’account utente del portale. Una volta effettuato l’accesso, apparirà una dashboard.

Se il cliente desidera gestire le opzioni di pagamento, vai alla sezione Gestione dei metodi di pagamento nel menu a destra. In seguito, aggiungi le nuove informazioni di pagamento e seleziona Aggiungi nuova carta.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/users/portal.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](facebook.html "Autenticazione accesso Facebook") |
  * [precedente](access_rights.html "Diritti di accesso") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Accedere al portale


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
  *[API]: application programming interfaces
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
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Punto vendita
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication