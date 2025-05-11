# Contratti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_entries.html "Work entries") |
  * [precedente](../payroll.html "Libro paga") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Contratti



# Contratti¶

Every employee in Odoo is required to have a contract in order to be paid. A contract outlines the terms of an employee’s position, their compensation, working hours, and any other details about their position.

Importante

Contract documents (PDFs) are uploaded and organized using the _Documents_ application, and are signed using the _Sign_ application. Ensure these applications are installed to send and sign contracts. Please refer to the [Documenti](../../productivity/documents.html) and [Firma](../../productivity/sign.html) documentation.

To view the employee contracts, go to the Payroll app ‣ Contracts ‣ Contracts from the top menu. All employee contracts, and their current contract status, are displayed in a Kanban view, by default. The Kanban view displays running contracts, contracts that require action, expired contracts, and cancelled contracts.

Nota

The list of contracts in the _Payroll_ application matches the list of contracts in the _Employees_ application.

In order for an employee to be paid, an active contract is required. If a new contract is needed, click the Create button on the Contracts dashboard. A contract form appears where the information can be entered. Required fields are underlined in bold.

## New contract form¶

## General information section¶

  * Contact Reference: type in the name or title for the contract, such as `John Smith Contract`. This field is **required**.

  * Employee: using the drop-down menu, select the employee that the contract applies to.

  * Contract Start Date: the date the contract starts. To choose a date, click the drop-down menu, navigate to the correct month and year with the < > (arrow) icons, then click on the desired date. This field is **required**.

  * Contract End Date: if the contract has a specific end date, click the drop-down menu, navigate to the correct month and year with the < > (arrow) icons, then click on the desired date.

  * Working Schedule: select one of the working schedules from the drop-down menu. This field is **required**.

Suggerimento

The Working Schedule drop-down menu displays all the working schedules for the selected company. To modify or add to this list, go to Payroll app ‣ Configuration ‣ Working Schedules. Click New, and create a new working schedule, or click on an existing working schedule and make edits.

  * Work Entry Source: select how the [work entries](work_entries.html) are generated. This field is **required**. Click the radio button next to the desired selection. The options are:

    * Working Schedule: work entries are generated based on the selected Working Schedule.

    * Attendances: work entries are generated based on the employee’s check-in records in the _Attendances_ application. (This requires the _Attendances_ application).

    * Planning: work entries are generated based on the planned schedule for the employee from the _Planning_ application. (This requires the _Planning_ application).

  * Salary Structure Type: select one of the salary structure types from the drop-down menu. The default salary structure types are Employee or Worker. A [new salary structure type](../payroll.html#payroll-new-structure-type) can be created, if needed.

  * Department: select the department the contract applies to from the drop-down menu.

  * Job Position: select the specific job position the contract applies to from the drop-down menu.

Nota

If the selected Job Position has a contract template linked to it with a specific Salary Structure Type, the Salary Structure Type changes to the one associated with that Job Position.

  * Wage on Payroll: enter the employee’s monthly wage.

  * Contract Type: choose either Permanent, Temporary, Seasonal, Full-Time, or Part-Time from the drop-down menu.




  * Contact Reference: type in the name or title for the contract, such as `John Smith Contract`. This field is **required**.

  * Employee: name of the employee the contract applies to.

  * Contract Start Date: the date the contract starts. Choose a date by clicking on the drop-down menu, navigating to the correct month and year by using the ____(arrow) icons, then clicking on the desired date. This field is **required**.

  * Contract End Date: the date the contract ends. Choose a date by clicking on the drop-down menu, navigating to the correct month and year by using the ____(arrow) icons, then clicking on the desired date. This field is **required**.

  * Salary Structure Type: select one of the salary structure types from the drop-down menu. The default salary structure types are Employee or Worker. A new salary structure type can be created by typing the name in the field. This field is **required**.

  * Working Schedule: select one of the working schedules from the drop-down menu. This field is **required**.

  * Department: the department the contract applies to.

  * Job Position: the specific job position the contract applies to.

  * Wage on Payroll: the amount to be paid to the employee each month.

  * Contract Type: choose from CDI, CDD, or PFI from the drop-down menu.

    * CDI is an open-ended contract with only a start date, but no end date.

    * CDD is a contract with both a start date and an end date.

    * PFI is a Belgian-specific contract used when hiring employees that need training, and covers the training period specifically.

  * HR Responsible: if there is a specific person in HR that is responsible for the contract, select the person from the drop-down menu. This field is required.




Suggerimento

The Working Schedule drop-down menu displays all the working times for the selected Company. To modify or add to this list, go to Payroll app ‣ Configuration ‣ Working Times, and either Create a new working time, or click on an existing working time, then edit it by clicking Edit.

  * Yearly Cost (Real): this field automatically updates after the Schedule Pay and Wage fields are entered. This amount is the total yearly cost for the employer. This field can be modified. However, if this is modified, the Wage field updates, accordingly. Ensure both the Wage and Yearly Cost (Real) are correct if this field is modified.

  * Monthly Cost (Real): this field automatically updates after the Schedule Pay and Wage fields are entered. This amount is the total monthly cost for the employer. This field **cannot** be modified, and is calculated based on the Yearly Cost (Real).




## Contract Details tab¶

The Contract Details tab allows for the addition and editing of a contract, along with specifying which template to use when a new contract is created. These fields **must** be populated in order to create a new contract.

Importante

To access the various contract template fields in the Contract Details tab, the _Salary Configurator_ (`hr_contract_salary`) module **must** be [installed](../../general/apps_modules.html#general-install).

When the _Salary Configurator_ module is installed, the _Salary Configurator - Holidays_ and _Salary Configurator - Payroll_ modules install, as well.

Once the modules are installed, the database reverts to the main dashboard.

  * Contract Template: select a pre-existing contract template from the drop-down menu. Contract templates are typically created through the configuration menu, and stored in the _Documents_ application.




### Sign section¶

  * HR Responsible: select the person who is responsible for validating the contract from the drop-down menu. This field is required.

  * New Contract Document Template: select a contract from the drop-down menu to be modified for this new employee contract. These documents are stored in the _Sign_ application.

  * Contract Update Document Template: select a contract from the drop-down menu, if the employee has an existing contract that requires updating. These documents are stored in the _Sign_ application.




Importante

The HR Responsible, New Contract Document Template, and Contract Update Document Template fields are only visible if the _Sign_ application is installed, along with the `hr_contract_salary` and `hr_contract_salary_payroll` [modules](../../general/apps_modules.html). The _Sign_ application is where the contract templates are stored. This application is required for an employee to sign any contract.

### Accounting section¶

  * Analytic Account: select the account the contract affects from the drop-down menu. It is recommended to check with the accounting department to ensure the correct account is selected.




### Part Time section¶

  * Part Time: tick this box if the employee is working part-time. When active, additional fields appear:

    * % (Percentage): enter the percent of time the employee works as compared to a full-time employee.

    * Standard Calendar: select the working hours that a typical full-time worker uses from the drop-down menu.

    * Part Time Work Entry Type: select the work entry type that generates the balance of a full-time working schedule.

Example

If a full-time employee works 40 hours a week, and the employee works 20, enter `50` in the % (Percentage) field (50% of 40 hours = 20 hours). The employee generates twenty (20) hours of work entries under the work entry type `part-time`, and another twenty (20) hours of work entries under the work entry type `generic time off`, for a total of forty (40) hours worth of work entries.




### Notes section¶

  * Notes: a text field where any notes for the employee contract are entered for future reference.




  * Analytic Account: this field allows a link between the contract and a specific analytic account for accounting purposes.

  * Contract Template: select a pre-existing contract template from the drop-down menu. Contract templates are typically created through the _Recruitment_ application.

  * New Contract Document Template: select a contract from the drop-down menu to be modified for this new employee contract.

  * Contract Update Document Template: select a contract from the drop-down menu, if the employee has an existing contract that requires updating.

  * Notes: the notes field is a text field where any notes for the employee contract can be entered for future reference.




### Modify a contract template¶

Click the __(external Link) icon at the end of either the New Contract Document Template or Contract Update Document Template to open the corresponding contract template, and proceed to make any desired changes.

Click the Upload your file button next to the corresponding document, navigate to the file, then click Open to select the document and add it to the tab.

#### Modifying contract templates¶

Contracts templates can be modified at any point when changes are needed.

  * Tags: select any tags associated with the contract.

  * Signed Document Workspace: this is where the signatures are stored. Choose a pre-configured workspace, or create a new one. To create a new Signed Document Workspace, type in the name of the workspace, then click either Create to add the new workspace, or Create and Edit to add the workspace and modify the workspace details.

  * Signed Document Tags: select or create any tags that are only associated with the signed contract, as opposed to the original unsigned contract.

  * Redirect Link: enter a redirect link for the employee to access the contract. A redirect link takes the user from one URL to another. In this case, it takes them to the newly-updated contract specifically written for them.

  * Who can Sign: select either All Users or On Invitation.

    * All Users: any user in the organization can sign the contract.

    * On Invitation: only users selected in this field can sign the contract.

  * Invited Users: select the person (or people) that can sign the document.

  * Document: the attached document can be replaced by clicking the __(pencil) icon. A pop-up window appears, so another document can be selected for upload. The file **must** be a PDF. To remove the document, click the __(trash can) icon.




Once the edits are complete, click the Save button. All the information for the selected contract template populates the fields in the Salary Information tab. Any additional tabs, such as Personal Documents, appears if applicable.

## Salary information¶

This section is where the specific salary details are defined. This section is country-specific, so these fields vary, depending on where the company is located.

Enter the amount in the various fields, or tick a checkbox to apply a benefit. Some options that can be entered here include Group Insurance Sacrifice Rate and Canteen Cost, for example.

Some fields may be automatically filled in as other fields are entered. For example, the Yearly Cost (Real) and Monthly Cost (Real) updates once the Wage is populated.

## Personal documents¶

This tab **only** appears after an Employee is selected, and houses any documents that are linked to the employee on their employee record. Documents cannot be added to this tab, this tab **only** shows documents that are already uploaded and associated with the employee.

The available documents in this tab can be downloaded. Click the __(download) icon next to the document to download it.

## Save and send the contract¶

Once a contract has been created and/or modified, save the contract by clicking the Save button. Next, the contract must be sent to the employee to be signed.

Click on one of the following buttons to send the contract to the employee:

  * Generate Simulation Link: this option is **only** for Belgian companies. Clicking this opens a pop-up window that contains the basic information from the contract, as well as a link for the contract when using the salary configurator. Click Send to send an email to the employee, so they can sign the contract.




At the bottom of the pop-up form is a Link Expiration Date. This is the timeframe that the contract offer is valid for. By default, this field is pre-populated with `30 days`, but it can be modified.

> Nota
> 
> In order to send a contract using the Generate Simulation Link, there **must** be a signature field in the contract PDF being sent to the employee, so they can sign it.

  * Signature Request: clicking this reveals a pop-up window, where an email can be typed to the employee. Select the document (such as a contract, NDA, or Homeworking Policy) from the drop-down menu, and fill out the email section. Click Send when the email is ready to be sent.




Nota

To send a contract using the Generate Simulation Link, there **must** be a signature field in the contract PDF being sent to the employee, so they can sign it.

## Salary attachments¶

Any automatic deductions or allocations for an employee, such as child support payments and wage garnishments, are referred to as a _salary attachment_. This section is where all of these deductions or allocations are set.

To add a new deduction, first navigate to Payroll app ‣ Contracts ‣ Salary Attachments. Next, click Create, and a new salary attachment form loads.

Fill out the following fields on the form:

  * Employee: using the drop-down menu, select the employee the salary attachment applies to.

  * Description: enter a short description for the salary attachment, such as `Child Support` or `529 Contribution`.

  * Type: using the drop-down menu, select the type of salary attachment being created. Choose from:

    * Attachment of Salary: any payments taken out towards something that is _not_ child support. Typically any garnishments, such as lawsuit payments, payments toward taxes owed, etc.

    * Assignment of Salary: any deduction that is not required, but voluntary, such as a pre-tax allocation to a college savings account.

    * Child Support: any payments taken out specifically for child support.

  * Start Date: the date the salary attachment starts. Choose a date by clicking on the drop-down menu, navigating to the correct month and year by using the ____(arrow) icons, then clicking on the desired date. This field is **required**.

  * Estimated End Date: this field automatically populates after both the Monthly Amount and Total Amount fields are populated. This field is **not** modifiable.

  * Document: attach any documents relevant to the salary attachment. Click the Upload Your File button, navigate to the desired document in the file explorer, then click Open to select the document, and attach it to the form. To change the attached document, click the __(pencil) icon, and select a different document. To remove a document, click the __(trash can) icon.

  * Monthly Amount: enter the amount to be taken out of the employee’s paycheck every month for this specific salary attachment.

  * Total Amount: enter the total amount that the employee pays for the salary attachment to be completed.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/payroll/contracts.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_entries.html "Work entries") |
  * [precedente](../payroll.html "Libro paga") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Libro paga](../payroll.html) »
  * Contratti


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
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price