# Mailing lists and blacklists — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pricing_and_faq.html "SMS Pricing and FAQ") |
  * [precedente](marketing_campaigns.html "SMS campaign settings") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * Mailing lists and blacklists



# Mailing lists and blacklists¶

Creating or importing mailing lists in Odoo is very useful when curating content to specific groups of people that already share similar demographics or interests. Mailing lists are also a great way to get started if a company is migrating from another system, and already has a established audience.

Moreover, providing an audience with the option to “unsubscribe” from mailings, helps businesses maintain good customer relations, by giving recipients the power to control what they are (and aren’t) sent.

## Mailing lists¶

In the SMS Marketing app, there’s an option on the header menu called Mailing Lists. When clicked, a sub-menu is revealed with options for Mailing Lists and Mailing List Contacts.

Click Mailing Lists ‣ Mailing Lists to see an overview of all mailing lists in the database.

To edit any existing list, select the desired list from the Mailing Lists page, and proceed to modify it in a number of ways.

To create a new mailing list, click Create in the upper left corner of the Mailing Lists page. Doing so, will reveal a blank mailing list template form.

First, choose a name for the Mailing List, and activate the option Is Public, to make the mailing list accessible to recipients on the Subscription Management page. Doing so allows users to update their subscription preferences at any time.

Nota

Checking the Is Public box is not required, but is recommended to maintain good customer relations.

When those fields are filled in, click Create to finalize the form. Then on the main Mailing Lists dashboard, the new mailing list that was just created will be accessible.

To edit or customize the mailing list further, select the mailing list from the main Mailing Lists page to reveal the mailing list detail form.

Along the top of the mailing list detail form, there are various analytical smart buttons displaying statistics for different metrics related to the mailing list (e.g. Recipients, Mailings, etc.).

To review or edit any of those elements, click the desired smart button to reveal a separate page with in-depth data associated with the mailing list.

To make changes to the mailing list itself, click the Edit button in the upper-left corner of the mailing list detail form.

Nota

Don’t forget to hit the Save button once changes have been made.

## Mailing lists contacts¶

Access contacts information from one or more mailing lists navigate to Mailing Lists ‣ Mailing List Contacts to reveal a dashboard with with all the contacts associated with one or more of the configured mailing lists in the database.

Nota

By default, Odoo reveals the Mailing List Contacts page with the Exclude Blacklisted Phone filter in the search bar. Therefore only showing contact information for recipients who still want to receive communications and mailings.

### Communication history in the Chatter¶

An accessible record of every sent mailing(s) is kept on each recipient’s _chatter_ section, located beneath a recipient’s contact form (in the _Contacts_ application).

Database users can reference the chatter to easily keep track of communications, and see a history of interactions with contacts and prospects.

For example, sales representatives can use the chatter to quickly find out which SMS mailing promotions a certain customer has received (or not received).

## Lista nera¶

Odoo _SMS Marketing_ has a Blacklist feature that provides recipients with the power to add their phone number to a list of people who no longer want to receieve communications or mailings.

This is also known as the unsubscribe process: customers will automatically be added onto a _blacklist_ , if they click Unsubscribe, via their Subscription Management page. Customers can also be added manually to the blacklist, if necessary.

To see a complete collection of blacklisted numbers, navigate to the SMS Marketing app ‣ Configuration ‣ Blacklisted Phone Numbers to reveal a dashboard containing every blacklisted phone number in the database.

To manually add a number to a blacklist, click the Create button in the upper-left corner of the dashboard and enter the phone number on the next page’s form. There’s also a checkbox to indicate whether that particular phone numnber is Active (or not).

Once the form is completed, click Save to add it to the Blacklisted Phone Numbers list. To remove any number from the blacklist, select the desired number on the dashboard, and then, on the phone number’s form, click Unblacklist.

### Importing blacklists¶

During a software/platform migration, it is possible to import an already existing blacklist of contacts. This would include customers, who have already asked to be blacklisted` on SMS mailings.

To do that, navigate to SMS Marketing app ‣ Configuration ‣ Blacklisted Phone Numbers, and then select the Favorites drop-down menu (beneath the search bar), and click Import records.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/sms_marketing/mailing_lists_blacklists.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pricing_and_faq.html "SMS Pricing and FAQ") |
  * [precedente](marketing_campaigns.html "SMS campaign settings") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * Mailing lists and blacklists


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