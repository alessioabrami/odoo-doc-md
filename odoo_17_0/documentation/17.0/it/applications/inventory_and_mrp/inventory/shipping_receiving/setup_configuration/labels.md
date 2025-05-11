# Print shipping labels — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bpost.html "Bpost integration") |
  * [precedente](third_party_shipper.html "Third-party shipping carriers") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Print shipping labels



# Print shipping labels¶

Integrate Odoo with [third-party shipping carriers](third_party_shipper.html) to automatically generate shipping labels that includes prices, destination addresses, tracking numbers, and barcodes.

Vedi anche

[Automatically print shipping carrier labels](print_on_validation.html#inventory-shipping-receiving-carrier-labels)

## Configurazione¶

To generate labels for a third-party shipping carrier, first [install the third-party shipping connector](third_party_shipper.html). Then, configure and activate the [delivery method](third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method), being sure to set the Integration Level to Get Rate and Create Shipment to generate shipping labels. Finally, provide the company’s [source address](third_party_shipper.html#inventory-shipping-receiving-configure-source-address) and [product weights](third_party_shipper.html#inventory-shipping-receiving-configure-weight).

Vedi anche

[Third-party shipping carriers](third_party_shipper.html)

### Labels for multi-step¶

For companies using [two](../daily_operations/receipts_delivery_two_steps.html) or [three step delivery](../daily_operations/delivery_three_steps.html), labels can be triggered to print after validating the picking or packing operation. To do that, go to Inventory app ‣ Configuration ‣ Operations Types, and choose the desired operation.

On the Operation Type configuration page, tick the Print Label checkbox. Enabling this feature ensures that the third-party shipping label is printed upon validating this operation.

Example

For [two-step delivery](../daily_operations/receipts_delivery_two_steps.html), where products are placed directly in packages during picking, companies can print shipping labels during picking instead of delivery. Odoo allows users to enable the Print Label feature on the `Pick` operation itself to achieve this flexibility.

## Print tracking labels¶

Tracking labels are printed when specific operations are validated. By default, validating a delivery order (DO) generates a tracking label in the chatter.

Nota

For companies using two or three step delivery, refer to the printing labels for multi-step delivery section to learn how to print the label after validating a picking or packing operation.

When both the _Sales_ and _Inventory_ apps are installed, begin in the Sales app, and proceed to the desired quotation or sales order (SO). There, and add the shipping cost to the order. Then, navigate to the linked DO — or another operation type when using multi-step delivery — to validate the operation and print the label.

If only the _Inventory_ app is installed, create DOs directly in the Inventory app, add the third-party carrier in the Carrier field, and validate the DO.

### Add shipping on quotation¶

To generate a tracking label for an order, begin by creating a quotation in Sales app ‣ Orders ‣ Quotations, clicking New, and filling out the quotation form. Then, click the Add Shipping button in the bottom-right corner of the quotation.

In the resulting pop-up window, select the intended carrier from the Shipping Method drop-down menu. The Total Order Weight field is automatically populated, based on the [weight of products in the order](third_party_shipper.html#inventory-shipping-receiving-configure-weight). Modify this field to overwrite the predicted weight, and use this weight to estimate the cost of shipping.

Next, click Get Rate to display the shipping cost for the customer, via the third-party carrier in the Cost field.

Importante

If clicking Get Rate results in an error, ensure the [warehouse’s address](third_party_shipper.html#inventory-shipping-receiving-configure-source-address) and [weight of products in the order](third_party_shipper.html#inventory-shipping-receiving-configure-weight) are properly configured.

Click Add to add the cost to the quotation, which is listed as the [configured delivery product](../setup_configuration.html#inventory-shipping-receiving-delivery-product). Finally, click Confirm on the quotation, and click the Delivery smart button to access the DO.

Suggerimento

For users who do not have the _Sales_ app installed, specify the Carrier by going to the Inventory app, navigating to the DO, and going to the Additional Info tab.

### Validate delivery order¶

On a delivery order form, navigate to the Additional Info tab to ensure the third-party shipping carrier has been added to the Carrier field.

Importante

If the _Sales_ app is not installed, the third-party carrier is set in the Carrier field.

After the items in the order have been packed, click Validate to get the shipping carrier’s tracking number, and generate the shipping label.

Nota

Create or select an existing delivery order by going to the Inventory app, and selecting the Delivery Orders card.

The Tracking Reference number is generated in the Additional Info tab of the delivery order. Click the Tracking smart button to access the tracking link from the shipping carrier’s website.

The tracking label is found in PDF format in the chatter.

Nota

For multi-package shipping, one label is generated per package. Each label appears in the chatter.

Sample label generated from Odoo’s shipping connector with FedEx.¶

Vedi anche

  * [Shipping cost invoicing](invoicing.html)

  * [Multi-package shipments](multipack.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/labels.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bpost.html "Bpost integration") |
  * [precedente](third_party_shipper.html "Third-party shipping carriers") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Print shipping labels


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