# Certificazioni — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](equipment.html "Attrezzatura") |
  * [precedente](departments.html "Reparti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Certificazioni



# Certificazioni¶

When jobs require specific knowledge, it is necessary to track employee certifications to ensure the necessary knowledge and certifications are in place.

When jobs require specific knowledge, track employee certifications (e.g., classes, tests, seminars) to verify required skills. Odoo accepts any certification type without restriction.

Importante

To add certifications to an employee profile, and to access the _Employee Certifications_ report, the **Surveys** app **must** be installed.

## View certifications¶

To view a full list of all employee certifications, navigate to Employees app ‣ Reporting ‣ Certifications.

All certifications appear in a list view, grouped by employee. Each certification entry displays the following:

  * Employee: the employee’s name, along with their avatar image.

  * Name: the title of the certification.

  * Validity Start: when the employee received the certification.

  * Validity End: when the certification expires.

  * Certification: the corresponding course in the **Surveys** app that was completed by the employee, if applicable.




The entries are also color-coded. Current certifications that are still valid appear in black, expired certifications appear in red, and certifications that are going to expire within the next 90 days appear in orange.

Importante

**Only** certification records with the _Display Type_ set to _Certification_ on their certification form appear on the Employee Certifications report. All other certifications appear in the resume section of the [employee form](new_employee.html#employees-resume).

### View certifications by expiration status¶

When managing a large number of employees with a variety of certifications, it can be difficult to determine which employees need to keep necessary certifications current in the default list view. In this scenario, it is beneficial to view the certifications by expiration status.

To do so, navigate to Employees app ‣ Reporting ‣ Certifications. Next, click the __(Toggle Search Panel) icon in the search bar, then click Add Custom Group __, revealing a drop-down menu. Click Expiration Status, then click away from the drop-down menu to close it.

After doing so, all the certifications are organized by status, starting with Expired certifications, then certifications that are Expiring soon (within the next 90 days), and lastly, certifications that are still Valid.

Filter certifications by expiration status to identify certifications expiring soon, and identify employees who must renew.

## Log a certification¶

To log a certification for an employee, navigate to Employees app ‣ Reporting ‣ Certifications. Click New, and a blank certification form loads. Enter the following information on the form:

  * Title: Enter a short description for the certification in this field.

  * Employee: Using the drop-down menu, select the employee who received the certification.

  * Type: Using the drop-down menu, select the type of certification received. This field determines where on the employee’s resume the certification appears. To create a new Type, enter the type in the field, then click Create [type].

The default options are:

    * Experience: Select this option to have the certification appear in the _Experience_ section of the _Resume_ tab on the [employee form](new_employee.html). Experience entries are typically previous jobs or internships.

    * Education: Select this option to have the certification appear in the _Education_ section of the _Resume_ tab on the [employee form](new_employee.html).

    * Social Media: Select this option to have the certification appear in the _Social Media_ section of the _Resume_ tab on the [employee form](new_employee.html). Social Media entries typically relate to certifications relating to digital marketing, social media management, and specific trainings from social media platforms.

    * Internal Certification: Select this option to have the certification appear in the _Internal Certification_ section of the _Resume_ tab on the [employee form](new_employee.html). Internal certifications entries are tied to courses, training, or programs created by the company, that once completed, have a certification associated with it.

    * Completed Internal Training: Select this option to have the certification appear in the _Completed Internal Training_ section of the _Resume_ tab on the [employee form](new_employee.html). Completed internal training entries are typically associated with trainings created by the company, for company-specific processes. These do not result in any certifications, but are logged on the employee profile to indicate completed training.

  * Display Type: Select the visibility of the certification in this field. The default options are:

    * Classic: Select this option to have the certification appear in the _Resume_ section of the employee form, and **not** appear on the _Employee Certifications_ report.

    * Certification: select this option to have the certification appear in the _Resume_ section of the employee form, **and** appear on the _Employee Certifications_ report. Once this is selected, a Certification field appears beneath the Display Type field. Using the drop-down menu, select the corresponding **Surveys** app certification the employee took. This field **only** appears if the **Surveys** app is installed.

    * Course: Select this option to have the certification appear in the _Resume_ section of the employee form, and **not** appear on the _Employee Certifications_ report. Once this option is selected, a Course field appears beneath the Display Type field. Using the drop-down menu, select the corresponding **eLearning** course the employee took. This field **only** appears if the **eLearning** app is installed.

  * Description: Enter a description for the certification in this field.

  * Duration: Click into the first field, and a calendar pop-over window appears. Click on the start and end dates for the certification validity period. When the correct dates are selected, click __ Apply, and both fields are populated.




Nota

Once a certification is logged for an employee, a new certification of the _same type_ (i.e. Education or Internal Certification) can be added directly from the employee form, instead of the Employee Certifications dashboard.

In the main **Employees** app dashboard, click on an employee profile to open their employee form. In the RESUME tab, click the ADD button at the end of the corresponding certification line.

This ADD button **only** appears on employee profiles that already have a certification.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/employees/certifications.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](equipment.html "Attrezzatura") |
  * [precedente](departments.html "Reparti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Dipendenti](../employees.html) »
  * Certificazioni


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record