# My time — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](management.html "Amministrazione") |
  * [precedente](request_time_off.html "Request time off") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * My time



# My time¶

The _My Time_ menu of the _Time Off_ application houses all the various time off information for the signed-in user.

This includes the main _Time Off_ dashboard, which displays an overview of the various time off balances, as well as time-off requests and allocations.

## Bacheca¶

All users have access to the _Time Off_ Dashboard, which is the first page that appears when the _Time Off_ application is opened. The Dashboard can also be accessed at any point in the application, by navigating to Time Off app ‣ My Time ‣ Dashboard.

The current year is displayed, and the current day is highlighted in a red circle.

To change the view, click on the Year button to reveal a drop-down menu. Then, select either Day, Week, or Month to present the calendar in that corresponding view.

Nota

To change the displayed dates, click the __(left arrow) or __(right arrow) icons to the left of the Year button. The calendar view adjusts in increments of the selected view.

For example, if Year is selected, the arrows adjust the view by one year.

To reset the view, so it includes the current date, click the Today button.

Above the calendar view is a summary of the user’s time off balances. Every time off type that has been allocated appears in its own summary box. Each summary lists the type of time off, the corresponding icon, the current available balance (in hours or days), and an expiration date (if applicable).

To view the full details of a time off balance, click the __(question mark) icon at the end of the (DAYS/HOURS) AVAILABLE on the time off summary. The complete details are presented in a popover window, including the Allocated time, Accrual (Future) time, Approved time off scheduled, Planned time off, and the currently Available time off.

A user can also select a future date to see an estimate of how much time they should accrue by that point. On the right side of the time off summary blocks, there is a Balance at the (date) field. Click on the date, and a calendar selector popover appears.

Nota

The Balance at the (date) field **only** appears if the user is accruing time off through an [accrual plan](../time_off.html#time-off-accrual-plans).

The current date is the default date selected. Navigate to the desired date, and Odoo displays the time off balances the user should have on that date. This takes into account all time off currently planned and approved. To return to the current date, click the Today button to the right of the date field.

On the right side of the calendar, the various time off types are displayed, each with their own corresponding color. The Legend explains how the various statuses for time off requests are presented.

Time off that has been validated appears in a solid color. Time off requests that still are still in the To Approve stage, appear with white stripes in the color. Refused time off requests have a line through the dates.

The color for each request corresponds to the specified color set with the various time off types, listed in the section above the Legend.

New time off requests can be made from the Dashboard. Click the New button in the upper-left corner, and a [New Time Off](request_time_off.html) pop-up window appears.

New allocation requests can also be made from the Dashboard. Click the New Allocation Request button to request more time off, and a [New Allocation](allocations.html#time-off-request-allocation) pop-up window appears.

## My time off¶

To view a list of all the time off requests, navigate to Time Off app ‣ My Time ‣ My Time Off. Here, all time off requests, both past and present, appear in a list view.

The list includes the following information for each request: the Time Off Type, Description, Start Date, End Date, Duration, and Status.

A new time off request can be made from this view. Click the New button to [Request time off](request_time_off.html).

## My allocations¶

To view a list of all allocations, navigate to Time Off app ‣ My Time ‣ My Allocations. All allocations and requested allocations appear in a list view.

The information presented on the My Allocations page includes: Time Off Type, Description, Amount, Allocation Type, and Status.

A new allocation request can be made from this view, as well. Click the New button to [request an allocation](allocations.html#time-off-request-allocation).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/time_off/my_time.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](management.html "Amministrazione") |
  * [precedente](request_time_off.html "Request time off") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Ferie](../time_off.html) »
  * My time


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