# Follow-up on invoices — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_sepa.html "Pay with SEPA") |
  * [precedente](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Follow-up on invoices



# Follow-up on invoices¶

Follow-up messages can be sent to customers when payments are overdue. Odoo helps identify late payments and allows scheduling and sending the appropriate reminders using **follow-up actions** according to the number of overdue days. Follow-ups can be sent through different methods, including email, post, or SMS.

Vedi anche

  * [Odoo Tutorials: Payment Follow-up](https://www.youtube.com/watch?v=50qy2ygS7eM)

  * [Termini di pagamento e piani di rateizzazione](../customer_invoices/payment_terms.html)




## Configurazione¶

To configure Follow-up actions, go to Accounting ‣ Configuration ‣ Follow-up Levels. In the Follow-up Levels list view, several follow-up levels and actions are configured by default.

To modify a follow-up level, click on the record. From the form view, edit the Description or adjust the number of days before a reminder is sent. In the Notification tab, select Actions such as Send Email, [Send a Letter](../customer_invoices/snailmail.html#customer-invoices-snailmail), and [Send SMS Message](../../../marketing/sms_marketing/pricing_and_faq.html#pricing-pricing-and-faq).

Nota

Sending letters or SMS messages in Odoo requires [In-App Purchase (IAP)](../../../essentials/in_app_purchase.html) credit or tokens.

To use a pre-filled template when sending an email or letter, select a Content Template. To modify it, click the __(internal link arrow) icon next to the Content Template field. If enabled, SMS messages use a specific Sms Template field that can be modified by clicking the __(internal link arrow) icon.

Other options can be enabled in the Options section within the specific follow-up level:

  * Automate the reminder with the Automatic option.

  * Attach Invoices that are overdue in the reminder.

  * Add followers on the related customer to receive notifications about any email reply made on the reminder’s email.




In the Activity tab, enable the option to automatically schedule [activities](../../../essentials/activities.html) when the follow-up level is triggered. Select the Responsible user and the Activity Type, and enter a Summary.

To add a new Follow-up Level, click New and fill in the fields.

Suggerimento

Set a negative number of days to send a reminder before the invoice due date.

## Invoice follow-ups¶

Nota

Reconcile all bank transactions before starting the follow-up process to avoid sending reminders for invoices that have already been paid.

To view all overdue invoices, go to Accounting ‣ Customers ‣ Invoices. In the Invoices list view, click into the search bar and filter on Overdue.

### Follow-ups for one customer¶

For a detailed overview of a customer’s invoice follow-up status, go to Accounting ‣ Customers ‣ Customers. Open the customer’s form and click the Accounting tab. In the Invoice follow-ups section, click on the different levels to view the Follow-up Status of each level. If actions are needed, click Overdue Invoices to have a detailed list of the overdue invoices.

Additional options can be set:

  * Reminders: These are either Automatic or Manual.

  * Next reminder: The date by which the next follow-up actions should be taken is automatically set when follow-ups are processed, but can be manually adjusted if needed.

  * Responsible: The user who handles the follow-up actions.




To manually send a payment reminder to a customer, click Send and select the actions in the Send and Print window:

  * Print

  * E-mail

  * Sms

  * By post




Enable the Attach Invoices option and change the Content Template if needed. Then, click Send or Send & Print to send the follow-up report.

Vedi anche

[Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

Nota

  * The contact information on the invoice or the contact form is used to send the reminder.

  * The chatter keeps a full record of all follow-up actions.




### Follow-ups for all customers due for action¶

After setting up the additional follow-up options, review which customers have overdue invoices or require follow-up. To do so, go to Accounting ‣ Customers ‣ Customers. In the Customers kanban view, click the search bar and filter by Overdue Invoices or Requires Follow-up.

To take follow-up actions for all relevant customers, switch to the list view and select the customers requiring follow-up. Then, click __(Actions) and select Process Follow-ups to send them the follow-up report.

## Report¶

### Customer statement¶

To get a comprehensive overview of a customer’s account status, click the Customer Statement smart button on the customer’s form. This statement corresponds to the [Partner Ledger](../customer_invoices.html#accounting-invoices-partner-ledger) report’s portion specific to that customer.

To send it to the customer, click Send, change the Email Template if needed, and click Print & Send.

To view the customer statements for multiple customers at once, select the customers from the Customers list view, click __(Actions), and select Open Customer Statements.

Click PDF or XLSX to generate a PDF or XLSX file, respectively.

### Follow-up report¶

To get a complete overview of a customer’s due invoices, separating those that are due from those that are overdue, click the Customer Statement smart button on the customer’s form. Then, click __ Report: Customer Statement and select Follow-Up Report.

To view the follow-up report for all customers at once, go to Accounting ‣ Reporting ‣ Partner Ledger. Then, click __ Report: and select Follow-Up Report.

Click PDF or XLSX to generate a PDF or XLSX file, respectively.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/payments/follow_up.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_sepa.html "Pay with SEPA") |
  * [precedente](batch_sdd.html "SEPA Direct Debit \(SDD\) customer payments") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
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