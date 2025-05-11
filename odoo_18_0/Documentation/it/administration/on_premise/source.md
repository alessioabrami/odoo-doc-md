# Installare dalla sorgente — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](update.html "Aggiornamenti per correzione bug") |
  * [precedente](packages.html "Programmi di installazione") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Installare dalla sorgente



# Installare dalla sorgente¶

L” «installazione» dalla sorgente non consiste nell’installare Odoo ma nell’eseguirlo direttamente dal codice sorgente.

L’utilizzo del codice sorgente di Odoo può essere più conveniente per gli sviluppatori di moduli in quanto è accessibile in modo più semplice rispetto ai programmi di installazione.

Questa pratica consente di avviare e arrestare Odoo in modo più flessibile ed esplicito rispetto ai servizi configurati dai programmi di installazione. Inoltre, consente di sovrascrivere impostazioni utilizzando i [parametri della riga di comando](../../developer/reference/cli.html#reference-cmdline) senza la necessità di modificare il file di configurazione.

Infine, fornisce grande controllo sulla configurazione di sistema e consente di mantenere (ed eseguire) più facilmente varie versioni di Odoo, l’una accanto all’altra.

## Recuperare i codici sorgente¶

Esistono due modi per ottenere il codice sorgente di Odoo: come **archivio** ZIP oppure attraverso **Git**.

### Archivia¶

Edizione Community:

  * [Pagina download Odoo](https://www.odoo.com/page/download)

  * [Repository GitHub Community](https://github.com/odoo/odoo)

  * [Server nightly](https://nightly.odoo.com/)




Edizione Enterprise:

  * [Pagina download Odoo](https://www.odoo.com/page/download)

  * [Repository GitHub Enterprise](https://github.com/odoo/enterprise)




### Git¶

Nota

È necessario aver installato [Git](https://git-scm.com/) ed è consigliato avere conoscenze di base dei comandi Git per procedere.

Per clonare una repository Git, scegli tra la clonazione con HTTPS o SSH. Nella maggior parte dei casi, la migliore soluzione è HTTPS. Tuttavia, scegli SSH per contribuire al codice sorgente di Odoo oppure seguendo il [tutorial per developer per iniziare](../../developer/tutorials/server_framework_101.html).

LinuxWindowsMac OS

Clone with HTTPSClone with SSH
    
    
    $ git clone https://github.com/odoo/odoo.git
    $ git clone https://github.com/odoo/enterprise.git
    
    
    
    $ git clone git@github.com:odoo/odoo.git
    $ git clone git@github.com:odoo/enterprise.git
    

Clone with HTTPSClone with SSH
    
    
    C:\> git clone https://github.com/odoo/odoo.git
    C:\> git clone https://github.com/odoo/enterprise.git
    
    
    
    C:\> git clone git@github.com:odoo/odoo.git
    C:\> git clone git@github.com:odoo/enterprise.git
    

Clone with HTTPSClone with SSH
    
    
    $ git clone https://github.com/odoo/odoo.git
    $ git clone https://github.com/odoo/enterprise.git
    
    
    
    $ git clone git@github.com:odoo/odoo.git
    $ git clone git@github.com:odoo/enterprise.git
    

Nota

**La repository git Enterprise non contiene il codice fonte Odoo completo**. Si tratta di un insieme di componenti aggiuntivi extra. Il codice server principale si trova nella versione Community. Eseguire la versione Enterprise significa eseguire il server dalla versione Community con l’opzione `addons-path` impostata per la cartella con la versione Enterprise. È necessario clonare sia la repository Community che Enterprise per far sì che l’installazione di Odoo Enterprise funzioni.

## Preparazione¶

### Python¶

Odoo richiede **Python 3.10** o versioni superiori per funzionare.

Cambiato nella versione 17: Requisito minimo aggiornato da Python 3.7 a Python 3.10.

LinuxWindowsMac OS

Utilizza un sistema di gestione pacchetti per scaricare e installare Python 3 se necessario.

[Scarica l’ultima versione di Python 3](https://www.python.org/downloads/windows/) e installala.

Durante l’installazione, seleziona **Aggiungi Python 3 al PERCORSO** per poi fare clic su **Personalizza installazione** e assicurati che il campo **pip** sia spuntato.

Utilizza un sistema di gestione pacchetti ([Homebrew](https://brew.sh/), [MacPorts](https://www.macports.org/)) per scaricare e installare Python 3 se necessario.

Nota

Se Python 3 è già installato, assicurati che la versione sia pari a 3.10 o superiori, in quanto le versioni precedenti non sono compatibili con Odoo.

LinuxWindowsMac OS
    
    
    $ python3 --version
    
    
    
    C:\> python --version
    
    
    
    $ python3 --version
    

Verifica che [pip](https://pip.pypa.io/) sia stato installato per questa versione.

LinuxWindowsMac OS
    
    
    $ pip3 --version
    
    
    
    C:\> pip --version
    
    
    
    $ pip3 --version
    

### PostgreSQL¶

Odoo utilizza PostgreSQL come sistema di gestione dei database.

LinuxWindowsMac OS

Utilizza un sistema di gestione pacchetti per scaricare e installare PostgreSQL (versioni supportate: 12.0 o superiori). È possibile farlo eseguendo il comando:
    
    
    $ sudo apt install postgresql postgresql-client
    

[Scarica PostgreSQL](https://www.postgresql.org/download/windows) (versioni supportate: 12.0 o superiori) e installalo.

Utilizza [Postgres.app](https://postgresapp.com/) per scaricare e installare PostgreSQL (versioni supportate: 12.0 o superiori).

Suggerimento

Per far sì che gli strumenti della riga di comando legati a Postgres.app siano disponibili, assicurati di configurare la variabile `$PATH` seguendo le [istruzioni relative agi strumenti CLI Postgres.app](https://postgresapp.com/Documentation/cli-tools.html).

Per impostazione predefinita, l’unico utente è `postgres`. Odoo non permette di connettersi come `postgres` quindi devi creare un nuovo utente PostgreSQL.

LinuxWindowsMac OS
    
    
    $ sudo -u postgres createuser -d -R -S $USER
    $ createdb $USER
    

Nota

Dato che l’utente PostgreSQL ha lo stesso nome del login Unix, è possibile collegare il database senza una password.

  1. Aggiungi la directory PostgreSQL’s `bin` (per impostazione predefinita: `C:\Program Files\PostgreSQL\<version>\bin`) al `PERCORSO`.

  2. Crea un utente postgres con una password utilizzando il gui admin pg:

     1. Apri **pgAdmin**.

     2. Fai doppio clic sul server per creare una connessione.

     3. Seleziona Oggetto ‣ Crea ‣ Ruolo accesso/gruppo.

     4. Inserisci il nome utente nel campo «Nome ruolo» (ad es., `odoo`).

     5. Apri la scheda **Definizione** , inserisci una password (ad es., `odoo`) e fai clic su **Salva**.

     6. Apri la scheda **Privilegi** e imposta **Può accedere?** su `Sì` e **Creare database?** su `SÌ`.



    
    
    $ sudo -u postgres createuser -d -R -S $USER
    $ createdb $USER
    

Nota

Dato che l’utente PostgreSQL ha lo stesso nome del login Unix, è possibile collegare il database senza una password.

### Dipendenze¶

LinuxWindowsMac OS

L’utilizzo di **pacchetti di distribuzione** è il metodo preferito per installare dipendenze. In alternativa, installa le dipendenze Python con **pip**.

Debian/UbuntuInstall with pip

Su Debian/Ubuntu, puoi installare i pacchetti richiesti tramite i seguenti comandi:
    
    
    $ cd odoo #CommunityPath
    $ sudo ./setup/debinstall.sh
    

Lo script `setup/debinstall.sh` analizzerà il file [debian/control](https://github.com/odoo/odoo/blob/18.0/debian/control) e installerà i pacchetti trovati.

Avvertimento

L’utilizzo di pip potrebbe comportare problemi di sicurezza e dipendente non funzionati. Utilizzalo solo se sai cosa stai facendo.

Dato che alcuni pacchetti Python richiedono una fase di compilazione, è necessario installare librerie di sistema.

Su Debian/Ubuntu, puoi installare le librerie richieste tramite il comando seguente:
    
    
    $ sudo apt install python3-pip libldap2-dev libpq-dev libsasl2-dev
    

Le dipendenze Odoo sono elencate nel file `requirements.txt` situato alla radice della directory Odoo Community.

Nota

I pacchetti Python nel file `requirements.txt` si basano sulla versione stabile/LTS Debian/Ubuntu corrispondente al momento del rilascio di Odoo. Ad esempio, per Odoo 15.0, la versione del pacchetto `python3-babel` è la 2.8.0 in Debian Bullseye e la 2.6.0 in Ubuntu Focal. La versione più bassa viene scelta nel file `requirements.txt`.

Suggerimento

È preferibile non combinare pacchetti del modulo Python fra varie istanze di Odoo o con il sistema. Tuttavia, è possibile utilizzare [virtualenv](https://pypi.org/project/virtualenv/) per creare ambienti Python isolati.

Apri il percorso dell’installazione di Odoo Community (`CommunityPath`) ed esegui **pip** sul file dei requisiti per installare gli stessi per l’utente corrente.
    
    
    $ cd /CommunityPath
    $ pip install -r requirements.txt
    

Prima di installare le dipendenze, scarica e installa gli [Strumenti Build per Visual Studio](https://visualstudio.microsoft.com/downloads/). Seleziona **C++ build tools** nella scheda **Workloads** e installali quando richiesto.

Le dipendenze Odoo sono elencate nel file `requirements.txt` situato alla radice della directory Odoo Community.

> Suggerimento
> 
> È preferibile non combinare pacchetti del modulo Python fra varie istanze di Odoo o con il sistema. Tuttavia, è possibile utilizzare [virtualenv](https://pypi.org/project/virtualenv/) per creare ambienti Python isolati.

Apri il percorso dell’installazione di Odoo Community (`CommunityPath`) ed esegui **pip** sul file dei requisiti in un terminale **con privilegi di amministratore** :
    
    
    C:\> cd \CommunityPath
    C:\> pip install setuptools wheel
    C:\> pip install -r requirements.txt
    

Le dipendenze Odoo sono elencate nel file `requirements.txt` situato alla radice della directory Odoo Community.

> Suggerimento
> 
> È preferibile non combinare pacchetti del modulo Python fra varie istanze di Odoo o con il sistema. Tuttavia, è possibile utilizzare [virtualenv](https://pypi.org/project/virtualenv/) per creare ambienti Python isolati.

Apri il percorso dell’installazione di Odoo Community (`CommunityPath`) ed esegui **pip** sul file dei requisiti:
    
    
    $ cd /CommunityPath
    $ pip3 install setuptools wheel
    $ pip3 install -r requirements.txt
    

Avvertimento

Le dipendenze non-Python devono essere installate tramite un sistema di gestione dei pacchetti ([Homebrew](https://brew.sh/), [MacPorts](https://www.macports.org/)).

  1. Scarica e installa gli **Strumenti riga di comando** :
         
         $ xcode-select --install
         

  2. Utilizza il sistema di gestione dei pacchetti per installare dipendenze non-Python.




Nota

Per le lingue che utilizza una **interfaccia da destra a sinistra** (come l’arabo o l’ebraico), è richiesto il pacchetto `rtlcss`-

LinuxWindowsMac OS

  1. Scarica e installa **nodejs** e **npm** tramite sistema di gestione pacchetti.

  2. Installa `rtlcss`:
         
         $ sudo npm install -g rtlcss
         




  1. Scarica e installa [nodejs](https://nodejs.org/en/download).

  2. Installa `rtlcss`:
         
         C:\> npm install -g rtlcss
         

  3. Modifica la variabile `PATH` dell’ambiente sistema per aggiungere la cartella dove è situtato `rtlcss.cmd` (tipicamente: `C:\Users\<user>\AppData\Roaming\npm\`).




  1. Scarica e installa **nodejs** tramite gestione pacchetti ([Homebrew](https://brew.sh/), [MacPorts](https://www.macports.org/)).

  2. Installa `rtlcss`:
         
         $ sudo npm install -g rtlcss
         




Avvertimento

`wkhtmltopdf` non è installato tramite **pip** e deve essere installato manualmente nella [versione 0.12.6](https://github.com/wkhtmltopdf/packaging/releases/tag/0.12.6.1-3) per far sì che supporti intestazioni e pié di pagina. Consulta la [wiki relativa a wkhtmltopdf](https://github.com/odoo/odoo/wiki/Wkhtmltopdf) per maggiori dettagli sulle varie versioni.

## Eseguire Odoo¶

Una volta che tutte le dipendenze sono state configurate, Odoo può essere avviato eseguendo `odoo-bin`, l’interfaccia della riga di comando del server. Si trova alla radice della directory di Odoo Community.

Per configurare il server, specifica gli [argomenti della riga di comando](../../developer/reference/cli.html#reference-cmdline-server) oppure un [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config).

Suggerimento

Per l’edizione Enterprise, aggiungi il percorso ai componenti aggiuntivi `enterprise` nell’argomento `addons-path`. Nota che per caricare correttamente i componenti aggiuntivi, è necessario che il percorso si trovi prima di altri percorsi in `addons-path`.

Le configurazioni comuni necessarie sono:

  * Utente e password PostgreSQL.

  * Percorsi personalizzati dei componenti aggiuntivi, oltre a quelli predefiniti, per caricare moduli personalizzati.




Uno dei modi tipici per avviare il server sarebbe:

LinuxWindowsMac OS
    
    
    $ cd /CommunityPath
    $ python3 odoo-bin --addons-path=addons -d mydb
    

Dove `CommunityPath` è il percorso dell’installazione di Odoo Community installation e `mydb` è il nome del database PostgreSQL.
    
    
    C:\> cd CommunityPath/
    C:\> python odoo-bin -r dbuser -w dbpassword --addons-path=addons -d mydb
    

Dove `CommunityPath` è il percorso dell’installazione Odoo Community, `dbuser` è l’accesso PostgreSQL, `dbpassword` rappresenta la password PostgreSQL e `mydb` è il nome del database PostgreSQL.
    
    
    $ cd /CommunityPath
    $ python3 odoo-bin --addons-path=addons -d mydb
    

Dove `CommunityPath` è il percorso dell’installazione di Odoo Community installation e `mydb` è il nome del database PostgreSQL.

Dopo che il server è stato avviato (il registro INFO `odoo.modules.loading: Modules loaded.` è stampato), apri [http://localhost:8069](http://localhost:8069/) in un browser web e accedi al database Odoo con l’account amministratore di base: usa `admin` come e-mail e di nuovo `admin` come password.

Suggerimento

  * Da qui, crea e gestisci nuovi [utenti](../../applications/general/users.html).

  * L’account utente utilizzato per eseguire l’accesso all’interfaccia web Odoo è diverso dall’argomento CLI [`--db_user`](../../developer/reference/cli.html#cmdoption-odoo-bin-r).




Vedi anche

[Elenco degli argomenti CLI per odoo-bin](../../developer/reference/cli.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/administration/on_premise/source.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](update.html "Aggiornamenti per correzione bug") |
  * [precedente](packages.html "Programmi di installazione") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Installare dalla sorgente


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