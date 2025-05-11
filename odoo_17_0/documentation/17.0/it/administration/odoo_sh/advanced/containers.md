# Contenitori — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](submodules.html "Moduli secondarii") |
  * [precedente](../advanced.html "Avanzate") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Avanzate](../advanced.html) »
  * Contenitori



# Contenitori¶

## Panoramica¶

Ogni build è isolato nel proprio contenitore (contenitore spazio nome Linux).

La base è un sistema Ubuntu dove tutte le dipendenze richieste da Odoo, così come pacchetti comuni utili, vengono installate.

Se il tuo progetto richiede dipendenze Python aggiuntive o versioni più recenti, puoi definire un file `requirements.txt` nella radice dei rami che le elencano. La piattaforma si occuperà di installare le dipendenze nei contenitori. La documentazione relativa ai [specificatori dei requisiti pip](https://pip.pypa.io/en/stable/reference/pip_install/#requirement-specifiers) può aiutarti a redigere un file `requirements.txt`. Per avere un esempio concreto, controlla il file [requirements.txt di Odoo](https://github.com/odoo/odoo/blob/17.0/requirements.txt).

I file `requirements.txt` dei moduli secondari vengono considerati allo stesso modo. La piattaforma cerca i file `requirements.txt` in ogni cartella contenente moduli Odoo: non nella cartella del modulo stesso ma nella cartella padre.

## Struttura della cartella¶

Dato che i contenitori si basano su Ubuntu, la struttura della cartella segue lo standard della gerarchia del filesystem di linux. [La panoramica dell’albero del filesystem di Ubuntu](https://help.ubuntu.com/community/LinuxFilesystemTreeOverview#Main_directories) spiega le principali cartelle.

Di seguito, le cartello Odoo.sh pertinenti:
    
    
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
    └── usr
         ├── lib
         │    ├── python2.7
         │         └── dist-packages       Python 2.7 standard libraries
         │    ├── python3
         │         └── dist-packages       Python 3 standard libraries
         │    └── python3.5
         │         └── dist-packages       Python 3.5 standard libraries
         ├── local
         │    └── lib
         │         ├── python2.7
         │         │    └── dist-packages  Python 2.7 third-party libraries
         │         └── python3.5
         │              └── dist-packages  Python 3.5 third-party libraries
         └── usr
              └── bin
                   ├── python2.7           Python 2.7 executable
                   └── python3.5           Python 3.5 executable
    

Sia Python 2.7 che 3.5 vengono installate nei contenitori. Tuttavia:

  * Se il tuo progetto è configurato per utilizzare Odoo 10.0, il server Odoo funzionerà con Python 2.7.

  * Se il tuo progetto è configurato per utilizzare Odoo 11.0, il server Odoo funzionerà con Python 3.5.




## Shell del database¶

Mentre accedi al contenitore attraverso la shell, puoi accedere al database utilizzando _psql_.
    
    
    odoo@odoo-addons-master-1.odoo.sh:~$ psql
    psql (9.5.2, server 9.5.11)
    SSL connection (protocol: TLSv1.2, cipher: ECDHE-RSA-AES256-GCM-SHA384, bits: 256, compression: off)
    Type "help" for help.
    
    odoo-addons-master-1=>
    

**Attenziona!** [Utilizza transazioni](https://www.postgresql.org/docs/current/static/sql-begin.html) (_BEGIN…COMMIT/ROLLBACK_) per ogni dichiarazione _sql_ che porta a modifiche (_UPDATE_ , _DELETE_ , _ALTER_ , …), specialmente per il database di produzione.

Il meccanismo di transazione è la tua ancora di salvezza in caso di errore. Devi semplicemente ripristinare le modifiche per far tornare il database allo stato precedente.

Ad esempio, potrebbe accadere di dimenticare di configurare la condizione _DOVE_.
    
    
    odoo-addons-master-1=> BEGIN;
    BEGIN
    odoo-addons-master-1=> UPDATE res_users SET password = '***';
    UPDATE 457
    odoo-addons-master-1=> ROLLBACK;
    ROLLBACK
    

In questo caso, puoi ripristinare lo stato precedente per annullare le modifiche non desiderate apportate per errore e riscrivere la dichiarazione:
    
    
    odoo-addons-master-1=> BEGIN;
    BEGIN
    odoo-addons-master-1=> UPDATE res_users SET password = '***' WHERE id = 1;
    UPDATE 1
    odoo-addons-master-1=> COMMIT;
    COMMIT
    

Tuttavia, non dimenticare di eseguire il commit o ripristinare lo stato della transazione dopo averlo fatto. Le transazioni aperte potrebbero bloccare i record nelle tue tabelle e i database in esecuzione potrebbero aspettarne il rilascio. Può causare un blocco del server a tempo indeterminato.

Inoltre, quando possibile, usa i database di staging per testare le dichiarazioni in anticipo e avere una seconda ancora di salvatagigo.

## Far funzionare un server Odoo¶

Puoi avviare l’istanza di un server Odoo da una shell di contenitore. Non sarai in grado di accedervi dall’esterno con un browser ma potrai:

  * utilizzare la shell Odoo;



    
    
    $  odoo-bin shell
    >>> partner = env['res.partner'].search([('email', '=', 'asusteK@yourcompany.example.com')], limit=1)
    >>> partner.name
    'ASUSTeK'
    >>> partner.name = 'Odoo'
    >>> env['res.partner'].search([('email', '=', 'asusteK@yourcompany.example.com')], limit=1).name
    'Odoo'
    

  * installare un modulo;



    
    
    $  odoo-bin -i sale --without-demo=all --stop-after-init
    

  * aggiornare un modulo;



    
    
    $  odoo-bin -u sale --stop-after-init
    

  * eseguire dei test per un modulo.



    
    
    $  odoo-bin -i sale --test-enable --log-level=test --stop-after-init
    

Nei comandi in alto, l’argomento:

  * `--without-demo=all` impedisce che i dati demo vengano caricati per tutti i moduli;

  * `--stop-after-init` arresterà immediatamente l’istanza del server dopo aver completato le operazioni richieste.




Più opzioni sono disponibili e descritte alla pagina relativa alla [documentazione CLI](../../../developer/reference/cli.html).

Nei registri (_~/logs/odoo.log_) puoi trovare il percorso dei componenti aggiuntivi usato da Odoo.sh per far funzionare il server. Cerca « _odoo: addons paths_ »:
    
    
    2018-02-19 10:51:39,267 4 INFO ? odoo: Odoo version 17.0
    2018-02-19 10:51:39,268 4 INFO ? odoo: Using configuration file at /home/odoo/.config/odoo/odoo.conf
    2018-02-19 10:51:39,268 4 INFO ? odoo: addons paths: ['/home/odoo/data/addons/17.0', '/home/odoo/src/user', '/home/odoo/src/enterprise', '/home/odoo/src/themes', '/home/odoo/src/odoo/addons', '/home/odoo/src/odoo/odoo/addons']
    

**Attenzione** , specialmente con il database di produzione. Le operazioni eseguite sull’istanza del presente server Odoo non sono isolate: le modifiche saranno applicate a tutti gli effetti sul database. Esegui i test sempre nei database di staging.

## Eseguire il debug in Odoo.sh¶

Eseguire il debug di un build di Odoo.sh non è molto diverso da un’altra app Python. Il presente articolo spiega solamente le specifiche e limitazioni della piattaforma Odoo.sh e presuppone che tu sappia già come utilizzare un debugger.

Nota

Se non sai ancora come effettuare il debug di un’applicazione Python, esistono molteplici corsi introduttivi facilmente reperibili su internet.

È possibile utilizzare `pdb`, `pudb` o `ipdb` per eseguire il debug del tuo codice su Odoo.sh. Dato che il server viene eseguito al di fuori di una shell, non è possibile avviare il debugger direttamente dal backend dell’istanza Odoo in quanto il debugger ha bisogno di una shell per funzionare.

  * [pdb](https://docs.python.org/3/library/pdb.html) viene installato per impostazione predefinita in ogni contenitore.

  * Se vuoi utilizzare [pudb](https://pypi.org/project/pudb/) o [ipdb](https://pypi.org/project/ipdb/) è necessario installarlo in anticipo.

Per farlo, hai due opzioni:

>     * temporanea (nel build attuale);
>           
>           $  pip install pudb --user
>           
> 
> oppure
>           
>           $  pip install ipdb --user
>           
> 
>     * permanente: aggiungi `pudb` o `ipdb` al file `requirements.txt` del progetto.




In seguito, modifica il codice dove vuoi attivare il debugger e aggiungi questo:
    
    
    import sys
    if sys.__stdin__.isatty():
        import pdb; pdb.set_trace()
    

La condizione `sys.__stdin__.isatty()` è un trucco che rileva se si esegue Odoo da una shell.

Salva il file per poi eseguire la shell Odoo:
    
    
    $ odoo-bin shell
    

Infine, _tramite_ la shell Odoo, puoi attivare la parte di codice/funzione/metodo di cui vuoi eseguire il debug.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/odoo_sh/advanced/containers.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](submodules.html "Moduli secondarii") |
  * [precedente](../advanced.html "Avanzate") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Avanzate](../advanced.html) »
  * Contenitori


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