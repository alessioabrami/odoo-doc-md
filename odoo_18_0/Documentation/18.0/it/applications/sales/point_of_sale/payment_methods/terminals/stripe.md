# Stripe — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tyro.html "Tyro") |
  * [precedente](six.html "SIX") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Stripe



# Stripe¶

Connecting a payment terminal allows you to offer a fluid payment flow to your customers and ease the work of your cashiers.

Importante

  * Stripe payment terminals do not require an [IoT Box](../../../../general/iot.html)

  * Stripe terminals can be used in many countries, but not worldwide. Check the [global availability for Stripe Terminal](https://support.stripe.com/questions/global-availability-for-stripe-terminal).

  * Stripe’s integration works with [Stripe Terminal smart readers](https://docs.stripe.com/terminal/smart-readers)




Vedi anche

  * [Stripe as payment provider](../../../../finance/payment_providers/stripe.html)

  * [List of payment methods supported by Stripe](https://stripe.com/payments/payment-methods)




## Configurazione¶

### Configure the payment method¶

Activate **Stripe** in the settings by going to Point of Sale ‣ Configuration ‣ Settings ‣ Payment Terminals and enabling Stripe.

Then, create the payment method:

  * Go to Point of Sale ‣ Configuration ‣ Payment Methods, click Create, and complete the Method field with your payment method’s name;

  * Set the Journal field as Bank and the Use a Payment Terminal field as Stripe;

  * Enter your payment terminal serial number in the Stripe Serial Number field;

  * Click Don’t forget to complete Stripe connect before using this payment method.




Nota

  * Click Identify Customer to allow this payment method **exclusively** for identified customers. For any unidentified customers to be able to pay with Stripe, leave the Identify Customer field unchecked.

  * The Outstanding Account and the Intermediary Account can stay empty to use the default accounts.

  * Find your payment terminal serial number under the device or on [Stripe’s dashboard](https://dashboard.stripe.com/).




### Connect Stripe to Odoo¶

Click Connect Stripe. Doing so redirects you automatically to a configuration page. Fill in all the information to create your Stripe account and link it with Odoo. Once the forms are completed, the API keys (Publishable Key and Secret Key) can be retrieved on **Stripe’s** website. To do so, click Get your Secret and Publishable keys, click the keys to copy them, and paste them into the corresponding fields in Odoo. Your terminal is ready to be configured in a POS.

Nota

  * When you use **Stripe** exclusively in Point of Sale, you only need the **Secret Key** to use your terminal.

  * When you use Stripe as **payment provider** , the State can stay set as Disabled.

  * For databases hosted **On-Premise** , the Connect Stripe button does not work. To retrieve the API keys manually, log in to your [Stripe dashboard](https://dashboard.stripe.com/), type `API` in the search bar, and click Developers > API.




### Configure the payment terminal¶

Swipe right on your payment terminal, click Settings, enter the admin PIN code, validate and select your network.

Nota

  * The user’s device and the terminal must share the same network.

  * In case of a Wi-Fi connection, the network must be secured.

  * You must enter the admin PIN code to access your payment terminal settings. By default, this code is `07139`.




### Link the payment method to a POS¶

To add a **payment method** to your point of sale, go to Point of Sale ‣ Configuration ‣ Settings. Select the POS, scroll down to the Payments section, and add your payment method for **Stripe** in the Payment Methods field.

## Risoluzione problemi¶

### Payment terminal unavailable in your Stripe account¶

If the payment terminal is unavailable in your Stripe account, you must add it manually:

  1. Log into your [Stripe’s dashboard](https://dashboard.stripe.com/) and go to Stripe dashboard ‣ Payments ‣ Readers ‣ Locations;

  2. Add a location by clicking the \+ New button or selecting an already created location;

  3. Click the \+ New button in the Readers box and fill in the required information.




Nota

You must provide a **registration code**. To retrieve that code, swipe right on your device, enter the admin PIN code (by default: `07139`), validate, and click Generate a registration code.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/point_of_sale/payment_methods/terminals/stripe.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tyro.html "Tyro") |
  * [precedente](six.html "SIX") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Vendite](../../../../sales.html) »
  * [Punto vendita](../../../point_of_sale.html) »
  * [Metodo di pagamento](../../payment_methods.html) »
  * [Payment terminals](../terminals.html) »
  * Stripe


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