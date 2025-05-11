# One-step manufacturing — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](two_step_manufacturing.html "Two-step manufacturing") |
  * [precedente](bill_configuration.html "Bill of materials") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * One-step manufacturing



# One-step manufacturing¶

Odoo _Manufacturing_ allows users to manufacture products using one, two, or three steps. When using one-step manufacturing, Odoo creates a manufacturing order (MO), but does not generate transfers for the movement of components out of inventory or finished products into stock. Inventory counts still update based on the number of components used and products manufactured, but the act of transferring them to and from inventory is not tracked.

Suggerimento

The number of steps used in manufacturing is set at the warehouse level, allowing for each warehouse to use a different number of steps. To change the number of steps used for a specific warehouse, begin by navigating to Inventory ‣ Configuration ‣ Warehouses, and then select a warehouse from the Warehouses screen.

On the Warehouse Configuration tab, find the Manufacture radio input field, and select one of the three options: Manufacture (1 step), Pick components and then manufacture (2 steps), or Pick components, manufacture and then store products (3 steps).

Importante

Products must be properly configured before they can be manufactured in Odoo. For details on how to do so, see the documentation on how to [configure a product for manufacturing](configure_manufacturing_product.html#manufacturing-management-configure-manufacturing-product).

## Create manufacturing order¶

To manufacture a product in Odoo _Manufacturing_ , begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and then click New to create a new MO.

On the new MO, select the product to be produced from the Product drop-down menu. The Bill of Material field auto-populates with the associated bill of materials (BoM).

If a product has more than one BoM configured for it, the specific BoM can be selected in the Bill of Material field, and the Product field auto-populates with the associated product.

After a BoM has been selected, the Components and Work Orders tabs auto-populate with the components and operations specified on the BoM. If additional components or operations are required for the MO being configured, add them to the Components and Work Orders tabs by clicking Add a line.

Finally, click Confirm to confirm the MO.

## Process manufacturing order¶

An MO is processed by completing all of the work orders listed under its Work Orders tab. This can be done on the MO itself, or from the work order tablet view.

### Basic workflow¶

To complete work orders from the MO itself, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and then select an MO.

On the MO page, select the Work Orders tab. Once work begins on the first work order that needs to be completed, click the Start button for that work order. Odoo _Manufacturing_ then starts a timer that keeps track of how long the work order takes to complete.

When the work order is completed, click the Done button for that work order. Repeat the same process for each work order listed on the Work Orders tab.

After completing all of the work orders, click Produce All at the top of the screen to mark the MO as Done, and register the manufactured product(s) into inventory.

### Shop Floor workflow¶

To complete the work orders for an MO using the _Shop Floor_ module, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and then select an MO.

On the MO, click on the Work Orders tab, and then select the ↗️ (square with arrow coming out of it) button on the line of the first work order to be processed. Doing so opens a Work Orders pop-up window, with details and processing options for the work order.

On the pop-up window, select the Open Shop Floor button at the top-left of the window to open the _Shop Floor_ module.

When accessed directly from a specific work order within an MO, _Shop Floor_ defaults to the page for the work center where the work order is configured to be carried out. The page shows a card for the work order that displays the MO number, the product and number of units to be produced, and the steps required to complete the work order.

A work order is processed by completing each step listed on its card. This can be done by clicking on a step and following the instructions listed on the pop-up window that appears. Once the step is completed, click Next to move on to the next step, if any are required.

Alternatively, work order steps can be completed by clicking the checkbox that appears on the right side of the step’s line on the work order card. When using this method, the step is automatically marked as completed, without a pop-up window appearing.

The final step on a work order card is titled _Register Production_. This step is used to register the number of product units that were produced. If the number produced is equal to the number that the MO was created for, click the # Units button on the right side of the line to automatically register that number as the quantity produced.

If a different number must be entered, click the Register Production step to open a pop-up window. Enter the number of units produced in the Units field, and then click Validate to register that number.

Nota

The _Register Production_ step appears on every work order card. It must be completed for the first work order that is processed. After doing so, the step appears as already completed for each remaining work order in the MO.

After completing all of the steps for a work order, a button appears on the footer of the work order card. If any other work orders must be completed before the MO can be closed, the button is titled Mark as Done. If there are no additional work orders to complete, the button is titled Close Production.

Clicking Mark as Done causes the work order card to fade away. Once it disappears completely, the work order’s status is marked as _Finished_ on the MO, and the next work order appears in the _Shop Floor_ module, on the page of the work center where it is configured to be carried out. Any additional work orders can be processed using the instructions detailed in this section.

Clicking Close Production causes the work order card to fade away. Once it disappears, the MO is marked as _Done_ , and the units of the product that were produced are entered into inventory.

After clicking Mark as Done or Close Production, each button is replaced by an Undo button. Click the Undo button before the work order card fades away to keep the work order open.

Suggerimento

This section details the basic workflow for processing an MO in the _Shop Floor_ module. For a more in-depth explanation of the module and all of its features, please see the [Shop Floor overview](../shop_floor/shop_floor_overview.html#manufacturing-shop-floor-shop-floor-overview) documentation.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/basic_setup/one_step_manufacturing.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](two_step_manufacturing.html "Two-step manufacturing") |
  * [precedente](bill_configuration.html "Bill of materials") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * One-step manufacturing


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
  *[FBM]: Fulfilled By Merchant
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: bills of material
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order