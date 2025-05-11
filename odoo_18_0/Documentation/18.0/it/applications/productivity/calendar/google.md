# Google Calendar synchronization — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../appointments.html "Appuntamenti") |
  * [precedente](outlook.html "Outlook Calendar synchronization") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Calendario](../calendar.html) »
  * Google Calendar synchronization



# Google Calendar synchronization¶

Synchronize Google Calendar with Odoo to see and manage meetings from both platforms (updates go in both directions). This integration helps organize schedules, so a meeting is never missed.

Vedi anche

  * [Autenticazione accesso Google](../../general/users/google.html)

  * [Collegare Gmail a Odoo utilizzando Google OAuth](../../general/email_communication/google_oauth.html)




## Installazione in Google¶

### Select (or create) a project¶

Create a new Google API project and enable the Google Calendar API. First, go to the [Google API Console](https://console.developers.google.com/) and log into the Google account.

Nota

If this is the first time visiting this page, Google will prompt the user to enter a country and agree to the Terms of Service. Select a country from the drop-down list and agree to the ToS.

Next, click Select a project and select (or create) an API project to configure OAuth in, and store credentials. Click New Project.

Give the API project a clear name, like `Odoo Sync`, so it can be identified. Then click the Create button.

### Enable Google calendar API¶

Now, click on Enabled APIs and Services in the left menu. Select Enabled APIs and Services again if the Search bar does not appear.

After that, search for `Google Calendar API` using the search bar and select Google Calendar API from the search results. Click Enable.

### Schermata di consenso OAuth¶

Now that the API project has been created, OAuth should be configured. To do that, click on OAuth consent screen in the left menu, then click the Get started button.

Avvertimento

Gli account Gmail _personali_ possono essere utilizzati solo con il tipo di utente **esterno** , il che significa che Google potrebbe richiedere l’approvazione o di aggiungere degli _Ambiti_. Tuttavia, l’uso di un account _Google WorkSpace_ consente di utilizzare il tipo di utente **interno**.

Si noti inoltre che quando la connessione API è in modalità di test _esterna_ , non è necessaria l’approvazione di Google. Il limite di utenti in questa modalità di test è impostato su 100 utenti.

Follow the proceeding steps, in order:

  1. In App Information, type `Odoo` in the App name field, then enter the email address for the User support email field and click the Next button.

  2. In Audience, select External, then click the Next button.

  3. In Contact Information, enter the email again, then click the Next button.

  4. In Finish, tick the checkbox to agree to Google API Services: User Policy. For the last step, click the Create button.




### Authorized domain setup¶

Next, any domains set to appear on the consent screen or in an OAuth client’s configuration must be pre-registered. To do so, navigate to Branding in the left menu. In the Authorized domains section, click the Add domain button to create a field to enter an authorized domain. Enter a domain, such as `odoo.com`, then click the Save button at the bottom of the page.

### Test users¶

To give users the ability to sync with personal Gmail accounts, they must be set as a test user. Setup test users by going to Audience in the left-side menu and clicking the Add users button in the Test users section. Enter any desired user emails, and click the Save button.

### Creare credenziali¶

The _Client ID_ and the _Client Secret_ are both needed to connect Google Calendar to Odoo. This is the last step in the Google console. Begin by clicking Clients in the left menu. Then, click Create Credentials, and select OAuth client ID, Google will open a guide to create credentials.

Under Create OAuth Client ID, select Website application for the Application Type field, and type `My Odoo Database` for the Name.

  * Under the Authorized JavaScript Origins section, click \+ Add URI and type the company’s Odoo full URL address.

  * Under the Authorized redirect URIs section, click \+ Add URI and type the company’s Odoo URL address followed by `/google_account/authentication`. Finally, click Create.




A Client ID and Client Secret will appear, save these somewhere safe.

## Installazione in Odoo¶

Once the _Client ID_ and the _Client Secret_ are located, open the Odoo database and go to Settings ‣ Calendar to find the Google Calendar feature. Tick the checkbox labeled Google Calendar.

Next, copy and paste the _Client ID_ and the _Client Secret_ from the Google Calendar API credentials page into their respective fields below the Google Calendar checkbox. Then, click Save.

Nota

Tick the Pause Synchronization checkbox to temporarily pause events from being updated. This allows for testing and troubleshooting without removing credentials or uninstalling the synchronization. To resume the sync, clear the checkbox and save.

## Sync calendar in Odoo¶

Finally, open the Calendar app in Odoo and click on the Google sync button to sync Google Calendar with Odoo.

Nota

When syncing Google Calendar with Odoo for the first time, the page will redirect to the Google Account. From there, select the Email Account that should have access, then select Continue (should the app be unverified), and finally select Continue (to give permission for the transfer of data).

Now, Odoo Calendar is successfully synced with Google Calendar!

Avvertimento

Odoo highly recommends testing the Google calendar synchronization on a test database and a test email address (that is not used for any other purpose) before attempting to sync the desired Google Calendar with the user’s production database.

Once a user synchronizes their Google calendar with the Odoo calendar:

  * Creating an event in Odoo causes Google to send an invitation to all event attendees.

  * Deleting an event in Odoo causes Google to send a cancellation to all event attendees.

  * Adding a contact to an event causes Google to send an invitation to all event attendees.

  * Removing a contact from an event causes Google to send a cancellation to all event attendees.




Events can be created in _Google Calendar_ without sending a notification by selecting Don’t Send when prompted to send invitation emails.

## Troubleshoot sync¶

There may be times when the _Google Calendar_ account does not sync correctly with Odoo. Sync issues can be seen in the database logs.

In these cases, the account needs troubleshooting. A reset can be performed using the Reset Account button, which can be accessed by navigating to Settings app ‣ Manage Users. Then, select the user to modify the calendar, and click the Calendar tab.

Next, click Reset Account under the correct calendar.

### Reset options¶

The following reset options are available for troubleshooting Google calendar sync with Odoo:

User’s Existing Events:

>   * Leave them untouched: no changes to the events.
> 
>   * Delete from the current Google Calendar account: delete the events from _Google Calendar_.
> 
>   * Delete from Odoo: delete the events from the Odoo calendar.
> 
>   * Delete from both: delete the events from both _Google Calendar_ and Odoo calendar.
> 
> 


Next Synchronization:

>   * Synchronize only new events: sync new events on _Google Calendar_ and/or Odoo calendar.
> 
>   * Synchronize all existing events: sync all events on _Google Calendar_ and/or Odoo calendar.
> 
> 


Click Confirm after making the selection to modify the user’s events and the calendar synchronization.

## FAQ Google OAuth¶

At times there can be configuration errors that occur, and troubleshooting is needed to resolve the issue. Below are the most common errors that may occur when configuring the _Google Calendar_ for use with Odoo.

### Production vs. testing publishing status¶

Choosing Production as the Publishing Status (instead of Testing) displays the following warning message:

`OAuth is limited to 100 sensitive scope logins until the OAuth consent screen is verified. This may require a verification process that can take several days.`

To correct this warning, navigate to the [Google API Platform](https://console.cloud.google.com/apis/credentials/consent). If the Publishing Status is In Production, click Back to Testing to correct the issue.

### No test users added¶

If no test users are added to the OAuth consent screen, then an Error 403: access_denied populates.

To correct this error, return to the OAuth consent screen, under APIs & Services, and add test users to the app. Add the email to be configured in Odoo.

### Tipo di applicazione¶

When creating the credentials (OAuth _Client ID_ and _Client Secret_), if Desktop App is selected for the Application Type, an Authorization Error appears (Error 400:redirect_uri_mismatch).

To correct this error, delete the existing credentials, and create new credentials, by selecting Web Application for the Application Type.

Then, under Authorized redirect URIs, click ADD URI, and type: `https://yourdbname.odoo.com/google_account/authentication` in the field, being sure to replace _yourdbname_ in the URL with the **real** Odoo database name.

Suggerimento

Ensure that the domain (used in the URI: `https://yourdbname.odoo.com/google_account/authentication`) is the exact same domain as configured in the `web.base.url` system parameter.

Access the `web.base.url` by activating [developer mode](../../general/developer_mode.html#developer-mode), and navigating to Settings app ‣ Technical header menu ‣ Parameters section ‣ System Parameters.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/calendar/google.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../appointments.html "Appuntamenti") |
  * [precedente](outlook.html "Outlook Calendar synchronization") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Calendario](../calendar.html) »
  * Google Calendar synchronization


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