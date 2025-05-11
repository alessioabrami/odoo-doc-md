# Adjust inventory with barcodes — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_deliveries.html "Process receipts and deliveries with barcodes") |
  * [precedente](../operations.html "Daily operations") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Adjust inventory with barcodes



# Adjust inventory with barcodes¶

An _inventory adjustment_ , or inventory audit, is the process of verifying the physical stock of products against the quantities recorded in the database. Regular audits ensure accurate inventory records, prevent stock discrepancies, and maintain efficient operations. In a warehouse setting, managers typically assign inventory counts to employees, who then walk to designated locations, scan product barcodes, and adjust quantities as needed.

Inventory adjustments can be completed through the **Barcode** application using a compatible scanner, or the Odoo mobile app.

Nota

For a list of Odoo-compatible barcode mobile scanners, and other hardware for the **Inventory** and **Barcode** apps, refer to the [Odoo Inventory • Hardware page](https://www.odoo.com/app/inventory-hardware).

Vedi anche

[Inventory adjustments](../../inventory/warehouses_storage/inventory_management/count_products.html)

Suggerimento

Odoo’s **Barcode** application provides demo data with barcodes to explore the features of the app. These can be used for testing purposes, and can be printed from the home screen of the app.

To access this demo data, navigate to the Barcode app and click demo data sheet or barcodes in the banner above the scanner.

## Assigning inventory counts¶

Before performing an inventory count, managers can [assign](../../inventory/warehouses_storage/inventory_management/count_products.html#inventory-plan-counts) counting tasks to employees. This can be done through Inventory app ‣ Operations ‣ Physical Inventory by selecting specific locations and products for counting, and assigning a User to them. Once assigned, users will see pending counts when they open the **Barcode** app.

To view a requested inventory count, navigate to the Barcode app dashboard. If a count has been requested, the number of products to be counted is listed on the Inventory count button.

## Configurazione¶

Before an inventory adjustment can be performed with the **Barcode** app, the app has to be installed, and configured. Navigate to Inventory app ‣ Configuration ‣ Settings, and scroll to the Barcode section. Tick the checkbox next to Barcode Scanner, and click Save to save any changes. If necessary, click Confirm on the pop-up.

Pericolo

Enabling the **Barcode** feature requires installing the **Barcode** application. Installing a new application on a One-App-Free database triggers a fifteen-day trial. At the end of the trial, if a paid subscription has not been added to the database, it will no longer be accessible.

After saving, a new drop-down menu appears under the Barcode Scanner option, labeled Barcode Nomenclature, where either Default Nomenclature or Default GS1 Nomenclature can be selected. Each nomenclature option determines how scanners interpret barcodes in Odoo.

To count products using barcodes, ensure that barcodes for products and storage locations are set up within Odoo first. Refer to this section for detailed instructions: [Set Product Barcodes](../setup/software.html#inventory-barcode-set-barcodes).

## Performing an inventory count¶

To perform an inventory adjustment, first navigate to the Barcode app. If assigned counts exist, tap Inventory Count to view pending tasks.

Walk to the designated storage location, then scan the location barcode.

Suggerimento

If the warehouse _multi-location_ feature is **not** enabled in the database, a source location does not need to be scanned. Instead, scan the product barcode to start the inventory adjustment.

Doing so highlights the location and displays all of the products stored there. Scan the barcode of each product to adjust its count.

Nota

If no counts have been assigned to a user, and the Count Entire Locations feature is **not** enabled, no products may appear after the location barcode is scanned.

Manually adjust quantities if necessary by tapping the __(edit) icon. Doing so opens a separate window with a keypad. Edit the number in the Quantity line to change the quantity. Additionally, the +1 and -1 buttons can be clicked to add or subtract quantity of the product, and the number keys can be used to add quantity, as well.

Example

In the below inventory adjustment, the source location `WH/Stock/Shelf 1` was scanned, assigning the location. Then, the barcode for the product `[FURN_7888] Desk Stand with Screen` was scanned three times, increasing the units in the adjustment. Additional products can be added to this adjustment by scanning the barcodes for those specific products.

### Count entire locations¶

The Count Entire Locations feature assigns a user to count all the products within a location once they scan the barcode for that location. This allows for easier cycle counts by assigning an entire location to a user by assigning a single product count. During cycle counts, users can ensure accurate inventory numbers, see if products that should be in a location are missing, or discover products incorrectly stored within a location.

To enable this feature, navigate to Inventory app ‣ Configuration ‣ Settings, and scroll to the Barcode section. Tick the Count Entire Locations checkbox, then click Save.

Importante

This setting is only visible if the Storage Locations checkbox is ticked.

To perform an inventory count of an entire location, navigate to Barcode app ‣ Inventory Count. Scan the desired location barcode. The app then displays all assigned products in that location. Proceed with the count as normal.

### Show quantity to count¶

When conducting an inventory count, the expected quantity of products is displayed by default, to provide the user with a baseline to use when performing the count. However, as this can result in users relying on this count instead of performing a new count, this quantity can be hidden.

Navigate to Inventory app ‣ Configuration ‣ Settings. In the Barcode section, clear the Show Quantity to Count checkbox, then click Save.

## Manually add products to an inventory count¶

When barcodes for location or products are not available, Odoo **Barcode** can still be used to perform inventory counts.

To do this, navigate to the Barcode app ‣ Inventory Count.

To manually add products to this adjustment, click the white Add Product button at the bottom of the screen.

This navigates to a new, blank page where the desired product, quantity, and source location must be chosen.

First, click the Product line, and choose the product whose stock count should be adjusted. Then, manually enter the quantity of that product, either by changing the `1` in the Quantity line, or by clicking the +1 and -1 buttons to add or subtract quantity of the product. The number pad can be used to add quantity, as well.

Below the number pad is the location line, which should read `WH/Stock` by default. Click this line to reveal a drop-down menu of locations to choose from, and choose the source location for this inventory adjustment.

Click Confirm to confirm the changes.

## Finalizing an inventory count¶

After counting all of the products, review the entries to ensure all the counted quantities are accurately entered. To complete the inventory adjustment, click Apply.

Suggerimento

The Validate barcode can be scanned in place of clicking the Apply button.

Odoo then navigates back to the Barcode Scanning screen. A small green banner appears in the top-right corner, confirming the inventory count has been updated.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/barcode/operations/adjustments.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](receipts_deliveries.html "Process receipts and deliveries with barcodes") |
  * [precedente](../operations.html "Daily operations") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Codice a barre](../../barcode.html) »
  * [Daily operations](../operations.html) »
  * Adjust inventory with barcodes


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