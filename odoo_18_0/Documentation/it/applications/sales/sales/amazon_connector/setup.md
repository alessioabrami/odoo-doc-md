# Amazon Connector configuration — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Amazon order management") |
  * [precedente](features.html "Amazon Connector features") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon Connector configuration



# Amazon Connector configuration¶

Odoo allows users to register an Amazon seller account in the database, but the user **must** have a paid Amazon Seller account prior to completing the configuration.

Set up a paid Seller account on Amazon by first logging into the Amazon platform, and navigating to Account & Lists ‣ Start a Selling Account from the drop-down menu located in the header section.

Then on the Sell with Amazon page, follow the sign-up process and finally proceed to follow the instructions below to register and link that Amazon Seller account in Odoo.

Vedi anche

[Sell with Amazon](https://www.amazon.com/b/?node=12766669011)

## Connect Amazon Seller account to Odoo¶

To connect an Amazon Seller account in Odoo, navigate to Sales app ‣ Configuration ‣ Settings ‣ Connectors section, activate the Amazon Sync feature, and click Save.

Then, return to Sales app ‣ Configuration ‣ Settings ‣ Connectors section, and click on the Amazon Accounts link under the Amazon Sync setting.

Doing so reveals a separate Amazon Accounts page. From here, click New to create and link a new Amazon account.

On the blank Amazon Account form page, start by choosing a name for the account (e.g. `American Marketplace`). Then, in the Credentials tab, select the marketplace on which the seller account was initially created from the Home Marketplace drop-down menu.

After saving, the field in the Credentials tab is replaced by a Link with Amazon button.

Clicking that button redirects to either the Amazon login page, or directly to the required consent page, if the user is already logged in to Amazon.

On the login page, log in to the desired Amazon seller account.

On the consent page, confirm that Amazon is allowed to give Odoo access to the account and related data.

Upon confirmation, Amazon returns the user to Odoo, and the account has been registered.

With the Amazon account successfully registered, the marketplaces available to this specific account are synchronized with Odoo and listed under the Marketplaces tab.

If desired, remove items from the list of synchronized marketplaces to disable synchronization.

## Amazon orders in Odoo¶

When an Amazon order is synchronized, up to three line items are created on the sales order in Odoo. Each one represents a product sold on Amazon: one for the product that was sold on Amazon Marketplace, one for the shipping charges (if any), and one for the gift wrapping charges (if any).

The selection of a database product for a sales order item is done by matching its Internal Reference (a customizable product reference idenifier in Odoo, like `FURN001`) with the Amazon _SKU_ for marketplace items, the Amazon _Shipping Code_ for delivery charges, and the Amazon _Gift Wrapping_ code for gift wrapping charges.

For marketplace products, pairings are saved as _Amazon Offers_ , which are listed under the Offers smart button on the account form.

Offers are automatically created when the pairing is established, and they’re used for subsequent orders to lookup SKUs. If no offer with a matching SKU is found, the internal reference is used instead.

Suggerimento

It’s possible to force the pairing of a marketplace item with a specific product, by changing either the product or the SKU of an offer to ensure they match. The offer can be manually created if it was not automatically done yet.

This is useful if the internal reference is not used as the SKU, or if the product sells under different conditions.

If no database product with a matching internal reference is found for a given Amazon SKU or gift wrapping code, then a default database product, _Amazon Sale_ , is used. The same is done with the default product _Amazon Shipping_ if no database product is found for a given Amazon shipping code.

Nota

To modify default products, activate the [developer mode](../../../general/developer_mode.html#developer-mode), and navigate to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Default Products.

## Product tax configuration¶

To allow for tax reporting of Amazon sales with Odoo, the taxes applied to the sales order items are those set on the product, or determined by the fiscal position.

Make sure to have the correct taxes set on your products in Odoo, or have it done by a fiscal position, to avoid discrepancies in the subtotals between _Amazon Seller Central_ and Odoo.

Nota

As Amazon does not necessarily apply the same taxes as those configured in Odoo, it may happen that order totals differ by a few cents between Odoo and _Amazon Seller Central_. Those differences can be resolved with a write-off when reconciling the payments in Odoo.

## Add a new marketplace¶

All marketplaces are supported by the Amazon Connector. To add a new marketplace, proceed as follows:

  1. attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode).

  2. Go to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Marketplaces.

  3. Click New to create a new marketplace record.

  4. Enter the Marketplace ID in the API Idenifier field, and select the Amazon Region for your marketplace as described in the [Amazon Documentation for marketplace IDs and regions](https://developer-docs.amazon.com/sp-api/docs/marketplace-ids), and the Seller Central URL as described in the [Amazon Documentation for seller central URLs](https://developer-docs.amazon.com/sp-api/docs/seller-central-urls).

  5. Set the Name of the record to `Amazon.<country code>` to easily retrieve it (e.g. `Amazon.se`). The API Identifier, the Region and the Seller Central URL fields should respectively hold the _Marketplace ID_ , the selected Amazon region, and the _Seller Central URL_ values from the Amazon Documentation.

  6. Once the marketplace is saved, update the Amazon Account configuration by going to Sales app ‣ Configuration ‣ Settings ‣ Connectors ‣ Amazon Sync ‣ Amazon Accounts.

  7. Select the account on which to use the new marketplace, go to the Marketplaces tab, and click on Update available marketplaces. An animation should confirm the success of the operation. Newly added marketplaces are automatically added to the list of synchronized marketplaces. If the new marketplace is not added to the list, it means that it is either incompatible or unavailable for the seller account.




Vedi anche

  * [Amazon Connector features](features.html)

  * [Amazon order management](manage.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/amazon_connector/setup.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Amazon order management") |
  * [precedente](features.html "Amazon Connector features") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Integrazione con Amazon](../amazon_connector.html) »
  * Amazon Connector configuration


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