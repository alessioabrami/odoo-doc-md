# On-premise — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](on_premise/packages.html "Programmi di installazione") |
  * [precedente](odoo_sh/advanced/frequent_technical_questions.html "Domande tecniche frequenti") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * On-premise



# On-premise¶

## Registrare un database¶

Per registrare il tuo database, inserisci il codice dell’abbonamento nel banner dell’app Dashboard. Se la registrazione avviene con successo, il banner diventerà verde e mostrerà la data di scadenza del database.

Suggerimento

La data di scadenza viene visualizzata anche in fondo alla pagina relativa alle Impostazioni.

## Duplicare un database¶

È possibile duplicare un database accedendo al gestore di database nel tuo server (`<odoo-server>/web/database/manager`). Generalmente, si vuole duplicare un database di produzione in un database di prova neutralizzato. È possibile farlo selezionando la casella neutralizza quando viene richiesto, laquale esegue tutti gli script `neutralize.sql` per ogni modulo installato.

## Messaggi di errore comuni e soluzioni¶

### Errore di registrazione¶

In caso di errore di registrazione, dovrebbe apparire il seguente messaggio.

Per risolvere il problema:

  * Verifca la **validità dell’abbonamento Odoo Enterprise** controllando se fra i dettagli dell’abbonamento c’è il tag In corso nell”[Account Odoo](https://accounts.odoo.com/my/subscription) oppure contatta l’Account Manager.

  * Assicurati che **nessun altro database sia collegato** al codice dell’abbonamento, in quanto è possibile collegare solo un database per abbonamento.

Suggerimento

Se hai bisogno di un database di prova o di sviluppo, è possibile duplicare un database.

  * Verifica che **nessun database condivida lo stesso UUID** (Identificatore Univoco Universale) aprendo il [contratto Odoo](https://accounts.odoo.com/my/subscription). Se due o più database condividono lo stesso UUID, verrà visualizzato il loro nome.

In questo caso, modifica manualmente l’UUID del/dei database oppure [invia un ticket di supporto](https://www.odoo.com/help).

  * Dato che la notifica di aggiornamento deve raggiungere i server di convalida dell’abbonamento Odoo, assicurati che **le impostazioni di rete e firewall** permettano al server Odoo di attivare connessioni in uscita verso:

    * Odoo 18.0 e versioni successive: `services.odoo.com` sulla porta `80`

    * Odoo 17.0 e inferiori: `services.openerp.com` sulla porta `80`

È necessario lasciare aperte le porte anche dopo la registrazione di un database perché la notifica di aggiornamento avviene una volta a settimana.




### Errore troppi utenti¶

Se in un database locale sono presenti più utenti rispetto a quanto previsto dall’abbonamento Odoo Enterprise, verrà visualizzato il seguente messaggio:

Quando il messaggio appare, hai 30 giorni per agire prima che il database scada. Il conto alla rovescia viene aggiornato ogni giorno.

Per risolvere il problema puoi:

  * **aggiungere più utenti** all’abbonamento facendo clic sul link Aggiorna abbonamento visualizzato nel messaggio per la convalida del preventivo di upsell e paga per gli utenti aggiuntivi.

  * [Disattivare gli utenti](../applications/general/users.html#users-deactivate) e **rifiutare** il preventivo di upsell.




Una volta che il database ha il numero corretto di utenti, il messaggio di scadenza scompare automaticamente dopo pochi giorni, al momento della verifica successiva.

### Errore database scaduto¶

Se il tuo database scade prima del rinnovo dell’abbonamento, verrà visualizzato il seguente messaggio:

Il messaggio appare se non riesci ad agire prima della fine del conto alla rovescia di 30 giorni.

Per risolvere il problema puoi:

  * Fai clic sul link Rinnova abbonamento visualizzato nel messaggio e completa la procedura. Se paghi tramite bonifico, l’abbonamento verrà rinnovato al momento della ricezione del pagamento, il che potrebbe impiegare qualche giorno. I pagamenti tramite carta di credito vengono elaborati immediatamente.

  * [Invia un ticket di supporto](https://www.odoo.com/help).




  * Programmi di installazione
    * Linux
      * [Preparazione](on_premise/packages.html#prepare)
      * [Repository](on_premise/packages.html#repository)
      * [Pacchetto di distribuzione](on_premise/packages.html#distribution-package)
    * [Windows](on_premise/packages.html#windows)
  * Installare la fonte
    * Recuperare le sorgenti
      * [Archivia](on_premise/source.html#archive)
      * [Git](on_premise/source.html#git)
    * Preparazione
      * [Python](on_premise/source.html#python)
      * [PostgreSQL](on_premise/source.html#postgresql)
      * [Dipendenze](on_premise/source.html#dependencies)
    * [Eseguire Odoo](on_premise/source.html#running-odoo)
  * Aggiornamenti correzione bug
    * [Introduzione](on_premise/update.html#introduction)
    * [In breve](on_premise/update.html#in-a-nutshell)
    * [Fase 1: Scarica una versione di Odoo aggiornata](on_premise/update.html#step-1-download-an-updated-odoo-version)
    * [Fase 2: Effettuare il back-up del database](on_premise/update.html#step-2-make-a-backup-of-your-database)
    * Fase 3: Installare la versione aggiornata
      * [Programmi di installazione](on_premise/update.html#packaged-installers)
      * [Installare dal codice sorgente (Tarball)](on_premise/update.html#source-install-tarball)
      * [Installare dal codice sorgente (Github)](on_premise/update.html#source-install-github)
      * [Docker](on_premise/update.html#docker)
  * Configurazione sistema
    * dbfilter
      * [Configurazione modelli](on_premise/deploy.html#configuration-samples)
    * PostgreSQL
      * [Esempio di configurazione](on_premise/deploy.html#configuration-sample)
      * Configurare Odoo
        * [Esempio di configurazione](on_premise/deploy.html#id4)
      * [SSL tra Odoo e PostgreSQL](on_premise/deploy.html#ssl-between-odoo-and-postgresql)
    * Server integrato
      * [Calcolo del numero di worker](on_premise/deploy.html#worker-number-calculation)
      * [Calcolo dimensioni memoria](on_premise/deploy.html#memory-size-calculation)
      * [LiveChat](on_premise/deploy.html#livechat)
      * [Esempio di configurazione](on_premise/deploy.html#id6)
    * HTTPS
      * [Esempio di configurazione](on_premise/deploy.html#id8)
      * [Protezione avanzata HTTPS](on_premise/deploy.html#https-hardening)
    * Odoo come applicazione WSGI
      * [Worker corn](on_premise/deploy.html#cron-workers)
      * [LiveChat](on_premise/deploy.html#id9)
    * Servire file statici e allegati
      * [Servire file statici](on_premise/deploy.html#serving-static-files)
      * [Servire degli allegati](on_premise/deploy.html#serving-attachments)
    * Sicurezza
      * [Bloccare attacchi Brute Force](on_premise/deploy.html#blocking-brute-force-attacks)
      * [Sicurezza gestione database](on_premise/deploy.html#database-manager-security)
      * Ripristinare la password master
        * [Individuare file di configurazione](on_premise/deploy.html#locate-configuration-file)
        * [Modificare password vecchie](on_premise/deploy.html#change-old-password)
        * [Riavviare il server Odoo](on_premise/deploy.html#restart-odoo-server)
        * [Utilizzare l’interfaccia web per ricrittografare la password](on_premise/deploy.html#use-web-interface-to-re-encrypt-password)
    * [Browser supportati](on_premise/deploy.html#supported-browsers)
  * Gateway di posta elettronica
    * [Prerequisiti](on_premise/email_gateway.html#prerequisites)
    * [Per Postfix](on_premise/email_gateway.html#for-postfix)
    * [Per Exim](on_premise/email_gateway.html#for-exim)
  * IP geo
    * [Installazione](on_premise/geo_ip.html#installation)
    * [Testare la geolocalizzazione GeoIP sul sito web Odoo](on_premise/geo_ip.html#test-geoip-geolocation-in-your-odoo-website)
  * Passare da Community a Enterprise
    * [Su Linux, utilizzando un programma di installazione](on_premise/community_to_enterprise.html#on-linux-using-an-installer)
    * [Su Linux, utilizzando il codice sorgente](on_premise/community_to_enterprise.html#on-linux-using-the-source-code)
    * [Su Windows](on_premise/community_to_enterprise.html#on-windows)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/on_premise.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](on_premise/packages.html "Programmi di installazione") |
  * [precedente](odoo_sh/advanced/frequent_technical_questions.html "Domande tecniche frequenti") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * On-premise


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
  *[EDI]: electronic data interchange
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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
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