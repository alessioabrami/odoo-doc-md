# Commands and canned responses — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chatbots.html "Chatbot") |
  * [precedente](ratings.html "Valutazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Commands and canned responses



# Commands and canned responses¶

In the Odoo **Live Chat** application, _commands_ allow the user to perform specific actions both inside the chat window, and through other Odoo applications. The **Live Chat** app also includes _canned responses_. These are customized, preconfigured substitutions that allow users to replace shortcut entries in place of longer, well-thought out responses to some of the most common questions and comments.

Both commands and canned responses save time, and allow users to maintain a level of consistency throughout their conversations.

## Execute a command¶

Live chat _commands_ are keywords that trigger preconfigured actions. When a live chat _operator_ is participating in a conversation with a customer or website visitor, they can execute a command by typing `/`, followed by the command.

Commands, and the resulting actions, are only visible in the conversation window for the live chat operator. A customer does not see any commands that an operator uses in a conversation from their view of the chat.

Example

During a conversation with a customer, a live chat operator executes the command to create a ticket. After entering the command, `/ticket`, the system automatically creates a ticket with the information from the conversation. It also includes a link to the new ticket, so the operator can go there directly to add any additional information, if necessary.

More information about each available command can be found below.

### Supporto¶

If an operator types `/help` in the chat window, an informative message that includes the potential entry types an operator can make is displayed.

  * Type `@username` to mention a user in the conversation. A notification will be sent to that user’s inbox or email, depending on their notification settings.

  * Type `/command` to execute a command.

  * Type `:shortcut` to insert a canned response.




Vedi anche

  * [Comunicazioni](../../productivity/discuss.html)

  * [Utilizzare i canali per comunicare con il team](../../productivity/discuss/team_communication.html)




### Ticket & search tickets¶

The `/ticket` and `/search_tickets` commands allow operators to create helpdesk tickets directly from a conversation, and search through existing tickets by keyword or ticket number.

Importante

The `/ticket` and `/search_tickets` commands can **only** be used if the **Helpdesk** app has been installed, and _Live Chat_ has been activated on a _Helpdesk_ team. To activate _Live Chat_ , go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams, and select a team. Scroll to the Channels section, and check the box labeled, Live Chat.

#### Create a ticket from a live chat¶

If an operator types `/ticket` in the chat window, the conversation is used to create a _Helpdesk_ ticket.

After entering the `/ticket` command, type a title for the ticket into the chat window, then press `Enter`.

The newly created ticket will be added to the _Helpdesk_ team that has live chat enabled. If more than one team has live chat enabled, the ticket will automatically be assigned based on the team’s priority.

The transcript from the conversation will be added to the new ticket, under the Description tab.

To access the new ticket, click on the link in the chat window, or go to the Helpdesk app and click the Tickets button on the Kanban card for the appropriate team.

#### Search for a ticket from a live chat¶

If an operator types `/search_tickets` in the chat window, they can search through _Helpdesk_ tickets, either by ticket number or keyword.

After entering the `/search_tickets` command, type a keyword or ticket number, then press `Enter`. If one or more related tickets are found, a list of links is generated in the conversation window.

Nota

Results from the search command will only be seen by the operator, not the customer.

### Cronologia¶

If an operator types `/history` in the chat window, it generates a list of the most recent pages the visitor has viewed on the website (up to 15).

### Contatto¶

By typing `/lead` in the chat window, an operator can create a _lead_ in the **CRM** application.

Importante

The `/lead` command can only be used if the **CRM** app has been installed.

After typing `/lead`, create a title for this new lead, then press `Enter`. A link with the lead title appears. Click the link, or navigate to the CRM app to view the Pipeline.

Nota

The link to the new lead can only be seen and accessed by the operator, not the customer.

The transcript of that specific live chat conversation (where the lead was created) is added to the Internal Notes tab of the lead form.

On the Extra Information tab of the lead form, the Source will be listed as Livechat.

### Permesso¶

If an operator types `/leave` in the chat window, they can automatically exit the conversation. This command does not cause the customer to be removed from the conversation, nor does it automatically end the conversation.

Vedi anche

  * [Acquisire nuovi contatti](../../sales/crm/acquire_leads.html)

  * [Helpdesk](../../services/helpdesk.html)




## Risposte predefinite¶

_Canned responses_ are customizable inputs where a _shortcut_ stands in for a longer response. An operator will enter the shortcut, and it is automatically replaced by the expanded _substitution_ response in the conversation.

### Create canned responses¶

To create a new canned response, go to Live Chat app ‣ Configuration ‣ Canned Responses ‣ New.

Type a shortcut command in the Shortcut field. Next, click the Substitution field, and type the message that should replace the shortcut.

Suggerimento

Try to connect the shortcut to the topic of the substitution. The easier it is for the operators to remember, the easier it is to use the canned responses in conversations.

#### Authorized groups¶

When a new canned response is created, it can **only** be utilized by the operator that created it. To allow the response to be used by other operators, select one or more [groups](../../general/users/access_rights.html#access-rights-groups) from the Authorized Groups drop-down list.

### Use canned responses in a live chat conversation¶

To use a canned response in a conversation, click the __(plus) icon in the message window. Then, click Insert a Canned Response. This opens a list of available canned responses. Either select a response from the list, or type the appropriate shortcut, then click the __(send) icon or hit `Enter`.

Suggerimento

Typing `::` into a chat window on its own generates a list of available canned responses. Responses can be manually selected from the list, in addition to the use of shortcuts.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/livechat/responses.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chatbots.html "Chatbot") |
  * [precedente](ratings.html "Valutazioni") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Livechat](../livechat.html) »
  * Commands and canned responses


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