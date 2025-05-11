# Impostazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](online-editor.html "Editor online") |
  * [precedente](status.html "Stato") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Impostazioni



# Impostazioni¶

## Panoramica¶

Le impostazioni consentono di gestire la configurazione del tuo progetto.

## Nome progetto¶

Il nome del tuo progetto.

Definisce l’indirizzo che verrà utilizzato per accedere al database di produzione.

Gli indirizzi dei build di staging e di sviluppo derivano da questo nome e sono assegnati in modo automatico. Tuttavia, quando modifichi il nome del tuo progetto, solo i build futuri utilizzeranno il nuovo nome.

## Collaboratori¶

Gestisci gli utenti Github che possono accedere al progetto.

Esistono tre livelli di utenti:

  * Admin: ha accesso a tutte le funzionalità di un progetto Odoo.sh

  * Tester: ha accesso ai database di _staging_ e _sviluppo_ e ai rispettivi strumenti. Questo ruolo è per gli utenti che effettuano test di accettazione utenti. I tester possono lavorare con copie dei dati di produzione ma non possono accedere ai database di produzione attraverso gli strumenti di Odoo.sh.

  * Developer: ha accesso esclusivamente ai database _di sviluppo_ e ai relativi strumenti. Questo ruolo è per sviluppatori che propongono modifiche del codice ma non possono accedere ai database di produzione e staging tramite Odoo.sh.


|  | Sviluppatore | Tester | Amministratore  
---|---|---|---|---  
Sviluppo | Storia | ● | ● | ●  
| Connessione 1 clic | ● | ● | ●  
| Log | ● | ● | ●  
| Shell/SSH | ● | ● | ●  
| E-mail | ● | ● | ●  
| Impostazioni | ● | ● | ●  
Staging | Storia | ● | ● | ●  
| Connessione 1 clic |  | ● | ●  
| Log |  | ● | ●  
| Shell/SSH |  | ● | ●  
| E-mail |  | ● | ●  
| Monitoraggio |  | ● | ●  
| Backup |  |  | ●  
| Aggiorna |  | ● | ●  
| Impostazioni |  | ● | ●  
Produzione | Storia | ● | ● | ●  
| Connessione 1 clic |  |  | ●  
| Log |  |  | ●  
| Shell/SSH |  |  | ●  
| E-mail |  |  | ●  
| Monitoraggio |  |  | ●  
| Backup |  |  | ●  
| Aggiorna |  |  | ●  
| Impostazioni |  |  | ●  
Stato |  | ● | ● | ●  
Impostazioni |  |  |  | ●  
  
Avvertimento

I ruoli descritti si applicano solo all’utilizzo di Odoo.sh. È importante riportare l’attribuzione dei ruoli degli utenti all’interno del repository su GitHub. Per avere informazioni più dettagliate, consulta la sezione della documentazione di GitHub [Gestire una regola di protezione di un ramo](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule).

## Accesso pubblico¶

Consenti l’accesso pubblico ai tuoi build di sviluppo.

Se attivata, l’opzione rende pubblica la pagina relativa ai build, permettendo ai visitatori di visualizzare i registri dei build di sviluppo.

I build di produzione e staging sono esclusi, i visitatori possono solo vederne lo stato.

## Stati commit GitHub¶

Una volta attivata, l’opzione permette a Odoo.sh di inviare gli stati dei commit alla repository di GitHub quando un build viene creato o aggiornato. Per farlo, è necessario avere il token GitHub con i permessi adatti. Consulta la [documentazione di GitHub sui token di accesso personale](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) per scoprire come creare il tuo.

Nota

I **token personali dettagliati** di GitHub hanno una data di scadenza e verranno disattivati se l’aggiornamento allo stato del commit fallisce. Puoi sostituire il token in qualsiasi momento su Odoo.sh.

Gli stati dei commit inviati a GitHub possono avere i seguenti contesti:

  * ci/odoo.sh (dev): stato di un build di sviluppo

  * ci/odoo.sh (staging): stato di un build di staging

  * ci/odoo.sh (production): stato di un build di produzione

  * ci/odoo.sh (test_ci): se il token viene testato dalla pagina delle impostazioni, all’ultimo commit nella repository verrà inviato uno stato di test




## Domini personalizzati¶

Per configurare domini aggiuntivi, fai riferimento alla [scheda impostazioni](branches.html#odoosh-gettingstarted-branches-tabs-settings) del ramo corrispondente.

## Moduli secondarii¶

Configura le chiavi di distribuzione per gli archivi privati che utilizzi come moduli secondari nei tuoi rami per consentire a Odoo.sh di scaricarli.

Avvertimento

Queste impostazioni sono richieste solo per **archivi privati**. Se sei alla ricerca di come configurare i moduli secondari, le istruzioni sono disponibili al capitolo [Moduli secondari](../advanced/submodules.html#odoosh-advanced-submodules) della documentazione.

Quando un archivio è privato, non è possibile scaricarne pubblicamente i rami e le revisioni. Per questo motivo, è necessario configurare una chiave di distribuzione per Odoo.sh, in modo che il server Git remoto permetta alla nostra piattorma di scaricare le revisioni dell’archivio privato.

La configurazione di una chiave di distribuzione per un archivio priviato avviene seguendo questi step:

  * nella casella di testo, incolla l’URL SSH del sub-archivio privato e fai clic su _Add_ ;

    * ad es. _git@github.com:USERNAME/REPOSITORY.git_ ;

    * può trattarsi di un server Git diverso da Github, come Bitbucket, Gitlab o anche il proprio server di host;

  * copia la chiave pubblica;

    * dovrebbe somigliare a _ssh-rsa some…random…characters…here…==_ ;

  * nelle impostazioni del sub-archivio privato, aggiungi la chiave pubblica tra le chiavi di distribuzione;

    * Github.com: Settings ‣ Deploy keys ‣ Add deploy key

    * Bitbucket.com: Settings ‣ Access keys ‣ Add key

    * Gitlab.com: Settings ‣ Repository ‣ Deploy Keys

    * self-hosted: aggiunge la chiave al file authorized_keys dell’utente git nella cartella .ssh corrispondente;




## Dimensioni di archiviazione¶

La sezione illustra le dimensioni di archiviazione utilizzate dal tuo progetto.

Le dimensioni di archiviazione sono calcolate come segue:

  * la dimensione del database PostgreSQL;

  * la dimensione dei file del disco disponibile nel contenitore: filestore del database, cartella archiviazione sessioni…




Avvertimento

In caso tu voglia analizzare l’utilizzo del disco, puoi utilizzare lo strumento [ncdu](https://dev.yorhel.nl/ncdu/man) nella Web Shell.

Se le dimensioni del tuo database di produzione aumentano fino a superare quanto stabilito dall’abbonamento, la sincronizzazione sarà automatica.

## Worker del database¶

Worker aggiuntivi per il database possono essere configurati qui. Un numero maggiore di worker aiuta ad aumentare il carico che il database di produzione può gestire. Se ne aggiungi altri, il tutto verrà automaticamente sincronizzato con l’abbonamento.

Avvertimento

L’aggiunta di worker non risolverà magicamente i problemi di prestazione. Consente solo al servere di gestire più connessioni allo stesso tempo. Se alcune operazioni sono stranamente lente, è probabile che si tratti di un problema di codice, se non dipende dalle personalizzazioni puoi aprire un ticket [qui](https://www.odoo.com/help).

## Rami di staging¶

Rami di staging aggiuntivi permettono di sviluppare e testare più funzionalità allo stesso tempo. Se ne aggiungi uno, verrà sincronizzato automaticamente con l’abbonamento.

## Attivazione¶

Mostra lo stato di attivazione del progetto. È possibile modificare il codice di attivazione del progetto se necessario.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/odoo_sh/getting_started/settings.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](online-editor.html "Editor online") |
  * [precedente](status.html "Stato") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Impostazioni


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
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