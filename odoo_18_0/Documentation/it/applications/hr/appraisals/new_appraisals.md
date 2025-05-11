# Conduct appraisals — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](goals.html "Obiettivi") |
  * [precedente](../appraisals.html "Valutazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Conduct appraisals



# Conduct appraisals¶

This guide explains the end-to-end appraisal workflow in Odoo, from creation to final rating, showing how managers and employees collaborate at each stage.

  * Employee self-assessment: The employee completes the Employee’s Feedback template and updates their skills. Responses remain hidden until the employee sets the form to _Visible to Manager_.

  * Manager feedback: While the employee works on their section, the manager reviews goals, gathers peer input if needed, and fills out the _Manager’s Feedback_ template. Feedback can remain hidden until the appraisal meeting.

  * Appraisal review: Manager and employee meet to discuss both feedback sections, validate skill changes, and agree on next steps. The meeting can be scheduled directly from the appraisal or the calendar.

  * Completion and rating: After the discussion, the manager assigns a final rating, adds any private notes, and marks the appraisal Done. The record then locks unless it is reopened for further edits.




Throughout the process, optional actions, such as requesting peer feedback or logging private manager notes, enhance the appraisal’s accuracy and relevance.

## Employee self-assessment¶

Once an appraisal is confirmed, the employee is required to fill out the self-assessment.

Nota

Only confirmed appraisals can be worked on. If an appraisal is _not_ confirmed, the fields on the appraisal form cannot be edited, and feedback cannot be recorded.

After the employee receives a notification via email that an appraisal is confirmed and scheduled, they are requested to fill out their half of the default appraisal template, and update any skills.

Employee’s can click on the link in the confirmation email to navigate to the appraisal, or they can open their appraisal in the **Appraisals** app. To do this, open the **Appraisals** app, then click on the appraisal card.

The Employee’s Feedback half of the template includes the following sections: My work, My future, and My feelings. Each of these sections consists of several questions for the employee to answer, allowing the employee to perform a self-assessment, and provide feedback on how they feel about the company and their role.

### Employee skills¶

After completing the Employee’s Feedback section in the Appraisal tab, the employee next updates their skills in the Skills tab.

Any skills that were present on the employee’s record when the appraisal was confirmed, appear in this tab. If a Skill Level has changed since the last appraisal, the level must be updated.

Nota

The Skills tab does not appear on the appraisal until the appraisal is confirmed.

Click on the Skill Level for the skill that has changed, revealing a drop-down of all available levels. Click on the new level for the skill. Once selected, the Progress field updates accordingly. Next, click into the Justification field for the skill, and enter any relevant details explaining the change. This field is not necessary, but may aid management when reviewing the employee’s skills.

### Complete the self-assessment¶

The employee feedback remains hidden from management while the employee is performing their self-assessment. Once the employee has completed their half of the appraisal, and updated any skills, they tick the gray Not Visible to Manager toggle. This changes the toggle text to Visible to Manager, the color changes to green, and their responses are then visible to management.

Additionally, a green dot appears on the appraisal card on the **Appraisals** app dashboard, indicating the employee has completed their assessment, and marked their half of the appraisal as done.

## Manager feedback¶

While the employee is completing their Employee’s Feedback section, the manager fills out the Manager’s Feedback section.

Before the manager fills out their portion of the appraisal, managers typically review the employee’s goals and skills, and ask for additional feedback from the employee’s coworkers, to better understand all the achievements and challenges for the employee.

Once the manager has all the information they need to evaluate the employee, they fill out the Manager’s Feedback section of the appraisal form. The manager’s half has the following sections: Feedback, Evaluation, and Improvements.

The manager’s appraisal focuses on the employee’s accomplishments, as well as identifying areas of improvements, with actionable steps to help the employee achieve their goals in both the long and short term.

When the feedback section is completed, the manager can tick the Not Visible to Employee toggle. This changes the toggle text to Visible to Employee, the color changes to green, and their responses are then visible to the employee.

Nota

Some managers prefer to keep their feedback hidden from the employee until they meet with the employee to discuss the appraisal.

### Ask for feedback¶

As part of the appraisal process, the manager can request feedback for an employee from anyone in the company about an employee. In Odoo, this is referred to as _360 Feedback_.

Feedback is requested from coworkers and anyone else who works with the employee. This is to get a more well-rounded view of the employee, and aid in the manager’s overall assessment.

Importante

To request feedback, the appraisal **must** be confirmed. Once confirmed, an Ask Feedback button appears in the upper-left corner of the form.

To request feedback from a colleague, click the Ask Feedback button, and an Ask Feedback email pop-up window appears, using the Appraisal: Ask Feedback email template.

First, using the drop-down menu, select the employees being asked to provide feedback in the Recipients field. Multiple employees may be selected. Next, make any desired changes to the default message, and attach any relevant documents. To attach a document, click the __ Attachments button, and a file explorer window appears. Navigate to the files, select them, then click Open.

The Answer Deadline date is automatically set to the day after the Appraisal Date on the appraisal form. Using the calendar selector, modify the date, if desired.

When the email is ready to send, click Send, and the feedback requests are sent to the specified employees.

## Appraisal review¶

Once both portions of an appraisal are completed (the employee and manager feedback sections), it is time for the employee and manager to meet and discuss the appraisal.

During the appraisal meeting, the manager reviews both the Employee’s Feedback section as well as their own Manager feedback.

Additionally, the employee’s skills and [goals](goals.html) are reviewed at this time, and updated as needed.

### Schedule appraisal review¶

A meeting can be scheduled in one of two ways: either from the **Appraisals** app dashboard, or from an individual appraisal card.

To schedule an appraisal from the dashboard of the **Appraisals** app, first navigate to Appraisals app ‣ Appraisals.

Click the activity icon beneath the appraisal date on the desired appraisal card, and an activity pop-up window appears. Click __ Schedule an activity, and set the Activity Type` to Meeting. For more information on scheduling activities, refer to the [activities documentation](../../essentials/activities.html#activities-all).

Doing so opens a New Event pop-up form. From this pop-up form, make any desired modifications, such as designating a Start time.

The employee populates the Attendees section by default. Add anyone else who should be in the meeting, if necessary.

To make the meeting a video call, instead of an in-person meeting, click __ Odoo meeting, and a Videocall URL link appears in the field.

Once all the desired changes are complete, click Save & Close.

The meeting now appears on the calendar, and the invited parties are informed, via email.

The other way to schedule a meeting is from the individual appraisal form. To do this, navigate to the Appraisal app dashboard, then click on an appraisal card.

Next, click on the __ Meeting smart button, and the calendar loads. Follow the same directions above to create the meeting.

For more detailed information on how to schedule activities, refer to the [activities](../../essentials/activities.html) documentation.

Nota

If no meetings are scheduled, the Meeting smart button reads No Meeting.

### Review employee skills¶

Part of an appraisal is evaluating an employee’s skills, and tracking their progress over time. The Skills tab of the appraisal form auto-populates with the skills from the [employee form](../employees/new_employee.html#employees-skills), once an appraisal is confirmed.

Each skill is grouped with like skills, and the Skill Level, Progress, and Justification are displayed for each skill.

[Update any skills, or add any new skills](../employees/new_employee.html#employees-skills) to the Skills tab.

If a skill level has increased, enter a reason for the improved rating in the Justification field, such as `took a fluency language test` or `received Javascript certification`.

After an appraisal is completed, and the skills have been updated, the next time an appraisal is confirmed, the updated skills populate the Skills tab.

Nota

The Skills tab _can_ be modified **after** the employee and their manager have met and discussed the employee’s appraisal.

This is a common situation as the manager may not have all the necessary information to assess and update the employee’s skills before meeting.

## Complete an appraisal¶

After the appraisal has been filled out by both the employee and the manager, and both parties have met and discussed the employee’s performance, the manager then logs any notes, and assigns a rating.

When completed, click the Mark as Done button in the upper-left corner of the appraisal form.

Once the appraisal is marked as _Done_ , the status changes from Confirmed to Done, and the Mark as Done button changes to a Reopen button.

Suggerimento

Modifications are **not** possible once the appraisal is marked as done.

To make any changes to an appraisal with a status of Done, click the Reopen button, then, click Confirm, and make any modifications needed. Once all modifications are complete, click the Mark as Done button again.

### Add a private note¶

Managers can log notes on an appraisal that are **only** visible to other managers. Enter any notes in the Private Note tab. This can be done anytime during the appraisal process.

The employee being evaluated does **not** have access to this tab, and the tab does **not** appear on their appraisal.

The tab is optional and does not affect the final rating.

### Provide a final rating¶

After both the manager and employee have met to discuss the employee’s performance, the appraisal must be given a Final Rating.

Using the drop-down menu, select the rating for the employee. The default options are: Needs improvement, Meets expectations, Exceeds expectations, Strongly Exceeds Expectations, and Good.

To add a new rating, navigate to Appraisals app ‣ Configuration ‣ Evaluation Scale. The default ratings are presented in a list view. To add a new rating, click the New button in the upper-left corner, and a blank line appears at the bottom of the list. Enter the new rating, then press the enter key, or click away from the line. Add as many new ratings as needed.

Click Appraisals in the top menu to return to the Appraisals dashboard, click on the appraisal, then select the desired Final Rating.

Vedi anche

  * [Obiettivi](goals.html)

  * [Appraisal analysis](appraisal_analysis.html)

  * [Skills evolution](skills_evolution.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/appraisals/new_appraisals.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](goals.html "Obiettivi") |
  * [precedente](../appraisals.html "Valutazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Conduct appraisals


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