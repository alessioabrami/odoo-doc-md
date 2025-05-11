# Outlook Calendar synchronization — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Google Calendar synchronization") |
  * [precedente](../calendar.html "Calendario") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Calendario](../calendar.html) »
  * Outlook Calendar synchronization



# Outlook Calendar synchronization¶

Synchronizing a user’s _Outlook Calendar_ with Odoo is useful for keeping track of tasks and appointments across all related applications.

Vedi anche

  * [Autenticazione accesso Microsoft Azure](../../general/users/azure.html)

  * [Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth](../../general/email_communication/azure_oauth.html)




## Microsoft Azure setup¶

To sync the _Outlook Calendar_ with Odoo’s _Calendar_ , a Microsoft _Azure_ account is required. Creating an account is free for users who have never tried, or paid for, _Azure_. For more information, view the account options on the [Azure website](https://azure.microsoft.com/en-us/free/?WT.mc_id=A261C142F).

Refer to [Microsoft’s documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant) on how to set up a Microsoft _Entra ID_ (formally called Microsoft _Azure Active Directory (Azure AD)_). This is an API console to manage and register Microsoft applications.

Existing Microsoft _Entra ID_ users should log in at the [Microsoft Azure developer portal](https://portal.azure.com/#home). Next, select View under the section labeled Manage Microsoft Entra ID.

### Register application¶

After logging in with the Microsoft _Entra ID_ , [register an application](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

To create an application, click \+ Add in the top menu. From the resulting drop-down menu, select App Registration.

Enter a unique Name for the connected application.

Choosing the appropriate Supported account type is essential, or else the connected application will not work. Users who wish to connect their _Outlook Calendar_ to Odoo should select the Accounts in any organizational directory (Any Microsoft Entra ID directory - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox) option for Supported account types.

When configuring the Redirect URI, choose the Web option from the first drop-down menu. Then, enter the Odoo database URI (URL) followed by `/microsoft_account/authentication`.

Example

Enter `https://yourdbname.odoo.com/microsoft_account/authentication` for the Redirect URI. Replace `yourdbname.odoo.com` with the URL.

Suggerimento

Ensure the database’s URL (domain) used in the URI is the exact same domain as the one configured on the `web.base.url` system parameter.

Access the `web.base.url` by activating [developer mode](../../general/developer_mode.html#developer-mode), and navigating to Settings app ‣ Technical header menu ‣ Parameters section ‣ System Parameters. Then, select it from the Key list on the System Parameters page.

For more information on the restrictions and limitations of URIs, check Microsoft’s [Redirect URI (reply URL) restrictions and limitations](https://docs.microsoft.com/en-us/azure/active-directory/develop/reply-url) page.

Finally, on the application registration page, click Register button to complete the application registration. The Application (client) ID is produced. Copy this value, as it is needed later, in the Configuration in Odoo.

### Create client secret¶

The second credential needed to complete the synchronization of the Microsoft _Outlook Calendar_ is the _Client Secret_. The user **must** add a client secret, as this allows Odoo to authenticate itself, requiring no interaction from the user’s side. _Certificates_ are optional.

To add a client secret, click Certificates & secrets in the left menu. Then click \+ New client secret to create the client secret.

Next, type a Description, and select when the client secret Expires. Available options include: 90 days (3 months), 365 days (12 months), 545 days (18 months), 730 days (24 months) or Custom. The Custom option allows the administrator to set a Start and End date.

Finally, click Add to Add a client secret.

Suggerimento

Since resetting the synchronization can be tricky, Odoo recommends setting the maximum allowed expiration date for the client secret (24 months or custom), so there is no need to re-synchronize soon.

Copy the Value for use in the next section.

Avvertimento

Client secret values cannot be viewed, except immediately after creation. Be sure to save the secret when created _before_ leaving the page.

## Configuration in Odoo¶

In the Odoo database, go to Calendar app ‣ Configuration ‣ Settings, and tick the checkbox beside the Outlook Calendar setting. Remember to click Save to implement the changes.

From the Microsoft _Azure_ portal, under the Overview section of the application, copy the Application (Client) ID, if it has not already been copied, and paste it into the Client ID field in Odoo.

Copy the previously-acquired Value (Client Secret Value), and paste it into the Client Secret field in Odoo.

Finally, on the Odoo Settings ‣ General Settings page, click Save.

## Sync with Outlook¶

Avvertimento

Odoo highly recommends testing the Outlook calendar synchronization on a test database and a test email address (that is not used for any other purpose) before attempting to sync the desired Outlook Calendar with the user’s production database.

If the user has any past, present, or future events on their Odoo calendar before syncing their Outlook calendar, Outlook will treat the events pulled from Odoo’s calendar during the sync as new events, causing an email notification to be sent from Outlook to all the event attendees.

To avoid unwanted emails being sent to all past, present, and future event attendees, the user must add the events from the Odoo calendar to the Outlook calendar before the first ever sync, delete the events from Odoo, and then start the sync.

Even after synchronizing the Odoo Calendar with the Outlook calendar, Outlook will still send a notification to all event participants every time an event is edited (created, deleted, unarchived, or event date/time changed), with no exceptions. This is a limitation that cannot be fixed from Odoo’s side.

In summary, once a user synchronizes their Outlook calendar with the Odoo calendar:

  * Creating an event in Odoo causes Outlook to send an invitation to all event attendees.

  * Deleting an event in Odoo causes Outlook to send a cancellation to all event attendees.

  * Unarchiving an event in Odoo causes Outlook to send an invitation to all event attendees.

  * Archiving an event in Odoo causes Outlook to send a cancellation to all event attendees.

  * Adding a contact to an event causes Outlook to send an invitation to all event attendees.

  * Removing a contact from an event causes Outlook to send a cancellation to all event attendees.




### Sync Odoo Calendar and Outlook¶

In the Odoo database, open to the _Calendar_ module, and click the Outlook sync button on the right-side of the page, beneath the monthly calendar.

The synchronization is a two-way process, meaning that events are reconciled in both accounts (_Outlook_ and Odoo). The page redirects to a Microsoft login page, and the user is asked to log in to their account, if they are not already. Finally, grant the required permissions by clicking Accept.

Nota

All users that want to use the synchronization simply need to sync their calendar with Outlook. The configuration of Microsoft’s _Azure_ account is only done once, as Microsoft _Entra ID_ tenants” client IDs and client secrets are unique, and help the user manage a specific instance of Microsoft cloud services for internal and external users.

Vedi anche

  * [Plug-in Outlook](../../general/integrations/mail_plugins/outlook.html)

  * [Google Calendar synchronization](google.html)




## Troubleshoot sync¶

There may be times when the _Microsoft Outlook Calendar_ account does not sync correctly with Odoo. Sync issues can be seen in the database logs.

In these cases, the account needs troubleshooting. A reset can be performed using the Reset Account button, which can be accessed by navigating to Settings app ‣ Manage Users. Then, select the user to modify the calendar, and click on the Calendar tab.

Next, click Reset Account under the correct calendar.

### Reset options¶

The following reset options are available for troubleshooting _Microsoft Outlook Calendar_ sync with Odoo:

User’s Existing Events:

>   * Leave them untouched: no changes to the events.
> 
>   * Delete from the current Microsoft Calendar account: delete the events from _Microsoft Outlook Calendar_.
> 
>   * Delete from Odoo: delete the events from the Odoo calendar.
> 
>   * Delete from both: delete the events from both _Microsoft Outlook Calendar_ and Odoo calendar.
> 
> 


Next Synchronization:

>   * Synchronize only new events: sync new events on _Microsoft Outlook Calendar_ and/or Odoo calendar.
> 
>   * Synchronize all existing events: sync all events on _Microsoft Outlook Calendar_ and/or Odoo calendar.
> 
> 


Click Confirm after making the selection to modify the user’s events and the calendar synchronization.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/productivity/calendar/outlook.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](google.html "Google Calendar synchronization") |
  * [precedente](../calendar.html "Calendario") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Calendario](../calendar.html) »
  * Outlook Calendar synchronization


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