# Editor online — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](first_module.html "Il primo modulo") |
  * [precedente](settings.html "Impostazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Editor online



# Editor online¶

## Panoramica¶

L’editor online consente di modificare il codice fonte dei build da un browser. Inoltre, offre la possibilità di aprire terminali, console Python, console Odoo Shell e [Notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html).

È possibile accedere all’editor di un build attraverso [le schede rami](branches.html#odoosh-gettingstarted-branches-tabs), [il menu a discesa dei build](builds.html#odoosh-gettingstarted-builds-dropdown-menu) oppure aggiungendo _/odoo-sh/editor_ al nome di dominio del build (e.g. _https://odoo-addons-master-1.dev.odoo.com/odoo-sh/editor_).

## Modificare il codice sorgente¶

La cartella di lavoro è composta dalle seguenti cartelle:
    
    
    .
    ├── home
    │    └── odoo
    │         ├── src
    │         │    ├── odoo                Odoo Community source code
    │         │    │    └── odoo-bin       Odoo server executable
    │         │    ├── enterprise          Odoo Enterprise source code
    │         │    ├── themes              Odoo Themes source code
    │         │    └── user                Your repository branch source code
    │         ├── data
    │         │    ├── filestore           database attachments, as well as the files of binary fields
    │         │    └── sessions            visitors and users sessions
    │         └── logs
    │              ├── install.log         Database installation logs
    │              ├── odoo.log            Running server logs
    │              ├── update.log          Database updates logs
    │              └── pip.log             Python packages installation logs
    

È possibile modificare il codice sorgente (file sotto _/src_) nei build di sviluppo e staging.

Nota

Le modifiche non verranno propagate in un nuovo build, è necessario eseguire il commit nel codice sorgente se vuoi che restino attive.

Per i build di produzione, il codice sorgente è di sola lettura, perché l’applicazione di cambiamenti locali su un server di produzione non è una buona pratica.

  * Il codice sorgente dell’archivio Github si trova sotto _/src/user_ ;

  * Il codice sorgente di Odoo si trova sotto

    * _/src/odoo_ ([odoo/odoo](https://github.com/odoo/odoo)),

    * _/src/enterprise_ ([odoo/enterprise](https://github.com/odoo/enterprise)),

    * _/src/themes_ ([odoo/design-themes](https://github.com/odoo/design-themes)).




Per aprire un file nell’editor, fai doppio clic su di esso nel pannello di visualizzazione dei file a sinistra.

In seguito, è possibile iniziare ad apportare modifiche. Puoi salvarle grazie al menu File ‣ Save .. File oppure tramite la scelta rapida da tastiera ``Ctrl`+`S``.

Se salvi un file Python sotto il percorso dei componenti aggiuntivi del server Odoo, Odoo lo individuerà e caricherà automaticamente in modo che le tue modifiche siano visibili immediatamente, senza dover riavviare il server manualmente.

Tuttavia, se la modifica corrisponde a dati salvati nel database, come l’etichetta di un campo o una vista, è necessario aggiornare il modulo corrispondente per applicare la modifica. È possibile aggiornare il modulo del file attualmente aperto utilizzando il menu Odoo ‣ Aggiorna modulo corrente. Nota che il file considerato attualmente aperto è il file evidenziato nell’editor di testo non il file evidenziato nel navigatore.

È anche possibile aprire un terminale ed eseguire il comando:
    
    
    $ odoo-bin -u <comma-separated module names> --stop-after-init
    

## Eseguire il commit e applicare le modifiche¶

Hai la possibilità di eseguire il commit e applicare le modifiche nell’archivio Github.

  * Apri un terminale (File ‣ New ‣ Terminal);

  * modifica la cartella in _~/src/user_ utilizzando `cd ~/src/user`;

  * prepara il commit per le modifiche `git add`;

  * esegui il commit delle modifiche utilizzando `git commit`;

  * esegui il push delle modifiche utilizzando `git push https HEAD:<branch>`.




Per quanto riguarda l’ultimo comando,

  * _https_ è il nome del tuo archivio Github remoto _HTTPS_ Github (ad es. <https://github.com/username/repository.git>);

  * HEAD è il riferimento all’ultima versione di cui è stato eseguito il commit;

  * <branch> deve essere sostituito dal nome del ramo per il quale vuoi eseguire il push delle modifiche, molto probabilmente il ramo corrente, se si lavora in un build di sviluppo.




Nota

L’SSH Github remoto non viene utilizzato perché la chiave privata SSH non è ospitata nei contenitori del tuo build (per ovvi motivi di sicurezza) tantomento inviata tramite un agente (in quanto puoi accedere all’editor attraverso un browser web) e quindi non è possibile autenticarsi su Github utilizzando SSH. È necessario utilizzare l’HTTPS remoto dell’archivio Github per eseguire il push delle modifiche, il quale viene aggiunto automaticamente e nominato _https_ nei Git remoti. Ti verrà richiesto di inserire username e password Github. Se hai attivato l’autenticazione a due fattori su Github, puoi creare un [token personale di accesso](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/) e utilizzarlo come password. È sufficiente garantire l’autorizzazione `repo`.

Nota

La cartella sorgente Git _~/src/user_ non viene spuntata per un ramo ma per una revisione distaccata: questo accade perché i build lavorano su revisioni specifiche invece che rami. In altre parole, significa che puoi avere più build nello stesso ramo ma su revisioni diverse.

Una volta che le modifiche sono state applicate, secondo il [comportamento del push del ramo](branches.html#odoosh-gettingstarted-branches-tabs-settings), potrebbe essere creato un nuovo build. Puoi continuare a lavorare nell’editor dal quale hai eseguito il push, in quanto avrà la stessa revisione del nuovo build appena creato ma assicurati sempre di essere nell’editor di un build che usa l’ultima revisione del tuo ramo.

## Console¶

È possibile aprire console Python che sono [shell interattive IPython](https://ipython.readthedocs.io/en/stable/interactive/tutorial.html). Uno degli aspetti più interessanti dell’utilizzo di una console Python rispetto ad una shell IPython in un terminale è la [ricchezza delle possibilità di visualizzazione](https://ipython.readthedocs.io/en/stable/config/integrating.html#rich-display).

Ad esempio, puoi visualizzare le celle di un file CSV utilizzando [pandas](https://pandas.pydata.org/pandas-docs/stable/tutorials.html).

Puoi anche aprire una console Odoo Shell per giocare con i metodi del registro e del modello del database. È possibile anche leggere o scrivere direttamente record.

Avvertimento

In una console Odoo, le transazioni vengono effettuate automaticamente. Ad esempio, ciò significa che le modifiche ai record vengono applicate in modo efficace al database. Se modifichi il nome di un utente, questo viene modificato anche nel database. Di conseguenza, devi usare con attenzione le console Odoo nei database di produzione.

Puoi utilizzare _env_ per richiamare i modelli del registro del database, ad es. `env['res.users']`.
    
    
    env['res.users'].search_read([], ['name', 'email', 'login'])
    [{'id': 2,
    'login': 'admin',
    'name': 'Administrator',
    'email': 'admin@example.com'}]
    

La classe `Pretty` consente di visualizzare facilmente elenchi e dizionari in modo carino usando [ricchezza di visualizzazione](https://ipython.readthedocs.io/en/stable/config/integrating.html#rich-display) citata in precedenza.

È anche possibile utilizzare [pandas](https://pandas.pydata.org/pandas-docs/stable/tutorials.html) per visualizzare grafici.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/odoo_sh/getting_started/online-editor.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](first_module.html "Il primo modulo") |
  * [precedente](settings.html "Impostazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Editor online


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