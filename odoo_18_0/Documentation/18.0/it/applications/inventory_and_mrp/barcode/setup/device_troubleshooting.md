# Barcode device troubleshooting — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](hardware.html "Barcode scanner setup") |
  * [precedente](../setup.html "Imposta") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Imposta](../setup.html) »
  * Barcode device troubleshooting



# Barcode device troubleshooting¶

Odoo _Barcode_ supports three main types of barcode scanners: USB scanners, bluetooth scanners, and mobile computer scanners. While configuring each type of scanner, common issues may arise, in which the scanners do not work as intended, and Odoo returns errors to the device.

Read the sections below to identify general and unique device issues, related to specific, popular types of scanners.

## General issues¶

Refer to the following sections below for common issues involving popular barcode scanner devices.

For issues related to specific devices, refer to the Android scanners section for mobile computer scanners, or to the Screenless scanners section for USB and bluetooth scanners.

### Barcode cannot be read¶

One common issue encountered when using barcode scanners is an error resulting from barcodes that cannot be read.

This can occur due to any of the following reasons:

  * The barcode is damaged.

  * The device cannot read the required barcode type (some scanners can only read 2D barcodes).

  * The barcode being scanned is on a screen. Some scanners don’t support this, and the barcodes **must** be printed out to be scanned. This is most common with 1D barcodes.

  * The device has no battery, or is broken. To rule this out, follow the troubleshooting instructions in the following sections.




### Odoo returns barcode error¶

All types of barcode scanners have their own device «language», which affects how they output barcode data to Odoo’s _Barcode_ app. Sometimes, this can cause Odoo _Barcode_ to return a barcode error after scanning. This could be due to any of the following reasons:

  * The computer is configured with a different keyboard layout than the barcode scanner. To rule this out, ensure that the device is configured with the same keyboard layout.

For example, if the computer is configured to use an FR-BE keyboard, configure the scanner to send FR-BE keystrokes. The same logic applies if using a tablet instead of a computer.

For more information on configuring keystrokes, refer to the [Barcode scanner setup](hardware.html) documentation.

  * For mobile computer scanners (such as Zebra devices, for example), the scanner might interpret the barcode differently than intended. To rule this out, scan a test barcode to see how the scanner interprets the barcode.




## Android scanners¶

The most recent barcode scanner models using Android and Google Chrome should work with Odoo. However, due to the variety of models and configurations, it is recommended to first test a scanner’s compatibility with Odoo.

The Zebra product line is recommended; specifically, the **Zebra TC21 (WiFi-only)** , and **Zebra TC26 (WiFi/cellular)**.

Vedi anche

[Odoo Inventory & Barcode compatible hardware](https://www.odoo.com/app/inventory-hardware)

### Barcode app does not give feedback¶

By default, Android barcode scanners pre-process the barcode, then send a full text. Since Odoo _Barcode_ does not read this type of output, settings for each type of scanner **must** be configured correctly.

Odoo _Barcode_ expects that the scanner works like an analogue keyboard, and so, only detects _key events_. Refer to the following sections for configuration settings for the most popular devices.

### Zebra TC21/TC26¶

When using Zebra scanners, ensure the following keystroke configurations are set to prevent errors.

Begin on the Zebra scanner’s home screen, and select the DataWedge app (the app is represented by a (light blue barcode) icon).

On the DataWedge Profiles page, select the profile option to access the Zebra scanner’s settings.

Once the profile is selected, scroll down to the Keyboard Output option, and ensure the Enable/disable keystroke output option is Enabled.

Once that option is enabled, go back to the Profile options page, and go to the Keystroke output section. Then, open the Key event options submenu. Under Characters, ensure the Send Characters as Events option is checked.

Importante

The Send Characters as Events option **must** be checked on the Zebra scanner, or Odoo **cannot** recognize the barcodes that are scanned.

Once the above steps have been taken, perform a test scan to ensure the Zebra scanner is working as intended.

### MUNBYN Android devices¶

When using MUNBYN Android scanners, ensure the following configurations are set to prevent errors.

From the device’s home screen, click AppSettings. On the resulting page, locate the Process mode section, and select Keyboard input.

Suggerimento

The selected _Process mode_ controls how data is processed after barcode data has been read out.

_Keyboard input_ enters read-out data at the position of the cursor, the same as input data on an analogue keyboard would.

Once the above steps have been taken, perform a test scan to ensure the MUNBYN Android scanner is working as intended.

Why is there no data output in the app after a successful scan?

When scanning a barcode, the scanner might beep, indicating a successful scan, but there is no data output in the app.

To fix this issue, adjust the output method to _keyboard analogue_ in the _Scanner_ app on the device.

From the device’s home screen, click Scanner App ‣ Settings. From the Settings page, click Output Mode. The resulting pop-up window presents the different output options available to users. Select Keyboard Mode, then click OK.

Go back to the app that needs to be scanned, and click on the input dialog box first before scanning. Finally, perform a test scan to ensure the MUNBYN Android scanner is working as intended.

### Datalogic Android devices¶

When using Datalogic Android scanners, ensure the following configurations are set to prevent errors.

To view and configure all settings for the scanner, use the _Settings_ app on the Datalogic Android device. From the applications menu, select Settings ‣ System ‣ Scanner Settings.

From the resulting list of settings, select Wedge. From this menu, under the Keyboard wedge section, ensure that the Enable keyboard wedge feature is activated.

Then, also under the Keyboard wedge section, locate the Keyboard wedge input mode option. By default, the input mode is set to Text injection.

Click Keyboard wedge input mode, and change the setting to Key pressure. This ensures that scanned barcodes are translated into keyboard strokes, instead of being injected into the text area.

Once all those steps have been taken, perform a test scan to ensure the Datalogic Android scanner is working as intended.

## Screenless scanners¶

Screenless scanners are barcode scanning devices that have no screens. These include USB scanners and bluetooth scanners.

Importante

Odoo supports most USB and Bluetooth barcode scanners, as they all emulate a keyboard. However, to verify that a scanner is compatible with a specific keyboard layout (or can be configured to do so), refer to Odoo’s [Inventory & Barcode compatible hardware](https://www.odoo.com/app/inventory-hardware) documentation.

### NETUM devices¶

By default, the NETUM barcode scanner’s user manual only shows the French keyboard configuration. To use the Belgian keyboard, scan the code below:

Once that code has been scanned, ensure the NETUM scanner has the correct keyboard configuration, and is working as intended.

Vedi anche

  * [Barcode scanner setup](hardware.html)

  * [Product and location barcodes](software.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/barcode/setup/device_troubleshooting.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](hardware.html "Barcode scanner setup") |
  * [precedente](../setup.html "Imposta") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Imposta](../setup.html) »
  * Barcode device troubleshooting


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
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