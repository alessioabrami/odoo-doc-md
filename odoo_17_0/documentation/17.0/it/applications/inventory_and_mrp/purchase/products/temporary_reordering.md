# Temporary reordering rules — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Purchase units of measure") |
  * [precedente](reordering.html "Configure reordering rules") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Temporary reordering rules



# Temporary reordering rules¶

Some businesses require certain products to always have a minimum quantity of stock on-hand at any given time. To avoid stock falling below a certain threshold, companies can create _reordering rules_ in Odoo to automate purchase orders for specific products.

Reordering rules keep the forecasted stock levels above a certain threshold, without exceeding a specified upper limit, or maximum amount. When a product with a reordering rule falls below a specified quantity, Odoo generates an order using the specified _route_ (e.g. _Buy_ or _Manufacture_) to replenish the stock.

In certain cases, businesses might opt for _temporary reordering rules_ when they do not want specific products to be replenished automatically.

In Odoo, a «temporary» reordering rule is created in the replenishment dashboard when a product:

  1. is configured with a _Buy_ route

  2. has no reordering rule configured

  3. has `0` quantity in stock

  4. is included in a sales order (SO).




This rule is deleted upon confirmation of the purchase order (PO) generated for the product.

Vedi anche

  * [Reordering rules](../../inventory/warehouses_storage/replenishment/reordering_rules.html)

  * [Configure reordering rules](reordering.html)




## Configurazione¶

To configure a product that triggers temporary reordering rules when its stock reaches `0`, begin by going to Inventory app ‣ Products ‣ Products, and click New.

Nota

The same configurations can also be made on an existing product, by going to Inventory app ‣ Products ‣ Products, and selecting an existing product.

On the product form, enter the product name, and ensure the Can be Sold and Can be Purchased options are enabled, located beneath the Product Name field.

Then, set the Product Type to `Storable Product`, under the General Information tab.

Next, click the Purchase tab, and under Vendor, click Add a line to select a vendor from the drop-down menu. Then, set a purchase price under Price.

Importante

A vendor **must** be set for temporary reordering rules to work. While a PO can still be created automatically, attempting to replenish the product from the Replenishment dashboard in the _Inventory_ app triggers a warning to add a vendor on the product form.

Before creating a SO for the product, ensure the On Hand smart button on the product form reads `0.00 Units`. Then, ensure that the Reordering Rules smart button reads `0`, indicating there are no rules applied to this product.

## Trigger temporary reordering rule¶

To trigger a temporary reordering rule, create a new sales order for a product by navigating to Sales app ‣ New.

Then, add a customer in the Customer field, and click Add a product under the Product column in the Order Lines tab. Next, select the desired product from the drop-down menu. Lastly, Confirm the SO.

## Check replenishment report¶

To see the temporary reordering rule created for the out-of-stock product included in the sales order, navigate to Inventory app ‣ Operations ‣ Replenishment. Doing so opens the Replenishment dashboard.

On this dashboard, locate the product for which the temporary reordering rule was created. On its product line, its On Hand quantity, negative Forecast quantity, _Buy_ Route, and To Order quantity to replenish can be seen.

Additionally, two replenishment options are located to the far-right of the row: Order Once and Automate.

To use the one-time, temporary reordering rule, click Order Once. This action triggers a confirmation pop-up window in the top-right corner, reading The following replenishment order has been generated, along with a new purchase order number.

Suggerimento

Once the purchase order has been generated after clicking Order Once, refresh the page. The temporary reordering rule for the product no longer appears in the Replenishment dashboard.

## Complete purchase order¶

To view the purchase order created from the Replenishment dashboard, navigate to the Purchase app, and select the generated PO from the Requests for Quotation overview.

From here, click Confirm Order, then click Receive Products. Finally, click Validate to complete the purchase order.

Now, the original sales order can be delivered and invoiced.

Nota

Once the SO is delivered and invoiced, ensure there are no reordering rules on the product form.

Go to Inventory app ‣ Products ‣ Products, select the product, and confirm that the Reordering Rules smart button displays `0`.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/products/temporary_reordering.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](uom.html "Purchase units of measure") |
  * [precedente](reordering.html "Configure reordering rules") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Temporary reordering rules


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
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: purchase order
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