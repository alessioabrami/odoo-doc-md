# Foreign currencies — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](discounts.html "Sconti") |
  * [precedente](pricing.html "Listini prezzi") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your pricing](../prices.html) »
  * Foreign currencies



# Foreign currencies¶

With Odoo, pricelists can be used to manage prices in a number of foreign currencies. Specifically, Odoo has the ability to work with 167 total currencies.

Nota

In order to use multiple currencies in Odoo _Sales_ , the _Accounting_ application **must** be installed.

## Impostazioni¶

Once the _Accounting_ app has been installed, foreign currencies can be added to the database. Navigate to Accounting app ‣ Configuration ‣ Settings, scroll to the Currencies section, and locate the Main Currency setting.

Odoo automatically sets the main currency as the currency of the country the company is based in.

To change the main currency of the company, select the drop-down menu in the Currency field, select the desired currency, and be sure to Save the changes.

Suggerimento

To ensure currency rates are updated automatically, enable the _automatic currency rates_ feature on the _Accounting_ settings page (Accounting app ‣ Configuration ‣ Settings ‣ Currencies section).

Click the checkbox beside the Automatic Currency Rates feature, choose a designated bank to get the currency rates from in the Service field drop-down menu, and select an Interval of time for the updates to take place. Then determine when the date of the Next Run should be.

To instantly update the currency rates, click the 🔁 (circular arrows) icon, located to the right of the Next Run field.

When all configurations are complete, be sure to Save all changes.

Nota

All payment methods **must** be in the same currency as the sales journal, or the company currency, if the company currency is not set. If it is not the same, a Validation Error message appears.

## View, edit, and add currencies¶

To view, edit, and add currencies to the database, making them available on pricelists and on the Main Currency drop-down menu, click the Currencies link, located beneath the Currency field on the Accounting app ‣ Settings page.

When the Currencies link is clicked, a separate Currencies page is revealed.

On this page, Odoo provides a master list of 167 global currencies. Each row shows the corresponding Currency, Symbol, Name, date of the Last Update, and Current Rate (compared to the default currency of the country in which the company is based).

To the far right, there are two columns, which can be toggled on or off:

  * Active: this currency is activated, which means it can be added to a pricelist, or used as the main currency of the company, if desired (via Accounting app ‣ Configuration ‣ Settings ‣ Currencies section).




Nota

By default, all the Active currency options are at the top of the list.

Suggerimento

It is recommended that _at least_ one pricelist is created per Active currency. See [Listini prezzi](pricing.html) to learn more about pricelist configuration.

To toggle options on/off, click the toggle switch in the row for the corresponding column. When _on_ the color of the switch is green. When _off_ , the color of the switch is grey.

### Currency detail form¶

To edit any currency on the Currencies page, click the desired currency to reveal the detail form for that specific currency, and proceed to make any necessary changes.

On the currency detail form, the relevant currency code appears in the Currency field. Beneath that, the name for the currency is in the Name field.

Then, toggle the currency’s availability with the Active toggle: _on_ is indicated with a green switch, and _off_ is indicated with a grey switch.

On the right of the currency detail form, the appropriate Currency Unit (e.g. `Dollars`) and Currency Subunit (e.g. `Cents`) can be found.

Next, under the Rates tab, the various conversion rates can be viewed, added, or deleted. Each row shows the Date of that specific rate, the Company to which it is connected, followed by the Unit per… and …per Unit.

Nota

The _…_ in each of the last two columns represents the main currency set for the company. For example, if the main currency is set to `USD`, the columns are titled Unit per USD and USD per Unit.

To add a new rate, click Add a line in the Rates tab, and proceed to fill in the necessary information in the aforementioned columns.

### Main currency detail form¶

If the selected currency is the main currency of the company, a blue banner appears at the top of the currency detail form with the message: This is your company’s currency..

All the fields are the same as a typical currency detail form, but there will **not** be a Rates tab because all other currency rates are based off the main currency of the company.

## Create new currency¶

If a desired currency isn’t on the Currencies page, click the New button to open a blank currency template form.

Suggerimento

The same New button is located in the upper-right corner of any currency detail form.

On the blank currency detail form, proceed to enter the desired currency code in the Currency field. Beneath that, enter the name for the currency in the Name field.

Then, toggle the currency’s availability with the Active toggle switch.

On the right of the currency detail form, enter the appropriate Currency Unit (e.g. `Dollars`) and appropriate Currency Subunit (e.g. `Cents`).

Next, under the Rates tab, add a new rate by clicking Add a line. Then, proceed to confirm and adjust the Date, Company, Unit per…, and …per Unit fields to ensure all the auto-populated information is accurate.

Nota

The _…_ in each of the last two columns represents the main currency set for the company. For example, if the main currency is set to `USD`, the columns are titled Unit per USD and USD per Unit.

## Currency-specific pricelists¶

It is recommended that _at least_ one pricelist is created per active currency in the database. To create (or assign) a pricelist to a specific currency, start by navigating to Sales app ‣ Products ‣ Pricelists.

From the Pricelists page, either select an existing pricelist to edit, or click New to create a new pricelist.

On the pricelist detail form, for either a new or existing pricelist, adjust the Currency field as desired.

Vedi anche

[Listini prezzi](pricing.html) to learn more about pricelist configuration.

## Auto-conversion from public price¶

It should be noted that the public price seen on products is directly related to the main currency the company has set, which is configured by navigating to Accounting app ‣ Configuration ‣ Settings ‣ Currencies section ‣ Main Currency ‣ Currency drop-down menu.

The sales price automatically updates if the pricelist is changed to a different pricelist that has a different currency than the company’s main currency. The change in price is directly related to the updated conversion rate for that currency.

## Set product prices¶

In order to have product prices set in place to avoid any changes in currency rates, start by navigating to Sales app ‣ Products ‣ Products.

From the Products page, select the desired product to modify. Or, create a new product by clicking the New button.

Then, on the product detail form, click the Extra Prices smart button, located in the upper-left corner. Doing so reveals a separate Price Rules page, specific to that particular product.

Click New, and select the desired pricelist from the drop-down menu in the Pricelist column.

The Applied On field is auto-populated with the product, so proceed to enter in the desired figures in the Min. Quantity and Price fields.

Nota

The figure in the Min. Quantity field means the Price being set will **only** trigger if at least that amount of product is purchased.

If necessary, configure a Start Date and End Date for the set prices. Leaving those columns blank ensures the set price will remain valid, regardless of the date of sale.

If working in a multi-company environment, designate to which company this price rule should be applied in the Company field. Leaving that field blank ensures the price rule applies to all companies in the database.

With those configurations complete, regardless of any changes/updates in conversion, whenever those designated pricelists are applied to a customer trying to purchase this specific product, these pre-determined set prices appear.

Vedi anche

[Listini prezzi](pricing.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/products_prices/prices/currencies.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](discounts.html "Sconti") |
  * [precedente](pricing.html "Listini prezzi") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Vendite](../../../sales.html) »
  * [Products & Prices](../../products_prices.html) »
  * [Manage your pricing](../prices.html) »
  * Foreign currencies


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