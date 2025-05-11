# Autenticazione a due fattori — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](access_rights.html "Diritti di accesso") |
  * [precedente](language.html "Modificare la lingua") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione a due fattori



# Autenticazione a due fattori¶

_L’autenticazione a due fattori (2FA)_ è un modo per migliorare la sicurezza e impedire alle persone non autorizzate di accedere agli account degli utenti.

In pratica, 2FA significa memorizzare un segreto all’interno di un _autenticatore_ , di solito su un telefono cellulare, e scambiare un codice dall’autenticatore quando si cerca di accedere.

Ciò significa che un utente non autorizzato dovrebbe indovinare la password dell’account _e_ avere accesso all’autenticatore, il che è più difficile.

## Requisiti¶

Importante

Questi elenchi sono solo esempi. **Non** si tratta di approvazioni di alcun software specifico.

Gli autenticatori basati sul telefono sono i più semplici e quelli più utilizzati. Alcuni esempi:

  * [Authy](https://authy.com/)

  * [FreeOTP](https://freeotp.github.io/)

  * [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=it&sjid=8327431702525404739-EU)

  * [LastPass Authenticator](https://lastpass.com/auth/)

  * [Microsoft Authenticator](https://www.microsoft.com/it-it/security/mobile-authenticator-app?cmp=h66ftb_42hbak)




I gestori delle password rappresentano un’altra opzione. Esempi comuni includono:

  * [1Password](https://support.1password.com/one-time-passwords/)

  * [Bitwarden](https://bitwarden.com/help/article/authenticator-keys/),




Nota

Utilizziamo Google Authenticator come esempio, in quanto è uno dei prodotti più comunemente utilizzati. **Non** si tratta di un’approvazione del prodotto.

## Configurazione autenticazione a due fattori¶

Dopo aver selezionato un autenticatore, accedi a Odoo, poi fai clic sull’avatar del profilo nell’angolo in alto a destra e seleziona Il mio profilo dal menu a tendina.

Fai clic sulla scheda Sicurezza account e poi fai scorrere il pulsante relativo alla Autenticazione a due fattori per _attivarla_.

Si aprirà una finestra pop-up Controllo sicurezza che richiede la conferma della password per continuare. Inserisci la password corretta, quindi fai clic su Conferma password. Apparirà la finestra pop-up Attivazione autenticazione a due fattori, con un QR code.

Utilizza l’applicazione di autenticazione che preferisci e scansiona il QR code quando viene mostrato.

Suggerimento

Se la scansione dello schermo non è possibile (ad esempio, l’impostazione viene completata sullo _stesso_ dispositivo dell’applicazione dell’autenticatore), fai clic sul link Non puoi scansionarlo? o copia il secret per impostare manualmente l’autenticatore.

In seguito, l’autenticatore dovrebbe mostrare un _codice di verifica_.

Inserisci il codice nel campo Codice di verifica, in seguito fai clic su Attiva.

## Accedere¶

Per confermare il completamento della configurazione della 2FA, esci da Odoo.

Nella pagina di accesso, inserisci il nome utente e la password, poi fai clic su Accedi. Nella pagina Autenticazione a due fattori, inserisci il codice fornito dall’autenticatore scelto nel campo Codice di autenticazione e fai clic su Accedi.

Pericolo

Se un utente perde l’accesso al proprio autenticatore, un amministratore **deve** disattivare la 2FA sull’account prima che l’utente possa accedere.

## Applicare l’autenticazione a due fattori¶

Per impostare l’utilizzo della 2FA per tutti gli utenti, apri la Dashboard principale di Odoo ‣ Applicazioni. Elimina il filtro App dalla barra Cerca… e poi cerca `2FA via e-mail`.

Fai clic sul pulsante Installa nella scheda kanban del modulo 2FA via e-mail.

Dopo aver completato l’installazione, apri l’app Impostazioni: Permessi. Spunta la casella Applicare l’autenticazione a due fattori. In seguito, usa i pulsanti per scegliere se applicare l’impostazione Solo ai dipendenti o a Tutti gli utenti.

Nota

Se scegli Tutti gli utenti, l’impostazione verrà applicata agli utenti del portale oltre che ai dipendenti.

Fai clic su Salva per salvare le modifiche.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/users/2fa.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](access_rights.html "Diritti di accesso") |
  * [precedente](language.html "Modificare la lingua") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione a due fattori


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
  *[QR]: Quick Response