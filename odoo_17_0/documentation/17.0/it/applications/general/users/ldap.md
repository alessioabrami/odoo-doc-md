# Autenticazione LDAP — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../companies.html "Aziende") |
  * [precedente](azure.html "Autenticazione accesso Microsoft Azure") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione LDAP



# Autenticazione LDAP¶

Per configurare l’autenticazione LDAP in Odoo:

  1. apri l’app Impostazioni, scorri in basso fino alla sezione Integrazioni e attiva Autenticazione LDAP

  2. fai clic su Salva, poi torna alla sezione Integrazioni e fai clic su Server LDAP

  3. nell’elenco Configura server LDAP, fai clic su Nuovo, quindi seleziona la società desiderata nell’elenco a tendina

  4. nella sezione Informazioni server, inserisci l’indirizzo IP del server e la porta nei campi Indirizzo server LDAP e Porta server LDAP

  5. attiva Usa TLS per richiedere la crittografia sicura TLS/SSL al momento della connessione al server LDAP assicurandosi che il server abbia lo StartTLS attivato

  6. Nella sezione Informazioni di accesso, inserisci l’ID e la password dell’account utilizzato per inviare una richiesta al server nei campi LDAP binddn e Password LDAP password. Se i campi non vengono riempiti, il server invierà la richiesta in maniera anonima

  7. Nella sezione Parametro processo, inserisci:

     * il nome del server LDAP nel campo LDAP base utilizzando il formato LDAP (ad es., `dc=example,dc=com`);

     * `uid=%s` nel campo LDAP filter.

  8. Nella sezione Informazioni utente:

     * abilita la funzionalità Crea utente per creare un profilo utente in Odoo al primo accesso tramite LDAP

     * seleziona il Modello utente da utilizzare per creare i nuovi profili utente. Se non viene selezionato alcun modello, viene utilizzato il profilo dell’amministratore




Nota

Quando si utilizza Microsoft Active Directory (AD) per l’autenticazione LDAP, se gli utenti riscontrano problemi di accesso nonostante l’uso di credenziali valide, crea un nuovo parametro di sistema per disabilitare il referral chasing nel client LDAP:

>   1. [attiva la modalità sviluppatore](../developer_mode.html#developer-mode)
> 
>   2. vai su Impostazioni ‣ Funzioni tecniche ‣ Parametri di sistema e fai clic su Nuovo.
> 
>   3. Compila i seguenti campi:
> 
>      * Chiave: `auth_ldap.disable_chase_ref`
> 
>      * Valore: `Vero`
> 
> 


[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/users/ldap.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../companies.html "Aziende") |
  * [precedente](azure.html "Autenticazione accesso Microsoft Azure") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Autenticazione LDAP


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
  *[LDAP]: Lightweight Directory Access Protocol