# Consenso doppio — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sms_marketing.html "SMS Marketing") |
  * [precedente](../campaign_templates.html "Campaign templates") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Marketing](../../../marketing.html) »
  * [Automazione marketing](../../marketing_automation.html) »
  * [Campaign templates](../campaign_templates.html) »
  * Consenso doppio



# Consenso doppio¶

A _double opt-in_ , also referred to as a _confirmed opt-in_ , may be required in some countries for marketing communications, due to anti-SPAM laws. Confirming consent has several other benefits, as well: it validates email addresses, avoids spam/robo subscribers, keeps mailing lists clean, and only includes engaged contacts in the mailing list.

When the _Double Opt-in_ campaign template is used, a new mailing list titled, _Confirmed contacts_ is created in the _Email Marketing_ app, and any new mailing list contacts that are added to the default _Newsletter_ mailing list are sent a confirmation email to double opt-in. The contacts that click on the confirmation link in the email are automatically added to the _Confirmed contacts_ mailing list in Odoo.

Importante

When using the _Double Opt-in_ campaign template, only the contacts in the _Confirmed contacts mailing_ list are considered to have confirmed their consent.

## Use the Double Opt-in campaign template¶

Open the Marketing Automation app, and select the Double Opt-in campaign template to create a new campaign for confirming consent.

Suggerimento

The campaign templates do **not** display, by default, when there are existing _Marketing Automation_ campaigns. To display the campaign templates, type the name of a campaign (that does not exist in the database) into the Search… bar, then press `Enter`.

For example, searching for `empty` displays the campaign template cards again, as long as there is not a campaign with the name «empty» in the database.

### Campaign configuration¶

Upon creation of the campaign, the campaign form loads with a new preconfigured campaign.

The Target and Filter configurations of the campaign are as follows:

  * Name: `Double Opt-in`

  * Responsible*: The user who created the campaign.

  * Target: Mailing Contact

  * Unicity based on: Email (Mailing Contact)

  * Filter:

    * Email is set

    * Blacklist is not set

    * Mailing lists contains `Newsletter`




* The Responsible field is only visible with [Modalità sviluppatore (modalità di debug)](../../../general/developer_mode.html#developer-mode) activated.

Importante

The Target model of the campaign should **not** be modified. Changing the Target model with activities in the Workflow invalidates the existing activities in the Workflow.

The _Double Opt-in_ campaign template is intended to **only** use the Mailing Contact model.

The campaign loads two activities in the Workflow section of the campaign: an email activity, with a child server action activity that triggers _on click_.

By default, the `Confirmation` email activity is set to trigger 1 Hours after the beginning of the workflow. In other words, the email is sent 1 hour after a new contact is added to the _Newsletter_ mailing list.

The email activity uses the preconfigured _Confirmation_ email template, which contains a button for the contact to click to confirm their consent.

To modify the email template, select the __ Templates smart button at the top of the campaign form. Then, in the list of templates, select the `Confirmation` email template.

Be sure to personalize the contents of the email template; however, it is recommended to keep the contents of double opt-in confirmation emails short and to-the-point.

The default confirmation button, in the body of the template, links directly to the database’s website homepage. Click on the button to edit the button text and URL.

Suggerimento

To provide a streamlined experience for the contact, consider [creating a page on the website](../../../websites/website/pages.html) that expresses gratitude to the contact for confirming their subscription to the mailing list. Add the link to that page in the URL of the confirmation button.

Importante

The email template should only include a single call-to-action link for confirmation, other than an unsubscribe link.

Any click on a link (or button) included in the confirmation email, besides the unsubscribe button, triggers the _Add to list_ server action.

The child activity _Add to list_ server action’s _On click_ trigger cannot differentiate between multiple URLs in an email, besides the `/unsubscribe_from_list` unsubscribe button that is included in any one of the footer blocks.

The `Add to list` server action activity triggers immediately after a click in the parent `Confirmation` email activity is detected.

When triggered, the `Add to list` activity executes the _Add To Confirmed List_ server action, automatically adding the contact to the _Confirmed contacts_ mailing list, if they are not already in the mailing list.

To modify the server action, select the title of the activity to open the Open: Activities pop-up window and edit the server action activities configuration.

Suggerimento

Consider setting an Expiry Duration to prevent executing the activity after a specific amount of time.

Importante

It is not recommended to modify the preconfigured Python code in the Add To Confirmed List server action, as doing so may trigger a change in the database’s pricing plan.

Once the campaign configuration is complete, consider [launching a test](../testing_running.html) to verify the campaign executes as expected. If the campaign testing is successful, Start the campaign to begin sending double opt-in confirmation emails to _Newsletter_ mailing list contacts, and fill the _Confirmed contacts_ mailing list with engaged contacts.

## Double Opt-in use-case¶

Example

To prepare for sending newsletter marketing emails on an Odoo database, a mailing contact list must be procured. One way of collecting subscribers is through a sign-up form on the website that adds contacts to the _Newsletter_ mailing list on the form submission.

Before sending any marketing emails, use the Double Opt-in campaign template in the _Marketing Automation_ app to confirm marketing email consent from the contacts in the _Newsletter_ mailing list.

After launching the _Double Opt-in_ campaign, view the contacts that have double opt-in in the _Confirmed contacts_ mailing list (Email Marketing app ‣ Mailing Lists ‣ Mailing Lists).

Now, the _Confirmed contacts_ mailing list is ready to be used for sending newsletter marketing emails from an Odoo database.

Vedi anche

  * [Campaign metrics](../understanding_metrics.html)

  * [Mailing lists](../../email_marketing/mailing_lists.html)

  * [Marketing via e-mail](../../email_marketing.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/marketing/marketing_automation/campaign_templates/double_optin.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sms_marketing.html "SMS Marketing") |
  * [precedente](../campaign_templates.html "Campaign templates") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Marketing](../../../marketing.html) »
  * [Automazione marketing](../../marketing_automation.html) »
  * [Campaign templates](../campaign_templates.html) »
  * Consenso doppio


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