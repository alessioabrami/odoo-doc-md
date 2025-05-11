# Presenze — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](attendances/check_in_check_out.html "Check in and out") |
  * [precedente](../hr.html "Human resources") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Presenze



# Presenze¶

Odoo’s _Attendances_ application functions as a time clock. Employees are able to check in and out of work using a dedicated device in kiosk mode, while users are also able to check in and out of work directly from the database. Managers can quickly see who is available at any given time, create reports to see everyone’s hours, and gain insights on which employees are working overtime, or checking out of work earlier than expected.

## Diritti di accesso¶

It is important to understand how the different access rights affect what options and features users can access in the _Attendances_ application.

Every user in the database is able to check in and out directly from the database, without needing access to the _Attendances_ application. Additionally, all users can access their own attendance records from their employee form in the _Employees_ app.

Access to both the _Attendances_ application, and the various features within the application is determined by access rights.

To see what access rights a user has, navigate to the Settings app ‣ Users & Companies: Users, and click on an individual user. The Access Rights tab is visible by default. Scroll down to the Human Resources section to see the setting. For the Attendances field, the options are either to leave the field blank or select Administrator.

If the Administrator option is selected, the user has full access to the entire _Attendances_ application, with no restrictions. They can view all employee attendance records, enter _Kiosk mMode_ from the application, access all reporting metrics, and make modifications to the settings. If left blank, the user does **not** have access to the _Attendances_ application.

### Approvatori¶

The **only** other scenario where different information may be accessible in the _Attendances_ application is for approvers. If a user does _not_ have administrative rights for the _Attendances_ application, but they are set as an employee’s approver for the _Attendances_ application, that user is able to view the attendance records for that specific employee, as well as make modifications to that employee’s attendance records, if necessary. This applies to all employees for whom the user is listed as the _Attendances_ application approver. Approvers are typically managers, though this is not required.

To see who the attendance approver is for an employee, navigate to the Employees application and click on the specific employee. Click on the Work Information tab, scroll to the Approvers section, and check the Attendance field. The person selected is able to view that employees” attendance records, both on the _Attendances_ application dashboard as well as in the attendance reports, and make modifications to their records.

## Configurazione¶

Few configurations are needed in the _Attendances_ application. Determining how employees check in and out, defining how the kiosks function, and determining how extra hours are computed are all set in the Configuration menu. Navigate to the Attendances application ‣ Configuration to access the configuration menu.

### Modalità¶

  * Attendances from Backend: activate this selection to allow users to check in and out directly from the Odoo database. If this is not activated, users must use a kiosk to check in and out of work.




### Ore aggiuntive¶

This section specifies how extra time is calculated, including when extra time is counted and what time is not logged.

  * Count of Extra Hours: enable this box to allow employees to log extra hours beyond their set working hours (sometimes referred to as _overtime_). Activating this selection displays the following settings as well. If this is not activated, no other configurations appear.

    * Start From: the current date is automatically entered in this field. If desired, click on this field and use the calendar selector to modify the start date on which extra hours are logged.

    * Tolerance Time In Favor Of Company: enter the amount of time, in minutes, that is **not** counted towards an employee’s overtime. When an employee checks out, and the extra time logged is below the specified minutes, the extra time is **not** counted as overtime for the employee.

    * Tolerance Time In Favor Of Employee: enter the amount of time, in minutes, that an employee is given, that does **not** adversely affect their attendance if they log less time than their working hours. When an employee checks out, and the total time logged for the day is less than their specified working hours and less than this specified grace period, they are **not** penalized for their reduced hours.

Example

A company sets both of the Tolerance fields to `15` minutes, and the working hours for the entire company are set from 9:00 AM to 5:00 PM.

If an employee checks in at 9:00 AM, and checks out at 5:14 PM, the extra 14 minutes are **not** counted towards their overtime.

If an employee checks in at 9:05 AM, and checks out at 4:55 PM, even though they logged a total of 10 minutes less than their full working hours, they are **not** penalized for this discrepancy.

    * Display Extra Hours: activate this box to display the extra hours logged by an employee when they check out with a kiosk, or when a user checks out in the database.




Nota

Employees are still able to log overtime hours even if the Count of Extra Hours option is not activated. The difference is that when Count of Extra Hours is activated, the extra hours can be [deducted from an approved time off request](time_off.html#time-off-deduct-extra-hours).

## Panoramica¶

When entering the _Attendances_ application, the Overview dashboard is presented, containing all the check in and check out information for the signed in user. If the user has specific access rights and/or are approvers for specific employees, then those additional employee’s check in and check out information is also visible on the Overview dashboard.

### Visualizzazioni¶

To change the view from the default Gantt chart to a list view, click the List icon in the top right of the dashboard, beneath the user’s photo. To switch back to the Gantt chart, click the Gantt button, located next to the List button.

The default view presents the current day’s information. To present the information for the Week, Month, or Year, click on the Day button to reveal a drop-down, displaying those other options. Select the desired view, and the dashboard updates, presenting the selected information. To change the Day, Week, Month, or Year presented, click the ← (left arrow) or → (right arrow) buttons on either side of the drop-down menu. To jump back to a view containing the current day, click the Today button. This refreshes the dashboard, presenting information containing the current day’s information.

In the Day view, the column for the current hour is highlighted in yellow. If the Week or Month view is selected, the column for the current day is highlighted. If the Year view is selected, the current month is highlighted.

Any entries that have errors appear in red, indicating they need to be resolved by a user with the proper access rights and/or are approvers for the employee(s) with the errors.

### Filtri e gruppi¶

To filter the results in the overview dashboard, or to present different groups of information, click the 🔻 (triangle drop down) button in the right side of the Search bar above the dashboard, and select one of the available Filters or Group By options. There are several pre-configured filters and groups to choose from, as well as an option to create custom ones.

#### Filtri¶

The default filters that can be selected are:

  * My Attendances: this filter only presents the user’s attendance data.

  * My Team: this filter presents the attendance data for the user’s team.

  * At Work: this filter displays the attendance data for everyone currently checked in.

  * Errors: this filter displays any entries with errors that need to be resolved.

  * Check In: this filter has a drop-down to further select a specific time period. Select the desired time period from the options presented, a specific month, quarter, or year.

  * Last 7 days: this filter presents the attendance data for the last seven days.

  * Add Custom Filter: create a custom filter using the pop-up that appears when this is selected.




#### Gruppi¶

The default groups that can be selected are:

  * Check In: this grouping presents a drop-down menu containing the following time period options: Year, Quarter, Month, Week, and Day. Selected the time period to display all the check-in information, grouped by the selected time period.

  * Employee: this group presents the attendance data organized by employee.

  * Check Out: this grouping presents a drop-down menu containing the following time period options: Year, Quarter, Month, Week, and Day. Selected the time period to display all the check-out information, grouped by the selected time period.

  * Add Custom Group: this option displays a drop-down menu with a variety of options to group the attendance data by, including City, Country, Mode, and IP Address.




### Attendance log details¶

Odoo captures various time and location details when a user checks in and out. The specific details provided are determined by the method the user checked in and out.

To view the specific check in and/or check out details for an employee, click on an individual entry in the overview dashboard.

A detailed attendance log for the user appears in a pop-up window. To close the detailed attendance log, click the Save & Close button in the bottom-left corner of the form.

The detailed attendance log contains the following information:

#### Main details¶

  * Employee: the name of the employee.

  * Check In: the date and time the employee checked in.

  * Check Out: the date and time the employee checked out. This only appears if the employee has checked out.

  * Worked Hours: the total amount of time the employee logged for the day, in an hour and minute format (HH:MM). This value calculates all the checks in and check outs for the day, if the employee checked in and out multiple times.

  * Extra Hours: any extra hours the employee logged that is beyond their expected working hours.




#### Check in/check out details¶

The following information appears for both the Check In and Check Out sections.

  * Mode: the method with which the attendance information was gathered. Systray is displayed if the employee logged in and out [directly from the database](attendances/check_in_check_out.html#attendances-check-in), Manual is displayed if the employee logged in and out [using an attendance kiosk](attendances/kiosks.html#attendances-kiosk-mode-entry).

  * IP Address: the IP address for the computer the employee used to log in or out.

  * Browser: the web browser the employee used to log in or out.

  * Localization: the city and country associated with the computer’s IP address.

  * GPS Coordinates: the specific coordinates when the user logged in or out. To view the specific coordinates on a map, click the → View on Maps button beneath the GPS Coordinates. This opens a map in a new browser tab, with the specific location pointed out.




### Errori¶

Entries that contain an error appear on the overview dashboard in red. In the Gantt view, the entry appears with a red background. If in the List view, the entry text appears in red.

An error typically occurs when an employee has checked in but has not checked out within the last 24 hours, or when an employee has a check in and check out period spanning over 16 hours.

To fix the error, the attendance entry must be modified or deleted. Click on the entry to reveal a pop-up containing the details for that particular entry. To modify the Check In and/or Check Out information, click on the Check In or Check Out field and a calendar selector appears. Click on the desired date, then use the time selector beneath the calendar to select the specific time for the entry. When the information is correct, click Apply.

When all the information on the pop-up is correct, click Save & Close. When the entry no longer has an error, the entry appears in gray instead of red.

To delete an entry, click Remove on the pop-up instead of making modifications to the entry.

## Rendiconto¶

To view attendance reports, click Reporting in the top menu. The default report displays each employee’s attendance information for the past 3 months, in a Line Chart.

The default view is a Graph. To view the data in a pivot table, click the Pivot Table button on the top right of the report. To switch back to the graph view, click the Graph button, located next to the Pivot Table button.

To present different information, adjust the filters and groups in the same way as in the Overview dashboard.

The data can be presented in either a Bar Chart, Line Chart, Pie Chart, Stacked chart, or in Descending or Ascending order. To change the view to any of these charts, click the corresponding button above the displayed chart.

To change the Measures, click the Measures button and select the desired measure from the drop-down menu.

The report can also be inserted into a spreadsheet. Click the Insert in Spreadsheet button and a pop-up appears. Select the desired spreadsheet, and click Confirm.

Vedi anche

  * [Check in and out](attendances/check_in_check_out.html)

  * [Kiosks](attendances/kiosks.html)

  * [Hardware](attendances/hardware.html)




  * [Check in and out](attendances/check_in_check_out.html)
  * [Kiosks](attendances/kiosks.html)
  * [Hardware](attendances/hardware.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/attendances.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](attendances/check_in_check_out.html "Check in and out") |
  * [precedente](../hr.html "Human resources") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Presenze


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