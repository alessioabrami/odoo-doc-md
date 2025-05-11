# Banco registrazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](revenues_report.html "Revenues report") |
  * [precedente](event_tracks.html "Event tracks") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Banco registrazioni



# Banco registrazioni¶

Use the _Registration Desk_ feature in Odoo **Events** to grant access to registered event attendees as they arrive, and store attendee-related data in the reporting metrics.

## Registration Desk page¶

On a mobile device (on the Odoo app or in a browser), open the Events app, and click the Registration Desk to view the Registration Desk page.

At the bottom of the Registration Desk box, there are options to either Scan a badge or Select Attendee.

## Scansiona un badge¶

Scan the codes present on event attendee badges, by navigating to Events app ‣ Registration Desk, and selecting the Scan a badge option.

Importante

Odoo **must** be granted access to the camera being used for the Scan a badge option to work.

Once Odoo has access to the camera, a Barcode Scanner pop-up window appears, showing the camera’s point-of-view. There is also a specified view finder box present, whose size can be manually modified, accordingly, using the __(crop) icon.

When the badge code is in the middle of the view finder box, the code is scanned, the Barcode Scanner pop-up window disappears, and the attendee is granted access to the event. Once the code is scanned, their attendance is logged in the Odoo **Events** app.

If the barcode being scanned is invalid, an error pop-up message appears in the upper-right corner.

## Select attendee¶

Manually grant access to event attendees, by navigating to Events app ‣ Registration Desk, and selecting the Select Attendee option.

Odoo reveals an Attendees page, with all the attendees for every event in the database, in a default __ Kanban view.

On the Attendees page, each attendee card displays that person’s name, which event they are registered to attend, their associated company (if applicable), what ticket tier they purchased (if applicable), along with two buttons: a __(checkmark) and __(counter-clockwise arrow).

To grant access to a person, marking them as attended, click the __(checkmark) button on that attendee’s card.

Click the __(counter-clockwise arrow) button on an attendee’s card to undo the previous action.

Suggerimento

It is recommended to use an event-specific filter on the Attendees page, via the search bar drop-down menu.

To do that, click the __(down arrow) beside the seach bar to reveal a drop-down menu with Filters, Group By, and Favorites options.

For example, click the Event option, in the Group By column. Then, click away to remove the drop-down menu. Odoo reveals the Attendees page with event-specific columns, allowing users to locate specific event attendees.

Vedi anche

[Cercare, filtrare e raggruppare i record](../../essentials/search.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/events/registration_desk.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](revenues_report.html "Revenues report") |
  * [precedente](event_tracks.html "Event tracks") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Eventi](../events.html) »
  * Banco registrazioni


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