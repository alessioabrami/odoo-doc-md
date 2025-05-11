# Consignment: buy and sell stock without owning it — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dropshipping.html "Dropshipping") |
  * [precedente](stock_warehouses.html "Sell stock from multiple warehouses using virtual locations") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Consignment: buy and sell stock without owning it



# Consignment: buy and sell stock without owning it¶

Most of the time, products stored in a company’s warehouse are either purchased from suppliers, or are manufactured in-house. However, suppliers will sometimes let companies store and sell products in the company’s warehouse, without having to buy those items up-front. This is called _consignment_.

Consignment is a useful method for suppliers to launch new products, and easily deliver to their customers. It’s also a great way for the company storing the products (the consignee) to earn something back for their efforts. Consignees can even charge a fee for the convenience of storing products they don’t actually own.

## Enable the consignment setting¶

To receive, store, and sell consignment stock, the feature needs to be enabled in the settings. To do this, go to Inventory ‣ Configuration ‣ Settings, and under the Traceability section, check the box next to Consignment, and then click Save to finish.

## Receive (and store) consignment stock¶

With the feature enabled in Odoo, consignment stock can now be received into a warehouse. From the main Inventory dashboard, click into the Receipts section. Then, click Create.

Nota

Consignment stock is not actually purchased from the vendor; it is simply received and stored. Because of this, there are no quotations or purchase orders involved in receiving consignment stock. So, _every_ receipt of consignment stock will start by creating manual receipts.

Choose a vendor to enter in the Receive From field, and then choose the same vendor to enter in the Assign Owner field.

Importante

Since the products received from the vendor will be owned by the same vendor, the Receive From and Assign Owner fields must match.

Once the vendor-related fields are set, enter products into the Product lines, and set the quantities to be received into the warehouse under the Done column. If the Units of Measure feature is enabled, the UoM can be changed, as well. Once all the consignment stock has been received, Validate the receipt.

## Sell and deliver consignment stock¶

Once consignment stock has been received into the warehouse, it can be sold the same as any other in-stock product that has the Can Be Sold option enabled on the product form.

To create a sales order, navigate to the Sales app, and from the Quotations overview, click Create. Next, choose a customer to enter into the Customer field.

Nota

The Customer _must_ be different from the Vendor that supplied the consignment stock received (and stored) in the warehouse.

Add the consignment product under the Product column in the order lines, set the Quantity, and fill out any other pertinent product details on the form. Once the quotation is complete, click Confirm.

Once the quotation has been confirmed, it becomes a sales order. From here, the products can be delivered by clicking on the Delivery smart button, and selecting Validate to validate the delivery.

## Traceability and reporting of consignment stock¶

Although consignment stock is owned by the vendor who supplied it, and not by the company storing it in their warehouse, consignment products will _still_ appear in certain inventory reports.

To find inventory reports, go to Inventory ‣ Reporting, and choose a report to view.

Nota

Since the consignee does not actually own consignment stock, these products are _not_ reflected in the Stock Valuation report, and have no impact on the consignee’s inventory valuation.

### Product moves report¶

To view all information about on-hand stock moves, navigate to the Product Moves dashboard by going to Inventory ‣ Reporting ‣ Product Moves. For consignment products, the information in this report is the same as any other product: the history of its product moves can be reviewed; the Quantity Done and Reference document are available; and its Locations are available, as well. The consignment stock will originate from Partner Location/Vendors.

Suggerimento

To view a consignment product’s moves by ownership, select the Group By filter, choose the Add Custom Group parameter, and then select From Owner, and Apply to finish.

Suggerimento

To see forecasted units of consignment stock, go to Inventory ‣ Reporting ‣ Forecasted Inventory.

### Stock on hand report¶

View the Stock On Hand dashboard by navigating to Inventory ‣ Reporting ‣ Inventory Report. From this report, the Locations of all stock on-hand are displayed, in addition to the quantities per location. For consignment products, the Owner column will be populated with the owner of those products, or the original vendor who supplied the products in the first place.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/daily_operations/owned_stock.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dropshipping.html "Dropshipping") |
  * [precedente](stock_warehouses.html "Sell stock from multiple warehouses using virtual locations") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Inbound and outbound flows](../daily_operations.html) »
  * Consignment: buy and sell stock without owning it


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