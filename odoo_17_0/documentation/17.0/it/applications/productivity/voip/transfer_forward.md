# Make, receive, transfer, and forward calls — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../to_do.html "Da fare") |
  * [precedente](devices_integrations.html "Devices and integrations") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * Make, receive, transfer, and forward calls



# Make, receive, transfer, and forward calls¶

Calling prospective clients, customers, or colleagues is an essential part of any business. A company also needs to be available when customers call, in order to build trust and make connections.

This document covers how to make, receive, transfer, and forward calls with Odoo _VoIP_.

## Make calls¶

Starting on the Odoo dashboard, a call can be made by opening the phone widget in the the upper-right corner, which is represented by a ☎️ (phone) icon.

Then, a user can click on the Contacts tab, and click into any contact in the database to make a call.

Additionally, one can also use the Search bar in the VOIP pop-up window to find any desired contact.

To manually make a call, click the ⌨️ (keyboard) icon, and proceed to manually key in the desired number. Do not forget to lead with the \+ (plus) icon, followed by the international country code.

Example

For the United States of America, the country code and \+ (plus) icon, would look like this: `+1`. If one were to dial Belgium, the number would be prefixed by `+32`, and for Great Britain it would be `+44`.

After entering the full number, with the required \+ (plus) icon prefix and country code, click the green 📞 (phone) icon to start the call. When finished, click the red 📞 (phone) icon to end the call.

## Receive calls¶

An incoming call automatically opens the _VoIP_ widget, when a user is using the Odoo database. Should the database be open in another tab, a sound plays (the sound **must** be activated on the device).

Once back to the tab, the calling screen of the _VoIP_ phone widget appears.

Click the green 📞 (phone) icon to pick up the call, or the red 📞 (phone) icon to reject the call.

## Aggiungi a coda chiamate¶

All the contacts and customers that need to be called can be seen in one place with the Odoo _VoIP_ phone widget, under the Next activities tab.

To add a call to the Next activities tab, click the green 📞 (phone) icon, while in kanban view of the _CRM_ application.

To remove them from the call queue, hover over the opportunity that has a call scheduled, and click the red 📞 (phone) icon that appears with the \- (minus) icon.

When navigating back to the _VoIP_ phone widget, **only** the calls that are scheduled immediately for that day appear in the queue under the Next Activities tab of the _VoIP_ pop-up widget.

The Next Activities tab of the _VoIP_ phone widget is integrated with the following Odoo apps: _CRM_ , _Project_ , and _Helpdesk_.

A call can be added in the chatter of records within those applications.

To manually add a call, via the chatter, click Activities (next to the 🕗 (clock) icon). Under Activity Type, select Call from the drop-down menu that appears.

Next, set a Due Date, and add a Summary.

Lastly, change the Assigned to field to the person that should make the call. Whomever is set in this last field (Assigned to) has this call show up in their Next Activities call queue in the Odoo _VoIP_ phone widget.

Importante

Only calls for the immediate day (today’s date) appear in the Next Activities tab of the _VoIP_ phone widget for that specific user.

If specified, click Save or Open Calendar to complete the scheduling of the call.

## Transfer calls¶

A call can be transferred from one user to another in the Odoo _VoIP_ phone widget. However, this can **only** occur after speaking to the caller first. Without picking up the call in the Odoo _VoIP_ phone widget, the only way to transfer a call is automatically though the provider console/portal.

Vedi anche

For more information on transfers, visit [Forwardings tab](axivox/manage_users.html#voip-axivox-forwardings-tab).

To transfer a call within the Odoo _VoIP_ phone widget, first, answer the call using the green 📞 (phone) icon.

Once the incoming call is answered, click the ↔ (left-right arrow) icon. Then, enter the extension of the user the call should be forwarded to. Finally, click Transfer to route the call to that phone number.

Suggerimento

To find the extension for a user, consult the VoIP administrator, or, if the user has _Settings_ access rights to _Administration_ , navigate to Settings App ‣ Manage Users ‣ Select the user ‣ Preferences ‣ VOIP ‣ VoIP username / Extension number.

For more information on access rights, visit: [Diritti di accesso](../../general/users/access_rights.html).

## Forward calls¶

To forward a call within the Odoo _VoIP_ phone widget, first, answer the call using the green 📞 (phone) icon. Once the incoming call is answered, click the ↔ (left-right arrow) icon.

Then, enter the full phone number of the user the call should be forwarded to. Finally, click Transfer to route the call to that phone number.

Vedi anche

For more information on forwarding, visit [Forwardings tab](axivox/manage_users.html#voip-axivox-forwardings-tab).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/voip/transfer_forward.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../to_do.html "Da fare") |
  * [precedente](devices_integrations.html "Devices and integrations") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../voip.html) »
  * Make, receive, transfer, and forward calls


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