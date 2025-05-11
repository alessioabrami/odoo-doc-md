# Call queues — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../voip_widget.html "VoIP actions") |
  * [precedente](dial_plan_advanced.html "Advanced dial plans") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Call queues



# Call queues¶

A call queue organizes and routes incoming calls when all agents are busy, placing callers on hold in the order they called. This system helps manage high call volumes more efficiently, ensures fair workload distribution, and provides a more predictable experience for both callers and agents.

This document explains how to configure call queue settings and log into a queue from the Odoo database.

Vedi anche

[Set up on hold music](vm_audio_messages.html#voip-axivox-music-on-hold)

## Add a queue¶

To add a call queue in Axivox, navigate to the [Axivox management console](https://manage.axivox.com/). In the left menu, click Queues. Next, click Add a queue. From here, set up the call queue.

  * Name: The call queue’s name. A required field.

  * Internal Extension: The extension agents can transfer callers to. A required field.

  * Strategy: How calls are routed. Choose the option that best matches the company’s needs for this call queue:

    * Call all available agents: The call is sent to every agent.

    * Calls the agent who has received the call for the longest time: The call is sent to the agent with the longest idle time.

    * Calls the agent who has received the least call: The call is sent to the agent who has handled the fewest calls in a time window.

    * Call a random agent: The call is sent to a random agent.

    * Call agents one after the other: The call is sent to the next agent in a specified order. This order is remembered, and the order does not reset after each call.

    * Call agents one after the other starting with the first in the list: The call is sent to the next agent in a specified order. This order is remembered, and the order does reset after each call.

  * Maximum waiting time in seconds: How long a customer can wait in the queue before getting forwarded to voicemail or a specific agent.

  * Maximum duration of ringing at an agent: How long an individual agent’s phone rings before the call gets moved onto the next step in the dial plan. Learn more about [dial plans](dial_plan_basics.html).

  * Static agents: Agents in the queue who receive calls without logging in.

  * Dynamic agents: Agents who must log into the queue to receive calls from it.




Vedi anche

  * [Music on-hold](vm_audio_messages.html#voip-axivox-music-on-hold)

  * [Dial plan basics](dial_plan_basics.html)

  * [Advanced dial plans](dial_plan_advanced.html)




## Agent connection¶

Agents have three ways to join a call queue:

  * Static agents connect automatically.

    * Static agents are always signed into the call queue.

  * Manager logs in specific agents, via the [Axivox management console](https://manage.axivox.com/).

  * Agent connects to the queue in Odoo, via the **VoIP** widget.




### Connect to the queue through Axivox¶

Once the call queue is set up and the changes are applied, a manager can log into the [Axivox management console](https://manage.axivox.com/) and connect dynamic agents to the queue manually.

To connect an agent, click Queues, located in the left-hand menu. Doing so opens the Queues dashboard, with a few different columns listed:

  * Name: name of the queue.

  * Extension: number of the extension to be dialed to reach the queue.

  * Agent Connection: number to dial for dynamic agents to log into the queue.

  * Agent disconnection: number to dial for dynamic agents to log out of the queue.

  * Connected Agents: name of agents connected to the queue.




The following buttons are also available on the Queues dashboard:

  * Connect an agent: manually connect an agent to the queue.

  * Report: run a report on the queue.

  * Delete: delete the queue.

  * Edit: make changes to the queue’s settings.




When agents are connected to the queue, or are live with a customer, they are displayed under the Connected Agents column.

If they are static agents, they **always** show up as connected.

Connect an agent by clicking the orange button labeled Connect an agent. Then, select the desired agent’s name from the drop-down menu, and click Connect.

To manually log a dynamic agent out of a call queue, navigate to the [Axivox management console](https://manage.axivox.com/), and click Queues from the left-hand menu. Then, click the green Refresh button at the top of the Connected agents column. From here, click the red Disconnect button, and they are immediately disconnected. This can be helpful in situations where agents forget to log out at the end of the day.

#### Resoconto¶

Click Report to open a Queue report page that shows queue activity. This report includes who connected and when when, as well as what phone calls were handled by the queue.f This information is showcased on a separate Queue report page.

Set the report’s date in the Period field. To pick a specific date range, use the From and to fields. The information can be organized by Event type (covered below), and Call ID.

Generate the report by clicking Apply.

Each report can be exported to a CSV file for further use and analysis, via the Export to CSV button.

When the Event type field is clicked, a drop-down menu appears with the following options:

  * The caller quit

  * An agent is connecting

  * An agent is disconnecting

  * The call was terminated (agent hangs up)

  * The call was terminated (caller hangs up)

  * The caller is connected to an agent.

  * Someone is entering the queue

  * The caller exits the queue (no agent is connected)

  * The caller exits the queue (timeout)

  * No one is answering

  * No one is answering, the caller hangs up

  * Transfer

  * Blind Transfer (when the caller is transferred without interacting with an agent)




Any or all of the thirteen options can be selected from the Event type drop-down menu. Clicking Check all selects all the available options from the drop-down menu, and clicking Uncheck all removes all selections from the drop-down menu.

To select an individual Event type, click on the desired option in the drop-down menu.

### Connect to queue on Odoo¶

Dynamic agents can connect manually to the Axivox call queue from the Odoo **VoIP** widget once the **VoIP** app is configured for the individual user in Odoo.

To access the Odoo **VoIP** widget, click the __(VoIP) icon in the upper-right corner of the screen anywhere in an Odoo database.

Vedi anche

  * [VoIP services in Odoo with Axivox](axivox_config.html)

  * [VoIP actions](../voip_widget.html)




For an agent to connect to the call queue, dial the Agent connection number, and then press the green call button __(phone) icon in the **VoIP** widget. Then, the agent hears a short, two-second message indicating the agent is logged in. The call automatically ends.

To view the connected agents in a call queue, navigate to the [Axivox management console](https://manage.axivox.com/), and click Queues from the left-hand menu.

Then, click the green Refresh button at the top of the Connected agents column. Any agent, static or dynamic, that is connected to the queue currently appears in the column next to the queue they are logged into.

To log out of the queue, open the Odoo **VoIP** widget, dial the Agent disconnection number, and then press the green call button __(phone) icon. The agent is disconnected from the queue after a short, two-second message.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/voip/axivox/call_queues.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../voip_widget.html "VoIP actions") |
  * [precedente](dial_plan_advanced.html "Advanced dial plans") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Call queues


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