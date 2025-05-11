# Live Session surveys — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](analysis.html "Survey analysis") |
  * [precedente](questions.html "Create questions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Sondaggi](../surveys.html) »
  * Live Session surveys



# Live Session surveys¶

With the Odoo _Surveys_ application, users can enhance in-person demonstrations and presentations with the _Live Session_ feature.

_Live Session_ surveys function the same way as a normal survey, but with a host or moderator, who presents the questions to participants, reveals their responses in real-time, and controls the tempo of the survey.

In _Live Session_ surveys, participants access the survey experience via a custom URL, and sign in with an optional access code. When the survey has begun, the host presents one question at a time.

Then, the audience of participants submit their answer, either via their computer or mobile device, and once the responses have been gathered, the host reveals all the participant’s responses, in real time, with each answer’s results displayed as a bar graph.

## Create Live Session survey¶

To create a _Live Session_ survey, begin by opening the _Surveys_ application. From the Surveys dashboard, click the New button to reveal a blank survey form.

Any of the survey type options (Survey, Live Session, Assessment, or Custom), presented as radio buttons at the top of the survey, can be used to create a _Live Session_.

However, selecting the Live Session survey type radio button streamlines the process because Odoo auto-selects the optimal settings and options for a _Live Session_ survey when that option is selected.

Importante

If the Is a Certification option is enabled in the Options tab, the survey **cannot** be used as a _Live Session_ survey.

With the desired survey radio button option selected, proceed to [create a survey](create.html) with [questions and sections](questions.html).

While creating questions for the _Live Session_ survey, open the Options tab on the Create Sections and Questions pop-up form, in order to reveal the Live Sessions section, which only has one available feature: Question Time Limit.

When the Question Time Limit option is enabled, a new field appears beside it, wherein the user **must** enter the desired amount of time (in seconds) the participant gets to answer the question.

### Options tab¶

After the questions have been created for the _Live Session_ survey, open the Options tab of the survey form to further configure the survey.

The Options tab is organized into four sections: Questions, Time & Scoring, Participants, and Live Session.

#### Questions section¶

Regardless of the option selected for the Pagination field, the _Live Session_ survey _only_ shows One page per question, and will default to that option when the Create Live Session button is clicked, and a _Live Session_ survey officially begins.

Nota

The One page per question option in the Pagination field is selected by default, and no other options appear in the Questions section, when the Live Session survey type radio button is selected.

The Display Progress as and Question Selection options are still viable and active options for _Live Session_ surveys, if desired, but they are **not** required.

However, the Allow Roaming feature is **not** available during _Live Session_ surveys whatsoever, as the host/moderator controls the survey, and participants have no control over what question they see, or when they see it.

#### Time & Scoring section¶

The Survey Time Limit option is **not** applicable for _Live Session_ surveys. This option does not even appear in the Time & Scoring section of the Options tab if the Live Session survey type radio button option is selected.

Nota

While the Survey Time Limit option is not applicable for _Live Session_ surveys, each question _can_ be affixed with its own _Question Time Limit_ , via the _Options_ tab of the question pop-up form. Those question-specific time limits _do_ work with _Live Session_ surveys.

If desired, any Scoring option, and subsequent Required Score (%) option are available to use with _Live Session_ surveys.

However, if the Is a Certification option is enabled, the survey **cannot** be used as a _Live Session_ survey. The Is a Certification option does **not** appear in the Time & Scoring section of the Options tab if the Live Session survey type radio button option is selected.

#### Participants section¶

The Access Mode field is set to the Anyone with the link option when the survey is used as a _Live Session_. The Anyone with the link option **cannot** be modified if the Live Session survey type radio button option is selected.

The Require Login option is available for _Live Session_ surveys. However, if the Live Session survey type radio button option is selected, the usual Limit Attempts field that appears when Require Login is enabled does **not** appear, as live session participants only get to attempt the survey once, as the host leads them through it.

#### Live Session section¶

The Session Code field allows users to create unique codes for participants to use, in order to gain access to the _Live Session_ survey. This code can consist of any combination of letters, numbers, and/or symbols.

The Session Code field is **not** required, however, it is encouraged because it adds a level of exclusivity to the survey and, without a Session Code, the URL that appears in the following Session Link field becomes far more complex.

Importante

If a Session Code is **not** entered, participants can access the survey, via the Session Link without needing a host, and the fundamental elements of the _Live Session_ are lost, as the survey is then just a normal questionnaire, without any real-time results.

With a Session Code, the URL in the non-modifiable Session Link field is simplified, and ends with the Session Code, preceded by `/s/`.

Example

If `1212` has been entered as the Session Code, the URL in the Session Link field begins with the basic URL of the database (e.g. `sample-database.odoo.com`), followed by: `/s/1212`.

So, collectively, that sample Session Link would be: `sample-database.odoo.com/s/1212`.

Suggerimento

If a user sends out the Session Link URL in its complete form - Session Code and all - participants would _not_ need to enter in a code, as it would already be entered for them. That complete link places the participant in a virtual waiting room, where they simply need to wait for the host to officially start the _Live Session_ survey.

If a user sends out the Session Link URL - _except_ for the Session Code at the end (i.e. the entire URL _through_ `.../s/`) - participants would be taken to a page, wherein they would need to enter the specific Session Code in order to access the _Live Session_.

If any Scoring option has been enabled, the opportunity to Reward quick answers is also available with _Live Session_ surveys.

## Start Live Session surveys¶

Once all the questions and configurations are complete, users can click the Create Live Session button at the top of the survey form. Doing so opens a new browser tab to the _Session Manager_.

When the Create Live Session button has been clicked, and the _Live Session_ has begun, a new Open Session Manager button appears on the survey form, which opens a new browser tab to the _Session Manager_. If the _Live Session_ has already begun, that button leads the user to the question or section the _Live Session_ is currently on.

Additionally, a Close Live Session button appears on the survey form. When that button is clicked, the _Live Session_ survey closes.

The _Session Manager_ is controlled by the host/moderator of the _Live Session_ survey, and is typically shown on a projection or screen, so the participants can collectively view the questions and real-time responses, as the host/moderator guides them through the _Live Session_.

Nota

The participant can see and answer the questions from their computer or mobile device, but the results and real-time responses can **only** be seen on the _Session Manager_.

Initially, the _Session Manager_ shows the title of the _Live Session_ survey, the link needed to access it, and a Waiting for attendees… counter, which populates as participants enter the _Live Session_ survey.

Once the desired amount of participants have entered the _Live Session_ survey, the host/moderator can click the Start button on the right side of the _Session Manager_ window to begin the _Live Session_.

Nota

If the survey begins with a section title on the survey form, that section title appears in the _Session Manager_ , and the participant’s view of the survey informs them to `Pay attention to the host screen until the next question`. This message appears whenever a section title appears during a _Live Session_.

When the first question appears on the survey, the _Session Manager_ shows the question above an empty bar graph, showing the potential answer options on the x-axis. The participants see the question and selectable answer options on their computer or mobile device.

As participants submit their answers, a progress bar, in the upper-left corner of the _Session Manager_ , fills in. This is how _Live Session_ hosts/moderators know when every participant has submitted their responses.

Then, when the desired amount of participants have submitted their responses, the host/moderator clicks the Show Results button on the right side of the _Session Manager_ to reveal the collective real-time responses on the bar graph.

Once the host/moderator feels like the participants have had enough time to view the real-time results, via the populated bar graph, they can click the Show Correct Answer(s) button on the right side of the _Session Manager_ window. Doing so highlights the correct response, if one has been designated, in green. All incorrect responses are highlighted in red.

When the host/moderator feels the participants have had enough time to take in the correct and incorrect responses, via the bar graph on the _Session Manager_ , they can click the Next button to move on to the next portion of the survey.

Repeat this process until the survey is complete.

Vedi anche

  * [Create surveys](create.html)

  * [Create questions](questions.html)

  * [Scoring surveys](scoring.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/surveys/live_session.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](analysis.html "Survey analysis") |
  * [precedente](questions.html "Create questions") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Sondaggi](../surveys.html) »
  * Live Session surveys


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
  *[POS]: Point Of Sale
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
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate