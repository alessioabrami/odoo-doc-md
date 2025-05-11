# Online food delivery — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reporting.html "Rendiconto") |
  * [precedente](pos_based_marketing.html "Marketing features") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Online food delivery



# Online food delivery¶

**UrbanPiper** is an order management system that integrates with multiple food delivery platforms. It consolidates orders from all connected platforms into a single interface, simplifying the delivery process.

Fornitori supportati:

  * [Careem](https://www.careem.com/)

  * [Cari](https://getcari.com/)

  * [ChowNow](https://www.chownow.com/)

  * [Deliveroo](https://deliveroo.co.uk/)

  * [DoorDash](https://www.doordash.com/)

  * [EatEasy](https://www.eateasy.ae/dubai)

  * [Glovo](https://glovoapp.com/)

  * [Grubhub](https://www.grubhub.com/)

  * [HungryPanda](https://www.hungrypanda.co/)

  * [HungerStation](https://hungerstation.com/)

  * [Jahez](https://www.jahez.net/)

  * [Just Eat](https://www.just-eat.ie/)

  * [Mrsool](https://mrsool.co/)

  * [Ninja](https://ananinja.com/)

  * [NoonFood](https://www.noon.com/)

  * [Postmates](https://www.postmates.com/)

  * [Rafeeq](https://www.gorafeeq.com/en)

  * [SkipTheDishes](https://www.skipthedishes.com/)

  * [Swiggy](https://www.swiggy.com/)

  * [Talabat](https://www.talabat.com/)

  * [UberEats](https://www.ubereats.com/)

  * [Zomato](https://www.zomato.com/)




## Configurazione¶

### UrbanPiper credentials¶

  1. Get your Atlas credentials:

     1. Go to the [POS settings](configuration.html#configuration-settings).

     2. Scroll down to the Food Delivery Connector section.

     3. Click Fill this form to get Username & Api key and fill out the survey.

  2. [Go to your Atlas account](https://atlas.urbanpiper.com/) and retrieve your API key and username by navigating to Settings ‣ API Access.




### Punto vendita¶

  1. Enable the Urban Piper setting:

     1. Go to the [POS settings](configuration.html#configuration-settings).

     2. Scroll down to the Food Delivery Connector section.

     3. Check the Urban Piper setting.

  2. Set up UrbanPiper:

     1. Fill in the Username and Api Key fields with your UrbanPiper credentials.

     2. Select the desired delivery providers in the Food Delivery Platforms field under the Urban Piper Location section (i.e., Zomato, Uber Eats).

  3. Save the settings.

  4. Click the \+ Create Store button. Doing so creates a new location on the UrbanPiper Atlas platform.




Nota

  * The Pricelist and Fiscal Position fields are automatically selected after saving.

  * A successful store creation triggers a notification.

  * The store creation process may take 2–3 minutes to reflect changes on the UrbanPiper Atlas platform.

  * The store is automatically named after your point of sale name.




### Prodotti¶

To make products available individually,

  1. Go to Point of Sale ‣ Products ‣ Products.

  2. Select any product to open its product form.

  3. Go to the Point of Sale tab.

  4. Complete the Urban Piper section:

     * Fill in the Available on Food Delivery with the desired POS.

     * Optionally, set up the Meal Type field and enable the Is Recommended and Is Alcoholic buttons.




To make multiple products available for food delivery at once,

  1. Go to Point of Sale ‣ Products ‣ Products.

  2. Click the list icon (__) to switch to the list view.

  3. Select the products.

  4. Enter the desired POS in the Available on Food Delivery column.




Nota

  * Currently, UrbanPiper does not support combo products.

  * As a workaround, create a product and define combo choices as [Attributes & Variants](../sales/products_prices/products/variants.html).




### Sincronizzazione¶

To make products available on food delivery platforms, synchronize with your UrbanPiper account:

  1. Go to the [POS settings](configuration.html#configuration-settings).

  2. Scroll down the Food Delivery Connector section.

  3. Click the Sync Menu button.

     * The Last Sync on timestamp below the Create Store and Sync Menu buttons updates.




Nota

  * A successful synchronization triggers a notification.

  * The synchronization process may take 2–3 minutes to reflect changes on the UrbanPiper Atlas platform.




### Go live¶

  1. [Go to the Locations tab](https://atlas.urbanpiper.com/locations) of your Atlas account.

  2. Select the location to activate, then click Request to go Live.

  3. In the popup window:

     1. Select the platform(s) to activate and click Next.

     2. Enter the Platform ID and Platform URL in the corresponding fields to establish the connection between the platform and UrbanPiper.

     3. Click the Request to Go Live button.

Nota

To find the location’s Platform ID and Platform URL,

     1. Click the location to open its setup form.

     2. The location’s parameters are available in the HUB tab.

  4. Verify that your location is live:

     1. [Go to the Locations tab](https://atlas.urbanpiper.com/locations) of your Atlas account.

     2. Select any provider in the Assoc. platform(s) column to review the status of that platform for this location.




## Order flow¶

An order placed via the configured delivery platform triggers a notification. To manage these orders, open the orders” list view by:

  1. Clicking Review Orders on the notification popup.

  2. Clicking the bag-shaped icon for online orders and New.

Nota

     * Clicking this icon displays the number of orders at each stage: New, Ongoing, and Done.

     * The New button indicates newly placed orders, Ongoing is for accepted orders, and Done is for orders ready to be delivered.




Then,

  1. Select the desired order.

  2. Click the Accept button.

  3. When an order is accepted, its Order Status switches from Placed to Acknowledged and is automatically displayed on the preparation display.




When the order is ready,

  1. Open the orders” list view.

  2. Select the order.

  3. Click the Mark as ready button. Its Order Status switches from Acknowledged to Food Ready, and its Status switches from Ongoing to Paid.




### Order rejection¶

Sometimes, the shop or restaurant may want to **reject** an order. In this case, open the orders” list view,

  1. Select the desired order.

  2. Click the Reject button.

  3. Select one of the reasons from the popup window.




Importante

**Swiggy** orders cannot be directly rejected. Attempting to reject one prompts Swiggy customer support to contact the restaurant. Similarly, **Deliveroo** , **JustEat** , and **HungerStation** do not allow order rejection. Always follow the respective provider’s guidelines for handling such cases.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/point_of_sale/online_food_delivery.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reporting.html "Rendiconto") |
  * [precedente](pos_based_marketing.html "Marketing features") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Punto vendita](../point_of_sale.html) »
  * Online food delivery


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[MRR]: Monthly Recurring Revenue
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
  *[NSSL]: Non-Shopee Supported Logistics