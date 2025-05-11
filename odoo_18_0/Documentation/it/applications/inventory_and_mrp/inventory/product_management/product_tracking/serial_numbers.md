# Numeri di serie — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lots.html "Numeri lotto") |
  * [precedente](../product_tracking.html "Product tracking") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Numeri di serie



# Numeri di serie¶

_Serial numbers_ are one of the two ways to identify and track products in Odoo, along with [lots](lots.html). A serial number is a unique identifier assigned to a product to distinguish it from other products in a series. Serial numbers can consist of several character types: they can contain numbers, letters, other typographical characters, or any mix of these character types.

The goal of assigning serial numbers allows for the tracking of individual products and their [expiration dates](expiration_dates.html) and location throughout the supply chain. For instance, serial numbers can help manufacturers locate products to provide after-sales services or in the event of a recall.

Vedi anche

[Odoo Tutorials: Serial Numbers](https://www.youtube.com/watch?v=XWJjWc0Vl04)

## Enable lots & serial numbers¶

To track products using serial numbers, two settings need to be enabled: the Lots & Serial Numbers traceability setting, and serial number usage by operation type.

### Traceability setting¶

The _Lots & Serial Numbers_ traceability feature _must_ be enabled first to track products. To do so, go to Inventory app ‣ Configuration ‣ Settings, scroll down to the Traceability section, and tick the Lots & Serial Numbers checkbox. Remember to click the Save button to save changes.

### By operation type¶

Next, specify whether the ability to create new or use existing serial numbers should be turned on for particular operation types (such as shipping or receiving goods). In other words, this setting allows for serial number tracking on warehouse receipts and delivery orders.

Example

Enabling the _Create New_ option for receipts allows new serial numbers to be assigned as items are received. However, for delivery orders, it is often disabled to prevent workers from accidentally assigning serial numbers that do not exist in inventory.

To enable the creation of new serial numbers on an operation, navigate to Inventory app ‣ Configuration ‣ Operations Types.

From the Operations Types page, select the desired operation type (e.g. Receipts, Delivery Orders, or Manufacturing), and select the Create New option in the Lots/Serial Numbers section of the operation type’s configuration page.

## Configure serial number tracking on individual products¶

Once the Lots & Serial Numbers setting has been activated, individual products can now be tracked using serial numbers. To track a product, go to Inventory app ‣ Products ‣ Products, and select the desired product.

In the General Information tab on the product form, make sure the box next to Track Inventory is checked. Then, select By Unique Serial Number, and click Save to save the changes. Now, existing or new serial numbers can now be selected and assigned to newly-received or manufactured batches of this product.

## Assign serial numbers¶

In Odoo, serial numbers can be assigned at several times and places:

  * When a product is already in stock

  * Via the Moves smart button on a receipt

  * Via the Open: Stock move window on a receipt

  * [During a manufacturing order](../../../manufacturing/basic_setup/configure_manufacturing_product.html) for a product tracked by lots/serial numbers

  * When [making an inventory adjustment](../../warehouses_storage/inventory_management/count_products.html)




### Create new serial numbers for products already in stock¶

New serial numbers can be created for products already in stock with no assigned serial number. To do so, go to Inventory ‣ Products ‣ Lots/Serial Numbers, and click New. Doing so reveals a blank lot/serial number form. On this form, a new Lot/Serial Number is generated automatically.

Suggerimento

While Odoo automatically generates a new lot/serial number to follow the most recent number, it can be edited and changed to any desired number, by clicking the line under the Lot/Serial Number field, and changing the generated number.

Once the Lot/Serial Number is generated, click the blank field next to Product to reveal a drop-down menu. From this menu, select the product to which this new number will be assigned.

This form also provides the option to adjust the On Hand Quantity, to assign a unique Internal Reference number (for additional traceability), and to assign this specific lot/serial number configuration to a specific company in the Company field. A detailed description of this specific lot/serial number can also be added in the Description tab below.

Suggerimento

The Internal Reference number field is a space for manufacturers to input an additional unique number to allow for easier tracking. For instance, SKU values may be used here.

When all desired configurations are complete, click the Save button to save all changes.

After a new serial number has been created, assigned to the desired product, and saved, navigate back to the product form, by going to Inventory app ‣ Products ‣ Products, and selecting the product that this newly-created serial number was just assigned to.

On that product’s detail form, click the Lot/Serial Numbers smart button to view the new serial number.

### Create serial numbers for incoming or outgoing products¶

Serial numbers can be assigned to both incoming and outgoing goods. The receipt and delivery order forms mirror one another; the instructions below can be followed to assign serial numbers in either form.

  * **Incoming goods:** Assign serial numbers directly on the **receipt**. Receipts can be accessed by navigating to Inventory app ‣ Operations ‣ Receipts.

  * **Outgoing goods:** Assign serial numbers directly on the **delivery order**. Receipts can be accessed by navigating to Inventory app ‣ Operations ‣ Deliveries.




Importante

Before assigning serial numbers on receipts or delivery orders, be sure that the ability to create new serial numbers by operations type is enabled.

#### Lots/serial number field¶

Serial numbers can be entered directly into the Serial Numbers field on a receipt or delivery order.

Suggerimento

To make the Serial Numbers field visible on a receipt or delivery order, click the __(Adjust Settings) icon, and in the drop-down menu, tick the Serial Numbers checkbox.

Example **Serial Numbers** field on a delivery order.¶

#### Stock move pop-up window¶

For various methods of assigning serial numbers individually or in bulk, click the __(list) icon in the product line of a receipt.

##### Aggiungi riga¶

In the Open: Stock move pop-up window, manually enter serial numbers in the Lot/Serial Number column. This method is best reserved for adding only one or a few serial numbers.

##### Genera numeri di serie/lotti¶

Assign multiple serial numbers at once by clicking the Generate Serials/Lots button in the Open: Stock move pop-up window.

Doing so opens a new popup, Generate Serial numbers, which contains a few fields:

  * First SN: Input the first serial number that should start the sequence. From there, Odoo automatically detects what pattern should be followed to generate more serial numbers.

  * Number of SN: Specify the desired number of serial numbers to generate.

Nota

The number of serials generated will be reflected in the Quantity field on a receipt or delivery order. Even if the number of serial numbers generated exceeds the Demand value, Odoo still allows the quantity (based on the serial numbers) to be delivered or received.

  * Keep current lines checkbox: Check this box to keep existing serial numbers that may have been previously added. To replace existing serial numbers in the list, leave the box unchecked.




After filling out these fields, click the Generate button. The newly generated serials now appear in the Open: Stock move window. By clicking __(Save), the Quantity and the Serial Numbers fields on the delivery order or receipt update automatically.

##### Importa seriali/lotti¶

Another option for assigning multiple serial numbers at once is to click the Import Serials/Lots button in the Open: Stock move pop-up window.

Importante

If the import button is not visible, ensure the Create New box is checked in the receipt’s configuration page.

Doing so opens the Import Serials pop-up window. Enter each serial number on a separate line in the Lots/Serial numbers text field.

As when generating serials, check the Keep current lines box to keep existing serial numbers, or leave it unchecked to overwrite them.

Suggerimento

To expedite this process, copy/paste serial numbers from an existing spreadsheet and add them to the Lots/Serial numbers text field.

Finally, click Generate.

Example

For a receipt with a Demand of `3.00` products, one product has already been assigned a serial number in the Open: Stock move pop-up window.

So, in the Import Lots pop-up window, two serial numbers, `124` and `125` are assigned to the remaining products by entering the following in the Lots/Serial numbers input field:
    
    
    124
    125
    

The Keep current lines option is selected to add these two serial numbers **in addition** to the serial number, `123`, that has already been assigned.

#### Detailed operations¶

Accessible from both receipt and delivery order forms, the _Detailed Operations_ page shows a detailed view of product movements, including information about serial numbers, exact locations, expiration dates, etc. This level of detail permits more precise tracking, for example, when handling perishable or regulated goods.

To access this page, first select a warehouse receipt or delivery order. Then, click on the __ Moves smart button at the top of the page.

In the Lot/Serial Number column, manually type (or select from the drop-down menu) the desired serial numbers for each individual product.

When finished, click the receipt/delivery order’s breadcrumbs, and the assigned serial numbers are automatically saved.

## Display serial numbers on delivery slips¶

When selling products tracked using serial numbers, it is possible to include the serial numbers on the delivery slips sent to customers. This can be helpful to customers in cases where serial numbers are needed, such as filing an RMA or repair request, or registering the product.

To include serial numbers on delivery slips, open the Inventory app, and navigate to Configuration ‣ Settings. Scroll down to the Traceability section, tick the Display Lots & Serial Numbers on Delivery Slips checkbox, and click Save.

After enabling the Display Lots & Serial Numbers on Delivery Slips setting, serial numbers are listed on delivery slips for products tracked by serial numbers, once the delivery order is validated.

To view serial numbers on delivery orders and delivery slips, navigate to the Inventory app, click on Delivery Orders, and select an order containing a product tracked using serial numbers.

To view the serial numbers of products included in the order, make sure the Operations tab is selected, then click the __(adjust) icon to the right of the tab. Ensure that the Serial Numbers checkbox is ticked, which causes a Serial Numbers column to appear. The serial number(s) for each product included in the order are displayed in this column.

When the order is ready to be processed, click Validate to confirm the delivery and add product information to the delivery slip.

At the top of the order’s form, click the __(Actions) button, and select Print ‣ Delivery Slip. The delivery slip is then downloaded. Open the delivery slip using the device’s browser or file manager. Serial numbers are listed next to their respective products in the Lot/Serial Number column.

## Traceability & reporting¶

Manufacturers and companies can refer to the _Lots/Serial Numbers_ dashboard and traceability reports to see the entire lifecycle of a product: when and where it originated, where it was stored, and who it was shipped to.

### Lots/Serial Numbers dashboard¶

To see the full traceability of a product, or group by serial numbers, go to Inventory app ‣ Products ‣ Lots/Serial Numbers. Doing so reveals the Lots/Serial Numbers dashboard.

#### Rendiconto¶

On the Lots/Serial Numbers dashboard, products with serial numbers assigned to them are listed by default. Click the __(expand) icon to show which serial numbers are assigned to the chosen product.

To group by serial numbers (or lots), first remove any default filters from the search bar in the upper-right corner. Then, click the __(down arrow) icon and select Add Custom Group, which reveals a mini drop-down menu. From this mini drop-down menu, select Lot/Serial Number, and click Apply.

Doing so reveals all existing serial numbers and lots. Each row can be expanded to show all quantities of product assigned to that serial/lot number. For unique serial numbers that are not reused, there should be just one product per serial number.

Suggerimento

For additional information regarding an individual serial (or lot) number, click the line item for the serial number to reveal that specific Serial Number form. From this form, click the Location and Traceability smart buttons to see all stock on-hand using that serial number, and any operations made using that serial number.

Vedi anche

[Reassign](reassign.html)

In addition to using the Lots/Serial Numbers dashboard, there are several other reporting templates that display the Lot/Serial Number field or the ability to filter by serial number. Go to Inventory app ‣ Reporting to access:

  * Locations report

  * Moves History report

  * Moves Analysis report




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/product_tracking/serial_numbers.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lots.html "Numeri lotto") |
  * [precedente](../product_tracking.html "Product tracking") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Numeri di serie


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