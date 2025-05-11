# Shop Floor time tracking — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../subcontracting.html "Subappalto") |
  * [precedente](shop_floor_overview.html "Shop Floor overview") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Linea di produzione](../shop_floor.html) »
  * Shop Floor time tracking



# Shop Floor time tracking¶

By signing in to the Odoo _Shop Floor_ module as _operators_ , employees are able to track the amount of time they spend working on each work order.

Odoo tracks the time it takes to complete each work order, as well as the time each operator spends on each work order.

## Operator sign in¶

To sign in to the _Shop Floor_ module as an operator, sign in to the Odoo database, and open the Shop Floor module. The employee profile that is signed in to the database is automatically signed in as an operator.

All active operators are listed in the operator panel on the left side of the module. The panel can be opened or collapsed by clicking the show/hide panel (white square with black column on left side) button, located in the top-left corner of the module.

To sign in to _Shop Floor_ as a different employee, click the \+ Add Operator button at the bottom of the panel. Doing so opens the Select Employee pop-up window, which lists every employee that is able to sign in to the module.

Click on a specific employee to sign in using their profile. If no PIN code is required to sign in as that employee, the profile will be signed in automatically.

If a PIN code is required, a Password? pop-up window appears, showing a number pad, from which the code can be entered. Enter the code using the number pad, and click Confirm to sign in to the _Shop Floor_ module.

Nota

A PIN code can be set for each employee, which must be entered each time they sign in to the _Shop Floor_ module, check in or out in the _Kiosk Mode_ of the _Attendances_ application, or sign in as a cashier in the _Point of Sale_ application.

To set an employee PIN, navigate to the Employees app, and select a specific employee. At the bottom of the employee’s form, click on the HR Settings tab, and enter a numerical code in the PIN Code field.

Once an employee is signed in to the module, their name appears in the operator panel, along with every other employee that has signed in. While the panel can list multiple employees, only one employee can be active at any given time, on a single instance of the _Shop Floor_ module.

Click on an employee’s name to make their profile active. The active employee appears highlighted in blue, while employees that are signed in, but not active, have their names faded out.

To sign out a specific employee from the module, click the X (remove) button next to their name, in the operator panel.

## Track work order duration¶

To track time spent working on a work order, begin by selecting the employee working on it from the operator panel.

Next, navigate to the page for the work center where the work order is scheduled to be carried out. This can be done by selecting the work center from the top navigation in the _Shop Floor_ module, or by clicking the name of the work center on the card for the manufacturing order (MO) that the work order is a part of.

On the page for the work center, find the card for the work order. Once work begins, click the header of the work order card to start timing the duration it takes to complete. This duration is displayed by a timer on the header of the work order card, which tracks the collective time spent working on the work order, by all employees.

In addition, the reference number of the work order appears in the operator panel, under the name of the employee working on it, along with a second timer, which tracks the amount of time the employee has spent on the work order individually. This timer only reflects work done during the current session, even if the employee has previously worked on the work order.

Employees are able to work on multiple work orders simultaneously, and track their time for each. The reference number for each work order being worked on appears below the employee’s name, along with a timer.

To pause the timer on the work order card, and remove the work order from below the employee’s name on the operator panel, click the header a second time.

Once the work order is completed, click the Mark as Done button at the bottom of the work order card, which causes the card to fade away. If the timer is still active, it stops once the card disappears completely.

## View work order duration¶

To view the duration of a work order, navigate to Manufacturing app ‣ Operations ‣ Manufacturing Orders, and select an MO.

To view and select MOs that have been completed and marked as _Done_ , remove the To Do filter from the Search… bar, by clicking on the X (close) button on the right side of the filter.

On the page for the MO, click on the Work Orders tab to see a list of all work orders included in the MO. The time it took to complete each work order is displayed in the Real Duration column of the tab.

The _Real Duration_ represents the total time spent working on the work order by all workers who worked on it. It includes time tracked in the _Shop Floor_ module, as well as time tracked on the Work Orders tab of the MO itself.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/shop_floor/shop_floor_tracking.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../subcontracting.html "Subappalto") |
  * [precedente](shop_floor_overview.html "Shop Floor overview") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Linea di produzione](../shop_floor.html) »
  * Shop Floor time tracking


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
  *[SOs]: Sales Order
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
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order