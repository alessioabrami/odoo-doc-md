# Gelato — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../point_of_sale.html "Punto vendita") |
  * [precedente](shopee_connector/manage.html "Shopee order management") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Gelato



# Gelato¶

Gelato is a global print-on-demand platform that integrates with Odoo to sync product catalogs and automate order fulfillment.

Connecting Gelato’s services with Odoo’s **Sales** and **eCommerce** apps enables the following:

  * Sync Odoo sales orders with Gelato for automated order fulfillment

  * Create and manage Gelato products within Odoo; supports product variant and image sync

  * Configure delivery options in Odoo and receive order updates via webhooks.




## Configurazione¶

Importante

The company information (_Company name_ and _Billing address_) in the Gelato account _must_ match the company information in the Odoo database in order for sales orders to be confirmed and sent to Gelato for fulfillment.

### Configure API keys and webhooks in Gelato¶

Before configuring the Gelato connector in Odoo, first obtain API credentials and webhooks from the Gelato account.

API connectors enable Odoo **Sales** to send and receive data from Gelato for order processing, while webhooks provide real-time updates on order status and shipment tracking.

#### Chiave API¶

An API Key is a unique authentication token that allows Odoo to securely communicate with Gelato’s API, enabling order transmission, status updates, and data synchronization.

After logging into Gelato, click __ Developer in the left menu bar. From here, click on API keys. In the new page, click the Add API Key button to open a new API key form. Type in a name, then click Create Key.

Copy the generated API key using Copy to Clipboard.

Importante

Copy the API key and store it somewhere safe and secure before leaving this page. Once the page is refreshed or exited, the key will not be available to copy.

If the key cannot be copied or is lost, return to the API key page and start over, creating a new API key.

#### Webhook¶

A webhook is an automated notification system that instantly updates Odoo when Gelato processes, ships, or delivers an order, ensuring real-time tracking and minimal manual intervention.

To create a webhook, go to Developer ‣ Webhooks under the Developer drop-down menu in the left menu bar. In the new page, click Add Webhook to open a Create Webhook form.

The webhook form requires several specific configurations:

  * URL: This tells Gelato where to send the order updates in Odoo. Copy and paste the Odoo database URL with the additional suffix `/gelato/webhook`.

Example

`https://stealthywood.odoo.com/gelato/webhook`

  * Events: Click into the field and select order_status_updated. Selecting order_status_updated ensures Odoo receives order changes automatically.

  * Method: Click into the field and select the HTTP Post option, as this is the request method used to send data from Gelato to Odoo.

  * Tick the checkbox next to I want to take Authorization to this webhook.

  * Header Name: In this field, type in `signature` to match the field in Odoo.

  * Click Generate Key to generate a Header Value.

  * Click Create to complete this webhook configuration.




Suggerimento

Copy and paste the API key and webhook on a notepad before tabbing out of the Gelato webpage as backup.

### Configure Gelato connector in Odoo¶

In Odoo, navigate to Sales app ‣ Configuration ‣ Settings, then scroll to the Connectors section. Enable the Gelato connector by ticking the checkbox. Next, paste the newly generated API keys and webhook secret key into their respective fields. Once saved, Gelato is available in Odoo **Sales** and **eCommerce** products.

## Synchronizing Gelato products with Odoo Sales¶

It is recommended to have products already configured in Gelato before configuring them in Odoo. To get the product ID in Gelato, navigate to the Templates page from the side bar menu. Select which product to synchronize in Odoo, then hover over the product card to reveal the __(vertical ellipsis) menu icon. Click the menu icon, then click Copy Template ID to copy the product template ID to the clipboard.

Vedi anche

[Start selling products with Gelato: Quick & easy setup](https://www.gelato.com/blog/get-started-with-gelato-creating-products)

### Odoo Sales product¶

To create a product in Odoo that matches the Gelato product, navigate to Sales app ‣ Products ‣ Products, select New to create a new product form. Type in the product Name, then navigate to the Sales tab. Find the Gelato section, then click into the Template Reference field and paste the copied template ID from the Gelato product. Finally, click Synchronize.

Successful synchronization pulls the Gelato product variant options into the newly configured Odoo product.

In the new Print Images field, click the default marker to set a default product image. Click the __(edit) icon and select the product image file to upload, then Save & Close.

Importante

The Print Images field _must_ be configured on all Gelato products and their respective product variations before they can be ordered.

### Varianti prodotto¶

To view and edit the newly synchronized product variants, navigate to the Attributes & Variants tab, which will have the variants pulled from the Gelato product configuration. Click the Configure button to edit and configure the variant images, delivery methods, additional pricing, etc.

### Order a Gelato product from Odoo¶

Once synchronized, Gelato products are available to order in Odoo through [sales quotations](sales_quotations.html) or on the **eCommerce** store. Gelato delivery options are automatically synchronized upon API and webhook configuration.

To add Gelato delivery, click Add shipping on the sales order. Select Standard Delivery or Express Delivery in the Shipping Method field, then click Get rate.

Once the quotation is confirmed, it becomes an active sales order, and the order is sent to Gelato for fulfillment. Once a sales order is sent from Odoo to Gelato, Gelato processes the order, produces the product at the nearest fulfillment center, and ships it directly to the end-customer.

Vedi anche

[Creare preventivi](sales_quotations/create_quotations.html)

Importante

When creating a sales order for Gelato products in the database, only Gelato products can be added to the same sales order. Multivendor orders are not available with the Gelato connector at this time.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/gelato.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../point_of_sale.html "Punto vendita") |
  * [precedente](shopee_connector/manage.html "Shopee order management") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Gelato


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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