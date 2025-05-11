# Barcode scanner setup — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](software.html "Product and location barcodes") |
  * [precedente](device_troubleshooting.html "Barcode device troubleshooting") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Imposta](../setup.html) »
  * Barcode scanner setup



# Barcode scanner setup¶

Follow this guide to choose and set up a barcode scanner compatible with Odoo’s _Inventory_ and _Barcode_ apps.

## Scanner types¶

Before setting up a barcode scanner, it is important to determine which type of scanner best meets the needs of the business. There are three main types of scanners that can be used with Odoo, each with their own benefits and use cases:

  * **USB scanners** are connected to a computer, and are suitable for businesses that scan products at a fixed location, like at the checkout line in a grocery store.

  * **Bluetooth scanners** pair with a smartphone or tablet, making them both a cost-effective and portable barcode scanner option. In this scenario, Odoo is installed on the smartphone, allowing warehouse operators to handle operations, and check stock, directly through their mobile devices.

  * **Mobile computer scanners** are mobile devices with a built-in barcode scanner.

Importante

If using a USB scanner, ensure the scanner is compatible with the keyboard layout of the computer.

If using a mobile computer scanner, ensure the device can run the Odoo mobile app properly. Recent models that use Android OS with the Google Chrome browser, or Windows OS with Microsoft Edge, should work. However, testing is crucial due to the variety of available models and configurations.




Vedi anche

[Odoo Inventory & Barcode • Compatible Hardware](https://www.odoo.com/app/inventory-hardware)

## Configurazione¶

When setting up the barcode scanner, make sure the following configurations are correct so the scanner can properly interpret barcodes with Odoo.

### Keyboard layout¶

When using a USB barcode scanner, match its keyboard layout with the operating system’s layout for proper interpretation of characters. Generally, the scanning mode should be set to accept a USB keyboard (HID), with the language set based on the keyboard that is in use.

To configure the keyboard layout for a **Zebra** scanner, scan the keyboard wedge barcode for the desired language in the scanner’s user manual.

Examples of keyboard language settings in the Zebra scanner user manual.¶

### Automatic carriage return¶

Odoo has a default 100-millisecond delay between scans to prevent accidental double scanning. To synchronize with the barcode scanner, set it to include a _carriage return_ (character like the «Enter» key on a keyboard) after each scan. Odoo interprets the carriage return as the end of the barcode input; so Odoo accepts the scan, and waits for the next one.

Typically, on the scanner, a carriage return is included by default. Ensure it is set by scanning a specific barcode in the user manual, like `CR suffix ON` or `Apply Enter for suffix`.

## Zebra scanner¶

When using Zebra scanners, ensure the following keystroke configurations are set to prevent errors.

Begin on the Zebra scanner’s home screen, and select the DataWedge app (the app is represented by a (light blue barcode) icon).

On the DataWedge Profiles page, select the profile option to access the Zebra scanner’s settings.

Avvertimento

It is **not** suggested to use the «DWDemo» profile, as it does not work properly in every circumstance.

Instead, it is recommended to create a new, personal profile. Once a new profile is created, add the _Odoo Mobile_ app and _Google Chrome_ app in the Associated Apps on the scanner’s home screen.

Once the profile is selected, scroll down to the Keyboard Output option, and ensure the Enable/disable keystroke output option is Enabled.

Once that option is enabled, go back to the Profile options page, and go to the Keystroke output section. Then, open the Key event options submenu. Under Characters, ensure the Send Characters as Events option is checked.

Importante

The Send Characters as Events option **must** be checked on the Zebra scanner, or Odoo **cannot** recognize the barcodes that are scanned.

Once all those steps have been taken, perform a test scan to ensure the Zebra scanner is working properly, as intended.

## Honeywell mobile computer scanner¶

When using Honeywell scanners, follow the instructions below to ensure barcodes can be scanned in Odoo.

Begin on the Honeywell scanner’s home screen, and select Settings, represented by a ⚙️ (gear) icon. Then, click Honeywell Settings, followed by Scanning.

From here, click Internal Scanner, followed by Default Profile. From the resulting list of options, select Data Processing Settings.

The Data Processing Settings specify how barcode data is processed by the computer. Locate the Wedge Method setting. By default, this is set to Standard.

Change the Wedge Method setting to Keyboard.

After completing the steps, conduct a test scan to verify the Honeywell scanner is working as intended.

## Cipherlab mobile computer scanner¶

When using Cipherlab scanners, follow the instructions below to ensure barcodes can be scanned in Odoo.

Begin on the Cipherlab scanner’s home screen, and navigate to the App Drawer (All Applications). Then, click the ReaderConfig app, represented by an orange ⚙️ (gear) icon over a blue (barcode) icon.

Next, select the Default Profile, or create a new profile, if needed.

Under the General Settings, click Data Output, followed by Keyboard Emulation.

By default, the Input Method, under Keyboard Emulation, is set to Default Mode. Change this setting to KeyEvent.

After completing the steps, conduct a test scan to verify the Cipherlab scanner is working as intended.

Vedi anche

[Product and location barcodes](software.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/barcode/setup/hardware.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](software.html "Product and location barcodes") |
  * [precedente](device_troubleshooting.html "Barcode device troubleshooting") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Imposta](../setup.html) »
  * Barcode scanner setup


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