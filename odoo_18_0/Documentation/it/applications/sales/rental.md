# Noleggio — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](members.html "Iscritti") |
  * [precedente](subscriptions/reports.html "Subscription reports") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Noleggio



# Noleggio¶

The Odoo _Rental_ application provides comprehensive solutions to configure and manage rentals.

Send quotations, confirm orders, schedule rentals, register products when they are picked up and returned, and invoice customers from this single platform.

Vedi anche

  * [Odoo Rental: product page](https://www.odoo.com/app/rental)

  * [Odoo Tutorials: Rental](https://www.odoo.com/slides/rental-48)




## Bacheca¶

Upon opening the _Rental_ application, the Rental Orders dashboard is revealed.

In the default kanban view, all rentals are visible. Each rental card displays the customer name, the price of the rental, the related sales order number, along with the status of the rental.

Nota

Rental kanban cards that do **not** display a rental status means those rentals have confirmed quotations, but have not been picked up yet.

On the left sidebar, the Rental Status for each rental can be found. Beneath that, the Invoice Status of the rentals is accessible. Clicking any option in the left sidebar filters the displayed rentals on the dashboard.

## Impostazioni¶

To configure additional rental delay costs, availability of rental items, or minimum time of rental, navigate to Rental app ‣ Configuration ‣ Settings.

In the Rental section, there are options to configure Default Delay Costs and Default Padding Time. There is also the option to activate Rental Transfers and Digital Documents.

  * Default Delay Costs are additional costs for late returns.

  * Default Padding Time represents the minimum amount of time between two rentals.

  * Rental Transfers means stock deliveries and receipts can be used for rental orders.

  * Digital Documents allows users to upload documents for customers to sign prior to
    

confirming their rental.




In the Rent Online section, there are options to configure a Minimal Rental Duration and designate Unavailability days, or days during which pickup and return are not possible.

## Rental products¶

To view all products that can rented in the database, navigate to Rentals app ‣ Products. By default, the Can be Rented search filter appears in the search bar.

Each product kanban card displays that product’s name, rental price, and product image (if applicable).

## Rental pricing¶

To adjust the rental pricing on a product, go to the Products page in the _Rental_ app, then select the desired product or click New to create a new product from scratch.

On the product form, ensure the Can be Rented checkbox is ticked. Then, open the Rental prices tab.

Nota

If creating a rental product outside of the _Rental_ app, just ensure the Can be Rented checkbox is ticked on the product form. By default, this checkbox is ticked whenever a product is created directly in the _Rental_ application.

### Tariffazione¶

Under the Pricing section of the Rental prices tab, designate custom rental prices and rental periods for the product.

To add pricing for a rental, click Add a price. Then, choose a _pricing period_ (the unit of duration of the rental) in the Period column, or create a new pricing period by typing in the name and clicking Create.

Next, decide whether or not to apply this custom rental price to a specific Pricelist.

Lastly, enter the desired Price for that specific Period.

Nota

There is no limit to how many pricing lines can be added. Multiple pricing options for rental products are typically used to give discounts for customers who agree to longer rental durations.

To delete any rental pricing option, click the 🗑️ (trash) icon, and that row is deleted.

### Prenotazioni¶

Under the Reservations section of the Rental prices tab, there is the option to configure additional fines for any Extra Hour or Extra Day that the customer takes to return a rental.

There is also the option to set a Security Time, expressed in hours, to make the rental product temporarily unavailable between two rental orders. Such a feature may prove useful if maintenance or cleaning is required between rentals.

### Price computing¶

Odoo always uses two rules to compute the price of a product when a rental order is created:

  1. Only one price line is used.

  2. The cheapest line is selected.




Exercise

Consider the following rental pricing configuration for a product:

  * 1 day: $100

  * 3 days: $250

  * 1 week: $500




A customer wants to rent this product for eight days. What price will they pay?

After an order is created, Odoo selects the second line as this is the cheapest option. The customer has to pay three times “3 days” to cover the rental’s eight days, for a total of $750.

## Rental orders¶

To create a rental order in the _Rental_ app, navigate to Rental app ‣ Orders ‣ Orders, and click New. Doing so reveals a blank rental order form to be filled in accordingly.

Start by adding a Customer, then configure the desired duration of the rental in the Rental period field.

To adjust the rental duration, click the first date in the Rental period field, and select the range of dates to represent the rental duration from the pop-up calendar form that appears.

Once complete, click Apply in the calendar pop-up form. Following that, the pop-up form disappears, and the designated time period of the rental is represented in the Duration field.

Next, add a rental product in the Order Lines tab, by clicking Add a product, and selecting the desired rental product to add to the form.

Nota

If a rental product is added _before_ the Rental period field has been properly configured, the user can _still_ adjust the Rental period field accordingly.

Simply select the desired range of dates to represent the duration of the rental, then click Update Rental Prices in the Duration field.

Doing so reveals a Confirmation pop-up window. If everything is correct, click Ok, and Odoo recalculates the rental price accordingly.

Once all the information has been entered correctly on the rental order form, click the Send by Email button to send the quotation to the customer, or click the Confirm button to confirm the order.

## Customer signature¶

Upon confirming a rental order, the Sign Documents button appears. This gives the ability to request the customer sign a rental agreement, outlining the arrangement between the company and customer, _before_ they pick up the rental product(s).

Such documents can ensure everything is returned on-time and in its original condition.

Importante

The Sign Documents button/option **only** appears if the Digital Documents feature has been activated in the _Rental_ application settings. To do so, navigate to Rental app ‣ Configuration ‣ Settings, activate Digital Documents, and click Save.

Nota

This feature also requires the [Sign](../productivity/sign.html) app. If necessary, Odoo automatically installs it after activating the Digital Documents setting.

To request a customer signature on a rental agreement, select a confirmed rental order, and click the Sign Documents button to reveal a Sign Documents pop-up window.

From here, select the desired document from the Document Template field. Then, click Sign Document. Doing so reveals a New Signature Request pop-up window.

Upon confirming the information in the New Signature Request pop-up form, click Sign Now to initiate the signing process.

A separate page is then revealed, showcasing the document to be signed, which is accessible to the customer via the customer portal.

Odoo guides the customer through the signing process with clear, clickable indicators, and allows them to create electronic signatures to quickly complete the form.

Once the document has been signed and completed, click the Validate & Send Completed Document button at the bottom of the document.

Upon clicking the Validate & Send Completed Document button, Odoo presents the option to download the signed document for record-keeping purposes, if necessary.

Vedi anche

[Odoo Tutorials: Sign](https://www.odoo.com/slides/sign-61)

## Pickup products¶

When a customer picks up the product(s), navigate to the appropriate rental order, click the Pickup button, and then click Validate in the Validate a pickup pop-up form that appears.

Doing so places a Picked-up status banner on the rental order.

## Return products¶

When a customer returns the product(s), navigate to the appropriate rental order, click the Return button, and validate the return by clicking Validate in the Validate a return pop-up form that appears.

Doing so places a Returned status banner on the rental order.

## Print pickup and return receipts¶

Pickup and return receipts can be printed for customers when they pick up and/or return rental products.

To print pickup and/or return receipts, navigate to the appropriate rental order, click the ⚙️ (gear) icon to reveal a drop-down menu.

From this drop-down menu, hover over the Print option to reveal a sub-menu. Then select Pickup and Return Receipt.

Odoo generates and downloads a PDF, detailing all information about the current status of the rented item(s).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/rental.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](members.html "Iscritti") |
  * [precedente](subscriptions/reports.html "Subscription reports") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Noleggio


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