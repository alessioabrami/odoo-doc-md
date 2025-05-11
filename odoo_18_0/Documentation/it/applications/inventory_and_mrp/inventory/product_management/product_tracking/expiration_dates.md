# Expiration dates — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../inventory_valuation.html "Valutazione dell’inventario") |
  * [precedente](reassign.html "Reassign lot/serial numbers") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Expiration dates



# Expiration dates¶

In Odoo, _expiration dates_ can be used to manage and track the lifecycles of perishable products, from purchase to sale. Using expiration dates reduces product loss due to unexpected expiry, and helps to avoid sending expired products to customers.

In Odoo, only products that are tracked using _lots_ and _serial numbers_ can be assigned expiration information. Once a lot or serial number has been assigned, an expiration date can be set. This is especially helpful for companies (such as food manufacturers) that consistently, or exclusively, buy and sell perishable products.

Vedi anche

  * [Numeri lotto](lots.html)

  * [Numeri di serie](serial_numbers.html)




## Enable expiration dates¶

To enable the use of _expiration dates_ , go to Inventory app ‣ Configuration ‣ Settings, and scroll down to the Traceability section. Then, click the checkbox to enable the Lots & Serial Numbers feature.

Once that feature is activated, a new option will appear to enable Expiration Dates. Click that checkbox to enable the feature, and be sure to Save changes.

Suggerimento

Once the Lots & Serial Numbers feature is activated, an additional feature appears to Display Lots & Serial Numbers on Delivery Slips. Activating these features helps with end-to-end traceability, making it easier to manage product recalls, identify batches of faulty products, and more.

## Configure expiration dates on products¶

Once the Lots & Serial Numbers and Expiration Dates features have been enabled in the **Inventory** app settings, expiration information can be configured on individual products.

To do so, go to Inventory app ‣ Products ‣ Products, and select a product to edit. Selecting a product reveals the product form for that particular item.

Importante

To be tracked using lots or serial numbers, or to configure expiration information, products _must_ have their Product Type set as Goods under the General Information tab. Then, in the Track Inventory field, select either By Unique Serial Number or By Lots.

Then, click the Inventory tab, and scroll down to the Traceability section. Tick the Expiration Date checkbox.

Nota

If a product has stock on-hand prior to activating tracking by lots or serial numbers, an inventory adjustment might need to be performed in order to assign lot numbers to the existing stock.

Suggerimento

For processing large quantities of products on receipts or deliveries, it is recommended to track using lots, so multiple products can be traced back to the same lot, if any issues arise.

Under the Dates section, there are four categories of expiration information to configure for the product:

  * Expiration Time: the number of days after receiving products (either from a vendor or in stock after production) in which goods may become dangerous and should not be used or consumed.

  * Best Before Time: the number of days before the expiration date in which the goods start deteriorating, **without** being dangerous yet.

  * Removal Time: the number of days before the expiration date in which the goods should be removed from stock.

  * Alert Time: the number of days before the expiration date in which an alert should be raised on goods in a particular lot or containing a particular serial number.




Nota

The values entered into these fields automatically compute the expiration date for goods entered into stock, whether purchased from a vendor or manufactured in-house.

Suggerimento

If the Dates field is not populated with any values for expiration information, dates (and lots) can be manually assigned upon receipts and deliveries in and out of the warehouse. Even when assigned, they can still be overwritten and changed manually if needed, as well.

## Set expiration dates on receipts with lots & serial numbers¶

Generating expiration dates for _incoming_ goods can be done directly on the Receipt. Navigate to Inventory app ‣ Operations ‣ Receipts, then click on a line to open the Receipt record.

Importante

Clicking Validate before assigning a serial number to the ordered product quantities causes a User Error popup to appear. The popup requires entry of a lot or serial number for the ordered products. The receipt cannot be validated without an assigned lot or serial number.

From here, click the __(Details) icon located on the of the product line. When clicked, a Detailed Operations pop-up will appear.

In the pop-up, the Expiration Date automatically populates, based on the configuration on the product form. Click the Lot/Serial Number field on the appropriate line, then enter the lot or serial number.

Suggerimento

If the Dates field on the product form has not been configured, the Expiration Date can be manually entered.

Click Save when finished to close the pop-up. Finally, click Validate.

A Traceability smart button will appear upon validating the receipt. Click the Traceability smart button to see the updated Traceability Report, which includes: a Reference document; the Product being traced; the Lot/Serial #; and more.

## Set expiration dates on manufactured products¶

Expiration dates can also be generated for products manufactured in-house. To assign expiration dates to manufactured products, a manufacturing order (MO) needs to be completed.

To create a MO, go to Manufacturing app ‣ Operations ‣ Manufacturing Orders, and click New. Choose a product to manufacture from the Product field drop-down menu, then select the Quantity to produce.

Nota

To manufacture a product, there must be materials to consume in the lines in the Product column. This can be achieved either by creating a Bill of Material for the Product, or manually adding materials to consume by clicking Add a line.

Once ready, click Confirm.

The appropriate number of Lots/Serial Numbers automatically populated in the field. Click the __(Details) icon to reveal additional information for those specific numbers. On that pop-up, all expiration information that was previously configured for the product is displayed.

## Sell products with expiration dates¶

Selling perishable products with expiration dates is done the same as any other type of product. The first step in selling perishable products is to create a sales order.

To do that, go to Sales app ‣ New to create a new quotation, and fill out the information on the sales order form.

Add a Customer, then click Add a product to add the desired products to the Product lines, and set a Quantity for the products.

Then, click the Other Info tab. Under the Delivery section, change the Delivery Date to a date after the expected date, and click Apply to confirm the date. Finally, click Confirm to confirm the sales order.

Importante

If the products are delivered before the Alert Date set on the product form, then no alerts are created.

Next, click the Delivery smart button at the top of the sales order to see the warehouse receipt form.

On the warehouse receipt form, click Validate, and then Apply in the accompanying pop-up window, to automatically process all Done quantities, and deliver the products to the customer.

Importante

To sell perishable products with expiration dates, the Removal Strategy for the Location the products are stored in must be set to FEFO. If there is not enough stock of perishable products in one lot, Odoo will automatically take the remaining quantity required from a second lot with the next-soonest expiration date. Removal strategies can also be set on Product Categories.

Vedi anche

[Removal strategies](../../shipping_receiving/removal_strategies.html)

## View expiration dates for lots & serial numbers¶

To view (and/or group) all products with expiration dates by lot number, go to Inventory app ‣ Products ‣ Lots/Serial Numbers.

Once there, remove any default search filters from the search bar. Then, click Group By, choose Add Custom Group, and select the Expiration Date parameter from the drop-down menu. Doing so breaks down all perishable products, their expiration dates, and the assigned lot number.

Suggerimento

Customers can also view the expiration date alert in their customer portal.

### Expiration alerts¶

To see expiration alerts, go to Inventory app ‣ Products ‣ Lots/Serial Numbers.

Then, click into a Lot/Serial Number with perishable products. Doing so reveals the serial number detail form.

Suggerimento

To view expiration date information in the list view, click the __(adjust settings) icon at the top of the list of records, then tick the Expiration Date checkbox.

On the Lot/Serial Number detail form, the Dates lists all expiration information related to the products.

If the expiration date for a lot/serial number has passed, the form displays a red Expiration Alert at the top of the page to indicate that the products in this lot are either expired or expiring soon.

From here, click back to the Lots/Serial Numbers page (via the breadcrumbs).

To see the new expiration alert, or any expiration alerts for products that are expired (or will expire soon), click back to the Lots/Serial Numbers page via the breadcrumbs. Remove all of the search filters from the search bar on the Lots/Serial Numbers dashboard.

Then, click Filters, and choose Expiration Alerts.

### Expiration notifications¶

Users can be notified when the expiration date for a product has passed. This can help keep specific employees up to date on the status of items under their purview.

To configure a notification, navigate to Inventory app ‣ Products ‣ Products. Select a product configured with lot/serial numbers and expiration date tracking. Navigate to the Inventory tab. Under the Logistics section, select a user in the Responsible field.

When the expiation date passes for a lot/serial number for this product, a notification is sent to the user in this field.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/product_management/product_tracking/expiration_dates.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../inventory_valuation.html "Valutazione dell’inventario") |
  * [precedente](reassign.html "Reassign lot/serial numbers") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Product management](../../product_management.html) »
  * [Product tracking](../product_tracking.html) »
  * Expiration dates


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
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
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
  *[SVL]: stock move layer
  *[JIT]: just-in-time