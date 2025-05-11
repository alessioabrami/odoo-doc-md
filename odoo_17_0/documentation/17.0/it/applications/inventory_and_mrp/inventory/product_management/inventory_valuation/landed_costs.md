# Landed costs — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../warehouses_storage.html "Warehouses and storage") |
  * [precedente](using_inventory_valuation.html "Using inventory valuation") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Landed costs



# Landed costs¶

When shipping products to customers, the landed cost is the total price of a product or shipment, including all expenses associated with shipping the product.

In Odoo, the _Landed Costs_ feature is used to take additional costs into account when calculating the valuation of a product. This includes the cost of shipment, insurance, customs duties, taxes, and other fees.

## Configurazione¶

To add landed costs to products, the _Landed Costs_ feature must first be enabled. To enable this feature, navigate to Inventory app ‣ Configuration ‣ Settings, and scroll to the Valuation section.

Tick the checkbox next to the Landed Costs option, and click Save to save changes.

Once the page refreshes, a new Default Journal field appears below the Landed Costs feature in the Valuation section.

Click the Default Journal drop-down menu to reveal a list of accounting journals. Select a journal for which all accounting entries related to landed costs should be recorded.

## Create landed cost product¶

For charges that are consistently added as landed costs, a landed cost product can be created in Odoo. This way, a landed cost product can be quickly added to a vendor bill as an invoice line, instead of having to be manually entered every time a new vendor bill is created.

To do this, create a new product by going to Inventory app ‣ Products ‣ Products, and clicking New.

Assign a name to the landed cost product in the Product Name field (i.e. `International Shipping`). In the Product Type field, click the drop-down menu, and select Service as the Product Type.

Importante

Landed cost products **must** have their Product Type set to Service.

Click the Purchase tab, and tick the checkbox next to Is a Landed Cost in the Vendor Bills section. Once ticked, a new Default Split Method field appears below it, prompting a selection. Clicking that drop-down menu reveals the following options:

  * Equal: splits the cost equally across each product included in the receipt, regardless of the quantity of each.

  * By Quantity: splits the cost across each unit of all products in the receipt.

  * By Current Cost: splits the cost according to the cost of each product unit, so a product with a higher cost receives a greater share of the landed cost.

  * By Weight: splits the cost, according to the weight of the products in the receipt.

  * By Volume: splits the cost, according to the volume of the products in the receipt.




When creating new vendor bills, this product can be added as an invoice line as a landed cost.

Importante

To apply a landed cost on a vendor bill, products in the original PO **must** belong to a _Product Category_ with a _Costing Method_ of either AVCO or FIFO, and the valuation method can be [manual](using_inventory_valuation.html) or [automatic](inventory_valuation_config.html).

## Create purchase order¶

Navigate to Purchase app ‣ New to create a new request for quotation (RfQ). In the Vendor field, add a vendor to order products from. Then, click Add a product, under the Products tab, to add products to the RfQ.

Once ready, click Confirm Order to confirm the order. Then, click Receive Products once the products have been received, followed by Validate.

### Create vendor bill¶

Once the vendor fulfills the PO and sends a bill, a vendor bill can be created from the PO in Odoo.

Navigate to the Purchase app, and click into the PO for which a vendor bill should be created. Then, click Create Bill. This opens a new Vendor Bill in the Draft stage.

In the Bill Date field, click the line to open a calendar popover menu, and select the date on which this draft bill should be billed.

Then, under the Invoice Lines tab, click Add a line, and click the drop-down menu in the Product column to select the previously-created landed cost product. Click the __(cloud with arrow) icon to manually save and update the draft bill.

In the Landed Costs column, the product ordered from the vendor does **not** have its checkbox ticked, while the landed cost product’s checkbox **is** ticked. This differentiates landed costs from all other costs displayed on the bill.

Additionally, at the top of the form, a Create Landed Costs button appears.

## Add landed cost¶

Once a landed cost is added to the vendor bill, click Create Landed Costs at the top of the vendor bill.

Doing so automatically creates a landed cost record, with a set landed cost pre-filled in the product line in the Additional Costs tab.

From the Landed Cost form, click the Transfers drop-down menu, and select which transfer the landed cost belongs to.

Suggerimento

In addition to creating landed costs directly from a vendor bill, landed cost records can _also_ be created by navigating to Inventory app ‣ Operations ‣ Landed Costs, and clicking New.

After setting the picking from the Transfers drop-down menu, click Compute (at the bottom of the form, under the Total: cost).

Click the Valuation Adjustments tab to see the impact of the landed costs. The Original Value column lists the original price of the PO, the Additional Landed Cost column displays the landed cost, and the New Value displays the sum of the two, for the total cost of the PO.

Once ready, click Validate to post the landed cost entry to the accounting journal.

This causes a Valuation smart button to appear at the top of the form. Click the Valuation smart button to open a Stock Valuation page, with the product’s updated valuation listed.

Nota

For a Valuation smart button to appear upon validation, the product’s Product Type **must** be set to Storable.

To view the valuation of _every_ product, including landed costs, navigate to Inventory app ‣ Reporting ‣ Valuation.

Nota

Each journal entry created for a landed cost on a vendor bill can be viewed in the _Accounting_ app.

To locate these journal entries, navigate to Accounting app ‣ Accounting ‣ Journal Entries, and locate the correct entry, by number (i.e. `PBNK1/2024/XXXXX`).

Click into the journal entry to view the Journal Items, and other information about the entry.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/product_management/inventory_valuation/landed_costs.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../warehouses_storage.html "Warehouses and storage") |
  * [precedente](using_inventory_valuation.html "Using inventory valuation") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Valutazione dell’inventario](../inventory_valuation.html) »
  * Landed costs


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