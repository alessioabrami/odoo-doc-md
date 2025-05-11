# Valutazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](responses.html "Commands and canned responses") |
  * [precedente](../livechat.html "Livechat") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Valutazioni



# Valutazioni¶

At the end of a _Live Chat_ conversation, customers have the opportunity to rate the quality of support they received from the live chat _operator_. Customers provide ratings as soon as they close the conversation. This allows operators to receive immediate feedback on their performance. It also allows customers the chance to share any final comments before leaving the chat window.

## Rate live chat conversations¶

Customers end a _live chat_ conversation by clicking the X in the upper right-hand corner of the chat window. They are then prompted to select an icon that reflects their level of satisfaction. The icons represent the following ratings:

>   * **Satisfied** \- _green smiling face_
> 
>   * **Okay** \- _yellow neutral face_
> 
>   * **Dissatisfied** \- _red frowning face_
> 
> 


Nota

When customers end a conversation, a field marked Receive a copy of this conversation appears under the _ratings_ icons. Customers can enter their email either before or after they submit a rating.

If the customer selects Satisfied (smile) icon, they are presented with a thank you message and a Close Conversation link.

If the customer selects either Okay (neutral) icon or Dissatisfied (frown) icon, a text box will appear. Customers can add comments in this text box to explain why they chose this rating. This message will be sent to the live chat operator, along with the rating icon.

## Publish customer ratings¶

To publish a channel’s ratings on the website, first navigate to a live chat channel’s record by going to the Live Chat app and clicking on the kanban card for that team. Then click on the Go to Website smart button. This will open the Live Chat Channel Statistics page.

In the upper right corner of the page, click the red Unpublished slider. The slider changes from Unpublished to Published.

Nota

The customer notes that are submitted with the rating will _not_ be published on the website. These are kept internal. Only a statistical overview of the operators” performance for the _channel_ appears on the website.

### Add ratings page to site¶

Once the rating page has been published, it has to be manually added to the website. To do this, go to the main Odoo dashboard and open the _Website_ application. Website app‣ Site ‣ Content ‣ Pages, then click New.

This will open a New Page pop-up window. In the Page Title field, enter `livechat`. This acts as the URL for the published webpage.

Importante

The URL _must_ be named `livechat` in order for the database to recognize and connect the ratings page. After the page has been published, the page title can be changed later under the Menu Editor.

Click Create, and the newly created webpage will open. The Webpage Editor appears in the right panel.

The page lists the names of the Live Chat Channels whose ratings pages have been published. On the left side of the channel name is a speech bubble icon, which users can click on to go to the ratings” page for the respective channel.

Make any desired changes or additions to this page, then click Save in the top right of the webpage editor. The website editor side panel closes, and the webpage remains on the screen.

To publish the `livechat` webpage, return to the list of webpages by navigating to Site ‣ Content ‣ Pages. Click the checkbox to the left of `livechat` in the list of pages to select the page and highlight the line. Then, click the checkbox under the column labeled Is Published. The field with the checkbox is highlighted in white. Click the checkbox a second time to activate the Is Published box. The webpage is now published.

Once the page has been added to the site, ratings are set to be published by default. However, individual ratings can be manually selected to be hidden from the public. The rating will still be included in internal reports, and can still be viewed by internal teams. However, public website visitors and portal users will not have access.

See Hide individual ratings for more information.

## Customer ratings report¶

The Customer Ratings report (Live Chat ‣ Report ‣ Customer Ratings) displays an overview of the ratings received on individual support tickets, as well as any additional comments submitted with the rating.

The report defaults to a kanban view, with each rating represented by a different card. To switch to a different view, click on one of the icons in the upper-right corner of the screen. The report is available in _list_ view, _pivot_ view, and _graph_ view.

Click on an individual rating to see additional details about the conversation, and the rating.

### Hide individual ratings¶

Ratings are set to be published by default. However, individual ratings can be manually selected to be hidden from the public. The rating will still be included in internal reports, and can still be viewed by internal teams. However, public website visitors and portal users will not have access.

To hide a rating, go to Live Chat app ‣ Reports ‣ Customer Ratings. Click on the kanban card for the rating to be hidden. On the individual rating’s detail page, check the box labeled Visible Internally Only.

Vedi anche

  * [Livechat](../livechat.html)

  * [Commands and canned responses](responses.html)

  * [Sito web](../website.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/livechat/ratings.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](responses.html "Commands and canned responses") |
  * [precedente](../livechat.html "Livechat") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Valutazioni


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
  *[URL]: Uniform Resource Locators
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
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing