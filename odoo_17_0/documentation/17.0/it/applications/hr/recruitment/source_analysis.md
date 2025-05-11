# Source analysis reporting — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recruitment_analysis.html "Recruitment analysis") |
  * [precedente](refuse_applicant.html "Refuse applicants") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Source analysis reporting



# Source analysis reporting¶

Reporting is a critical tool used by recruiting departments to gain insights into the entire recruitment process.

Determining where applicants come from can provide information about which sources have the best results. This information is determined by the _Source Analysis_ report. With this data, recruitment teams can better pivot their recruiting strategies to gain better applicants, in both quantity and quality.

## Open report¶

To access the _Source Analysis_ report, navigate to Recruitment app ‣ Reporting ‣ Source Analysis.

This presents the data for the __ Last 365 Days Applicant, in a default __(Graph) view, showing the amount of applicants by Source, and further separated by stage (In Progress and Hired)

Hover the cursor over any column to view the specific numbers fort that column.

To view more details, view the Source Analysis report in a pivot table. To do so, click the __(Pivot) icon in the top-right corner. The data is presented in a pivot table, with rows populated by job positions, and columns populated stages.

## Source effectiveness report¶

To identify which sources (e.g., job boards, social media, employee referrals, company website) produce the most hires, the pivot table view of the Source Analysis report can be configured to display further details.

To expand this chart to show what specific sources the applicants came from, click the __ Total box above the columns, to reveal a drop-down menu, and click Source.

Each column is then grouped by the source, such as: Search engine, Facebook, Newsletter, etc. Each source displays a separate count for Applicant, Hired, and Refused.

This information, as presented, makes it difficult to view the specific numbers for each source. Click the __(Flip axis) icon, to swap the information. After that, the rows represent the source, and the columns represent the job positions, further divided by stage.

In this view, the total number of applicants, hired employees, and refused applicants, are displayed for each source, as well as for each stage by job position.

### Medio¶

Viewing the medium for the applicants can be beneficial to see which specific medium is more successful.

_Mediums_ are the specific methods the applicant used to discover and then apply for job positions, such as organic search, paid search, social media ad, email, etc.

To further group the results by medium, click into one of the __[Source] rows. Click Medium in the resulting drop-down menu. The row presents the specific mediums, relevant to that specific source.

Once Medium is selected for one source, clicking into another row automatically reveals the specific metrics for the mediums for that source.

Nota

The only mediums that appear for a source, are mediums that have been set on an applicant’s form. If a medium has **not** been set for any applicants, the medium does not appear in the drop-down rows beneath the source.

For example, if no applicants applied with the medium _Google Adwords_ , that medium does **not** appear beneath the _Search engine_ source row.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/source_analysis.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](recruitment_analysis.html "Recruitment analysis") |
  * [precedente](refuse_applicant.html "Refuse applicants") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Source analysis reporting


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