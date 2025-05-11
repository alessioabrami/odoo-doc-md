# Livechat — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](livechat/ratings.html "Valutazioni") |
  * [precedente](blog.html "Blog") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * Livechat



# Livechat¶

Odoo **Live Chat** allows users to communicate with website visitors in real-time. With **Live Chat** , leads can be qualified for their sales potential, support questions can be answered quickly, and issues can be directed to the appropriate team for further investigation or follow up. **Live Chat** also provides the opportunity for instant feedback from customers.

## Enable Live Chat¶

The **Live Chat** application can be installed multiple ways:

  * Go to Apps application, search `Live Chat`, and click Install.

  * Go to the Helpdesk app ‣ Configuration ‣ Helpdesk Teams list view, select a team, and on the team’s settings page, click the checkbox next to Live Chat, under the Channels section.

  * In the Website app, go to Configuration ‣ Settings, scroll to the Email & Marketing section, check the box next to Livechat, and click Save.




Nota

After the **Live Chat** application is installed, a live chat _Channel_ is created, by default.

## Create live chat channels¶

To create a new live chat _Channel_ , go to Main Odoo Dashboard ‣ Live Chat app ‣ New. This opens a blank channel detail form. Enter the name of the new channel in the Channel Name field.

To configure the remaining tabs on the channel detail form (Operators, Options, Channel Rules, and Widget), follow the steps below.

Suggerimento

The channel detail form for any channel can be accessed by navigating back to the Website Live Chat Channels dashboard, via the breadcrumbs. Find the Kanban card for the appropriate live chat channel, hover over it, and then click on the __(vertical ellipsis) icon to open the drop-down menu. Click Configure Channel to open the channel detail form.

### Operators tab¶

_Operators_ are the users who act as agents and respond to live chat requests from customers. When a user is added as an operator in a live chat channel, they can receive chats from website visitors wherever they are in the database. Chat windows open in the bottom-right corner of the screen.

On the channel detail form, click the Operators tab. The user who originally created the live chat channel has been added as an operator by default.

Nota

Current operators can be edited, or removed, by clicking on their respective boxes in the Operators tab, which reveals a separate Open: Operators modal. In that modal, adjust any information, as needed. Then, click Save, or click Remove to remove that operator from the channel.

Click Add to reveal an Add: Operators pop-up window.

In the pop-up window, scroll to find the desired users, or enter their name in the search bar. Then, tick the checkbox next to the users to be added, and click Select.

New operators can be created and added to the list directly from this pop-up window, as well, by clicking New, and filling out the Create Operators form. When the form is complete, click Save & Close, or Save & New for multiple record creations.

Pericolo

Creating a new user can impact the status of an Odoo subscription, as the total number of users in a database counts towards the billing rate. Proceed with caution before creating a new user. If a user already exists, adding them as an operator will **not** alter the subscription or billing rate for a database.

### Options tab¶

The Options tab on the live chat channel detail form contains the visual and text settings for the live chat window.

#### Livechat button¶

The _Livechat Button_ is the icon that appears in the bottom-right corner of the website.

Change the text in the Notification text field to update the greeting displayed in the text bubble when the live chat button appears on the website.

The Livechat Button Color alters the color of the live chat button as it appears on the website. To change the color, click on a color bubble to open the color selection window, then click and drag the circle along the color gradient. Click out of the selection window once complete. Click the __(refresh) icon to the right of the color bubbles to reset the colors to the default selection.

Suggerimento

Color selection, for the button or header, can be made manually using a slider or through RGB, HSL, or HEX color code entries from the pop-up color selection window that appears when either of the color bubbles are clicked. Different options are available, depending on the operating system.

#### Finestra chat dal vivo¶

The _Livechat Window_ is the space where the live chat conversation with website visitors takes place.

Edit the Welcome Message to change the message a visitor sees when they open a new chat session. This message appears as though it is sent by a live chat operator, and acts as both a greeting and an invitation to continue the conversation.

Edit the Chat Input Placeholder to alter the text that appears in the box where visitors type their replies. This message prompts the visitor to initiate the chat.

The _Channel Header_ is the colored bar at the top of the chat window. The Channel Header Color can be changed following the same steps as the Livechat button.

The live chat window with a purple channel header and placeholder text that reads, «Say Something…»¶

### Channel Rules tab¶

To configure which website user actions open the live chat window, go to the Channel Rules tab on the live chat channel detail form.

To create a new channel rule, click Add a line. This opens the Create Rules pop-up window.

#### Create new rules¶

Fill out the fields on the Create Rules pop-up window as instructed below, then click Save & Close.

Live Chat ButtonChatbotURL RegexOpen automatically timerCountry

The _Livechat Button_ is the icon that appears in the bottom-right corner of the website. Select from one of the following display options:

  * Show: displays the chat button on the page.

  * Show with notification: displays the chat button, as well as a floating text bubble next to the button.

  * Open automatically: displays the button, and automatically opens the chat window after a specified amount of time (designated in the Open automatically timer field, that appears when this option is selected).

  * Hide: hides the chat button on the page.




To include a [Chatbot](livechat/chatbots.html) on this channel, select it from the drop-down menu. If the chatbot should only be active when no operators are active, check the box labeled Enabled only if no operator.

The Enabled only if no operator field is **only** visible if a chatbot is selected in the Chatbot field.

The _URL Regex_ specifies the web pages where this rule should be applied. In the URL Regex field, input the relative URL of the page where the chat button should appear.

For example, to apply the rule to the URL, `https://mydatabse.odoo.com/shop`, enter `/shop` to the URL Regex field.

To apply the rule to _all_ pages on the database, enter `/` in the URL Regex field.

This field designates the amount of time (in seconds) a page should be open before the chat window opens. This field **only** appears if the Live Chat Button for this rule is set to Open automatically.

If this channel should **only** be available to site visitors in specific countries, add them to the Country field. If this field is left blank, the channel is available to all site visitors, regardless of location.

Nota

In order to track the geographical location of visitors, _GeoIP_ **must** be installed on the database. While this feature is installed by default on _Odoo Online_ databases, _On-Premise_ databases require additional [setup steps](../../administration/on_premise/geo_ip.html).

### Widget tab¶

The Widget tab on the live chat channel detail form provides the code for a website widget. This code can be added to a website to provide access to a live chat window.

Suggerimento

The live chat widget can be added to websites created through Odoo by navigating to Website app ‣ Configuration ‣ Settings. Then, scroll to the Email & Marketing section. In the Channel field, select the channel to add to the site. Click Save to apply.

To add the widget to a website created on a third-party platform, click the first COPY button on the Widget tab, and paste the code into the `<head>` tag on the site.

Likewise, to send a live chat session to a customer, click the second COPY button on the Widget tab. This link can be sent directly to a customer. When they click the link, they are redirected to a new chat window.

Vedi anche

  * [Comunicazioni](../productivity/discuss.html)

  * [Commands and canned responses](livechat/responses.html)

  * [Valutazioni](livechat/ratings.html)

  * [Chatbot](livechat/chatbots.html)

  * [Participate in live chat](livechat/participate.html)




  * [Valutazioni](livechat/ratings.html)
  * [Commands and canned responses](livechat/responses.html)
  * [Chatbot](livechat/chatbots.html)
  * [Report](livechat/reports.html)
  * [Participate in live chat](livechat/participate.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/livechat.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](livechat/ratings.html "Valutazioni") |
  * [precedente](blog.html "Blog") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Siti web](../websites.html) »
  * Livechat


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
  *[CSV]: Valori separati da virgola
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement