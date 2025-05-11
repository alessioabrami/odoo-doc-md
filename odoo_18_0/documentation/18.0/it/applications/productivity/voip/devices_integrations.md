# Devices and integrations — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales_calls.html "Sales calls with VoIP") |
  * [precedente](voip_widget.html "VoIP actions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * Devices and integrations



# Devices and integrations¶

VoIP can be used on many different devices, such as a computer, tablet, mobile phone, and many more. This is helpful in that it reduces costs, and employees can work from anywhere in the world, so long as they have a broadband internet connection.

Odoo _VoIP_ is SIP (Session Initiation Protocol) compatible, which means it can be used with _any_ SIP compatible application.

This document covers the process of setting up Odoo _VoIP_ across different devices and integrations.

Odoo is fully-integrated with all Odoo apps, allowing users to click into any app, and schedule a call as an activity in the chatter.

Example

For example, in the _CRM_ app, a user can click into an opportunity, and click on Activities in the chatter.

Next, they can choose Call, and under Due Date, they can select a date.

Once they click Save, an activity shows up in the chatter.

Should the Due Date be for today’s date, the activity shows up in the VoIP widget.

## Odoo VoIP (laptop/desktop computer)¶

The Odoo _VoIP_ (Voice over Internet Protocol) module and widget can be used from any browser on a laptop or desktop device. Simply click on the ☎️ (phone) icon in the upper-right corner, while in the Odoo database, and the widget appears.

Vedi anche

To see how to use the VoIP widget on a desktop/laptop computer, check out this documentation: [VoIP actions](voip_widget.html).

## Odoo VoIP (tablet/mobile device)¶

The Odoo _VoIP_ app can be used on tablets and mobile phones, through the Odoo Android or Apple IOS applications. Additionally, a mobile web browser can be used to access the database.

Avvertimento

Odoo Android and Apple IOS applications are no longer being maintained by Odoo on the Android and Apple portals. This means Odoo support only handles limited scopes of Odoo Android or Apple IOS support tickets.

Importante

While outgoing calls can be placed using Odoo on a mobile device, be aware that Odoo is **not** a full VoIP application, and does **not** ring on incoming calls. If the user needs to be reachable on a mobile device at all times, an app, like Zoiper, should be used. Apps like that stay connected in the background at all times.

For more information, see this documentation: Zoiper Lite.

While in the mobile application on a mobile device/tablet, access the Odoo _VoIP_ widget, by tapping on the ☎️ (phone) icon in the upper-right corner. The widget appears in the lower-left corner.

When first making a call from the tablet using the mobile application, the user is prompted to Allow the database to use the microphone. Click Allow when prompted to continue with the call using the microphone.

This step is **necessary** , whether using the mobile Odoo application or web browser.

Odoo then asks how to make the call. The two options are : VOIP or Phone (should the tablet be enabled for calling). Click the box next to Remember ? should this decision be the default moving forward.

Here is the layout of what the Odoo _VoIP_ app looks like on a mobile device:

## Zoiper Lite¶

_Zoiper Lite_ is a free VoIP SIP dialer with voice and video.

To start using the _Zoiper_ app, download it to the device, via the [Zoiper download page](https://www.zoiper.com/en/voip-softphone/download/current).

A mobile device is the most common installation, and this document covers how to set up on the _Zoiper_ IOS application. Screenshots and steps may differ depending on the set up conditions.

After installing the _Zoiper_ application on the mobile phone, open the application, and tap on Settings. Navigate to Accounts, and tap on the \+ (plus) icon to add an account.

If the VoIP account is already set up, then click Yes. This means an account username and password has already been produced.

Next, tap on Select a provider. On the screen that populates, tap Country, in the upper-right corner, to narrow the providers down to a specific country. Choose the country for the provider that is being configured, then find the Provider, and select it.

Example

If the provider being configured is _Axivox_ , then select Belgium. Then, choose Axivox as the provider.

Under SIP options, enter the Account name, Domain, Username, and Password. All this information varies, based on the account.

Suggerimento

To access this information, via the _Axivox_ portal, navigate to Users ‣ Choose user ‣ Edit ‣ SIP Identifiers tab. The SIP username, Domain, SIP password, and Address of the proxy server are all present in this tab.

Zoiper Field | Axivox Field  
---|---  
Nome conto | _Can be anything_  
Dominio | Dominio  
Nome utente | SIP username  
Password | SIP password  
  
Once this account information is entered, click the green Register button at the top of the screen. Once the registration information is checked, _Zoiper_ populates a message, stating Registration Status: OK.

At this point, _Zoiper_ is now set up to make phone calls using the VoIP service.

## Linphone¶

_Linphone_ is an open-source VoIP SIP softphone, used for voice, video, messaging (group and individual), as well as conference calls.

To start using the _Linphone_ app, download it to the device, via the [Linphone download page](https://new.linphone.org/technical-corner/linphone?qt-technical_corner=2#qt-technical_corner).

A mobile device is the most common installation, and this document covers how to set up the _Linphone_ IOS application. Screenshots and steps may differ depending on the circumstances.

To begin configuring _Linphone_ for use with a SIP provider, first open _Linphone_ , and an assistant screen appears.

From this screen, select Use SIP Account. Then, on the following screen, enter the Username, Password, Domain, and Display Name. Once complete, press Login.

At this point, _Linphone_ is ready to start making calls, once there is a green button at the top of the application screen that reads, Connected.

Suggerimento

 _Linphone_ makes a variety of applications for mobile and desktop devices in operating systems, such as Windows, Linux, Apple, and Android. Because _Linphone_ is an open-source project, many new updates are released on a regular basis.

See [Linphone’s wiki-documentation page](https://wiki.linphone.org/xwiki/wiki/public/view/Linphone/).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/productivity/voip/devices_integrations.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales_calls.html "Sales calls with VoIP") |
  * [precedente](voip_widget.html "VoIP actions") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * Devices and integrations


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