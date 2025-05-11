# Third-party shipping carriers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](labels.html "Print shipping labels") |
  * [precedente](new_delivery_method.html "Add a new delivery method") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Third-party shipping carriers



# Third-party shipping carriers¶

Users can link third-party shipping carriers to Odoo databases, in order to verify carriers” delivery to specific addresses, [automatically calculate shipping costs](../setup_configuration.html), and [generate shipping labels](labels.html).

In Odoo, shipping carriers can be applied to a sales order (SO), invoice, or delivery order. For tips on resolving common issues when configuring shipping connectors, skip to the Troubleshooting section.

Vedi anche

  * [DHL integration](dhl_credentials.html)

  * [Sendcloud integration](sendcloud_shipping.html)

  * [UPS integration](ups_credentials.html)




The following is a list of available shipping connectors in Odoo:

Corriere | Region availability  
---|---  
[DHL Express](dhl_credentials.html) | Tutti  
[Envia.com](envia_shipping.html) | Tutti  
[FedEx](fedex.html) | Tutti  
[UPS](ups_credentials.html) | Tutti  
US Postal Service | Stati Uniti d’America  
[Sendcloud](sendcloud_shipping.html) | Some European countries (see details below)  
[Bpost](bpost.html) | Belgio  
Easypost | America del Nord  
Shiprocket | India  
[Starshipit](starshipit_shipping.html) | Australia and New Zealand  
  
Importante

Other services from DHL are **not** supported.

Sendcloud currently supports shipping **from** Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, and the United Kingdom, and **to** any European country.

## Configurazione¶

To ensure proper setup of a third-party shipping carrier with Odoo, follow these steps:

  1. Install the shipping connector.

  2. Set up delivery method.

  3. Activate production environment.

  4. Configure warehouse.

  5. Specify weight of products.




### Install shipping connector¶

To install shipping connectors, go to Inventory app ‣ Configuration ‣ Settings.

Under the Shipping Connectors section, tick the third-party shipping carrier’s checkbox to install it. Multiple third-party shipping connectors can be selected at once. Then, click Save.

Nota

[Delivery methods](../setup_configuration.html) can also be integrated with operations in the _Sales_ , _eCommerce_ , and _Website_ apps. To install, refer to the [install apps and modules](../../../../general/apps_modules.html#general-install) documentation.

### Metodo di consegna¶

To configure the API credentials, and activate the shipping carrier, begin by going to Inventory app ‣ Configuration ‣ Shipping Methods, and select the desired delivery method.

Nota

The list often includes **two** delivery methods from the same Provider: one for international shipping and one for domestic shipping.

Additional delivery methods can be created for specific purposes, such as [packaging](../../product_management/configure/packaging.html).

Vedi anche

[Configure delivery methods](../setup_configuration.html)

Nota

Ensure the delivery method is published when it should be available on the _Website_ app. To publish a delivery method on the website, click the desired delivery method, then click the Unpublished smart button. Doing so changes that smart button to read: Published.

The Shipping Method page contains details about the provider, including:

  * Shipping Method (_Required field_): the name of the delivery method (e.g. `FedEx US`, `FedEx EU`, etc.).

  * Website: configure shipping methods for an _eCommerce_ page that is connected to a specific website in the database. Select the applicable website from the drop-down menu, or leave it blank to apply the method to all web pages.

  * Provider (_Required field_): choose the third-party delivery service, like FedEx. Upon choosing a provider, the Integration Level, Invoicing Policy and Insurance Percentage fields become available.

  * Integration Level: choose Get Rate to simply get an estimated shipment cost on an SO or invoice.

Importante

Select Get Rate and Create Shipment to also [generate shipping labels](labels.html).

  * Company: if the shipping method should apply to a specific company, select it from the drop-down menu. Leave the field blank to apply the method to all companies.

  * Delivery Product (_Required field_): the delivery charge name that is added to the SO or invoice.

  * Invoicing Policy: select and calculate an Estimated cost of shipping directly from the shipping carrier. If the Real cost of shipping is wanted instead, refer to [Invoice real shipping costs](invoicing.html) document.

  * Margin on Rate: specify an additional percentage amount added to the base shipping rate to cover extra costs, such as handling fees, packaging materials, exchange rates, etc.

  * Free if order amount is above: enables free shipping for orders surpassing a specified amount entered in the corresponding Amount field.

  * Insurance Percentage: specify a percentage amount of the shipping costs reimbursed to the senders if the package is lost or stolen in transit.




**Shipping Method** configuration page for `FedEx US`.¶

In the Configuration tab, fill out the API credential fields (e.g. API key, password, account number, etc.). Depending on the third-party shipping carrier chosen in the Provider field, the Configuration tab will contain different required fields. For more details about configuring specific carriers” credentials, refer to the following documents:

Vedi anche

  * [DHL credentials](dhl_credentials.html)

  * [Sendcloud credentials](sendcloud_shipping.html)

  * [UPS credentials](ups_credentials.html)




### Production environment¶

With the delivery method details configured, click the Test Environment smart button to set it to Production Environment.

Avvertimento

Setting the delivery method to Production creates **real** shipping labels, and users are at risk of being charged through their carrier account (e.g. UPS, FedEx, etc.) **before** users charge customers for shipping. Verify all configurations are correct before launching the delivery method to Production.

### Warehouse configuration¶

Ensure the warehouse’s Address (including ZIP code) and Phone number are entered accurately. To do that, go to Inventory app ‣ Configuration ‣ Warehouses, and select the desired warehouse.

On the warehouse configuration page, open the warehouse contact page by clicking the Company field.

Verify that the Address and Phone number are correct, as they are required for the shipping connector to work properly.

### Product weight¶

For the carrier integration to work properly, specify the weight of products by going to Inventory app ‣ Products ‣ Products, and selecting the desired product.

Then, switch to the Inventory tab, and define the Weight of the product in the Logistics section.

## Apply third-party shipping carrier¶

Shipping carriers can be applied on a SO, invoice, or delivery order.

After configuring the third-party carrier’s delivery method in Odoo, create or navigate to a quotation by going to Sales app ‣ Orders ‣ Quotations.

### Sales order¶

To assign a third-party shipping carrier, and get an estimated cost of shipping, begin by going to Sales app ‣ Orders ‣ Quotations. Create or select an existing quotation, and add the cost of shipping through a third-party carrier to a quotation, by clicking the Add Shipping button in the bottom-right corner of the Order Lines tab.

In the resulting Add a shipping method pop-up window, select the intended carrier from the Shipping Method drop-down menu. The Cost field is automatically filled based on:

  * the amount specified in the Total Order Weight field (if it is not provided, the sum of product weights in the order is used)

  * the distance between the warehouse’s source address and the customer’s address.




After selecting a third-party provider in the Shipping Method field, click Get Rate in the Add a shipping method pop-up window to get the estimated cost through the shipping connector. Then, click the Add button to add the delivery charge to the SO or invoice.

Vedi anche

[Charge customers for shipping after product delivery](invoicing.html)

### Delivery order¶

For users making shipments without installing the _Sales_ app, assign the shipping carrier to the delivery order, by first going to the Inventory app. Then, from the Inventory Overview dashboard, select the Delivery Orders operation type, and choose the desired delivery order that is not already marked as Done or Cancelled.

In the Additional info tab, set the Carrier field to the desired third-party shipping carrier. When the delivery method is set to production mode, a Tracking Reference is provided.

Vedi anche

[Generate shipping labels](labels.html)

## Risoluzione problemi¶

Since shipping connectors can sometimes be complex to set up, here are some checks to try when things are not working as expected:

  1. Ensure the warehouse information (e.g., address and phone number) in Odoo is correct **and** matches the records saved in the shipping provider’s website.

  2. Verify that the [package type](../../product_management/configure/package.html#inventory-warehouses-storage-package-type) and parameters are valid for the shipping carrier. To check, ensure the shipment can be directly created on the shipping carrier’s website.

  3. When encountering a price mismatch between Odoo’s estimated cost and the provider’s charge, first ensure the delivery method is set to production environment.

Then, create the shipment in both the carrier’s website and Odoo, and verify the prices are the same across Odoo, the shipping provider, and in the _debug logs_.

Example

When checking for a price mismatch in the debug logs, if the request says the package weighs six kilograms, but the response from FedEx says the package weights seven kilograms, it concludes that the issue is on FedEx’s side.




### Debug log¶

Track shipping data inconsistencies by activating debug logging. To do that, go to the delivery method’s configuration page (Inventory app ‣ Configuration ‣ Shipping Method), and select the desired shipping method. Click the No Debugging smart button to activate Debug Requests.

With Debug Requests activated, each time the shipping connector is used to estimate the cost of shipping, records are saved in the Logging report. To access the report, turn on [developer mode](../../../../general/developer_mode.html#developer-mode), and go to Settings app ‣ Technical ‣ Database Structure section ‣ Logging.

Nota

Logs are created for a shipping method each time the Get Rate button is clicked on SOs and invoices, **and** when a customer adds the shipping carrier to their order through the _Website_ app.

Click the _HTTP request_ line item to open a detailed page, and verify the correct information is sent from Odoo to the shipping carrier. In the _HTTP response_ , verify that the same information is received.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](labels.html "Print shipping labels") |
  * [precedente](new_delivery_method.html "Add a new delivery method") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Third-party shipping carriers


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
  *[RfQ]: request for quotation
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
  *[AVCO]: Average Cost
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