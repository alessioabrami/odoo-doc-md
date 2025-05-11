# Vehicle models — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](new_vehicle.html "New vehicles") |
  * [precedente](../fleet.html "Parco veicoli") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Vehicle models



# Vehicle models¶

When adding a vehicle to the fleet, specify the vehicle model to maintain updated records, which keeps track of specific details, like maintenance schedules and parts compatibility.

Odoo comes with preconfigured car models from four major auto manufacturers: Audi, BMW, Mercedes, and Opel.

If a new vehicle model joins the fleet, and it is not one of the preconfigured models from these manufacturers, the model (and/or manufacturer) **must** be added to the database.

## Preconfigured models¶

The following models are preconfigured in Odoo, and do not need to be added to the database:

AUDI | BMW | Mercedes | Opel  
---|---|---|---  
A1 | Serie 1 | Class A | Agilia  
A3 | Serie 3 | Class B | Ampera  
A4 | Serie 5 | Class C | Antara  
A5 | Serie 6 | Class CL | Astra  
A6 | Serie 7 | Class CLS | AstraGTC  
A7 | Serie Hybrid | Class E | Combo Tour  
A8 | Serie M | Class GL | Corsa  
3° trimestre | Serie X | Class GLK | Insignia  
Q5 | Serie Z4 | Class M | Meriva  
Q7 |  | Class R | Mokka  
TT |  | Class S | Zafira  
|  | Class SLK | Zafira Tourer  
|  | Class SLS |   
  
## Add a new model¶

To add a new vehicle model, navigate to Fleet app ‣ Configuration ‣ Models: Models. Click New, and in a new vehicle model form, enter the following information on the form.

Nota

Be advised, some fields are specific to Belgian based companies, so not all fields or sections may be visible depending on the location of the company.

  * Model name: enter the model name in the field.

  * Manufacturer: select the manufacturer from the drop-down menu. If the manufacturer is not configured, type in the manufacturer, and click Create or Create and edit...

Nota

When the manufacturer is selected, if it is one of the default manufacturers in _Odoo_ , the logo for the manufacturer automatically loads in the image box in the top-right corner.

  * Vehicle Type: select one of two preconfigured vehicle types, either Car or Bike, from the drop-down menu. The vehicle types are hardcoded in Odoo, and are integrated with the _Payroll_ application, since vehicles can be part of an employee’s benefits. Adding additional vehicle types is _not_ possible as it affects payroll.

  * Category: select a category for the vehicle from the drop-down menu. To create a new category, type in the category and then click Create (new category).




### Information tab¶

In the Information tab, specify details about the car model, such as the car size, passenger capacity, cost settings (applicable to the Belgium localization only), and engine information.

#### Model section¶

  * Seats Number: enter how many passengers the vehicle can accommodate.

  * Doors Number: enter the number of doors the vehicle has.

  * Color: enter the color of the vehicle.

  * Model Year: enter the year the vehicle was manufactured.

  * Trailer Hitch: tick this checkbox if the vehicle has a trailer hitch installed.




#### Salary section¶

Nota

The Salary section **only** appears for Belgian-based companies, and **only** if the company has their localization setting set to Belgium. The cost values are all _monthly_ , with the exception of the Catalog Value (VAT Incl.).

  * Can be requested: tick this checkbox if employees can request this model vehicle, if a vehicle is part of their employee contract.

  * Catalog Value (VAT Incl.): enter the MSRP for the vehicle at the time of purchase or lease.

  * C02 fee: represents the carbon dioxide emission fee paid to the Belgian government. This value is automatically calculated, based on Belgian laws and regulations, and **cannot** be modified. The value is based on the figure entered in the CO2 Emissions field (in the Engine section of the Information tab) on the vehicle form.




Importante

Modifying the CO2 Emissions field adjusts the value in the CO2 fee field.

  * Cost (Depreciated): enter the monthly vehicle cost, which appears in the salary configurator for future employees. This value impacts the gross and net salary of the employee assigned to the vehicle. This figure is depreciated over time, according to local tax laws. The Cost (Depreciated) does **not** depreciate automatically on the _vehicle model_ , it only depreciates based on the _contract_ linked to a specific vehicle.

  * Total Cost (Depreciated): this value is the combination of the Cost (Depreciated) and the C02 fee fields. It also depreciated over time.




#### Motore¶

  * Fuel Type: select the type of fuel the vehicle uses from the drop-down menu. The options are Diesel, Gasoline, Hybrid Diesel, Hybrid Gasoline, Plug-in Hybrid Diesel, Plug-in Hybrid Gasoline, CNG, LPG, Hydrogen, or Electric.

  * CO2 Emissions: enter the average carbon dioxide emissions the vehicle produces in grams per kilometer (g/km). This information is provided by the car manufacturer.

  * CO2 Standard: enter the standard amount of carbon dioxide in grams per kilometer (g/km) for a similar-sized vehicle.

  * Transmission: select Manual or Automatic transmission from the drop-down menu.

  * Power: if the vehicle is electric or hybrid, enter the power the vehicle uses in kilowatts (kW).

  * Horsepower: enter the vehicle’s horsepower in this field.

  * Horsepower Taxation: enter the amount that is taxed, based on the size of the vehicle’s engine. This is determined by local taxes and regulations, and varies depending on the location. It is recommended to check with the accounting department to ensure this value is correct.

  * Tax Deduction: this field auto-populates, according to the engine specifications, and **cannot** be modified. The percentage is based on the localization settings and local tax laws.




### Vendors tab¶

Specify the vendors a vehicle can be purchased from in this tab. With proper setup, requests for quotations for vehicles can be easily created through Odoo’s _Purchase_ app.

To add a vendor, click Add, which opens an Add: Vendors pop-up window, with a list of all the vendors currently in the database. Add a vendor by ticking the checkbox next to the vendor name, then click Select. There is no limit to the number of vendors that can be added to this list.

If a vendor is not in the database, add a vendor by clicking New in the bottom-left of the Add: Vendors pop-up window. In the Create Vendors form that appears, enter the necessary information, then click Save & Close to add the vendor, or click Save & New to add the current vendor and create another new vendor.

## Model category¶

To best organize a fleet, it is recommended to have vehicle models housed under a specific category, to easily see what kinds of vehicles are in the fleet. Model categories are set on the vehicle model form.

Odoo does **not** come with any models preconfigured; all models **must** be added.

To view any models currently set up in the database, navigate to Fleet app ‣ Configuration ‣ Models: Categories. All models are displayed in a list view.

### Add a new model category¶

To add a new category, click the New button in the top-left corner of the Categories page. A new entry line appears at the bottom of the list. Type in the new category, then either click Save, or click anywhere on the screen, to save the entry.

To reorganize how the categories appear in the list, click on the __(draggable) icon to the left of any desired category name, and drag the line to the desired position.

The order of the list does not affect the database in any way. However, it may be preferable to view the vehicle categories in a specific order, for example, by size, or the numbers of passengers the vehicle can carry.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/fleet/models.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](new_vehicle.html "New vehicles") |
  * [precedente](../fleet.html "Parco veicoli") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Parco veicoli](../fleet.html) »
  * Vehicle models


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
  *[FBM]: Fulfilled By Merchant
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