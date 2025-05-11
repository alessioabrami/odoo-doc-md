# Chatbot — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Report") |
  * [precedente](responses.html "Commands and canned responses") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Chatbot



# Chatbot¶

A _Chatbot_ is a program designed to mimic a conversation with a live human. Chatbots are assigned a script of pre-written steps to follow. The scripts are designed to anticipate a visitor’s potential response, and lead them through a series of questions and answers the same way a live team member would.

Chatbots can be customized to fill various roles, from customer support, to creating leads, to collecting contact information. The goal of each chatbot can vary based on several criteria, including the webpage where it is located, and the information it captures.

## Build a chatbot¶

Before creating a new chatbot, the **Live Chat** application must first be [installed](../../general/apps_modules.html#general-install).

After the **Live Chat** application has been installed on the database, go to Live Chat app ‣ Configuration ‣ Chatbots.

Nota

When the **Live Chat** app is installed, a sample chatbot is created, named _Welcome Bot_. This chatbot has a preconfigured script that walks through a few basic steps, including asking for a visitor’s email address, and forwarding the conversation to an operator.

_Welcome Bot_ can be used as a starting point. The existing steps can be edited or removed, and new steps can be added to customize the script, as needed.

_Welcome Bot_ can be deleted or archived, if necessary.

To create a new chatbot, navigate to the Chatbot page (Live Chat app ‣ Configuration ‣ Chatbots) and click New to open a blank chatbot details page.

Enter a name in the Chatbot Name field and hover over the image on the right. Click on the __(pencil) icon that appears to add a photo.

## Chatbot scripts¶

After the new chatbot has been created and named, the next step is to create a script. Chatbot conversations follow an accompanying script, comprised of lines of dialog. Each line is designed to either deliver or capture information.

To create a chatbot script, click Add a Line in the Script tab of the chatbot detail page, and a Create Script Steps pop-up window appears. This form must be filled out for each line of text (dialog) that the chatbot could potentially deliver during the conversation.

First, enter the content of the message in the Message field. Then, select an option from the Step Type and Only If drop-down menus.

### Step types¶

The Step Type selected depends on the intended purpose of the message. The available options in the Step Type drop-down menu are detailed below.

#### Testo¶

This step is used for messages where no answer is expected or necessary. Text steps can be used for greetings, to offer resources, such as documentation, or provide links to specific web pages.

Importante

 _Text_ step types are only intended to deliver information, and do not allow for any visitor input. As such, they must be followed by additional steps to continue the conversation.

#### Domanda¶

This step asks a question and provides a set of answers. The visitor clicks on one answer, which either leads to a new step in the conversation, or can lead to an optional link to a new webpage.

Enter the question in the Message field. Then, under the Answer heading, click Add a Line to create a blank answer line.

Proceed to enter the answer as it should appear to the visitor. To turn the answer into a link that redirects the visitor when selected, add the URL to the answer line under the Optional Link heading.

Repeat these steps for every answer to be included for the question. Click Save & Close or Save & New when finished.

Suggerimento

It is helpful to add a catchall answer to question steps (e.g: `Something else`). This helps visitors continue the conversation, even if their needs do not fit with any of the other answers.

#### E-mail¶

This step prompts visitors to provide their email address, which is stored and can be used by team members later to follow up with additional information.

The only accepted inputs for this step type are email addresses that are in a valid format. If a visitor attempts to enter anything other than a valid email address, the chatbot responds with a message stating it does not recognize the information submitted.

#### Telefono¶

Similar to email, this step type prompts the visitor to enter their phone number, which can be used to follow up with additional information, schedule demos, and more.

Avvertimento

Due to the vast number of formats used for phone numbers worldwide, responses to this step type are not validated for formatting, and can include both numbers and special characters.

#### Inoltra all’operatore¶

This step forwards the conversation to an active live chat operator, so they can continue assisting the visitor. As the conversation transcript is passed on to the operator, they can pick up where the chatbot left off. This not only saves time for all parties involved, it can also help qualify conversations before they reach live operators.

Nota

If no active operator is available on the channel, the chatbot continues the conversation with the visitor. Therefore, additional steps should be added after this one to ensure there is no abrupt end to the conversation. The additional steps can both inform visitors about the lack of available operators (e.g. `Uh-oh, it looks like none of our operators are available`) and continue the conversation (e.g. `Would you like to leave your email address?`).

#### Free Input/Multi-Line¶

The _free input_ step allows visitors to respond to questions without providing pre-written responses. Information provided in these responses is stored in the chat transcripts.

Choose between Free Input and Free Input (Multi-Line) depending on the type and amount of information the visitor is asked to provide.

#### Crea lead¶

This step creates a lead in the **CRM** application. Select an option from the Sales Team drop-down field that appears to assign the created lead to a specific team.

Nota

This step is only available if the **CRM** application is installed on the database.

#### Crea segnalazione¶

This step creates a [ticket](../../services/helpdesk/overview/receiving_tickets.html) in the **Helpdesk** application. Select an option from the Helpdesk Team drop-down field that appears to assign the created ticket to a specific team.

Nota

This step is only available if the **Helpdesk** application is installed on the database.

### Only if¶

Chatbot scripts operate on an if/then basis, which means the next question presented to the visitor is determined by the answer provided to the previous question.

To continue the progression of the conversation, the Create Script Steps form for a new step contains a field labeled Only If. This field is where the progression of questions are defined.

If a step is intended to follow all of the previous messages, this field can be left empty. However, if a message should only be sent conditionally, based on a previous response, or several previous responses, those responses **must** be added to this field.

Importante

If any selections are made in the Only If field, they must all be selected during the conversation before this step is included. Only include selections in this field if they are necessary for this step to be displayed.

Example

In the _Welcome Bot_ script, a visitor can ask about pricing information. If the visitor selects this response, a step is included to forward the conversation to an operator. The chatbot first sends a message informing the visitor that it is checking to see if an operator is available to assist with pricing information.

However, this message should only be delivered if the visitor requests pricing information. In that situation, the conversation would proceed as below:

  * Bot di benvenuto: « _Costa stai cercando?_ »

  * Visitor: «**I have a pricing question.** »

  * Welcome Bot: « _Hmmm, let me check if I can find someone that could help you with that…_ »




In the details form for the Text step, the _I have a pricing question_ response has been selected in the Only If field. As such, this step is only shown in conversations where that response has been selected.

## Script testing¶

To ensure all visitors have a satisfactory experience with the chatbot, each message needs to lead to a natural conclusion. Chatbot scripts should be tested to confirm there are no dead-ends, and to understand what the visitor sees when they interact with the chatbot.

Importante

If the visitor provides an answer, or input, that is not assigned a corresponding follow-up response, the conversation stops (_dead-ends_). Since the visitor cannot re-engage the chatbot, they must restart the conversation by refreshing the chat window, or their browser. They may also click on the __(refresh) icon at the top of the message window.

The __(refresh) icon only appears when the chatbot script has reached a dead-end.¶

To test the performance of a chatbot, first click on the Test button at the top-left of the chatbot script page. Then, upon being redirected to the testing screen, answer the chatbot prompts the same way a potential site visitor would.

When the script has reached an end-point, the message _Conversation ended…_ appears at the bottom of the chat window. To begin the conversation at the beginning of the script, click on the __(refresh) icon at the top of the message window. To return to the script page, click Back to edit mode at the top of the page.

## Add chatbot to a channel¶

After a chatbot has been created and tested, it needs to be added to a live chat channel.

First, open the Live Chat application, find the Kanban card for the appropriate live chat channel, hover over it, and click the __(vertical ellipsis) icon to open the drop-down menu. Click Configure Channel to open the channel detail form.

Nota

To create a new live chat channel, open the Live Chat app and click New. See [Live Chat](../livechat.html) for more information.

Click on the Channel Rules tab. Then, open an existing rule, or create a new one by clicking Add a line.

On the Create Rules pop-up window, choose the appropriate chatbot in the Chatbot field.

If the chatbot should only be active if there are no live chat operators available, check the box labeled Enabled only if no operator.

Vedi anche

[Live chat channel rules](../livechat.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/livechat/chatbots.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reports.html "Report") |
  * [precedente](responses.html "Commands and canned responses") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Chatbot


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
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
  *[URL]: Uniform Resource Locators
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions