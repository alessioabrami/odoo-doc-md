# Mensa — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lunch/vendors.html "Fornitori") |
  * [precedente](referrals/reporting.html "Rendiconto") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Mensa



# Mensa¶

The _Lunch_ application in Odoo allows users a convenient way to order food and pay for their meal directly from the database.

Before employees can use the _Lunch_ application, there are a number of configurations to consider: settings, vendors, locations, products, product categories, and alerts. Once these are created, employees can view offerings and order food.

## Impostazioni¶

Only two settings are needed to configure in the _Lunch_ app: overdraft settings and notifications. To access the settings, navigate to Lunch app ‣ Configuration: Settings.

Configure the following:

  * Lunch Overdraft: enter the maximum overdraft amount for employees. The currency format is determined by the localization setting of the company.

  * Reception notification: set the message users receive via the _Discuss_ app when their food has been delivered. The default message `Your lunch has been delivered. Enjoy your meal!` populates this field, but can be modified, if desired.




Suggerimento

> If in a database with multiple languages installed, many forms in the _Lunch_ application have the option of entering translations for various fields.
> 
> If translations are available to be configured, a language code appears next to a translatable field on a form. To add translations for that field, click the two letter language code (for example, EN for English) and a translation pop-up window appears.
> 
> The following is an example for the Reception notification field in the settings menu:
> 
> Navigate to Lunch app ‣ Configuration: Settings. Click the EN In the top-right of the text box beneath the Reception notification section. A Translate: company_lunch_notify_message pop-up window loads with the option to enter a translation for the other languages used by the database.
> 
> The first column lists the different languages in alphabetical order, with the currently selected language in bold. The second column has the currently configured message in each column. The last column in the far-right provides a text box to type in a translation for each language.
> 
> Enter the text that should appear for each language, then click Save.

## Ubicazioni¶

By default, Odoo creates an `HQ Office` location when the _Lunch_ application is installed. If a company has more than one location, they must be configured.

To add a location, navigate to Lunch app ‣ Configuration: Locations. The currently configured locations appear in a list view. Click the New button in the top-left corner and a blank line appears beneath the last location in the list.

Enter the name of the location in the field. Next, click into the Address field to the right of the name, and enter the location’s address. It is possible to enter multiple lines in the address field.

Repeat this for all locations that need to be added.

## Avvisi¶

It is possible to set up alerts that can either be displayed in the _Lunch_ app, or be sent to specific employees via the _Discuss_ app.

No alerts are pre-configured by default. To set up an alert, navigate to Lunch app ‣ Configuration: Alerts. Click the New button in the top-left corner and a blank lunch alert form loads. Enter the following information on the form:

  * Alert Name: enter a name for the alert. This should be short and descriptive, such as `New Lunch Vendor` or `Order by 11`. This field is **required**.

  * Display: select whether the alert is visible in the _Lunch_ app (Alert in app) or sent to employees via the _Discuss_ app in a chat window (Chat notification).

    * Recipients: this field only appears if Chat notification is selected for the Display option. Select who receives the chat alert. The options are: Everyone, Employee who ordered last week, Employee who ordered last month, or Employee who ordered last year.

  * Location: select the locations the alert should appear for from the drop-down menu. Multiple locations can be selected. This field is **required** , therefore, if the alert applies to all locations, select all the locations from the drop-down menu.

  * Show Until: if the alert should expire on a specific date, select the date from the calendar picker.

  * Active: this option is on (appears green) by default. To turn off the alert, click the toggle so that it no longer appears green.

  * Message: Enter the alert message in this field. This field is **required**.

  * Notification Time: select the days of the week the alert should be sent. By default, all seven days are active. Click on a checkbox to change the setting from active to inactive.

If Chat notification was selected for the Display option, a Time field also appears. Enter the time the chat message should be sent. Next, select if the time is either AM or PM using the drop-down menu to the right of the Time field.




Vedi anche

  * [Fornitori](lunch/vendors.html)

  * [Prodotti](lunch/products.html)

  * [Ordini](lunch/orders.html)

  * [Manage user accounts](lunch/user-accounts.html)

  * [Lunch management](lunch/management.html)




  * [Fornitori](lunch/vendors.html)
  * [Prodotti](lunch/products.html)
  * [Ordini](lunch/orders.html)
  * [Manage user accounts](lunch/user-accounts.html)
  * [Lunch management](lunch/management.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/lunch.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lunch/vendors.html "Fornitori") |
  * [precedente](referrals/reporting.html "Rendiconto") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Mensa


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
  *[POS]: Punto vendita
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