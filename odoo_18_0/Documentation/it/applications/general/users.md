# Utenti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](users/language.html "Modificare la lingua") |
  * [precedente](apps_modules.html "App e Moduli") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
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

After filling out all the necessary fields on the page, __(Save manually). An invitation email is automatically sent to the user, using the email in the Email Address field. The user must click on the link included in the email to accept the invitation, and to create a database login. email is automatically sent to the user, using the email in the Email Address field. The user must click on the link included in the email to accept the invitation, and to create a database login.

Avvertimento

Se l’azienda ha un piano di abbonamento mensile, il database si aggiorna automaticamente per riflettere gli utenti aggiunti. Se l’azienda ha un piano annuale o pluriennale, nel database appare un banner di scadenza. È possibile creare un preventivo di upselling facendo clic sul banner per aggiornare l’abbonamento. In alternativa, puoi `inviare un ticket di supporto <<https://www.odoo.com/help>> ` per risolvere il problema.

### Tipo di utente¶

User Type can be chosen on the Manage Users page by clicking on the search bar, and then [setting a filter](../essentials/search.html#search-preconfigured-filters) for either Internal User or Portal User.

Odoo databases have three types of users: Internal User, Portal, and Public. Users are considered _internal database_ users. Portal users are _external users_ , who only have access to the database portal to view records. Public users are those visiting websites, via the website’s frontend. See the documentation on [Accedere al portale](users/portal.html).

The Portal user option does **not** allow the administrator to choose access rights. These users have specific access rights pre-set (such as, record rules and restricted menus), and usually do not belong to the usual Odoo groups.

## Disattivare utenti¶

To deactivate (i.e. archive) a user, navigate to Settings app ‣ Users section ‣ Manage Users. Then, tick the checkbox to the left of the users to be deactivated.

After selecting the appropriate user to be archived, click the __(Actions) icon, and select Archive from the resulting drop-down menu. Then, click OK from the Confirmation pop-up window that appears.

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

#### Abilitare la reimpostazione della password dalla pagina di accesso¶

È possibile attivare/disattivare la reimpostazione della password direttamente dalla pagina di accesso. L’azione viene eseguita dal singolo utente e l’impostazione è attivata per impostazione predefinita.

Per modificare l’impostazione, apri l’app Impostazioni ‣ Permessi, attiva Reimposta password e poi fai clic su Salva.

Nella pagina di accesso, fai clic su Reimposta password per avviare il processo di reimpostazione della password e ricevere un token per il reset all’e-mail registrata.

#### Inviare istruzioni reimpostazione password¶

Apri l’app Impostazioni ‣ Utenti e aziende ‣ Utenti, seleziona l’utente dall’elenco e fai clic su Invia istruzioni ripristino password sul modulo dell’utente. Viene inviata automaticamente un’e-mail con le istruzioni per la reimpostazione della password.

Nota

Il pulsante Invia istruzioni ripristino password appare **solamente** se l’e-mail di invito di Odoo è stata già confermata dall’utente. Altrimenti, apparirà il pulsante Invia di nuovo l’e-mail di invito.

Questa e-mail contiene tutte le istruzioni necessarie per reimpostare la password, insieme a un link che reindirizza l’utente a una pagina di login di Odoo.

### Modificare password utente¶

Go to Settings app ‣ Users & Companies ‣ Users, and select a user to access its form. Click on the __(Actions) icon, and select Change Password from the resulting drop-down menu. Enter a new password in the New Password column of the Change Password pop-up window that appears, and confirm the change by clicking Change Password.

Nota

This operation only modifies the password of the users locally, and does **not** affect their Odoo account.

If the Odoo password needs to be changed, use the send the password reset. Odoo.com passwords grant access to the _My Databases_ page, and other portal features.

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



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/general/users.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](users/language.html "Modificare la lingua") |
  * [precedente](apps_modules.html "App e Moduli") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
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
  *[FBM]: Fulfilled by Merchant
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
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID