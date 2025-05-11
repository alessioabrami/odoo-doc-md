# Setup guide — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](server_framework_101.html "Server framework 101") |
  * [precedente](../tutorials.html "Tutorials") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Setup guide



# Setup guide¶

Depending on the intended use case, there are multiple ways to install Odoo. For developers of the Odoo community and Odoo employees alike, the preferred way is to perform a source install (running Odoo from the source code).

Importante

Follow the [Environment setup](../../contributing/development.html#contributing-development-setup) section of the contributing guide to prepare your environment for pushing local changes to the Odoo repositories.

## Adapt the environment for the tutorials¶

By now, you should have downloaded the source code into two local repositories, one for `odoo/odoo` and one for `odoo/enterprise`. These repositories are set up to push changes to pre-defined forks on GitHub. This will prove to be convenient when you start contributing to the codebase, but in the scope of following a tutorial, we want to avoid polluting them with training material. Let’s then push your changes in a third repository: `odoo/tutorials`. Like the first two repositories, it will be part of the `addons-path` that references all directories containing Odoo modules.

Nota

Depending on the tutorial that you are following, you might not need to install all the modules that this repository contains.

  1. Following the same process as with the `odoo/odoo` and `odoo/enterprise` repositories, clone the `odoo/tutorials` repository on your machine with:
         
         $ git clone git@github.com:odoo/tutorials.git
         

  2. Configure your fork and Git to push changes to your fork rather than to the main codebase. If you work at Odoo, configure Git to push changes to the shared fork created on the account **odoo-dev**.

Link Git with your forkLink Git with odoo-dev

     1. Visit [github.com/odoo/tutorials](https://github.com/odoo/tutorials) and click the Fork button to create a fork of the repository on your account.

     2. In the command below, replace `<your_github_account>` with the name of the GitHub account on which you created the fork.
            
            $ cd /TutorialsPath
            $ git remote add dev git@github.com:<your_github_account>/tutorials.git
            
    
    $ cd /tutorials
    $ git remote add dev git@github.com:odoo-dev/tutorials.git
    $ git remote set-url --push origin you_should_not_push_on_this_repository
    




That’s it! Your environment is now prepared to run Odoo from the sources, and you have successfully created a repository to serve as an addons directory. This will allow you to push your work to GitHub.

Importante

**For Odoo employees only:**

  1. Make sure to read very carefully [Make your first contribution](../../contributing/development.html#contributing-development-first-contribution). In particular, your branch name must follow our conventions.

  2. Once you have pushed your first change to the shared fork on **odoo-dev** , create a PR. Please put your quadrigram in the PR title (e.g., «abcd - Technical Training»).

This will enable you to share your upcoming work and receive feedback from your coaches. To ensure a continuous feedback loop, we recommend pushing a new commit as soon as you complete a chapter of the tutorial. Note that the PR is automatically updated with commits you push to **odoo-dev** , you don’t need to open multiple PRs.

  3. At Odoo we use [Runbot](https://runbot.odoo.com/) extensively for our CI tests. When you push your changes to **odoo-dev** , Runbot creates a new build and test your code. Once logged in, you will be able to see your branches [Tutorials project](https://runbot.odoo.com/runbot/tutorials-12).




Nota

The specific location of the repositories on your file system is not crucial. However, for the sake of simplicity, we will assume that you have cloned all the repositories under the same directory. If this is not the case, make sure to adjust the following commands accordingly, providing the appropriate relative path from the `odoo/odoo` repository to the `odoo/tutorials` repository.

## Run the server¶

### Launch with `odoo-bin`¶

Once all dependencies are set up, Odoo can be launched by running `odoo-bin`, the command-line interface of the server.
    
    
    $ cd $HOME/src/odoo/
    $ ./odoo-bin --addons-path="addons/,../enterprise/,../tutorials" -d rd-demo
    

There are multiple [command-line arguments](../reference/cli.html#reference-cmdline-server) that you can use to run the server. In this training you will only need some of them.

-d <database>¶
    

The database that is going to be used.

\--addons-path <directories>¶
    

A comma-separated list of directories in which modules are stored. These directories are scanned for modules.

\--limit-time-cpu <limit>¶
    

Prevent the worker from using more than <limit> CPU seconds for each request.

\--limit-time-real <limit>¶
    

Prevent the worker from taking longer than <limit> seconds to process a request.

Suggerimento

  * The `--limit-time-cpu` and `--limit-time-real` arguments can be used to prevent the worker from being killed when debugging the source code.

  * You may face an error similar to `AttributeError: module '<MODULE_NAME>' has no attribute '<$ATTRIBUTE'>`. In this case, you may need to re-install the module with **$ pip install --upgrade --force-reinstall <MODULE_NAME>**.

If this error occurs with more than one module, you may need to re-install all the requirements with **$ pip install --upgrade --force-reinstall -r requirements.txt**.

You can also clear the python cache to solve the issue:

> $ cd $HOME/.local/lib/python3.8/site-packages/
>         $ find -name '*.pyc' -type f -delete
>         

  * Other commonly used arguments are:

    * [`-i`](../reference/cli.html#cmdoption-odoo-bin-i): Install some modules before running the server (comma-separated list). This is equivalent to going to Apps in the user interface, and installing the module from there.

    * [`-u`](../reference/cli.html#cmdoption-odoo-bin-u): Update some modules before running the server (comma-separated list). This is equivalent to going to Apps in the user interface, selecting a module, and upgrading it from there.




### Log in to Odoo¶

Open <http://localhost:8069/> on your browser. We recommend using [Chrome](https://www.google.com/intl/en/chrome/), [Firefox](https://www.mozilla.org/firefox/new/), or any other browser with development tools.

To log in as the administrator user, use the following credentials:

  * email: `admin`

  * password: `admin`




## Enable the developer mode¶

The developer or debug mode is useful for training as it gives access to additional (advanced) tools. [Enable the developer mode](../../applications/general/developer_mode.html#developer-mode) now. Choose the method that you prefer; they are all equivalent.

## Extra tools¶

### Useful Git commands¶

Here are some useful Git commands for your day-to-day work.

  * Switch branches:

When you switch branches, both repositories (odoo and enterprise) must be synchronized, i.e. both need to be in the same branch.
        
        $ cd $HOME/src/odoo
        $ git switch 18.0
        
        $ cd $HOME/src/enterprise
        $ git switch 18.0
        

  * Fetch and rebase:
        
        $ cd $HOME/src/odoo
        $ git fetch --all --prune
        $ git rebase --autostash odoo/18.0
        
        $ cd $HOME/src/enterprise
        $ git fetch --all --prune
        $ git rebase --autostash enterprise/18.0
        




### Code Editor¶

If you are working at Odoo, many of your colleagues are using [VSCode](https://code.visualstudio.com/), [VSCodium](https://vscodium.com/) (the open source equivalent), [PyCharm](https://www.jetbrains.com/pycharm/download/#section=linux), or [Sublime Text](https://www.sublimetext.com/). However, you are free to choose your preferred editor.

It is important to configure your linters correctly. Using a linter helps you by showing syntax and semantic warnings or errors. Odoo source code tries to respect Python’s and JavaScript’s standards, but some of them can be ignored.

For Python, we use PEP8 with these options ignored:

  * `E501`: line too long

  * `E301`: expected 1 blank line, found 0

  * `E302`: expected 2 blank lines, found 1




For JavaScript, we use ESLint and you can find a [configuration file example here](https://github.com/odoo/odoo/wiki/Javascript-coding-guidelines#use-a-linter).

### Administrator tools for PostgreSQL¶

You can manage your PostgreSQL databases using the command line as demonstrated earlier or using a GUI application such as [pgAdmin](https://www.pgadmin.org/download/pgadmin-4-apt/) or [DBeaver](https://dbeaver.io/).

To connect the GUI application to your database we recommend you connect using the Unix socket.

  * Host name/address: `/var/run/postgresql`

  * Port: `5432`

  * Username: `$USER`




### Python Debugging¶

When facing a bug or trying to understand how the code works, simply printing things out can go a long way, but a proper debugger can save a lot of time.

You can use a classic Python library debugger ([pdb](https://docs.python.org/3/library/pdb.html), [pudb](https://pypi.org/project/pudb/) or [ipdb](https://pypi.org/project/ipdb/)), or you can use your editor’s debugger.

In the following example we use ipdb, but the process is similar with other libraries.

  1. Install the library:
         
         pip install ipdb
         

  2. Place a trigger (breakpoint):
         
         import ipdb; ipdb.set_trace()
         

Example
         
         def copy(self, default=None):
             import ipdb; ipdb.set_trace()
             self.ensure_one()
             chosen_name = default.get('name') if default else ''
             new_name = chosen_name or _('%s (copy)') % self.name
             default = dict(default or {}, name=new_name)
             return super(Partner, self).copy(default)
         




Here is a list of commands:

h(elp) [command]¶
    

Print the list of available commands if not argument is supplied. With a command as an argument, print the help about that command.

pp expression¶
    

The value of the `expression` is pretty-printed using the `pprint` module.

w(here)¶
    

Print a stack trace with the most recent frame at the bottom.

d(own)¶
    

Move the current frame one level down in the stack trace (to a newer frame).

u(p)¶
    

Move the current frame one level up in the stack trace (to an older frame).

n(ext)¶
    

Continue the execution until the next line in the current function is reached or it returns.

c(ontinue)¶
    

Continue the execution and only stop when a breakpoint is encountered.

s(tep)¶
    

Execute the current line. Stop at the first possible occasion (either in a function that is called or on the next line in the current function).

q(uit)¶
    

Quit the debugger. The program being executed is aborted.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/tutorials/setup_guide.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](server_framework_101.html "Server framework 101") |
  * [precedente](../tutorials.html "Tutorials") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Setup guide


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous Integration
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