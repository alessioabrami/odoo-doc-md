# Obiettivi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appraisal_analysis.html "Appraisal analysis") |
  * [precedente](new_appraisals.html "New appraisals") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Obiettivi



# Obiettivi¶

The Odoo _Appraisals_ application allows managers to set goals for their employees. That way, employees know what to work toward before their next review.

To view all goals, navigate to Appraisals app ‣ Goals. This presents all the goals for every employee, in a default Kanban view.

Each goal card contains the following information:

  * Goal: the name of the goal.

  * Employee: the employee the goal is assigned to.

  * __(clock) icon: displays the corresponding [activity icon](../../essentials/activities.html) for the record. If no activities are scheduled, the default icon is the __(clock). If any activities have been scheduled, the icon represents the activity scheduled soonest.

  * Deadline: the due date for the goal.

  * Progress: the percentage of competency set for the goal. The options are 0%, 25%, 50%, 75%, or 100%.

  * Employee Icon: the profile icon of the employee the goal is assigned to.




If a goal is completed, a Done banner appears in the top-right corner of the goal card.

Nota

Every individual goal requires its own record for each employee. If multiple employees have the same goal, a goal card for each employee appears on the list.

For example, if Bob and Sara have the same goal of `Typing`, two cards appear in the Kanban view: one `Typing` goal for Bob, and another `Typing` goal for Sara.

## New goal¶

To create a new goal, navigate to Appraisals app ‣ Goals, and click New top-left corner to open a blank goal form.

Input the Goal, Employee, Progress, and Deadline, information on the goal card, as discussed in the goal card section of this document.

The information requested is all the same information that appears on the goal card in the Kanban view, with the addition of a Tags field and a Description tab.

Suggerimento

The _Appraisals_ application does **not** have any pre-configured tags, so all tags need to be added. To add a tag, enter the name of the tag on the line, then click Create «(tag)». Repeat this for all tags that need to be added.

The current user populates the Employee field, by default, and the Manager field populates with the manager set on the employee profile.

Make any necessary changes to the form, and add any notes that might be useful to clarify the goal in the Description tab.

## Completed goals¶

When a goal has been met, it is important to update the record. A goal can be marked as `Done` in one of two ways: from the main Goals dashboard, or from the individual goal card.

To mark a goal as `Done` from the main Goals dashboard, click on the __(vertical ellipsis) icon in the top-right of a goal card.

Nota

The __(vertical ellipsis) icon **only** appears when the mouse hovers over the top-right corner of a goal card.

Then, click Mark as Done from the resulting drop-down menu. A green Done banner appears in the top-right corner of the goal card.

To mark a goal as `Done` from the goal card itself, click on a goal card to open that goal’s form. Then, click the Mark as Done button in the top-left of the form. When clicked, a green Done banner appears in the top-right corner of the goal form.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/appraisals/goals.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](appraisal_analysis.html "Appraisal analysis") |
  * [precedente](new_appraisals.html "New appraisals") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Valutazioni](../appraisals.html) »
  * Obiettivi


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