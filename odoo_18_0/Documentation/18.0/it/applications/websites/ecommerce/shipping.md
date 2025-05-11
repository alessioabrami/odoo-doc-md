# Consegna — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](order_handling.html "Order handling") |
  * [precedente](payments.html "Fornitori di pagamento") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Consegna



# Consegna¶

Odoo eCommerce allows you to configure various delivery methods, enabling customers to choose their preferred option at [checkout](checkout.html). These methods include external providers, custom options such as flat-rate or free shipping, local carriers via [Sendcloud](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping.html) or [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-rules), and in-store pickup.

## External provider integration¶

To handle product delivery, you can connect your database to [third-party shipping carriers](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html) like [FedEx](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/fedex.html), [UPS](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/ups_credentials.html), or [DHL](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dhl_credentials.html). A shipping connector links to these providers, automating [tracking labels](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/labels.html) and shipping processes.

To enable a third-party delivery provider, go to Website ‣ Configuration ‣ Settings, scroll to the Delivery section, select the desired delivery provider(s), and Save.

Go to Website ‣ Configuration ‣ Delivery Methods and select the delivery method in the list to [configure it](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method).

Vedi anche

[Third-party shipping carriers](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html)

Importante

The field used to define additional fees **must** be filled **in your third-party delivery provider account** , even if you do not plan to charge customers any additional fee. If you do not want to apply a fee, enter `0`. If the field is left empty, the delivery price cannot be calculated, and an error message prompts the customer to select an alternative delivery method.

### Margin on delivery rate¶

To add an additional fee to the base shipping rate (e.g., to cover extra costs), log into your carrier account and set the desired fee in the related field. The shipping connector retrieves this fee and includes it in the final price at checkout. Contact your carrier for further assistance with this configuration.

Alternatively, enter `0` in your third-party shipping provider account, then set the fee in Odoo. To do so, access the desired [shipping method’s form](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) and enter the fee in the Margin on Rate field to add a percentage to the shipping costs and/or the Additional margin field to add a fixed amount.

Importante

The field used to define additional fees cannot be left empty in your third-party shipping provider account.

## Custom delivery method¶

Custom delivery methods must be created, for example:

  * to integrate delivery carriers through [Sendcloud](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping.html);

  * to configure specific rules (e.g., to offer free shipping for orders above a specific amount) for a specific provider;

  * to configure [Fixed Price](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-fixed) shipping, or shipping [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-rules).




To create a custom delivery method, go to Website ‣ Configuration ‣ Delivery Methods, click New, and fill in the [fields](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-shipping-methods-details).

In the Provider field, select [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-rules) or [Fixed Price](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-fixed).

Suggerimento

Upon [configuring](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) a delivery method, you can:

  * Restrict it [to a specific website](../website/configuration/multi_website.html) by selecting it in the Website field.

  * Click the Test Environment smart button to switch to the Production Environment. Then, click Unpublished to Publish the delivery method and make it available to website visitors.

  * Use the Availability tab to define [conditions](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/new_delivery_method.html#inventory-shipping-receiving-availability) for the delivery method based on the order’s content or destination.




## Fai clic e ritira¶

To allow customers to reserve products online and pay for/collect them in-store, follow these steps:

  1. Go to Website ‣ Configuration ‣ Settings.

  2. Scroll to the Delivery section, enable Click & Collect, and Save.

  3. Click __ Configure Pickup Locations to [configure](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) the delivery method and ensure the Provider field is set to Pick up in store.

  4. In the Stores tab, click Add a line and select the warehouse(s) where customers can collect their orders.

  5. Once your setup is complete, click the Unpublish button to change the status to Publish and make the delivery method available to customers.




Nota

  * When the product is in stock, a location selector is displayed on the [product](products.html) and [checkout](checkout.html) pages. Customers cannot select a pickup location if the product is out of stock at that location. The [Continue selling](products.html#ecommerce-products-stock-management) option for out-of-stock products is not supported.

  * If the [Show Available Qty](products.html#ecommerce-products-stock-management) option is enabled for a product, customers can view the stock quantity available for each warehouse in the location selector on the product page.

  * Each warehouse must have a **complete address** to ensure its location is accurately displayed to customers. Incomplete addresses prevent the warehouse from being shown.

  * The Click & Collect option is not available for services.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/ecommerce/shipping.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](order_handling.html "Order handling") |
  * [precedente](payments.html "Fornitori di pagamento") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Consegna


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[FAQs]: Frequently Asked Questions