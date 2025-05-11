# Ogone — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](paypal.html "PayPal") |
  * [precedente](mollie.html "Mollie") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Ogone



# Ogone¶

[Ogone](https://www.ingenico.com/), also known as **Ingenico Payment Services** is a France-based company that provides the technology involved in secure electronic transactions.

Vedi anche

  * [Enabling a payment provider](../payment_providers.html#payment-providers-add-new)

  * [Ogone’s documentation](https://epayments-support.ingenico.com/get-started/).




Avvertimento

The provider Ogone is deprecated. It is recommended to use [Stripe](stripe.html) instead.

## Settings in Ogone¶

### Create an API user¶

Log into your Ogone account and head to the Configuration tab.

You need to create an **API user** to be used in the creation of transactions from Odoo. While you can use your main account to do so, using an **API user** ensures that if the credentials used in Odoo are leaked, no access to your Ogone configuration is possible. Additionally, passwords for **API users** do not need to be updated regularly, unlike normal users.

To create an **API user** , go to Configuration ‣ Users and click on New User. The following fields must be configured:

  * UserID: you can choose anything you want.

  * User’s Name, E-mail and Timezone: you can enter the information you want.

  * Profile: should be set to Admin.

  * Special user for API: should be checked.




After the creation of the user, you are required to generate a password. Save the password and **UserID** , as they will be required later on during the setup.

Suggerimento

If you already have an user set up, make sure it is activated without any error. If not, simply click the Activate(Errors) button to reset the user.

### Set up Ogone for Odoo¶

Ogone must now be configured to accept payments from Odoo. Head to Configuration ‣ Technical Information ‣ Global Security Parameters, select SHA-512 as Hash Algorithm and UTF-8 as character encoding. Then, go to the Data and Origin verification tab of the same page and leave the URL field of the e-Commerce and Alias Gateway section blank.

Suggerimento

If you need to use another algorithm, such as `sha-1` or `sha-256`, within Odoo, activate the [developer mode](../../general/developer_mode.html#developer-mode) and go to the **Payment Providers** page in Accounting ‣ Configuration ‣ Payment Providers. Click on Ogone, and in the Credentials tab, select the algorithm you wish to use in the Hash function field.

You are now required to generate **SHA-IN** passphrases. **SHA-IN** and **SHA-OUT** passphrases are used to digitally sign the transaction requests and responses between Odoo and Ogone. By using these secret passphrases and the `sha-1` algorithm, both systems can ensure that the information they receive from the other was not altered or tampered with.

Enter the same **SHA-IN** passphrase in both Checks for e-Commerce & Alias Gateway and Checks for DirectLink and Batch (Automatic). You can leave the IP address field blank.

Your **SHA-IN** and **SHA-OUT** passphrases should be different, and between 16 and 32 characters long. Make sure to use the same **SHA-IN** and **SHA-OUT** passphrases throughout the entire Ogone configuration, as Odoo only allows a single **SHA-IN** and single **SHA-OUT** passphrase.

In order to retrieve the **SHA-OUT** key, log into your Ogone account, go to Configuration ‣ Technical Information ‣ Transaction feedback ‣ All transaction submission modes, and get or generate your **API Key** and **Client Key**. Be careful to copy your API key as you’ll not be allowed to get it later without generating a new one.

When done, head to Configuration ‣ Technical Information ‣ Transaction Feedback and check the following options:

  * The URL fields for HTTP redirection in the browser can be left empty, as Odoo will specify these URLs for every transaction request.

  * I would like to receive transaction feedback parameters on the redirection URLs: should be checked.

  * Direct HTTP server-to-server request: should to be set to `Online but switch to a deferred request when the online request fails`.

  * Both **URL** fields should contain the same following URL, with `<example>` replaced by your database: `https://<example>/payment/ogone/return`.

  * Dynamic eCommerce Parameters should contain the following values: `ALIAS`, `AMOUNT`, `CARDNO`, `CN`, `CURRENCY`, `IP`, `NCERROR` `ORDERID`, `PAYID`, `PM`, `STATUS`, `TRXDATE`. Other parameters can be included (if you have another integration with Ogone that requires them), but are not advised.

  * In the All transaction submission modes section, fill out **SHA-OUT** passphrase and disable `HTTP request for status change`.




To allow your customers to save their credit card credentials for future use, head to Configuration ‣ Alias ‣ My alias information. From this tab, you can configure how the user can have its card details saved, for how long the information is saved, if a checkbox to save the card information should be displayed, etc.

## Settings in Odoo¶

To set up Ogone in Odoo, head to Accounting ‣ Configuration ‣ Payment Providers and open the Ogone provider. In the Credentials tab, enter the **PSPID** of your Ogone account, and fill out the other fields as configured in your Ogone portal.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers/ogone.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](paypal.html "PayPal") |
  * [precedente](mollie.html "Mollie") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Ogone


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