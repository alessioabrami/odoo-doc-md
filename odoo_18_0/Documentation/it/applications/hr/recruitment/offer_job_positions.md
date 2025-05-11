# Offer job positions — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](refuse_applicant.html "Refuse applicants") |
  * [precedente](schedule_interviews.html "Schedule interviews") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Offer job positions



# Offer job positions¶

Once an applicant has successfully passed the various interview stages, the recruitment team is ready to send an offer for employment. The next step is to send the applicant a contract.

Vedi anche

Refer to the [recruitment](../recruitment.html) documentation for details on the various stages of the recruitment process.

## Contract proposal¶

When an offer is ready to be sent, first open the applicant’s card by navigating to the Recruitment app, and clicking on the desired job position card.

From the resulting Job Positions Kanban view, the corresponding applicant card can be dragged-and-dropped to the Contract Proposal stage. Or, click into the desired applicant’s card, and click the Contract Proposal stage, located in the status bar in the top-right of the applicant’s form.

The next step is to send an offer to the applicant. Start by selecting the desired applicant’s card to open their applicant form.

On the applicant’s form, click the Generate Offer button. A Generate a Simulation Link pop-up window appears.

Most fields are pre-populated with information from the job position. If any necessary fields are blank, or if any information needs to be updated, enter, or update, the relevant information in the corresponding fields.

Nota

Depending on the localization setting for the company, and which applications are installed, some fields may not appear in the Generate a Simulation Link pop-up window.

For example, if the _Fleet_ application is **not** installed, any fields related to vehicles do **not** appear.

### Universal fields¶

The following fields appear in the Generate a Simulation Link pop-up window, regardless of the localization.

  * Contract Template: the template currently being used to populate the Generate a Simulation Link pop-up window. Use the drop-down menu to select a different Contract Template, if desired.

Nota

To modify the template, hover over the current template name, and click the __ Internal link icon that appears to the right of the field. Make any desired changes, then click Save & Close.

  * Job Position: the name of the Job Position being offered to the applicant. The selections available in the drop-down menu correspond to the job position configured on the main _Recruitment_ dashboard.

  * Job Title: the selected Job Position populates this field, by default. The title can be modified to suit the specific applicant’s position and provide more details.

Example

An applicant is offered a marketing manager job at a shoe company, specifically for the children’s line.

The Job Position selected from the drop-down menu is `Marketing Manager`, and the Job Title is modified for their specific responsibilities, `Marketing Manager: Children's Shoes`.

  * Department: the department the job position falls under.

  * Contract Start Date: the date the contract takes effect. The default date is the current date. To modify the date, click on the displayed date to reveal a calendar popover window. Navigate to the desired month, then click the day to select the date.

  * Yearly Cost: the annual salary being offered.

  * Link Expiration Date: the number of days the job offer is valid. The default expiration date is `30` days. Modify the expiration date, if desired.




### Send offer¶

Once the Generate a Simulation Link pop-up window is complete, click Send By Email to reveal an email pop-up window.

Importante

If the applicant does not have an email address listed on their applicant card, a warning appears in a red box at the bottom of the Generate a Simulation Link pop-up window, stating: The applicant does not have a valid email set. The Offer Link won’t be able to be completed. Click Discard, then enter an email on the applicant’s card. Once an email is entered, click the Generate Offer button, and the email pop-up window loads again.

The default Recruitment: Your Salary Package email template is used (set in the Load template field), and the Recipients, Subject, and email body are pre-populated based on the email template.

If any attachments need to be added, click the __ Attachments button, and a file explorer window appears. Navigate to the desired file, then click Open to attach it to the email. The attachment loads, and is listed above the __ Attachments button.

Once the email is ready to send, click Send. The email pop-up window closes, and an Offers smart button appears at the top of the applicant’s card.

Nota

To send an offer, ensure the _Sign_ application is installed. This is necessary, so the offer can be sent to the applicant by the recruiter, and they can actually sign the offer. The applicant does **not** need any software installed to sign the offer.

### Configure your package¶

If applicable, the applicant can modify their salary package. This option is not available for all localizations. Depending on where the company is located, this option may not be available.

The email template includes a Configure your package button. This link takes the applicant to a webpage, where they can modify the proposed salary package, and enter their personal information.

Once the applicant is hired, the personal information entered on the webpage is imported to their employee record, when created.

Once all the information is completed, the applicant can then accept the offer by clicking the Review Contract & Sign button to accept the contract, and sign it using the _Sign_ application.

## Contract signed¶

Once the applicant has accepted the offer and signed the contract, the next step is to move the applicant to the Contract Signed stage. This stage is folded in the Kanban view, by default.

To move the applicant to that stage, drag-and-drop the applicant’s card to the Contract Signed stage. If the stage is not visible, click the __(ellipsis) button to the right of Contract Proposal on the applicant’s form, and click Contract Signed from the resulting drop-down menu.

Once the applicant is moved to the Contract Signed stage, a green HIRED banner appears in the top-right of the applicant’s card and form.

## Crea dipendente¶

Once the applicant has been hired, the next step is to create their employee record. Click the Create Employee button in the top-left corner of the hired applicant’s form.

An employee form appears, with information from the applicant’s card, and the employee contract.

Fill out the rest of the employee form. For detailed information on the fields, refer to the [Nuovi dipendenti](../employees/new_employee.html) documentation.

Once completed, the employee record is saved in the _Employees_ app.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/recruitment/offer_job_positions.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](refuse_applicant.html "Refuse applicants") |
  * [precedente](schedule_interviews.html "Schedule interviews") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Offer job positions


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