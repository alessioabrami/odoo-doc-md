# Gestire messaggi in uscita — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_domain.html "Configurare record DNS per inviare e-mail in Odoo") |
  * [precedente](email_servers_inbound.html "Gestire messaggi in entrata") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Gestire messaggi in uscita



# Gestire messaggi in uscita¶

## Inviare e-mail con la configurazione predefinita di Odoo¶

Su **Odoo online** e **Odoo.sh** , inviare e ricevere e-mail è un gioco da ragazzi perché non è richiesta nessuna configurazione.

Quando viene creato un database, il sottodominio `company-name.odoo.com` viene utilizzato per inviare e ricevere e-mail. La consegna è ottimizzata per questo sottodominio, poiché utilizza la configurazione DNS di Odoo.

Example

Se il sottodominio del database corrisponde a `company-name.odoo.com` e tutte le impostazioni relative alle e-mail sono quelle predefinite, tutte le e-mail verranno inviate da `notifications@company-name.odoo.com`.

This configuration is handled by the system parameter `mail.default.from_filter`. In case where the sender’s domain do not match the value of this parameter, the notification address is used instead. Multiple values can be defined in this system parameter: comma-separated, domains or full email addresses are all allowed. Once an outgoing mail server is configured, the system parameter is no longer considered and the value used is the FROM filtering of the mail server.

Le e-mail vengono inviate con `catchall@company-name.odoo.com` che corrisponde all’indirizzo _rispondi a_. Inoltre, gli errori di consegna vengono inviati a `bounce@company-name.odoo.com`.

Nota

Gli indirizzi catchall, bounce e di notifica non funzionano come gli altri alias. Non hanno la vocazione di creare record in un database. Le e-mail inviate a un alias vengono instradate automaticamente e rispondono a un record esistente e collegato o ne creano uno nuovo nel database.

## Utilizzare un dominio personalizzato per inviare e-mail¶

Il database può essere configurato per utilizzare un dominio personalizzato e in questo caso tutti gli indirizzi e-mail predefiniti vengono costruiti utilizzando il dominio personalizzato. Se il dominio personalizzato è `company-name.com`, l’indirizzo del mittente sarà `notifications@company-name.com`, l’indirizzo _rispondi a_ `catchall@company-name.com` e l’indirizzo di _rimbalzo_ `bounce@company-name.com`. Il dominio personalizzato può essere utilizzato quando si inviano e-mail sia con i server e-mail di Odoo che con un server esterno.

Questa sezione presuppone la proprietà di un dominio personalizzato. In caso contrario, il dominio personalizzato deve essere acquistato da una società di registrazione di domini come GoDaddy, Namecheap o qualsiasi altro fornitore alternativo.

Vedi anche

[`Magic Sheet - Email domain configuration PDF`](../../../_downloads/50b9652590b53fd589663fe0a2f281b8/magic-sheet-email-domain.pdf)

### Utilizzare un dominio personalizzato con server e-mail di Odoo¶

Su **Odoo online** od **Odoo.sh** , alcune configurazioni sono obbligatorie nel DNS del dominio personalizzato al fine di garantire la consegna.

Avvertimento

La gran parte della configurazione verrà effettuata da parte del fornitore del dominio e potrebbe richiedere alcune impostazioni anche sul server e-mail. **Sono richieste alcune competenze tecniche**.

Il primo passo da fare è configurare lo [SPF](email_domain.html#email-domain-spf) e il [DKIM](email_domain.html#email-domain-dkim) per essere conforme al server e-mail di Odoo.

In seguito, Il modulo personalizzato deve essere impostato come dominio alias di un’azienda. Seleziona l’azienda, apri le Impostazioni e aggiungi il dominio personalizzato nel campo Dominio alias.

Dopo aver aggiunto il dominio alias, fai clic sull’icona __( link interno) per assegnare più aziende al dominio personalizzato se necessario. Attiva la modalità sviluppatore per modificare gli alias predefiniti se desiderato:

  * Alias rimbalzo: la casella di posta utilizzata per trovare errori di consegna e popolare la [busta rossa](faq.html#email-issues-outgoing-delivery-failure) sul messaggio corrispondente;

  * Alias catchall: la casella di posta predefinita utilizzata per centralizzare tutte le risposte;

  * Predefinito dall’alias: l’indirizzo predefinito del mittente.




Nota

Al momento della creazione del primo dominio alias, tutte le aziende lo utilizzeranno. Se crei una nuova azienda, il dominio alias impostato automaticamente è quello con la priorità più bassa (come mostrato nell’elenco dei domini alias nella modalità sviluppatore).

Tutti gli alias e-mail (ad es., relativi ai team CRM o Helpdesk) devono avere la casella di posta corrispondente nel server e-mail del dominio personalizzato.

Per ricevere e-mail nel database Odoo all’interno del chatter corrispondente (CRM, fatture, ordini di vendita, ecc.), bisogna utilizzare uno di questi tre metodi:

  * [Reindirizzamento/inoltro](email_servers_inbound.html#email-inbound-custom-domain-redirections)

  * [Server e-mail in entrata](email_servers_inbound.html#email-inbound-custom-domain-incoming-server)

  * [Record MX](email_servers_inbound.html#email-inbound-custom-domain-mx) (richiede conoscenze tecniche avanzate).




L’utilizzo di un dominio personalizzato implica l’utilizzo di parti locali specifiche da parte di Odoo per inviare e-mail.

### Inviare e-mail con un server SMTP esterno¶

Nota

Se utilizzi il tuo server e-mail in uscita, quest’ultimo deve essere abbinato al tuo dominio in quanto non è possibile aggiornare il DNS di un sottodominio Odoo.

Per aggiungere un server SMTP esterno in Odoo, apri le Impostazioni e attiva l’opzione Usa server e-mail personalizzati che si trova nella sezione E-mail. In seguito, fai clic su Salva nella parte alta della pagina per salvare le modifiche.

Tornando alla sezione E-mail, fai clic su Server e-mail in uscita, in seguito `Nuovo` per creare un record per il server stesso. La maggior parte dei campi sono i parametri comuni utilizzati per configurare una connessione a un server SMTP. Utilizza i valori forniti dal fornitore di posta.

Una volta completata la procedura, fai clic su Prova connessione. Nota che una connessione di prova funzionante non conferma il fatto che l’e-mail verrà inviata in quanto potrebbero essere presenti alcune restrizioni lato fornitore quindi consigliamo di consultarne la documentazione.

#### Valori della parte locale¶

Di seguito vengono elencati i vari valori della parte locale che possono essere utilizzati da Odoo per inviare e-mail. Potrebbe essere necessario inserirli nella whitelist del tuo server e-mail:

  * l’alias di rimbalzo del dominio alias (valore predefinito = `bounce`)

  * il dominio alias Predefinito da ( valore predefinito = `notifications`)

  * l’indirizzo admin predefinito `admin@company-name.odoo.com` (o il nuovo valore se modificato)

  * l’indirizzo Odoobot predefinito `odoobot@company-name.odoo.com` (o il nuovo valore se modificato)

  * il FROM specifico indicato per una campagna marketing e-mail

  * il FROM specifico che può essere indicato in un modello e-mail.




Vedi anche

  * [Collegare Gmail a Odoo utilizzando Google OAuth](google_oauth.html)

  * [Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth](azure_oauth.html)




## Configurare server diversi per e-mail di transazione e di massa¶

### Server e-mail personalizzati¶

Le e-mail di transazione e di mass possono essere configurate utilizzando server e-mail separati in Odoo. Ciò significa che le e-mail, i preventivi o le fatture inviate ai clienti ogni giorno verranno gestite come _e-mail di transazione_. Le _e-mail di massa_ , compreso l’invio di gruppi di fatture o preventivi, verranno gestite dall’app Automazione marketing o E-mail marketing.

Example

Puoi utilizzare servizi come Gmail, Amazon SES o Brevo per le e-mail di transazione e servizi come Mailgun, Sendgrid o Mailjet per le e-mail di massa.

Per prima cosa, attiva la modalità sviluppatore e vai su Impostazioni ‣ Funzioni tecniche ‣ E-mail: Server e-mail in uscita. In questa sezione, aggiungi due record di server e-mail in uscita, uno per il server di e-mail transazionale e uno per il server e-mail di massa. Inserisci un valore più basso nel campo Priorità per il server transazionale (ad es., `1`) rispetto al server e-mail di massa (ad es., `2`), così da dare priorità alle e-mail di transazione.

Apri l’app Marketing e-mail ‣ Configurazione ‣ Impostazioni, attiva il server dedicato e seleziona il server e-mail appropriato. Odoo usa il server con il valore di priorità più basso per le e-mail di transazione e il server selezionato qui per le e-mail di massa.

#### Filtro mittente¶

Importante

È **fortemente consigliato** configurare il filtro mittente nei server e-mail in uscita seguendo le istruzioni del fornitore.

Il campo Filtro mittente permette di utilizzare un server e-mail in uscita specifico in base all’indirizzo e-mail del _mittente_ o al dominio di cui Odoo fa le veci. Il **valore deve essere un dominio o un indirizzo completo** che corrisponde all’indirizzo e-mail del mittente e viene considerato sicuro dal server e-mail in uscita lato fornitore.

Se il filtro mittente non viene utilizzato, le e-mail verranno inviate utilizzando l’indirizzo di notifica.

Avvertimento

Alcuni server e-mail in uscita richiedono una configurazione specifica del filtro mittente.

Quando un’e-mail viene inviata da Odoo, la seguente sequenza viene utilizzata per scegliere il server e-mail in uscita:

  * In primo luogo, Odoo cerca un server che ha lo stesso valore per il filtro mittente (ad es. indirizzo e-mail) indicato nell’e-mail in uscita. Questa configurazione è ideale se tutti gli utenti di un’azienda condividono lo stesso dominio ma hanno parti locali diverse.




Example

Se l’indirizzo e-mail del mittente corrisponde a `test@example.com`, è possibile utilizzare solo un server e-mail con il valore filtro mittente uguale a `test@example.com` o `example.com`.

  * Se in base al primo criterio non viene trovato nessun server, Odoo cercherà il primo server senza un valore impostato per il filtro mittente. L’e-mail verrà sostituita dall’indirizzo di notifica.

  * Se non viene trovato alcun server in base al secondo criterio, Odoo utilizza il primo server e l’e-mail verrà sostituita dall’indirizzo di notifica.




Nota

Per determinare quale sia il primo server, Odoo utilizza il valore priorità (più basso è il valore, più alta è la priorità). In caso contrario, il primo server viene determinato dai nomi dei server, utilizzando l’ordine alfabetico.

  * If there is no mail server, Odoo relies on the system parameter value.




È anche possibile utilizzare il server e-mail di Odoo per le e-mail transazionali oltre che per gli invii di massa.

### Utilizzare un server e-mail esterno e il server predefinito di Odoo¶

In Odoo Online e Odoo.sh, i database vengono avviati con il server SMTP di Odoo. Se non viene impostato alcun server e-mail in uscita, verrà utilizzato il server SMTP predefinito di Odoo.

Example

Se si utilizza un server e-mail in uscita contemporaneamente al server predefinito di Odoo (CLI), il filtro mittente del server e-mail in uscita deve contenere un dominio personalizzato e il filtro mittente del CLI deve contenere il sottodominio di Odoo. Se non c’è un filtro mittente, l’e-mail verrà inviata utilizzando l’indirizzo di notifica.

Nota

Su Odoo online, l’interfaccia della riga di comando è equivalente al server e-mail predefinito di Odoo, utilizzando lo stesso limite come se non ci fosse un server e-mail in uscita.

Suggerimento

Su Odoo Online, la pagina mostra anche l’utilizzo giornaliero delle e-mail e il limite giornaliero. Su Odoo.sh, è necessario controllare nella pagina di monitoraggio il numero di e-mail in uscita che sono state inviate.

Nota

Su Odoo.sh, per utilizzare l’interfaccia a riga di comando, è possibile configurare un server e-mail in uscita nel file di configurazione.

Avvertimento

Il server e-mail di Odoo è progettato per le e-mail di transazione e campagne marketing su piccola scala. Il [limite giornaliero](faq.html#email-issues-outgoing-delivery-failure-messages-limit) dipende dal tipo di database e dalle applicazioni utilizzate.

## Utilizzare un dominio personalizzato con un server e-mail esterno¶

Come nel capitolo precedente, è necessaria una configurazione adeguata per assicurarsi che il server e-mail esterno possa inviare e-mail utilizzando il tuo dominio personalizzato. Consulta la documentazione del fornitore per configurare in maniera adeguata i record necessari (SPF, DKIM e DMARC). È disponibile un elenco dei [fornitori più comuni](email_domain.html#email-domain-providers-documentation).

Nota

La configurazione DNS è richiesta quando usi il tuo proprio dominio. Se stai utilizzando un server e-mail in uscita esterno, la configurazione dei record, secondo quanto descritto nella sezione [Configurazione DNS Odoo per i propri server e-mail](email_domain.html), **non avrà l’effetto desiderato** perché dipende da Odoo quando si utilizza un server e-mail personalizzato. Odoo non permette di configurare sottodomini Odoo.

## Restrizione Port¶

Il Port 25 è bloccato per ragioni di sicurezza su Odoo online e Odoo.sh. Prova a utilizzare i port 465, 587 o 2525.

## Dominio alias¶

Il dominio catchall è specifico dell’azienda. Per impostazione predefinita, tutte le aziende condividono il sottodominio di Odoo (ad es., `company-name.odoo.com`) ma ogni azienda deve avere il proprio dominio e-mail personalizzato.

Quando attivi la modalità sviluppatore, le opzioni del dominio alias sono disponibili andando su Impostazioni ‣ Funzioni tecniche ‣ E-mail: Domini alias.

Avvertimento

Qualsiasi modifica del dominio alias deve essere effettuata con molta attenzione. Se uno degli alias (rimbalzo, catchall, predefinito da) viene modificato, tutte le e-mail precedenti che non sono state correttamente reindirizzate ai nuovi alias andranno perse.

Il campo Predefinito dall’alias può essere completato con una parte locale dell’indirizzo e-mail (`notifications` di default) o un indirizzo e-mail completo. Configuralo per determinare l’intestazione `mittente` delle tue e-mail. Se utilizzi un indirizzo e-mail completo, tutte le e-mail in uscita verranno sostituite da questo indirizzo.

## Sistema di notifica¶

Quando un’e-mail viene inviata dal chatter, i clienti possono rispondere direttamente. Se un cliente risponde direttamente a un’e-mail, la risposta viene registrata nello stesso chatter, funzionando così come un thread di messaggi relativi al record.

Una volta ricevuta la risposta, Odoo utilizza i follower registrati (in base ai sottotipi) per inviare una notifica via e-mail o nella casella di posta di Odoo, a seconda delle preferenze dell’utente.

Example

Se un cliente con indirizzo e-mail `“Mary” <mary@customer.example.com>` risponde direttamente a un’e-mail in arrivo dal database Odoo, il comportamento predefinito di Odoo consiste nel ridistribuire il contenuto delle e-mail agli altri follower nel thread.

Dato che il dominio di Mary non appartiene dal dominio alias, Odoo sostituisce l’indirizzo e-mail e utilizza l’indirizzo e-mail di notifica per notificare i follower. La sostituzione dipende dalla configurazione eseguita nel database. Per impostazione predefinita, su Odoo online e Odoo.sh, l’indirizzo e-mail del `mittente` verrà sostituito con il valore `notifications@company-name.odoo.com` invece di `mary@customer.example.com`.

L’indirizzo viene costruito utilizzando il nome del mittente e `{dominio alias, predefinito dall'alias}`@`{dominio alias, nome dominio}`, per impostazione predefinita, `notifications@company-name.odoo.com`.

## Utilizzare un unico indirizzo e-mail per e-mail in uscita¶

To force the email address from which emails are sent, activate the [Modalità sviluppatore (modalità di debug)](../developer_mode.html#developer-mode), and go to Settings ‣ Technical ‣ Email: Alias Domains. On the Default From Alias, use the local-part or a complete email address as the value.

Avvertimento

Se un **indirizzo completo** viene utilizzato come valore del campo Predefinito dall’alias, **tutte** le e-mail in uscita verranno sostituite da questo indirizzo.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/email_communication/email_servers_outbound.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_domain.html "Configurare record DNS per inviare e-mail in Odoo") |
  * [precedente](email_servers_inbound.html "Gestire messaggi in entrata") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Gestire messaggi in uscita


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