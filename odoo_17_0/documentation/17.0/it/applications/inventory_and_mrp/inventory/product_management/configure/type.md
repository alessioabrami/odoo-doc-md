# Product type — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Unità di misura") |
  * [precedente](../configure.html "Configure product") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Product type



# Product type¶

Define _product types_ in Odoo to track products in varying levels of detail.

Classify products as _storable_ to track stock counts, allowing users to trigger [reordering rules](../../warehouses_storage/replenishment/reordering_rules.html) for generating purchase orders. _Consumable_ products are assumed to always be in stock, and _service_ products are performed and served by the business.

Vedi anche

[Odoo Tutorials: Product Type](https://www.youtube.com/watch?v=l6j0ZkP5mLM)

## Set product type¶

To set a product type, go to Inventory app ‣ Products ‣ Products, and select the desired product from the list.

On the product form, in the Product Type field, select:

  * Storable Product for products tracked with stock counts. Only storable products can trigger reordering rules for generating purchase orders;

> Suggerimento
> 
> Choose Storable Product if it is necessary to track a product’s stock at various locations, inventory valuations, or if the product has lots and/or serial numbers.

  * Consumable for products that are always assumed to be in stock, whose quantities are not necessary to track or forecast (e.g. nails, toilet paper, coffee, etc.). Consumables are replaceable and essential, but exact counts are unnecessary; or

  * Service for sellable service products that are performed, and not tracked with stock counts (i.e. maintenance, installation, or repair services).




Nota

The product types listed above are part of the standard _Inventory_ app. For access to the fields below, [install](../../../../general/apps_modules.html#general-install) the corresponding apps **in addition** to _Inventory_.

  * Booking Fees: charge a fee for booking appointments through the _Appointments_ app. Requires the installation of the _Calendar_ app and _Pay to Book_ (`appointment_account_payment`) module

  * Combo: create discounted products sold in a bundle. Requires the installation of the _PoS_ app.

  * Event Ticket: sold to attendees wanting to go to an event. Requires the installation of the _Events_ app

  * Event Booth: sold to partners or sponsors to set up a booth at an event. Requires the installation of the _Events_ app

  * Course: sell access to an educational course. Requires the installation of the _eLearning_ app




## Compare types¶

Below is a summary of how each product type affects common _Inventory_ operations, like transfers, reordering rules, and the forecasted report. Click the chart item with an asterisk (*) to navigate to detailed sections.

Product type | Storable | Consumabile | Servizio  
---|---|---|---  
Physical product | Sì | Sì | No  
On-hand quantity | Yes* | Yes* | No  
[Inventory valuation](../inventory_valuation/using_inventory_valuation.html) | Sì | No | No  
Create transfer | Yes* | Yes* | No*  
[Lot/serial number tracking](../product_tracking.html) | Sì | No | No  
Create purchase order | Sì | Yes* | No  
Can be manufactured or subcontracted | Yes* | Yes* | No  
Can be in a kit | Sì | Sì | No  
Placed in package | Sì | Yes* | No  
Appears on Inventory report | Yes | No | No  
  
### On-hand quantity¶

A storable product’s on-hand and forecasted quantities, based on incoming and outgoing orders, are reflected on the product form, accessed by going to Inventory app ‣ Products ‣ Products, and selecting the desired product.

Current and forecasted quantities are displayed in the **On Hand** and **Forecasted** smart buttons on the product form.¶

On the other hand, consumable products are regarded as always available, and they **cannot** be managed using reordering rules or lot/serial numbers.

### Create transfer¶

_Transfers_ are any warehouse operation, such as receipts, internal or batch transfers, or deliveries.

When creating a transfer for storable products in the _Inventory_ app, transfers modify the on-hand quantity at each location.

For example, transferring five units from the internal location `WH/Stock` to `WH/Packing Zone` decreases the recorded quantity at `WH/Stock` and increases it at `WH/Packing Zone`.

For consumable products, transfers can be created, but exact quantities at each storage location are not tracked.

Service products cannot be included in transfers, but these products can be [linked to projects and tasks for deadline tracking](https://www.youtube.com/watch?v=fix2LGkv13c).

### Create purchase order¶

Both storable and consumable products can be included in a request for quotation in the _Purchase_ app.

However, when receiving consumable products, their on-hand quantity does not change upon validating the receipt (e.g. `WH/IN`).

### Manufacture or subcontract¶

Storable and consumable products can be manufactured, subcontracted, or included in a bill of materials (BoM).

When the **Bill of Materials** and **Used In** smart buttons are visible on the product form, this indicates the product can be manufactured or used as a component of a BoM.¶

### Colli¶

Both storable and consumable products can be placed in [packages](package.html).

However, for consumable products, the quantity is not tracked, and the product is not listed in the package’s Contents, accessed by going to Inventory app ‣ Products ‣ Packages, and selecting the desired package.

A consumable product was placed in the package, but the **Content** section does not list it.¶

If the _Move Entire Package_ feature is enabled, moving a package updates the location of the contained storable products. However, the location of consumable products are not updated.

### Inventory report¶

**Only** storable products appear on the following reports.

The _stock report_ is a comprehensive list of all on-hand, unreserved, incoming, and outgoing storable products. The report is only available to users with [administrator access](../../../../general/users/access_rights.html), and is found by navigating to Inventory app ‣ Reporting ‣ Stock.

The _location report_ is a breakdown of each location (internal, external, or virtual) and the on-hand and reserved quantity of each storable product. The report is only available with the _Storage Location_ feature activated (Inventory app ‣ Configuration ‣ Settings), and to users with [administrator access](../../../../general/users/access_rights.html).

Navigate to the location report by going to Inventory app ‣ Reporting ‣ Locations.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/configure/type.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Unità di misura") |
  * [precedente](../configure.html "Configure product") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Configure product](../configure.html) »
  * Product type


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
  *[FIFO]: First In First Out
  *[FEFO]: First Expired, First Out
  *[UoMs]: Units of Measure