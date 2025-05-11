# Lost leads reactivation email — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](analyze_metrics.html "Analyze metrics") |
  * [precedente](unsubscriptions.html "Manage unsubscriptions \(blacklist\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Lost leads reactivation email



# Lost leads reactivation email¶

In Odoo, lost leads are removed from the active _CRM_ pipeline, but can still be targeted with the _Email Marketing_ application for strategic campaign purposes, such as lost leads reactivation.

A lost leads reactivation email looks at the leads that were lost during a specific period of time, and uses custom filters and lost reasons to exclude undesirable leads from the mailing list.

Once a lost leads reactivation email is complete, it can be sent as is, modified and sent to different groups for A/B testing, or saved as a template for later.

Example

A warehouse has leftover merchandise from a limited run of items from last year. To help clear out the excess inventory, the warehouse manager creates a lost leads email to reach out to old opportunities that were lost, and inform them that the limited merchandise is back in stock.

The warehouse manager uses the following filters for a lost leads email:

  * Blacklist _is_ `not set`

  * Created on _> =_ `01/01/2024 00:00:01`

  * Stage _is not in_ `New`, `Qualified`, or `Won`

  * Lost Reason _is in_ `Not enough stock`

  * and either Active _is_ `set` or `not set`




Suggerimento

As filters are added and removed, pay attention to the # record(s) value below the filtering section. This value indicates the total number of records that match the current criteria.

To view a list of all matching records, click the # record(s) text.

## Minimum requirements¶

In order to create and deliver a lost leads reactivation email campaign, the _CRM_ and _Email Marketing_ applications **must** be [installed](../../general/apps_modules.html#general-install) and configured.

Here are the minimum necessary filters that pertain to a lost leads reactivation mailing campaign:

  * The Recipients field **must** be set to the _Lead/Opportunity_ model.

  * A Blacklist filter to exclude unsubscribed recipients.

  * A Created on to target leads that were lost during a specific period of time.

  * Stage filter(s) to exclude leads that were already won, or are still active in new stages of the sales pipeline (i.e. _New_ , _Qualified_ , etc.). These values will be different per organization; however, it’s minimally viable to exclude all the leads in the _Won_ stage.

  * One or more Lost Reason filters to exclude undesired leads, such as duplicate, spam, or irrelevant records.

  * A pair of Active filters to target _both_ active and inactive leads.




## Add the necessary filters¶

First, navigate to the Email Marketing app, and on the Mailings page, click the New button in the top-left corner.

On the new Mailings form, enter an appropriate Subject line for the email in the corresponding field. Then, in the Recipients field, choose the Lead/Opportunity model from the drop-down menu.

In the rules section, located beneath the Recipients field, click the modify filter (▶ (triangle pointing right)) icon to expand the filter rules. Leave the default Blacklist rule in place.

### Data creazione¶

Begin by clicking New Rule beneath the default Blacklist rule. Then, click the first field of the new rule that appears, and select the Created on parameter from the drop-down menu. With that in place, a specific time period during which the targeted leads were lost can be designated (e.g. 30 days prior, 90 days prior, previous year, etc.).

Then, in the second field, select <= (less than or equal to), >= (greater than or equal to), or is between as a date operator, in order to frame the time selection chosen in the third field.

In the third field, use the calendar popover window to select dates, and click Apply to lock in the time range.

Importante

When there is more than one rule applied, make sure the statement at the top of the Recipients filter list reads: Match all of the following rules. If it does not, click on the statement, and select all from the drop-down menu (as opposed to any).

### Fase¶

Now, add the Stage filter to exclude leads that are in the _New_ , _Qualified_ , and _Won_ stages of the sales pipeline.

Nota

This step assumes that the _New_ , _Qualified_ , and _Won_ stages exist in the CRM pipeline; however, stage names may differ from business to business. Refer to the database’s actual stage names in the _CRM_ app’s pipeline to complete this step, accordingly.

Begin again by clicking New Rule and select Stage from the first field’s drop-down menu. In the second field, select the is not in operator, and in the third field, select the New, Qualified and Won stages to define the rule’s parameters.

When the rule is added in this way, the logic in the third field renders as `OR` (`|`) statements.

Suggerimento

Another way to add _Stage_ rules, is to do so on a one-rule-per-row basis using the contains or does not contain operators, and manually typing out the defining characters in each stage name. This method, however, only allows for one selection at a time, which can be useful for quickly turning on/off filters in the Search… bar.

### Motivo della perdita¶

Next, add one or more Lost Reason rules to exclude leads that should **not** be targeted for specific [lost reasons](../../sales/crm/pipeline/lost_opportunities.html).

To do that, create another New Rule, once again. Then, in the rule’s first field, select Lost Reason from the drop-down menu. For the operator, choose either is not in or does not contain from the drop-down menu. With either selection, use the third field to enter a lost reason (or multiple lost reasons, depending on your operator choice) to include in the rule.

If choosing the does not contain operator, then repeat the preceding steps to add more lost reasons, as needed, where each lost reason occupies one rule row at a time.

For more information, refer to the section below outlining how to select appropriate lost reasons.

### Attivo¶

Finally, add a pair of Active filters to include both active and inactive leads for the campaign.

Importante

Adding both active _and_ inactive lead records is necessary to capture the full scope of lost leads in the database. Doing one without the other greatly impacts the number of targetable records for the email campaign, and does **not** include a complete or accurate lost leads audience.

First, click the (Add Branch) icon on the most recently created rule (e.g. Lost Reason), which is the middle of three icons located to the right of the rule row. Doing so adds a pair of any of rules. Then, in the top rule’s first field of the newly-created branch, select the Active parameter from the drop-down menu. The rule then automatically fills out to read: Active _is_ `set`.

For the first field of the bottom rule of the branch, select Active from the drop-down menu again. However, this time, select is not from the operator drop-down menu in the second field. The rule should then read: Active _is not_ `set`.

## Add body content¶

Now, with the domain section of the email campaign complete, create the body content of the email using any of the premade stylized templates, or choose between the Plain Text or Start From Scratch options for more granular control. For more information, refer to the _Email Marketing_ [documentation on how to create an email](../email_marketing.html#email-marketing-create-email).

Suggerimento

To save the set of filters for later use, click Save as Favorite Filter 💾 (floppy disk), enter a name (such as `Lost Leads`), and click Add.

## Send or schedule¶

Once all the components of the email campaign are complete, either:

  * click the purple Send button at the top-left of the form to immediately send the email; or

  * click the gray Schedule button, located to the right of the Send button, to send the email at a future date and time.




Suggerimento

Consider using _A/B Testing_ to send an alternate version of the email to a percentage of the target leads. This can help determine what subject lines and body content produce the best click-through rates, before sending a final version to the remaining leads.

To do so, open the A/B Tests tab on the mailing form and check the box next to Allow A/B Testing. Then, adjust the parameters as needed, and click Create an Alternative Version.

## Select appropriate lost reasons¶

When a lead is marked as lost, Odoo recommends selecting a _Lost Reason_ to indicate why the opportunity did not result in a sale. Doing so keeps the pipeline organized and reporting data accurate, and generates potential to follow up with the lead in the future.

If an existing _Lost Reason_ is not applicable, users with the necessary permissions can create new ones, which means the lost reasons in a database can vary from organization to organization, and from pipeline to pipeline.

For more information on _Lost Reasons_ , including the creation of them, refer to [Opportunità perse](../../sales/crm/pipeline/lost_opportunities.html).

By default, Odoo includes a few common _Lost Reasons_ , such as:

  * _Too expensive_

  * _We don’t have people/skills_

  * _Not enough stock_




When determining which reasons to include in a lost leads reactivation email, consider what the email is advertising, in order pinpoint one or more relevant lost reasons. Then, add a rule stating, Lost Reason _does not contain_ `_____` for every reason in the database, **except** for the relevant one(s).

Example

If the email advertises a selection of previously-limited merchandise that is now back in stock, it makes sense to target leads with the lost reason: _not enough stock_.

If the email advertises a price reduction, it makes sense to target leads with the lost reason: _too expensive_.

## Analyze the results¶

After sending a lost leads reactivation email, marketing teams can use the smart buttons along the top of the email to analyze the results, and determine follow-up actions.

Clicking on any of the smart buttons opens a list of records matching that button’s specific criteria.

The smart buttons include:

  * Sent: total number of emails sent.

  * Opened: percentage of recipients that opened the email.

  * Replied: percentage of recipients that replied to the email.

  * Clicked: click-through rate (%) of recipients that clicked on a link in the email.

  * Leads/Opportunities: number of leads (or opportunities) that have been created in the _CRM_ pipeline, as a result of the email campaign.

  * Quotations: number of quotations that have been created in the _Sales_ application, as a result of the email.

  * Invoiced: total revenues generated, as a result of the email campaign, via invoices sent to, and paid by, customers. These values are recorded in either the _Invoicing_ or _Accounting_ application, depending on which app is installed in the database.

  * Received: percentage of recipients that received the email.

  * Bounced: percentage of emails that bounced (not delivered).

  * Ignored: the number of recipients that received the email, but have not interacted with it in a meaningful way (i.e. opened, clicked, etc.).




## Email nurturing¶

_Email nurturing_ (sometimes referred to as _lead nurturing_) is the process of sending a series of timely and relevant «nudge» emails to connect with a lead, build a deeper relationship, and ultimately convert the lead into a sale.

The point of nurturing is to keep the email campaign «visible» or at the top of a lead’s inbox, until they are ready to buy.

There are many approaches to effective lead nurturing, but they often involve:

  * Sending an initial email (such as, a lost leads reactivation email).

  * Sending a follow-up email each week (or according to specific triggers) for the duration of the campaign.

  * Continuously analyzing results to learn what approaches have resulted in sales.

  * Continuously adjusting the approach to remain «visible» at the top of the lead’s inbox, and hopefully, get a meaningful response from the lead.




As a campaign progresses, a marketing team may send different follow-up emails depending on how a lead responded the previous week.

Example

A marketing team wants to advertise a restocking of limited-run merchandise to all leads with a lost reason of _not enough stock_. They develop the following three-week long lead nurturing campaign.

  * **Week 1:** the marketing team sends an initial email, with the subject line: _“Limited run merchandise is back in stock! Act now!”_

  * **Week 2:** the marketing team sends two different emails, depending on how a lead responded.

    * If a lead ignored the Week 1 email: _“Stock is almost out, did you get yours?”_

    * If a lead clicked on the Week 1 email: _«You still have time to add this to your collection»_

  * **Week 3:** the marketing team sends a final email to all leads who have not been converted stating: _“20% off, don’t miss your last chance to get these items before they’re gone!”_




Throughout the campaign, the marketing team continuously refers to the smart buttons along the top of the mailing page to see what percentages of leads are opening, clicking on, or ignoring the emails. They also regularly analyze reports on how many opportunities, quotations, and invoices have been generated by the campaign.

Vedi anche

  * [Marketing via e-mail](../email_marketing.html)

  * [Manage unsubscriptions (blacklist)](unsubscriptions.html)

  * [Automazione marketing](../marketing_automation.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/email_marketing/lost_leads_email.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](analyze_metrics.html "Analyze metrics") |
  * [precedente](unsubscriptions.html "Manage unsubscriptions \(blacklist\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Lost leads reactivation email


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
  *[FBM]: Fulfilled by Merchant
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
  *[POS]: point of sale
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record