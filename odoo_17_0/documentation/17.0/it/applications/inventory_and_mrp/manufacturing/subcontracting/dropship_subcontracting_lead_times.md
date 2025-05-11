# Dropship subcontracting lead times — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reporting.html "Rendiconto") |
  * [precedente](subcontracting_dropship.html "Dropship to subcontractor") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Dropship subcontracting lead times



# Dropship subcontracting lead times¶

In Odoo, lead times are used to predict how long it takes to complete a certain action. For example, a _delivery lead time_ can be set for a purchased product, which specifies the number of days it usually takes for the product’s vendor to deliver the product to the purchasing company.

For subcontracted products specifically, delivery lead times can be configured to take into account the amount of time required for the subcontractor to manufacture a product. Doing so allows the contracting company to better predict the delivery dates of subcontracted products.

Certain subcontracted products require the contracting company to supply the subcontractor with manufacturing components. In this case, a _manufacturing lead time_ can be used, in addition to the delivery lead time, to generate the date on which the subcontractor must receive the required components, in order to manufacture the product and deliver it on time.

In cases where components are dropshipped to the subcontractor, an additional delivery lead time can be set for each component. This should be set to the amount of time it takes the vendor to deliver components to the subcontractor.

Once a delivery lead time has been set on a component, dropship orders for the component display the date by which the order must be confirmed, so that it can be dropshipped to the subcontractor by the date on which manufacturing must begin.

Importante

Like all lead times in Odoo, lead times for subcontracted products are only an estimate, and are based on how long actions are _expected_ to take.

Unforeseen circumstances can impact the completion of these actions, which means that lead times should not be viewed as guarantees.

## Configurazione¶

When using the [Dropship Subcontractor on Order](subcontracting_dropship.html) route, a company is responsible for purchasing the necessary components from a vendor, and having them dropshipped directly to the subcontractor.

This means that, in addition to the amount of time it takes the subcontractor to manufacture and deliver the product, it is also necessary to consider how long it takes the component vendor to dropship the components to the subcontractor.

By assigning a product’s subcontractor a _delivery lead time_ , specifying a _manufacturing lead time_ on the product’s BoM, and assigning the vendor of the components an additional _delivery lead time_ , _Dropship Subcontractor_ orders for the product’s components display the deadline for confirming a dropship order to send the components to the subcontractor.

### Product delivery lead time¶

To set a delivery lead time for a product’s subcontractor, navigate to Inventory app –> Products –> Products, and select a subcontracted product.

Then, select the Purchase tab on the product’s page. If the subcontractor has not already been added as a vendor, do so now by clicking Add a line, and selecting the subcontractor in the Vendor column.

Once the subcontractor has been added, enter the number of days it takes them to manufacture and deliver the product, in the Delivery Lead Time column.

### Product manufacturing lead time¶

Next, navigate to the product’s BoM by clicking the Bill of Materials smart button at the top of the product’s page. Then, select a BoM from the list.

On the BoM, select the Miscellaneous tab. In the Manuf. Lead Time field, enter the same number of days that was entered in the Delivery Lead Time field of the BoM’s product.

While not all of these days are actually used for manufacturing by the subcontractor, setting the same number of days in each field tells Odoo that the subcontractor must receive the components and begin production by the start of the product’s delivery lead time. This gives the subcontractor enough time to both manufacture and deliver the product.

### Component delivery lead time¶

From the product’s BoM, navigate to each component by clicking on the component in the Components tab, and then clicking the __(right arrow) button to the right of the component.

On the product page for each component, select the Purchase tab. If the vendor has not already been added, do so now by clicking Add a line, and selecting the subcontractor in the Vendor column.

Once the vendor has been added, enter the number of days it takes them to dropship the product to the subcontractor, in the Delivery Lead Time column.

## Dropship subcontracting workflow¶

Create a request for quotation (RfQ) for the product by navigating to Purchase app ‣ Orders ‣ Requests for Quotation, and clicking New.

Specify the subcontractor in Vendor field. Then, add the product in the Products tab by clicking Add a product, selecting the product in the Product column, and specifying a quantity in the Quantity column.

In the Expected Arrival field, enter a date that provides enough time for the component vendor to dropship the components, and the subcontractor to manufacture and deliver the product.

Importante

When a product is added to an RfQ, the Expected Arrival field auto-populates with a date that is today’s date plus the delivery lead time of the product. However, this does not consider the time it takes to dropship the components to the subcontractor.

When purchasing a product subcontracted using the _Dropship Subcontractor on Order_ route, it is necessary to adjust this date to take into account the extra time needed for the components to be delivered to the subcontractor.

Since production does not begin until they receive the components, leaving the date as is results in the finished product arriving _after_ the date listed on the RfQ.

Next, click Confirm Order to turn the RfQ into a PO. Doing so creates a second RfQ to purchase the components from the dropshipper, and have them sent to the subcontractor.

Navigate to Purchase app ‣ Orders ‣ Requests for Quotation, and select the RfQ that lists the dropshipper in the Vendor column.

On the RfQ, the Expected Arrival field lists the date on which the subcontractor must receive the components, in order to deliver the finished product by the _Expected Arrival_ date listed on the subcontractor PO.

The Order Deadline field lists the latest date on which the RfQ can be confirmed, in order for the dropshipper to deliver the components to the subcontractor by the Expected Arrival date.

Click Confirm Order to turn the RfQ into a PO, and confirm the purchase of the components from the dropshipper. Doing so causes a Dropship smart button to appear at the top of the page.

Click the Dropship smart button to open the dropship order. This order can also be accessed from the Resupply smart button that now appears on the subcontractor PO.

After the dropshipper has delivered the components to the subcontractor, click the Validate button at the top of the dropship order to confirm that the subcontractor has received the components.

Once the subcontractor receives the components, they begin manufacturing the component, before delivering it to the contracting company.

Example

Bike retailer _Mike’s Bikes_ works with a subcontractor — _Bike Friends_ — to produce units of their _Bicycle_ product.

Mike’s Bikes must purchase the required components from vendor Bike World, and have them dropshipped to Bike Friends.

On average, Bike Friends takes three days to manufacture each bicycle, plus an addition two days to deliver it to Mike’s Bikes.

As a result, Mike’s Bikes sets a delivery lead time of five days for bicycle manufactured by Bike Friends: three days for manufacturing, plus two days for delivery.

On the bicycle’s BoM, they enter a manufacturing lead time of five days as well, to remind themselves of the date that components must be delivered to the subcontractor.

On the product pages for each of the bicycle’s components, they assign Bike World a delivery lead time of two days. This is the amount of time it takes Bike World to dropship each component directly to the subcontractor.

On May 10th, Mike’s Bikes confirms a PO for one bicycle, with an expected delivery date of May 17th.

The RfQ for purchasing the components from Bike World and having them dropshipped to Bike Friends has an Expected Arrival date of May 12th, and a Deadline of May 10th. The RfQ must be confirmed by the deadline in order for Bike Friends to receive the components by the Expected Arrival date, giving them enough time to deliver the finished bicycle to Mike’s Bikes by May 17th.

Mike’s Bikes confirms the RfQ on May 10th, and Bike World delivers the components to Bike Friends on May 12th. Bike Friends manufactures the bicycle, and delivers it to Mike’s Bikes on May 17th.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/subcontracting/dropship_subcontracting_lead_times.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reporting.html "Rendiconto") |
  * [precedente](subcontracting_dropship.html "Dropship to subcontractor") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Dropship subcontracting lead times


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