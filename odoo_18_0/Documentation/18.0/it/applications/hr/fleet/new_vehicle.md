# Adding vehicles — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](service.html "Servizi") |
  * [precedente](models.html "Models & manufacturers") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Adding vehicles



# Adding vehicles¶

Odoo’s **Fleet** app manages all vehicles, and the accompanying documentation that comes with vehicle maintenance and driver records.

Upon opening the Fleet application, all vehicles are organized within the Vehicles dashboard, which is the default dashboard. Each vehicle is displayed in its corresponding Kanban stage, based on its status. The default stages are New Request, To Order, Registered, and Downgraded.

## Impostazioni¶

Before registering any vehicles, review two **Fleet** settings that directly affect day-to-day operations and employee benefits:

  * End Date Contract Alert — emails the contract’s _Responsible_ person a set number of days before the vehicle agreement expires, so renewals or returns aren’t missed.

  * New Vehicle Request — (Belgian Payroll localization only) blocks employees from requesting a new company car through the salary configurator, once the available vehicles already exceeds the defined limit, helping control benefits costs.




To access the settings menu, go to Fleet app ‣ Configuration ‣ Settings.

### Avviso data di fine contratto¶

The End Date Contract Alert field shows how many days before the end of a vehicle contract an alert should be sent. The responsible parties receive an email informing them that a vehicle contract is about to expire in the number of days defined in this field.

#### Responsible parties¶

To determine the responsible person is for a contract, open an individual contract. The person listed as Responsible under the Contract Information section of the contract receives the alert.

To open a contract from a list of all contracts, navigate to Fleet app ‣ Fleet ‣ Contracts and all contracts appear in the list. Click on a Contract to open it. In the Information section of the contract, look under Responsible to see who receives expiration alerts.

An individual contract can also be opened from a specific vehicle by navigating to Fleet app ‣ Fleet ‣ Fleet and clicking on an individual vehicle. On the vehicle form, click the Contracts smart button at the top of the page. Only contracts associated with the vehicle appear in the list. Click on an individual contract to open it. The Responsible person is listed on the contract.

### New Vehicle Request (Belgian Payroll - Fleet)¶

Enter the maximum fleet size that may be reached through the salary-configurator flow. When the total number of available vehicles (vehicles without an assigned driver) is equal to or below this limit, employees can request a new company car. Once the available vehicles exceeds the limit, the request option is hidden.

Example

If the New Vehicle Request limit is set to 20 vehicles, and there are 25 vehicles available, employees cannot request a new car and must select from the 25 already available. If there are only 10 cars available, then the employee would be able to request a new vehicle.

Nota

This settings option **only** appears if the Belgian-Payroll-Fleet module is installed for the Belgian localization.

## Add a vehicle¶

To add a new vehicle to the fleet from the Vehicles dashboard, click the New button in the top-left corner, and a blank vehicle form loads. Then, proceed to enter the vehicle information on the vehicle form.

## Vehicle form fields¶

  * Model: Using the drop-down menu, select the vehicle’s model. Once a model is selected, additional fields may appear on the form. If the model is not listed, type in the model name, and click either Create «model», or Create and edit… to [create a new model and edit the model details](models.html#fleet-add-model).

  * License Plate: Enter the vehicle’s license plate number.

  * Tags: Select any tags from the drop-down menu, or type in a new tag. There is no limit on the amount of tags that can be selected.




Nota

The Model is the _only_ required field on the new vehicle form. When a model is selected, other fields appear on the vehicle form, and relevant information auto-populates the fields that apply to the model. If some of the fields do not appear, this may indicate there is no model selected.

### Driver¶

This section of the vehicle form relates to the person who is currently driving the car, as well as any plans for a change in the driver in the future, and when.

  * Driver: Using the drop-down menu, select the driver for the vehicle. If the driver is not listed, create the new driver, and edit the driver details.

Importante

A driver does _not_ have to be an employee. When creating a new driver, the driver is added to the **Fleet** app, _not_ the **Employees** app.

If the **Contacts** app is installed, the driver information is also stored there.

  * Mobility Card: If the selected driver has a mobility card (such as a gas card) listed on their employee record in the **Employees** application, the mobility card number automatically appears in this field. If there is no mobility card listed, and one should be added, [edit the employee record](../employees/new_employee.html#employees-hr-settings) in the **Employees** application.

  * Future Driver: If the next driver for the vehicle is known, select the next driver from the drop-down menu. Or, type in the next driver and click either Create «future driver» or Create and edit… to create a new future driver, and edit the driver details.

Nota

If this field is populated, a Apply New Driver button appears on the vehicle form. Click the Apply New Driver button to change the driver information.

  * Plan To Change Car: Tick this box when the current driver already knows they’ll switch to another vehicle, whether they are awaiting an ordered car, using this one only temporarily, or are leaving the company.

  * Assignment Date: Using the calendar selector, select when the vehicle is available for another driver. If this field is left blank, that indicates the vehicle is currently available, and can be assigned to another driver. If it is populated, the vehicle is not available for another driver until the selected date.

  * Company: Select the company from the drop-down menu. This field only appears in a multi-company database.




#### Create a new driver¶

If a driver is not already in the system, the new driver should first be configured and added to the database. A new driver can be added either from the Driver or Future Driver fields on the vehicle form.

First, type in the name of the new driver in either the Driver or Future Driver field, then click Create and edit…. A Create Driver or Create Future Driver form appears, depending on which field initiated the form.

Both the Create Driver and Create Future Driver forms are identical, and are stored in the **Contacts** app. [Configure the new contact](../../essentials/contacts.html), then click Save & Close.

Nota

Depending on the installed applications, different tabs or fields may be visible on the Create Driver and Create Future Driver forms.

### Vehicle¶

This section captures key physical details of a vehicle. Selecting an existing Model may auto-fill some fields.

Fill in the following fields on the form:

  * Category: Using the drop-down menu, select the vehicle category from the available options. If the **Inventory** app is installed, the category affects any configured [dispatch management system](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dispatch.html).

  * Order Date: Using the calendar selector, select the date the vehicle was ordered. Keeping track of how long vehicles have been in the fleet can help when making decisions on expensive repairs, or help decide when to surrender a vehicle.

  * Registration Date: Using the calendar selector, select the date the vehicle was registered. Many regions require proper registration, so keeping track of registration dates is important.

  * Cancellation Date: Using the calendar selector, select the date the vehicle lease expires, or when the vehicle is no longer part of the fleet (e.g., sold, plates surrendered).

  * Chassis Number: Enter the chassis number in the field. This is known in some countries as the VIN number. Every vehicle has a unique number, so in the event of a theft or accident, a vehicle can be identified with this unique number.

  * Last Odometer: Enter the last known odometer reading in the number field. Using the drop-down menu next to the number field, select whether the odometer reading is in kilometers (km) or miles (mi). Keeping track of a vehicle’s mileage is crucial when determining the value of the vehicle for both tax purposes and resale value.

  * Fleet Manager: Select the fleet manager from the drop-down menu, or type in a new fleet manager, and click either Create or Create and edit….

  * Location: Type in the specific location where the vehicle is typically located in this field. The entry should clearly explain where the vehicle can be found, such as `Main Garage` or `Building 2 Parking Lot`. This is crucial information for companies with many locations where vehicles are stored.




### Tax Info tab¶

Depending on the localization setting for the database, and what additional applications are installed, other fields may be present on the form.

The sections below are default and appear for all vehicles, regardless of other installed applications or localization settings.

#### Fiscalità¶

  * Horsepower Taxation: Enter the amount that is taxed based on the size of the vehicle’s engine. This is determined by local taxes and regulations, and varies depending on the location. It is recommended to check with the accounting department to ensure this value is correct.

  * Disallowed Expenses Rate: Configure the dates and percentages of the vehicle-related costs (fuel, maintenance, depreciation, etc.) that **cannot** be deducted from the company’s taxable income.




#### Contratto¶

  * First Contract Date: Select the start date for the vehicle’s first contract using the calendar selector. Typically this is the day the vehicle is purchased or leased.

  * Catalog Value (VAT Incl.): Enter the MSRP for the vehicle at the time of purchase or lease.

  * Purchase Value: Enter the purchase price or the original value of the lease for the vehicle.

  * Residual Value: Enter the current value of the vehicle.




Nota

The values listed above affect the accounting department. It is recommended to check with the accounting department for more information and/or assistance with these values.

### Model tab¶

If the model for the new vehicle is already configured in the database, the MODEL and ENGINE sections are populated with the corresponding information. If the model is _not_ already in the database and the Model tab needs to be configured, [configure the new vehicle model](models.html#fleet-add-model).

Check the information in the Model tab to ensure it is accurate. For example, the color of the vehicle, or if a trailer hitch is installed, are examples of common information that may need updating.

### Note tab¶

Enter any notes for the vehicle in this section.

Vedi anche

  * [Models & manufacturers](models.html)

  * [Servizi](service.html)

  * [Accidents](accidents.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/fleet/new_vehicle.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](service.html "Servizi") |
  * [precedente](models.html "Models & manufacturers") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Adding vehicles


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