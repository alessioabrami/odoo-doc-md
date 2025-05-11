# FedEx integration — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sendcloud_shipping.html "Sendcloud integration") |
  * [precedente](envia_shipping.html "Envia.com integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * FedEx integration



# FedEx integration¶

Integrating a FedEx account with Odoo’s **Inventory** app makes it possible to [calculate shipping rates](../setup_configuration.html), and [generate shipping labels](labels.html) within Odoo. This is accomplished by enabling the FedEx _shipping connector_ , then configuring at least one _shipping method_.

Nota

This documentation contains configuration details specific to FedEx integration. See the documentation on [third-party shippers](third_party_shipper.html) for general shipper integration instructions.

## Enable shipping connector¶

To enable the shipping connector for FedEx, navigate to Inventory app ‣ Configuration ‣ Settings. Scroll down to the Shipping Connectors section, and tick the checkbox next to FedEx Connector.

Finally, click Save to save the changes. After doing so, a __ FedEx Shipping Methods button appears below FedEx Connector.

## Configure shipping method¶

Once the FedEx shipping connector is enabled, it is necessary to configure at least one shipping method. After doing so, the shipping method can be included in sales orders (SOs), and used to compute shipping costs, and print shipping labels.

To enable a shipping method, navigate to Inventory app ‣ Configuration ‣ Settings, and click the FedEx Shipping Methods button below the FedEx Connector checkbox. Doing so opens a page that shows all existing FedEx shipping methods.

Nota

To see all shipping methods for every shipper with a connector enabled, navigate to Inventory app ‣ Configuration ‣ Shipping Methods.

Select a shipping method to open its form. Alternatively, click New to open a blank form, and configure a new shipping method.

Importante

Enabling the FedEx shipping connector automatically creates two default shipping methods: FedEx US and FedEx International. Each of these methods are pre-configured with test credentials, allowing them to be used for testing purposes.

Before the shipping method can be used to create actual shipments, the test credentials must be replaced with credentials from a valid FedEx account.

### General information¶

At the very top of a shipping method form are fields used to configure the way the method operates in Odoo. In the Provider field, select FedEx from the drop-down menu, if it is not already selected.

The rest of the fields in this section are general to all shipping providers. For details on how to fill them out, see the documentation on [third-party shippers](third_party_shipper.html).

### Fedex Configuration tab¶

The options in the Fedex Configuration tab of a FedEx shipping method form are used to connect the method to a FedEx account, and configure the shipping details associated with the method (drop-off type, package type, etc.).

A FedEx business account is required to obtain the information needed to fill out the fields in this tab. To create a new account, navigate to FedEx’s [Open Account](https://www.fedex.com/en-us/open-account.html) page, click on Create Account, and follow the instructions.

#### Developer Key and Meter Number fields¶

A _developer key_ is used to integrate a FedEx account with an external service, like the Odoo **Inventory** app. A _meter number_ is a unique ID number used by FedEx to identify negotiated shipping rates for each account.

To get a developer key and meter number, begin by navigating to FedEx’s [Developer Resource Center](https://www.fedex.com/en-us/developer/web-services.html). Then, click on the FedEx Web Services drop-down menu.

Click Get Test Key to start the process of getting a developer key and meter number which can be used to configure a shipping method for testing purposes.

Click Get Production Key to start the process of getting a developer key and meter number, which can be used to configure a shipping method that generates real shipments with FedEx.

After clicking either option, follow the instructions until the Confirmation screen is reached. This screen displays the developer key and meter number.

Once the developer key and meter number are determined, enter them in the Developer Key and Meter Number fields on the Fedex Configuration tab of the shipping method form.

#### Password and Account Number fields¶

A _password_ is used, along with a username, to log into a FedEx account. An _account number_ is the unique number assigned to each FedEx account.

To find a FedEx account number, log in to a FedEx account at [https://www.fedex.com](https://www.fedex.com/). Click on the account holder’s name in the top-right corner of the screen, and select My Profile from the drop-down menu.

On the profile page, click Account Management on the left side of the screen. The account number is displayed on this screen.

Once the password and account number are determined, enter them in the Password and Account Number fields on the Fedex Configuration tab of the shipping method form.

#### Shipping details¶

The main section of the Fedex Configuration tab includes a number of additional fields used provide information about the shipping method:

  * Fedex Service Type: The FedEx service used to ship a package.

  * Fedex Drop-Off Type: The method for getting a package into FedEx’s possession.

  * Fedex Package Type: The type of package used for the shipping method.

  * Package Weight Unit: The unit of measure used to weigh packages.

  * Package Length Unit: The unit of measure used to determine the dimensions of packages.

  * Label Type: The type of shipping label used for packages.

  * Label Format: The file format used by Odoo to generate shipping labels.

  * Commercial Invoice Type: The dimensions and type of the paper used to print invoices.




Importante

The options that should be selected on the Fedex Configuration tab of a shipping method depend on the negotiated shipping services of the associated FedEx account. To confirm the available services for a FedEx account, visit the _Account Management_ page after logging in to the FedEx website, or speak with a customer service representative.

#### Options section¶

The Options section of the Fedex Configuration tab provides a few additional options to further configure the shipping method:

  * Saturday Delivery: Tick the checkbox to allow packages shipped with the delivery method to be delivered on Saturdays.

  * Generate Return Label: Tick the checkbox to automatically generate a return label upon validation of a delivery order.

  * Duties paid by: Use the drop-down menu to select whether duty charges should be paid by the Sender or Recipient.




## Activate shipping method¶

By default, shipping methods in Odoo are created within a _test environment_. This means they can only be used for testing purposes, and are unable to generate actual shipping orders.

To activate a shipping method in a _production environment_ , click the __ Test Environment smart button at the top of the shipping method form. After doing so, the smart buttons changes to read __ Production Environment.

With the production environment enabled, validating a delivery order using the shipping method generates an actual shipping label with FedEx.

Click the __ Production Environment smart button to return the shipping method to a test environment.

Avvertimento

**Do not** enable the production environment for a shipping method before it is ready to be used for actual shipping orders. Doing so may lead to the creation of unwanted charges with FedEx.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/fedex.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sendcloud_shipping.html "Sendcloud integration") |
  * [precedente](envia_shipping.html "Envia.com integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * FedEx integration


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
  *[VAT]: Value-Added Tax Identification
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