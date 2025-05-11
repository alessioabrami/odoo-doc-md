# Dial plan basics — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dial_plan_advanced.html "Advanced dial plans") |
  * [precedente](conference_calls.html "Conference calls") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Dial plan basics



# Dial plan basics¶

When someone calls a business, they might need to get in contact with customer support, a sales team, or even a person’s direct line. The caller might also be in search of some information about the business, such as store hours. Or, they might want to leave a voicemail, so someone from the company can call them back. With dial plans in Axivox, a company can manage how incoming calls like this are handled.

Using proper call architecture through a dial plan, callers get directed to the right people, or to the right information, in a quick, efficient manner.

This document covers the basic configuration of dial plans in Axivox.

Vedi anche

For more information on advanced dial plans, visit [Advanced dial plans](dial_plan_advanced.html).

Importante

Using a browser add-on for spelling may hinder the use of the visual editor in dial plans. Do not use a translator with the Axivox management console.

## Dial plans¶

Access dial plans by navigating to [Axivox management console](https://manage.axivox.com/), and clicking on Dial plans from the menu on the left.

To add a new dial plan from the Dial plan page, click the green button labeled, Add a new dial plan.

Nota

Axivox has no limit to the number of dial plans that can be created. These can be added, and improved upon, at any time. This allows for sandboxes to be created with many different configurations.

To edit an existing dial plan, choose one of the following options to the right of the saved dial plan:

  1. Delete: this action deletes the attached dial plan.

  2. Edit: this action allows the user to edit the dial plan.

  3. Visual Editor: this action opens a visual editor window, where the dial plan architecture can be viewed and edited.

  4. Duplicate: this action duplicates the dial plan, and puts it at the bottom of the list, with an extension of one number (+1) larger than the original extension.




### Dialplan editor (visual editor)¶

When the Visual Editor button is clicked for a dial plan on the Dial plan page, a pop-up Dialplan Editor window appears.

This pop-up window is the primary place where the architecture, or structure, of the dial plan is configured. In this window, a GUI appears, where various dial plan elements can be configured and linked together.

Importante

New dial plans come blank with New element options for the user to Add and Save.

The method for saving in the Dialplan Editor is different from saving any other edits in the Axivox management console because the Save button **must** be pressed before closing the Visual editor.

Then, before these changes can take place on the Axivox platform, the user **must** click Apply changes in the upper-right corner of the Dial plan page.

From the Dialplan Editor pop-up window, users can add a new element to the dial plan. To do that, open the New element drop-down menu, and select the desired element. Then, click Add.

Doing so adds that element to the visual editor display of the dial plan being modified. This element can be moved where desired amongst the other elements present in the dial plan.

Connect elements in the dial plan by clicking and dragging outward from the (open circle) icon on the right side of the element. Doing so reveals an (arrow) icon. Proceed to drag this (arrow) icon to the desired element in the dial plan that it is meant to connect with.

Connect the (arrow) icon to the circle on the left side of the desired element.

Calls displayed in the dial plan flow from left-to-right in the element.

In order to further configure a New element, double-click on the element inside the dial plan, to reveal a subsequent pop-up window, wherein additional customizations can be entered.

Each element has a different configuration pop-up window that appears when double-clicked.

Importante

All elements **must** have a final destination in the dial plan in order to close a loop. This can be accomplished by implementing the Hang up element, or looping the element back to a Menu element or Digital Receptionist element elsewhere in the dial plan.

Once all desired dial plan elements and configurations are complete, remember to click Save before exiting the Dialplan Editor pop-up window. Then, click Apply changes on the Dial plans page to ensure they are implemented into Axivox production.

### Dial plan elements¶

The following elements are available in the New element drop-down menu, while designing a dial plan in the Dialplan Editor pop-up window.

#### Basic elements¶

These are the basic elements that are used in simple dial plans in Axivox:

  * Call: call an extension or queue.

  * Play a file: play an audio file or voice greeting.

  * Voicemail: forward to a voicemail (terminal).

  * Hang up: hang up the call (terminal).

  * Queue: attach a call queue with a group of users to answer a call.

  * Conference: add a conference room for a caller to connect to.




#### Basic routing elements¶

Routing elements change or route the path of a caller, these are some basic routing elements used in Axivox:

  * Menu: add a dial-by-number directory and configure downstream actions (not terminal).

  * Switch: attach a manual on/off control that can divert traffic based on whether it is opened (On) or closed (Off).

  * Digital Receptionist: attach a virtual dispatcher to listen for extensions to connect to.




#### Advanced routing elements¶

These are the more advanced elements that route calls in Axivox:

  * Dispatcher: create a call filter to route traffic based on the geo-location of the caller ID.

  * Access List: create a tailored access list with VIP customer preference.

  * Time Condition: create time conditions to route incoming traffic around holidays, or other sensitive time-frames.

  * Multi-Switch: a mechanism to create paths, and turn them on and off, to divert incoming calls.




#### Advanced elements¶

The following are more advanced elements (not routing) in Axivox:

  * Record: recording feature is enabled (requires plan change, enabled in Axivox settings).

  * Caller ID: replace the caller ID by the called number or free text.




Importante

Dial plan elements can be configured by double-clicking them, and linking different aspects of the Axivox console to them.

## Attach to incoming number¶

To attach an existing dial plan to an incoming number, go to [Axivox management console](https://manage.axivox.com/) , and click on Incoming numbers.

Next, click Edit next to the number to which the dial plan should be attached.

Doing so reveals a separate page wherein that number’s dial plan can be modified. To do that, select Dial plan from the Destination type for voice call field drop-down menu. Then, choose the desired dial plan from the Dial plan field that appears.

With that in place, that means when that specific number calls in, the configured dial plan is activated, and runs through the prompts to properly route the caller.

Finally, Save the changes, and click Apply changes in the upper-right corner.

### Basic dial plan scenario¶

The following showcases a basic dial plan scenario for call routing, where additional elements can be added to expand the setup. This basic dial plan scenario includes the following linked elements Start ‣ Play a file ‣ Menu ‣ (Hang-up, Calls, Queues, Conferences) ‣ (Voicemail, Hang-up).

Vedi anche

This setup does **not** include any basic or advanced call routing. For more information on call routing, reference this documentation: [Advanced dial plans](dial_plan_advanced.html).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/voip/axivox/dial_plan_basics.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](dial_plan_advanced.html "Advanced dial plans") |
  * [precedente](conference_calls.html "Conference calls") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Produttività](../../../productivity.html) »
  * [VoIP (Voice over Internet Protocol)](../../voip.html) »
  * [Axivox configuration](../axivox.html) »
  * Dial plan basics


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