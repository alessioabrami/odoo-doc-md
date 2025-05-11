# Follow-up on invoices — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](internal_transfers.html "Trasferimenti interni") |
  * [precedente](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Follow-up on invoices



# Follow-up on invoices¶

A follow-up message can be sent to customers when a payment is overdue. Odoo helps you identify late payments and allows you to schedule and send the appropriate reminders using **follow-up actions** that automatically trigger one or more actions according to the number of overdue days. You can send your follow-ups via different means, such as email, post, or SMS.

Vedi anche

  * [Odoo Tutorials: Payment Follow-up](https://www.odoo.com/slides/slide/payment-follow-up-1682)




## Configurazione¶

To configure a Follow-Up Action, go to Accounting ‣ Configuration ‣ Follow-up Levels, and select or create (a) new follow-up level(s). Several follow-up actions are available by default under the Notification tab, and the **name** as well as the **number of days** can be changed. The follow-up Actions available are:

  * Send Email;

  * [Send a Letter](../customer_invoices/snailmail.html#customer-invoices-snailmail);

  * [Send an SMS message](../../../marketing/sms_marketing/pricing_and_faq.html#pricing-pricing-and-faq).




You can use a pre-filled template for your messages by selecting a Content Template. To change the template used, hover over the field and click the –>. If enabled, SMS messages have a specific Sms Template field.

It is possible to automatically send a reminder by enabling the Automatic option, and attaching the _open_ invoice(s) by enabling Attach Invoices, within a specific follow-up action.

By clicking on the Activity tab, scheduling activities (tasks) is possible. That way, an activity is automatically scheduled when the follow-up is triggered. To do so, enable Schedule Activity, and select a Responsible person for the task. Choose an Activity Type, and enter a Summary on how to handle the activity, if desired.

Suggerimento

Set a negative number of days to send a reminder before the actual due date.

## Report promemoria di pagamento¶

Overdue invoices you need to follow up on are available in Accounting ‣ Customers ‣ Follow-up Reports. By default, Odoo filters by Overdue Invoices, but you can also filter by In need of action in the Filters menu.

When selecting an invoice, you can see all of the customer’s unpaid invoices (overdue or not), with the due dates of late invoices appearing in red. You can exclude invoices from a reminder by clicking Exclude from Follow-ups. You can set either Automatic or Manual reminders as well as a Responsible person for that customer.

To send reminders, click on Follow up, and select the action(s) you want to perform from:

  * Print;

  * Email;

  * Sms;

  * By post.




You can Attach Invoices and change the content templates from this view. When done, click Send or Send & Print.

Nota

  * The contact information on the invoice or the contact form is used to send the reminder.

  * When the reminder is sent, it is documented in the chatter of the invoice.

  * If it is not the right time for a reminder, you can specify the Next Reminder date. You will get the next report according to the next reminder date set.




Suggerimento

Reconcile all bank statements right before launching the follow-up process to avoid sending a reminder to a customer that has already paid.

### Debtor’s trust level¶

To know whether a customer usually pays late or not, you can set a trust level by marking them as Good Debtor, Normal Debtor, or Bad Debtor on their follow-up report. To do so, click on the bullet next to the customer’s name and select a trust level.

### Send reminders in batches¶

You can send reminder emails in batches from the Follow-up Reports page. To do so, select all the reports you would like to process, click on the Action gear icon, and select Process follow-ups.

Vedi anche

  * [Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

  * [SMS Pricing and FAQ](../../../marketing/sms_marketing/pricing_and_faq.html)

  * [Posta ordinaria](../customer_invoices/snailmail.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/follow_up.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](internal_transfers.html "Trasferimenti interni") |
  * [precedente](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Follow-up on invoices


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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax