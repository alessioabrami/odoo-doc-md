# Basic subcontracting lead times — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subcontracting_resupply.html "Resupply subcontractor") |
  * [precedente](subcontracting_basic.html "Basic subcontracting") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Basic subcontracting lead times



# Basic subcontracting lead times¶

In Odoo, lead times are used to predict how long it takes to complete a certain action. For example, a _delivery lead time_ can be set for a purchased product, which specifies the number of days it usually takes for the product’s vendor to delivery the product to the purchasing company.

For subcontracted products specifically, delivery lead times can be configured to take into account the amount of time required for the subcontractor to manufacture a product. Doing so allows the contracting company to better predict the delivery dates of subcontracted products.

Importante

Like all lead times in Odoo, lead times for subcontracted products are only an estimate, and are based on how long actions are _expected_ to take.

Unforeseen circumstances can impact the completion of these actions, which means that lead times should not be viewed as guarantees.

## Configurazione¶

When using the [basic subcontracting](subcontracting_basic.html) workflow to manufacture a product, a company is not responsible for supplying the subcontractor with the necessary components. This means that the only factors affecting the delivery date of a product are the amount of time it takes the subcontractor to manufacture and deliver it.

By assigning a product’s subcontractor a delivery lead time that considers both of these factors, the _Expected Arrival_ date displayed on purchase orders (POs) for the product more accurately reflects the amount of time required for both manufacturing and delivery.

### Product delivery lead time¶

To set a delivery lead time for a product’s subcontractor, navigate to Inventory app ‣ Products ‣ Products, and select a subcontracted product.

Then, select the Purchase tab on the product’s page. If the subcontractor has not already been added as a vendor, do so now by clicking Add a line, and selecting the subcontractor in the Vendor column.

Once the subcontractor has been added, enter the number of days it takes them to manufacture and deliver the product, in the Delivery Lead Time column.

Nota

Multiple subcontractors can be added to the Purchase tab on a product’s page, and a different Delivery Lead Time can be set for each.

## Lead time workflow¶

After setting a delivery lead time for a product’s vendor, create an RfQ by navigating to Purchase app ‣ Orders ‣ Purchase Orders, and clicking New.

Specify the subcontractor in the Vendor field. Then, add the product in the Products tab by clicking Add a product, selecting the product in the Product column, and adding a quantity in the Quantity column.

Once a product has been added, the Expected Arrival field on the RfQ auto-populates with a date that reflects the vendor’s delivery lead time, as specified on the product’s page.

If the date needs to be adjusted, click on the Expected Arrival field to open a calendar popover, and select the desired date. Make sure not to choose a date sooner than the one that was auto-populated, unless the subcontractor has confirmed that they are able to deliver the product by that date.

Finally, click Confirm Order on the RfQ to turn it into a PO. At this point, the subcontractor should begin manufacturing the subcontracted product, before delivering it to the contracting company.

Example

Bike retailer _Mike’s Bikes_ works with a subcontractor — _Bike Friends_ — to produce units of their _Tricycle_ product.

On average, Bike Friends requires three days to manufacture a tricycle, plus an additional two days to deliver it to Mike’s Bikes.

As a result, Mike’s Bikes sets a delivery lead time of five days for tricycles manufactured by Bike Friends: three days for manufacturing, plus two days for delivery.

On May 3rd, Mike’s Bikes confirms a PO to purchase one tricycle from Bike Friends.

The Expected Arrival date listed on the PO is May 8th, five days after the Confirmation Date.

Bike Friends begins manufacturing the tricycle on May 3rd — the day that the PO is confirmed — and finishes on May 6th, three days later.

The tricycle is then shipped to Mike’s Bikes the same day, and they receive it on May 8th, two days later.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/subcontracting/basic_subcontracting_lead_times.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subcontracting_resupply.html "Resupply subcontractor") |
  * [precedente](subcontracting_basic.html "Basic subcontracting") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Basic subcontracting lead times


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
  *[BoMs]: bills of materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order