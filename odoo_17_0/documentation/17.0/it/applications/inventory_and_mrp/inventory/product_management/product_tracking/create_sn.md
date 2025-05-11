# Assign serial numbers — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lots.html "Numeri lotto") |
  * [precedente](serial_numbers.html "Use serial numbers to track products") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Assign serial numbers



# Assign serial numbers¶

Assigning serial numbers to individual products allows the for tracking of properties, [expiration dates](expiration_dates.html), and location throughout the supply chain, which particularly benefits manufacturers providing after-sales services.

Vedi anche

  * [Odoo Tutorials: Serial Numbers](https://www.youtube.com/watch?v=ZP-gMz2X5AY)

  * [Use serial numbers to track products](serial_numbers.html)




In Odoo, serial numbers are assigned to products:

  * in the Detailed Operations page on a receipt

  * by clicking the Assign Serial Numbers button on a receipt

  * in the Open: Stock move window on a receipt

  * [during a manufacturing order](../../../manufacturing/basic_setup/configure_manufacturing_product.html) for a product tracked by lot/serial numbers

  * when making an inventory adjustment




Display the **Detailed Operations** smart button and bulleted list icon on a receipt.¶

## Configurazione¶

To assign serial numbers to products, activate the Lots and Serial Numbers feature in Inventory app ‣ Configuration ‣ Settings.

Then, in the Inventory tab of an item’s product form, set the Tracking field to By Unique Serial Number.

Vedi anche

  * [Enable serial numbers](serial_numbers.html#inventory-product-management-enable-lots)

  * [Track products by serial numbers](serial_numbers.html#inventory-product-management-configure-lots)




Next, enable creating new serial numbers by going to Inventory app ‣ Configuration ‣ Operations Types.

From the Operations Types page, select the desired operation type (e.g. Receipts, Delivery Orders, or Manufacturing), and select the Create New option in the Lots/Serial Numbers section of the operation type’s configuration page.

## Operazioni dettagliate¶

Serial numbers can be assigned to products when entering stock for the first time, from the Detailed Operations page on the receipt. Receipts can be accessed by navigating to Inventory app ‣ Operations ‣ Receipts.

Importante

Serial numbers can **not** be assigned to products on a request for quotation (RfQ) or purchase order (PO) — **only** on a receipt.

Screenshot of a «Purchase Order» with the «Receipt» smart button at the top.¶

To record an item’s serial number before receiving the item, follow the steps in the next sections to assign serial numbers, but do **not** click the receipt’s Validate button, until the products are received from the vendor.

Assign a single serial number to a product by clicking the Detailed Operations smart button on a receipt.

In the Lot/Serial Number Name column, manually type in the serial number for a single product.

When finished, click the receipt’s breadcrumbs, and the assigned serial numbers are automatically saved.

## Assign serial numbers¶

To generate new serial numbers in a sequence, click the \+ (plus) icon in the product line.

Importante

If the icon is not visible, ensure the Create New option is selected in the receipt’s configuration page.

Doing so opens the Assign Serial Numbers pop-up window. The Number of SN field is auto-filled based on the product quantity requiring serial numbers. Manually input the first serial number in the First SN field, and click Assign Serial Numbers to generate a sequence of serial numbers based on the first serial number entered.

## Stock move pop-up window¶

For various methods of assigning serial numbers in bulk, click the ⦙≣ (bulleted list) icon in the product line of a receipt.

### Aggiungi riga¶

In the Open: Stock move pop-up window that appears, manually input the serial numbers in the Lot/Serial Number column.

### Genera seriali¶

Assign multiple serial numbers at once by clicking the Generate Serials/Lots button in the Open: Stock move pop-up window.

Doing so opens the Generate Serial numbers pop-up window, where the first serial number is entered in the First SN field to generate a sequence of serial numbers, based on the first serial number entered.

For more details on how to fill in this pop-up window, refer to this section.

### Importa seriali¶

Assign multiple serial numbers at once by clicking the Import Serials/Lots button in the Open: Stock move pop-up window.

Importante

If the button is not visible, ensure the Create New option is selected in the receipt’s configuration page.

Doing so opens the Import Lots pop-up window. Enter each serial number on a separate line in the Lots/Serial numbers text field.

Suggerimento

Copy/paste serial numbers from an existing excel spreadsheet and add them to the Lots/Serial numbers text field.

Tick the Keep current lines checkbox to add serial numbers to the list of products, and serial numbers in the Lot/Serial Number table, in the Open: Stock move pop-up window. To replace the serial numbers in the list, leave the Keep current lines option unchecked.

Finally, click Generate.

Example

For a receipt with a Demand of `3.00` products, one product has already been assigned a serial number in the Open: Stock move pop-up window.

So, in the Import Lots pop-up window, two serial numbers, `124` and `125` are assigned to the remaining products by entering the following in the Lots/Serial numbers input field:
    
    
    124
    125
    

The Keep current lines option is selected to add these two serial numbers **in addition** to the serial number, `123`, that has already been assigned.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/product_tracking/create_sn.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](lots.html "Numeri lotto") |
  * [precedente](serial_numbers.html "Use serial numbers to track products") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Assign serial numbers


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
  *[FBM]: Fulfilled By Merchant
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure