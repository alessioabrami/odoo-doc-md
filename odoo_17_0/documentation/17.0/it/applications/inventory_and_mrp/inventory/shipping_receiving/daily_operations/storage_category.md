# Storage categories — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_dock.html "Organize a cross-dock in a warehouse") |
  * [precedente](putaway.html "Putaway rules") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Storage categories



# Storage categories¶

A _storage category_ is used with [putaway rules](putaway.html), as an extra location attribute to automatically propose optimal storage locations for products.

Follow these steps to complete the setup:

  1. Enable the Storage Category feature

  2. Define a storage category with specific limitations

  3. Assign a category to storage locations

  4. Add the storage category as an attribute to a putaway rule




Vedi anche

[Putaway rules](putaway.html)

Nota

Assigning categories to storage locations tells Odoo these locations meet specific requirements, such as temperature or accessibility. Odoo then evaluates these locations, based on defined capacity, and recommends the best one on the warehouse transfer form.

## Configurazione¶

To enable storage categories, go to Inventory app ‣ Configuration ‣ Settings. Then, in the Warehouse section, ensure the Storage Locations and Multi-Step Routes features are enabled.

Next, activate the Storage Categories feature. Finally, click Save.

## Define storage category¶

A storage category with specific limitations **must** be created first, before it is applied to locations, in order to decide the optimal storage location.

To create a storage category, go to Inventory app ‣ Configuration ‣ Storage Categories, and click Create.

On the storage category form, type a name for the category in the Storage Category field.

Options are available to limit capacity by weight, product, and package type.

Nota

Weight limits can be combined with capacity by package or product (e.g. a maximum of one hundred products with a total weight of two hundred kilograms).

While it is possible to limit capacity by product and package type at the same location, it may be more practical to store items in different amounts across various locations, as shown in this example of capacity by package.

The Allow New Product field defines when the location is considered available to store a product:

  * If location is empty: a product can be added there only if the location is empty.

  * If products are the same: a product can be added there only if the same product is already there.

  * Allow mixed products: several different products can be stored in this location at the same time.




Suggerimento

When clicked, the Location smart button shows which storage locations the category has been assigned to.

### Capacity by weight¶

On a storage category form (Inventory app ‣ Configuration ‣ Storage Categories), set a maximum product weight in the Max Weight field. This limit applies to each location assigned this storage category.

### Capacity by product¶

In the Capacity by Product tab, click Add a Line to input items, and enter their capacities in the Quantity field.

Example

Ensure only a maximum of five `Large Cabinets` and two `Corner Desk Right Sit` are stored at a single storage location, by specifying those amounts in the Capacity by Product tab of a storage category form.

### Capacity by package¶

For companies using [packages](../../product_management/configure/package.html), it becomes possible to ensure real-time storage capacity checks, based on package types (e.g., crates, bins, boxes, etc.).

Importante

Enable the Packages feature in Inventory app ‣ Configuration ‣ Settings to show the Capacity by Package tab.

Example

Create putaway rules for pallet-stored items, by creating the `High Frequency pallets` storage category.

In the Capacity by Package tab, specify the number of packages for the designated Package Type, and set a maximum of `2.00` `Pallets` for a specific location.

## Assign to location¶

Once the storage category is created, assign it to a location. Navigate to the location by going to Inventory app ‣ Configuration ‣ Locations, and select the desired location. Then, select the created category in the Storage Category field.

Example

Assign the `High Frequency pallets` storage category (which limits pallets stored at any location to two pallets) to the `WH/Stock/pallets/PAL 1` sub-location.

## Putaway rule¶

With the storage category and location set up, create the [putaway rule](putaway.html) by navigating to Inventory app ‣ Configuration ‣ Putaway Rules.

Click the Create button to create the putaway rule. In the Having Category field of the new putaway rule form, select the storage category.

Example

Continuing the example from above, the `High Frequency Pallets` storage category is assigned to the putaway rule directing pallets of lemonade to locations with the `High Frequency Pallets` storage category assigned to them.

## Use case: limit capacity by package¶

To limit the capacity of a storage location by a specific number of packages, create a storage category with a Capacity By Package.

Continuing the example from above, the `High Frequency Pallets` storage category is assigned to the `PAL1` and `PAL2` locations.

Then, [putaway rules](putaway.html#inventory-routes-putaway-rule) are set, so that any pallets received in the warehouse are directed to be stored in `PAL1` and `PAL2` locations.

Depending on the number of pallets on-hand at each of the storage locations, when one pallet of lemonade cans is received, the following scenarios happen:

  * If `PAL1` and `PAL2` are empty, the pallet is redirected to `WH/Stock/Pallets/PAL1`.

  * If `PAL1` is full, the pallet is redirected to `WH/Stock/Pallets/PAL2`.

  * If `PAL1` and `PAL2` are full, the pallet is redirected to `WH/Stock/Pallets`.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations/storage_category.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cross_dock.html "Organize a cross-dock in a warehouse") |
  * [precedente](putaway.html "Putaway rules") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Storage categories


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
  *[UoM]: Units of Measure
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
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