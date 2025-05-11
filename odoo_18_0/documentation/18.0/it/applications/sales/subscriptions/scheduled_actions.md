# Scheduled actions — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Subscription reports") |
  * [precedente](automatic_alerts.html "Regole di automazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Scheduled actions



# Scheduled actions¶

_Scheduled actions_ are pre-configured processes that allow users to automate certain tasks within a database, based on a designated schedule or number of occurrences. These tasks can include sending emails, generating invoices, data clean-up, and so much more.

In Odoo, some scheduled actions are active, by default, to ensure that certain functions are triggered automatically, however there are _also_ many scheduled action options that appear in the database that are **not** activated by default.

In Odoo _Subscriptions_ , there are two scheduled actions that initiate the billing process for active recurring subscriptions, as well as when billing should stop due to subscription expiration.

They are turned on, by default and can be deactivated at any time in order to manage subscriptions manually.

## Access scheduled actions¶

Importante

In order to access scheduled actions, [developer mode](../../general/developer_mode.html#developer-mode) **must** be activated.

With developer mode activated, navigate to Settings app ‣ Technical ‣ Scheduled Actions.

Doing so reveals a dedicated Scheduled Actions dashboard. On this page, there is a complete list of scheduled actions for the entire database.

From here, enter `Subscription` in the search bar. Doing so provides three subscription-specific results. The following documentation focuses on the last two results in the list:

  * Sale Subscription: generate recurring invoices and payments

  * Sale Subscription: subscriptions expiration




Determine if a scheduled action is active by looking under the Active column, in the it’s corresponding row on the Scheduled Actions dashboard, for a ticked checkbox; if the checkbox is green with a check mark, the scheduled action is active.

If a scheduled action needs to be activated, click into the desired scheduled action from the list.

Then, from the scheduled action form, toggle the switch in the Active field to the right. Doing so turns the switch green, indicating that the scheduled action is now `Active`.

The ability to set up how often the scheduled action runs is also available on the scheduled action form, in the Execute Every field.

Importante

The scheduled action does **not** function correctly if the execution time is less than five minutes. This is a general rule for all scheduled actions.

For more information, read the [Frequent Technical Questions](../../../administration/odoo_sh/advanced/frequent_technical_questions.html) documentation.

## Generate recurring invoices and payments¶

In order for the Sale Subscription: generate recurring invoices and payments scheduled action to properly generate recurring invoices and payments on subscriptions, the _Deferred Expense_ and _Deferred Revenue_ accounts **must** be set up, in order for Odoo to process various invoices and payments related to subscriptions.

To set up _Deferred Expense_ and _Deferred Revenue_ accounts, navigate to Accounting app ‣ Configuration ‣ Settings. Both accounts can be configured in the Default Accounts section.

Once the correct accounts are entered in the Deferred Expense and Deferred Revenue drop-down menu fields, click Save in the upper-left corner.

### Crea fattura¶

Elements related to the Sale Subscription: generate recurring invoices and payments scheduled action can be found on confirmed subscription sales orders.

To examine these elements, open any confirmed sales order in the _Subscriptions_ application to reveal the subscription sales order form.

On a confirmed subscription sales order form, focus on the Recurring Plan and Date of Next Invoice fields.

The scheduled action creates an invoice when today’s date is the same date as the Date of Next Invoice.

Odoo uses the information in the Recurring Plan field to update the next invoice date accordingly.

Avvertimento

If the product invoicing policy is set to _Based on Delivered Quantities (Manual)_ , and the delivered quantity is `0`, Odoo does **not** create an invoice, and the customer is not charged.

Instead, the subscription is processed as a free recurring product, and is reflected as such in the _chatter_ of the subscription sales order.

When this occurs, the following message appears: `Automatic renewal succeeded. Free subscription. Next invoice:[date]. No email sent.`

Once the invoice for the subscription sales order is created, the invoice can be viewed by clicking the Invoices smart button that appears at the top of the subscription sales order.

An email is sent to the customer notifying them of the recurring subscription charge, _if_ there is a Payment Token on the account.

To check if there is a Payment Token, open the Other Info tab, and look at the Payment Token field, under the Subscription section.

If there is no Payment Token, the invoice is created, and sent to the customer. The payment **must** be registered manually in this case.

### Closing invoices¶

The Sale Subscription: generate recurring invoices and payments scheduled action also has the ability to close a subscription, if the following conditions are met:

  * If the subscription has no Payment Token, create and post the invoice.

  * If the subscription has a Payment Token, try to charge.

>     * If the charge is successful, create and post the invoice.
> 
>     * If the charge fails, send reminders periodically.
>
>>       * Close the subscription if it continues to fail for more than fourteen days.




## Subscriptions expiration¶

The Sale Subscription: subscriptions expiration scheduled action checks for all other conditions that may cause a subscription to close automatically. If certain conditions are met, the scheduled action closes that subscription.

First, the Sale Subscription: subscriptions expiration scheduled action checks to see if the end date has passed, which is configured on the subscription sales order.

Then, the Sale Subscription: subscriptions expiration scheduled action checks if the invoice has not been paid within the payment terms deadline.

To access the invoices attached to a subscription, access the sales order for the subscription product, and click the Invoices smart button. Then, look at the Invoice Date column.

Unpaid subscriptions with an Invoice Date that are past the determined number of days in the Automatic Closing field of a Recurring Plan are automatically closed by the Sale Subscription: subscriptions expiration scheduled action.

For example, if the next invoice date is July 1st, and the Automatic Closing is set to “30 Days”, the scheduled action would close the subscription on August 1st.

Vedi anche

  * [Abbonamenti](../subscriptions.html)

  * [Subscription plans](plans.html)

  * [Regole di automazione](automatic_alerts.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/subscriptions/scheduled_actions.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Subscription reports") |
  * [precedente](automatic_alerts.html "Regole di automazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Abbonamenti](../subscriptions.html) »
  * Scheduled actions


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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