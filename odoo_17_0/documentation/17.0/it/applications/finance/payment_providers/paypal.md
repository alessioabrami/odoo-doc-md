# PayPal — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](razorpay.html "Razorpay") |
  * [precedente](ogone.html "Ogone") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * PayPal



# PayPal¶

[Paypal](https://www.paypal.com/) is an American online payment provider available worldwide, and one of the few that does not charge a subscription fee.

Nota

While PayPal is available in [over 200 countries/regions](https://www.paypal.com/webapps/mpp/country-worldwide), only [a selection of currencies are supported](https://developer.paypal.com/docs/reports/reference/paypal-supported-currencies).

## Settings in PayPal¶

To access your PayPal account settings, log into PayPal, open the Account Settings, and open the Website payments menu.

Importante

Note that for PayPal to work **in Odoo** , the options Auto Return and PDT **must** be enabled.

### Auto Return¶

The **Auto Return** feature automatically redirects customers to Odoo once the payment is processed.

From Website payments, go to Website preferences ‣ Update ‣ Auto return for website payments ‣ Auto return and select On. Enter the address of your Odoo database (e.g., `https://yourcompany.odoo.com`) in the Return URL field, and Save.

Nota

Any URL does the job. Odoo only needs the setting to be enabled since it uses another URL.

### Payment Data Transfer (PDT)¶

PDT allows to receive payment confirmations, displays the payment status to the customers, and verifies the authenticity of the payments. From Website preferences ‣ Update, scroll down to Payment data transfer and select On.

Suggerimento

PayPal displays your **PDT Identity Token** as soon as Auto return and Payment Data Transfer (PDT) are enabled. If you need the **PDT Identity Token** , disable and re-enable Payment data transfer to display the token again.

### PayPal Account Optional¶

We advise not to prompt customers to log in with a PayPal account upon payment. It is better and more accessible for customers to pay with a debit/credit card. To disable that prompt, go to Account Settings ‣ Website payments ‣ Update and select On for PayPal account optional.

### Payment Messages Format¶

If you use accented characters (or anything other than primary Latin characters) for customer names or addresses, then you **must** configure the encoding format of the payment request sent by Odoo to PayPal. If you do not, some transactions fail without notice.

To do so, go to [your production account](https://www.paypal.com/cgi-bin/customerprofileweb?cmd=_profile-language-encoding). Then, click More Options and set the two default encoding formats as UTF-8.

Suggerimento

  * For Encrypted Website Payments & EWP_SETTINGS error, please check the [Paypal documentation](https://developer.paypal.com/docs/online/).

  * Configure your Paypal Sandbox account, then follow this [link](https://sandbox.paypal.com/cgi-bin/customerprofileweb?cmd=_profile-language-encoding) to configure the encoding format in a test environment.




## Settings in Odoo¶

Vedi anche

[Enabling a payment provider](../payment_providers.html#payment-providers-add-new)

Odoo needs your **API Credentials** to connect with your PayPal account. To do so, go to Accounting ‣ Configuration ‣ Payment Providers and Activate PayPal. Then, enter your PayPal account credentials in the Credentials tab:

  * Email: the login email address in Paypal;

  * PDT Identity Token: the key used to verify the authenticity of transactions.




## Test environment¶

### Configurazione¶

Thanks to PayPal sandbox accounts, you can test the entire payment flow in Odoo.

Log into the [Paypal Developer Site](https://developer.paypal.com/) using your PayPal credentials, which creates two sandbox accounts:

  * A business account (to use as merchants, e.g., [pp.merch01-facilitator@example.com](mailto:pp.merch01-facilitator%40example.com));

  * A default personal account (to use as shoppers, e.g., [pp.merch01-buyer@example.com](mailto:pp.merch01-buyer%40example.com)).




Log into PayPal sandbox using the merchant account and follow the same configuration instructions. Enter your sandbox credentials in Odoo (Accounting ‣ Configuration ‣ Payment Providers ‣ PayPal in the Credentials tab, and make sure the status is set on Test Mode.

Run a test transaction from Odoo using the sandbox personal account.

Vedi anche

  * [Online payments](../payment_providers.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers/paypal.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](razorpay.html "Razorpay") |
  * [precedente](ogone.html "Ogone") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * PayPal


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales order
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Order
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
  *[ACH]: Automated Clearing House
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer