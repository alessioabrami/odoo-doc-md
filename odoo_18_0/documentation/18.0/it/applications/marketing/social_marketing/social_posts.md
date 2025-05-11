# Social posts — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](social_campaigns.html "Social marketing campaigns") |
  * [precedente](../social_marketing.html "Marketing social") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing social](../social_marketing.html) »
  * Social posts



# Social posts¶

The Odoo _Social Marketing_ application provides various ways to create posts for any type of social media outlet.

## Posts page¶

To see a complete overview of posts, go to Odoo Social Marketing app ‣ Posts. Here, on the Social Posts page, every post that has been created and posted with Odoo can be seen and accessed.

There are four different view options for the Social Posts page data: _kanban_ , _calendar_ , _list_ , and _pivot_.

The view options are located in the upper right corner of the Posts page, beneath the search bar.

Kanban viewCalendar viewList viewPivot view

By default, Odoo displays the posts in a kanban view. The information on this page can be sorted even further, via the left sidebar, where all connected social accounts and posts can be quickly seen, accessed, and analyzed.

The kanban view is represented by an inverted bar graph icon in the upper-right corner.

The calendar view option displays a visual representation of posts in a calendar format of when posts were published, or are scheduled to be published. This option provides a clear overview of any planned day, week, or month, and Odoo displays all drafted, scheduled, and published posts.

Clicking on a date reveals a blank social media post detail form, in which a social media post can be created, and Odoo will post it on that specific date/time.

The calendar view is represented by a calendar icon in the upper-right corner.

The list view option is similar to the kanban option, but instead of individual blocks, all post information is displayed in a clear, list layout. Each line of the list displays the Social Accounts, Message, and Status of every post.

There is also a helpful left sidebar that organizes all posts by Status and lists all connected Social Accounts, as well.

The list view is represented by four vertical lines in the upper-right corner.

The pivot view option provides a fully customizable grid table, where different measures of data can be added and analyzed.

The pivot view option provides numerous analytical options, allowing for in-depth, detailed analysis of various posts and metrics.

Click on any ➕ (plus sign) icon next to a line in the pivot table to reveal more metric options to add to the grid.

While in the pivot view, the option to Insert in Spreadsheet is available, located to the right of the Measures drop-down menu, in the upper-left corner of the Social Posts page.

Next to the Insert in Spreadsheet are three options, specific to the pivot view.

From left to right, those options are:

  * Flip Axis, which switches the _X_ and _Y_ axis in the grid table.

  * Expand All, which expands each line in the grid, revealing more detailed information related to it.

  * Download, which, when clicked, instantly downloads the pivot table as a spreadsheet.




### Messaggi¶

Clicking on a post from a social media stream reveals a pop-up window, showcasing the content of that specific post, along with all the engagement data related to it (e.g. likes, comments, etc.).

If desired, the user can leave a new comment of the post from the post’s pop-up window, by typing one in the Write a comment… field, and clicking Enter to post that comment.

### Create leads from comments¶

Odoo _Social Marketing_ also provides the ability to create leads directly from social media comments.

To create a lead from a comment left on a social media post, click on the desired post from the dashboard to reveal that post’s specific pop-up window. Then, scroll to the desired comment, and click the three vertical dots icon to the right of that comment.

Doing so reveals a drop-down menu with the option: Create Lead.

Upon clicking Create Lead from the comment’s drop-down menu, a Conver Post to Lead pop-up window appears.

In this pop-up window, select to either: Create a new customer, Link to an existing customer, or Do not link to a customer.

Nota

If Link to an existing customer is selected, a new Customer field appears beneath those options, wherein a customer can be chosen to be linked to this lead.

Once the desired selection has been made, click the Convert button at the bottom of the Convert Post to Lead pop-up window. Doing so reveals a fresh lead detail form, where the necessary information can be entered and processed.

### Approfondimenti¶

When a social media account stream is added to the _Social Marketing_ dashboard, each stream also displays and links that specific social media platform’s KPIs (if the platform has them).

To get redirected to the statistics and metrics related to any social media account’s KPIs, click on the Insights link, located at the top of each stream.

Nota

In a multi-company environment, if not _all_ pages are selected, de-authentication happens.

For example, if the companies have 3 _Facebook_ pages, but only grant access to 1, and try to grant access to another at a later date, they will be de-authenticated, and access to the initial page’s insights/analytics will be lost.

So, be sure to add _all_ pages for _all_ companies in a multi-company environment to avoid this issue. If a page gets de-autenticated, simply remove the stream, and re-establish it.

## Create and post social media content¶

Odoo _Social Marketing_ offers the ability to create and post content for social media accounts directly through the application.

To create content for social media accounts, navigated to the Social Marketing app, and click New Post located in the upper-right corner of the _Social Marketing_ dashboard.

Or, navigate to Social Marketing app ‣ Posts and click the New button.

Either route reveals a blank social media post detail form that can be customized and configured in a number of different ways.

### Post detail form¶

The social media post detail form in Odoo _Social Marketing_ has many different configurable options available.

#### Azienda¶

If working in a multi-company environment, the first field in the Your Post section of the social media post detail form is Company. In this field, select the company that should be connected to this specific social media post.

#### Pubblica su¶

If working in a single-company environment, the first field in the Your Post section of the social media post detail form is Post on. In this field, determine which social media outlets (streams) this post is intended to be posted on, and/or which website’s visitors this post should be sent to, via push notification, by checking the box beside the desired option(s).

Odoo automatically provides every available social media account that’s been linked to the database as an option in this section. If a social media account hasn’t been added as a stream to the _Social Marketing_ application, it will **not** appear as an option on the post template.

Multiple social media outlets (streams) and websites can be selected in the Post on field. At least **one** option in the Post on field _must_ be selected.

Importante

In order for the Push Notification option to appear on the social media post detail form in Odoo _Social Marketing_ , make sure the _Enable Web Push Notifications_ feature is enabled in the _Website_ app.

To do that, navigate to Website app ‣ Configuration ‣ Settings, activate Enable Web Push Notifications, fill out the corresponding fields, and click Save.

#### Messaggio¶

Next, there’s the Message field. This is where the main content of the post is created.

In the Message field, type in the desired message for the social post. After typing, click away from the Message field to reveal visual samples of how the post will look on all the previously selected social media accounts (and/or websites, as push notifications).

Suggerimento

Emojis can also be added directly to the text in the Message field. Just click the 🙂 (smiley face) icon, located on the line of the Message field to the far right. Clicking this icon reveals a drop-down menu containing numerous emojis to choose from.

Nota

If Twitter is chosen in the Post on field, a character counter appears beneath the Message field.

#### Allega immagini¶

If images are to be used in the post, click the Attach Images button, in the Attach Images field, located beneath the Message field. When clicked, Odoo reveals a pop-up window. In this pop-up window, select the desired image from the hard drive, and upload it.

After successfully uploading and attaching the desired image, Odoo reveals a new preview of the social media post, complete with the newly-added image, on the right side of the detail form.

#### Campagna¶

Next, there is the Campaign field. This non-required field provides the options to attach this post to a specific marketing campaign.

To add this post to a pre-existing campaign, click the empty Campaign field to reveal a drop-down menu, containing all the existing campaigns in the database. Select the desired campaign from this drop-down menu to add this post to that campaign.

To create a new campaign directly from the social media post detail form, start typing the name of the new campaign in the blank Campaign field, and select either Create or Create and edit….

Clicking Create creates the campaign, which can be edited/customized later.

Clicking Create and edit… creates the campaign, and reveals a Create Campaign pop-up form, wherein the Campaign Identifier, Responsible, and Tags can be instantly configured.

When all the desired settings have been entered, click Save & Close to save the campaign and return to the social media post detail form.

#### Quando¶

Then, in the When field, choose either Send Now to have Odoo publish the post immediately, or Schedule later to have Odoo publish the post at a later date and time.

If Schedule later is selected, a new Scheduled Date field appears. Clicking the empty field reveals a pop-up calendar, in which a future date and time can be designated.

After selecting a desired date and time, click Apply. Then, Odoo will promptly publish the post at that specific date and time on the pre-detemined social media account(s).

Nota

If scheduling a post, the Post button at the top of the social media post detail form changes to Schedule. Be sure to click Schedule after completing the social media post detail form.

Doing so, locks in that specific date/time for Odoo to send the post, and it changes the status of the post to Scheduled.

#### Opzioni di notifiche push¶

If one (or multiple) [Push Notification] options are chosen in the Post on field, a specific Push Notification Options section appears at the bottom of the social media post detail form.

It should be noted that _none_ of these fields are required.

The first field in this section is Notification Title. In this field, there is the option to add a custom title to the push notification that will be sent.

To designate a specific page on the website that should trigger this push notification, enter that page’s URL in the Target URL field. Then, once a visitor reaches that specific page, Odoo will display the push notification.

Below that field is the option to add a custom Icon Image to the push notification. This is an icon that appears beside the push notification.

To upload a new image, click the ✏️ (pencil) icon when hovering over the Icon Image camera icon. Doing so reveals a pop-up window, in which the desired icon image can be located on the hard drive, and subsequently uploaded.

Once that’s complete, Odoo automatically updates the visual preview of how the icon appears on the push notification.

Nota

Next, if the post is scheduled to be posted later, there is the option to ensure the post is sent in the visitor’s timezone, by enabling the Local Time option. If enabled, Odoo will send it at the appropriate, pre-determined time, taking the visitor’s location into consideration.

Then, there is the Match all records field. This field provides the ability to target a specific group of recipients in the database, based on certain criteria, and can be applied to match all or any of the rules.

To utilize this field, click the \+ Add condition button, which reveals an equation-like rule field.

In this equation-like rule field, specifiy the specific criteria Odoo should take into account when sending this post to a particular target audience.

To add an additional rule, click the ➕ (plus sign) icon to the far-right of the rule.

To add a branch (series of additional rules based on the previous rule, to further specify a target audience), click the unique branch icon, located to the right of the ➕ (plus sign) icon.

Lastly, click the 🗑️ (trash can) icon to delete any rule.

The size of the specified target audience of recipients is represented by the number of Records displayed beneath the rules.

Vedi anche

[Social marketing campaigns](social_campaigns.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/social_marketing/social_posts.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](social_campaigns.html "Social marketing campaigns") |
  * [precedente](../social_marketing.html "Marketing social") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing social](../social_marketing.html) »
  * Social posts


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
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
  *[POS]: point of sale
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