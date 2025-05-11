# E-learning — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forum.html "Forum") |
  * [precedente](ecommerce/performance.html "Performance management") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * E-learning



# E-learning¶

The **eLearning** app allows you to easily upload content, define learning objectives, manage attendees, assess students” progress, and even set up rewards. Engaging participants in a meaningful learning experience enhances their attentiveness and fosters heightened productivity.

Importante

You can manage your eLearning content on the **front end** or the **back end**. The **front end** allows you to create content quickly from your website, while the **back end** provides additional options and allows collaboration. This documentation focuses on using the back end to create your content.

Vedi anche

[Odoo Tutorials: eLearning](https://www.odoo.com/slides/elearning-56)

## Corsi¶

By going to eLearning ‣ Courses ‣ Courses, you can get an overview of all your courses.

Click on a course title to edit your course on the back end. Click on View course to access your course on the front end.

### Course creation¶

Click New to create a new course. When the page pops up, you can add your Course Title and one or more Tags to describe your course. You can add an image to illustrate your course by hovering your mouse on the camera placeholder image and clicking on the edit icon. Four tabs allow you to edit your course further: Content, Description, Options, and Karma.

#### Content tab¶

This tab allows you to manage your course content. Click on Add Section to divide your course into different sections. Click on Add Content to create content. Click on Add Certification to assess the level of understanding of your attendees, certify their skills, and motivate them. **Certification** is part of the [Surveys](../marketing/surveys/create.html) app.

#### Description tab¶

You can add a short description or information related to your course in the Description tab. It appears under your course title on your website.

#### Options tab¶

In the Options tab, different configurations are available: Course, Communication, Access rights, and Display.

##### Corso¶

Assign a Responsible user for your course. If you have multiple websites, use the Website field to only display the course on the selected website.

##### Comunicazioni¶

  * Allow Reviews: tick the box to allow attendees to like and comment on your content and to submit reviews on your course;

  * Forum: add a dedicated forum to your course (only shown if the **Forum** feature is enabled in the app’s settings);

  * New Content Notification: select an email template sent to your attendees when you upload new content. Click on the internal link button (➜) to have access to the email template editor;

  * Completion Notification: select an email template sent to your attendees once they reach the end of your course. Click on the internal link button (➜) to access the email template editor;




##### Diritti di accesso¶

  * Prerequisites: set one or more courses that users are advised to complete before
    

accessing your course;

  * Show course to: define who can access your course and their content between Everyone, Signed In or Course Attendees;

  * Enroll Policy: define how people enroll in your course. Select:

>     * Open: if you want your course to be available to anyone;
> 
>     * On Invitation: if only people who received an invitation can enroll to your course. If selected, fill in the Enroll Message explaining the course’s enrollment process. This message appears on your website under the course title;
> 
>     * On Payment: if only people who bought your course can attend it. The Paid Courses feature must be enabled to get this option. If you select On Payment, you must add a Product for your course.
>
>> Nota
>> 
>> Only products set up with Course as their Product Type are displayed.




##### Mostra¶

  * Training: the course content appears as a training program, and the courses must be taken in the proposed order.

  * Documentation: the content is available in any order. If you choose this option, you can choose which page should be promoted on the course homepage by using the Featured Content field.




#### Karma tab¶

This tab is about gamification to make eLearning fun and interactive.

In the Rewards section, choose how many karma points you want to grant your students when they Review or Finish a course.

In the Access Rights section, define the karma needed to Add Review, Add Comment, or Vote on the course.

Nota

From your course, click the Contact Attendees button to reach people who are enrolled in the course.

### Course groups¶

Use the **Course Groups** to inform users and allow them to filter the courses from the All Courses dashboard.

You can manage them by going to Configuration ‣ Course Groups. Click New to create a new course group. Add the Course Group Name, tick the Menu Entry box to allow users to search by course group on the website, and add tags in the Tag Name column. For each tag, you can select a corresponding color.

### Impostazioni¶

You can enable different features to customize your courses by going to eLearning ‣ Configuration ‣ Settings:

  * **Certifications** : to evaluate the knowledge of your attendees and certify their skills;

  * **Paid courses** : to sell access to your courses on your website and track revenues;

  * **Mailing** : to update all your attendees at once through mass mailings;

  * **Forum** : to create a community and let attendees answer each other’s questions.




## Contenuto¶

Manage your content by going to eLearning ‣ Courses ‣ Contents. Click New to create content. Add your Content Title, and if you want Tags, then fill in the related information among the different tabs.

### Document tab¶

  * Course: select the course your content belongs to;

  * Content Type: select the type of your content;

  * Responsible: add a responsible person for your content;

  * Duration: indicate the time required to complete the course;

  * Allow Download: allow users to download the content of the slide. This option is only visible when the content is a document;

  * Allow Preview: the course is accessible by anyone.

  * # of Public Views: displays the number of views from non-enrolled participants;

  * # Total Views: displays the total number of views (non-enrolled and enrolled participants).




### Description tab¶

You can add a description of your content that appears front end in the About section of your course content.

### Additional Resources tab¶

Click Add a line to add a link or a file that supports your participants” learning. It appears in the course content on your website.

### Quiz tab¶

From this tab you can create a quiz to assess your students at the end of the course.

The Points Rewards section lets you give a specific number of karma points depending on how many tries they need to correctly answer the question. Then, create your questions and the possible answers by clicking on Add a line. A new window pops up, add the question by filling in the Question Name and add multiple answers by clicking on Add a line. Tick the Is correct answer to mark one or more answers as correct. You can also fill in the Comment field to display additional information when the answer is chosen by the participant.

### Etichette contenuto¶

The **Content Tags** help users to classify the content from the Contents dashboard.

You can manage them by going to eLearning ‣ Configuration ‣ Content Tags. Click New to create a new tag.

## Publish your content¶

Everything created on the back end needs to be published from the front end. Unpublished content is always visible from your website but still needs to be published to be available to your audience.

You must be on your website’s front end to publish your content. To do so, click on the Go To Website smart button, and tick the Publish option available in the right-hand corner.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/elearning.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](forum.html "Forum") |
  * [precedente](ecommerce/performance.html "Performance management") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * E-learning


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