# Process repair orders — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../hr.html "Human resources") |
  * [precedente](../repairs.html "Riparazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Riparazioni](../repairs.html) »
  * Process repair orders



# Process repair orders¶

Sometimes, products delivered to customers can break or be damaged in transit, and need to be returned for a refund, delivery of a replacement product, or repairs.

In Odoo, repairs for products returned by customers can be tracked in the _Repairs_ app. Once repaired, products can be redelivered to the customer.

The return and repair process for damaged products typically follows the below steps:

  1. Process return order for damaged product

  2. Create repair order for returned product

  3. Return repaired product to customer




## Return order¶

Returns can be processed in Odoo via _reverse transfers_ , created directly from a sales order (SO) once products have been delivered to a customer.

To create a return, navigate to the Sales app, and click into an SO from which a product should be returned. Then, from the SO form, click the Delivery smart button. Doing so opens the delivery order (DO) form.

From this form, click Return. This opens a Reverse Transfer pop-up window.

This pop-up lists the Product included in the order, the Quantity delivered to the customer, and the Unit of Measure the product was in.

Click the value in the Quantity field to change the quantity of the product to be returned, if necessary.

Click the 🗑️ (trash) icon at the far-right of the product line to remove it from the return, if necessary.

Once ready, click Return to confirm the return. This creates a new receipt for the returned products.

Once the product has been returned to the warehouse, receipt of the return can be registered in the database by clicking Validate from the reverse transfer form.

Suggerimento

Once a reverse transfer for a return is validated, the value in the Delivered column on the original SO updates to reflect the difference between the original Quantity ordered, and the Quantity returned by the customer.

## Create repair order¶

Once products have been returned, their repairs can be tracked by creating a repair order (RO).

To create a new RO, navigate to Repairs app, and click New. This opens a blank RO form.

On this form, begin by selecting a Customer. The customer selected should be for whom the order will be invoiced and delivered.

In the Product to Repair field, click the drop-down menu to select the product that needs repair. If necessary, click Search More… to open a Search: Product to Repair pop-up window, and browse all products in the database.

Once a Product to Repair is selected, a new Product Quantity field appears below it. In that field, enter the quantity (in a `0.00` format) of the product that requires repair.

To the right of that value, click the drop-down list to select the unit of measure (UoM) for the product.

In the Return field, click the drop-down menu and select the return order from which the product to be repaired comes from.

Tick the Under Warranty checkbox, if the product being repaired is covered by a warranty. If ticked, the Customer is not charged for all the parts used in the repair order.

In the Scheduled Date field, click the date to reveal a calendar popover window. From this calendar, select a date for the repair, and click Apply.

In the Responsible field, click the drop-down menu and select the user who should be responsible for the repair.

In the Company field, if in a multi-company environment, select which company this RO belongs to.

In the Tags field, click the drop-down menu and select which tags should be applied to this RO.

### Parts tab¶

Add, remove, or recycle parts in the Parts tab. To do so, click Add a line at the bottom of the form.

In the Type column, click the box to reveal three options to choose from: Add (selected by default), Remove, and Recycle.

Choosing Add adds this part to the RO. Adding parts lists components for use in the repair. If the components are used, the user completing the repair can record they were used. If they were not used, the user can indicate that, too, and the components can be saved for another use.

Choosing Remove removes this part from the RO. Removing parts lists components that should be removed from the product being repaired during the repair process. If the parts are removed, the user completing the repair can indicate they were removed.

Choosing Recycle recycles this part from the RO, designating it for later use or to be repurposed for another use in the warehouse.

In the Product column, select which product (part) should be added, removed, or recycled. In the Demand column, change the quantity, if necessary, to indicate what quantity of this part should be used in the repair process.

In the Done column, change the value (in a `0.00` format) once the part has been successfully added, removed, or recycled.

In the Unit of Measure column, select the UoM for the part.

Finally, in the Used column, tick the checkbox once the part has been used in the repair process.

To add additional columns to the line, click the (optional columns drop-down) icon, at the far-right of the header row. Select the desired options to add to the line.

### Repair Notes and Miscellaneous tabs¶

Click the Repair Notes tab to add internal notes about this specific RO, and anything the user performing the repair might need to know.

Click the blank text field to begin writing notes.

Click the Miscellaneous tab to see the Operation Type for this repair. By default, this is set to YourCompany: Repairs, indicating this is a repair type operation.

Once all desired configurations have been made on the RO form, click Confirm Repair. This moves the RO to the Confirmed stage, and reserves the necessary components needed for the repair.

A new Forecasted column appears on the product lines under the Parts tab, displaying the availability of all components needed for the repair.

Once ready, click Start Repair. This moves the RO to the Under Repair stage (in the upper-right corner). If the RO should be cancelled, click Cancel Repair.

Once all products have been successfully repaired, the RO is completed. To register this in the database, click End Repair.

Nota

If all parts added to the RO were not used, clicking End Repair causes an Uncomplete Move(s) pop-up window to appear.

The pop-up window informs the user that there is a difference between the initial demand and the actual quantity used for the order.

If the Used quantity should be changed, click Discard or close the pop-up window. If the order should be confirmed, click Validate.

This moves the RO to the Repaired stage. A Product Moves smart button also appears above the form.

Click the Product Moves smart button to view the product’s moves history during and after the repair process.

### Return product to customer¶

#### Product is under warranty¶

Once the product has been successfully repaired, it can be returned to the customer.

#### Product is not under warranty¶

If the product is not under warranty, or should the customer bear the repair costs, click Create Quotation. This opens a new SO form, pre-populated with the parts used in the RO, with the total cost of the repair calculated.

If this SO should be sent to the customer, click Confirm, and proceed to invoice the customer for the repair.

Suggerimento

If the customer should be charged for a repair service, a service type product can be created and added to the SO for a repaired product.

To return the product to the customer, navigate to the Sales app, and select the original SO from which the initial return was processed. Then, click the Delivery smart button.

From the resulting list of operations, click the reverse transfer, indicated by the Source Document, which should read `Return of WH/OUT/XXXXX`.

This opens the return form. At the top of this form, a Repair Orders smart button now appears, linking this return to the completed RO.

Click Return at the top of the form. This opens a Reverse Transfer pop-up window.

This pop-up lists the Product included in the order, the Quantity delivered to the customer, and the Unit of Measure the product was in.

Click the value in the Quantity field to change the quantity of the product to be returned, if necessary.

Click the 🗑️ (trash) icon at the far-right of the product line to remove it from the return, if necessary.

Once ready, click Return to confirm the return. This creates a new delivery for the returned products.

When the delivery has been processed and the product has been returned to the customer, click Validate to validate the delivery.

Vedi anche

[Returns and refunds](../../sales/sales/products_prices/returns.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/repairs/repair_orders.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../hr.html "Human resources") |
  * [precedente](../repairs.html "Riparazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Riparazioni](../repairs.html) »
  * Process repair orders


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
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Order
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
  *[BOM]: Bill of Materials
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
  *[RFQs]: Requests for Quotation
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