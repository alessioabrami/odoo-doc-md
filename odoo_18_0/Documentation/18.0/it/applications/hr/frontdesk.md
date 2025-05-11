# Reception — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](frontdesk/visitors.html "Visitatori") |
  * [precedente](appraisals/skills_evolution.html "Skills evolution") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Reception



# Reception¶

The Odoo **Frontdesk** application provides a way for visitors to check in to a building or location, and alert the person they are meeting about their arrival. Additionally, they can request a preconfigured beverage to be brought to them, while they wait.

This application is ideal for businesses that do **not** have someone working at a reception desk, or locations **without** a designated waiting area available to guests and visitors.

## Configurazione¶

The first item to configure with the **Frontdesk** application is the station, followed by any drink selections that might optionally be offered.

### Aree¶

In Odoo’s **Frontdesk** application, a _Station_ can be thought of as any location where someone can sign in and wait for an employee. This is typically some form of waiting room, such as a lobby. Each station has a kiosk where visitors check in.

When setting up the **Frontdesk** application, a minimum of one station **must** be configured, but there is no limit to how many stations can be created and configured.

To create a station, navigate to Frontdesk app ‣ Configuration ‣ Stations, and click New. When clicked, a blank frontdesk form appears.

Inserisci le seguenti informazioni nel modulo:

  * Frontdesk Name: enter a name for the specific frontdesk location. This should be short and identifiable, such as `Reception Desk` or `Main Lobby`. This field is required in order to create a station.

  * Responsibles: select the person (or persons) who are alerted when a visitor checks in using this specific frontdesk. Multiple selections can be entered. This field is required in order to create a station.

  * Kiosk URL: this field auto-populates once the frontdesk form is saved, with at least the Frontdesk Name and Responsibles fields filled. To save manually, click the __(Save manually) icon located at the top of the form.

Once saved, a URL is generated in the Kiosk URL field. This URL is one way the frontdesk kiosk is accessed.

To access the kiosk, click the Copy button at the end of the URL, and navigate to that URL in a web browser. This URL opens that specific station’s frontdesk sign-in page.

Suggerimento

To add an image/photo to a frontdesk form, hover over the (camera with a “+” sign) icon in the top-right of the form to reveal a __(Edit) icon.

Click on the __(Edit) icon to open a file explorer, navigate to the desired image/photo file, then click Open to select it.

The image selected for the station photo appears as the background image for the station kiosk.




#### Options tab¶

  * Host Selection: if the visitor is attending a meeting, this option allows the visitor to select the meeting host from a presented list, and notify that individual. When enabled, additional fields appear, as detailed below.

  * Authenticate Guest: if additional information is required when a guest checks in, enable this option, and select which of the following are required:

    * Email: select whether the guest’s email address is Required, Optional, or if the information is not requested at all (None).

    * Phone: select whether the guest’s phone number is Required, Optional, or if the information is not requested at all (None).

    * Organization: select whether the guest’s organization is Required, Optional, or if the information is not requested at all (None).

  * Theme: select the color mode of the kiosk. Choose either Light or Dark. The Light selection displays a pale gray background on the kiosk, whereas the Dark selection displays a dark gray and black background.

  * Self Check-In: enable this option to present a check-in QR code on the kiosk. The QR code allows guests to check in using their mobile device, instead of using the kiosk. This option is recommended for a busy kiosk with multiple guests checking in at any time.

  * Offer Drinks: enable this option to offer guests a drink upon check in. If this option is enabled, it is necessary to configure the drinks being offered, via the Configure Drinks link that appears when the option is enabled. Once all drink options are configured, select each drink to be offered using the drop-down menu.




Nota

The following options are only visible in the Options tab if the Host Selection option is enabled.

  * Notify by email: enable this option to have an email sent to the person the guest is visiting upon check in. When enabled, an Email Template field appears beneath, with the default Frontdesk Email Template selected.

To change the default email template, click the drop-down menu in the Email Template field, then select another email template.

To modify the currently selected template, click the __(Internal link) icon at the end of the line, and make any edits to the template.

  * Notify by SMS: enable this option to have an SMS (text) message sent to the person the guest is visiting upon check in. When enabled, an SMS Template field appears beneath, with the default Frontdesk SMS Template selected.

To change the default SMS template, click the drop-down menu in the SMS Template field, and select another SMS template.

To modify the currently selected template, click the __(Internal link) icon at the end of the line, and make any desired edits to the content of the template. The SMS message may have a maximum of 242 characters, which fits in 4 SMS (UNICODE) messages.

  * Notify by Discuss: this option is enabled by default when the Host Selection option is enabled. This option opens a **Discuss** application message window with the person the guest is visiting upon check in.

When enabled, a default message appears for the person the guest is visiting. The **Discuss** application **must** be installed in order for this option to work.




Nota

 _Discuss_ is installed by default when creating an Odoo database, and does not count towards billing. As long as the _Discuss_ application is not intentionally uninstalled, the Notify by Discuss option works.

Example

The default message format for the Notify by Discuss option is: `(Frontdesk Station) Check-In: (Guest Name) (Guest Phone Number) (Organization) to meet (Name of employee).`

An example of how that might appear in a **Discuss** message is: `Main Lobby Check-In: John Doe (555-555-5555) (Odoo, Inc.) to meet Marc Demo.`

#### Side Message tab¶

Enter any desired text to appear on the station kiosk after a guest has checked in, such as a welcome greeting or any necessary instructions. The text appears on the confirmation page, on the right side of the screen after a guest has completed the check-in process.

### Bevande¶

After a station is created, the next step is to configure the drinks to offer visitors, if desired.

Nota

This step is **not** necessary or required for the **Frontdesk** application to work, and only needs to be configured if drinks are offered to guests.

To add a drink option, navigate to Frontdesk app ‣ Configuration ‣ Drinks, and click New. Doing so reveals a blank drink form to configure.

Enter the following information on the drink form:

  * Drink Name: type the name of the drink option in this field. This field is required.

  * People to Notify: use the drop-down menu in this field to select who is notified when the drink is selected. Multiple people can be entered in this field. This field is required.

  * Sequence: enter a numerical value in this field to indicate where in the list of drink options this specific option appears. The lower the number, the higher on the list the drink appears. For example, entering the number one would place that drink at the top of the list, and appear first in the sequence.




Suggerimento

To add an image/photo to a drink form, hover over the (camera with a “+” sign) icon in the top-right of the form to reveal a __(Edit) icon.

Click on the __(Edit) icon to open a file explorer, navigate to the desired image/photo file, then click Open to select it.

The image selected now appears in the picture field, and is set as the image for the drink.

## Station dashboard¶

Suggerimento

To add an image/photo to a drink form, hover over the (camera with a “+” sign) icon in the top-right of the form to reveal a __(Edit) icon.

Click on the __(Edit) icon to open a file explorer, navigate to the desired image/photo file, then click Open to select it.

The image selected now appears in the picture field, and is set as the image for the drink.

## Kiosk setup¶

Set up each kiosk for use after configuring the various stations. It is recommended to use a dedicated device for each frontdesk kiosk, such as a tablet.

Navigate to the kiosk in one of two ways:

  * Navigate to the main **Frontdesk** application dashboard, and click the Open Desk button on the desired station card. The kiosk loads in a new browser tab.

  * Navigate to Frontdesk app ‣ Configuration ‣ Stations, and click on the desired station. Then, click the Copy button at the end of the Kiosk URL line, and paste the URL into a new browser tab or window.




Importante

Once a frontdesk kiosk is accessed, either with the Open Desk button or the Kiosk URL, the user is _automatically signed out of the database_ on that specific device.

This is a security measure designed to prevent unauthorized access to the database.

## Rendiconto¶

The **Frontdesk** application has two reports available: Visitors and Drinks.

To access either of these reports, navigate to Frontdesk app ‣ Reporting to reveal a drop-down menu containing the options: Visitors and Drinks.

The Visitors report displays the number of visitors by month, for the current year. The Drinks report shows how many total requests were made for each drink.

As with all reports in Odoo, the filters and groups can be modified to show other metrics, as well.

Vedi anche

  * [Visitatori](frontdesk/visitors.html)




  * [Visitatori](frontdesk/visitors.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/hr/frontdesk.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](frontdesk/visitors.html "Visitatori") |
  * [precedente](appraisals/skills_evolution.html "Skills evolution") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Reception


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
  *[POS]: Punto vendita
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