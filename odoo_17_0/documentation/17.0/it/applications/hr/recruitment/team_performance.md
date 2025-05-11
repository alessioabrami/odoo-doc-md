# Team performance reporting — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../referrals.html "Referral dipendenti") |
  * [precedente](time_in_stage.html "Time in stage analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Team performance reporting



# Team performance reporting¶

The _Team Performance_ report in the **Recruitment** app shows how many applicants each recruiter is managing.

This information is determined by the individuals populating the [Recruiter](add-new-applicants.html#recruitment-applicant-details) field on each applicant form.

## Open report¶

To access the _Team Performance_ report, navigate to Recruitment app ‣ Reporting ‣ Team Performance.

The number of In Progress, Hired, and Refused applicants for each recruiter is displayed in the __(Graph) view.

The information shown is for the __ Last 365 Days Applicant default filter, as displayed in the search bar.

Hover the cursor over any column to view a popover window, displaying the specific details for that column.

### Pivot table view¶

For a more detailed view of the information in the Team Performance report, click the __(Pivot) icon in the top-right corner. This displays all the information in a pivot table.

In this view, the job positions are displayed in the rows, while the columns display the total number of applicants. The applicants are further organized by # Applicant (in process), # Hired, and # Refused.

The displayed information can be modified, if desired.

In this example, there are 19 total applicants. Out of those 19, eight have been hired, and three refused.

From the data presented, the Experienced Developer job position is the most successful. This job position has the highest number of total applicants, as well as the most hires. In addition, the Experienced Developer has the least amount of refused applicants.

This pivot table also shows that the Chief Executive Officer position is the hardest to fill, as it has the fewest total applicants.

## Use case: recruiter performance over time¶

One way to modify this report is to show how recruiters are performing over time. To show this information, begin with the Team Performance report in the __(Pivot) view.

Next, click the __(down arrow) in the search bar, revealing a drop-down menu. Click Add Custom Group __at the bottom of the __ Group By column, then click Recruiter. Click away from the drop-down menu to close it. Now, each row on the table represents a recruiter.

To compare the team’s performance over different time periods, click the __(down arrow) in the search bar. Click Start Date __in the __ Filters column, revealing various time periods to select.

In this example, the desired data is the comparison between the team’s performance in the third quarter (June - August) and the second quarter (April - July). To do so, click Q3. Once clicked, the current year is also ticked. In this example, it is 2024.

After making this selection, a __ Comparison column appears. Click Start Date: Previous Period to compare the third quarter with the second quarter, for the various recruiters.

From this report, several things can be extrapolated: the total number of applicants increased, the number of hired applicants remained the same, while the number of refused applicants decreased.

Additionally, Jane Jobs had the highest increase in number of applicants during the third quarter, but her number of hired applicants went down 67%. The recruiter with the best overall numbers was Rose Recruiter, who had both their active applicants and hired applicants, increase in the third quarter, while their refused applicants went down.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/team_performance.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../referrals.html "Referral dipendenti") |
  * [precedente](time_in_stage.html "Time in stage analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Team performance reporting


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