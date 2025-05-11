# Manage unsubscriptions (blacklist) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lost_leads_email.html "Lost leads reactivation email") |
  * [precedente](mailing_lists.html "Mailing lists") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Manage unsubscriptions (blacklist)



# Manage unsubscriptions (blacklist)¶

Providing recipients with the power to unsubscribe from mailing lists is not only a smart business practice, it’s often a legal requirement. Allowing recipients to unsubscribe from a mailing list establishes a sense of trust and control with an audience. It also helps companies appear more genuine, and less _spammy_.

## Unsubscribe and blacklist¶

In addition to having the option to unsubscribe from specific mailing lists, the recipient can also _blacklist_ themselves during the unsubscription process, meaning they will not receive _any_ more marketing emails from the Odoo database.

In order to provide recipients with the ability to blacklist themselves, a specific feature **must** be enabled in the _Email Marketing_ application.

Navigate to Email Marketing app ‣ Configuration ‣ Settings, and tick the checkbox next to the Blacklist Option when Unsubscribing feature. Then, click Save in the upper-left corner of the Settings page.

### Annulla iscrizione¶

By default, an _Unsubscribe_ link appears at the bottom of all mailing templates.

Avvertimento

The _Unsubscribe_ link does **not** appear by default if the _Start From Scratch_ template is used to create a mailing. The user **must** manually add the specific unsubscribe link `/unsubscribe_from_list` in the body of the email, or use a block from the _Footers_ section of the email builder, which includes the unsubscribe link.

If a recipient clicks the _Unsubscribe_ link in a mailing, Odoo instantly unsubscribes them from the mailing list, presents them with a Mailing Subscriptions page where they can directly manage their subscriptions, and informs them that they’ve been Successfully Unsubscribed.

Beneath that, Odoo asks the former subscriber to Please let us know why you updated your subscription, and the user can proceed to choose the appropriate opt-out reason from a series of options presented to them.

Nota

The opt-out answer options can be created and modified by navigating to Email Marketing app ‣ Configuration ‣ Optout Reasons.

Once they’ve chosen the appropriate opt-out reason from the options presented to them, they can click the Send button. Odoo then logs their reasoning for unsubscribing in the _Email Marketing_ app for future analysis.

### Lista nera¶

For a recipient to remove (i.e. blacklist) themselves from **all** marketing emails during the unsubscription process, on the Mailing Subscriptions page, they must click Exclude Me.

Upon clicking Exclude Me, Odoo informs the recipient they have been successfully blacklisted, with a message reading: ✔️ Email added to our blocklist.

Beneath that, Odoo asks the former subscriber to Please let us know why you want to be added to our blocklist, and the user can proceed to choose the appropriate reason from a series of options presented to them.

Once they’ve chosen the appropriate reason from the options presented to them, they can click the Send button. Odoo then logs their reasoning for blacklisting themselves in the _Email Marketing_ app for future analysis.

## Blacklisted email addresses¶

To view a complete list of all blacklisted email addresses, navigate to Email Marketing app ‣ Configuration ‣ Blacklisted Email Addresses.

When a blacklisted record is selected from this list, Odoo reveals a separate page with the recipient’s contact information, along with the provided Reason why they chose to blacklist themselves.

In the _chatter_ of the blacklisted record page, there’s a time-stamped message, informing the user when the recipient blacklisted themselves (via a Mail Blacklist created log note).

Nota

Blacklisted emails are excluded from all marketing mailings, however, these emails can still receive transactional emails, such as order confirmations, shipping notifications, etc.

## Unblacklist contacts¶

To _Unblacklist_ contacts, click the Unblacklist button in the upper-left corner of a blacklisted record’s page to remove the contact from the blacklist, allowing them to receive mailings once again.

When Unblacklist is clicked, an Are you sure you want to unblacklist this Email Address? pop-up window appears.

In this pop-up window, the email address of the selected blacklisted record is shown, and there’s a Reason field, in which a reason can be entered, explaining why this particular contact was removed from the blacklist.

After filling in the fields, click Confirm to officially remove that particular contact from the blacklist.

Vedi anche

  * [Marketing via e-mail](../email_marketing.html)

  * [Mailing lists](mailing_lists.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/email_marketing/unsubscriptions.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lost_leads_email.html "Lost leads reactivation email") |
  * [precedente](mailing_lists.html "Mailing lists") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Manage unsubscriptions (blacklist)


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