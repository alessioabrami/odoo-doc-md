# Scrap during manufacturing — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manufacturing_backorders.html "Manufacturing backorders") |
  * [precedente](work_center_time_off.html "Work center time off") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Scrap during manufacturing



# Scrap during manufacturing¶

During the manufacturing process, the need to scrap manufacturing components or finished products may arise. This can be necessary if a component or product is damaged, or unusable for any other reason.

By default, scrapping a component or finished product removes it from physical inventory and places it in a virtual location titled _Virtual Locations/Scrap_. A virtual location is **not** a physical space, but rather a designation in Odoo that is used to track items that are no longer in physical inventory.

Vedi anche

For more information, see the documentation about the different types of [locations](../../inventory/warehouses_storage/inventory_management.html).

Components can be scrapped from both the _Manufacturing_ app and the _Shop Floor_ module, before the associated manufacturing order (MO) is closed. Finished products can only be scrapped from the _Manufacturing_ app, and only after closing the associated MO.

Suggerimento

Scrap orders can be viewed by navigating to Inventory ‣ Operations ‣ Scrap. Each scrap order shows the date and time the order was created, along with the product and quantity that was scrapped.

To view the total quantity of each item scrapped, navigate to Inventory ‣ Configuration ‣ Locations, then remove the Internal filter from the Search… bar to display all virtual locations. From the list, select the Virtual Locations/Scrap location.

## Scrap pop-up window¶

Scrapping components and finished products is done through the Scrap pop-up window. The pop-up window can be accessed from an MO in the backend, or the _Shop Floor_ module.

### Scrap component from Manufacturing¶

To scrap a component from an MO, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders, and then select an MO. At the top of the MO, click the Scrap button to open the Scrap pop-up window.

### Scrap finished product from Manufacturing¶

To scrap a finished product from an MO, begin by navigating to Manufacturing ‣ Operations ‣ Manufacturing Orders. Select an open MO, and then click the Produce All button to close it.

To select an MO that has already been closed, navigate to Manufacturing ‣ Operations ‣ Manufacturing Orders, remove the To Do filter from the Search… bar, and then select the desired MO.

Once closed, click the Scrap button at the top of the MO to open the Scrap pop-up window.

### Scrap component from Shop Floor¶

To scrap a component from the _Shop Floor_ module, begin by navigating to Shop Floor. Then, either click the ⋮ (three vertical dots) button on an MO card, or select a work center from the top navigation, and click the ⋮ (three vertical dots) button on a work order card.

Either method opens the What do you want to do? pop-up window. Click the Scrap button on the window to open the Scrap pop-up window.

## Scrap pop-up window¶

After opening the scrap pop-up window using one of the methods detailed above, select the component or finished product being scrapped, from the Product drop-down menu.

In the Quantity field, enter the quantity being scrapped.

By default, the Source Location field is set to the warehouse’s pre-production location, while the Scrap Location field is set to the Virtual Locations/Scrap location. If either the source or scrap location should be changed, select a different location from their respective drop-down menus.

Enable the Replenish Scrapped Quantities checkbox if a picking order should be created to replace the scrapped component(s) upon confirmation of the scrap order. This option should only be enabled for warehouses with [two-step](../basic_setup/two_step_manufacturing.html) or [three-step](../basic_setup/three_step_manufacturing.html) manufacturing enabled, since components are not picked as part of the [one-step](../basic_setup/one_step_manufacturing.html) manufacturing process.

Click the Scrap button to scrap the selected component. After one or more scrap orders have been created, a Scraps smart button appears at the top of the screen. Click it to view a list of all scrap orders for the MO.

If a picking order was automatically created to replenish the scrapped components, it can be accessed by opening the Inventory app, clicking the # To Process button on the Pick Components card, and selecting the order.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/workflows/scrap_manufacturing.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manufacturing_backorders.html "Manufacturing backorders") |
  * [precedente](work_center_time_off.html "Work center time off") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Scrap during manufacturing


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
  *[API]: Application programming interface
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: sales orders
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: manufacturing orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders