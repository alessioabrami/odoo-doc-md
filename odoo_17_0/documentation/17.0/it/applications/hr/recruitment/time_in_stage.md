# Time in stage analysis — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](team_performance.html "Team performance reporting") |
  * [precedente](recruitment_analysis.html "Recruitment analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Time in stage analysis



# Time in stage analysis¶

The _Time In Stage Analysis_ report provides information on how long applicants stay in each stage of the recruitment process. This is important, as every job position has specific [process details](new_job.html#recruitment-new-job-position-edit) that state the length of time applicants should expect to wait between specific stages.

Knowing how long applicants remain in each stage can help highlight possible bottlenecks. Analyzing this data allows the recruitment team to assess each stage, identify any issues, and pivot their strategies to move applicants through each stage, within the expected time interval.

## Time in stage analysis report¶

To access the report, navigate to Recruitment app ‣ Reporting ‣ Time in Stage Analysis. By default, the report displays data from all job positions, with the stages populating the x-axis, and the number of days populating the y-axis, in a __(Line Chart).

The default filter is Last 365 Days Applicant, showing information for the last 365 days.

Hover over a stage in the line chart to reveal a popover window listing all the job positions within it, and the average number of days each job position sits in each stage.

For a more visually digestible view of the information in the Time In Stage Analysis report, click the __(Bar Chart) icon in the upper-left corner. This displays all the information in a bar chart.

In this view, it is easier to visualize the differences between the job positions, regarding how long applicants stay in each stage. From this view, recruiters can more easily determine which job positions have delays or bottlenecks at certain stages.

### Use case: comparing times by month¶

With the Time In Stage Analysis report, it is possible to see if there are certain months where applicants take longer to be moved through the pipeline. To view this data, switch to the __(Pivot) view in the upper-right corner.

This presents the data in a detailed pivot table, with the rows representing the different job positions, and the columns representing the stages. The average Days in Stage populates the various boxes.

Nota

If a field is empty, it indicates no applicant has been in that stage. Instead, all applicants moved from a previous stage without being placed in the stage with an empty field.

Click __ Total above the job position rows to collapse the information. Next, click __ Total again, revealing a drop-down menu. Click Add Custom Group __at the bottom of the list, revealing further grouping options. Click Start Date from the expanded list.

After doing so, the data presented is grouped with the various months from the previous 365 days for the rows, leaving the Days In Stage as the columns.

In this example, July 2024 had the longest time that applicants spent in each stage, on average. In addition, the Contract Proposal stage had the longest wait time in July, with an average of 31.62 days in that stage.

While this report does not display the reasons applicants stayed in the various stages for these lengths of time, it can be helpful to know when delays occur.

Vedi anche

[Essentials reporting documentation](../../essentials/reporting.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/time_in_stage.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](team_performance.html "Team performance reporting") |
  * [precedente](recruitment_analysis.html "Recruitment analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Time in stage analysis


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