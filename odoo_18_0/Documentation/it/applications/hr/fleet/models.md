# Models & manufacturers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](new_vehicle.html "Adding vehicles") |
  * [precedente](../fleet.html "Parco veicoli") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Models & manufacturers



# Models & manufacturers¶

Odoo’s **Fleet** app categorizes each vehicle by _manufacturer_ and _model_ (e.g. `BMW`, `X2`). Before the vehicle can be added to the Odoo database, its manufacturer and a model records must already exist in the database.

## Produttori¶

Odoo’s **Fleet** app comes preconfigured with sixty-six commonly used car and bicycle manufacturers in the database, along with their logos. To view the pre-loaded manufacturers, go to Fleet app ‣ Configuration ‣ Manufacturers.

The default filter, With Models, displays only manufacturers that already have vehicle models. Remove the default filter to view _all_ manufacturers.

Manufacturers re listed alphabetically, and each card shows how many specific models are configured for each particular manufacturer.

### Add a manufacturer¶

To add a new manufacturer to the database, click New in the upper-left corner, to open a blank manufacturers form. Type the name of the manufacturer in the Name field, and select an image to upload for the logo.

## Models¶

When adding a vehicle to the fleet, specify the vehicle model to maintain updated records, which keeps track of specific details, like maintenance schedules and parts compatibility.

Unlike manufacturers, models do **not** come preconfigured in the **Fleet** app. When a new vehicle model joins the fleet, the model (and, if necessary, the manufacturer) **must** be added to the database.

### Add a model¶

To add a new vehicle model, navigate to Fleet app ‣ Configuration ‣ Models. Click New in the upper-left corner, and enter the following information on the new model form.

Nota

Depending on the installed [localization](../../finance/fiscal_localizations.html), some fields or sections may not appear.

  * Model name: Enter the model name in the field.

  * Manufacturer: Using the drop-down menu, select the manufacturer. If it is not configured, add the manufacturer

  * Vehicle Type: Using the drop-down menu, select one of two preconfigured vehicle types, either Car or Bike.

Importante

Additional vehicle types can **not** be added. **Fleet** keeps them fixed to preserve its **Payroll** integration, where vehicles may count as employee benefits.

  * Category: Using the drop-down menu, select a category for the vehicle or create a new one.




### Information tab¶

In the Information tab, specify details about the car model, such as the car size, passenger capacity, cost settings (applicable to the Belgium localization only), and engine information.

#### Model¶

  * Seats Number: Enter how many passengers the vehicle can accommodate.

  * Doors Number: Enter the number of doors the vehicle has.

  * Model Year: Enter the year the vehicle was manufactured.

  * Trailer Hitch: Tick this checkbox if the vehicle has a trailer hitch installed.




#### Retribuzione¶

The Salary section **only** appears if the company has their localization setting set to Belgium. The cost values are all _monthly_ , with the exception of the Catalog Value (VAT Incl.).

  * Can be requested: Tick this checkbox if employees can request this model vehicle, if a vehicle is part of their employee contract.

  * Catalog Value (VAT Incl.): enter the MSRP for the vehicle at the time of purchase or lease.

  * C02 fee: Represents the carbon dioxide emission fee paid to the Belgian government. This value is automatically calculated, based on Belgian laws and regulations, and **cannot** be modified. The value is based on the figure entered in the CO2 Emissions field (in the Engine section of the Information tab) on the vehicle form.




Importante

Modifying the CO2 Emissions field adjusts the value in the CO2 fee field.

  * Cost (Depreciated): Enter the monthly vehicle cost, which appears in the salary configurator for future employees. This value impacts the gross and net salary of the employee assigned to the vehicle. This figure is depreciated over time, according to local tax laws. The Cost (Depreciated) does **not** depreciate automatically on the _vehicle model_ , it only depreciates based on the _contract_ linked to a specific vehicle.

  * Total Cost (Depreciated): This value is the combination of the Cost (Depreciated) and the C02 fee fields. It also depreciated over time.




#### Motore¶

  * Fuel Type: Using the drop-down menu, select the type of fuel the vehicle uses. The default options are Diesel, Gasoline, Full Hybrid Plug-in Hybrid Diesel, Plug-in Hybrid Gasoline, CNG, LPG, Hydrogen, or Electric.

  * Range: Enter the distance the vehicle can travel on one tank of gas, or one battery charge, in kilometers.

  * CO2 Emissions: Enter the average carbon dioxide emissions the vehicle produces in grams per kilometer (g/km). This information is provided by the car manufacturer.

  * CO2 Standard: Enter the standard amount of carbon dioxide in grams per kilometer (g/km) for a similar-sized vehicle.

  * Transmission: Using the drop-down menu, select the type of transmission, either Manual or Automatic.

  * Power Unit: Using the drop-down menu, select how the vehicle’s power is measured, either in kilowatts or horsepower.

  * Power: If the vehicle is electric or hybrid, enter the power the vehicle uses in kilowatts (kW). This field only appears if kW is selected for the Power field.

  * Horsepower: Enter the vehicle’s horsepower in this field. This field only appears if Horsepower is selected for the Power field.

  * Horsepower Taxation: Enter the amount that is taxed, based on the size of the vehicle’s engine. This is determined by local taxes and regulations, and varies depending on the location. It is recommended to check with the accounting department to ensure this value is correct. This field only appears if Horsepower is selected for the Power field.

  * Horsepower Taxation: Enter the amount of taxes incurred according to the engine specifications. The number is dependent on the local tax laws, therefore it is recommended to check with the accounting department to ensure the correct taxation amount is entered. This field only appears if the Power field is set to Horsepower.

  * Tax Deduction: The percentage that can be deducted from taxes is populated based on the localization, and **cannot** be modified. This field only appears for certain localizations.




### Vendors tab¶

Specify the vendors a vehicle can be purchased from in this tab. With proper setup, [requests for quotations](../../inventory_and_mrp/purchase/manage_deals/rfq.html) for vehicles can be created through Odoo’s **Purchase** app.

To add a vendor, click Add in the upper-left corner of the Vendors tab. This opens an Add: Vendors pop-up window, with a list of all the vendors currently in the database. Add a vendor by ticking the checkbox next to the vendor name, then click Select. No limitations exist on the number of vendors that can be added to this list.

If a vendor is _not_ already in the database, add a vendor by clicking New in the bottom-left of the Add: Vendors pop-up window. In the Create Vendors form that appears, enter the necessary information, then click Save & Close to add the vendor, or click Save & New to add the current vendor and create another new vendor.

## Model category¶

To aid with fleet organization, it is recommended to have vehicle models housed under a specific category. Model categories are set on the vehicle model form.

Odoo does **not** come with any categories preconfigured; all categories **must** be added.

To view any categories currently set up in the database, navigate to Fleet app ‣ Configuration ‣ Categories. All categories are displayed in a list view.

### Add a new model category¶

To add a new category, click the New button in the top-left corner of the Categories dashboard. A new entry line appears at the bottom of the list. Type in the new category, then either click Save, or click anywhere on the screen, to save the entry.

To reorganize how the categories appear in the list, click on the __(draggable) icon to the left of any desired category name, and drag the line to the desired position.

The order of the list does _not_ affect the database in any way. However, it may be preferable to view the vehicle categories in a specific order, for example, by size, or the number of passengers the vehicle can carry.

Nota

When used with the **Inventory** app, the Max Weight and Max Volume fields track a vehicle’s capacity. This helps manage in-house deliveries by [showing how much space and weight remain for loading products](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dispatch.html).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/fleet/models.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](new_vehicle.html "Adding vehicles") |
  * [precedente](../fleet.html "Parco veicoli") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Models & manufacturers


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