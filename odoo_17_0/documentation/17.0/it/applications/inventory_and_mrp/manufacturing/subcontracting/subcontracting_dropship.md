# Dropship to subcontractor — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dropship_subcontracting_lead_times.html "Dropship subcontracting lead times") |
  * [precedente](resupply_subcontracting_lead_times.html "Resupply subcontracting lead times") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Dropship to subcontractor



# Dropship to subcontractor¶

In manufacturing, subcontracting is the process of a company engaging a third-party manufacturer, or subcontractor, to manufacture products that are then sold by the contracting company.

In Odoo, the _Dropship Subcontractor on Order_ route is used to purchase the necessary components for a subcontracted product from the vendor, and have them delivered directly to the subcontractor, each time a purchase order (PO) for that product is confirmed.

The subcontractor then uses the components to manufacture the desired product, before shipping it back to the contracting company.

Importante

It is necessary to understand the differences between the _Dropship_ and _Dropship Subcontractor on Order_ routes. While both routes involve dropshipping, they are used for different purposes.

The _Dropship_ route is used to purchase products from a vendor, and have them shipped directly to the end customer.

The _Dropship Subcontractor on Order_ route is used to purchase components from a vendor, and have them shipped directly to a subcontractor. By default, finished products are then sent from the subcontractor back to the contracting company.

However, it is possible to combine both the _Dropship_ and _Dropship Subcontractor on Order_ routes so they are used for the same product. In this workflow, components are dropshipped to the subcontractor, who then ships the finished product directly to the end customer.

This can be achieved by following steps one through five in the workflow section of this doc.

## Configurazione¶

To use the _Dropship Subcontractor on Order_ route, navigate to Manufacturing app ‣ Configuration ‣ Settings, and enable the checkbox next to Subcontracting, under the Operations heading.

Once the _Subcontracting_ setting is enabled, it is also necessary to properly configure the subcontracted product, the product’s BoM, and the components listed on the BoM.

### Configure product¶

To configure a product for the _Dropship Subcontractor on Order_ route, navigate to Inventory app ‣ Products ‣ Products, and select a product, or create a new one by clicking New.

Select the Purchase tab, and add the product’s subcontractor as a vendor by clicking Add a line, selecting the subcontractor in the Vendor drop-down menu, and entering a price in the Price field.

Then, click on the Inventory tab to configure a route that determines what happens to the finished product, once it has been manufactured by the subcontractor.

If the finished product is shipped back to the contracting company, make sure that the Buy route is selected. In addition, select the Replenish on Order (MTO) route to automatically create a PO for the product upon confirmation of a SO, unless there is enough stock on-hand to fulfill the SO.

If the finished product is shipped directly to the customer by the subcontractor, make sure that only the Dropship route is selected.

### Configure bill of materials¶

To configure a BoM for the _Dropship Subcontractor on Order_ route, click the Bill of Materials smart button on the product’s page, and select the BoM.

Alternatively, navigate to Manufacturing app ‣ Products ‣ Bills of Materials, and select the BoM for the subcontracted product.

Vedi anche

For a full overview of BoM configuration, see the [Bill of materials](../basic_setup/bill_configuration.html) documentation.

In the BoM Type field, select the Subcontracting option. Then, add one or more subcontractors in the Subcontractors field that appears below.

Finally, make sure that all necessary components are specified on the Components tab. To add a new component, click Add a line, select the component in the Component drop-down menu, and specify the required quantity in the Quantity field.

### Configure Components¶

To configure components for the _Dropship Subcontractor on Order_ route, navigate to each component from the BoM by selecting the component’s name in the Components tab, and clicking the ➡️ (right arrow) button to the right of the name.

Alternatively, navigate to each component by going to Inventory app ‣ Products ‣ Products, and selecting the component.

On the component product form, select the Purchase tab, and add a vendor by clicking Add a line, selecting the vendor in the Vendor field, and adding the price they sell the product for in the Price field. This is the vendor that sends components to the subcontractor, once they are purchased.

Then, click on the Inventory tab and select the Dropship Subcontractor on Order route in the Routes section.

Repeat the process for every component that must be dropshipped to the subcontractor.

## Dropship subcontractor on order workflow¶

The dropship subcontractor on order workflow consists of up to six steps:

  1. Create a sales order (SO) for the subcontracted product; doing so creates a _subcontractor_ PO to purchase the product from the subcontractor.

  2. Confirm the PO created in the previous step, or create a new PO; doing so creates a request for quotation (RfQ) to purchase the components from the vendor, as well as a receipt order or a dropship order.

  3. Confirm the RfQ to turn it into a second PO (_vendor_ PO); doing so creates a _Dropship Subcontractor_ order.

  4. Process the _Dropship Subcontractor_ order once the vendor has sent the components to the subcontractor.

  5. Process the receipt once the subcontractor has finished manufacturing the subcontracted product, and shipped it back to the contracting company **OR** process the dropship order to ship the product directly to the end customer.

  6. If the workflow was started by creating an SO, and the finished product is not dropshipped to the end customer, process the delivery order once the product has been shipped to the customer.




The specific number of steps depends on the reason that the subcontracted product is being purchased from the subcontractor.

If the reason is to fulfill a specific customer order, the process starts with creating an SO, and ends with delivering the product to the customer, or having the subcontractor dropship it to them.

If the reason is to increase quantity of stock on-hand, the process starts with creating a PO, and ends with receiving the product into inventory.

### Create an SO¶

It is only necessary to complete this step if the product is being purchased from the subcontractor to fulfill a customer need. If the product is being purchased to increase the quantity of stock on-hand, move on to the next step.

To create a new SO, navigate to Sales app ‣ Orders ‣ Orders, and click New.

Select the customer in the Customer drop-down menu. Then, click Add a product on the Order Lines tab, select the product in the Product drop-down menu, and enter a quantity in the Quantity field.

Click Confirm to confirm the SO, at which point a Purchase smart button appears at the top of the page. This is the _subcontractor_ PO, or the PO created to purchase the subcontracted product from the subcontractor.

Nota

An SO for the product only creates a _subcontractor_ PO if the _Replenish on Order (MTO)_ route is enabled on the product’s page, **and** there is no stock of the product on-hand.

If there is stock on-hand, confirming an SO for the product will instead create a delivery order, because Odoo assumes that the SO is fulfilled using the stock in the warehouse.

This is not the case for subcontracted products that are dropshipped to the end customer. In that case, a _subcontractor_ PO is **always** created, even if there is stock on-hand.

### Process subcontractor PO¶

If a _subcontractor_ PO was not created in the previous step, do so now by navigating to Purchase app ‣ Orders ‣ Purchase Orders, and clicking New.

Begin filling out the PO by selecting a subcontractor from the Vendor drop-down menu.

In the Products tab, click Add a product to create a new product line. Select a product produced by the subcontractor in the Product field, and enter the quantity in the Quantity field.

Finally, click Confirm Order to confirm the _subcontractor_ PO.

When a PO is confirmed for a product that requires dropshipping components to a subcontractor, a receipt or dropship order is automatically created, and can be accessed from the corresponding Receipt or Dropship smart button that appears at the top of the PO.

In addition, an RfQ is created for the components that are purchased from the vendor and sent to the subcontractor. However, the RfQ **IS NOT** automatically linked to the _subcontractor_ PO.

Once the RfQ is confirmed and becomes a _vendor_ PO, a _Dropship Subcontractor_ order is created. This order is linked to both the _vendor_ PO and the _subcontractor_ PO.

### Confirm vendor RfQ¶

To access the RfQ created by confirming the _subcontractor_ PO, navigate to Purchase app ‣ Orders ‣ Requests for Quotation. Select the RfQ that lists the correct vendor in the Vendor field, and the reference number of the receipt that was created after confirming _subcontractor_ PO, in the Source Document field.

On the RfQ, the Deliver To field reads Dropship Subcontractor, and the Dropship Address field shows the name of the subcontractor to whom components are being dropshipped.

Click Confirm Order to turn the RfQ into a _vendor_ PO, and confirm the purchase of components from the vendor. After doing so, a Dropship smart button appears at the top of the _vendor_ PO, and a Resupply smart button appears at the top of the _subcontractor_ PO.

### Process Dropship Subcontractor order¶

Once the components have been delivered to the subcontractor, navigate to Purchase app ‣ Orders ‣ Purchase Orders, and select the _vendor_ PO or the _subcontractor_ PO. Then, click the Dropship smart button or the Resupply smart button, respectively.

Clicking either button opens the _Dropship Subcontractor_ order. Click the Validate button at the top of the order to confirm that the subcontractor has received the components.

### Process receipt or dropship order¶

Once the subcontractor has manufactured the finished product, navigate to Purchase app ‣ Orders ‣ Purchase Orders, and select the _subcontractor_ PO.

If the subcontracted product should be received into inventory, once the product arrives, click the Receive Products button at the top of the _subcontractor_ PO to open the receipt. Then, click Validate at the top of the receipt to register the product into inventory.

Alternatively, select the Receipt smart button at the top of the _subcontractor_ PO, and click Validate at the top of the receipt.

If the subcontracted product should be dropshipped, select the Dropship button at the top of the page to open the dropship order, and click Validate once the subcontractor has sent the product to the customer.

### Process delivery order¶

If the subcontracting workflow was started by a customer SO, and the finished product was **not** dropshipped to the customer, but rather delivered to the contracting company, it is necessary to ship the product to the customer, and process the delivery order.

Once the product has been shipped to the customer, navigate to the Sales app, and select the SO. Select the Delivery smart button at the top of the page to open the delivery order, and click Validate to confirm that the product has been shipped to the customer.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/subcontracting/subcontracting_dropship.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dropship_subcontracting_lead_times.html "Dropship subcontracting lead times") |
  * [precedente](resupply_subcontracting_lead_times.html "Resupply subcontracting lead times") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Dropship to subcontractor


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