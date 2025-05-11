# Website analytics — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](link_tracker.html "Link tracker") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Rendiconto](../reporting.html) »
  * Website analytics



# Website analytics¶

Website analytics helps website owners monitor how people use their site. It provides data on visitor demographics, behavior, and interactions, helping improve websites and marketing strategies.

You can track your Odoo website’s traffic using Plausible.io or Google Analytics. We recommend using Plausible.io as it is privacy-friendly, lightweight, and easy to use.

The Plausible analytics dashboard is also integrated into Odoo and can be accessed via Website ‣ Reporting ‣ Analytics.

## Plausible.io¶

Odoo hosts its own Plausible.io server and provides a free and ready-to-work Plausible.io solution for **Odoo Online** databases. Odoo automatically creates and sets up your account. You can start using it by going to Website ‣ Reporting ‣ Analytics.

Nota

**If you already have a Plausible.io account** and you want to connect it to your Odoo Online database, you must create two `ir.config.parameters` to use Plausible.io’s servers. To do so, enable the [developer mode](../../../general/developer_mode.html#developer-mode) and go to General Settings ‣ Technical – System Parameters. Click New and fill in the following Key and Value fields:

Chiave | Valore  
---|---  
`website.plausible_script` | `https://plausible.io/js/plausible.js`  
`website.plausible_server` | `https://plausible.io`  
  
Then, follow the steps below to connect your existing account with Plausible.io servers.

If your database is hosted on **Odoo.sh** or **On-premise** , or if you wish to use your own Plausible.io account, proceed as follows:

  1. Create or sign in to a Plausible account using the following link: <https://plausible.io/register>.

  2. If you are creating a new account, go through the registration and activation steps. When asked to provide your website details, add its Domain without including `www` (e.g., `example.odoo.com`) and change the Reporting Timezone if necessary. Click Add snippet to proceed to the next step. Ignore the Add JavaScript snippet instructions and click Start collecting data.

  3. Once done, click the Plausible logo in the upper-left part of the page to access your [list of websites](https://plausible.io/sites), then click the gear icon next to the website.

  4. In the sidebar, select Visibility, then click \+ New link.

  5. Enter a Name, leave the Password field empty, as the Plausible analytics dashboard integration in Odoo doesn’t support it, then click Create shared link.

  6. Copy the shared link.

  7. In Odoo, go to Website ‣ Configuration ‣ Settings.

  8. In the SEO section, enable Plausible Analytics, then paste the Shared Link and click Save.




Suggerimento

If you have [multiple websites](../configuration/multi_website.html), add your websites to your Plausible.io account by going to <https://plausible.io/sites> and clicking \+ Add website. In Odoo, in the **Website settings** , make sure to select the website in the Settings of Website field before pasting the Shared link.

Nota

Odoo automatically pushes two custom goals: `Lead Generation` and `Shop`.

Vedi anche

[Plausible Analytics documentation](https://plausible.io/docs)

## Google Analytics¶

To follow your Odoo website’s traffic with Google Analytics:

  1. Create or sign in to a Google account using the following link: [https://analytics.google.com](https://analytics.google.com/).

  2.      * If you are setting up Google Analytics for the first time, click Start measuring and go through the account creation step.

     * If you already have a Google Analytics account, sign in and click the gear icon in the bottom-left corner of the page to access the **Admin** page. Then, click \+ Create Property.

  3. Complete the next steps: [property creation](https://support.google.com/analytics/answer/9304153?hl=en/&visit_id=638278591144564289-3612494643&rd=2#property), business details, and business objectives.

  4. When you reach the **Data collection** step, choose the Web platform.

  5. Set up your data stream: Specify your Website URL and a Stream name, then click Create stream.

  6. Copy the Measurement ID.

  7. In Odoo, go to Website ‣ Configuration ‣ Settings.

  8. In the SEO section, enable Google Analytics, then paste the Measurement ID and click Save.




Suggerimento

If you have [multiple websites](../configuration/multi_website.html) with separate domains, it is recommended to create [one property](https://support.google.com/analytics/answer/9304153?hl=en/&visit_id=638278591144564289-3612494643&rd=2#property) per domain. In Odoo, in the **Website settings** , make sure to select the website in the Settings of Website field before pasting the Measurement ID.

Vedi anche

[Google documentation on setting up Analytics for a website](https://support.google.com/analytics/answer/1008015?hl=en/)

## Google Tag Manager¶

GTM is a tag management system that allows you to easily update measurement codes and related code fragments, collectively known as tags on your website or mobile app, directly through the code injector.

Avvertimento

  * Some GTM tags use data layers (e.g., advanced eCommerce tracking data layers) to retrieve variables and send them to Google Analytics. Data layers are currently not managed in Odoo.

  * Google Tag Manager may not be compliant with local data protection regulations.




To use GTM, proceed as follows:

  1. Create or sign in to a Google account by going to <https://tagmanager.google.com/>.

  2. In the Accounts tab, click Create account.

  3. Enter an Account Name and select the account’s Country.

  4. Enter your website’s URL in the Container name field and select the Target platform.

  5. Click Create and agree to the Terms of Service.

  6. Copy the `<head>` and `<body>` codes from the popup window. Then, go to your website, click Edit, go to the Themes tab, scroll down to the Website Settings section, then click <head> and </body> to paste the codes.




Nota

The data is collected in the marketing tools used to monitor the website (e.g., Google Analytics, Plausible, Facebook Pixel), not in Odoo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/website/reporting/analytics.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](link_tracker.html "Link tracker") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Rendiconto](../reporting.html) »
  * Website analytics


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