# Call queues — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../voip_widget.html "VoIP widget") |
  * [precedente](dial_plan_advanced.html "Advanced dial plans") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Call queues



# Call queues¶

A call queue is a system that organizes and routes incoming calls. When customers call a business, and all of the agents are busy, the call queue lines up the callers in sequential order, based on the time they called in.

The callers then wait on hold to be connected to the next available call center agent.

Implementing a call queue system reduces stress for employees, and helps build brand trust with customers. Many companies use call queues to set expectations with customers, and to distribute the workload equally amongst employees.

This document covers the process required to configure call queues (with advanced settings), as well as how to log into a call queue from the Odoo database.

Vedi anche

[Music on-hold](vm_audio_messages.html#voip-axivox-music-on-hold)

## Add a queue¶

To add a call queue in Axivox, navigate to the [Axivox management console](https://manage.axivox.com/). In the left menu, click Queues. Next, click Add a queue. Doing so reveals a blank New queue form with various fields to fill out.

### Nome¶

Once the New queue page appears, enter the Name of the queue.

### Internal extension¶

Choose an Internal extension for the queue. This is a number to be dialed by users of the database to reach the login prompt for the queue.

### Strategia¶

Next, is the Strategy field. This field determines the call routing of received calls into this queue.

The following choices are available in the Strategy drop-down menu:

  * Call all available agents

  * Calls the agent who has received the call for the longest time

  * Calls the agent who has received the least call

  * Call a random agent

  * Call agents one after the other

  * Call agents one after the other starting with the first in the list




Choose a strategy that best meets the company’s needs for customers in the queue.

### Maximum waiting time in seconds¶

In the Maximum waiting time in seconds field, determine the longest time a customer waits in the queue before going to a voicemail, or wherever else they are directed to in a dial plan. Enter a time in seconds.

### Maximum duration of ringing at an agent¶

In the Maximum duration of ringing at an agent field, determine the longest time an individual agent’s line rings before moving on to another agent, or moving to the next step in the dial plan. Enter a time in seconds.

Vedi anche

For more information on dial plans, visit:

  * [Dial plan basics](dial_plan_basics.html)

  * [Advanced dial plans](dial_plan_advanced.html)




### Adding agents¶

The final two fields on the New queue form revolve around adding agents. Adding Static agents and Dynamic agents are two pre-configured methods for adding agents onto the call queue during the configuration.

#### Static agents¶

When Static agents are added, these agents are automatically added to the queue without the need to log in to receive calls.

#### Dynamic agents¶

When Dynamic agents are added, these agents have the ability to log into this queue. They are **not** logged-in automatically, and **must** log in to receive calls.

Be sure to Save the changes, and click Apply changes in the upper-right corner to implement the change in production.

## Agent connection¶

There are three ways call agents can connect to an Axivox call queue:

  1. Dynamic agents connect automatically.

  2. Manager logs in specific agent(s), via the [Axivox management console](https://manage.axivox.com/).

  3. Agent connects to the queue in Odoo, via the _VoIP_ widget.




Vedi anche

See the documentation on setting Dynamic agents in the [Axivox management console](https://manage.axivox.com/).

### Connect via Axivox queue¶

After the initial configuration of the call queue is completed, with the changes saved and implemented, a manager can log into the [Axivox management console](https://manage.axivox.com/) and connect dynamic agents to the queue manually.

To connect an agent, click Queues, located in the left-hand column. Doing so reveals the Queues dashboard, with a few different columns listed:

  * Name: name of the queue.

  * Extension: number of the extension to be dialed to reach the queue.

  * Agent Connection: number to dial to log into the queue.

  * Agent disconnection: number to dial to log out of the queue.

  * Connected Agents: name of agent connected to the queue.




The following buttons are also available on the Queues dashboard:

  * Connect an agent: manually connect an agent to the queue.

  * Report: run a report on the queue.

  * Delete: delete the queue.

  * Edit: make changes to the settings of the queue.




When agents are connected to the queue, or are live with a customer, they are displayed under the Connected Agents column.

If they are static agents, they **always** show up as connected.

Connect an agent by clicking the orange button labeled, Connect an agent. Then, select the desired agent’s name from the drop-down menu, and click Connect.

Vedi anche

For more information on static and dynamic agents, see this documentation:

  * Static agents

  * Dynamic agents




#### Rendiconto¶

Click Report to check on the reporting for a particular queue, in order to see who connected when, and what phone calls came in and out of the queue. This information is showcased on a separate Queue report page, when the green Report button is clicked.

Reports can be customized by date in the Period field, and specified in the From and to fields. The information can be organized by Event type, and Call ID.

When the custom configurations have been entered, click Apply.

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

  * Blind Transfer




There is no limit to how many options can be selected from the Event type drop-down menu.

Clicking Check all selects all the available options from the drop-down menu, and clicking Uncheck all removes all selections from the drop-down menu.

To select an individual Event type, click on the desired option in the drop-down menu.

### Connect to queue on Odoo¶

Dynamic agents can connect manually to the Axivox call queue from the Odoo _VoIP_ widget, once the _VoIP_ app is configured for the individual user in Odoo.

Vedi anche

[VoIP services in Odoo with Axivox](axivox_config.html)

To access the Odoo _VoIP_ widget, click the ☎️ (phone) icon in the upper-right corner of the screen, from any window within Odoo.

Vedi anche

For more information on the Odoo _VoIP_ widget, see this documentation: [VoIP widget](../voip_widget.html)

For an agent to connect to the call queue, simply dial the Agent connection number, and press the green call button 📞 (phone) icon in the _VoIP_ widget. Then, the agent hears a short, two-second message indicating the agent is logged in. The call automatically ends (disconnects).

To view the connected agents in a call queue, navigate to the [Axivox management console](https://manage.axivox.com/), and click Queues, located in the left-hand column.

Then, click the green Refresh button at the top of the Connected agents column. Any agent (static or dynamic) that is connected to the queue currently, appears in the column next to the queue they are logged into.

To log out of the queue, open the Odoo _VoIP_ widget, dial the Agent disconnection number, and press the green call button 📞 (phone) icon. The agent is disconnected from the queue after a short, two-second message.

To manually log a dynamic agent out of a call queue, navigate to the [Axivox management console](https://manage.axivox.com/), and click Queues, located in the left-hand column. Then, click the green Refresh button at the top of the Connected agents column.

To disconnect an agent manually, click the red Disconnect button, and they are immediately disconnected. This can be helpful in situations where agents forget to log out at the end of the day.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/voip/axivox/call_queues.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../voip_widget.html "VoIP widget") |
  * [precedente](dial_plan_advanced.html "Advanced dial plans") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
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
  *[EDI]: electronic data interchange
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
  *[FBM]: Fulfilled By Merchant
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