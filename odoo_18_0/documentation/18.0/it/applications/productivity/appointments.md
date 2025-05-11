# Appuntamenti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appointments/create-opps.html "Create opportunities from appointments") |
  * [precedente](calendar/google.html "Google Calendar synchronization") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Appuntamenti



# Appuntamenti¶

Odoo’s **Appointments** app is a self-service scheduling app that simplifies the process of booking meetings, consultations, or services. Integrated with Odoo’s suite of business apps, it allows companies to automate appointment scheduling, reduce manual coordination, and provide a seamless experience for clients. Appointments can be linked to calendars, **CRM** opportunities, employee schedules, and more, making it an ideal tool for service-based businesses seeking efficiency and organization.

## Configurazione¶

The **Appointments** app allows for new appointments to be scheduled based on the availability of users, or the availability of _resources_ , such as meeting rooms or seating areas. To create a new resource, or manage existing resources, navigate to Appointments ‣ Configuration ‣ Resources. This opens a list of the available resources in the database, as well as their individual capacity.

### Risorse¶

Click New to create a new resource. On the blank record, enter a Name for the new resource. In the Capacity field, enter the maximum number of people the resource can accommodate. Then, confirm the Timezone for this resource.

If desired, select one or more Linked Resource from the drop-down. This option designates one or more resources that can be used in combination to handled a bigger demand.

Importante

 _Linked resources_ are only used when using the auto-assign Assignment Method.

Lastly, add a Description for this resource.

Nota

The contents of the Description tab are visible to customers when booking an appointment online.

## Appointment type configuration¶

Before appointments can be scheduled or booked, an appointment type must be created. Navigate to the Appointments app dashboard and click New. On the new blank record, enter an Appointment Title, then set a Duration for this appointment type.

Next, set a Pre-Booking Time. This is the minimum amount of time between when an appointment can be booked and when the appointment can begin. If the Pre-Booking Time is `1` hour, appointments must be booked _at least_ `1` hour in advance.

Example

An appointment type is created for `Tennis Courts`, with a Duration of `1` hour, and a Pre-Booking Time of `1` hour. At `02:00` PM, a customer attempts to book an appointment for the same day at `02:45` pm. The first available time is `04:00` pm.

Select a Scheduling Window:

  * Select Available now to allow customers to book an appointment immediately. Use the Up to X days into the future field to define how far in advance customers can schedule appointments. For example, if `14` is entered, customers cannot book anything more than 14 days from the current date.

  * Select Within a date range to limit bookings to a specific range of dates. After selecting this option, click the From and to fields, and use the calendar pop-up window to customize the date and time range.




Update the Allow Cancelling field to limit the amount of time before an appointment where a customer can cancel. If this setting is enabled, customers are unable to cancel within the designated time frame.

Nota

If a customer does try to cancel within the time frame, they receive an error message with contact information. If the appointment is for a resource, the contact details are for the user that created the appointment type. If the appointment is for a user, the contact details are for the user the appointment is with.

Next, designate whether this appointment type is based on Users or Resources, by selecting the appropriate radio button. If it is based on users, select one or more Users in the drop-down. If it is based on resources, select one or more Resources in the drop-down.

Suggerimento

User-based appointment types can be used for scheduling sales meetings and demos, as well as recruiting interviews.

Resource-based appointment types can be used for scheduling time in specific rooms or locations.

Selecting Resources in the Availability on field reveals the Manage Capacities option. If selected, the appointment limits the number of participants based on the capacity of the resources selected.

Choose an Assignment Method by selecting the appropriate radio button:

>   * Pick User/Resource then Time: customers select from a list of available users/resources, then select an open time slot.
> 
>   * Select Time then User/Resource: customers choose a date and time, then select from the list of available users/resources.
> 
>   * Select Time then auto-assign: customers select a time slot and are automatically assigned a user/resource.
> 
> 


### Schedule tab¶

The Schedule tab is used to outline when this appointment type is to be made available. The settings define the time slots shown on the booking page.

Click Add a line to create a new time frame. Select a day of the week from the Every drop-down menu, then update the times in the From and To fields. Click the __(trash) icon to delete an entry. Multiple entries can be included for a single day.

Suggerimento

If an appointment should not be available at specific times, such as when users are taking lunch, include time slots before and after.

### Options tab¶

The Options tab is used to customize the display options for this appointment, as well as notification settings for customers and users.

The Front-End Display field determines how the appointment is presented on the website to customers. Select the Show Pictures radio button to publish the default pictures of the user or resources for this appointment on the website.

The Timezone and Location fields automatically populate for resource appointments, based on where the resource is located. For user-based appointments, the Location field defaults to an `Online Meeting`, with a Videoconference Link automatically generated. If this should not be an online meeting, select a different option in the Location field.

Tick the Manual Confirmation checkbox to require approval before a meeting is accepted. If this feature is enabled, the appointment time slot is still considered _reserved_ until it is confirmed or rejected. Leave this checkbox blank to automatically accept meetings created from this appointment.

The [Create Opportunities](appointments/create-opps.html) feature adds an opportunity to the **CRM** app for each scheduled appointment, which is assigned to the responsible user. Tick the Create Opportunities checkbox to enable this option.

Importante

This field is only visible if the **CRM** app is installed on the database.

The Reminders field is used to set how customers are to be contacted before the appointment time. Select one or more options from the drop-down, based on the communication method, and the time frame.

Tick the Allow Guests checkbox to grant customers the ability to add additional guests when registering for an appointment.

### Questions tab¶

The Questions tab can be used to prompt customers for additional information while they are booking an appointment. Click Add a line to add a new question.

On the Create Questions pop-up window, enter the Question, then choose an Answer Type.

Tick the Mandatory Answer checkbox to require customers to answer this question before they are allowed to book an appointment. Click Save & New to add another question, or Save & Close when finished.

### Messages tab¶

The Messages tab is used by the business to provide additional information to customers regarding this appointment type.

Importante

The content in the Messages tab is visible to customers and website visitors.

In the Introduction Message field, add a short description of the appointment type. This can include the topic of the appointment, a meeting agenda, or an introduction to the users responsible for the meeting.

The Extra Message on Confirmation is displayed to a customer after they have booked a meeting. Add any additional information here that the customer should be aware of. This can include parking information, last minute rules, or additional instructions.

## Publishing an appointment¶

When an appointment is ready to publish, click the Go to Website smart button at the top of the record. Then, slide the __ Unpublished icon to __ Published.

  * [Create opportunities from appointments](appointments/create-opps.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/productivity/appointments.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appointments/create-opps.html "Create opportunities from appointments") |
  * [precedente](calendar/google.html "Google Calendar synchronization") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Appuntamenti


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions