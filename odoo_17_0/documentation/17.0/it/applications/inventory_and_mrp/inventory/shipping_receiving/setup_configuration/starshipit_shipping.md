# Starshipit shipping — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ups_credentials.html "UPS integration") |
  * [precedente](sendcloud_shipping.html "Sendcloud integration") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Starshipit shipping



# Starshipit shipping¶

Starshipit is a shipping service operator that facilitates the integration of Australasian shipping couriers with Odoo. Once integrated, users can create shipping methods that will automatically get rates from specific couriers (such as Australia Post, NZ Post, DHL,…) based on predefined conditions.

Vedi anche

  * [Automatically calculate shipping](../setup_configuration.html)

  * [Integrate other third-party couriers](third_party_shipper.html)




## Setup in Starshipit¶

### Create an account and activate couriers¶

To get started, go to [Starshipit’s platform](https://starshipit.com/) to configure the account and generate the connector credentials. Log in with the Starshipit account, or create a new one if needed.

### Pickup address configuration¶

Once logged into the Starshipit account, navigate to Settings ‣ Pickup address, and fill in the Pickup address. Ensure this field matches the warehouse address.

### Couriers configuration¶

To integrate with third-party couriers, navigate to Settings ‣ Couriers, and select Couriers.

Suggerimento

For details on integrating with different couriers, refer to [Starshipit’s support center](https://support.starshipit.com/hc/en-us/).

### Checkout rates¶

To configure shipping rate calculations, navigate to Settings ‣ Checkout rates. The selected delivery costs are automatically applied in Odoo when calculating shipping costs.

### Starshipit API key¶

Configure shipping rules to assign the correct shipping methods to orders based on specific conditions.

To create a rule, go to Settings ‣ Rules and click Add a new rule.

While there are multiple ways to configure rules, it is recommended to set:

  1. Condition to Contains

  2. Value to the product code

  3. Action to Set Courier & Product Code




### Finding Starshipit API credentials¶

In the Starshipit account, navigate to Settings ‣ API in the side menu. This page contains the API keys needed to connect to Odoo.

## Installazione in Odoo¶

### Installa¶

After the Starshipit account is set up, integrate it with the Odoo database. To do that, go to Odoo’s Apps module, search for the Starshipit Shipping module, and click Activate to install it.

### Configurazione¶

Once installed, activate the feature by going to Inventory ‣ Configuration ‣ Settings. Under the Shipping Connectors section, activate the Starshipit Connector option.

After activating Starshipit Connector, click the Starshipit Shipping Methods link below the listed connector. Once on the Shipping Methods page, click Create.

Suggerimento

Shipping Methods can also be accessed by going to Inventory ‣ Configuration ‣ Delivery ‣ Shipping Methods.

Configure Starshipit in Odoo by filling out the fields on the Shipping Methods form as follows:

  * Shipping Method: type `Starshipit`.

  * Provider: select Starshipit from the drop-down menu.

  * Delivery Product: assign or create the delivery product that will appear on the sales order line when the cost of shipping is computed.

Nota

The fields discussed in this section are specific to configuring Starshipit. For more information about the other fields, refer to [Delivery methods](../setup_configuration.html).




In the Starshipit Configuration tab, fill out these fields:

  * Starshipit API Key: enter the API key obtained from Starshipit.

  * Starshipit Subscription Key: enter the subscription key obtained from the same place as the API key.

  * Origin Address: Enter the address where products are shipped from. This field is crucial for calculating shipping rates and generating shipping labels.

  * Default Package Type: Set a default package type to include the weight of the empty package when automatically calculating shipping rates.




Importante

To set a default package type, the _Packages_ feature **must** be enabled in Inventory ‣ Configuration ‣ Settings.

  * Manually Save the form by clicking the cloud icon next to the Shipping Methods / New breadcrumbs.




To load the newly configured shipping products, click the Select a service linked to the Starshipit account link at the bottom of the Starshipit Configuration tab.

Doing so opens the Choose Starshipit Shipping Service pop-up window. In the Delivery Service field, choose the desired shipping service for deliveries and returns from the drop-down menu. Finally, click Confirm.

The chosen delivery service will populate in the Service Name field.

Example

Sample of a Starshipit shipping product configured in Odoo:

Sendle: Sendle drop off

Shipping Product: `Sendle Delivery`

Starshipit Service Code: `STANDARD-DROPOFF`

Suggerimento

Starshipit does not provide test keys when a company tests the sending of a package in Odoo. This means that if a package is created, the account may be charged.

Odoo has a built-in layer of protection against unwanted charges when using test environments. Within a test environment, if a shipping method is used to create labels, then those labels are immediately canceled after creation — this occurs automatically. Please note that depending on the shipping provider being used, the account might be charged for printing label, unless the order is cancelled manually on the couriers’s portal.

Switch between the test and production environment by clicking the Environment smart button at the top of the shipping method form.

### Generate a label with Starshipit¶

When creating a quotation in Odoo, add the Starshipit shipping method by clicking the Add shipping button.

In the Add a shipping method pop-up window, select Starshipit in the Shipping Method field.

Calculate the shipping rate by clicking Get rate. Finally, click Add to include the cost of shipping to the sales order line, labeled as the _delivery product_.

Nota

Automatically calculate shipping costs for Starshipit in **both** Odoo _Sales_ and _eCommerce_ applications.

Then, Validate the delivery. Shipping label documents are automatically generated in the chatter, which includes the following:

  1. Shipping label(s) depending on the number of packages.

  2. Tracking number(s) if the selected courier supports it.

  3. Return label(s) if the Starshipit connector is configured for returns.




Importante

Package weight in Odoo is calculated by adding the weights of the products plus the empty package saved in the database. Ensure the correct shipping option is selected, as the package weight is not automatically verified.

Verify the destination address, as Starshipit checks it when the order is created.

Finally, some couriers may require other information, such as an email address or phone number. Please ensure that all necessary information are set upon sending a shipping order.

### Resi¶

Starshipit allows returns with the following couriers:
    

  * Australia Post eParcel

  * TNT

  * Couriers Please

  * Aramex

  * StarTrack

  * DHL Express

  * NZ Post Domestic




This can be done by clicking the Return smart button on the intended delivery order. If the selected courier supports returns, the Print Return Label button will be available.

### Cancellations¶

If a delivery order is cancelled in Odoo, it will be automatically archived in Starshipit. However, the cancellation will not be sent to the courier itself, so make sure to log onto the courier’s platform to handle the cancellation manually.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/starshipit_shipping.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ups_credentials.html "UPS integration") |
  * [precedente](sendcloud_shipping.html "Sendcloud integration") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Starshipit shipping


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