# Recruitment analysis — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](time_in_stage.html "Time in stage analysis") |
  * [precedente](source_analysis.html "Source analysis reporting") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Recruitment analysis



# Recruitment analysis¶

The _Recruitment Analysis_ report allows recruiting departments to see which job positions have the most applicants, which have the most referrals, and how long it takes for applicants to move through the pipeline.

Knowing how many applicants each specific job position has, along with statistics about how many are hired and refused, can provide valuable insights. This information can assist the recruiting team to pivot their strategies to acquire the most desirable candidates.

## Recruitment analysis report¶

Start by navigating to Recruitment app ‣ Reporting ‣ Recruitment Analysis. This presents a line chart of all applicants for the last year.

Three separate color-coded metrics are presented: In Progress, Hired, and Refused.

Hover the cursor over a month of the chart, and a pop-up window appears, displaying the specific numbers for that month.

### Pivot table view¶

For a more detailed view of the information in the Recruitment Analysis report, click the __(Pivot) icon in the top-right corner. This displays all the information in a pivot table.

In this view, the job positions are displayed in the rows, and the columns display the total numbers of applicants, including how many of those applicants were hired or refused. The displayed information can be modified, if desired.

In this example, there are 17 total applicants. Out of that, three have been hired, and four refused. The Experienced Developer position has eight total applicants, two of which were hired, and two were refused.

#### Use case: applicants with referrals¶

To get a better understanding of how effective the company’s [referral program](../referrals.html) is, the Recruitment Analysis report can be modified to show how many applicants were referred by current employees.

From the __(Pivot) view of the Recruitment Analysis report, first click the Measures button to reveal a drop-down menu of options.

Click both Has Referrer and Count, to activate those two measures. Then, click # Applicant, # Hired, and # Refused to deactivate those default measures.

Now, the column displays the number of applicants that came from a referral in the Has Referrer column, and the total number of applicants in the Count column.

In this example, the Experienced Developer job position has the most applicants from referrals. Out of the eight applicants, six have applied through a referral from a current employee. Meanwhile, the Marketing and Community Manager job position has the least amount of referrals out of the total applicants, only one out of six.

##### Hired through referrals¶

It is possible to modify this report even further to see how many referred applicants end up being hired.

To view this data, click on a __[job position] row, which reveals a drop-down menu. Then, click State to show the various states applicants are currently in.

Nota

Only states that have applicants in them are shown for each job position. If a state does **not** have any applicants, it does not appear in the list.

To expand the other rows, and display the various states, click on the __[job position] button.

In this example, the Experienced Developer job position is the most successful in terms of referrals. Both of the hired employees came from internal referrals. Meanwhile, there have been no hired employees for the Chief Executive Officer position, and the only hired employee for the Marketing and Community Manager was not referred by an employee.

In this scenario, it is possible to determine that the current software developers are providing the most referrals, with the highest success rate.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/recruitment_analysis.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](time_in_stage.html "Time in stage analysis") |
  * [precedente](source_analysis.html "Source analysis reporting") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Recruitment analysis


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