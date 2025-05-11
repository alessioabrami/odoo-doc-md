# Visitatori — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../fleet.html "Parco veicoli") |
  * [precedente](../frontdesk.html "Reception") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Reception](../frontdesk.html) »
  * Visitatori



# Visitatori¶

In the Odoo **Frontdesk** application, a _visitor_ refers to any non-employee (e.g., repair person, job candidate, auditor, etc.). Visitor arrivals and departures can be logged for security purposes, ensuring an accurate record of who is on the premises.

## Visitor list¶

To access a complete list of checked-in visitors, navigate to Frontdesk app ‣ Visitors.

Nota

By default, the Planned or Checked-In and Today filters appear in the Search… bar.

All visitors are presented in a list view, with the following details that were entered upon check in:

  * Name: the guest’s name.

  * Visitor Company: the company the guest represents.

  * Phone: the guest’s phone number.

  * Drinks*: the drink the guest requested.

  * Host: who the guest is waiting to see.

  * CheckIn: the date and time the guest checked in.

  * Checkout*: the date and time the guest checked out. In the default view, only guests with a Checked-In or Planned status are visible. Guests with check-out times are only visible if the Today filter is removed.

  * Duration: the amount of time the guest has been checked in for.

  * Station: the location of where the guest checked in.

  * Status: the status of the guest. The options are Checked-In, Planned, Checked-Out, or Cancelled.

  * Email*: the guest’s email address.

  * Company*: the company the guest is there to visit. This field is only available if in a multi-company database.




* These fields are not visible in the default Visitor list. These must be enabled using the __(adjust settings) icon in the top-right corner of the list.

To the far-right of the titled columns on the Visitors page, there is an untitled column, where a guest’s status can be updated.

When a guest leaves, click the available Check out button to update the guest’s record, and log the date and time they left.

If a scheduled guest arrives, and they did not check in using a **Frontdesk** kiosk, they can be checked in from this list, by clicking the available Check in button to log the date and time they arrived.

Beside the untitled status column, a Drink Served button appears, but only if that particular visitor requested a drink.

When their drink has been served, click the Drink Served button to indicate the drink has been delivered to the guest. Once clicked, that button disappears.

On the far-right of the line, a Print Badge button appears for _planned_ visitors **only**. Click this button to download a PDF file of the visitor’s badge. The badge displays the date and time the visitor checked in, the visitor’s name and company, who they are visiting, and the logo of the company they are visiting.

Nota

The PDF badge can be printed onto adhesive labels for the visitor to wear, or onto paper that can be placed into a plastic badge holder.

If any column is not visible, or if a visible column is preferred to be hidden, click the __(adjust settings) icon, located at the end of the top line. Doing so, reveals a drop-down menu of column options to enable or disable. A __(check) icon indicates the column is visible.

## Planned visitors¶

When guests are expected, such as job candidates, government officials, or new suppliers, it can be helpful to enter the visitor information in advance. When the visitors arrive, they can utilize the _Quick Check In_ option on the kiosk, rather than entering all their information manually upon arrival.

Enter expected guest information in advance by creating a planned guest in the **Frontdesk** app.

To create a planned guest, navigate to Frontdesk app ‣ Visitors, and click New. Then, enter the same information as any other visitor on the guest form that appears. The only required fields are the visitor’s Name and the Station at which they are expected to arrive.

Importante

If a guest is planned in advance, they must be checked in from the list on the Visitors page in the **Frontdesk** application (Frontdesk app ‣ Visitors). If a planned guest checks in using a kiosk, they are checked in separately from their planned visitor entry, and their planned visitor entry remains listed as Planned.

The Planned status of a planned guest **only** changes to Checked-In when they are checked in _inside_ the application’s Visitors list.

If a guest does check in using a kiosk, ensure all records are current, and the list of guests that are currently on-site is correct. Be sure to check in and/or check out the correct entries, so the visitors list correctly reflects who is currently on the premises.

Ensure planned guests are informed that they should **not** check in using the kiosk if they are listed as a planned guest in advance.

## Visitor flow¶

### Visitor check in¶

When a visitor arrives at a facility, they approach a [Frontdesk kiosk](../frontdesk.html#frontdesk-kiosk), and click Check in. The information requested from the visitor is what was configured for that specific **Frontdesk** station. If any information is required, the field displays a red asterisk (*). The visitor **must** enter the required information in order to check in.

Once all the information is entered, the visitor taps the Check In button.

Nota

At any point in the check-in process, if ten seconds pass with no selection, the kiosk returns to the main welcome screen.

#### Planned visitor check in¶

When a planned visitor arrives at a facility, they first approach a [Frontdesk kiosk](../frontdesk.html#frontdesk-kiosk). If there are planned visitors for that day, a Quick Check In panel appears on the right-side of the kiosk, asking Are you one of these people? Beneath the question is a list of all visitors schedule to arrive that day.

Click on the corresponding name in the list to check-in.

### Bevande¶

If drinks were configured for the station, after tapping Check In, a registration confirmation screen loads, along with the question: Do you want something to drink?

The visitor can tap either Yes, please, or No, thank you.

If they select Yes, please, a drink selection screen appears, and the preconfigured options are listed. The visitor then taps the desired selection, or, if they do not want anything, they can tap the Nothing, thanks button at the bottom of the screen.

If a drink selection was made, a Thank you for registering! Your drink is on the way. message appears.

### Notifiche¶

Once the visitor has checked in, the person they are visiting, and any other users who were configured to be notified when check-ins occur at the kiosk, are notified. The notification is either by email, SMS message, a _Discuss_ chat, or any combination of those three options.

If the visitor requested a drink, the users configured as the People to Notify on the drink form are notified, via the _Discuss_ application. The message that appears is: (Visitor Name) just checked-in. They requested (Drink Name).

Once the drink has been delivered to the guest, the person who delivered the drink is responsible for marking the drink as delivered.

To mark a drink as delivered, navigate to Frontdesk app ‣ Stations, and choose the desired station card displaying (#) Drinks to serve.

This opens a list of all the visitors checked in at that station, and are waiting for a drink. Click the Drink Served button at the end of the line for the visitor who was served. Once they are marked as having their drink served, the visitor disappears from the list.

### Check-out¶

Once the visitor has completed their business, and has left the premises, it is important to check them out for accurate record keeping.

To check visitors out properly, navigate to Frontdesk app ‣ Stations, and choose the desired station card displaying (#) Drinks to serve. Doing so opens a list of all the visitors who are currently checked-in at that station.

Click the Check out button near the end of the line for the visitor who left. Once they are marked as checked-out, the visitor disappears from the list.

Importante

Visitors do **not** check themselves out when they leave. It is important for **Frontdesk** users to check out visitors for accurate record keeping.

Always have an accurate list of who is on the premises at any given time. This is important for security purposes, and in the case of an emergency.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/frontdesk/visitors.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../fleet.html "Parco veicoli") |
  * [precedente](../frontdesk.html "Reception") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Reception](../frontdesk.html) »
  * Visitatori


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