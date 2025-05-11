# Reservation methods — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reservation_methods/at_confirmation.html "At confirmation reservation") |
  * [precedente](setup_configuration/print_on_validation.html "Printable delivery PDFs") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Reservation methods



# Reservation methods¶

Companies that sell and deliver goods to customers need to make sure they always have stock on-hand, so when new sales orders are confirmed, they can deliver products on time.

In Odoo, this can be handled using _reservation methods_. Reservation methods control how products included in a delivery order (DO) should be reserved for delivery, ensuring they are reserved at the correct times, for the correct orders.

There are three different reservation methods in Odoo: _At Confirmation_ , _Manually_ , and _Before scheduled date_.

At ConfirmationManuallyBefore scheduled date

Reserves products **only** when a sales order is confirmed, **and** if stock is already available.

Once a quote is confirmed, product availability **must** be checked manually, and the required quantity **must** be reserved manually.

A specific number of days can be selected; this is the maximum number of days **before** a scheduled delivery date that products should be reserved.

## Configurazione¶

Reservation methods are set on individual operations types. To configure reservation methods, go to Inventory app ‣ Configuration ‣ Operations Types. Then, select the desired operation type. Or, create a new one by clicking New.

In the General tab of the operation type form, locate the Reservation Method option, and choose which method should be used for this type of operation.

Suggerimento

If the Before scheduled date reservation method is selected, a new Reserve before scheduled date field appears below. From this field, the number of days before and days before when starred can be changed from the default `0`.

Changing the days before value changes the maximum number of days before a scheduled date that products should be reserved.

Changing the days before when starred value changes the maximum number of days before a scheduled date that starred (favorited) transfers for products should be reserved.

## Required applications¶

The two required applications that **must** be [installed](../../../general/apps_modules.html#general-install) to use reservation methods are the _Sales_ and _Inventory_ apps.

Nota

In addition to delivery orders, reservation methods can also be used for _manufacturing orders_ , _resupply subcontractor_ orders, orders for _repairs_ , and _internal transfers_ , if desired. To enable this, configure the additional settings:

  * **For manufacturing orders:** Install the _Manufacturing_ application by going to the Apps application, locating the _Manufacturing_ app, and clicking Install.

  * **For resupply subcontractor:** Navigate to Manufacturing app ‣ Configuration ‣ Settings, and under the Operations section, enable Subcontracting. Then, click Save.

  * **For repairs:** Install the _Repairs_ application by going to the Apps application, locating the _Repairs_ app, and clicking Install.

  * **For internal transfers:** Navigate to Inventory app ‣ Configuration ‣ Settings, and under the Warehouse section, enable Storage Locations. Then, click Save.




Once these apps are installed, no additional features need to be enabled from the settings for reservation methods to work. They will be available by default on certain operations types, and can be viewed and changed by navigating to Inventory app ‣ Configuration ‣ Operations Types, and then clicking on a specific operations type.

Nota

When the Type of Operation is changed to Receipt on an Operations Type form, reservation methods are **not** available.

Vedi anche

  * [At confirmation reservation](reservation_methods/at_confirmation.html)

  * [Manual reservation](reservation_methods/manually.html)

  * [Before scheduled date reservation](reservation_methods/before_scheduled_date.html)




  * [At confirmation reservation](reservation_methods/at_confirmation.html)
  * [Manual reservation](reservation_methods/manually.html)
  * [Before scheduled date reservation](reservation_methods/before_scheduled_date.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/reservation_methods.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reservation_methods/at_confirmation.html "At confirmation reservation") |
  * [precedente](setup_configuration/print_on_validation.html "Printable delivery PDFs") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Magazzino](../../inventory.html) »
  * [Shipping and receiving](../shipping_receiving.html) »
  * Reservation methods


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
  *[VAT]: Value Added Tax
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