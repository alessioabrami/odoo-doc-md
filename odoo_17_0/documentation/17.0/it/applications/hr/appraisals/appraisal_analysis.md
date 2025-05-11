# Appraisal analysis — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](skills_evolution.html "Skills evolution") |
  * [precedente](goals.html "Obiettivi") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Appraisal analysis



# Appraisal analysis¶

The **Appraisals** app has the ability to report on all the appraisals in the system, including past, present, and future appraisals, and their respective statuses. This report helps managers track scheduled appraisals, and identify any overdue or unconfirmed ones.

To access the _Appraisal Analysis_ report, navigate to Appraisals app ‣ Reporting ‣ Appraisal Analysis.

On the Appraisal Analysis page, a report loads, displaying all the appraisals in the database. Each entry is highlighted in a different color to represent their status:

Colore | Stato | Meaning  
---|---|---  
Giallo | Done | The appraisal was completed.  
Arancione | Appraisal Sent | The appraisal was confirmed, but not completed.  
Rosso | Cancelled | The appraisal was cancelled.  
Grigio | To Start | The appraisal was scheduled, but not confirmed.  
  
Nota

Appraisals are scheduled automatically (appear in gray), according to their respective [Appraisals plans](../appraisals.html#appraisals-appraisal-plan).

The report displays the current year, in a default Gantt view, grouped by department, with the current month highlighted.

To change the period of time that is presented, adjust the date settings in the top-left corner of the report by clicking the default Year to reveal a drop-down menu of options. The options to display are Day, Week, Month, and Year. Use the adjacent arrows to move forward or backward in time.

At any point, click the Today button to have the Gantt view include today’s date in the view.

To view the details of any appraisal, click on any appraisal. A pop-over window appears, displaying the due date for the appraisal. To view more details, click the View button, and further details appear in a pop-up window.

The report can have other [filters](../../essentials/search.html#search-filters) and [groupings](../../essentials/search.html#search-group) set in the search bar at the top.

## Group by status¶

When a company has a large number of employees, the default Appraisal Analysis report may display too much information to view easily. In this scenario, viewing the data by status can be beneficial.

First, remove the default __ Department grouping from the search bar. Next, click the __(down arrow) icon in the far-right of the search bar. Click Status in the __ Group By column. Click away from the drop-down menu to close it.

All the appraisals are now organized by status, in the following order: Cancelled, Done, To Start, and Appraisal Sent.

This view makes it easy to see which appraisals need to be completed, and when, as well as which appraisals still need to be confirmed.

## Use case: view only the user’s appraisals¶

When viewing the Appraisal Analysis report, it can save time to only view the appraisals the signed-in user is responsible for, and hide the rest.

To only view this data, click the __(down arrow) icon in the far-right of the search bar, revealing a drop-down menu.

Nota

It is not necessary to remove the default __ Department grouping. If it remains active, the results are grouped by department. If it is removed, the results appear in a list, alphabetically.

Click Add Custom Filter at the bottom of the __ Filters column, and a Add Custom Filter pop-up window appears.

Click into the first field, and a pop-over appears with a variety of options. Click the __(right arrow) icon after the word Employee, then scroll down and click on Manager. Next, set the middle field to = (equal). Last, click the third field and select the desired user from the list. When all the fields are set, click Add.

Now, the only appraisals that appear are the appraisals that the selected user is responsible for, instead of viewing _all_ the appraisals.

This report can also be grouped by status.

Vedi anche

  * [Odoo essentials reporting](../../essentials/reporting.html)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/appraisals/appraisal_analysis.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](skills_evolution.html "Skills evolution") |
  * [precedente](goals.html "Obiettivi") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Appraisal analysis


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