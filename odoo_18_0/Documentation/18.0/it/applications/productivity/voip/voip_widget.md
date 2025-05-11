# VoIP actions — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](devices_integrations.html "Devices and integrations") |
  * [precedente](axivox/call_queues.html "Call queues") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * VoIP actions



# VoIP actions¶

The VoIP widget is an add-on made available to Odoo users by installing the VoIP module. Instead of managing mobile devices for every salesperson, fumbling through call transfers for upset customers, or needing a meeting room to handle a conference call, utilize the VoIP widget to tackle any of these business needs.

## Navigate the VoIP widget¶

The VoIP widget contains three tabs: Recent, Next Activities, and Contacts, which are used for managing calls and day-to-day activities in Odoo. Use the search bar to find contacts faster.

### Recent tab¶

Under the Recent tab of the VoIP widget, the call history for the user is available. This includes incoming and outgoing calls. Any number can be clicked to begin a call.

### Next activities tab¶

Under the Next Activities tab of the VoIP widget, a user can see any calls assigned to them, and which ones are due to be completed for the day.

Click an activity from this tab to perform any of these actions to prepare for and complete (found under the **Documents** heading):

  * __(envelope): send an email to a contact (e.g., coworkers or clients)

  * __(user): shows the contact information for this contact

  * __(documents): shows the attached record in Odoo (like sales orders)

  * __(Activities): schedule an activity




When viewing the activity, the user can also manage the activity’s details and status:

  * __(check): marks the activity as complete

  * __(edit): edits the activity (like its due date)

  * __(close): cancels the activity




To call the customer related to a scheduled activity, click the __(phone) icon. Click the __(keyboard) icon to dial another number.

#### Add a call¶

From the database home page, click CRM app. On the Pipeline, make sure it is open to the Kanban view. Next, near the top of the screen, click the __ VoIP icon and make sure the VoIP widget is opened to the Next Activites tab. After that, hover over the opportunity that should have a call and click the __(phone) with the small green __ plus icon.

To remove a call from the Next activities tab, hover over the opportunity that has a call scheduled, and click the red __(phone) icon that appears with the __(minus) icon.

### Contacts tab¶

Under the Contacts tab of the VoIP widget, a user can access a contact in the **Contacts** app.

Any contact that has a saved phone number can be called by clicking into the contact from the VoIP widget’s Contacts tab.

A search feature is also available at the top of the widget, represented by a __(search) icon. Use this tool to find a specific contact. Scheduled activities will not appear as search results.

## Make a phone call with VoIP¶

One of the primary purposes of VoIP is to make phone calls without needing a phone. Here are the three ways to make a phone call in the Odoo database. First, click the __(VoIP) icon, located in the top-right of the navigation bar. From here:

  * Enter the phone number to be called by clicking the __(keyboard) icon, and then entering the phone number.

  * Click the __(phone) icon to redial the last called contact.

  * Search for a specific contact’s name or go to the Contacts tab. Then, select the contact and click the __(phone) icon.




When receiving calls in Odoo, the VoIP widget rings, and displays a notification. To close the widget, click the __(close) icon in the upper-right of the widget’s screen.

Nota

The VoIP number is the one provided by Axivox. It can be accessed by navigating to <https://manage.axivox.com/>. After logging into the portal, go to Users ‣ Outgoing number (column).

### Transfer a phone call¶

Manually transferring a call only happens when on a call. To transfer a call within the VoIP widget, first, answer the call using the green __(phone) icon.

Once the incoming call is answered, click the __(left-right arrows) icon. Then, enter the extension of the user the call should be forwarded to. Finally, click Transfer to route the call to that phone number.

Suggerimento

To find the extension for a user, consult the VoIP administrator. If the user has Administration access rights set to Settings, find extensions by going to Settings app and click the __ Manage Users button. Select the user, and go to the VoIP tab. That user’s extension is their VoIP username.

If the user does not pick up the call or is busy with another call, then calls can be automatically transferred. This gets configured with the VoIP service provider.

### Forward a phone call¶

To forward a call within the VoIP widget, first, answer the call using the green __(phone) icon.

Then, click the __(left-right arrows) icon. Enter the full phone number of the user the call should be forwarded to. Finally, click Transfer to route the call to that phone number.

## Send an email through the VoIP widget¶

Emails can also be sent through the VoIP widget. This is helpful for sending follow-up emails to the call participants, emailing a question to a coworker, or reminding a vendor to send over some components during a check-in call.

To send an email through the VoIP widget, click the __(VoIP) icon, located in the top navigation bar. When this is clicked, the VoIP widget will appear in the bottom-left corner of the page. Then, search for a contact to email or find them in the Contacts tab of the VoIP widget.

Next, click the __(envelope) icon, and then select the email recipients, enter the email’s subject line, and write the email. When it is ready to be sent, click Send. To schedule an email to send later, click the __(dropdown) icon next to Send, click Send Later, pick the scheduled time, and click Schedule.

## Troubleshooting the VoIP widget¶

Each section below goes through common issues with the VoIP widget and how to resolve them.

### Missing parameter¶

If a _Missing Parameter_ error message appears in the VoIP widget, refresh the window, and try again.

### Incorrect number¶

If an _Incorrect Number_ error message appears in the VoIP widget, make sure to use the international format, leading with the __(plus), followed by the international country code (e.g., +16506913277, where `+1` is the international prefix for the United States.)

### The websocket connection with the server has been lost¶

If a _The websocket connection with the server has been lost. Please try to refresh the page._ error message appears in the VoIP widget, then refresh the page close other browser tabs.

This error is caused by returning to the database after a period of inactivity, like lunch, or if there are too many browser tabs open.

### Failed to start the user agent¶

If a _Failed to start the user agent. The URL of the websocket may be wrong. Please have an administrator verify the websocket server URL in the General Settings._ error message appears in the VoIP widget, then update the browser and computer.

This error is caused by the browser or computer not being up-to-date (and can also cause issues with the microphone).

### Grayed-out VoIP widget¶

If the VoIP widget is completely grayed out and cannot be interacted with, then update the browser and computer, and delete the Google Chrome extension causing the problem.

### Cannot connect to the VoIP phone number¶

If the user cannot connect to their VoIP phone number, then their Odoo profile is missing their Voip Secret. To add this, click the user avatar, and then click My Profile. From here, click the VoIP tab, and then enter the user’s Voip Secret. This is the user’s password to their account for their VoIP service provider.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/voip/voip_widget.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](devices_integrations.html "Devices and integrations") |
  * [precedente](axivox/call_queues.html "Call queues") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * VoIP actions


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