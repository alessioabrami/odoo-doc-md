# Skills evolution — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../frontdesk.html "Reception") |
  * [precedente](appraisal_analysis.html "Appraisal analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Skills evolution



# Skills evolution¶

In Odoo’s **Appraisals** app, it is possible to view employee’s skills as they progress over time in the Skills Evolution report, also known as the _Appraisal Skills Report_.

Managers can use this to see who is achieving their various skill goals set on their appraisals, who is meeting their skill deadlines, who has the highest performance in terms of skill development, and more.

The _Skills Evolution_ report also provides the ability to search for employees with specific skills at certain levels, which can be helpful for scenarios where specific skills are required.

## Skills evolution report¶

To access this _Skills Evolution_ report, navigate to Appraisals app ‣ Reporting ‣ Skills Evolution.

Doing so reveals the Appraisal Skills Report page, which displays a report of all skills, grouped by employee, in alphabetical order, by default.

Nota

Skill levels are **only** updated after an appraisal is marked as done. Any skill level changes from ongoing appraisals that have **not** been finalized are **not** included in this report.

All the Employee lines are expanded, with all the various skill types nested below. Each individual skill type is collapsed, by default. To view the individual skills contained within a skill type, click anywhere on the skill type line to expand the data.

Each skill has the following information listed:

  * Employee: the name of the employee.

  * Skill Type: the category the skill falls under.

  * Skill: the specific, individual skill.

  * Previous Skill Level: the level the employee had previously achieved for the skill.

  * Previous Skill Progress: the previous percentage of competency achieved for the skill (based on the Skill Level).

  * Current Skill Level: the current level the employee has achieved for the skill.

  * Current Skill Progress: the current percentage of competency achieved for the skill.

  * Justification: any notes entered on the skill, explaining the progress.




The color of the skill text indicates any changes from the previous appraisal. Skill levels that have increased since the last appraisal appear in green, as an _Improvement_. Skill levels that have **not** changed appear in black, as _No Change_. Skills that have regressed appear in red, as _Regression_.

This report can be modified to find specific information by adjusting the [filters](../../essentials/search.html#search-filters) and [groupings](../../essentials/search.html#search-group) set in the search bar at the top.

## Use case: Identify employees with specific skills¶

Since the Appraisal Skills Report organizes all skills by employee, it can be difficult to find employees with a specific skill at a specific level. To find these employees, a custom filter must be used.

In this example, the report is modified to show employees with an expert level of Javascript knowledge. To view only those employees, first remove all active filters in the search bar.

Next, click the __(down arrow) icon in the search bar, then click Add Custom Filter beneath the __ Filters column to load an Add Custom Filter pop-up window.

Using the drop-down menu in the first field, select Skill. Then, keep the second field as-is, and select Javascript from the third drop-down menu in the third field.

Next, click New Rule, and another line appears. In this second line, select Current Skill Level for the first drop-down field, leave the second field as-is, then select Expert for the third drop-down field.

After the New Rule button is clicked, the word «any» in the sentence Match any of the following rules:, changes from plain text into a drop-down menu. Click the __(down arrow) icon after the word any, and select all.

Finally, click the Add button.

Now, only employees that have an Expert level for the skill Javascript appear. In this example, only Marc Demo meets these criteria.

Vedi anche

  * [Odoo essentials reporting](../../essentials/reporting.html)

  * [Cercare, filtrare e raggruppare i record](../../essentials/search.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/appraisals/skills_evolution.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../frontdesk.html "Reception") |
  * [precedente](appraisal_analysis.html "Appraisal analysis") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Skills evolution


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