# Refuse applicants — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](source_analysis.html "Source analysis reporting") |
  * [precedente](offer_job_positions.html "Offer job positions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Refuse applicants



# Refuse applicants¶

At any point in the recruitment process, an applicant can be refused for a job position.

To refuse an applicant, start by navigating to the applicant’s card in the _Recruitment_ app. This is done in one of two ways:

  * Navigate to Recruitment app ‣ Applications ‣ All Applications. In the Applications list, click anywhere on the desired applicant’s line to open that specific applicant’s card.

  * Navigate to the main _ob Positions_ dashboard by navigating to Recruitment app ‣ Applications ‣ By Job Position. Next, click on the desired job position card, then click on the individual applicant card from the Applications page.




At the top of the applicant’s card, there are several buttons. Click the one labeled Refuse.

## Refuse reasons¶

_Refuse reasons_ allow recruiters to document why an applicant was not a good fit, and send specific refusal reason email templates to the applicant.

Clicking Refuse on an applicant’s form makes the Refuse Reason pop-up window appear.

The default refuse reasons in Odoo, and their corresponding email templates, are:

Modello e-mail | Motivo rifiuto  
---|---  
Recruitment: Refuse |  Doesn’t fit the job requirements Language issues Role already fulfilled Duplicate Spam  
Recruitment: Not interested anymore |  Refused by Applicant: don’t like job Refused by Applicant: better offer Refused by Applicant: salary  
  
Additional refusal reasons can be created, and existing ones can be modified (or deleted).

Select a refusal reason to send a refusal email.

### Create or modify refuse reasons¶

To view and configure refuse reasons, navigate to Recruitment app ‣ Configuration ‣ Applications: Refuse Reasons. Doing so reveals the Refuse Reasons page, where all the existing refuse reasons are listed.

To create a new refuse reason from the Refuse Reasons page, click the New button in the top-left corner. A blank line appears at the bottom of the list, with an empty field present in the Description column.

Type in the new refuse reason in the field. It is recommended to enter a reason that is short and concise, such as `Offer expired` or `Withdrew application`.

Then, in the Email Template field, click on the field to reveal a drop-down menu. Select an Email Template from the list to be used when this refuse reason is selected.

If a new Email Template is desired, type in the name for the new template in the field. Then, click Create and edit…, and a Create Email Template form pop-up window appears.

In the Create Email Template pop-up window, enter a Name for the form, and an email Subject in the corresponding fields.

Enter the desired email content in the Content tab. Proceed to make any other modifications to the template in the Email Configuration and Settings tabs, then click Save & Close to save the template. Upon clicking that, Odoo returns to the Refuse Reasons list.

The new template appears in the new refuse reason Email Template field.

Nota

Pre-configured recruitment refusal email templates in Odoo use dynamic placeholders, which are personalized placeholders that populate data from the applicant’s record in the email body.

For example, if the applicant’s name is a used in a dynamic placeholder, the applicant’s name appears anytime that dynamic placeholder appears on the email template.

For more detailed information on email templates, refer to the [Modelli e-mail](../../general/companies/email_template.html) documentation.

## Send refusal email¶

After clicking the Refuse button on an applicant form, a Refuse Reason can be selected from the refuse reason pop-up window. Then, two fields appear below the selected refusal reason: Send Email and Email Template.

The applicant’s email address automatically populates the Send Email field; additional email recipients **cannot** be added.

If an email should **not** be sent to the applicant, uncheck the Send Email checkbox.

The email template associated with the refusal reason populates the Email Template field. If a different email template is desired, select a different template from the Email Template drop-down menu.

To send the refusal email to the applicant, ensure the Send Email checkbox is ticked, then click Refuse at the bottom of the Refuse Reason pop-up window. The refusal email is sent to the applicant, and a red Refused banner appears on the applicant’s card in the top-right corner.

## View refused applicants¶

After refusal, the applicant’s card is no longer visible in the job position’s Kanban view. However, it is still possible to view applicants who have been refused.

To view only the refused applicants, go to Recruitment app ‣ Applications ‣ By Job Positions, or Recruitment app ‣ Applications ‣ All Applications.

On the Applications page, click the __(caret down) button in the Search… bar, then click Refused, located under the Filters section.

All applicants that have been refused for the job position appear on the Applications page for that position, organized by the stage they were in when they were refused.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/recruitment/refuse_applicant.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](source_analysis.html "Source analysis reporting") |
  * [precedente](offer_job_positions.html "Offer job positions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Selezione del personale](../recruitment.html) »
  * Refuse applicants


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