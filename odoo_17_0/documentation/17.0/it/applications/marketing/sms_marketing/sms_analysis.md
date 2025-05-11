# SMS analysis — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_campaigns.html "SMS campaign settings") |
  * [precedente](create_sms.html "Create SMS messages") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * SMS analysis



# SMS analysis¶

On the Reporting page (accessible via the Reporting option in the header menu), there are options to apply different combinations of Filters and Measures to view metrics in a number of different layouts (e.g. Graph, List, and Cohort views.)

Each Reporting metric view option allows for more extensive performance analysis of SMS mailings.

For example, while in the default Graph view, SMS data is visualized as different graphs and charts, which can be sorted and grouped in various ways (e.g. Measures drop down menu).

Suggerimento

SMS messages can be sent using automation rules in Odoo. Odoo _Studio_ is required to use automation rules.

To install Odoo _Studio_ , go to the Apps application. Then, using the Search… bar, search for `studio`.

If it is not already installed, click Install.

Adding the _Studio_ application upgrades the subscription status to _Custom_ , which increases the cost. Consult [support](https://www.odoo.com/contactus), or reach out to the database’s customer success manager, with any questions on making the change.

To use automation rules, navigate in [developer mode](../../general/developer_mode.html#developer-mode), to Settings app ‣ Technical menu ‣ Automation section ‣ Automation Rules. Then, click New to create a new rule.

Enter a name for the automation rule, and select a Model to implement this rule on.

Based on the selection for the Trigger, additional fields will populate below. Set the Trigger to one of the following options:

Values Updated

  * User is set

  * State is set to

  * On archived

  * On unarchived




Timing Conditions

  * Based on date field

  * After creation

  * After last update




Custom

  * On save

  * On deletion

  * On UI change




External

  * On webhook




Other options may appear based on the Model selected. For example if the Calendar Event model is selected, then the following options appear in addition to those above:

Email Events

  * On incoming message

  * On outgoing message




Under the Before Update Domain field, set a condition to be met before updating the record. Click Edit Domain to set record parameters.

Under the Actions To Do tab, select Add an action. Next, in the resulting Create Actions pop-up window, select Send SMS, and set the Allowed Groups. Allowed Groups are the access rights groups that are allowed to execute this rule. Leave the field empty to allow all groups. See this documentation: [Creare e modificare gruppi](../../general/users/access_rights.html#access-rights-groups).

Next, set the SMS Template and choose whether the SMS message should be logged as a note, by making a selection in the drop-down menu: Send SMS as. Click Save and Close to save the changes to this new action.

Add any necessary notes under the Notes tab. Finally, navigate away from the completed automation rule, or manually save (by clicking the ☁️ (cloud) icon), to implement the change.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/sms_marketing/sms_analysis.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](marketing_campaigns.html "SMS campaign settings") |
  * [precedente](create_sms.html "Create SMS messages") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [SMS Marketing](../sms_marketing.html) »
  * SMS analysis


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