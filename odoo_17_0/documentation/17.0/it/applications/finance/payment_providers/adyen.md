# Adyen — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](alipay.html "Alipay") |
  * [precedente](sdd.html "Addebito Diretto SEPA") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Adyen



# Adyen¶

[Adyen](https://www.adyen.com/) is a Dutch company that offers several online payment possibilities.

Vedi anche

  * [Enabling a payment provider](../payment_providers.html#payment-providers-add-new)

  * [Online payments](../payment_providers.html)




Nota

Adyen works only with customers processing **more** than **10 million annually** or invoicing a **minimum** of **1.000** transactions **per month**.

## Configurazione¶

Vedi anche

[Enabling a payment provider](../payment_providers.html#payment-providers-add-new)

First, reach Adyen support to enable multiple partial capture for you.

### Credentials tab¶

Odoo needs your **API Credentials** to connect with your Adyen account, which comprise:

  * **Merchant Account** : The code of the merchant account to use with Adyen.

  * API Key: The API key of the webservice user.

  * Client Key: The client key of the webservice user.

  * HMAC Key: The HMAC key of the webhook.

  * Checkout API URL: The base URL for the Checkout API endpoints.

  * Recurring API URL: The base URL for the Recurring API endpoints.




You can copy your credentials from your Adyen account, and paste them in the related fields under the **Credentials** tab.

Importante

If you are trying Adyen as a test, with an Adyen _test account_ , head to Accounting ‣ Configuration ‣ Payment Providers. There, click on Adyen, enable Test Mode and enter your credentials in the Credentials tab.

#### API Key and Client Key¶

In order to retrieve the API Key and the Client Key, log into your Adyen account, go to Developers ‣ API Credentials.

  * If you already have an API user, open it.

  * If you don’t have an API user yet, click on **Create new credential**.




Go to Server settings ‣ Authentification and copy or generate your **API Key**. Be careful to copy your API key as you’ll not be allowed to get it later without generating a new one.

Now, head to Client settings ‣ Authentification and cody or generate your **Client Key**. This is also the place where you can allow payments to be made from your website.

#### HMAC key¶

In order to retrieve the HMAC Key, you’ll need to configure a `Standard Notification` webhook. For this, log into your Adyen account then go to Developers ‣ Webhooks ‣ Add webhook ‣ Add Standard notification.

There, in General ‣ Server configuration ‣ URL, enter your server address followed by `/payment/adyen/notification`.

Then enter Security ‣ HMAC Key ‣ Generate. Be careful to copy the key as you will not be allowed to do it later without generating a new one.

You have to save the webhook to finalize its creation.

#### API URLs¶

All Adyen API URLs include a customer area-specific prefix generated by Adyen. To configure the URLs, proceed as follows:

  1. Log into your Adyen account, then go to Developers ‣ API URLs.

  2. Copy the Prefix for your live Customer area (i.e., **data center**) and save it for later.

  3. In Odoo, [navigate to the payment provider Adyen](../payment_providers.html#payment-providers-add-new).

  4. In the Checkout API URL field, enter the following URL and replace `yourprefix` with the prefix you previously saved: `https://yourprefix-checkout-live.adyenpayments.com/checkout`

  5. In the Recurring API URL field, enter the following URL and replace `yourprefix` with the prefix you previously saved: `https://yourprefix-pal-live.adyenpayments.com/pal/servlet/Recurring`.




Nota

If you are trying Adyen as a test, you can use the following URLs instead:

  * Checkout API URL: `https://checkout-test.adyen.com`

  * Recurring API URL: `https://pal-test.adyen.com/pal/servlet/Recurring`




### Conto Adyen¶

#### Allow payments from a specific origin¶

To allow payment originated from your website, follow the steps in API Key and Client Key to navigate to your API user and go to Add allowed origins, then add the URLs from where payments will be made (the URLs of the servers hosting your Odoo instances).

### Place a hold on a card¶

Adyen allows you to capture an amount manually instead of having an immediate capture.

To set it up, enable the **Capture Amount Manually** option on Odoo, as explained in the [payment providers documentation](../payment_providers.html#payment-providers-manual-capture).

Then, open your Adyen Merchant Account, go to Account ‣ Settings, and set the **Capture Delay** to **manual**.

Attenzione

  * If you configure Odoo to capture amounts manually, make sure to set the **Capture Delay** to **manual** on Adyen. Otherwise, the transaction will be blocked in the authorized state in Odoo.




Nota

  * After **7 days** , if the transaction has not been captured yet, the customer has the right to **revoke** it.




Vedi anche

[Online payments](../payment_providers.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers/adyen.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](alipay.html "Alipay") |
  * [precedente](sdd.html "Addebito Diretto SEPA") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Adyen


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