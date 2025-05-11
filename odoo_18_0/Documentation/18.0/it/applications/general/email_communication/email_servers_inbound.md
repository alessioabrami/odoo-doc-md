# Gestire messaggi in entrata — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_servers_outbound.html "Gestire messaggi in uscita") |
  * [precedente](../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Gestire messaggi in entrata



# Gestire messaggi in entrata¶

Un messaggio in entrata è un’e-mail inviata a un database Odoo. Chiunque può inviare e-mail a un alias e-mail creato nel database o rispondere a un’e-mail che è stata inviata precedentemente dal database tramite l’intestazione _rispondi a_.

## Alias e-mail¶

### Alias specifici per modello¶

Alcune applicazioni hanno alias specifici (team vendite, helpdesk, progetti, ecc.). Questi tipi di alias vengono utilizzati per:

  * creare un record quando un’e-mail viene inviata direttamente all’alias;

  * Ricevere risposte a un’e-mail inviata inizialmente da un record.




Example

Nell’esempio mostrato di sopra, l’invio di un’e-mail a `info@company-name.odoo.com` porterà alla creazione di una nuova opportunità o di un nuovo lead che verrà assegnato automaticamente al team vendite corrispondente. Se un’e-mail viene inviata dal chatter di un’opportunità esistente, l’indirizzo _rispondi a_ sarà `info@company-name.odoo.com`. La risposta verrà registrata nel chatter giusto secondo l’intestazione dell” _id del messaggio_.

### Catchall¶

Se un’applicazione non ha un alias, viene utilizzato un alias generico di ripiego: il catchall. Un’e-mail inviata da un chatter ha un indirizzo di risposta impostato su questo alias catchall. Una risposta inviata al catchall viene registrata nel chatter giusto grazie all’intestazione _id messaggio_.

Per impostazione predefinita, verrà utilizzato il _catchall_ della parte locale. Attiva la modalità sviluppatore e vai su Impostazioni ‣ Funzioni tecniche ‣ E-mail: Domini alias per accedere alla configurazione.

Un’e-mail inviata al catchall deve sempre essere una risposta a un’e-mail precedente inviata dal database. Se un’e-mail viene inviata direttamente al catchall, il mittente riceverà il seguente messaggio:

Nota

L’indirizzo e-mail `info@company-name.com` mostrato nello screenshot sopra è l’indirizzo e-mail configurato per l’azienda. Una volta attività la modalità sviluppatore, saranno disponibili ulteriori opzioni di configurazione (come catchall e rimbalzo). È possibile modificarle facendo clic sul link interno del dominio e-mail. In generale, non è consigliato modificare le opzioni tranne se per motivi specifici in quanto impatterà tutte le risposte alle e-mail inviate precedentemente.

Example

Nell’app CRM è possibile configurare un alias per un team vendite. Quando un cliente risponde a un’e-mail in arrivo dall’app, l’indirizzo _rispondi a_ sarà `info@company-name.odoo.com`.

Quando un’e-mail viene inviata dall’app Contatti, l’indirizzo di risposta è `catchall@company-name.odoo.com` perché non c’è nessun alias sul modello del contatto.

Nota

Consigliamo di mantenere invariata la parte locale della catchall e del rimbalzo. Se questo valore viene modificato, le e-mail precedenti inviate dal database continueranno ad avere i valori delle parti locali precedenti. Ciò potrebbe comportare che le risposte non vengano ricevute correttamente nel database.

### Rimbalzo¶

Allo stesso modo in cui l’alias catchall è usato per costruire l’indirizzo di risposta, l’alias di rimbalzo è usato per costruire il _percorso di ritorno_ dell’e-mail. Il _percorso di ritorno_ viene utilizzato quando le e-mail non possono essere consegnate al destinatario e viene restituito un errore al mittente.

Per impostazione predefinita, verrà utilizzato il nome _rimbalzo_. Attiva la modalità sviluppatore e vai su Impostazioni ‣ Funzioni tecniche ‣ E-mail: Domini alias per accedere alla configurazione.

Nota

Su Odoo online, quando utilizzi il server per le e-mail in uscita predefinito, l’indirizzo del percorso di ritorno viene forzato al valore `bounce@company-name.odoo.com` indipendentemente dal valore configurato come alias di rimbalzo.

Quando si verifica un errore, viene ricevuta una notifica e visualizzata in una busta rossa nel chatter. In alcuni casi, la busta rossa può contenere solo un messaggio di `nessun errore`, il che significa che c’è un errore che Odoo non ha potuto gestire.

Verrà mostrata anche una notifica sull’icona dell’app Comunicazioni presente nella barra di navigazione.

Example

Se l’indirizzo e-mail del destinatario non è corretto, facendo clic sulla busta rossa nel chatter verrà visualizzato un messaggio di errore contenente il motivo del fallimento.

## Ricevere e-mail con la configurazione predefinita di Odoo¶

Su **Odoo online** e **Odoo.sh** , gli alias e-mail, gli indirizzi di risposta e di rimbalzo sono preconfigurati. Questi indirizzi utilizzano il dominio alias aggiunto automaticamente a un database standard.

Example

Ammesso che `https://mydatabase.odoo.com` sia l’URL del database, il dominio alias `mydatabase.odoo.com` viene creato automaticamente.Gli indirizzi catchcall e bounce, [rispettivamente`catchall@mydatabase.odoo](mailto:rispettivamente`catchall%40mydatabase.odoo).com` e `bounce@mydatabase.odoo.com`, possono essere utilizzati.

Una volta installa l’app CRM e creato un team vendite con alias `info`, sarà possibile utilizzare immediatamente l’indirizzo `info@mydatabase.odoo.com`. Lo stesso vale per ogni altro alias creato in altre applicazioni.

Il dominio del database è pronto per essere utilizzato per ricevere e-mail senza nessuna configurazione aggiuntiva.

## Usare sottodomini Odoo multipli¶

Su **Odoo online** , l’unico sottodominio Odoo è quello definito al momento della creazione del database.

Su **Odoo.sh** , è possibile usare vari sottodomini Odoo. Nelle impostazioni del branch, è possibile aggiungere ulteriori sottodomini Odoo a condizione che non siano stati ancora utilizzati in un altro branch. Questi domini devono essere aggiunti ai domini alias per essere utilizzati da un’azienda.

## Utilizzare un dominio personalizzato per i messaggi in entrata¶

Il [dominio alias](email_servers_outbound.html#email-outbound-alias-domain) deve essere selezionato nelle impostazioni generali. Se hai più aziende, ognuna deve essere configurata.

Tutti gli alias utilizzeranno questo dominio personalizzato. Le risposte ai modelli per i quali è configurato un alias vengono inviate a `[alias]@my-custom-domain.com`. Le risposte ad altri modelli vengono inviate al catchall attraverso `catchall@my-custom-domain.com`.

Importante

Se le e-mail vengono inviate utilizzando i server e-mail di Odoo e un dominio personalizzato, segui le [istruzioni descritte nella sezione «Utilizzare un dominio personalizzato con il server e-mail di Odoo»](email_servers_outbound.html#email-outbound-custom-domain-odoo-server).

Quando si inizia a utilizzare il dominio personalizzato, tutte le e-mail che utilizzano un alias (risposte, rimbalzi e invii diretti) vengono inviate a un indirizzo del dominio. In seguito, vengono inviate al server e-mail collegato al dominio stesso (record MX). Per visualizzarle nel chatter o creare nuovi record, è necessario recuperare le e-mail in entrata nel database Odoo.

Metodo | Benefici | Drawback  
---|---|---  
Reindirizzamento | Facile da configurare, le e-mail vengono inviate direttamente al database. | È necessario configurare ogni alias del database.  
Server e-mail in entrata | Permette di conservare una copia dell’e-mail nella casella di posta (con IMAP). Consente di creare record nel modello scelto. | In base al CRON, significa che le e-mail non vengono recuperate immediatamente nel database. Ogni alias del database deve essere configurato.  
Record MX | Solo un record deve essere creato per far funzionare correttamente tutti gli alias. | È richiesto l’utilizzo di un sottodominio. Richiede conoscenza tecnica avanzata.  
  
Importante

Per i **database on-premise** , i metodi di reindirizzamento e record MX richiedono anche la configurazione dello [script del gateway dell’e-mail](../../../administration/on_premise/email_gateway.html). L’esecuzione di questo script richiede **conoscenze tecniche e dell’infrastruttura avanzate**.

Importante

Per informazioni più dettagliate sulla gestione dei metodi descritti di seguito, consulta la documentazione del fornitore.

### Reindirizzamento¶

Se il database è su **Odoo online** od **Odoo.sh** , l’utilizzo del reindirizzamento è consigliato perché permette di ricevere messaggi senza ritardo nel database.

È obbligatorio reindirizzare l’indirizzo di catchall e di rimbalzo al sottodominio Odoo del database. Anche tutti gli altri alias utilizzati devono essere reindirizzati.

Example

Per un solo team vendite, sono necessari i seguenti reindirizzamenti:

  * `catchall@company-name.com` → `catchall@company-name.odoo.com`

  * `bounce@company-name.com` → `bounce@company-name.odoo.com`

  * `info@company-name.com` → `info@company-name.odoo.com`




Importante

Alcuni fornitori chiedono di convalidare il reindirizzamento inviando un link all’indirizzo e-mail di destinazione. Questa procedura è un problema per catchall e rimbalzo, poiché non vengono utilizzati per creare record.

  1. Modifica il valore del catchall sul dominio alias e-mail. La modalità sviluppatore deve essere attiva per accedere al menu. Ad esempio, può essere modificata da `catchall` a `temp-catchall`. Questo permetterà di utilizzare `catchall` come parte locale di un altro alias.

  2. Apri un’app che utilizza un alias. Ad esempio, l’app CRM contiene alias per ogni team vendite. Imposta `catchall` come parte locale degli alias di un team vendite.

  3. L’e-mail di convalida creerà un record nell’applicazione CRM. L’e-mail inviata sarà visibile nel chatter, permettendo la convalida del reindirizzamento.

  4. Non dimenticare di modificare nuovamente l’alias del team di vendita e il valore di catchall sul dominio alias e-mail, così come erano prima di questa procedura.




Nota

Un’alternativa ai reindirizzamenti è **inoltrare**. Grazie all’inoltro, **l’indirizzo che inoltra l’e-mail verrà identificato come mittente** mentre nel caso dei reindirizzamenti, il mittente originale sarà sempre lo stesso.

### Server e-mail in entrata¶

Come menzionato in precedenza, l’utilizzo dei reindirizzamenti è il metodo consigliato per ricevere e-mail in Odoo. Tuttavia, è anche possibile configurare server e-mail in entrata. L’utilizzo di questo metodo implica la creazione di un server e-mail in entrata per ogni casella di posta sul tuo server, catchall, rimbalzo e ogni alias del database così da recuperare tutte le e-mail in entrata. I server per le e-mail in entrata vengono creati andando su Impostazioni ‣ Funzioni tecniche ‣ E-mail: Server e-mail in entrata.

Importante

Si consiglia di utilizzare il protocollo IMAP piuttosto che il protocollo POP, in quanto IMAP recupera tutte le e-mail non lette, mentre POP recupera tutta la cronologia delle e-mail e poi le etichetta come eliminate nella casella di posta.

Suggerimento

È anche possibile collegare una casella di posta tramite [Gmail con Google OAuth](google_oauth.html) o [Outlook con Microsoft Azure OAuth](azure_oauth.html).

Indipendentemente dal protocollo scelto, le e-mail vengono recuperate utilizzando l’azione pianificata _E-mail: servizio recupero e-mail_.

Inoltre, l’utilizzo di un server di posta in entrata in Odoo offre l’opportunità di creare nuovi record in un modello specifico. Ogni server di posta in arrivo può creare record in un modello diverso.

Example

Le e-mail ricevute su `task@company-name.com` vengono recuperate dal database Odoo. Tutte le e-mail recuperate creeranno un nuovo lavoro nel database.

### Record MX¶

Una terza opzione è quella di creare un record MX nella zona DNS che specifichi il server e-mail che gestisce le e-mail inviate al tuo dominio. **Sono richieste conoscenze tecniche avanzate**.

Importante

La configurazione funziona solamente con un sottodominio nell’infrastruttura Odoo online od Odoo.sh (ad es., `@mail.mydomain.com`)

Di seguito vengono elencate alcune specifiche in base al tipo di hosting:

Odoo OnlineOdoo.sh

Il sottodominio personalizzato deve essere aggiunto al [Portale Odoo](../../websites/website/configuration/domain_names.html).

Il sottodominio personalizzato deve essere aggiunto alle [impostazioni del progetto](../../../administration/odoo_sh/getting_started/settings.html):

## Loop e-mail infiniti¶

In alcuni casi, è possibile creare loop e-mail infiniti. Odoo fornisce una protezione contro questo fenomeno garantendo che lo stesso mittente non invii troppe e-mail, **che potrebbero creare record** , a un alias in un intervallo di tempo specifico.

Per impostazione predefinita, un indirizzo e-mail può inviare fino a 20 e-mail in 120 minuti. Se vengono inviate più e-mail, quest’ultime verranno bloccate e il mittente riceverà il seguente messaggio:

Per modificare il comportamento predefinito, abilita la modalità sviluppatore, poi vai su Impostazioni ‣ Funzioni tecniche ‣ Parametri: Parametri di sistema per aggiungere due parametri.

  * Per il primo parametro, inserisci `mail.gateway.loop.minutes` come Chiave e scegli un numero di minuti come Valore (`120` è il valore predefinito).

  * Per il secondo parametro, inserisci `mail.gateway.loop.threshold` come Chiave e scegli un numero di e-mail come Valore (`20` è il comportamento predefinito).




Importante

Questi parametri vengono utilizzati esclusivamente per evitare la creazione di nuovi record e **non impediscono** l’aggiunta di **risposte** nel chatter.

## Autorizzare i parametri di sistema del dominio alias¶

Gli alias in entrata vengono impostati nel database Odoo per creare record a seguito della ricezione di e-mail. Per visualizzare gli alias impostati nel database Odoo, è necessario prima attivare la [modalità sviluppatore](../developer_mode.html#developer-mode). In seguito, vai su Impostazioni ‣ Funzioni tecniche ‣ Alias.

Il seguente parametro di sistema, `mail.catchall.domain.allowed`, con i valori dei domini alias consentiti, separati da virgole, filtra le e-mail indirizzate correttamente agli alias. L’impostazione dei domini per i quali l’alias può creare un ticket, un lead, un’opportunità e così via, elimina i falsi positivi in cui sono presenti indirizzi e-mail con il solo prefisso alias e non il dominio.

In alcuni casi, sono state effettuate delle corrispondenze nel database di Odoo quando viene ricevuta un’e-mail con lo stesso prefisso alias e un dominio diverso sull’indirizzo e-mail in entrata. Questo è vero per gli indirizzi e-mail del mittente, del destinatario e della Cc di un e-mail in arrivo.

Example

Quando Odoo riceve e-mail con il prefisso dell’alias `commerciale` negli indirizzi e-mail del mittente, del destinatario o della abbr:`Cc (Copia carbone)` (ad es. commercial@example.com), il database tratta erroneamente l’e-mail come alias `commerciale` completo, con un dominio diverso e quindi crea un ticket/lead/opportunità ecc.

Per aggiungere il parametro di sistema `mail.catchall.domain.allowed`, per prima cosa attiva la [modalità sviluppatore](../developer_mode.html#developer-mode). In seguito, vai su Impostazioni ‣ Funzioni tecniche ‣ Parametri di sistema. Fai clic su Nuovo. In seguito, inserisci `mail.catchall.domain.allowed` nel campo Chiave.

Successivamente, per il campo Valore, aggiungi i domini separati da virgole. __(Salva) manualmente e il parametro di sistema verrà applicato immediatamente.

## Rilevamento dell’arrivo di una parte locale¶

Quando crei un nuovo alias, appare un’opzione per attivare il Rilevamento dell’arrivo di una parte locale. Se selezionata, Odoo richiede solo la corrispondenza della parte locale per instradare un’e-mail in arrivo. Se questa funzione è disattivata, Odoo richiede la corrispondenza dell’intero indirizzo e-mail per instradare un’e-mail in arrivo.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/email_communication/email_servers_inbound.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_servers_outbound.html "Gestire messaggi in uscita") |
  * [precedente](../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Gestire messaggi in entrata


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