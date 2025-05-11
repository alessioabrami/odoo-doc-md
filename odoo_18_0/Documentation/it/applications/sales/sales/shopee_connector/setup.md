# Shopee Connector configuration — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Shopee order management") |
  * [precedente](../shopee_connector.html "Connettore Shopee") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Connettore Shopee](../shopee_connector.html) »
  * Shopee Connector configuration



# Shopee Connector configuration¶

Odoo allows users to synchronize with Shopee Seller account in the database, but users **must** have a registered **Shopee Seller account** and a **Shopee Open account** prior to completing the configuration.

Set up an Open Shopee account by first going to the [Shopee Open Platform](https://open.shopee.com/), and click the Get Access (Now) button located in the middle of the page.

Use the [Open Shopee Developer Guide](https://open.shopee.com/developer-guide/12), and follow the registration process. Once all done, proceed to follow the instructions below to register and link the Open Shopee account in Odoo.

Importante

Shopee Open Platform access and seller account requirements are **regionally specific**. This means the rules, qualifications, and processes differ from country to country. Before proceeding with Odoo’s Shopee Connector setup, verify the requirements for _your_ specific Shopee region.

**Key Considerations:**

  * **Shopee Seller Status & Business Type:** You must have an active Shopee seller account (Individual or Registered Business). Your eligibility depends on your region and business registration.

  * **Order Volume/Seller Tier (If Applicable):** Many regions require a minimum number of orders within a specific time frame or a certain seller tier (e.g., Mall, Preferred, Managed) to access the Open Platform.




**Action Required:**

  1. Identify your Shopee region.

  2. Locate the official Shopee documentation for your region. [Open Shopee Developer Guide](https://open.shopee.com/developer-guide/12)

  3. Carefully review the requirements for seller accounts and Open Platform access in your region.

  4. Ensure your Shopee account meets all the necessary criteria _before_ proceeding with the Odoo Shopee Connector configuration.




## Connect Shopee seller account to Odoo¶

[Install](../../../general/apps_modules.html#general-install) the Shopee Connector (`sale_shoppe`) by going to Apps.

Then connect your Shopee Open account by navigating to Sales app ‣ Configuration ‣ Shopee ‣ Accounts.

From here, click New to create to link a new Shopee account.

Then, in the Credentials tab, select the appropriate API Endpoint from the drop-down menu.

Nota

Shopee offers several API endpoints for production and testing. Selecting the correct endpoint is crucial for successful integration. Choose the endpoint that corresponds to your marketplace location.

  * Shopee Production Endpoint (Singapore): This is the primary endpoint for sellers in most APAC countries. Select this option unless you are specifically operating within mainland China or Brazil.

  * Shopee Production Endpoint (China): This endpoint is exclusively for sellers operating within mainland China. It is designed to comply with local regulations and business practices.

  * Shopee Production Endpoint (Brazil): This endpoint is dedicated to sellers operating within Brazil. Select this option if your Shopee store is based in Brazil.

  * Shopee Testing Endpoint: This endpoint is for development and testing purposes only. Use it to simulate interactions with the Shopee API without affecting your live data. **Do not use this endpoint for production.**

  * Shopee Testing Endpoint (China): Similar to the general testing endpoint, this one is specifically for testing integrations related to the China-specific production endpoint. **Do not use this endpoint for production.**




After selecting the correct API Endpoint in the Credentials form, input your Open Shopee Partner ID and Partner Key in the corresponding fields. Then click Save And Authorize.

Importante

You’ll need your Open Shopee Partner ID and Partner Key to complete this step. Here’s how to find them in the Shopee Open Platform:

  1. **Log in to the Shopee Open Platform:** [Log in](https://open.shopee.com/) with the credentials you used to register your Open Shopee account.

  2. **Navigate to App Management:** Go to the App Management section, then select App List.

  3. **Select your app:** Choose the specific app you want to synchronize with Odoo (either your test app or your production app).

  4. **Find your credentials:** Within the app details, you’ll find your Partner ID and Partner Key. These are the values you’ll need to copy and paste into the corresponding fields in Odoo.




Nota

  * **Copy carefully:** Copy the Partner ID and Partner Key accurately, without any extra spaces or characters. These are case-sensitive.

  * **Keep your key secure:** Your Partner Key is sensitive information. Do not share it with anyone. Treat it like a password.




## Authorization and account registration¶

After entering connecting the Shoppe Seller account to Odoo, the authorization process begins.

### Shopee seller account selection/login¶

Upon clicking Save and Authorize, Odoo redirects to the Shopee seller account selection page.

  * **Already logged in:** If you are already logged in to a Shopee account, your email address or username will be displayed. Click on your account to proceed.

  * **Not logged in:** If you are not logged in, you will be prompted to enter the credentials (email/username and password) of the Shopee seller account you wish to connect to Odoo.




### Granting access to Odoo¶

After selecting or logging into your Shopee seller account, you will be directed to the authorization (or consent) page. Here, confirm that you allow Shopee to grant Odoo access to your account and related data. This step is essential for the integration to function correctly.

## Account registration and Shopee shop creation¶

Upon confirming access, Shopee redirects you back to Odoo. An indicator appears, confirming that your Shopee account has been successfully registered.

### Post-synchronization configuration¶

After the redirection, you should perform the following steps within Odoo:

  1. **Rename the Shopee Account (Optional):** The newly created Shopee account in Odoo will likely have a default name. You can rename it to something more descriptive (e.g., the name of your Shopee shop) for easier management.

  2. **Set the Last Order Synchronization Date:** This setting determines the starting point for fetching orders from Shopee. Choose a date from which you want Odoo to retrieve past orders.

  3. **Configure Inventory Synchronization:** Decide whether you want to synchronize your product inventory between Odoo and Shopee. Enable the Synchronize Inventory option to automatically push stock updates from Odoo to Shopee. Disabling this option prevents automatic inventory updates.

  4. **Assign a Default Sales Team:** Assign a default sales team to your Shopee account in Odoo. This helps with reporting and order management.




With the Shopee account successfully registered, the marketplaces available with this specific account can later be synchronized the exact same way, and listed under the Shops button.

## Shopee orders in Odoo¶

When a Shopee order is synchronized, only lines for items are created on the sales order in Odoo. Each one represents one for the product that was sold on Shopee.

Any necessary price reconciliation related to shipping or income versus fees can be managed later using Shopee’s weekly / monthly financial reports, which can then be imported into the Odoo **Accounting** app.

The selection of a database product for a sales order item is done by matching its Internal Reference (a customizable product reference identifier in Odoo, like `FURN001`) with the Shopee _SKU_.

If no database product with a matching internal reference is found for a given Shopee SKU, then a default database product, _Shopee Item_.

Nota

To modify default products, activate the [developer mode](../../../general/developer_mode.html#developer-mode), and navigate to Sales app ‣ Configuration ‣ Settings. In the Connectors section, under Shopee Sync, find the Default Products.

## Product tax configuration¶

To allow for tax reporting of Shopee sales with Odoo, the taxes applied to the sales order items are those set on the product, or determined by the [fiscal position](../../../finance/fiscal_localizations.html).

Make sure to have the correct taxes set on your products in Odoo, or have it done by a fiscal position, to avoid discrepancies in the subtotals between _Shopee Seller Central_ and Odoo.

Nota

As shopee does not necessarily apply the same taxes as those configured in Odoo, it may happen that order totals differ by a few cents between Odoo and _Shopee Seller Central_. Those differences can be resolved with a write-off when reconciling the payments in Odoo.

## Add a new marketplace¶

To add a new marketplace, follow these steps:

  1. **Navigate to Shopee Accounts:** Go to Sales ‣ Configuration ‣ Accounts.

  2. **Create a New Shopee Account:** Click New to create a new Shopee marketplace account.

  3. **Select the API Endpoint:** Choose the appropriate API endpoint for your local market. (Typically, this will be Shopee Production Endpoint (Singapore) unless you are operating in mainland China or Brazil. Refer to the documentation for details on endpoint selection).

  4. **Enter Credentials:** Your Partner ID and Partner Key are the same as those linked to your unique Open Shopee account. Enter these values in the corresponding fields.

  5. **Name Your Shop:** Give the new shop a descriptive name (e.g., `Shopee Philippines`) to identify it later.

  6. **Assign a Sales Team:** Assign a relevant sales team (e.g., `Shopee Sales Philippines`) to enable advanced reporting capabilities.

  7. **Synchronize Your Account:** If none of your existing marketplaces are listed, click Log in with another account to synchronize a new one. This will initiate the Shopee authorization process.




### Sincronizzazione automatica¶

Newly added marketplaces are automatically added to the list of synchronized marketplaces. If a new marketplace does _not_ appear in the list after synchronization, it indicates that the marketplace is either incompatible with the Shopee Open Platform or unavailable for your specific seller account. Consult the Shopee Open Platform documentation or contact their support for further assistance.

Importante

While Odoo allows creating the same Shopee shop multiple times, only one instance will function due to token limitations. To avoid order management issues, synchronize each shop only once. For connection updates, manually fetch orders first before re-establishing the connection.

Vedi anche

  * [Shopee supported features and marketplaces](../shopee_connector.html)

  * [Shopee order management](manage.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/shopee_connector/setup.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Shopee order management") |
  * [precedente](../shopee_connector.html "Connettore Shopee") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Connettore Shopee](../shopee_connector.html) »
  * Shopee Connector configuration


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
  *[NSSL]: Non-Shopee Supported Logistics