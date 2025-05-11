# Printable delivery PDFs — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dispatch.html "Dispatch management system") |
  * [precedente](multipack.html "Multi-package shipments") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Printable delivery PDFs



# Printable delivery PDFs¶

Automatically print delivery-related PDFs documents and labels in Odoo, containing package recipient details, contents, or handling instructions.

The following PDFs can be configured to print upon validating an _Inventory_ operation (e.g. receipt, picking, delivery orders, quality checks):

  1. Delivery slip

  2. Return slip

  3. Product labels of items in the order

  4. Lot and serial number labels

  5. Carrier labels

  6. Export documents

  7. Package content

  8. Package label




To automatically print these forms, navigate to Inventory app ‣ Configuration ‣ Operations Types, and select the desired operation type.

In the Hardware tab, tick each of the desired options available in the Print on Validation section to download the PDF of those selected documents automatically after validating the Operation Type. For details on what each of the checkbox options do, jump to the related section.

## Delivery slip¶

A _delivery slip_ contains recipient and package details, usually placed inside (or attached to) the package.

Vedi anche

  * [Tracking label](labels.html)




After enabling the Delivery Slip setting in the Hardware tab configuration options, clicking Validate on the desired operation type downloads a PDF of the delivery slip.

The delivery slip shows products, quantities, the delivery order reference number, and the total order weight.

## Buono di reso¶

Print a _return slip_ to include in a delivery for customer return packages. It identifies the return, links to the sales order, and includes item details and customer information. It can also include specific return instructions for the customer.

After enabling the Return Slip setting in the Hardware tab configuration options, clicking Validate on the desired operation type downloads a PDF of the return slip.

The return slip displays the company’s return address, along with barcodes for both the order and the return operation.

## Product labels¶

Print _product labels_ to affix to items in an order, providing essential information, such as product name, barcode, and price.

After navigating to the intended operation type (Inventory app ‣ Configuration ‣ Operations Types), in the Hardware tab, tick the Product Labels option.

Doing so makes the Print label as: drop-down menu visible, where each product label can be printed as:

  * 2 x 7 with price: PDF displays product name, barcode, and price, fitting two rows and seven columns of product labels per page.

Example 2 x 7

  * 4 x 7 with price: displays product name, barcode, and price, fitting four rows and seven columns of product labels per page.

Example 4 x 7

  * 4 x 12: displays product name and barcode. Fits four rows and twelve columns of product labels per page.

Example 4 x 12

  * 4 x 12 with price: displays product name, barcode, and price. Fits four rows and twelve columns of product labels per page.

  * ZPL Labels: prints labels in the Zebra Programming Language (ZPL) containing the product name and barcode. Readable for Zebra printers to automatically print labels.

  * ZPL Labels with price: prints labels in the ZPL containing the product name, barcode, and price.




Nota

Product labels can be manually printed from any delivery order, by clicking the Print Labels button.

## Etichette lotto/NS¶

Print _lot/SN labels_ to affix to items in an order, providing essential information, such as product name, lot or serial number, and the barcode.

To automatically print this PDF, navigate to the intended operation type’s options page (Inventory app ‣ Configuration ‣ Operations Types). Then, in the Hardware tab, tick the Lot/SN Labels option.

Doing so makes the Print label as: drop-down menu visible, where each product label can be printed as:

  * 4 x 12 - One per lot/SN: PDF with labels for unique lot/serial numbers in the order, including product name, lot/serial number, and barcode. Fits four rows and twelve columns per page.

Example 4 x 12 - One per lot/SN

Labels for an order with only one unique set of lot/serial numbers.¶

  * 4 x 12 - One per unit: PDF with labels matching the quantity of items, displaying the product name, lot/serial number, and barcode. Fits four rows and twelve columns per page.

  * ZPL Labels - One per lot/SN: prints labels in ZPL, containing the product name, lot/serial number, and barcode.

  * ZPL Labels - One per unit: prints labels with the quantity of items in ZPL, containing the product name, lot/serial number, and barcode.




## Carrier labels¶

To automatically print a _carrier label_ with the recipient address, tracking number, and carrier details for specific third-party shipping carriers, complete the following setup:

  1. Tick the Carrier Labels checkbox in the operation type settings.

  2. [Connect a printer](../../../../general/iot/devices/printer.html) to Odoo’s _IoT_ app.

  3. Assign the carrier label to the printer.

  4. Configure the shipping method’s label type.




### Assign printer¶

Refer to the [Connect a printer](../../../../general/iot/devices/printer.html) documentation for details on connecting a printer to Odoo’s _IoT_ app. Upon completion, assign the carrier label to the printer, by navigating to IoT app ‣ Devices, and selecting the desired printer.

In the printer configuration form, go to the Printer Reports tab to configure the types of documents the printer automatically prints. Click Add a line to open the Add: Reports pop-up window. In the Search… bar, type `Shipping`, and select Shipping Labels.

Nota

The Shipping Documents report is for export documents.

After adding the Shipping Labels report in the Printer Reports tab, ensure the Report Type matches the IoT-connected printer’s type.

  * For laser printers, set the Report Type to PDF.

  * For Zebra printers, set the Report Type to Text.




### Shipping carrier label type¶

Next, complete the setup for the [third-party shipping connector](third_party_shipper.html). After that, go to Inventory app ‣ Configuration ‣ Shipping Methods, and select the desired shipping method.

On the shipping method configuration form, in the [carrier name] Configuration tab, ensure the Label Format matches the report type assigned earlier:

  * For laser printers, set the Label Format to PDF.

  * For Zebra printers, set the Label Format to ZPL2.




### Example carrier label¶

After validating the operation, the carrier label is generated in the chatter, and printed using the IoT-connected printer.

Example carrier label

Carrier label for FedEx, containing the recipient address, tracking number, barcode, and other shipping information.¶

Vedi anche

[Print carrier labels](labels.html)

## Export document¶

An _export document_ , required by customs to ship packages from one country to another, can be automatically printed in Odoo by following these steps:

  1. Tick the Export Documents checkbox in the operation type settings.

  2. [Connect a printer](../../../../general/iot/devices/printer.html) to Odoo’s _IoT_ app.

  3. Assign the export document to the printer.




### Assign printer¶

Similar to the printer assignment instructions for carrier labels, after connecting a compatible printer to the Odoo _IoT_ app, go to IoT app ‣ Devices, and select the desired printer.

In the printer configuration form, go to the Printer Reports tab, and click Add a line. In the Add: Reports pop-up window that appears, add the Shipping Documents report to assign the export document to the printer.

Example export document

Export document for a shipment from the USA to Belgium.¶

## Package content¶

A _package content_ PDF includes the package’s barcode, packed date, along with a list of contained products and quantities.

To print this form automatically, go to Inventory app ‣ Configuration ‣ Operation Types, and select the desired operation type. Then, go to the Hardware tab, and tick the Package Contents checkbox.

Importante

If the option is not available, enable the [Packages](../../product_management/configure/package.html) feature, by going to Inventory app ‣ Configuration ‣ Settings, ticking the Packages checkbox, and clicking Save.

After enabling the feature in the Hardware tab, validating the operation prints a PDF of the package contents.

Example package content PDF

Package contents showing the package contents, barcode, and pack date.¶

## Package label¶

A _package label_ that shows the package’s barcode and pack date can be configured to print upon clicking the _Put in Pack_ button.

Importante

The Put in Pack button is available **only** when the [Packages](../../product_management/configure/package.html) feature is enabled in Inventory app ‣ Configuration ‣ Settings.

After it is enabled, the Put in Pack button is available on all inventory operations (e.g. receipt, pickings, internal transfers, delivery orders, etc.).

To automatically print the package label when the Put in Pack button is clicked, go to Inventory app ‣ Configuration ‣ Operation Types. Select the desired operation type, and tick the Package Label checkbox in the Hardware tab. Labels can be printed in PDF or ZPL file formats, as defined in the Print label as field.

Example of package barcode

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/print_on_validation.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dispatch.html "Dispatch management system") |
  * [precedente](multipack.html "Multi-package shipments") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Printable delivery PDFs


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
  *[RfQ]: request for quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application programming interface
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost
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