# UPS integration — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](zebra.html "Zebra label configuration") |
  * [precedente](starshipit_shipping.html "Starshipit shipping") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * UPS integration



# UPS integration¶

UPS is a shipping carrier service that integrates with Odoo to coordinate shipping to all regions. Once integrated, users can create shipping methods that estimate shipping costs and [generate labels](labels.html).

Vedi anche

[Third-party shipping carriers](third_party_shipper.html)

To set up the UPS shipping connector in Odoo, complete these steps:

  1. Create a UPS account to get account number

  2. Create UPS developer account to get client credentials

  3. Set up shipping method in Odoo




## UPS account setup¶

To get started, go to the [UPS website](https://www.ups.com/) and click the Log In button in the top-right corner to log in or create a UPS account.

After logging in, click the profile icon in the top-right corner, and select Accounts and Payment from the drop-down menu.

On the Accounts and Payment Options page, two accounts must be configured: an Odoo shipment account and a payment card.

### Shipping account¶

To add an Odoo shipment account, select Add New Account from the Add a Payment Method drop-down menu, and click Add.

On the next screen, labeled Open a Shipping Account, complete the forms to configure the shipping account type (e.g. Business) and if any regulated items will be shipped. Then finish the remaining three steps in the wizard to Add Addresses, Verify Identity, and Explore Discounts, with the last option being optional.

When complete, submit the application on the last page of the wizard to finish setting up the shipping account.

### Get account number¶

With the shipping account set up, the UPS Account Number becomes available. To access it, navigate to Profile ‣ Accounts and Payment and refer to the shipping account’s Number field.

### Payment card¶

Navigate back to the Accounts and Payments page and select the Add Payment Card option from the Add a Payment Method drop-down menu. Then, complete the form to add the credit card information.

## UPS developer account setup¶

Next, log into the [UPS developer account](http://developer.ups.com/) to generate the developer key. To begin, click the profile icon in the top-right corner, and choose the Apps option from the drop-down menu.

### Add app¶

Then, click the Add Apps button to begin filling out the form. In the I need API credentials because * field, select I want to integrate UPS technology into my business.

Under the next label, Choose an account to associate with these credentials. *, select Add existing account from the drop-down menu in the corresponding field, and then select the account number linked to the UPS account created in the previous step.

Click Next, and proceed to the Add App form, and fill out the fields:

  * App Name: Type the name to identify the app by.

  * Callback URL: Type the URL of the Odoo database, in the format: `https://databaseName.odoo.com`. Do **not** include `www` in the URL.




In the Add Products section on the right, search for and click the \+ (plus) icon to add the following products to the app:

  * Authorization (O Auth): Used to generate the authorization token to request information from the UPS API.

  * Address Validation: Validates addresses at the street level in the United States and Puerto Rico.

  * Locator: Enables search for UPS shipping locations based on type and available services.

  * Paperless Documents: Enables the upload of document images to link to shipments.

  * Shipping: Enables UPS shipping services, such as preparing packages for shipment, managing returns, and canceling scheduled shipments.

  * Rating: Compare delivery services and shipping rates.




Finally, click Save and accept UPS’s terms and conditions.

Vedi anche

[UPS API Catalog](https://developer.ups.com/catalog?loc=en_US)

### Client ID and Client Secret¶

With the new app created, in the Profile ‣ My Apps ‣ App page, select the app from the Credentials section to view the UPS credentials.

In the Credentials section, copy the Client ID and Client Secret key.

## Installazione in Odoo¶

With the credentials obtained, configure the UPS shipping method in Odoo by going to Inventory app ‣ Configuration ‣ Shipping Methods.

On the Shipping Methods page, click the New button.

Nota

For existing UPS shipping methods whose Provider is UPS Legacy, archive it and create a new shipping method using UPS.

In the Provider field, select UPS. Doing so reveals the UPS Configuration tab, where various fields must be entered. For details instructions on configuring the other fields on the shipping method, refer to the [Configure third-party carrier](third_party_shipper.html) documentation.

In the UPS Configuration tab, complete the following fields:

  * UPS Account Number: (_required_) Get the account number from the UPS portal.

  * UPS Client ID: (_required_) Get the Client ID from the UPS developer website.

  * UPS Client Secret: (_required_) Get the Client Secret key from the UPS developer website.

  * UPS Service Type: Select from the drop-down menu the type of shipping service.

  * UPS Package Type: (_required_) Select from the drop-down menu the [package type](../../product_management/configure/package.html) that is supported for the shipping service.

  * Package Weight Unit: The unit of measure for the package weight.

  * Package Size Unit: The unit of measure for the package dimensions.

  * Label Format: Choose the label format shipping labels: PDF, ZPL, EPL, or SPL.




In the Options section, the following features are available:

  * Bill My Account: Charge the user’s UPS account for shipping in the _eCommerce_ app.

  * Collect on Delivery: Collect payment from customers for shipping after the shipment is delivered.

  * Generate Return Label: Print the return label for the order after the delivery order is validated.

  * Duties paid by: Select whether duties or other fees are charged to the Sender or Recipient of the order.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/ups_credentials.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](zebra.html "Zebra label configuration") |
  * [precedente](starshipit_shipping.html "Starshipit shipping") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * UPS integration


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