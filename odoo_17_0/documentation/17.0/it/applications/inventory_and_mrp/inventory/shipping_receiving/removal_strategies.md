# Removal strategies — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](removal_strategies/fifo.html "FIFO removal") |
  * [precedente](picking_methods/wave.html "Process wave transfers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Removal strategies



# Removal strategies¶

For companies with warehouses, _removal strategies_ determine **which** products are taken from the warehouse, and **when**. For example, for perishable products, prioritizing the picking of goods with the nearest expiration date helps minimize food spoilage.

The following columns in the table below list the removal strategies available in Odoo, and detail how pickings are determined along with the picking order. Leverage these removal strategies to have Odoo automatically select how products are selected for orders:

| [FIFO](removal_strategies/fifo.html) | [LIFO](removal_strategies/lifo.html) | [FEFO](removal_strategies/fefo.html) | [Closest Location](removal_strategies/closest_location.html) | [Least Packages](removal_strategies/least_packages.html)  
---|---|---|---|---|---  
Basato su | [Incoming date](removal_strategies/fifo.html#inventory-warehouses-storage-arrival-date) | [Incoming date](removal_strategies/fifo.html#inventory-warehouses-storage-arrival-date) | [Removal date](removal_strategies/fefo.html#inventory-warehouses-storage-removal-date) | [Location sequence](removal_strategies/closest_location.html#inventory-warehouses-storage-sequence) | [Package quantity](removal_strategies/least_packages.html#inventory-warehouses-storage-pkg-qty)  
Selection order | First in | Last in | [First to expire](removal_strategies/fefo.html#inventory-warehouses-storage-exp-date) | [Alphanumeric name of location](removal_strategies/closest_location.html#inventory-warehouses-storage-location-name) | Quantity closest to fulfilling demand  
  
For comprehensive examples for how to use each removal strategy, refer to each individual documentation page.

## Configurazione¶

Removal strategies are set on either the product category or storage location.

Configure removal strategies on the location by going to Inventory ‣ Configuration ‣ Locations, and selecting the desired location. On the location form, choose a removal strategy from the Removal Strategy field’s drop-down menu options.

Importante

To set a removal strategy on a location, the Storage Locations and Multi-Step Routes settings **must** be enabled in Inventory ‣ Configuration ‣ Settings.

These features are **only** necessary when setting the removal strategy on a location.

Configure removal strategies on product categories by going to Inventory ‣ Configuration ‣ Product Categories and selecting the intended product category. Next, choose a removal strategy from the Force Removal Strategy drop-down menu options.

Importante

When there are different removal strategies applied on both the location and product category for a product, the value set on the Force Removal Strategy field set on a Product Category form is applied as top priority.

## Required features¶

While some removal strategies are available by default, some additional features **must** be enabled in Inventory ‣ Configuration ‣ Settings for the removal strategy option to appear in the drop-down menu of the Force Removal Strategy or Removal Strategy field.

Refer to the table below for a summary of required features. Otherwise, refer to the dedicated sections for the removal strategy for more details on requirements and usage.

| FIFO | LIFO | FEFO | Ubicazione più vicina | Colli minimi  
---|---|---|---|---|---  
Required features | Numeri di lotto e serie | Numeri di lotto e serie | Lots & Serial Numbers, Expiration Date | Storage Locations, Multi-Step Routes | Colli  
  
### Lots and serial numbers¶

Lots and serial numbers differentiate identical products and track information like arrival or expiration dates. To enable this feature, navigate to Inventory ‣ Configuration ‣ Settings. Under the Traceability heading, check the box beside Lots & Serial Numbers to enable the feature.

Next, ensure the intended product is tracked by lots or serial numbers by navigating to the product form through Inventory ‣ Products ‣ Products, and selecting the desired product. On the product form, switch to the Inventory tab, and under the Tracking field, select either the By Unique Serial Number or By Lots options.

After enabling the features, assign lot or serial numbers to products using an [inventory adjustment](../warehouses_storage/inventory_management/count_products.html) or during [product reception](../product_management/product_tracking/lots.html#inventory-product-management-assign-lots).

### Locations and routes¶

**Storage locations** and **multi-step routes** are necessary features for setting **all** types of removal strategies on a location. However, these features are specifically required for the closest location removal strategy since it is only applied at the location level.

To activate these features, navigate to Inventory ‣ Configuration ‣ Settings. Under the Warehouse heading, enable the Storage Location and Multi-Step Routes features.

### Data di scadenza¶

Enable the **expiration date** feature to track expiration dates, best before dates, removal dates, and alert dates on a lot or serial number by navigating to Inventory ‣ Configuration ‣ Settings.

Under the Traceability heading, ensure the Lots & Serial Numbers feature is selected, and then select the check box for Expiration Dates to enable the feature.

### Colli¶

The _packages_ feature is used to group products together and is required for the least packages removal strategy.

Navigate to Inventory ‣ Configuration ‣ Settings and select the check box for the Packages feature.

Vedi anche

  * [Packages](../product_management/configure/package.html)

  * [2-step delivery](daily_operations/receipts_delivery_two_steps.html)

  * [3-step delivery](daily_operations/delivery_three_steps.html)




  * [FIFO removal](removal_strategies/fifo.html)
  * [LIFO removal](removal_strategies/lifo.html)
  * [FEFO removal](removal_strategies/fefo.html)
  * [Closest location removal](removal_strategies/closest_location.html)
  * [Least packages removal](removal_strategies/least_packages.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/removal_strategies.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](removal_strategies/fifo.html "FIFO removal") |
  * [precedente](picking_methods/wave.html "Process wave transfers") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Removal strategies


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
  *[VAT]: Value Added Tax
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