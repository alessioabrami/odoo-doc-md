# Testing/running campaigns — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](understanding_metrics.html "Campaign metrics") |
  * [precedente](workflow_activities.html "Campaign workflow activities") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Testing/running campaigns



# Testing/running campaigns¶

The Odoo _Marketing Automation_ app allows users to test marketing campaigns (and mailings) before officially running them to check for errors and correct any mistakes before it reaches its target audience.

## Test campaigns¶

To test a marketing campaign, open the Marketing Automation app, and select the desired campaign to test, which reveals the campaign’s detail form.

On the campaign detail form, make sure the campaign already has activities configured in the workflow (or build a campaign by following the directions on [Campaign workflow activities](workflow_activities.html) documentation).

Nota

Testing marketing automation campaigns is meant to be performed in the production version of the database. Duplicate (or trial) databases have limited email sending capabilities.

To start a test, click the Launch a Test button at the top of the campaign form, to the right of the Start button.

When clicked, a Launch a test pop-up window appears.

In the Launch a test pop-up window, click the Pick or create a/an Contact to generate a Test Participant field to reveal a drop-down menu of contacts. From this drop-down menu, select an existing contact (or create a new one) to run the test on.

Nota

Only one contact can be selected from the Launch a test pop-up window.

To create a new contact directly from the Launch a test pop-up window, start typing the name of the new contact in the blank field, and click Create and edit….

Doing so reveals a blank Create Record pop-up form, in which the necessary contact information (Email, Mobile, etc.) _must_ be entered, in order for the test to work. When the necessary information is entered, click Save & Close.

When all the necessary fields have been entered, click Save & Close to return to the Launch a test pop-up window.

Once a contact is selected, click Launch to reveal the campaign test page.

On the campaign test page, the name of the Record being tested is visible, along with the precise time this test workflow was started in the Workflow Started On field. Beneath that, in the Workflow section is the first activity (or activities) in the workflow that’s being tested.

To start a test, click the Run button, represented by a ▶️ (play button) icon beside the first activity in the workflow. When clicked, the page reloads, and Odoo shows the various results (and analytics) connected to that specific activity as they occur, in real-time.

Nota

If a child activity is scheduled beneath a parent activity, that child activity will be revealed slightly indented in the workflow, once that parent activity has been run, via the ▶️ (play button) icon.

Once all the workflow activities are completed, the test ends, and the status bar (in the upper-right corner) moves to the Completed stage.

To stop a test before all the workflow activities are completed, click the Stop button in the upper-left corner of the campaign test page.

## Run campaigns¶

To run a campaign, navigate to Marketing Automation app, and select the desired campaign to run.

On the campaign detail form, with all the desired activities ready in the Workflow section, click Start in the upper-left corner to officially run the campaign to the configured target audience specified on the campaign detail form.

Clicking Start launches the campaign, and the status bar of the campaign switches to Running, which is located in the upper-right corner of the campaign detail form.

Nota

If some participants are already running on a campaign, and was stopped for any reason, clicking the Start button again prompts a pop-up warning. This warning advises the user to click an Update button to apply any modifications made to the campaign.

Be aware that participants that had already gone through an entire campaign in its original state **can** be reintroduced into the newly-modified campaign, and new traces could be created for them.

Then, as the mailings and actions are triggered in the Workflow, the various stats and data related to each activity appear in each activity block. There is also a series of stat-related smart buttons that appear at the top of the campaign detail form, as well.

These analytical smart buttons will _also_ populate with real-time data as the campaign progresses: Templates, Clicks, Tests, Participants.

## Stop campaigns¶

To stop a campaign that’s currently running, navigate to the Marketing Automation app, and select the desired campaign to stop. On the campaign detail form, click the Stop button in the upper-left corner.

When clicked, the campaign is officially stopped, and the status changes to Stopped in the upper-right corner of the campaign detail form.

Vedi anche

  * [Campaign configuration](../marketing_automation.html)

  * [Audience targeting](target_audience.html)

  * [Campaign workflow activities](workflow_activities.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/marketing_automation/testing_running.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](understanding_metrics.html "Campaign metrics") |
  * [precedente](workflow_activities.html "Campaign workflow activities") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Testing/running campaigns


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