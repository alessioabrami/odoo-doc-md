# Dispatch management system — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reservation_methods.html "Reservation methods") |
  * [precedente](print_on_validation.html "Printable delivery PDFs") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Dispatch management system



# Dispatch management system¶

The _dispatch management system_ feature in Odoo is used to plan and build shipments. Key features include:

  * **Load building** : Group products for specific carriers, assign those [batches](../picking_methods/batch.html) to loading docks, and manage vehicle assignments based on fleet capacity. This ensures the right products are packed into the appropriate trucks for delivery.

  * [Fleet management](../../../../hr/fleet.html): Track and manage the capacity of in-house delivery vehicles.




## Configurazione¶

To use the dispatch management system, the following setup must be completed:

  1. [Install](../../../../general/apps_modules.html#general-install) the **Fleet** application.

  2. Configure vehicle capacity (volume and weight).

  3. Enter vehicle [car model(s)](../../../../hr/fleet/models.html).

  4. Enable necessary features in the **Inventory** app.

  5. Set up vehicles as delivery methods.

  6. Create dock locations.




### Vehicle capacity¶

To configure the vehicle capacity, go to Fleet app ‣ Configuration ‣ Categories.

Next, click New to add a new category, or click into an existing category to modify it. In the Name field, enter the type of vehicle (e.g., `Pick-up truck`, `Van`, or `Cargo truck`). Then, enter the vehicle capacity in the Max Weight (in kilograms) and Max Volume (in cubic meters) fields.

Nota

The units of measurement for vehicle capacity are assigned at the global level in the **Settings** app, in the Units of Measure section.

Vedi anche

[Vehicle category](../../../../hr/fleet/models.html#fleet-categories)

### Car model¶

Configuring a vehicle’s car model is required when adding vehicles in Odoo. Ensure the correct _Category_ is selected for a car model. Doing so automatically applies weight and volume capacities to all vehicles of that type.

To configure, navigate to Fleet app ‣ Configuration ‣ Models.

From the Models list, select an existing model, or click New in the top-left corner to create a new model. Then, set the relevant Category field to the relevant vehicle category.

Vedi anche

[Create car model](../../../../hr/fleet/models.html)

### Inventory settings¶

Next, go to Inventory app ‣ Configuration ‣ Settings, and enable the required features for dispatch management.

In the Operations section, tick the Batch, Wave & Cluster Transfers checkbox to prepare batches of orders for delivery.

In the Shipping section, tick the Delivery Methods and Dispatch Management System checkboxes. Doing so allows specific vehicles to be set as carriers.

In the Warehouse section, tick the Storage Locations checkbox to assign specific locations in the warehouse as loading zones for delivery trucks.

Then, once all the configurations are complete, be sure to click Save.

### Metodo di consegna¶

Next, assign each delivery vehicle as a _Carrier_ by configuring a delivery method.

To configure delivery methods, go to Inventory app ‣ Configuration ‣ Delivery Methods. Select an existing delivery method, or click New.

Vedi anche

[Configure delivery method](../setup_configuration.html)

On the Delivery Method form, enter a name for the delivery method. It is recommended to use identifying information, such as the vehicle description and license plate number (e.g. `Truck 123-ABCD`).

Since the delivery methods are managed internally, set the Provider to either Fixed Price or Based on Rules. For more information about how shipping prices are calculated, refer to the [Delivery method](../setup_configuration.html) article.

Next, set a Delivery Product, which is the product that shows up as the customer’s [delivery charge](../setup_configuration.html#inventory-shipping-sales-order) on the sales order or invoice.

Optionally, in the Availability tab, set the Countries, States, or Zip Prefixes to limit the range of local delivery.

Example delivery method, with the Zip Prefixes set to San Francisco’s zip code.¶

### Dock locations¶

Each loading dock must have a dedicated location. To create or configure dock locations, go to Inventory app ‣ Configuration ‣ Locations.

Click the desired location, which opens the Location form. In the Additional Information section, tick the Is a Dock Location checkbox.

Location configuration page with Is a Dock Location checkbox ticked.¶

## Build loads¶

Once setup is complete, assign orders to a carrier and group them into batches. Then, configure the batch form, as needed.

To group products, go to the Inventory app ‣ Operations ‣ Deliveries, which reveals a list of outgoing deliveries.

Vedi anche

Since this article is about a specific use case, explore details about each picking method in their dedicated articles.

  * [Batch picking](../picking_methods/batch.html)

  * [Wave picking](../picking_methods/wave.html)

  * [Cluster picking](../picking_methods/cluster.html)




### Carrier assignment¶

Reveal the _Carrier_ column, if it is not visible by default, by clicking the __(settings) icon in the top-right corner, and ticking the Carrier checkbox.

Suggerimento

Other useful columns to enable can be Zip code, Shipping Weight, and Shipping Volume.

Select the delivery orders for the batch by ticking the checkboxes on the left. Next, click into the line’s Carrier fields. In the resulting drop-down menu, choose the desired vehicle’s delivery method. A Confirmation pop-up window appears, indicating the number of orders being added to the batch. Click Confirm, and the carrier is updated for all the selected records.

The delivery method `Truck 1-MER-001` is set as the Carrier for two delivery orders.¶

### Create batch¶

With the carrier set, begin adding orders to a batch or wave transfer by ticking the checkbox.

Nota

If a delivery order is already assigned to a batch transfer, assigning a batch transfer here does **not** update it.

Then, click the __ Actions button, and click either Add to batch or Add to wave. In the pop-up window, ensure Add to is set to a new [batch/wave] transfer, then click Confirm.

Delivery orders are selected to be grouped into a wave transfer.¶

#### Alternative batch creation method¶

Another place to create batches is by going to the Inventory app, and in the Delivery Orders card, click the __(three dots) icon. In the resulting drop-down menu, click Prepare batch.

Nota

The Transport Management drop-down menu contains other tools for fleet management:

  * Manage Batches: open list of batches

  * Dock Dispatching: open weekly calendar view of scheduled batch operations

  * Batches by Route: Kanban view of batches grouped by fulfillment route

  * Calendar: open hourly calendar view of scheduled operations

  * Statistics: open pivot table of the batch transfers




### Batch form¶

On the batch transfer form, fill the following fields out accordingly:

  * Responsible: employee assigned to the picking. Leave blank if _any_ worker can fulfill this picking.

  * Operation Type: from the drop-down menu, select the operation type under which the picking is categorized.

  * Scheduled Date: specifies the date by which the Responsible person should complete the transfer to the output location.

  * Dock Location: select the loading location.

  * Vehicle: select the vehicle, which will auto-fill Vehicle Category.

  * Vehicle Category: show if the order exceeds the vehicle’s capacity limits




Example

The Volume bar is grayed out because the capacity has been reached.

#### Prepare delivery route¶

To help the driver prepare, click the Map button at the top of the batch or wave form to view delivery destinations on a map. Selecting an individual delivery order pinpoints its location.

Nota

The Map button is only visible for transfers with the In progress status.

Additionally, use the View in Google Maps button to generate a route from the warehouse to the delivery points.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dispatch.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reservation_methods.html "Reservation methods") |
  * [precedente](print_on_validation.html "Printable delivery PDFs") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Dispatch management system


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