# SMS Pricing and FAQ — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../events.html "Eventi") |
  * [precedente](mailing_lists_blacklists.html "Mailing lists and blacklists") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * SMS Pricing and FAQ



# SMS Pricing and FAQ¶

## What do I need to send SMSs?¶

SMS Text Messaging is an In-App Purchase (IAP) service that _requires prepaid credits_ to work.

## How many types of SMSs are there?¶

There are 2 types: GSM7 and UNICODE.

**GSM7** is the standard format, with a limit of 160 characters per message, that includes the following characters:

**UNICODE** is the format applied if a special character, that _is not_ in the GSM7 list, is used. Limit per SMS: 70 characters.

Nota

For GSM7 SMS the size limit is 160 characters, and for Unicode is 70. _Above these limits, the content is divided into a multi-part message_ and the limit of characters is lowered to 153 for GSM7 and to 67 for Unicode. Then, in real-time, the system displays the number of SMS mailings the message represents.

## How much does it cost to send an SMS?¶

The price of an SMS depends on the destination and the length (number of characters) of the message. To see the **price per country, please consult** : [Odoo SMS - FAQ](https://iap-services.odoo.com/iap/sms/pricing#sms_faq_01).

The number of SMSs a message represents will always be available in the database.

## How to buy credits¶

Go to Settings ‣ Buy Credits.

Or go to Settings ‣ View my Services.

Suggerimento

If Odoo Online (Saas) is being used, along with the Enterprise version, free trial credits are available to test the feature.

## More common questions¶

  1. **Is there an expiration time for my credits?**

No, credits do not expire.

  2. **Can I send an SMS to a phone number (which is not a mobile phone) because I see the icon in front of the field “phone”?**

Only if that phone number supports SMS (e.g. SIP phones).

  3. **Do I receive an invoice to buy my credits?**

Yes.

  4. **Can the recipient answer me?**

No, it is not possible to reply to the SMS.

  5. **What happens if I send multiple SMSs at once, but I don’t have enough credits to send them all?**

Multiple SMS communications at once at are counted as a single transaction, so no SMSs will be sent until there are enough credits to send them all.

  6. **Do I have a history of the sent SMSs?**

A history of sent SMSs, along with all pertinent information related to its sent contacts (and the message itself), can be found in the Sent column of the main SMS Marketing dashboard (while in Kanban view).

> For more detailed information, select a desired SMS from the main dashboard (in Kanban view), and click on either link in the blue banner above the SMS detail form to learn more.

  7. **Can I send as many SMSs I want at once?**

Yes, if you have enough credits.

  8. **If an SMS is sent to a number that doesn’t exist in the list of recipients, will credits be lost?**

No, not if the phone number is incorrectly formatted (e.g. too many digits). However, if the SMS is sent to the wrong person (or to a fake number), the credit for that SMS will be lost.

  9. **What happens if I send my SMS to a paying number (e.g.: a contest to win a ticket for a festival)?**

The SMS will not be delivered to that kind of number, so no charges will be made.

  10. **Can I identify the numbers that do not exist when I send several SMSs?**

Only the ones that have an invalid format.

  11. **How does the GDPR regulation affect this service?**

Please find our [Privacy Policy here](https://iap.odoo.com/privacy#sms).

  12. **Can I use my own SMS provider?**

Yes, but it is not possible out-of-the-box. Odoo experts can help customize a database to allow for the use of a personal SMS provider. Please check our success packs [here](https://www.odoo.com/pricing-packs).




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/sms_marketing/pricing_and_faq.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../events.html "Eventi") |
  * [precedente](mailing_lists_blacklists.html "Mailing lists and blacklists") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * SMS Pricing and FAQ


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