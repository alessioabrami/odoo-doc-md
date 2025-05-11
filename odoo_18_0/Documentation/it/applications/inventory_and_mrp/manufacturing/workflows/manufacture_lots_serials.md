# Manufacture with lots and serial numbers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shop_floor.html "Linea di produzione") |
  * [precedente](continuous_improvement.html "Continuous product improvement") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Manufacture with lots and serial numbers



# Manufacture with lots and serial numbers¶

In Odoo, _lot numbers_ and _serial numbers_ are used to identify and track products in Odoo. Serial numbers are used to assign unique numbers to individual products, while lot numbers are used to assign a single number to multiple units of a specific product.

When manufacturing products tracked using lots or serial numbers, Odoo requires the lot or serial number to be assigned to each product before manufacturing can be completed. This ensures that each product is properly tracked from the moment it enters inventory.

## Configure products for tracking¶

By default, Odoo tracks the quantity of each product on hand, but does not track individual units of a product. Lot or serial number tracking must be enabled for each product individually.

To track a product using lots or serial numbers, begin by navigating to Inventory ‣ Configuration ‣ Settings, then scroll down to the Traceability section, and tick the Lots & Serial Numbers checkbox. Finally, click Save to save the change.

Next, click on Products ‣ Products, and select a product to track. Make sure the Track Inventory checkbox is ticked in the General Information tab. Since lot and serial number functionality is enabled, a drop-down menu appears next to the ticked checkbox.

Click on the Track Inventory drop-down menu. By default, By Quantity is selected, which only tracks the quantity on hand. Select By Lots to track the product using lot numbers, or By Unique Serial Number to track the product using serial numbers.

Vedi anche

[Lots](../../inventory/product_management/product_tracking/lots.html) [Serial numbers](../../inventory/product_management/product_tracking/serial_numbers.html)

## Lot number manufacturing¶

To manufacture a product tracked with lots, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Click New to create a new manufacturing order (MO).

In the Product field, select a product tracked using lots, and enter the desired Quantity. Click Confirm to confirm the MO.

Once the MO is confirmed, a Lot/Serial Number field appears in the top section of the MO form. By default, this field is empty.

To populate the Lot/Serial Number field with a lot number, click the __(plus) icon to the right of the field. Doing so automatically generates a lot, using the next available number, and enters it in the field.

Alternatively, click on the Lot/Serial Number field and select an existing lot number, or manually enter a new lot number and click Create «#» in the drop-down menu.

Either of these methods assign the product(s) in the MO a lot number before production is finished. It is also possible to complete production and close the MO by clicking Produce All, without assigning a lot number. Doing so automatically generates and assigns a lot, using the next available number.

## Serial number manufacturing¶

To manufacture a product tracked with serial numbers, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Click New to create a new MO.

In the Product field, select a product tracked using serial numbers, and enter the desired Quantity. Click Confirm to confirm the MO.

Once the MO is confirmed, a Lot/Serial Number field appears in the top section of the MO form. By default, this field is empty.

The rest of the manufacturing process depends on how many units the MO contains.

### Manufacture single unit¶

If a single unit of the product is being manufactured, clicking Produce All closes the MO, and automatically generates and assigns the next available serial number, which appears in the Lot/Serial Number field.

To assign a serial number without closing the MO, enter a number manually in the Lot/Serial Number field, and click Create «#», or click the __(plus) icon to the right of the field to auto-fill it with the next available number.

### Manufacture multiple units¶

Importante

When manufacturing a product tracked using serial numbers, an MO can be created for multiple units. However, when serial numbers are assigned to each unit, either at the end of production or before, the MO is split into multiple MOs, each containing one unit of the product.

Each of the split MOs is identified by a numerical tag added to the end of the original MO number.

Example

MO `WH/MO/00109` contains two units of a `Chair`, a product tracked using serial numbers. A serial number is assigned to each unit of the chair. This causes the MO to be split into two MOs, each containing one unit of the chair. The MOs are titled `WH/MO/00109-001` and `WH/MO/00109-002`.

To assign serial numbers to each unit of an MO, click Produce All to open the Batch Production pop-up window.

The First Lot/SN field of the pop-up window is auto-filled with the next available serial number. The Number of SN field defaults to the number of units being manufactured. The values of either field can be changed manually.

Click Generate to generate the specified number of serial numbers, beginning with the number entered in the First Lot/SN field. The serial numbers are displayed in the text box at the bottom of the pop-up window, and can be manually changed after generation.

To assign serial numbers without completing production, click the Prepare MO button. Doing so splits the MO into individual MOs, one for each unit in the original MO. Each MO is left open, and can be closed individually.

To assign serial numbers and complete production, click the Produce button. Doing so splits the MO into individual MOs, one for each unit in the original MO. All of the MOs are closed, since production is complete.

After clicking Prepare MO or Produce, the Manufacturing app automatically shows the first of the split MOs (ex. `WH/MO/00109-001`). To view and access the rest the split MOs, click the Backorders smart button at the top of the screen.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/workflows/manufacture_lots_serials.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shop_floor.html "Linea di produzione") |
  * [precedente](continuous_improvement.html "Continuous product improvement") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Manufacture with lots and serial numbers


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
  *[API]: Application programming interface
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: sales orders
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
  *[BOM]: Bill of Materials
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