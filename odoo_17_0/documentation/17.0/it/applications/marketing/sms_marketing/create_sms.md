# Create SMS messages — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sms_analysis.html "SMS analysis") |
  * [precedente](../sms_marketing.html "SMS Marketing") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * Create SMS messages



# Create SMS messages¶

To start, click Create on the main SMS Marketing dashboard, and Odoo reveals a blank SMS template form, which can be configured in a number of different ways.

First, give the mailing a Subject, which describes what the mailing is about.

Next, in the Recipients field, choose to whom this SMS will be sent. By default, Odoo has Mailing List selected. If this is the desired Recipients field option, specify which mailing list Odoo should send this SMS to in the Select Mailing List field.

Nota

To create (or edit) a mailing list, go to Mailing Lists ‣ Mailing List. There, Odoo displays all previously created mailing lists, along with various types of data related to that specific list (e.g. number of contacts, mailings, recipients, etc.).

To learn more about mailing lists and contacts, check out [Mailing lists and blacklists](mailing_lists_blacklists.html).

To reveal all the possible options in the Recipients field, click the field to see all the choices Odoo makes available.

When another field (other than Mailing List) is selected, the option to specify that chosen field even further becomes available — either with a default recipient filter equation that appears automatically (which can be customized to fit any business need), or, if no default recipient filter equation is present, an Add Filter button will appear.

Clicking the Add Filter button, reveals fully customizable domain rule fields, which can be configured similar to an equation. You can create multiple recipient rules, if necessary.

Then, Odoo will only send the SMS to recipients who fit into whatever criteria is configured in those fields. Multiple rules can be added.

Example

If Contact is chosen, all of the _Contacts_ records in the Odoo database (vendors, customers, etc.) will receive the SMS, by default — unless more specific recipient rules are entered.

For instance, the message below will only be sent to contacts in the database that are located in the United States (e.g. `Country` > `Country Name` equals `United States`), and they haven’t blacklisted themselves from any mailings (e.g. `Blacklist` > `is` > `not set`).

## Writing SMS messages¶

Enter the content of the SMS in the text field, found in the SMS Content tab. Links and emojis can also be included. Beneath the text field, Odoo displays how many characters are used in the message, along with how many SMS mailings it will take to deliver the complete message.

Suggerimento

To check the price of sending an SMS for a country, click on the Information icon.

Nota

Credits must be purchased from Odoo in order to take advantage of the _SMS Marketing_ app; SMS messages will not be sent without credits.

Vedi anche

[Odoo SMS - FAQ](https://iap-services.odoo.com/iap/sms/pricing)

## Track links used in SMS messages¶

When links are used in SMS messages, Odoo automatically generates link trackers to gather analytical data and metrics related to those specific links, which can be found by going to Configuration ‣ Link Tracker.

### Adjust SMS settings¶

Under the Settings tab of the SMS template, there is an option to Include opt-out link. If activated, the recipient is able to unsubscribe from the mailing list, thus avoiding all future mailings.

An employee can be designated as the Responsible in the Tracking section of the Settings tab, as well.

### Send SMS messages¶

Once a mailing is created, choose when Odoo should deliver the message from the following options:

  * Send: sends the message immediately. Consider using this option if the recipient list is highly refined, or in cases that involve fast approaching deadlines, such as a «flash sale.»

  * Schedule: choose a day (and time) for Odoo to send the mailing. This is typically the best option for mailings related to a specific event. Such a method can also be used to promote a limited-time offer, or to help plan a company’s content strategy in advance.

  * Test: allows for an SMS to be sent to one or multiple numbers for test purposes. Remember to use a comma between phone numbers if multiple numbers are used as recipients.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/sms_marketing/create_sms.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sms_analysis.html "SMS analysis") |
  * [precedente](../sms_marketing.html "SMS Marketing") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * Create SMS messages


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