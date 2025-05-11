# Centro assistenza — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sla.html "Service level agreements \(SLA\)") |
  * [precedente](receiving_tickets.html "Receiving tickets") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Centro assistenza



# Centro assistenza¶

Odoo **Helpdesk** integrates with the **Forums** , **eLearning** , and **Knowledge** apps to create the _Help Center_. The _Help Center_ is a centralized location where teams and customers can search for and share detailed information about products and services.

## Configurazione¶

To activate any of the _Help Center_ features on a _Helpdesk_ team, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and select a team, or create a [new one](../../helpdesk.html). Verify the Visibility of the team is set to Invited portal users and all internal users (public) in the Visibility & Assignment section.

Additionally, the Website Form option on the **Helpdesk** team form **must** be enabled to activate any of the _Help Center_ features. When one or more of the _Help Center_ features is enabled, the Website Form is automatically enabled, as well.

Pericolo

Since all of the _Help Center_ features require integration with other applications, enabling any of them may result in the installation of additional modules or applications.

Installing a new application on a _One-App-Free_ database will trigger a 15-day trial. At the end of the trial, if a [paid subscription](https://www.odoo.com/pricing) has **not** been added to the database, it will no longer be active or accessible.

Vedi anche

[Helpdesk Overview](../../helpdesk.html)

## Knowledge¶

Odoo’s **Knowledge** application is a collaborative library, where users can store, edit, and share information. The **Knowledge** app can be used to publish user guides and FAQs with customers externally, while also collaborating internally on shared documents.

The **Knowledge** app is accessible throughout the database by clicking on the Knowledge (bookmark) icon.

The Knowledge app is represented by the bookmark icon.¶

### Enable Knowledge on a Helpdesk team¶

To enable the **Knowledge** feature on a _Helpdesk_ team, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and select a team, or create a [new one](../../helpdesk.html).

When a team has been selected or created, Odoo displays that team’s detail form.

On the team’s detail form, scroll down to the Help Center section. Then, click the box next to Knowledge to activate the **Knowledge** feature. When clicked, a new field labeled, Article appears.

Clicking the Article field reveals a drop-down menu. At first, there is only one option in the drop-down menu titled Help, which Odoo provides by default. Select Help from the drop-down menu to choose this article.

Suggerimento

To create a new article, go to the Knowledge app, then hover the cursor next to the Workspace section heading, located in the left sidebar. Moving the cursor there reveals a hidden __(plus) icon.

Click the __(plus) icon to create a new article in the Workspace. Click the __ Share icon, and slide the Share to Web toggle switch until it reads Article Published. It can then be added to a **Helpdesk** team.

Once an article has been created and assigned to a **Helpdesk** team, content can be added and organized through the **Knowledge** app.

Vedi anche

[Editing Knowledge articles](../../../productivity/knowledge/articles_editing.html)

### Search articles from a Helpdesk ticket¶

When members of a **Helpdesk** team are trying to solve a ticket, they can search through the content in the **Knowledge** app for more information on the issue.

To search **Knowledge** articles, open a ticket — either from the **Helpdesk** app dashboard, or by going to Helpdesk app ‣ Tickets ‣ All Tickets, then select a ticket from the list.

When a ticket is selected, Odoo reveals that ticket’s detail form.

Click the Knowledge (bookmark) icon, located at the top-right of the page, to open a pop-up search window.

Suggerimento

**Knowledge** articles can also be searched by pressing **Ctrl + K** to open the command palette, then typing `?`, followed by the name of the desired article.

When Odoo reveals the desired article, click it, or highlight the Article title, and press **Enter**. This will open the article in the Knowledge application.

To open the article in a new tab, press **Ctrl + Enter**.

Suggerimento

If a more in-depth search is required, press **Alt + B**. That reveals a separate page, in which a more detailed search can occur.

#### Share an article to the Help Center¶

To make a **Knowledge** article available to customers and website visitors, it **must** be published.

Importante

Even though the _Help_ article has been enabled on a team, Odoo does **not** share all the nested articles to the web. Individual articles intended for customers **must** be published for them to be viewable on the website.

To publish an article, navigate to the desired article, by following the above steps, and click the __ Share icon. This reveals a menu. Slide the toggle button labeled Share to Web to read Article Published.

### Solve tickets with a clipboard box¶

_Clipboard_ boxes can be added to **Knowledge** articles to allow content to be reused, copied, sent as messages, or added to the description on a ticket. This allows teams to maintain consistency when answering customer tickets, and minimize the amount of time spent on responding to repeat questions.

#### Add clipboard boxes to articles¶

To create a clipboard box, go to Knowledge app ‣ Help. Click on an existing nested article or create a new one by clicking the __(plus) icon next to _Help_.

Type `/` to open the _powerbox_ , and view a drop-down list of [commands](../../../productivity/knowledge/articles_editing.html). Select or type `clipboard`. A gray block is then added to the page. Add any necessary content to this block.

Nota

Clipboard boxes only display the Use as description or Send as Message options if they are accessed directly from the **Helpdesk**.

#### Use clipboard boxes in tickets¶

Clipboard boxes can be used to respond directly to a **Helpdesk** ticket as a message, or to add information to the ticket’s description.

To use clipboard boxes in a **Helpdesk** ticket, first, open a ticket, either from the Helpdesk dashboard or by going to Helpdesk app ‣ Tickets ‣ All Tickets and selecting a ticket from the list.

Click on the Knowledge (bookmark) icon in the top-right corner. This opens a search window. In this search window, select, or search, for the desired article. Doing so reveals that article page in the Odoo **Knowledge** application.

To use a clipboard box to respond to a ticket, click Send as message in the upper-right corner of the clipboard box, located in the body of the article.

Doing so opens a Compose Email pop-up window. In this window, select the recipients, make any necessary additions or edits to the clipboard content, then click Send.

Suggerimento

To use a clipboard box to add information to a ticket’s description, click Use as description in the upper-right corner of the clipboard box, located in the body of the article. Doing so does **not** replace the existing text in a ticket’s description. The content from the clipboard box is added as additional text.

## Forum community¶

A _Community Forum_ provides a space for customers to answer each other’s questions and share information. By integrating a forum with a **Helpdesk** team, tickets submitted by customers can be converted to posts and shared.

### Enable forums on a Helpdesk team¶

To enable Community Forums on a **Helpdesk** team, start by navigating to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and select a team, or create a [new one](../../helpdesk.html).

Selecting or creating a team reveals that team’s detail form. Scroll down to the Help Center section of features, and enable Community Forum, by checking the box beside it.

When activated, a new field labeled Forums appears beneath.

Click the empty Forums field to reveal a drop-down menu. By default, there is only one option to begin with, labeled Help. That is the option Odoo automatically created when the Community Forums feature was enabled. Select Help from the drop-down menu to enable that forum.

To create a new forum, type a name into the blank Forums field, then click the Create and Edit option. Multiple forums can be selected in this field.

Vedi anche

[Forum documentation](../../../websites/forum.html)

### Create a forum post from a Helpdesk ticket¶

When a **Helpdesk** team has a _Forum_ enabled, tickets submitted to that team can be converted to forum posts.

To do that, select a ticket, either from a team’s pipeline or from Tickets ‣ All Tickets in the Helpdesk application.

At the top of the ticket detail form, click the Share on Forum button.

When clicked, a pop-up window appears. Here, the Forum post and Title can be edited to correct any typos, or modified to remove any proprietary or client information.

Tags can also be added to help organize the post in the forum, making it easier for users to locate during a search. When all adjustments have been made, click Create and View Post.

### Create a Helpdesk ticket from a forum post¶

Forum posts submitted by portal users can be converted to **Helpdesk** tickets.

To create a ticket, navigate to a forum post, and click the __(ellipsis) icon. Then, click Create Ticket.

This opens a Create Ticket pop-up. Make any necessary edits to the Create Ticket field. Then, confirm the Helpdesk Team the ticket should be assigned to.

Click Create & View Ticket or Create Ticket.

Nota

The original forum post is linked in the chatter on the new ticket.

## E-learning¶

Odoo **eLearning** courses offer customers additional training and content in the form of videos, presentations, and certifications/quizzes. Providing additional training enables customers to work through issues and find solutions on their own. They can also develop a deeper understanding of the services and products they are using.

### Enable eLearning courses on a Helpdesk team¶

To enable **eLearning** courses on a **Helpdesk** team, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and select a team, or create a [new one](../../helpdesk.html).

On the team’s settings page, scroll to the Help Center section, and check the box next to eLearning. A new field appears below, labeled Courses.

Click the empty field next to Courses beneath the eLearning feature to reveal a drop-down menu. Select an available course from the drop-down menu, or type a title into the field, and click Create and edit to create a new course from this page. Multiple courses can be assigned to a single team.

### Create an eLearning course¶

A new **eLearning** course can be created from the Helpdesk team’s settings page, as in the step above, or from the **eLearning** app.

To create a course directly through the **eLearning** application, navigate to eLearning ‣ New. This reveals a blank course template that can be customized and modified as needed.

On the course template page, add a Course Title, and below that, Tags.

Click on the Options tab.

Under Access Rights, select which users are able to view and enroll in the course.

The Show Course To field defines who can access the courses. The Enroll Policy field specifies how they can register for the course.

Under Display, choose the preferred course Type.

#### Add content to an eLearning course¶

To add content to a course, click the Content tab and select Add Content. Choose the Content Type from the drop-down menu and upload the file, or paste the link, where instructed. Click Save when finished. Click Add Section to organize the course in sections.

Nota

In order to add a certification to a course, go to eLearning ‣ Configuration ‣ Settings, check the box labeled Certifications, and Save to activate the setting.

Vedi anche

[Odoo Tutorials: eLearning](https://www.odoo.com/slides/elearning-56)

### Publish an eLearning course¶

To allow customers to enroll in a course, both the course and the contents **must** be published.

Suggerimento

If the course is published, but the contents of the course are **not** published, customers can enroll in the course on the website, but they are **not** able to view any of the course content. Knowing this, it may be beneficial to publish the course first, if the course contents are intended to be released over time, such as classes with a weekly schedule.

To make the entire course available at once, each piece of course content must be published first, then the course can be published.

To publish a course, choose a course from the **eLearning** dashboard. On the course template page, click the Go to Website smart button.

This will reveal the front end of the course’s web page. At the top of the course web page, move the Unpublished toggle switch to Published.

#### Publish eLearning course contents from the back-end¶

To publish **eLearning** course content from the back-end, choose a course from the **eLearning** dashboard. On the course template page, click the Published Contents smart button.

Doing so reveals a separate page displaying all the published content related to that course. Remove the default Published filter from the search bar in the upper-right corner, to reveal all the content related to the course - even the non-published content.

Click the __(list) icon to switch to list view.

While in list view, there is a checkbox on the far-left of the screen, above the listed courses, to the left of the Title column title. When that checkbox is clicked, all the course contents are selected at once.

With all the course content selected, click any of the boxes in the Is Published column. This reveals a pop-up window, asking for confirmation that all selected records are intended to be published. Click Confirm to automatically publish all course content.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/services/helpdesk/overview/help_center.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sla.html "Service level agreements \(SLA\)") |
  * [precedente](receiving_tickets.html "Receiving tickets") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Panoramica](../overview.html) »
  * Centro assistenza


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