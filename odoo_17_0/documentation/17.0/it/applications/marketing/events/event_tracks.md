# Event tracks — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](registration_desk.html "Banco registrazioni") |
  * [precedente](event_booths.html "Event booths") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event tracks



# Event tracks¶

Odoo _Events_ provides the ability to create, schedule, and manage talks, lectures, demonstrations, presentations, etc., which known as _Tracks_ in Odoo.

The Odoo _Events_ application also has an option to allow event attendees to propose talks (tracks) for an event, which can then be approved (or disapproved).

## Configurazione¶

First, there are some settings that need to be enabled, in order to get the most out of event tracks.

To do that, navigate to Events app ‣ Configuration ‣ Settings, and tick the checkbox beside the Schedule & Tracks setting. Doing so provides the ability to manage and publish an event schedule with various tracks.

Also, when that setting checkbox is ticked, two additional setting options appear beneath it: Live Broadcast and Event Gamification.

The Live Broadcast option provides the ability to air tracks online through a _YouTube_ integration.

The Event Gamification options provides the ability to share a quiz with track attendees once the track is over, in order to test how much they learned.

Nota

With the Event Gamification setting enabled, an Add Quiz button appears on track forms, providing the ability to quickly create a quiz specific to the topic related to that particular track.

Once all desired settings have been enabled, be sure to click the Save button in the upper-left corner of the Settings page.

## Event Tracks page¶

To access, modify, and/or create tracks for an event, first navigate to a preconfigured event, or [create a new one](create_events.html) from the _Events_ application.

To do that, navigate to Events app, and either select a pre-existing event from the Events dashboard, or create a new one by clicking New.

Once on the desired event form, click into the Tracks smart button at the top of the form.

Suggerimento

If the Tracks smart button is not readily available, click the More __drop-down menu to reveal hidden smart buttons. Then, click Tracks from the resulting drop-down menu.

Clicking the Tracks smart button reveals the Event Tracks page for that particular event, which presents all the tracks (both scheduled and proposed) for the event, if there are any.

The tracks are presented in a default __(Kanban) view, but there is also the option to view these tracks in a __(List), __(Gantt) chart, __(Calendar), __(Graph), or __(Activity) view. All of which are accessible in the upper-right corner of the Tracks page.

In the default __(Kanban) view, the tracks are categorized into different stages. The default stages are: Proposal, Confirmed, Announced, Published, Refused (collapsed stage), and Cancelled (collapsed stage). All of which can be edited, if needed.

Suggerimento

To edit a stage, hover over the stage name, click the __(Settings) icon, and select Edit from the resulting drop-down menu.

Clicking into a track from the Event Tracks page reveals the track form for that particular track.

### Create event track¶

From the Event Tracks page, click New in the upper-left corner to reveal a blank event track form to create an event track.

Start by giving this track a Title. This field is **required** by Odoo.

Then, if desired, add an accompanying image to the track via the __(pencil) icon that appears when the cursor hovers over the __(camera) icon in the upper-right corner of the form. When clicked, proceed to upload the desired image for the track. This image appears on the front-end of the event website, on this specific tracks webpage.

Next, enter a Track Date and time for the track, and designate a Location where the talk is planning to be held.

Suggerimento

To access a complete list of locations for event tracks, which can be modified (and added to) at any time, navigate to Events app ‣ Configuration ‣ Track Locations.

Then, add a Duration to the track (in minutes).

If the _Live Broadcast_ setting has been enabled in the _Events_ app settings, the option to add a corresponding link in the YouTube Video Link field is available.

If the Always Wishlisted checkbox is ticked, the talk is automatically set as a favorite for each registered event attendee.

Assign someone to be in charge of managing this track in the Responsible field. By default, the person who initially created the track is assigned.

Then, ensure the track is applied to the correct event in the Event field. By default, this field is auto-populated with the event related to the _Event Tracks_ page the track was originally created from.

Next, choose to add existing tags, or create new ones, to further organize the track. These tags, and their corresponding tag categories are utilized on the event specific website - mainly on the _Talks_ web page on the event website, via the drop-down filter menus.

Beneath that general information section, there are three tabs: Speaker, Description, and Interactivity.

#### Speaker tab¶

The Speaker tab on an event track form is filled with various fields related to the specific speaker who is planning to conduct/host the track.

##### Contact Details section¶

In the Contact Details section, proceed to use the Contact drop-down field to select an existing contact from the database as the main point of contact for the talk.

If this contact is not yet in the database, type in the name of the contact, and click Create to create and edit the contact form later, or click Create and edit… to be taken to that new contact’s contact form, where the rest of their pertinent information can be entered.

The Contact Email and Contact Phone fields are greyed-out and populated with the information found on that chosen contact’s contact form. These fields are not modifiable once the Contact field is selected.

##### Speaker Bio section¶

In the Speaker Bio section, proceed to enter information related to the specific speaker scheduled to conduct/host the track. This section may auto-populate based on the Contact selected in the Contact Details section. If not, enter information in the necessary fields.

Nota

This information appears on the front-end of the event website, on the specific track webpage, providing more information about the speaker to the track attendees.

Start by entering a Name, Email, and Phone number for the speaker.

Next, if desired, add an image to appear alongside the speaker biogrpahy on the event website, via the __(pencil) icon that appears when the cursor hovers over the __(camera) icon. When clicked, proceed to upload the desired image for the speaker.

Then, enter a Job Position for the designated speaker, followed by the Company Name associated with the speaker.

In the Biography field, proceed to enter in a custom biography with any speaker-related information.

#### Description tab¶

The Description tab of an event track form is a blank text field, in which a description of the track can be entered. The information entered here appears on the specific track page on the event website.

#### Interactivity tab¶

The Interactivity tab on an event track form features a single option at first: Magic Button.

When the checkbox beside Magic Button is ticked, Odoo displays a _call to action_ button to attendees on the track sidebar, while the track is taking place.

With that checkbox ticked, three more options appear, all of which are related to the Magic Button:

  * Button Title: enter a title to appear on the button for attendees.

  * Button Target URL: enter a URL that leads attendees, who click the button, to a specific page.

  * Show Button: enter a number in the field, and the button will appear that number of minutes after Track start.




Nota

The magic button **only** appears if there is more than one published track.

#### Add Quiz button¶

The Add Quiz button **only** appears on event track forms if the _Event Gamification_ setting is enabled in the Odoo _Events_ settings.

To add a quiz to the event track, click the Add Quiz button. Doing so reveals a separate page where an event track quiz can be created and configured.

Start by entering a title for the quiz in the blank field at the top of the page. Then, if participants should be allowed to try the quiz multiple times, tick the checkbox beside Allow multiple tries.

The Event and Event Track fields are non-modifiable, and show the corresponding event and track this quiz is associated with.

To add questions to the quiz, click Add a line beneath the Question column. Doing so reveals a Create Questions pop-up window.

Nota

**All** track quiz questions are multiple choice.

From the pop-up window, enter the question in the blank field at the top. Then, click Add a line to add answer options. Upon clicking Add a line, a new line appears, in which an answer option can be entered.

Once an answer option has been entered, proceed to designate whether it is the Correct response, by ticking the checkbox in the Correct column.

Then, there is the option to add a point value in the Points column.

And, if there are any additional comments that should accompany an answer option, type them into the Extra Comment field.

Nota

The Correct, Points, and Extra Comment fields are all optional.

Repeat this process for all the answer options.

To remove an answer option, click the __(trash can) icon on the far-right.

Once all desired answer options (and their configurations) are complete, click Save & Close to save the question, close the pop-up window, and return to the track quiz form. Or, click Save & New to save this question, and instantly start creating another question on a new Create Questions pop-up form.

To remove any question from the quiz, click the __(trash can) icon on the far-right of the question line.

## Publish event track¶

Once all the desired configurations are complete on an event track form, click the desired stage it should be in from the status bar in the upper-right corner (e.g. Confirmed, Announced, etc.).

Nota

The stage of a track can also be changed from the Event Tracks page, where the desired track card can be dragged-and-dropped into the appropriate Kanban stage.

If an event track has _not_ been published yet, and it is moved to the Published stage, Odoo automatically publishes the track on the event website.

An event track can _also_ be published by opening the desired event track form, and clicking the Go to Website smart button. Then, in order for the track page to be viewable (and accessible) for event attendees, toggle the __ Unpublished switch at the top of the page to __ Published; thus turning it from red to green, and making it accessible for attendees.

Vedi anche

  * [Create events](create_events.html)

  * [Talks, proposals, and agenda](track_manage_talks.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/events/event_tracks.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](registration_desk.html "Banco registrazioni") |
  * [precedente](event_booths.html "Event booths") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Event tracks


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