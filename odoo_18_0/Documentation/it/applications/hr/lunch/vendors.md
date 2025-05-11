# Fornitori — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products.html "Prodotti") |
  * [precedente](../lunch.html "Mensa") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Fornitori



# Fornitori¶

Before [products can be added](products.html) to the **Lunch** app, the restaurants that provide the food needs to be configured.

To add a new vendor, first navigate to Lunch app ‣ Configuration ‣ Vendors. Here, all currently configured vendors for the **Lunch** app appear in a default Kanban view. To change to a list view, click the __(List) icon in the top-right corner.

Nota

No vendors are preconfigured in the **Lunch** app, so all vendors **must** be added to the database.

A placeholder Lunch Supplier card appears on the Vendors dashboard, by default. Click on this card, and configure the following fields on the vendor form:

  * Vendor information

  * Availability

  * Orders

  * Extras




After the first vendor is configured, add more vendors by clicking the New button in the top-left corner, and configure the new lunch supplier form. Repeat for all needed vendors.

## Vendor information¶

  * Vendor: Enter a name for the vendor in this field.

  * Vendor (beneath the line for vendor name): Using the drop-down menu, select the corresponding vendor in the **Contacts** app. If the vendor has not already been created, type in the vendor name, and click Create «new vendor name» to add them. Alternatively, click Create and edit… to create the vendor and edit the vendor contact form. The vendor contact form allows for more details to be entered, such as contact information.

Nota

If a selection is made to the drop-down Vendor field, the Vendor text field (above, for the vendor’s name) updates with the name of the vendor chosen from the drop-down menu.

The list of vendors that is presented in the drop-down menu is pulled from the **Contacts** application.

  * Address: Enter the vendor’s address in the various fields.

  * Email: Enter the vendor’s email in this field.

  * Phone: Enter the vendor’s phone number in this field.

  * Company: If this vendor is only available to a specific company, select the company from the drop-down menu. If this field is left blank, the vendor’s items are available to **all** companies. This field **only** appears in a multi-company database.




## Disponibilità¶

The AVAILABILITY section presents a table with two rows. The days of the week populate the top row, and the bottom row has checkboxes. Tick the corresponding checkbox for each day of the week the vendor is available.

By default, Monday through Friday are ticked.

## Ordini¶

The ORDERS section of the vendor form details which locations the vendor is available for, in addition to how and when orders are placed and received.

  * Delivery: Using the drop-down menu, select Delivery if the vendor delivers to the office, or select No Delivery if orders must be picked up.

  * Location: Select which locations are able to order from this vendor. Multiple locations can be selected. If this field is left blank, **all** locations can order from the vendor.

Nota

An `HQ Office` location is created by default when creating a database, and is available to select from the list.

  * Send Order By: Click the radio button to select how orders are sent to the vendor. The available options are Phone or Email.

  * Order Time: This field **only** appears if Email is selected in the Send Order By field. Enter the time that an order must be emailed for it to be accepted. Enter the time in the following format: `HH:MM`. Then select either AM or PM from the drop-down menu, next to the time field.




## Supplementi¶

When ordering an item in the **Lunch** app, optional extra items, sometimes referred to as _add-ons_ , can be shown. These can be configured in any manner that suits the products being offered.

By default, Odoo allows for three types of extra items, which can be thought of as _categories_. By default, the first type (or _category_) of add-ons is labeled `Extras`, the second is labeled `Beverages`, and the third is labeled `Extra Label 3`.

Importante

When configuring the extras, it is important to keep in mind that all the extras configured appear for **every item** offered by the vendor. That means that only items which apply to **all** products from the vendor should be added.

### Configure extras¶

Enter the following information for each of the three available extra sections:

  * Extra (#) Label: Enter a name for the type of extra, such as `Toppings`. This can be thought of as a _category_.

  * Extra (#) Quantity: Select how the extras are selected. The options are:

    * None or More: Select this option if the user is not required to make a selection.

    * One or More: Select this option to **require** the user to make **at least one** selection.

    * Only One: Select this option to **require** the user to make **only one** selection.




### Add extras¶

After the labels and quantities have been configured for an extra category, the individual extra items must be added for each category.

Click Add a line at the bottom of the list that appears on the right-hand side of the extra category. Enter the Name and Price for each item being added. The price can remain at `$0.00` if there is no cost. This is common for items like disposable silverware or condiments.

Example

For a pizzeria that only offers personal pizzas, see their extras configured as follows:

The first extra is configured for the various toppings they offer. The Extra 1 Label is set to `Toppings`, and the Extra 1 Quantity is set to None or More. The various toppings are then added, with their corresponding costs.

The pizzeria also offers a free beverage with any purchase. To set this up, the Extra 2 Label is set to `Beverages`, and the Extra 2 Quantity is set to Only One. The various beverage choices are added, and the cost for each remains zero.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/lunch/vendors.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](products.html "Prodotti") |
  * [precedente](../lunch.html "Mensa") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Fornitori


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
  *[API]: application programming interfaces
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
  *[POS]: Punto vendita
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
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number