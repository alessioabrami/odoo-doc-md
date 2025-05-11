# Colli — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](packaging.html "Imballaggio") |
  * [precedente](uom.html "Unità di misura") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Colli



# Colli¶

A _package_ is a physical container holding one or more products. Packages can also be used to store items in bulk.

Packages are commonly used for the following purposes:

  1. Grouping products to move them in bulk.

  2. Shipping to customers: configure package types to align with shipping carriers” size and weight requirements, streamlining the packing process, and ensuring compliance with carrier shipping specifications.

  3. Storing items in bulk.




_Package use_ is a field on the package form in Odoo that is only visible by enabling the _Batch Transfers_ and _Packages_ features (Inventory app ‣ Configuration ‣ Settings).

By default, the _Package Use_ field on a packages form is set to _Disposable Box_. Change this field to _Reusable Box_ **only** when configuring packages for cluster pickings.

_Package type_ is an optional feature used for [calculating shipping cost](../../shipping_receiving/setup_configuration.html), based on real shipping weight. Create package types to include the weight of the package itself (e.g. boxes, pallets, other shipping containers) in shipping cost calculations.

Nota

While packages are commonly used in the [three-step delivery route](../../shipping_receiving/daily_operations/delivery_three_steps.html), they can be used in any workflow involving storable products.

## Configurazione¶

To use packages, first go to Inventory app ‣ Configuration ‣ Settings. Under the Operations heading, activate the Packages feature. Then, click Save.

When moving packages internally, the _Move Entire Packages_ feature can be enabled on an operation type to update a package’s contained item’s location upon updating the package’s location.

To do that, go to Inventory app ‣ Configuration ‣ Operations Types and select the desired operation this feature will apply to (may have to set it for multiple).

On the operation type page, in the Packages section, tick the Move Entire Packages checkbox.

## Pack items¶

Products can be added to packages in any transfer by:

  1. Clicking each Detailed Operations icon on the product line.

  2. Using the Put in Pack button to place everything in the transfer into a package.




### Detailed operations¶

On any warehouse transfer (e.g. receipt, delivery order), add a product to a package by clicking the ⦙≣ (bulleted list) icon in the Operations tab.

Doing so opens the Detailed Operations pop-up window for the Product.

To put the Product in a package, click Add a line, and assign the product to a Destination Package. Select an existing package, or create a new one by typing the name of the new package, then select Create….

Twelve units of `Acoustic Bloc Screen` are placed in `PACK0000001`.¶

Then, specify the quantity of items to go into the package in the Done column. Repeat the above steps to place the Product in different packages. Once finished, click Confirm to close the window.

Vedi anche

[Ship one order in multiple packages](../../shipping_receiving/setup_configuration/multipack.html)

### Put in pack¶

Alternatively, click the Put in Pack button on **any** warehouse transfer to create a new package, and place all the items in the transfer in that newly-created package.

Importante

The Put in Pack button appears on receipts, delivery orders, and other transfer forms with the _Packages_ feature enabled in Inventory app ‣ Configuration ‣ Settings.

In batch transfer `BATCH/00003`, the Put in Pack button was clicked to create a new package, `PACK0000002`, and assign all items to it in the Destination Package field.¶

## Tipologia collo¶

Create package types by navigating to Inventory app ‣ Configuration ‣ Package Types, in order to set custom dimensions and weight limits. This feature is mainly used to calculate package weights for shipping costs.

Vedi anche

  * [Shipping carriers](../../shipping_receiving/setup_configuration/third_party_shipper.html)

  * [Delivery methods](../../shipping_receiving/setup_configuration.html)




On the Package Types list, clicking New opens a blank package type form. The fields of the form are as follows:

  * Package Type (required): define the package type’s name.

  * Size: define the dimensions of the package in millimeters (mm). The fields, from left to right, define the Length, Width, and Height.

  * Weight: weight of an empty package (e.g. an empty box, pallet).




Nota

Odoo calculates the package’s weight by adding the weight of the empty package plus the weight of the item(s), which can be found in the Weight field, in the Inventory tab, of each product form.

  * Max Weight: maximum shipping weight allowed in the package.

  * Barcode: define a barcode to identify the package type from a scan.

  * Company: specify a company to make the package type available **only** at the selected company. Leave the field blank if it is available at all companies.

  * Carrier: specify the intended shipping carrier for this package type.

  * Carrier Code: define a code that is linked to the package type.




## Cluster packages¶

To use _cluster packages_ , first navigate to Inventory app ‣ Configuration ‣ Settings, and activate the Batch Transfers feature, located in the Operations section. Doing so makes the _Package Use_ field become visible on a package form.

Add new packages by going to Inventory app ‣ Products ‣ Packages. Then, click New, or select an existing package. Doing so opens the package form, which contains the following fields:

  * Package Reference (required): name of the package.

  * Package Type: used for configuring shipping boxes to ship to the customer.

Nota

Package Type is unnecessary for configuring packages for cluster pickings.

  * Shipping Weight: used to input the weight of the package after measuring it on a scale.

  * Company: specify a company to make the package available **only** at the selected company. Leave the field blank if the package is available at all companies.

  * Location: current location of the package.

  * Pack Date: the date the package was created.

  * Package Use: choose Reusable for packages used for moving products within the warehouse; Disposable for packages used to ship products to customers.




Vedi anche

[Using cluster packages](../../shipping_receiving/picking_methods/cluster.html)

## View packages¶

To view all packages go to Inventory app ‣ Products ‣ Packages. By default, packages are shown in Kanban view, in their current storage location.

Suggerimento

Drag-and-drop packages to move them between internal locations.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/configure/package.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](packaging.html "Imballaggio") |
  * [precedente](uom.html "Unità di misura") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Colli


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
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
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
  *[SO]: Sales Order
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In First Out
  *[FEFO]: First Expired, First Out
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