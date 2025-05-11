# Skills evolution — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../frontdesk.html "Reception") |
  * [precedente](appraisal_analysis.html "Appraisal analysis") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Skills evolution



# Skills evolution¶

In Odoo’s **Appraisals** app, it is possible to view employee’s skills as they progress over time in the Skills Evolution report, also known as the _Appraisal Skills Report_.

Managers can use this to see who is achieving their various skill goals set on their appraisals, who is meeting their skill deadlines, who has the highest performance in terms of skill development, and more.

The _Skills Evolution_ report also provides the ability to search for employees with specific skills at certain levels, which can be helpful for scenarios where specific skills are required.

## Skills evolution report¶

To access this _Skills Evolution_ report, navigate to Appraisals app ‣ Reporting ‣ Skills Evolution.

Doing so reveals the Appraisal Skills Report page. All skills are grouped by the month they were created, then by employee, and then by skill type.

Importante

> The Appraisals Skills Report only displays skills for employees with at least one completed appraisal. Skills for employees whose appraisals are still draft or pending are not included.

When an employee completes their first appraisal, all their skills appear on the report. Once subsequent appraisals are marked as done, any skill changes from the previous appraisal appear on the report.

Any skill level changes from ongoing appraisals that have **not** been finalized are **not** included in this report.

To view the specific details for an employee’s skill types, expand the Employee, then expand the individual Skill Types. Each skill type displays the following information:

  * Employee: the name of the employee.

  * Skill Type: the category the skill falls under.

  * Skill: the specific, individual skill.

  * Current Level: the current level the employee has achieved for the skill.

  * Previous Progress: the previous percentage of competency achieved for the skill.

  * Current Progress: the current percentage of competency achieved for the skill.

  * Justification: any notes entered on the skill, explaining the progress.




The color of the skill text indicates any changes from the previous appraisal. Skill levels that have increased since the last appraisal appear in green, as an _Improvement_. Skill levels that have **not** changed appear in black, as _No Change_. Skills that have regressed appear in red, as _Regression_.

This report can be modified to find specific information by adjusting the [filters](../../essentials/search.html#search-filters) and [groupings](../../essentials/search.html#search-group) set in the search bar at the top.

## Use case: Identify employees with specific skills¶

Since the Appraisal Skills Report organizes all skills by month, then employee, it can be difficult to find employees with a specific skill at a specific level. To find these employees, a custom filter must be used.

In this example, the report is modified to show employees with an expert level of Javascript knowledge. To view only those employees, first remove all active filters in the search bar.

Next, click the __(Toggle Search Panel) icon in the search bar, then click Add Custom Filter beneath the __ Filters column to load an Add Custom Filter pop-up window.

Using the drop-down menu in the first field, select Skill. Then, keep the second field as-is (is in), and select Javascript from the third drop-down menu in the third field.

Next, click New Rule, and another line appears. In this second line, select Current Level for the first drop-down field, leave the second field as-is (is in), then select Expert for the third drop-down field.

After the second rule is added, navigate to the text at the top of the pop-up window that shows Match any __ of the following rules. Click the drop-down menu for any and change it to all.

Finally, click the Add button.

Now, only employees that have an Expert level for the skill Javascript appear. In this example, only Marc Demo meets these criteria.

## Use case: Assess highest improvement¶

Another way to modify the Appraisal Skills Report is to identify the employee who has the highest amount of improved skills over a specific period of time.

To view this information, first remove the default filter in the search bar. Next, click the __(Toggle Search Panel) icon in the search bar, then click Improvement beneath the __ Filters column. Enabling this filter only presents skills that have improved.

It is possible to view the skills that have improved over a period of time, such as a specific quarter, or month. With the search bar drop-down menu still expanded, click Add Custom Filter at the bottom of the __ Filters column, and an Add Custom Filter pop-up window appears.

Select Create Date for the first drop-down field, then select is between for the second drop-down field. Once is between is selected, a second field appears after the last field. Using the calendar selector, select the date range to apply the filter to. Once all the fields are properly formatted, click Add.

The custom filter presents all skills that have been improved, organized by employee, in a default list view.

Example

To determine the employee with the most amount of improved skills for the second quarter, remove the default filter in the search bar of the Appraisal Skills Report. Next, activate the Improvement filter, then click Add Custom Filter at the bottom of the __ Filters column.

In the resulting Add Custom Filter pop-up window, select Create Date for the first drop-down field, then select is between for the second drop-down field. Two date fields appear after is between is selected.

Using the calendar selector, set the first date to 04/01/2025 and the second date to 06/30/2025, then click Add.

To view the number of employees and skills in further detail, click the __(Pivot) icon in the top-right corner to view the data in a pivot table. This presents a pivot table with the employees populating the rows, and the only visible column represents the total number of improved skills.

To expand the columns to view which skill types had the most overall improvement, click __ Total above the Count column, then click Add Custom Group __, then click Skill from the resulting drop-down menu. This expands all the improved skills, organized by individual skill.

Example

> In this example, Audrey Peterson improved the most in the third quarter, with five improved skills.

Vedi anche

  * [Odoo essentials reporting](../../essentials/reporting.html)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/appraisals/skills_evolution.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../frontdesk.html "Reception") |
  * [precedente](appraisal_analysis.html "Appraisal analysis") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Skills evolution


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