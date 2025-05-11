# Analyze metrics — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../marketing_automation.html "Automazione marketing") |
  * [precedente](lost_leads_email.html "Lost leads reactivation email") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Analyze metrics



# Analyze metrics¶

In order to properly understand the success or failure of an email marketing campaign, it is necessary to monitor several key metrics. The insights gained from these metrics can then be used to optimize future campaigns. Odoo’s **Email Marketing** application tracks several key metrics, that can be interpreted through reports to improve future campaigns.

## View metrics¶

After a mass mail has been sent, the results for that particular mailing are displayed in multiple locations.

To access the metrics for an individual mailing, navigate to Email Marketing app ‣ Mailings. Locate the specific mailing in the list view, and use the column headings to view the results for that mailing. Click on one of the mailings in the list to open the record.

At the top of the record, detailed metrics are displayed as smart buttons.

### Opened rate¶

The percentage of emails opened by recipients, against the total number of sent emails.

In cases where a reply is expected, such as cold outreach emails, high open rate may indicate the subject line was timely, compelling, and successfully prompted the recipients to view the message.

In cases where a reply is not expected, such as promotional emails, it may indicate an issue with the email, such as incorrect product links or coupon codes.

In cases where a reply is expected, a low open rate may indicate the subject line failed to capture the recipients” interest or the message ended up in a spam or junk folder. It could also indicate the email ended up in a spam or junk folder.

Nota

Emails that consistently land in recipient spam folders could be due to having a poor sender reputation (i.e. high unsubscribe rate, high percentage of past emails marked as spam, etc.), or failing to [configure the proper DNS records](../../general/email_communication/email_domain.html).

### Replied rate¶

The percentage of recipients who responded to the email, against the total number of sent emails.

A high replied rate may indicate the email resonated with recipients, prompting them to take action or provide feedback.

A low replied rate may suggest the message lacked relevance or did not contain a clear call-to-action.

### Clicked rate¶

This represents the _Clicked through rate (CTR)_ , which measures the percentage of recipients who clicked on a link within the email, against the total number of sent emails.

A high CTR may indicate the email content was relevant and appropriately targeted. Recipients were motivated to click the links provided, and likely found the content engaging.

A low CTR may indicate issues with either the targeting, or the content itself. Recipients may have been unmotivated by the calls-to-action, if there were any, or the message itself may have been directed toward the wrong audience.

### Received rate¶

This rate measures the percentage of emails that were **successfully** delivered, against the total number of sent emails.

A high received rate can indicate the mailing list used is up-to-date, and the sender authentication is trusted by email providers.

A low received rate may indicate issues, either with the mailing list used for the mailing, or with the sender authentication. View the Mass mailing analysis section for more information.

### Bounced rate¶

This rate measures the percentage of emails that were **unsuccessfully** delivered, and did not enter a recipient’s inbox, against the total number of sent emails.

A high bounce rate could indicate issues, either with the mailing list used for the mailing, or with the sender authentication.

A low bounce rate may indicate that the mailing list used is up-to-date, and the sender authentication is trusted by email providers. View the Mass mailing analysis section for more information.

Suggerimento

Click on the respective smart buttons to see all the corresponding recipient records that are attributed to each metric. When these filtered records are in view, multiple types of reports can be run for further analysis.

## Create metrics reports¶

Individual metrics can be analyzed by creating a report. To begin, click on the smart button of the desired metric.

Next, click the __(down arrow) to the right of the search bar to see a drop-down menu of filtering and grouping parameters.

Filters, located in the left column of the search options, can be used to keep only the results that fit the filter. For example, selecting the _Bounced_ filter only shows emails that could not be delivered.

La colonna centrale Raggruppa per viene utilizzata per organizzare i risultati in gruppi e può essere usata con o senza filtri.

Nota

Setting multiple Group By options creates nested groups, according to which option is selected first. For example, selecting Sent Period, followed by Add Custom Group –> Responsible, in the Group By column, sorts all results _first_ by the sent period, _then_ by the team member responsible. This is a useful metric for analyzing who on the team is sending in volume or quantity over a set time period.

This can be verified by looking at the direction, and order, of the selections in the group tile that appears in the search bar after the selections are made.

Example

A monthly newsletter has been sent out, and 6.9% of the sent emails were bounced.

To see what these bounced recipients have in common, the records are grouped using a custom group targeting Mailing Lists, which groups all records by the mailing lists they are on. The records are then filtered using a custom filter with the rule `Created on >= 07/01/2024 00:00:00`, to filter by when the mailing list was last checked. This filter only includes recipients that have been created on, or after, July 1st, 2024, in the report.

Using these configurations, it is evident that all the recipients with bounced emails were added after the list was last checked. Looking closer at the domains, it is evident that each recipient has a malformed email domain (i.e: @yaoo.com instead of @yahoo.com), likely due to a manual entry error while updating the database.

Vedi anche

View [Cercare, filtrare e raggruppare i record](../../essentials/search.html) for more information about making custom groups and filters.

## Mass mailing analysis¶

It is also possible to analyze the success between mailing campaigns by creating a _Mass Mailing Analysis_ report. To begin, navigate to Email Marketing app ‣ Reporting ‣ Mass Mailing Analysis.

A dashboard appears displaying a bar chart containing each mailing campaign. By default, Sent is selected, displaying the number of sent records on the y-axis. To change the measure, click the Measures button, and select the desired measure from the drop-down menu.

Example

The following chart displays the number of opened emails from two different mass mailings.

In this view, it can be seen that the first mass mailing led to a higher opened rate than the second. Because a lower opened rate can sometimes be attributed to a subject line that failed to capture readers” attention, the subject line of each mass mailing can be a good place to begin looking.

Comparing the two subject lines, it is clear the newsletter’s subject line was less engaging, which may have led to the lower opened rate, when compared to the other mass mailing.

## Deliverability issues¶

The following define possible reasons for a high bounce rate or low received rate:

  * Using a mailing list that contains outdated contact information, or malformed email addresses are likely to result in a high bounce rate and/or a low received rate.

  * Mailings sent using a _From_ email address that differs from the sender’s domain are likely to bounce with certain email providers due to failing [DMARC authentication](../../general/email_communication/email_domain.html#email-domain-dmarc).

  * Failing to [configure the proper DNS records](../../general/email_communication/email_domain.html) can also result in a high bounce rate.




Vedi anche

  * [Mailing campaigns](../email_marketing.html#email-marketing-mailing-campaigns)

  * [Manage unsubscriptions](unsubscriptions.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/marketing/email_marketing/analyze_metrics.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../marketing_automation.html "Automazione marketing") |
  * [precedente](lost_leads_email.html "Lost leads reactivation email") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Marketing via e-mail](../email_marketing.html) »
  * Analyze metrics


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