# Sendcloud integration — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](starshipit_shipping.html "Starshipit shipping") |
  * [precedente](fedex.html "FedEx integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Sendcloud integration



# Sendcloud integration¶

Sendcloud is a shipping service aggregator that facilitates the integration of European shipping carriers with Odoo. Once integrated, users can select shipping carriers on inventory operations in their Odoo database.

Vedi anche

[Sendcloud integration documentation](https://support.sendcloud.com/hc/en-us/articles/360059470491-Odoo-integration)

## Setup in Sendcloud¶

### Create an account and activate carriers¶

To get started, go to [Sendcloud’s platform](https://www.sendcloud.com/) to configure the account and generate the connector credentials. Log in with the Sendcloud account, or create a new one if needed.

Nota

For new account creation, Sendcloud will ask for a VAT number or EORI number. After completing the account setup, activate (or deactivate) the shipping carriers that will be used in the Odoo database.

Importante

Odoo integration of Sendcloud works on free Sendcloud plans _only_ if a bank account is linked, since Sendcloud won’t ship for free. To use shipping rules, or individual custom carrier contacts, a paid plan of Sendcloud is **required**.

### Warehouse configuration¶

Once logged into the Sendcloud account, navigate to Settings ‣ Shipping ‣ Addresses, and fill in the field for Warehouse address.

To allow Sendcloud to process returns as well, a Return Address is required. Under the Miscellaneous section, there is a field called Address Name (optional). The Odoo warehouse name should be entered here, and the characters should be exactly the same.

Example

**SendClould configuration**

Miscellaneous

Address Name (optional): `Warehouse #1`

Brand: `Default`

**Odoo warehouse configuration**

Warehouse: `Warehouse #1`

Short Name: `WH`

Company: `My company (San Francisco)`

Address: `My Company (San Francisco)`

Notice how the inputs for the Warehouse field, for both the Odoo configuration and the Sendcloud configuration, are the exact same.

### Generate Sendcloud credentials¶

In the Sendcloud account, navigate to Settings ‣ Integrations in the menu on the right. Next, search for Odoo Native. Then, click on Connect.

After clicking on Connect, the page redirects to the Sendcloud API settings page, where the Public and Secret Keys are produced. The next step is to name the Integration. The naming convention is as follows: `Odoo CompanyName`, with the user’s company name replacing `CompanyName` (e.g. `Odoo StealthyWood`).

Then, check the box next to Service Points and select the shipping services for this integration. After saving, the Public and Secret Keys are generated.

## Installazione in Odoo¶

To ensure seamless Sendcloud integration with Odoo, install and link the Sendcloud shipping connector to the Sendcloud account. Then, configure Odoo fields, so Sendcloud can accurately pull shipping data to generate labels.

### Install Sendcloud shipping module¶

After the Sendcloud account is set up and configured, it’s time to configure the Odoo database. To get started, go to Odoo’s Apps module, search for the `Sendcloud Shipping` integration, and install it.

### Sendcloud shipping connector configuration¶

Once installed, activate the Sendcloud Shipping module in Inventory ‣ Configuration ‣ Settings. The Sendcloud Connector setting is found under the Shipping Connectors section.

After activating the Sendcloud Connector, click on the Sendcloud Shipping Methods link below the listed connector. Once on the Shipping Methods page, click Create.

Suggerimento

Shipping Methods can also be accessed by going to Inventory ‣ Configuration ‣ Delivery ‣ Shipping Methods.

Fill out the following fields in the New Shipping Method form:

  * Shipping Method: type `Sendcloud DPD`.

  * Provider: select Sendcloud from the drop-down menu.

  * Delivery Product: set the product that was configured for this shipping method or create a new product.

  * In the SendCloud Configuration tab, enter the Sendcloud Public Key.

  * In the SendCloud Configuration tab, enter the Sendcloud Secret Key.

  * Manually Save the form by clicking the cloud icon next to the Shipping Methods / New breadcrumbs.




After configuring and saving the form, follow these steps to load the shipping products:

  * In the SendCloud Configuration tab of the New Shipping Method form, click on the Load your SendCloud shipping products link.

  * Select the shipping products the company would like to use for deliveries and returns.

  * Click Select.




Example

Sample Sendcloud shipping products configured in Odoo:

DELIVERY

Shipping Product: `DPD Home 0-31.5kg`

Carrier: `DPD`

Minimum Weight: `0.00`

Maximum Weight: `31.50`

Paesi: `Austria` `Belgio` `Bosnia-Herzegovina` `Bulgaria` `Croazia` `Repubblica ceca` `Danimarca` `Estonia` `Finlandia` `Francia` `Germania` `Grecia` `Ungheria` `Islanda` `Irlanda` `Italia` `Lettonia` `Liechtenstein` `Lituania` `Lussemburgo` `Monaco` `Paesi Bassi` `Norvegia` `Polonia` `Portogallo` `Romania` `Serbia` `Slovacchia` `Slovenia` `Spagna` `Svezia` `Svizzera`

RETURN

Return Shipping Product: `DPD Return 0-20kg`

Return Carrier: `DPD`

Return Minimum Weight: `0.00`

Return Maximum Weight: `20.00`

Return Countries: `Belgium` `Netherlands`

Suggerimento

Sendcloud does not provide test keys when a company tests the sending of a package in Odoo. This means if a package is created, the configured Sendcloud account will be charged, unless the associated package is cancelled within 24 hours of creation.

Odoo has a built-in layer of protection against unwanted charges when using test environments. Within a test environment, if a shipping method is used to create labels, then those labels are immediately cancelled after the creation — this occurs automatically. The test and production environment settings can be toggled back and forth from their respective smart buttons.

### Shipping information¶

To use Sendcloud to generate shipping labels, the following information **must** be filled out accurately and completely in Odoo:

  1. **Customer information** : when creating a quotation, ensure the selected Customer has a valid phone number, email address, and shipping address.

To verify, select the Customer field to open their contact page. Here, add their shipping address in the Contact field, along with their Mobile number and Email address.

  2. **Product weight** : ensure all products in an order have a specified Weight in the Inventory tab of their product form. Refer to the [Product weight section](third_party_shipper.html#inventory-shipping-receiving-configure-weight) of this article for detailed instructions.

  3. **Warehouse address** : ensure the warehouse name and address in Odoo match the previously defined warehouse in the Sendcloud setup. For details on warehouse configuration in Odoo, refer to the [warehouse configuration section](third_party_shipper.html#inventory-shipping-receiving-configure-source-address) of the third-party shipping documentation.




## Generate labels with Sendcloud¶

When creating a quotation in Odoo, add shipping and a Sendcloud shipping product. Then, Validate the delivery. Shipping label documents are automatically generated in the chatter, which include the following:

  1. Shipping label(s) depending on the number of packages.

  2. Return label(s) if the Sendcloud connector is configured for returns.

  3. Customs document(s) should the destination country require them.




Additionally, the tracking number is now available.

Importante

When return labels are created, Sendcloud automatically charges the configured Sendcloud account.

### Shipping rules¶

Optionally, create shipping rules to automatically generate shipping labels tailored to different product needs. For example, a shipping rule can be created for customers shipping expensive jewelry items to purchase insurance.

Nota

Shipping rules do **not** affect [shipping rate calculations](third_party_shipper.html#inventory-shipping-receiving-third-party-rate), and are only used to improve the process of [generating shipping labels](labels.html).

To use shipping rules, navigate to Inventory app ‣ Configuration ‣ Delivery: Shipping Methods, and select the intended `Sendcloud` shipping method.

Under the Sendcloud Configuration tab, in the OPTIONS section, choose the kind of shipments the shipping rules apply to, via the Use Sendcloud shipping rules field.

From here, choose either: Shipping to customers, Returns from customers, or Both.

Then, in the Sendcloud website, navigate to Settings ‣ Shipping rules. Create a new shipping rule by clicking Create New.

In the Actions section, set a Condition to determine when the rule applies. Then, configure what to do when packages meet the condition.

Vedi anche

[Create shipping rules on Sendcloud](https://support.sendcloud.com/hc/en-us/articles/10274470454292-How-to-create-shipping-rules#examples-smart-shipping-rules)

## FAQ¶

### Shipment is too heavy¶

If the shipment is too heavy for the Sendcloud service that is configured, then the weight is split to simulate multiple packages. Products will need to be put in different Packages to Validate the transfer and generate labels.

Rules can also be set up in Sendcloud to use other shipping methods when the weight is too heavy. However, note that these rules will not apply to the shipping price calculation on the calculation on the sales order.

### Personal carrier contract¶

Use custom prices from a direct carrier contract, via CSV upload, by first logging into Sendcloud, navigating to Settings ‣ Carriers ‣ My contracts, and then selecting the intended contract.

Under the Contract prices section, click Download CSV and fill out the contract prices in the price column of the CSV file template.

Avvertimento

Ensure the CSV file includes the correct prices to avoid any inaccuracies.

Upload the completed CSV file to Sendcloud, then click Save these prices.

Vedi anche

[Sendcloud: How to upload contract prices with carriers](https://support.sendcloud.com/hc/en-us/articles/5163547066004)

### Measuring volumetric weight¶

Many carriers have several measures for weight. There is the actual weight of the products in the parcel, and there is the _volumetric weight_ (Volumetric weight is the volume that a package occupies when in transit. In other words it is the physical size of a package).

Suggerimento

Check to see if selected carrier(s) already have defined formulas to compute the volumetric weight.

Vedi anche

[Sendcloud: How to calculate & automate parcel volumetric weight](https://support.sendcloud.com/hc/en-us/articles/360059644051-How-to-calculate-automate-parcel-volumetric-weight)

### Unable to calculate shipping rate¶

First, verify that the product being shipped has a weight that is supported by the selected shipping method. If this is set, then verify that the destination country (from the customer address) is supported by the carrier. The country of origin (warehouse address) should also be supported by the carrier.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](starshipit_shipping.html "Starshipit shipping") |
  * [precedente](fedex.html "FedEx integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Sendcloud integration


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