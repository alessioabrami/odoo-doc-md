# Nomi di dominio — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](address_autocomplete.html "Address autocomplete") |
  * [precedente](../configuration.html "Configurazione") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Configurazione](../configuration.html) »
  * Nomi di dominio



# Nomi di dominio¶

I nomi di dominio sono indirizzi basati su testo che identificano una posizione su Internet come nel caso di un sito web. Rispetto agli indirizzi IP numerici, i nomi di dominio consentono una navigazione riconoscibile e memorizzabile.

I database **Odoo Online** e **Odoo.sh** utilizzano un **sottodominio** del **dominioéé `odoo.com` per impostazione predefinita (ad es., `mycompany.odoo.com`).

Tuttavia, è possibile utilizzare un nome di dominio personalizzato registrando un nome di dominio gratuito (disponibile solo per database Odoo Online) oppure configurando un nome di dominio già posseduto.

Vedi anche

[Tutorial Odoo: Registra un nome di dominio gratuito [video]](https://www.odoo.com/slides/slide/register-a-free-domain-name-1663)

## Registrare un nome di dominio gratuito con Odoo¶

Per registrare un nome di dominio gratuito per un anno per un database Odoo Online, accedi al tuo account e apri il [gestore di database](https://www.odoo.com/my/databases). Fai clic sull’icona a forma di ingranaggio (⚙️) accanto al nome del database e seleziona Nomi di dominio.

Cerca il nome di dominio che più ti piace e verificane la disponibilità.

Suggerimento

Assicurati che l’app Sito web sia installata se l’opzione per la registrazione del nome di dominio non appare.

Seleziona il nome di dominio desiderato, completa il modulo Proprietario dominio e fai clic su Registra. Il nome di dominio scelto viene collegato direttamente al databse.

In seguito, puoi mappare il nome di dominio al tuo sito web.

Importante

L’indirizzo specificato nel campo Proprietario dominio riceverà un’e-mail di verifica da `noreply@domainnameverification.net`. È fondamentale verificare l’indirizzo e-mail per mantenere il dominio attivo e ricevere il preventivo di rinnovo prima della scadenza.

La registrazione del nome di dominio è gratuita per il primo anno. Dopo questo periodo, Odoo continuerà a gestire il dominio in collaborazione con **Gandi.net** , registratore di nomi di dominio, e ti verrà addebitato [il tasso di rinnovo di Gandi.net](https://www.gandi.net/en/domain). Odoo invia il preventivo di rinnovo ogni anno all’indirizzo e-mail indicato nel campo Proprietario dominio molte settimane prima rispetto alla data di scadenza del dominio. Il dominio viene rinnovato automaticamente una volta confermato il preventivo.

Nota

  * L’offerta è disponibile solo per database **Odoo Online**.

  * L’offerta è linitata ad **un** nome di dominio per cliente.

  * L’offerta è limitata alla registrazione di un **nuovo** nome di dominio.

  * L’offerta è disponibile per il piano _Una App Gratuita*_. Assicurati che il tuo sito web contenga del contenuto originale affinché Odoo possa verificare che la tua richiesta sia legittima e rispetti l”[Informativa sui criteri di utilizzo di Odoo](https://www.odoo.com/acceptable-use). Dato l’alto numero di richieste, Odoo potrebbe impiegare più giorni per visionarle.




### Record DNS¶

Per gestire record relativi al nome di dominio gratuito DNS, apri il [gestore di database](https://www.odoo.com/my/databases), fai clic sull’icona a forma di ingranaggio (⚙️) accanto al nome del database, seleziona Nomi di dominio e fai clic su DNS.

  * A: il record A contiene l’indirizzo IP del dominio. Viene creato automaticamente e **non** può essere modificato o eliminato.

  * CNAME: i record CNAME inoltra un dominio o sottodominio a un altro dominio. Uno viene creato automaticamente per mappare il sottodominio `www.` al database. Se il database viene rinominato, anche il record CNAME **deve** essere rinominato.

  * MX: i record MX indica ai server a chi far recapitare le e-mail.

  * TXT: i record TXT possono essere utilizzati per vari scopi (ad es., verificare la proprietà del nome di dominio).




Qualsiasi modifica apportata ai record DNS può impiegare fino a **72 ore** per essere applicata a tutti i server.

Nota

[Invia un ticket di supporto](https://www.odoo.com/help) se hai bisogno di assistenza per gestire il nome di dominio.

### Casella di posta elettronica¶

L’offerta relativa al nome di dominio gratuito per un anno **non** include una casella di posta. Esistono due opzioni per collegare il nome di dominio ad una casella.

#### Utilizzare un sottodominio¶

È possibile creare un sottodominio (ad es., `subdomain.yourdomain.com`) per utilizzarlo come dominio alias per il database. Ciò permette agli utenti di creare record nel database da e-mail ricevute tramite l’alias `email@subdomain.yourdomain.com`.

Per farlo, apri il [gestore di database](https://www.odoo.com/my/databases), fai clic sull’icona a forma di ingranaggio (⚙️) accanto al nome del database e vai su Nomi di dominio ‣ DNS ‣ Aggiungi record DNS ‣ CNAME. In seguito, inserisci il sottodominio desiderato nel campo Nome (ad es., `sottodominio`), il dominio del database originale con un punto alla fine (ad es., `mycompany.odoo.com.`) nel campo Contenuto e fai clic su Aggiungi record.

Aggiungi l’alias di dominio come _dominio personale_ facendo clic su Usa il mio dominio, inserendo l’alias (ad es., `subdomain.yourdomain.com`), cliccando su Verifica per poi selezionare Confermo, è stato sistemato.

Infine, apri il tuo database e vai su Impostazioni. Nel campo Dominio alias, inerisci il dominio alias (ad es., `subdomain.yourdomain.com`), fai clic su Crea e poi Salva.

#### Utilizzare un provider di servizi e-mail esterno¶

Per utilizzare un provider di servizi e-mail esterno, devi configurare un record MX. Per farlo, apri il [gestore di database](https://www.odoo.com/my/databases), fai clic sull’icona a forma di ingranaggio (⚙️) accanto al nome del database per poi fare clic su Nomi di dominio ‣ DNS ‣ Aggiungi record DNS ‣ MX. I valori da inserire per i campi Nome, Contenuto e Priorità dipendono dal provider di servizi e-mail esterno.

Vedi anche

  * [Google Workspace: valori record MX](https://support.google.com/a/answer/174125?hl=en)

  * [Outlook e Exchange Online: aggiungere un record MX per le e-mail](https://learn.microsoft.com/en-us/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide#add-an-mx-record-for-email-outlook-exchange-online)




## Configurare un nome di dominio esistente¶

Se possiedi già un nome di dominio, puoi utilizzarlo per il tuo sito web Odoo.

Avvertimento

È fortemente consigliato seguire le tre fasi **in ordine** per evitare qualsiasi problema con la convalida del certificato SSL:

  1. Aggiungi un record CNAME

  2. Mappa il nome di dominio al tuo database Odoo

  3. Mappa il nome di dominio al tuo sito web Odoo




### Aggiungere un record CNAME¶

È necessario aggiungere un record CNAME per trasferire il nome di dominio all’indirizzo del database Odoo.

Odoo OnlineOdoo.sh

L’indirizzo di destinazione del record CNAME deve essere l’indirizzo del database indicato durante la creazione (ad es., `mycompany.odoo.com`).

L’indirizzo di destinazione del record CNAME deve essere l’indirizzo principale del progetto che può essere trovato su Odoo.sh facendo clic su Impostazioni ‣ Nome progetto oppure un ramo specifico (produzione, staging o sviluppo) seguendo il percorso Rami ‣ Seleziona ramo ‣ Impostazioni ‣ Domini personalizzati e fai clic su Come configurare il dominio?. Un messaggio indicherà quale sarà l’indirizzo di destinazione del record CNAME.

Le istruzioni specifiche dipendono dal servizio di hosting DNS.

Vedi anche

  * [GoDaddy: Aggiungere un record CNAME](https://www.godaddy.com/help/add-a-cname-record-19236)

  * [Namecheap: come creare un record CNAME per un dominio](https://www.namecheap.com/support/knowledgebase/article.aspx/9646/2237/how-to-create-a-cname-record-for-your-domain)

  * [OVHcloud: Aggiungere un nuovo record DNS](https://docs.ovh.com/us/en/domains/web_hosting_how_to_edit_my_dns_zone/#add-a-new-dns-record)

  * [Cloudflare: Manage DNS records](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-dns-records/)




Importante

Odoo supporta esclusivamente sottodomini. Per utilizzare nomi di domini semplici (un nome di dominio senza sottodomini o prefissi) (`yourdomain.com`), crea un reindirizzamento 301 per reindirizzare i visitatori verso `www.yourdomain.com`.

Example

Possiedi il nome di dominio `yourdomain.com` e l’indirizzo del tuo database Odoo Online è `mycompany.odoo.com`. Vuoi accedere al database Odoo con il dominio `www.yourdomain.com` ma anche con il dominio semplice `yourdomain.com`.

Per farlo, crea un record CNAME per il sottodominio `www` inserendo `mycompany.odoo.com` come indirizzo di destinazione. In seguito, crea un reindirizzamento (301 definitivo o visibile) per reindirizzare i visitatori da `yourdomain.com` a `wwww.yourdomain.com`.

#### Using Cloudflare to secure and redirect a naked domain¶

To redirect a naked domain with a secure HTTPS connection, we recommend using Cloudflare, as most DNS hosting services do not offer an easy way to do so.

  1. [Sign up and log in to Cloudflare](https://dash.cloudflare.com/sign-up).

  2. Enter your domain name on [Cloudflare’s dashboard](https://dash.cloudflare.com/login) and select Quick scan for DNS records.

  3. Choose a plan (the free plan is sufficient).

  4. Follow Cloudflare’s instructions and recommendations to complete the activation.

  5. Add a CNAME record to redirect your naked domain (`yourdomain.com`) to the `www` subdomain (e.g., `www.yourdomain.com`) by clicking DNS in the navigation menu, then clicking the Add record button, and using the following configuration:

     * Type: CNAME

     * Name: `@` (or `yourdomain.com`)

     * Target: e.g., `www.yourdomain.com`

     * Proxy status: Proxied

  6. Add another second CNAME record to redirect the `www` subdomain (e.g., `www.yourdomain.com`) to your database address (e.g., `mycompany.odoo.com`) using the following configuration:

     * Type: CNAME

     * Name: e.g., `www.yourdomain.com`

     * Target: e.g., `mycompany.odoo.com`

     * Proxy status: DNS only

  7. Define a redirect rule to permanently redirect (301) your naked domain (e.g., `yourdomain.com`) to both `http://` and `https://` by going to Rules ‣ Create rule ‣ Products, and clicking Create a Rule under Redirect Rules:

     * Enter any Rule name.

     * Under the If incoming requests match… section, select Custom filter expression and use the following configuration:

       * Field: Hostname

       * Operator: equals

       * Value: e.g., `yourdomain.com`

     * Under the Then… section, use the following configuration:

       * Type: Dynamic

       * Expression: e.g., `concat("https://www.yourdomain.com", http.request.uri.path)`

       * Status code: 301

       * Preserve query string: enabled

  8. Go to SSL/TLS and set the encryption mode to Full.




### Mappare un nome di dominio in un database Odoo¶

Avvertimento

Assicurati di aver aggiunto un record CNAME al DNS del nome di dominio **prima** di mappare il nome di dominio nel tuo database Odoo.

In caso di mancata esecuzione, il certificato SSL potrebbe non essere convalidato e restituire un errore di tipo _nome certificato non corrispondente_. I browser web spesso mostrano l’errore come _«La connessione non è privata»_.

Se riscontri l’errore dopo aver mappato il nome di dominio nel database, aspetta fino a 5 giorni in quanto la convalida potrebbe ancora avvenire. Altrimenti, è possibile [inviare un ticket di supporto](https://www.odoo.com/help) inserendo screenshot dei record CNAME.

Odoo OnlineOdoo.sh

Open the [database manager](https://www.odoo.com/my/databases), click the gear icon (⚙️) next to the database name, and go to Domain Names ‣ Use my own domain. Then, enter the domain name (e.g., `www.yourdomain.com`), click Verify and I confirm, it’s done.

Su Odoo.sh, vai su Rami ‣ seleziona il tuo ramo ‣ Impostazioni ‣ Domini personalizzati, inserisci il nome di dominio da aggiungere per poi fare clic su Aggiungi dominio.

Vedi anche

[Rami Odoo.sh: scheda impostazioni](../../../../administration/odoo_sh/getting_started/branches.html#odoosh-gettingstarted-branches-tabs-settings)

#### Crittografia SSL (protocollo HTTPS)¶

La **codifica SSL** permette ai visitatori di navigare in un sito web attraverso una connessione sicura che appare come protocollo _https://_ all’inizio di un indirizzo web rispetto ad un protocollo non sicuro _http://_.

Odoo genera un certificato SSL separato per ogni dominio mappato in un database utilizzando il [protocollo Let’s Encrypt’s certificate authority and ACME](https://letsencrypt.org/how-it-works/).

Nota

  * La generazione di un certificato potrebbe impiegare fino a 24 ore.

  * Dopo aver mappato il nome di dominio nel database, verranno effettuati vari tentativi per convalidare il certificato nell’arco di cinque giorni.

  * Se utilizzi un altro servizio, è possibile continuare ad utilizzarlo o modificarlo con Odoo.




Importante

Non viene generato nessun certificato SSL per domini semplici (nomi di dominio senza sottodomini o prefissi).

#### URL base web di un database¶

Nota

Se l’app Sito web è installata nel database, salta questa sezione e continua dalla sezione Mappa un nome di dominio in un sito web.

L” _URL base web_ o URL radice di un database ha un impatto sull’indirizzo del sito web principale e su tutti i link inviati ai clienti (ad es., preventivi, link portale, ecc.).

Per far sì che il nome di dominio personalizzato diventi l” _URL base web_ del tuo database, accedi al database utilizzando il nome di dominio personalizzato e accedi come amministratore (un utente appartenente al gruppo di diritti di accesso Impostazioni in Amministrazione).

Importante

Se hai accesso al database con l’indirizzo Odoo originale (ad es., `mycompany.odoo.com`), l” _URL base web_ del tuo database verrà aggiornato di conseguenza. Per evitare l’aggiornamento automatico dell” _URL base web_ quando un amministratore accede al database, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode), vai su Impostazioni ‣ Tecnico ‣ Parametri sistema ‣ Nuovo e inserisci `web.base.url.freeze` come Chiave e `Vero` come Valore.

Nota

È possibile configurare l’URL base web anche manualmente. Per farlo, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode), vai su Impostazioni ‣ Tecnico ‣ Parametri sistema e cerca la chiave `web.base.url` (creala se necessario) e inserisci l’indirizzo completo del tuo sito web come valore (ad es.., `https://www.yourdomain.com`). L’URL deve includere il protocollo `https://` (or `http://`) e _non_ deve terminare con uno slash (`/`).

### Mappare un nome di dominio in un sito web Odoo¶

La mappatura del nome di dominio nel tuo sito web è diversa rispetto alla mappatura nel database:

  * Definisce il nome di dominio come principale per il tuo sito web così da aiutare i motori di ricerca a indicizzare il sito web correttamente.

  * Definisce il nome di dominio come l’URL base per il tuo database, inclusi link al portale inviate via e-mail ai clienti.

  * Se possiedi diversi siti web, mappa il nome di dominio nel sito web appropriato.




Vai su Sito web ‣ Configurazione ‣ Impostazioni. Se possiedi più siti web, seleziona quello che vuoi configurare. Nel campo Dominio, inserisci l’indirizzo del tuo sito web (ad es., `https://www.yourdomain.com`) e Salva.

Avvertimento

La mappatura del nome di dominio nel sito web Odoo impedisce a Google Search di indicizzare il tuo indirizzo di database originale (ad es., `mycompany.odoo.com`).

Se entrambi gli indirizzi sono già stati indicizzati, potrebbe volerci un po” di tempo prima che l’indicizzazione del secondo indirizzo venga rimossa da Google Search. Puoi utilizzare la [Console Google Search](https://search.google.com/search-console/welcome) per risolvere il problema.

Nota

Se hai più siti web e aziende sul tuo database, assicurati di selezionare l”Azienda corretta in Sito web ‣ Configurazione ‣ Impostazioni. Facendolo, a Odoo verrà indicato quale URL utilizzare come URL base secondo l’azienda in uso.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/website/configuration/domain_names.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](address_autocomplete.html "Address autocomplete") |
  * [precedente](../configuration.html "Configurazione") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Configurazione](../configuration.html) »
  * Nomi di dominio


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions