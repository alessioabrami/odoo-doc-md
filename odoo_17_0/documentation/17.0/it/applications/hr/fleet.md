# Parco veicoli — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fleet/models.html "Vehicle models") |
  * [precedente](frontdesk/visitors.html "Visitatori") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Parco veicoli



# Parco veicoli¶

This document outlines the configurations and settings for the _Fleet_ application, for both settings and manufacturers.

## Impostazioni¶

To access the settings menu, go to Fleet app ‣ Configuration ‣ Settings. Only two settings need configuration: End Date Contract Alert and New Vehicle Request.

### Avviso data di fine contratto¶

The End Date Contract Alert field how many days before the end of a vehicle contract an alert should be sent. The responsible people receive an email informing them a vehicle contract is about to expire in the number of days defined in this field.

Nota

To determine who the responsible person is for a contract, open an individual contract. The person listed as Responsible under the Contract Information section of the contract is the person who will receive the alert.

To access all contracts, navigate to Fleet app ‣ Fleet ‣ Contracts and all contracts appear in the list. Click on a Contract to view it.

An individual contract can also be found by navigating to Fleet app ‣ Fleet ‣ Fleet and clicking on an individual vehicle. On the vehicle form, click the Contracts smart button at the top of the page. The contract(s) associated with this vehicle only appears in the list. Click on an individual contract to open it. The Responsible person is listed on the contract.

### New Vehicle Request¶

The New Vehicle Request field sets a limit on how many new vehicles are requested based on fleet availability. An employee filling out the salary configurator form (after being offered a position), will _not_ be able to request a new car if the number of existing cars is greater than the number specified in the New Vehicle Request field. Enter the specific number limit for existing available cars in this field.

Example

If the New Vehicle Request limit is set to 20 vehicles, and there are 25 vehicles available, an employee would not be able to request a new vehicle. If there are only 10 cars available, then the employee would be able to request a new vehicle.

## Produttori¶

Odoo _Fleet_ comes pre-configured with sixty-six commonly used car and bicycle manufacturers in the database, along with their logos. To view the pre-loaded manufacturers, go to Fleet app ‣ Configuration ‣ Manufacturers.

The manufacturers appear in an alphabetical list. Each manufacturer’s card lists how many specific models are configured for each particular manufacturer. Odoo comes with forty-six preconfigured [models](fleet/models.html) from four major auto manufacturers, and one major bicycle manufacturer: Audi, BMW, Mercedes, Opel (cars), and Eddy Merckx (bicycle).

### Add a manufacturer¶

To add a new manufacturer to the database, click Create. A manufacturer form will load. Only two pieces of information are needed, the Name of the manufacturer, and the logo. Type the name of the manufacturer in the name field, and select an image to upload for the logo. When the information is entered, click Save.

Vedi anche

  * [Vehicle models](fleet/models.html)

  * [New vehicles](fleet/new_vehicle.html)

  * [Servizi](fleet/service.html)

  * [Accidents](fleet/accidents.html)




  * [Vehicle models](fleet/models.html)
  * [New vehicles](fleet/new_vehicle.html)
  * [Servizi](fleet/service.html)
  * [Accidents](fleet/accidents.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/fleet.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fleet/models.html "Vehicle models") |
  * [precedente](frontdesk/visitors.html "Visitatori") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Parco veicoli


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