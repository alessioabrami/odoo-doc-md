# Allocazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](request_time_off.html "Request time off") |
  * [precedente](../time_off.html "Ferie") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Allocazioni



# Allocazioni¶

Once [time off types](../time_off.html#time-off-time-off-types) and [accrual plans](../time_off.html#time-off-accrual-plans) have been configured, the next step is to _allocate_ , or give, time off to employees.

The _Allocations_ page of the **Time Off** app is **only** visible to users who have either _Time Off Officer_ or _Administrator_ access rights for the **Time Off** application. For more information on access rights, refer to the [access rights](../../general/users/access_rights.html) documentation.

## Allocate time off¶

To create a new allocation, navigate to Time Off app ‣ Management ‣ Allocations.

This presents a list of all current allocations, including their respective statuses.

Click New to allocate time off, and a blank allocation form appears.

After entering a name for the allocation on the first blank field of the form, enter the following information:

  * Time Off Type: Using the drop-down menu, select the type of time off that is being allocated to the employees.

  * Allocation Type: Select either Regular Allocation or Accrual Allocation. If the allocation is **not** based on an [accrual plan](../time_off.html#time-off-accrual-plans), select Regular Allocation.

  * Accrual Plan: If Accrual Allocation is selected for the Allocation Type, the Accrual Plan field appears. Using the drop-down menu, select the accrual plan with which the allocation is associated. An accrual plan **must** be selected for an Accrual Allocation.

  * Validity Period/Start Date: If Regular Allocation is selected for the Allocation Type, this field is labeled Validity Period. If Accrual Allocation is selected for the Allocation Type, this field is labeled Start Date.

The current date populates the first date field, by default. To select another date, click on the pre-populated date to reveal a popover calendar window. Navigate to the desired start date for the allocation, and click on the date to select it.

If the allocation expires, select the expiration date in the next date field. If the time off does _not_ expire, leave the second date field blank. No Limit appears in the field if no date is selected.

If Accrual Allocation is selected for the Allocation Type, this second field is labeled Run until.

Importante

If the Start Date entered is in the middle of a period of time, such as the middle of the month, Odoo applies the allocation to the beginning or end of the period, depending on the _Accrued Gain Time_ entered on the [accrual plan](../time_off.html#time-off-accrual-plans) (either _At the start of the accrual period_ , or _At the end of the accrual period_) instead of the specific date entered.

For example, an allocation is created, and references an accrual plan that grants time _At the start of the accrual period_ , monthly, on the first of the month.

On the allocation form, the Allocation Type is set to Accrual Allocation, and the Start Date entered is `06/16/24`.

Odoo’s **Time Off** app retroactively applies the allocation to the beginning of the time period entered in the Start Date.

Therefore, this allocation accrues time from `06/01/24`, rather than `06/16/24`.

Additionally, if on the accrual form, the allocation references an accrual plan that grants time _`At the end of the accrual period_ , the allocation accrues time from `7/01/24` rather than `6/18/24`.

  * Allocation: Enter the amount of time that is being allocated to the employees. This field displays the time in either Hours or Days, depending on how the selected [Time Off Type](../time_off.html#time-off-time-off-types) is configured.

  * Mode: Using the drop-down menu, select how the allocation is assigned. This selection determines who receives the time off allocation. The options are By Employee, By Company, By Department, or By Employee Tag.

Depending on what is selected for the Mode, the field beneath Mode is labeled either: Employees, Company, Department, or Employee Tag.

Using the drop-down menu, indicate the specific employees, company, department, or employee tags receiving this time off.

Multiple selections can be made for either Employees or Employee Tag.

Only one selection can be made for the Company or Department.

  * Add a reason…: If any description or note is necessary to explain the time off allocation, enter it in this field at the bottom of the form.




## Request allocation¶

If an employee has used all their time off, or will run out of time off, they can request an allocation for additional time. Allocations can be requested in one of two ways, either from the [Dashboard](my_time.html#time-off-dashboard) or the [My Allocations](my_time.html#time-off-my-allocations) view.

To create a new allocation request, click either the New Allocation Request button on the main **Time Off** dashboard, or the New button in the My Allocations list view. Both buttons open a new allocation request form.

Nota

Both options open a new allocation request form, but when requested from the Dashboard, the form appears in a pop-up window, and the _Validity Period_ field does **not** appear. When requested from the My Allocations list view, the screen navigates to a new allocation request page, instead of presenting a pop-up window.

Enter the following information on the new allocation request form:

  * Time Off Type: Select the type of time off being requested for the allocation from the drop-down menu. After a selection is made, the title updates with the time off type.

  * Validity Period: By default, the current date populates this field, and it is **not** able to be modified. This field **only** appears when requesting an allocatoin from the My Allocations view (Time Off ‣ My Time ‣ My Allocations).

  * Allocation: Enter the amount of time being requested in this field. The format is presented in either Days or Hours, depending on how the Time Off Type is configured. Once this field is populated, the name of the allocation request is updated to include the amount of time being requested.

  * Add a reason…: Enter a description for the allocation request in this field. This should include any details that approvers may need to approve the request.




If the request was created from the Dashboard, click the Save & Close button on the New Allocation pop-up window to save the information and submit the request.

If the form was completed from the My Allocations list view, the information is automatically saved as it is entered. However, the form can be saved manually at any time by clicking the __(cloud upload) icon.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/time_off/allocations.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](request_time_off.html "Request time off") |
  * [precedente](../time_off.html "Ferie") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * Allocazioni


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