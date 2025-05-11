# Before scheduled date reservation — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../picking_methods.html "Picking methods") |
  * [precedente](manually.html "Manual reservation") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Reservation methods](../reservation_methods.html) »
  * Before scheduled date reservation



# Before scheduled date reservation¶

The _Before scheduled date_ reservation method allows users to select a specific number of days that act as the maximum number of days **before** a scheduled delivery date, when products included in a sales order (SO) should be reserved.

Vedi anche

[About reservation methods](../reservation_methods.html)

## Configurazione¶

To set the reservation method to _Before scheduled date_ , navigate to Inventory app ‣ Configuration ‣ Operations Types. Then, select the desired Operation Type to configure, or create a new one by clicking New.

In the General tab, locate the Reservation Method field, and select Before scheduled date.

Nota

When the Type of Operation is changed to Receipt on an Operations Type form, reservation methods are **not** available.

Once selected, a new Reserve before scheduled date field appears below. From this field, the number of days before and days before when starred can be changed from the default `0`.

Changing the days before value changes the maximum number of days before a scheduled date that products should be reserved.

Changing the days before when starred value changes the maximum number of days before a scheduled date that products should be reserved if the transfers are starred (favorited).

Example

Here, the days before value is set to `2` days before, and the days before when starred value is set to `3`.

This means products are reserved two days before the scheduled delivery date for normal orders, and three days before the scheduled delivery date for starred (favorited) transfers.

This is the configuration applied for the following workflow found below.

### Edit product form¶

Before the _Before scheduled date_ reservation method can be used, ensure that a _customer lead time_ is added to products that plan to be sold with this method.

To do that, navigate to Inventory app ‣ Products ‣ Products, and select the desired product to configure.

On the product form, click the Inventory tab, and under the Logistics section, change the value in the Customer Lead Time field.

For this example workflow, change it to `5` days.

This sets the scheduled delivery date for this specific product to five days after the creation date of the sales order.

## Flusso di lavoro¶

To see the _Before scheduled date_ reservation method in action, create a new SO by navigating to Sales app ‣ New.

Add a customer in the Customer field, then, in the Order Lines tab, click Add a product, and select a product from the drop-down menu that has a configured _customer lead time_ , to add to the quotation form.

Finally, in the Quantity column, adjust the desired quantity of the product to sell.

For this sample workflow, set the Quantity to `10`.

Once ready, click Confirm to confirm the sales order.

Click the green 📈 (area graph) icon on the product line to reveal the product’s Availability tooltip. This tooltip reveals the reserved number of units for this order. Because the reservation method is set to _Before scheduled date_ , the Reserved quantity reads `0 Units`.

However, below that quantity reads `Available in stock`. This is because the quantity is available, but the scheduled date, for this example workflow, is five days from the order date.

Since reservation is not until two days before the scheduled delivery, it will not reserve the products until then.

Nota

If there is **not** sufficient quantity of stock for the product included in the SO, the 📈 (area graph) icon is red, instead of green.

Instead of revealing the reserved number of units for the order, the Availability tooltip reads Reserved, and reveals the available number of units (e.g., `0 Units`).

Additionally, unless there is a set replenishment or a live receipt, it also reads No future availability, in red text.

Click the Delivery smart button to see the delivery order form.

On the delivery order form, the status in the Product Availability field is listed as `Available`, in yellow text, instead of green. This is because there is sufficient stock on-hand for this order, but no quantity has been reserved yet.

Note the Scheduled Date field, above the Product Availability field, displays the date five days from the order creation date. This indicates that the products are not reserved until three days from today’s date (two days before the scheduled delivery date).

In the Operations tab on the Product line, the numbers in the Demand column and the Quantity column do not match (in this case, the Demand column lists `10.00`, while the Quantity column lists `0`).

The Quantity column lists `0` because the products aren’t reserved until two days _before_ their delivery date. Odoo automatically reserves the products once the scheduled date arrives, at which point the Demand and Quantity columns will match.

Suggerimento

If the products in the SO should be reserved _sooner_ than the scheduled reservation date, the reservation can be manually overridden. To manually reserve the products sooner than scheduled, click Check Availability at the top of the form.

This turns the `Available` status in the Product Availability field green, and changes the number in the Quantity column to match the Demand column.

Once ready, click Validate.

Vedi anche

  * [Manual reservation](manually.html)

  * [At confirmation reservation](at_confirmation.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/reservation_methods/before_scheduled_date.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../picking_methods.html "Picking methods") |
  * [precedente](manually.html "Manual reservation") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Reservation methods](../reservation_methods.html) »
  * Before scheduled date reservation


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