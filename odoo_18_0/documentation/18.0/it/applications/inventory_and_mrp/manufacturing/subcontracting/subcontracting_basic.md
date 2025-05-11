# Basic subcontracting — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](basic_subcontracting_lead_times.html "Basic subcontracting lead times") |
  * [precedente](../subcontracting.html "Subappalto") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Basic subcontracting



# Basic subcontracting¶

In manufacturing, subcontracting is the process of a company engaging a third-party manufacturer, or subcontractor, to manufacture products that are then sold by the contracting company.

In basic subcontracting, the subcontractor is responsible for acquiring the necessary components. This means that the contracting company only has to worry about what happens to subcontracted products once they are produced.

The workflow for purchasing a product manufactured using basic subcontracting is similar to the one used when purchasing a non-subcontracted product from a vendor. The main differences are the way that subcontracted products are configured, and the fact that subcontracted products take longer to be sent from the vendor, since they must first be manufactured by them.

## Configurazione¶

To use subcontracting in Odoo, navigate to Manufacturing app ‣ Configuration ‣ Settings, and tick the checkbox next to the Subcontracting setting, under the Operations heading. Then, click Save.

Once the Subcontracting setting is enabled, it is also necessary to properly configure the subcontracted product, and the product’s BoM.

### Configure product¶

To configure a product for basic subcontracting, navigate to Inventory app ‣ Products ‣ Products, and select a product, or create a new one by clicking New.

On the product form, select the Purchase tab, and add the product’s subcontractor as a vendor by clicking Add a line, selecting the subcontractor in the Vendor drop-down menu, and entering a price in the Price field.

Then, click on the Inventory tab, and use the Routes field to configure a route that determines what happens to the finished product once it has been manufactured by the subcontractor.

If the finished product is shipped back to the contracting company, make sure the Buy route is selected. In addition, select the Replenish on Order (MTO) route to automatically create a PO for the product upon confirmation of a sales order (SO), unless there is enough stock on-hand to fulfill the SO.

If the finished product is shipped directly to the customer by the subcontractor, make sure that **only** the Dropship route is selected.

### Configure BoM¶

To configure a BoM for basic subcontracting, click the Bill of Materials smart button on the product form, and select the desired BoM.

Alternatively, navigate to Manufacturing app ‣ Products ‣ Bills of Materials, and select the BoM for the subcontracted product.

Vedi anche

For a full overview of BoM configuration, see the [Bill of materials](../basic_setup/bill_configuration.html) documentation.

In the BoM Type field, select the Subcontracting option. Then, add one or more subcontractors in the Subcontractors field that appears below.

Finally, click on the Miscellaneous tab. In the Manuf. Lead Time field, enter the number of days it takes the subcontractor to manufacture the product. This number is factored in when calculating the product’s expected arrival date.

Nota

When using basic subcontracting, there is no need to list components in the Components tab of the BoM, since the components required for manufacturing, and the means by which they are acquired, are handled by the subcontractor.

## Basic subcontracting workflow¶

The basic subcontracting workflow consists of up to four steps:

  1. Create a sales order (SO) for the subcontracted product; doing so creates a PO to purchase the product from the subcontractor.

  2. Confirm the PO created in the previous step, or create a new PO; doing so creates a receipt order or a dropship order.

  3. Process the receipt once the subcontractor has finished manufacturing the subcontracted product, and shipped it back to the contracting company, **OR** process the dropship order to ship the product directly to the customer.

  4. If the workflow was started by creating an SO, and the finished product is not dropshipped to the end customer, process the delivery order once the product is shipped to the customer.




The specific number of steps depends on the reason that the subcontracted product is being purchased from the subcontractor.

If the reason is to fulfill a specific customer order, the process starts with creating an SO, and ends with delivering the product to the customer, or having the subcontractor dropship it to them.

If the reason is to increase the quantity of stock on-hand, the process starts with creating a PO, and ends with receiving the product into inventory.

### Create SO¶

It is only necessary to complete this step if the product is being purchased from the subcontractor to fulfill a customer need. If the product is being purchased to increase the quantity of stock on-hand, move on to the next step.

To create a new SO, navigate to Sales app ‣ Orders ‣ Orders, and click New.

Select the customer in the Customer drop-down menu. Then, click Add a product on the Order Lines tab, select a subcontracted product in the Product drop-down menu, and enter a quantity in the Quantity field.

Click Confirm to confirm the SO, at which point a Purchase smart button appears at the top of the page. This opens the PO created to purchase the subcontracted product from the subcontractor.

Nota

An SO for the product only creates a PO if the _Replenish on Order (MTO)_ route is enabled on the product’s form, **and** there is not enough stock of the product on-hand to fulfill the SO.

If there is enough stock on-hand, confirming an SO for the product creates a delivery order instead, because Odoo assumes that the SO is fulfilled using the stock in the warehouse.

This is not the case for subcontracted products that are dropshipped to the end customer. In that case, a PO is **always** created, even if there is enough stock on-hand.

### Process PO¶

If a PO was created in the previous step, navigate to it by clicking the Purchase smart button at the top of the SO, or by going to Purchase app –> Orders –> Purchase Orders, and selecting the PO. Then, click Confirm Order to confirm it, and move on to the next step.

If a PO was not created in the previous step, do so now by navigating to Purchase app ‣ Orders ‣ Purchase Orders, and clicking New.

Begin filling out the PO by selecting a subcontractor from the Vendor drop-down menu. In the Products tab, click Add a product to create a new product line. Select a subcontracted product in the Product field, and enter the quantity in the Quantity field. Finally, click Confirm Order to confirm the PO.

When a PO is confirmed for a product manufactured using basic subcontracting, a receipt or dropship order is automatically created, and can be accessed from the corresponding Receipt or Dropship smart button that appears at the top of the PO.

PO for a basic subcontracting product, with a Receipt smart button at the top of the page.¶

### Process receipt or dropship order¶

Once the subcontractor has finished manufacturing the product, they either ship it to the contracting company, or dropship it to the end customer, depending on how the product was configured.

#### Process receipt¶

If the subcontractor ships the finished product to the contracting company, once it has been received, navigate to Purchase app ‣ Orders ‣ Purchase Orders, and select the PO.

Click the Receive Products button at the top of the PO, or the Receipt smart button at the top of the page, to open the receipt. Then, click Validate at the top of the receipt to enter the product into inventory.

#### Process dropship order¶

If the subcontractor dropships the product, once they have sent it, navigate to Purchase app ‣ Orders ‣ Purchase Orders, and select the PO.

Select the Dropship smart button at the top of the page to open the dropship order, and click Validate at the top of the order to confirm that the product has been sent to the customer.

### Process delivery order¶

If the subcontracting workflow was started by a customer SO, and the finished product was **not** dropshipped to the customer, but rather delivered to the contracting company, it is necessary to ship the product to the customer, and process the delivery order.

Once the product has been shipped to the customer, navigate to the Sales app, and select the SO. Select the Delivery smart button at the top of the page to open the delivery order, and click Validate on the order to confirm that the product has been shipped.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/subcontracting/subcontracting_basic.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](basic_subcontracting_lead_times.html "Basic subcontracting lead times") |
  * [precedente](../subcontracting.html "Subappalto") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Subappalto](../subcontracting.html) »
  * Basic subcontracting


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
  *[SOs]: sales orders
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
  *[BoMs]: bills of materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
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