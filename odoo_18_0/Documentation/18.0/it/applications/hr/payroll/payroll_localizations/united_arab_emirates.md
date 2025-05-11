# Emirati Arabi Uniti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../time_off.html "Ferie") |
  * [precedente](jordan.html "Giordania") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Human resources](../../../hr.html) »
  * [Libro paga](../../payroll.html) »
  * [Payroll localizations](../payroll_localizations.html) »
  * Emirati Arabi Uniti



# Emirati Arabi Uniti¶

## Configurazione¶

[Install](../../../general/apps_modules.html#general-install) the following modules to get all the features of the **United Arab Emirates** **Payroll** localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
United Arab Emirates - Payroll | `l10n_ae_hr_payroll` | Includes all rules, calculations, and salary structures.  
United Arab Emirates - Payroll with Accounting | `l10n_ae_hr_payroll_account` | Includes all accounts related to the payroll module.  
  
Vedi anche

[United Arab Emirates fiscal localization documentation](../../../finance/fiscal_localizations/united_arab_emirates.html)

## Dipendenti¶

First, configure the [employee general information](../../employees/new_employee.html) and then configure the following fields under the Private Information tab:

  * Nationality (Country): The nationality affects an employee’s payslips, whether they are nationals or expats.

  * Identification Number: Used to extract the WPS report.

  * Bank Account: Used to extract the WPS report and generate payments for those employees.




Nota

The Nationality (Country) field needs to be set even if the employee is a UAE national since there is a different type of handling if they are citizens of a GCC country.

## Contratti¶

Once the employee form has been created, ensure the [contract](../contracts.html) is enabled by clicking on the __ Contracts smart button, or going to Employees ‣ Contracts.

The following contractual information related to employees working in the United Arab Emirates are found under the Salary Information tab:

  * Wage Type: select Fixed Wage for Full-time or Part-time employees, or Hourly Wage for employees who are paid hourly.

  * Scheduled Pay: the frequency of payslip issuance.

  * Wage: Monthly or Hourly depending on the Wage Type.

  * Housing Allowance

  * Transportation Allowance

  * Other Allowance




Nota

The allowance values set on the contract are used on the payslip lines as allowances.

  * Number of Leave Days: Used to specify the number of annual leave days that an employee deserves in a particular year. Regardless of the actual number of leaves that the employee gets (extra leave days for some internal company reasons), the final calculation of the end of service and unpaid leaves is dependent on the number set on this field.

Nota

The Number of Leave Days affects the calculation for unpaid leave provisions.

  * Is DEWS Applied: DIFC Employee Workplace Savings (DEWS), if the employee is a UAE national and has DEWS applied, tick this checkbox.

  * Computed Based On Daily Salary: Defines the way that the end of service is calculated:

    * Do not tick this checkbox if the standard calculation is to be used. This computes the compensation amount by dividing the monthly salary by **30** and then multiplying it by **21**.

    * Tick this checkbox and directly set the actual Daily Salary so that it is used in the end of service calculation.




## Salary structures and salary rules¶

### Other input rules¶

The following are the different allowances that can be defined directly on the [payslip form](../payslips.html) to allow for the values that are set against these inputs to affect the WPS calculations as monthly variable salaries for the specific employee that they are linked to.

Rules that are related to the WPS setup, are linked to other input types, and whenever they are used, their values are reflected on the WPS as monthly variable salary for that specific employee.

**Type** | **Code**  
---|---  
Conveyance Allowance | `CONVALLOW`  
Housing Allowance | `HOUALLOW`  
Medical Allowance | `MEDALLOW`  
Annual Passage Allowance | `ANNUALPASSALLOW`  
Overtime Allowance | `OVERTIMEALLOW`  
Other Allowance | `OTALLOW`  
Leave Encashment | `LEAVEENCASH`  
  
### End of service (EOS)¶

End of service (EOS) provides the calculation for the allowance that the employee gets at the end of their service. It is triggered when the employee’s departure reason is set by archiving the employee’s record.

There are several different calculations depending on the scenario:

  1. _The Employee spent less than a year in the company_ : The employee does not get any EOS allowance since they are not eligible for it (they are eligible once they complete their first year in the company).

  2. _The Employee spent more than a year and less than 5 years in the company_ : The employee is eligible for an equivalent of **21** days of salary for each year they spent on the company.

Nota

There are two ways for calculating the daily wage that gets paid for the employee against the 21 days of the EOS: Either by the default way of dividing the monthly basic wage by 30. Or, it can be manually input on the contract of the employee under the _Daily Salary_ field.

  3. _The Employee spent more than 5 years in the company_ : The employee is eligible for an equivalent of **30** days of salary for each year they spent on the company. In this case, if the default method is used, then the employee gets paid an equivalent of 1 month of salary, and the set _Daily Salary_ field, they will get the amount for the day multiplied by 30.

Nota

There are two payslips printout formats, one for normal salaries and one for end of service payslips, it is based on the employee being archived and having a departure reason or not.




### End of service provision (EOS Provision)¶

The EOS provision provides the calculation for the end-of-service provision amount that the company puts aside every month to count for the EOS that will be paid to them as an EOS allowance.

Unlike the EOS, the provision is part of the employee’s payslip from the start of their contract.

Just like the EOS, the provision has two calculations depending on the period spent by the employee in the company:

  * Less than 5 years: \\(\frac{\text{Monthly Wage}}{30}\times{\frac{21}{12}}\\)

  * More than 5 years: \\(\frac{\text{Monthly Wage}}{30}\times{\frac{30}{12}}\\)

Nota

This rule is not shown to the employee on the payslip printout and it does not affect their net payable, it is only for internal use by the company.




### Annual leave provisions¶

Annual leave provisions are used for calculating the annual leave provision accumulated each month, just like the EOS provision, it does not affect the total amount paid to the employee, it is for internal use by the company.

It is calculated by dividing the employee’s total salary (Total Salary = Wage + Allowances) by **30** to get the daily salary. The daily salary is then multiplied by the eligible leave days and divided by **12** to determine the monthly provision amount.

\\[\text{Monthly Leave Provision} = \frac{\text{Total Salary} \times \text{Number of Leave Days}}{30} \div 12\\]

### Social insurance contributions¶

Social insurance contributions calculate the _social insurance_ , which is only available to UAE nationals.

The company contributes **15%** of the total monthly salary for the employee if the company is in **Abu Dhabi** and **12.5%** if the company is in **another Emirate**.

Nota

The total monthly salary for the employee = [basic + all allowances set on the contract].

On the other hand, the employee contributes **5%** of their total monthly salary and that amount gets deducted from the payslip amount.

### Annual remaining leave balance rules¶

Annual remaining leave balance rules are used for calculating the amount to be paid to or taken from the employee based on the number of leave days deserved by the employee during the current year.

The annual leave [time off type](../../time_off.html#time-off-time-off-types) is specified using the Is Annual Leave checkbox.

If enabled, the rule calculates the amount of leave days deserved by the employee up to the current date and subtracts the number of annual leave days taken, and if the result is positive, this means that the employee should be compensated for remaining amount and if negative this means that the employee is liable to the company for the difference.

### Sick leave rules¶

Sick leave rules provide the calculation for cases where the employee is on sick leave and decides how the payslip should be affected.

There are **3 cases** for the employee to have:

  1. **Fully paid sick leave:** The employee can upload a sick leave certificate (SLI). Employees are eligible for **15 days** of this type of leave per calendar year.

Suggerimento

The SLI is not mandatory in Odoo but can be done from the setup of the [time off types](../../time_off.html#time-off-time-off-types).

  2. **50% paid sick leave:** Same as the fully paid one, but the employees are eligible for **30 days** from this leave type. These 30 days are counted after the first **15** fully paid days.

  3. **0% paid sick leave:** Same as the fully paid one, but the employees are eligible for **45 days** from this leave type. These **45 days** are counted after the first **15/30** fully/half-paid days.




Importante

As per the labor law of the United Arab Emirates, the 15, 30, 45 days are not specified as working days or calendar days so this point will rely on the company policy.

The amount paid for the employee per sick leave day is counted as follows:

\\[\frac{\text{Number of Leave Days} \times \text{Gross Per Month}}{30} \times \text{Percentage}\\]

Where the gross per month is the basic + all other allowances set on the employee’s contract.

### Daman investments end of service programme (DEWS)¶

DEWS allows for calculating the DEWS amounts for the employees who are eligible for it and would like to be registered on it under their current contract with the company.

It is calculated based on the number of years that employees have spent in the company:

  * **Less than 5 years:** 5.83% is deducted from the employee’s **BASIC** salary towards the DEWS.

  * **More than 5 years:** 8.33% of The employee’s **BASIC** is deducted from the total payable for that employee.




### Unpaid leaves¶

Unpaid leaves allows for calculating the amount to be deducted when an employee takes an unpaid leave. It is calculated by the following equation:

\\[\frac{\text{Total Number of Unpaid Leave Days} \times \text{Gross Per Month}}{30}\\]

Where the gross per month is the basic + all other allowances set on the employee’s contract.

### Out of contract days¶

The out of contract days rule provides a calculation for the days before/after the contract period that overlaps with the contract of days on the employee’s payslips.

Example

Payslips are generated for the period of 1st-30th of September but the contract expires on the 21st, in this case, there are 7 days flagged as out of contract.

It is calculated by the following equation:

\\[\frac{\text{Total Number of Unpaid Leave Days} \times \text{Gross Per Month}}{\text{Number of Days in Current Month}}\\]

### Manual deductions¶

Manual deductions allows the user to add manual deductions to be applied to employees per payslip.

The amount to be deducted and the description of the deduction is to be set directly on the payslip manually as other inputs.

### Net salary¶

Net salary showcases the net amount that the employee will get based on the payslip.

It is calculated by adding basic to all allowances and deducting all deductions from it.

Importante

The approach taken for the rules above is to first get the full amounts for all static amounts that are set on the contract and then deduct the amounts that should be deducted such as unpaid leaves, sick leaves, manual deductions, commission, etc.

## Generating accounting entries from payslips¶

The accounts are linked to each payroll rule as a debit or credit so that when a draft entry is generated from a payslip, the amounts are reflected on the accounts accordingly.

The accounts need to be set in a way that would make the end-result entry balanced, otherwise a warning is raised if it is not balanced and it will not generate the entry.

After reviewing the payslips and making sure that all the amounts are correct, generate a draft entry, either one entry for all employees or an entry per employee depending on the setup done on the settings.

Example

Debit and credit accounts set up for the basic and allowance rules.

## Pay employees¶

After a batch or a payslip’s journal entry has been posted, the company can proceed to pay their employees.

In the batch itself or on the payslip, by clicking on the pay button, a payment is created and linked to the posted entry for the payslip. The same can be done for batch payslips if one payment is done from a single/multiple payment bank/cash journal.

Nota

Once the payslip is generated, the employee will be able to access the slips from their portal users. They will automatically receive an email mentioning that the payslips are now available to be viewed on their portal view.

## Payslip printouts¶

Two printout formats can be extracted from the payslip, it depends on the type of the payslip either a _Monthly_ payslip or an _End of Service_ Payslip. It is triggered if the employee for the payslip is generated is archived during that month.

## Master report¶

The _Master report_ provides a detailed view of the amounts paid to employees for a specific period based on the payslips that are generated for them during that period with payslip lines being set as columns in an Excel report.

It is mainly used to make the auditing process for the human resources department easier and faster.

To access this report, go to Payroll ‣ Reporting ‣ Master Report.

## Wages protection system (WPS) reports¶

The WPS is a report that needs to be submitted by the company to prove that they paid their employees the right amounts on the right dates. It can either be generated per payslip or batch.

The following steps need to be followed before generating the report:

  1. Go to Payroll ‣ Configuration ‣ Settings and under the UAE Payroll WPS Settings section, configure the following:

     * Employer Unique ID: Set a unique identifier for the company to be used in the WPS report.

     * Salaries Bank Account: Select a bank account or start typing to Create and edit a new bank account.

Importante

When setting the Salaries Bank Account make sure to complete the following:

       * Account Holder: set as the company.

       * Account Number: has to be a valid IBAN.

       * Bank: has to have the UAE Routing Code Agent ID set.

       * Send Money: should be enabled and set to Trusted.

  2. Set the unique identifier on all of the employees who are a part of the target of the batch/payslip.

The Identification No field can be found on the employee’s page under the Private Information tab.




Once the initial setup is done, the WPS can be generated either for one payslip or for a batch as follows:

  1. Generate the payslip one by one or as a batch.

  2. Post the draft entity related to the payslips.

  3. Create the payment report and set the Export Format to UAE WPS.




Nota

The report comes in a `.sif` format as per the governmental requirements, so either use software that can open `.sif` files or convert it to another format (`.xslx`) to be able to review it.

The resulting file consists of the following:

  1. **Employee Detail Record** (**EDR**): includes details of the employees on the batch. There should be one EDR record per employee.

  2. **Employee Variable Pay** (**EVP**): includes the details of the variable salary the employee got on that payslip. If the employee has any. The variable amounts are calculated from when other inputs are used that are linked to the salary rules (Payroll ‣ Configuration ‣ Rules).

  3. **Salary Control Record** (**SCR**): There should only be one SCR per WPS file as it indicates the employer details and the totals for the payslips.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/payroll/payroll_localizations/united_arab_emirates.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../time_off.html "Ferie") |
  * [precedente](jordan.html "Giordania") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Human resources](../../../hr.html) »
  * [Libro paga](../../payroll.html) »
  * [Payroll localizations](../payroll_localizations.html) »
  * Emirati Arabi Uniti


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