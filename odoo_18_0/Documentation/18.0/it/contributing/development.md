# Development — Odoo 18.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](development/coding_guidelines.html "Coding guidelines") |
  * [precedente](../contributing.html "Contributing") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Contributing](../contributing.html) »
  * Development



# Development¶

  * [Coding guidelines](development/coding_guidelines.html)
  * [Git guidelines](development/git_guidelines.html)



If you are reading this, chances are that you are interested in learning how to contribute to the codebase of Odoo. Whether that’s the case or you landed here by accident, we’ve got you covered!

Vedi anche

[Discover other ways to contribute to Odoo](../contributing.html)

When you feel ready, jump to the Environment setup section to begin your journey in contributing to the development of Odoo.

## Environment setup¶

The instructions below help you prepare your environment for making local changes to the codebase and then push them to GitHub. Skip this section and go to Make your first contribution if you have already completed this step.

  1. First, you need to [create a GitHub account](https://github.com/join). Odoo uses GitHub to manage the source code of its products, and this is where you will make your changes and submit them for review.

  2. [Generate a new SSH key and register it on your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

  3. Go to [github.com/odoo/odoo](https://github.com/odoo/odoo) and click on the Fork button in the top right corner to create a fork (your own copy) of the repository on your account. Do the same with [github.com/odoo/enterprise](https://github.com/odoo/enterprise) if you have access to it. This creates a copy of the codebase to which you can make changes without affecting the main codebase. Skip this step if you work at Odoo.

  4. [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). It is a command-line (a text interface) tool that allows tracking the history of changes made to a file and, more importantly, working on different versions of that file simultaneously. It means you do not need to worry about overwriting someone else’s pending work when making changes.

Verify that the installation directory of Git is included in your system’s `PATH` variable.

Linux and macOSWindows

Follow the [guide to update the PATH variable on Linux and macOS](https://unix.stackexchange.com/a/26059) with the installation path of Git (by default `/usr/bin/git`).

Follow the [guide to update the PATH variable on Windows](https://www.howtogeek.com/118594/how-to-edit-your-system-path-for-easy-command-line-access/) with the installation path of Git (by default `C:\Program Files\Git`).

  5. Configure Git to identify yourself as the author of your future contributions. Enter the same email address you used to register on GitHub.
         
         $ git config --global user.name "Your Name"
         $ git config --global user.email "youremail@example.com"
         

  6. [Install Odoo from the sources](../administration/on_premise/source.html). Make sure to fetch the sources through Git with SSH.

  7. Configure Git to push changes to your fork(s) rather than to the main codebase. If you work at Odoo, configure Git to push changes to the shared forks created on the account **odoo-dev**.

Link Git with your fork(s)Link Git with odoo-dev

In the command below, replace `<your_github_account>` with the name of the GitHub account on which you created the fork(s).
         
         $ cd /CommunityPath
         $ git remote add dev git@github.com:<your_github_account>/odoo.git
         

If you have access to `odoo/enterprise`, configure the related remote too.
         
         $ cd /EnterprisePath
         $ git remote add dev git@github.com:<your_github_account>/enterprise.git
         
         
         $ cd /CommunityPath
         $ git remote add dev git@github.com:odoo-dev/odoo.git
         $ git remote set-url --push origin you_should_not_push_on_this_repository
         
         $ cd /EnterprisePath
         $ git remote add dev git@github.com:odoo-dev/enterprise.git
         $ git remote set-url --push origin you_should_not_push_on_this_repository
         

  8. That’s it! You are ready to make your first contribution.




## Make your first contribution¶

Importante

  * Odoo development can be challenging for beginners. We recommend you to be knowledgeable enough to code a small module before contributing. If that is not the case, take some time to go through the [developer tutorials](../developer/tutorials.html) to fill in the gaps.

  * Some steps of this guide require to be comfortable with Git. Here are some [tutorials](https://www.atlassian.com/git/tutorials) and an [interactive training](https://learngitbranching.js.org/) if you are stuck at some point.




Now that your environment is set up, you can start contributing to the codebase. In a terminal, navigate to the directory where you installed Odoo from sources and follow the guide below.

  1. Choose the version of Odoo to which you want to make changes. Keep in mind that contributions targeting an [unsupported version of Odoo](../administration/supported_versions.html) are not accepted. This guide assumes that the changes target Odoo 18, which corresponds to branch `18.0`.

  2. Create a new branch starting from branch 18.0. Prefix the branch name with the base branch: `18.0-...`. If you work at Odoo, suffix the branch name with your Odoo handle: `18.0-...-xyz`.

Example
         
         $ git switch -c 18.0-fix-invoices
         
         
         $ git switch -c 18.0-fix-invoices-xyz
         

  3. [Sign the Odoo CLA](https://github.com/odoo/odoo/blob/18.0/doc/cla/sign-cla.md) if not already done. Skip this step if you work at Odoo.

  4. Make the desired changes to the codebase. When working on the codebase, follow these rules:

     * Keep your changes focused and specific. It is best to work on one particular feature or bug fix at a time rather than tackle multiple unrelated changes simultaneously.

     * Respect the [stable policy](https://github.com/odoo/odoo/wiki/Contributing#what-does-stable-mean) when working in another branch than `master`.

     * Follow the [coding guidelines](development/coding_guidelines.html).

     * Test your changes thoroughly and [write tests](../developer/reference/backend/testing.html) to ensure that everything is working as expected and that there are no regressions or unintended consequences.

  5. Commit your changes. Write a clear commit message as instructed in the [Git guidelines](development/git_guidelines.html).
         
         $ git add .
         $ git commit
         

  6. Push your change to your fork, for which we added the remote alias `dev`.

Example
         
         $ git push -u dev 18.0-fix-invoices-xyz
         

  7. Open a PR on GitHub to submit your changes for review.

     1. Go to the [compare page of the odoo/odoo codebase](https://github.com/odoo/odoo/compare), or the [compare page of the odoo/enterprise codebase](https://github.com/odoo/enterprise/compare), depending on which codebase your changes target.

     2. Select **18.0** for the base.

     3. Click on compare across forks.

     4. Select **< your_github_account>/odoo** or **< your_github_account>/enterprise** for the head repository. Replace `<your_github_account>` with the name of the GitHub account on which you created the fork or by **odoo-dev** if you work at Odoo.

     5. Review your changes and click on the Create pull request button.

     6. Tick the Allow edits from maintainer checkbox. Skip this step if you work at Odoo.

     7. Complete the description and click on the Create pull request button again.

  8. At the bottom of the page, check the mergeability status and address any issues.

  9. As soon as your PR is ready for merging, a member of the Odoo team is automatically assigned for review. If the reviewer has questions or remarks, they will post them as comments and you will be notified by email. Those comments must be resolved for the contribution to go forward.

  10. Once your changes are approved, the review merges them and they become available for all Odoo users after the next code update!




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/contributing/development.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](development/coding_guidelines.html "Coding guidelines") |
  * [precedente](../contributing.html "Contributing") |
  * [Odoo 18.0 documentazione](../index-2.html) »
  * [Contributing](../contributing.html) »
  * Development


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
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