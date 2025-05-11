# Autenticazione accesso Facebook — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Autenticazione accesso Google") |
  * [precedente](portal.html "Accedere al portale") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Facebook



# Autenticazione accesso Facebook¶

La funzione di accesso OAuth di _Facebook_ consente agli utenti di Odoo di accedere al proprio database con il proprio account Facebook.

Pericolo

I database ospitati su odoo.com **non** dovrebbero utilizzare il login OAuth per il proprietario o l’amministratore del database, in quanto questo scollegherebbe il database dal loro account odoo.com. Se l’OAuth è impostato per quell’utente, il database non potrà più essere duplicato, rinominato o gestito in altro modo dal portale odoo.com.

## Configurare Meta for Developers¶

Vai su [Meta for Developers](https://developers.facebook.com/) e accedi. Fai clic su Le mie app. Nella pagina Applicazioni, fai clic su Crea app.

Sulla pagina Casi d’uso, seleziona Autenticati e richiedi dati dagli utenti con Facebook login e poi fai clic su Avanti.

Nel campo Aggiungi un nome per l’app, inserisci `Odoo Login OAuth` o un titolo simile.

Nota

L’app e-mail contatto è automaticamente impostato sull’indirizzo e-mail associato all’account Meta. Se questo indirizzo di posta elettronica non viene monitorato regolarmente, può essere opportuno utilizzare un altro indirizzo di posta elettronica.

Fai clic su Avanti. Rivedi i Requisiti di pubblicazione, i Termini della piattaforma Meta e le Politiche degli sviluppatori. In seguito, fai clic su Crea app.

Importante

Facendo clic su Crea app ti potrebbe essere richiesta la password.

### Personalizzare l’app¶

Dopo aver creato la nuova app, apparirà la pagina Dashboard con un elenco di step da completare prima di poter pubblicare l’app. Da qui, fai clic su Personalizza aggiungendo un pulsante di accesso a Facebook.

Sulla pagina Personalizza, fai clic su Impostazioni.

Nel campo URL reindirizzamento OAuth valido, inserisci `https://<odoo base url>/auth_oauth/signin` e sostituisci `<odoo base url>` con l’URL del database applicabile.

Example

Se il database ha l’URL `https://example.odoo.com`, l’URL `https://example.odoo.com/auth_oauth/signin` deve essere inserito nel campo URL reindirizzamento OAuth valido.

Fai clic su Salva modifiche quando hai terminato.

### Configurare le impostazioni¶

All’estremità sinistra della pagina, fai clic su Impostazioni app ‣ Base. La pagina contiene impostazioni aggiuntive richieste prima che l’app possa essere inviata per l’approvazione.

Nel campo URL politica privacy, inserisci `https://www.odoo.com/privacy`.

Nota

<https://www.odoo.com/privacy> è la politica privacy predefinita per i database ospitati su odoo.com.

Fai clic sul campo Icona app per aprire una finestra per caricare un file. Da qui, seleziona e carica un’icona per l’app.

Nel campo Eliminazione dati utente, inserisci `https://www.odoo.com/documentation/17.0/administration/odoo_accounts.html`.

Nota

La documentazione fornisce istruzioni su come eliminare il proprio account Odoo.

Infine, fai clic sul campo Categoria e seleziona Business e pagine dal menu a tendina.

Fai clic su Salva modifiche.

### Acquisire ID app¶

Dopo aver creato e approvato l’app, seleziona e copia l’ID app. Incolla l’informazione negli appunti o in un file, in quanto sarà necessaria nell’ultimo step per completare la configurazione.

### Pubblicata¶

Nella parte sinistra della pagina, fai clic su Pubblica. In base allo staso dell’account Facebook collegato, potrebbero essere richiesti step aggiuntivi per la verifica e il test, entrambi elencati in questa pagina.

Dopo aver revisionato l’informazione, fai clic su Pubblica.

Vedi anche

Informazioni aggiuntive sullo sviluppo di app Meta, compresi ulteriori dettagli su creazione, test e casi d’uso, sono consultabili [alla pagina](https://developers.facebook.com/docs/development).

## Configurare Odoo¶

Per prima cosa, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode-activation).

Accedi all’app Impostazioni e scorri in basso verso la sezione Integrazione. , tick the checkbox labeled, OAuth Authentication. Click Save.

In seguito, accedi al database una volta che appare la schermata di accesso.

Dopo aver eseguito l’accesso con successo, accedi all’app Impostazioni ‣ Utenti e aziende ‣ Fornitori OAuth. Fai clic su Facebook Graph.

Nel campo ID client, inserisci l’ID app dalla sezione precedente e poi spunta la casella Consentito.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/users/facebook.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Autenticazione accesso Google") |
  * [precedente](portal.html "Accedere al portale") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione accesso Facebook


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
  *[2FA]: Autenticazione a due fattori