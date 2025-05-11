# Campaign metrics — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](campaign_templates.html "Campaign templates") |
  * [precedente](testing_running.html "Testing/running campaigns") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign metrics



# Campaign metrics¶

_Campaign metrics_ are detailed statistics and analytics within a marketing campaign, measuring its success and effectiveness. Triggered marketing activities populate relevant activity blocks with real-time metrics, in the campaign detail form.

## Activity analytics¶

In the Workflow section of a campaign detail form in the _Marketing Automation_ app, where the various campaign activities are located, a collection of useful data can be found on every individual activity block, like number of communications Sent, percentage of messages that have been Clicked, and more.

To the left of the activity block, the configured [trigger time](workflow_activities.html) is displayed as a duration (either Hours, Days, Weeks, or Months) if it corresponds to period after the workflow begins.

Nota

If the trigger time is dependent on another activity or triggering action (e.g. Mail: Replied, etc.) the time is displayed, along with the necessary action for that activity to be activated (e.g. `Replied after 2 Hours`).

In the activity block, an icon represents each activity type. An ✉️ (envelope) icon means the activity is an email. Three tiny, interlocking ⚙️ (gear) icons means the activity is an internal action. And, a small, basic 📱 (mobile) icon means the activity is an SMS.

Suggerimento

The activity type name is also displayed in smaller font below the activity title.

Beside the activity icon, at the top of the activity block, is the title of the activity. To the right of the activity title, there are Edit and Delete buttons.

Click Edit to open the Open: Activities pop-up form for that specific activity, in which that activity can be modified. Click the Delete button to completely delete that specific activity from the workflow.

Vedi anche

[Campaign workflow activities](workflow_activities.html)

### Activity graph tab¶

In every activity block, the Graph (pie chart icon) tab is open by default, displaying related metrics as a simple line graph. The success metrics are represented in `green` and the rejected metrics are represented in `red`.

Numerical representations of both Success and Rejected activities are shown to the right of the line graph.

Suggerimento

Hovering over any point in the line graph of the activity block reveals a notated breakdown of data for that specific date.

Beneath the graph in the activity block, for _Email_ or _SMS_ activity types, a line of accessible data figures provide a bird’s eye view of the campaign activity, including: Sent (numerical), Clicked (percentage), Replied (percentage), and Bounced (percentage).

Suggerimento

Clicking any of those stats on the DETAILS line, beneath the line graph, reveals a separate page containing every specific record for that particular data point.

### Activity filter tab¶

Next to the Graph tab on the activity block, there’s the option to open a Filter tab (represented by a filter/funnel icon).

Clicking the Filter tab on an activity block, reveals what the specific filters are for that particular campaign activity, and how many records in the database match that specific criteria.

Suggerimento

Clicking the records link beneath the displayed filter reveals a separate pop-up window containing a list of all the records that match that specific campaign activity rule(s).

## Link tracker¶

Odoo tracks all URLs used in marketing campaigns. To access and analyze those URLs, navigate to Marketing Automation app ‣ Reporting ‣ Link Tracker. Doing so reveals a Link Statistics page, wherein all campaign-related URLs can be analyzed.

The default view on the Link Statistics page is the Bar Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Pie Chart.

Beside that, there is also the option to view the statistics as Stacked, and the data can be put into Descending or Ascending order.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Number of Clicks or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

## Monitoraggi¶

Odoo tracks all activities used in every marketing campaign. The data related to these activities can be accessed and analyzed in the Traces page, which can be found by navigating to Marketing Automation app ‣ Reporting ‣ Traces.

The default view on the Traces page is the Bar Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Pie Chart.

At the top of the graph, there’s a color key, informing the user which activities have been Processed, Scheduled, and Rejected. There’s also an outline indicator to inform users of the Sum of certain activities, as well.

Beside the various view option in the upper-left corner of the Traces page, there is also the option to view the statistics as Stacked, and the data can be put into Descending or Ascending order.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Document ID or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

## Partecipanti¶

Odoo tracks all participants related to every marketing campaign. The data related to these participants can be accessed and analyzed in the Participants page, which can be found by navigating to Marketing Automation app ‣ Reporting ‣ Participants.

The default view on the Participants page is the Pie Chart view, but there are different view options available in the upper-left corner. There is the option to view the statistics as a Line Chart or Bar Chart.

At the top of the graph, there’s a color key that describes the type of participants found in the graph.

To the far-left of the view options, there is the Measures drop-down menu. When clicked, the options to view the Record ID or total Count are available. And, to the right of the Measures drop-down menu, there’s the ability to add any data to a spreadsheet by clicking the Insert in Spreadsheet button.

Also, in the upper-right corner of the Link Statistics page, to the far-right of the search bar, there are additional view options to choose from: the default Graph view, the Pivot table view, and the List view.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/marketing_automation/understanding_metrics.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](campaign_templates.html "Campaign templates") |
  * [precedente](testing_running.html "Testing/running campaigns") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Campaign metrics


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