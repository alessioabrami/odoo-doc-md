# Il primo modulo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzate") |
  * [precedente](online-editor.html "Editor online") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Il primo modulo



# Il primo modulo¶

## Panoramica¶

Il presente capitolo ti aiuterà a creare il primo modulo Odoo per poi distribuirlo nel progetto Odoo.sh desiderato.

Il tutorial richiede che [tu abbia creato un progetto su Odoo.sh](create.html#odoosh-gettingstarted-create) e la conoscenza dell’URL dell’archivio Github.

Verrà spiegato l’utilizzo base di Git e Github.

Si formulano le seguenti ipotesi:

  * _~/src_ è la cartella dove sono memorizzate tutti gli archivi Git collegati ai tuoi progetti Odoo;

  * _odoo_ è l’utente Github;

  * _odoo-addons_ è l’archivio Github;

  * _feature-1_ è il nome del ramo di sviluppo;

  * _master_ è il nome del ramo di produzione;

  * _my_module_ è il nome del modulo.




Sostituisci i valori elencati con valori a tua scelta.

## Creare il ramo di sviluppo¶

### Da Odoo.sh¶

Nella vista con i rami:

  * fai clic su `+` accanto alla fase di sviluppo;

  * scegli il ramo _master_ nel campo _Fork_ ;

  * scrivi _feature-1_ nel campo _To_.




Una volta che il build è stato creato, puoi accedere all’editor e caricare la cartella _~/src/user_ per accedere al codice del ramo di sviluppo.

### Dal computer¶

Clona l’archivio Github sul tuo computer:
    
    
    $ mkdir ~/src
    $ cd ~/src
    $ git clone https://github.com/odoo/odoo-addons.git
    $ cd ~/src/odoo-addons
    

Crea un nuovo ramo:
    
    
    $ git checkout -b feature-1 master
    

## Creare la struttura del modulo¶

### Eseguire lo scaffolding del modulo¶

Anche se non è necessario, lo scaffolding evita il fastidio di dover configurare la struttura di base dei moduli Odoo. È possibile eseguire lo scaffolding di un nuovo modulo utilizzando l’eseguibile _odoo-bin_.

Dall’editor Odoo.sh, in un terminale:
    
    
    $ odoo-bin scaffold my_module ~/src/user/
    

Oppure dal computer, se hai [installato Odoo](../../on_premise/source.html):
    
    
    $ ./odoo-bin scaffold my_module ~/src/odoo-addons/
    

Se non vuoi installare Odoo sul tuo computer, è possibile [`scaricare il seguente modello di struttura del modulo`](../../../_downloads/b7f3a4243ae7f3166cd5c4d23a256739/my_module.zip) dove potrai sostituire ogni occorrenza di _my_module_ con un nome a tua scelta.

Verrà creata la seguente struttura:
    
    
    my_module
    ├── __init__.py
    ├── __manifest__.py
    ├── controllers
    │   ├── __init__.py
    │   └── controllers.py
    ├── demo
    │   └── demo.xml
    ├── models
    │   ├── __init__.py
    │   └── models.py
    ├── security
    │   └── ir.model.access.csv
    └── views
        ├── templates.xml
        └── views.xml
    

Avvertimento

Non utilizzare caratteri speciali diversi dal trattino basso ( _ ) o il segno meno (-) per il nome del modulo. Il nome viene utilizzato per le classi Python del tuo modulo e hanno nomi con caratteri speciali diversi dal trattino basso che non è valido in Python.

Elimina i commenti dal contenuto dei file:

  * _models/models.py_ , un esempio di modello con i rispettivi campi;

  * _views/views.xml_ , un albero e una vista modulo con i menu che li aprono;

  * _demo/demo.xml_ , record demo per il modello di esempio in alto;

  * _controllers/controllers.py_ , un esempio di controller che implementa alcuni percorsi;

  * _views/templates.xml_ , due esempi di viste qweb utilizzate dai percorsi del controller di cui sopra;

  * ___manifest__.py_ , il manifesto del tuo modulo che include il titolo, la descrizione e i file dati da caricare. Devi solo eliminare i commenti dal file con i dati relativi alla lista di controllo degli accessi:
        
        # 'security/ir.model.access.csv',
        




### Manuale¶

Se vuoi creare la struttura dei moduli manualmente, puoi seguire il tutorial [Server framework 101](../../../developer/tutorials/server_framework_101.html) per comprendere la struttura di un modulo e il contenuto di ogni file.

## Eseguire il push del ramo di sviluppo¶

Fissa le modifiche di cui eseguire il commit
    
    
    $ git add my_module
    

Esegui il commit delle modifiche
    
    
    $ git commit -m "My first module"
    

Esegui il push delle modifiche nell’archivio remoto

Da un terminale dell’editor Odoo.sh:
    
    
    $ git push https HEAD:feature-1
    

Il comando in alto viene spiegato nella sezione [Eseguire il commit e applicare le modifiche](online-editor.html#odoosh-gettingstarted-online-editor-push) del capitolo sull” [Editor online](online-editor.html#odoosh-gettingstarted-online-editor) che include la spiegazione riguardo i campi da riempire come nome utente e password e cosa fare se si utilizza l’autenticazione a due fattori.

Oppure dal terminale del computer:
    
    
    $ git push -u origin feature-1
    

È necessario specificare _-u origin feature-1_ solo per il primo push. Da questo momento, per applicare le modifiche future dal tuo computer, puoi utilizzare semplicemente
    
    
    $ git push
    

## Testare il proprio modulo¶

Il ramo dovrebbe apparire nei rami di sviluppo del tuo progetto.

Nella vista rami del tuo progetto, puoi fare clic sul nome del ramo nel pannello di navigazione a sinistra per accedere alla cronologia.

Qui è possibile visualizzare i cambiamenti appena applicatim compresi i commenti configurati. Una volta che il database è pronto, è possibile accedervi facendo clic sul pulsante _Collegati_.

Se il tuo progetto Odoo.sh è configurato per l’installazione automatica del modulo, lo visualizzerai direttamente tra le app del database. Altrimenti, sarà disponibile tra le app da installare.

In seguito, puoi giocare con il modulo, creare nuovi record e provare funzionalità e pulsanti.

## Testare con i dati di produzione¶

È necessario avere a disposizione un database di produzione per questa fase. È possibile crearne uno.

Una volta testato il modulo in un build di sviluppo con dati demo, se sei pronto puoi testarlo con i dati di produzione utilizzando un ramo di staging.

Le tue opzioni:

  * rendere il ramo di sviluppo un ramo di staging, trascinandolo e rilasciandolo nel titolo della sezione _staging_ ;

  * unire il ramo con un ramo di staging esistente, trascinandolo e rilasciandolo nel ramo di staging desiderato.




Inoltre, puoi anche utilizzare il comando `git merge` per unire i rami.

Questo porterà alla creazione di un nuovo build di staging che duplicherà il database di produzione e lo farà funzionare utilizzando un server aggiornato con le ultime modifiche del ramo.

Una volta che il database è pronto, puoi eseguire l’accesso utilizzando il pulsante _Collegati_.

### Installare il modulo¶

Il tuo modulo non verrà installato automaticamente, è necessario installarlo dal menu delle app. In realtà, lo scopo del build di staging è testare il comportamento delle modifiche perché applicate alla produzione e nella tua produzione non vuoi che un modulo venga installato automaticamente ma su richiesta.

Il tuo modulo potrebbe non apparire direttamente tra le app da installare e per questo è necessario prima aggiornare l’elenco:

  * attivare la [modalità sviluppatore](../../../applications/general/developer_mode.html#developer-mode);

  * nel menu delle app, fai clic sul pulsante _Aggiorna elenco app_ ;

  * nella finestra di dialogo che appare, fai clic sul pulsante _Aggiorna_ ;




In seguito, il modulo apparirà nell’elenco di app disponibili.

## Distribuire in produzione¶

Una volta testato il modulo con i dati di produzione in un ramo di staging e constatato il corretto funzionamento, puoi unire il tuo ramo a quello di produzione.

Trascina e rilascia il ramo di staging nel ramo di produzione.

Inoltre, puoi anche utilizzare il comando `git merge` per unire i rami.

L’azione unirà le ultime modifiche al ramo di staging nel ramo di produzione e aggiornerà il server di produzione con le ultime modifiche.

Una volta che il database è pronto, puoi eseguire l’accesso utilizzando il pulsante _Collegati_.

### Installare il modulo¶

Il tuo modulo non verrà installato automaticamente, devi installarlo manualmente come spiegato nella sezione in alto riguardo l’installazione del modulo in database di staging.

## Aggiungere una modifica¶

La sezione spiega come aggiungere una modifica al modulo aggiungendo un nuovo campo in un modello e distribuirlo.

Dall’edito di Odoo.sh,
    

  * sfoglia la cartella del modulo _~/src/user/my_module_ ;

  * in seguito, apri il file _models/models.py_.



Oppure, dal computer:
    

  * utilizza il browser di file a tua scelta per sfogliare la cartella del modulo _~/src/odoo-addons/my_module_ ;

  * in seguito, apri il file _models/models.py_ utilizzando l’editor a tua scelta come _Atom_ , _Sublime Text_ , _PyCharm_ , _vim_ , …




In seguito, dopo il campo descrizione
    
    
    description = fields.Text()
    

Aggiungi un campo Data/Ora
    
    
    start_datetime = fields.Datetime('Start time', default=lambda self: fields.Datetime.now())
    

In seguito, apri il file _views/views.xml_.

Dopo
    
    
    <field name="value2"/>
    

Aggiungi
    
    
    <field name="start_datetime"/>
    

Queste modifiche alterano la struttura del database aggiungendo una colonna in una tabella e modificando la vista memorizzata nel database.

Al fine di applicare le modifiche a database come il tuo database di produzione, è necessario aggiornare il modulo.

Se vuoi che l’aggiornamento venga eseguito automaticamente dalla piattaforma Odoo.sh quando applichi le modifiche, è necessario aumentare la versione del modulo nel manifesto corrispondente.

Apri il modulo del manifesto ___manifest__.py_.

Sostituisci
    
    
    'version': '0.1',
    

con
    
    
    'version': '0.2',
    

La piattaforma individuerà l’aggiornamento della versione e attiverà l’aggiornamento del modulo a seguito della distribuzione della nuova revisione.

Sfoglia la cartella Git.

In seguito, da un terminale Odoo.sh:
    
    
    $ cd ~/src/user/
    

Oppure dal terminale del computer:
    
    
    $ cd ~/src/odoo-addons/
    

In seguito, fissa le modifiche di cui eseguire il commit
    
    
    $ git add my_module
    

Esegui il commit delle modifiche
    
    
    $ git commit -m "[ADD] my_module: add the start_datetime field to the model my_module.my_module"
    

Applica le modifiche:

Da un terminale Odoo.sh:
    
    
    $ git push https HEAD:feature-1
    

Oppure dal terminale del computer:
    
    
    $ git push
    

La piattaforma creerà un nuovo build per il ramo _feature-1_.

Una volta testate le modifiche è possibile unirle nel ramo di produzione, ad esempio trascinando e rilasciando il ramo nel ramo di produzione tramite l’interfaccia Odoo.sh. Man mano che aumenti la versione del modulo nel manifesto, la piattaforma aggiornerà automaticamente il modulo e il tuo nuovo campo sarà subito disponibile. Altrimenti, puoi aggiornare manualmente il modulo dall’elenco delle app.

## Utilizzare una libreria Python esterna¶

Se vuoi utilizzare una libreria Python esterna, non installata per impostazione predefinita, puoi definire un file _requirements.txt_ che elenca le librerie esterna da cui dipendono i tuoi moduli.

Nota

  * Non è possibile installare o aggiornare pacchetti di sistema su un database Odoo.sh (ad es. pacchetti apt). Tuttavia, in condizioni specifiche, i pacchetti possono essere valutati per l’installazione. Questo si applica anche a _moduli Python_ che richiedono pacchetti di sistema per la compilazione e **moduli Odoo di terze parti**.

  * Le **estensioni PostgreSQL** non sono supportate su Odoo.sh.

  * Per maggiori informazioni, consulta le [FAQ](https://www.odoo.sh/faq#install_dependencies).




La piattaforma utilizzerà il file per installare automaticamente le librerie Python di cui il tuo progetto ha bisogno.

La funzionalità viene spiegata nella seguente sezione utilizzando la `libreria Unidecode<https://pypi.python.org/pypi/Unidecode>`_ nel tuo modulo.

Crea un file _requirements.txt_ nella cartella radice del registro

Dall’editor di Odoo.sh, crea e apri il file ~/src/user/requirements.txt.

Oppure, dal tuo computer, crea e apri il file ~/src/odoo-addons/requirements.txt.

Aggiungi
    
    
    unidecode
    

In seguito, utilizza la libreria nel modulo per eliminare accenti dai caratteri nel campo nome del modello ad esempio.

Apri il file _models/models.py_.

Prima
    
    
    from odoo import models, fields, api
    

Aggiungi
    
    
    from unidecode import unidecode
    

Dopo
    
    
    start_datetime = fields.Datetime('Start time', default=lambda self: fields.Datetime.now())
    

Aggiungi
    
    
    @api.model
    def create(self, values):
        if 'name' in values:
            values['name'] = unidecode(values['name'])
        return super(my_module, self).create(values)
    
    def write(self, values):
        if 'name' in values:
            values['name'] = unidecode(values['name'])
        return super(my_module, self).write(values)
    

L’aggiunta di una dipendenza Python richiede una versione del modulo più grande per far sì che la piattaforma possa installarlo.

Modifica il manifesto del modulo ___manifest__.py_

Sostituisci
    
    
    'version': '0.2',
    

con
    
    
    'version': '0.3',
    

Fissa ed esegui il commit delle modifiche:
    
    
    $ git add requirements.txt
    $ git add my_module
    $ git commit -m "[IMP] my_module: automatically remove special chars in my_module.my_module name field"
    

In seguito, applica le modifiche:

In un terminale Odoo.sh:
    
    
    $ git push https HEAD:feature-1
    

Nel terminale del tuo computer:
    
    
    $ git push
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/odoo_sh/getting_started/first_module.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzate") |
  * [precedente](online-editor.html "Editor online") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Il primo modulo


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