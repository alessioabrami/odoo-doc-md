# Purchase units of measure — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../manage_deals.html "Manage deals") |
  * [precedente](temporary_reordering.html "Temporary reordering rules") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Purchase units of measure



# Purchase units of measure¶

When you purchase a product, it may happen that your vendor uses a different unit of measure than when it is sold. This can cause confusion between sales and purchase representatives. It is also time-consuming to convert measures manually every time. With Odoo, you can configure your product once and let Odoo handle the conversion.

Consider the following examples:

  1. You purchase orange juice from an American vendor, and they use **gallons**. However, your customers are European and use **liters**.

  2. You buy curtains from a vendor in the form of **rolls** and you sell pieces of the rolls to your customers using **square meters**.




## Enable units of measure¶

Open your Sales app and go to Configuration ‣ Settings. Under Product Catalog, enable _Units of Measure_.

## Specify sales and purchase units of measure¶

### Standard units of measure¶

A variety of units of measure are available by default in your database. Each belongs to one of the five pre-configured units of measure categories: _Length / Distance_ , _Unit_ , _Volume_ , _Weight_ and _Working Time_.

Suggerimento

You can create your new units of measure and units of measure categories (see next section).

To specify different units of measures for sales and purchases, open the Purchase app and go to Products ‣ Products. Create a product or select an existing one. Under the product’s _General Information_ tab, first select the _Unit of Measure_ to be used for sales (as well as for other apps such as inventory). Then, select the _Purchase Unit of Measure_ to be used for purchases.

Back to the first example, if you purchase orange juice from your vendor in **gallons** and sell it to your customers in **liters** , first select _L_ (liters) as the _Unit of Measure_ , and _gal (US)_ (gallons) as the _Purchase Unit of Measure_ , then click on _Save_.

### Create new units of measure and units of measure categories¶

Sometimes you need to create your own units and categories, either because the measure is not pre-configured in Odoo or because the units do not relate with each other (e.g. kilos and centimeters).

If you take the second example where you buy curtains from a vendor in the form of **rolls** and you sell pieces of the rolls using **square meters** , you need to create a new _Units of Measure Category_ in order to relate both units of measure.

To do so, go to Configuration ‣ Units of Measure Categories. Click on _Create_ and name the category.

The next step is to create the two units of measures. To do so, click into the Unit of Measure Category field and enter a name for the category. Then, under the Units of Measure tab, click Add a line.

First, create the unit of measure used as the reference point for converting to other units of measure inside the category. Name the unit, and select the units of measure category you just created. For the _Type_ , select _Reference Unit of Measure for this category type_. Enter the _Rounding Precision_ you would like to use. The quantity computed by Odoo is always a multiple of this value.

In the example, as you cannot purchase less than 1 roll and won’t use fractions of a roll as a unit of measure, you can enter 1.

Nota

If you use a _Rounding Precision_ inferior to 0.01, a warning message might appear stating that it is higher than the _Decimal Accuracy_ and that it might cause inconsistencies. If you wish to use a _Rounding Precision_ lower than 0.01, first activate the [developer mode](../../../general/developer_mode.html#developer-mode), then go to Settings ‣ Technical ‣ Database Structure ‣ Decimal Accuracy, select _Product Unit of Measure_ and edit _Digits_ accordingly. For example, if you want to use a rounding precision of 0.00001, set _Digits_ to 5.

Next, create a second unit of measure, name it, and select the same units of measure category as your reference unit. As _Type_ , select _Smaller_ or _Bigger than the reference Unit of Measure_ , depending on your situation.

As the curtain roll equals to 100 square meters, you should select _Smaller_.

Next, you need to enter the _Ratio_ between your reference unit and the second one. If the second unit is smaller, the _Ratio_ should be greater than 1. If the second unit is larger, the ratio should be smaller than 1.

For your curtain roll, the ratio should be set to 100.

You can now configure your product just as you would using Odoo’s standard units of measure.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/products/uom.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../manage_deals.html "Manage deals") |
  * [precedente](temporary_reordering.html "Temporary reordering rules") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Purchase units of measure


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
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: purchase order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure