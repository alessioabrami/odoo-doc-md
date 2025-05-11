# Forum — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blog.html "Blog") |
  * [precedente](elearning.html "E-learning") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * Forum



# Forum¶

**Odoo Forum** is a question-and-answer forum designed with providing customer support in mind. Adding a forum to a website enables you to build a community, encourage engagement, and share knowledge.

## Create a forum¶

To create or edit a forum, go to Website ‣ Configuration ‣ Forum: Forums. Click New or select an existing forum and configure the following elements.

Forum Name: add the name of the forum.

Mode: select Questions to enable marking an answer as best, meaning questions then appear as _solved_ , or Discussions if the feature is not needed.

Nota

Regardless of the selected mode, only **one answer** per user is allowed on a single post. Commenting multiple times is allowed, however.

Default Sort: choose how questions are sorted by default.

>   * Newest: by latest question posting date
> 
>   * Last Updated: by latest posting activity date (answers and comments included)
> 
>   * Most Voted: by highest vote tally
> 
>   * Relevance: by post relevancy (determined by a formula)
> 
>   * Answered: by likelihood to be answered (determined by a formula)
> 
> 


Nota

Users have several sorting options (total replies, total views, last activity) on the forum front end.

Privacy: select Public to let anyone view the forum, Signed In to make it visible only for signed-in users, or Some users to make it visible only for a specific user access group by selecting one Authorized Group.

Next, configure the karma gains and the karma-related rights.

### Karma points¶

Karma points can be given to users based on different forum interactions. They can be used to determine which forum functionalities users can access, from being able to vote on posts to having moderator rights. They are also used to set user ranks.

Importante

  * A user’s karma points are shared across all forums, courses, etc., of a single Odoo website.

  * eLearning users can earn karma points through different [course interactions](elearning.html#elearning-karma) and by [completing quizzes](elearning.html#elearning-quiz).




#### Karma gains¶

Several forum interactions can give or remove karma points.

Interaction | Descrizione | Default karma gain  
---|---|---  
Asking a question | You post a question. | 2  
Question upvoted | Another user votes for a question you posted. | 5  
Question downvoted | Another user votes against a question you posted. | -2  
Answer upvoted | Another user votes for an answer you posted. | 10  
Answer downvoted | Another user votes against an answer you posted. | -2  
Accepting an answer | You mark an answer posted by another user as best. | 2  
Answer accepted | Another user marks an answer you posted as best. | 15  
Answer flagged | A question or an answer you posted is marked as offensive. | -100  
  
Nota

New users receive **three points** upon validating their email address.

To modify the default values, go to Website ‣ Configuration ‣ Forum: Forums, select the forum, and go to the Karma Gains tab. Select a value to edit it.

If the value is positive (e.g., `5`), the number of points will be added to the user’s tally each time the interaction happens on the selected forum. Conversely, if the value is negative (e.g., `-5`), the number of points will be deducted. Use `0` if an interaction should not impact a user’s tally.

#### Karma-related rights¶

To configure how many karma points are required to access the different forum functionalities, go to Website ‣ Configuration ‣ Forum: Forums, select the forum, and go to the Karma Related Rights tab. Select a value to edit it.

Avvertimento

Some functionalities, such as Edit all posts, Close all posts, Delete all posts, Moderate posts, and Unlink all comments, are rather sensitive. Make sure to understand the consequences of giving _any_ user reaching the set karma requirements access to such functionalities.

Functionality | Descrizione | Default karma requirement  
---|---|---  
Ask questions | Post questions. | 3  
Answer questions | Post answers to questions. | 3  
Upvote | Vote for questions or answers. | 5  
Downvote | Vote against questions or answers. | 50  
Edit own posts | Edit questions or answers you posted. | 1  
Edit all posts | Edit any question or answer. | 300  
Close own posts | Close questions or answers you posted. | 100  
Close all posts | Close any question or answer. | 500  
Delete own posts | Delete questions or answers you posted. | 500  
Delete all posts | Delete any question or answer. | 1.000  
Nofollow links | If you are under the karma threshold, a _nofollow_ attribute tells search engines to ignore links you post. | 500  
Accept an answer on own questions | Mark an answer as best on questions you posted. | 20  
Accept an answer to all questions | Mark an answer as best on any question. | 500  
Editor Features: image and links | Add links and images to your posts. | 30  
Comment own posts | Post comments under questions or answers you created. | 1  
Comment all posts | Post comments under any question or answer. | 1  
Convert own answers to comments and vice versa | Convert comments you posted as answers. | 50  
Convert all answers to comments and vice versa | Convert any comment as answer. | 500  
Unlink own comments | Delete comments you posted. | 50  
Unlink all comments | Delete any comment. | 500  
Ask questions without validation | Questions you post do not require to be validated first. | 100  
Flag a post as offensive | Flag a question or answer as offensive. | 500  
Moderate posts | Access all moderation tools. | 1.000  
Change question tags | Change posted questions” tags (if you have the right to edit them). | 75  
Create new tags | Create new tags when posting questions. | 30  
Display detailed user biography | When a user hovers their mouse on your avatar or username, a popover box showcases your karma points, biography, and number of badges per level. | 750  
  
Suggerimento

Track all karma-related activity and add or remove karma manually by [enabling developer mode](../general/developer_mode.html#developer-mode) and going to Settings ‣ Gamification Tools ‣ Karma Tracking.

### Competizione con gli altri¶

Ranks and badges can be used to encourage participation. Ranks are based on the total karma points, while badges can be granted manually or automatically by completing challenges.

#### Livelli¶

To create new ranks or modify the default ones, go to Website ‣ Configuration ‣ Forum: Ranks and click New or select an existing rank.

Add the Rank Name, the Required Karma points to reach it, its Description, a Motivational message to encourage users to reach it, and an image.

#### Riconoscimenti¶

To create new badges or modify the default ones, go to Website ‣ Configuration ‣ Forum: Badges and click New or select an existing badge.

Enter the badge name and description, add an image, and configure it.

##### Assign manually¶

If the badge should be granted manually, select which users can grant them by selecting one of the following Allowance to Grant options:

  * Everyone: all non-portal users (since badges are granted from the backend).

  * A selected list of users: users selected under Authorized Users.

  * People having some badges: users who have been granted the badges selected under Required Badges.




It is possible to restrict how many times per month each user can grant the badge by enabling Monthly Limited Sending and entering a Limitation Number.

##### Assign automatically¶

If the badge should be granted **automatically** when certain conditions are met, select No one, assigned through challenges under Allowance to Grant.

Next, determine how the badge should be granted by clicking Add under the Rewards for challenges section. Select a challenge to add it or create one by clicking New.

Suggerimento

It is possible to give the badge a Forum Badge Level (Bronze, Silver, Gold) to give it more or less importance.

### Etichette¶

Users can use tags to filter forum posts.

To manage tags, go to Website ‣ Configuration ‣ Forum: Tags. Click New to create a tag and select the related Forum.

Suggerimento

  * Use the Tags section on the forum’s sidebar to filter all questions assigned to the selected tag. Click View all to display all tags.

  * New tags can be created when posting a new message, provided the user has enough karma points.




## Use a forum¶

Nota

Access to many functionalities depends on a user’s karma points.

### Post questions¶

To create a new post, access the forum’s front end, click New Post, and fill in the following:

  * Title: add the question or the topic of the post.

  * Description: add a description for the question.

  * Tags: add up to five tags.




Click Post Your Question.

### Interact with posts¶

Different actions are possible on a post.

  * Mark a question as **favorite** by clicking the star button (☆).

  * Follow a post and get **notifications** (by email or within Odoo) when it is answered by clicking the bell button (🔔).

  * **Vote** _for_ (up arrow ▲) or _against_ (down arrow ▼) a question or answer.

  * Mark an answer as **best** by clicking the check mark button (✔). This option is only available if the Forum Mode is set to Questions.

  * Answer a question.

  * **Comment** on a question or answer by clicking the speech bubble button (💬).

  * **Share** a question on Facebook, Twitter, or LinkedIn by clicking the _share nodes_ button.




Click the ellipsis button (…) to:

>   * Edit a question or answer.
> 
>   * Close a question.
> 
>   * Delete a question, answer, or comment. It is possible to Undelete questions afterward.
> 
>   * Flag a question or answer as offensive.
> 
>   * Convert a comment into an answer.
> 
>   * View the related [Helpdesk ticket](../services/helpdesk/overview/help_center.html#helpdesk-forum), if any.
> 
> 


Nota

By default, 150 karma points are required to view another user’s profile. This value can be configured when creating a new website.

## Moderate a forum¶

On the forum’s front end, the sidebar’s Moderation tools section gathers the essential moderator functionalities.

To Validate: access all questions and answers waiting for validation before being displayed to non-moderator users.

Nota

A question is pending if a user does not have the required karma. The user is not able to post questions or answers while awaiting validation. Only one pending question per user is allowed per forum.

Flagged: access all questions and answers that have been flagged as offensive. Click Accept to remove the offensive flag or Offensive to confirm it, then select a reason and click Mark as offensive. The post is then hidden from users without moderation rights, and 100 karma points are deducted from the offending user’s tally.

Closed: access all questions that have been closed. It is possible to Delete or Reopen them. To close a question, open it, click the ellipsis button (…), then Close, select a Close Reason, and click Close post. The post is then hidden from users without moderation rights.

Nota

When selecting Spam or advertising or Contains offensive or malicious remarks as the reason, 100 karma points are deducted from the poster’s tally.

Suggerimento

  * Create and edit close reasons by going to Website ‣ Configuration ‣ Forum: Close Reasons. Select Basic as Reason Type if the reason should be used when closing a question, and Offensive if it should be used for flagged posts.

  * Manage all posts by going to Website ‣ Configuration ‣ Forum: Forums, selecting the forum, and clicking the Posts smart button. By clicking the Actions button, it is possible to Export, Archive, Unarchive, or Delete one or multiple posts.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/forum.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](blog.html "Blog") |
  * [precedente](elearning.html "E-learning") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * Forum


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