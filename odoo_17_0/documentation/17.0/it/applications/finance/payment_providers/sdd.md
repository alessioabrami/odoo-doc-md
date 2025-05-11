# Addebito Diretto SEPA — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](adyen.html "Adyen") |
  * [precedente](wire_transfer.html "Wire transfers") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Addebito Diretto SEPA



# Addebito Diretto SEPA¶

SEPA (Single Euro Payments Area) is a payment-integration initiative of the European Union that facilitates standardized and simplified electronic payments in euros across participating countries.

SEPA Direct Debit (SDD) is a payment provider that allows future payments to be collected from customers” bank accounts based on a signed [SEPA Direct Debit mandate](../accounting/payments/batch_sdd.html#accounting-batch-sdd-sdd-mandates). This mandate authorizes the recipient to automatically initiate one-time or [recurring](../../sales/subscriptions.html) payments using SDD.

Importante

To use the SEPA Direct Debit (SDD) payment provider and create [SEPA Direct Debit mandates](../accounting/payments/batch_sdd.html#accounting-batch-sdd-sdd-mandates):

  * The invoice being paid must be for an amount in euros.

  * The SEPA Direct Deposit (SDD) feature must be enabled, and the company’s Creditor Identifier must be defined in the [Accounting or Invoicing settings](../accounting/payments/batch_sdd.html#accounting-batch-sdd-sepa-configuration).




To configure **SEPA Direct Debit** :

  1. [Navigate to the SEPA Direct Debit payment provider](../payment_providers.html#payment-providers-supported-providers).

  2. In the Configuration tab, select whether the memo or Communication to be displayed alongside the payment instructions should be:

     * Based on Document Reference: the sales order or invoice number

     * Based on Customer ID: the customer identifier

  3. Select the Enable QR codes check box to activate QR code payments.

Nota

[Additional accounting setup](../accounting/customer_invoices/epc_qr_code.html) is required to use QR codes.

  4. Edit the default payment instructions in the Messages tab to include your **bank account number**. These instructions are displayed at the end of the checkout process on your ecommerce website or on the customer portal.

  5. Set the State field to Enabled.




Importante

  * Leave the Currencies field set to the default EUR tag to ensure SDD is only available for payments in euros.

  * The Bank Account defined for the Payment Journal must be a valid IBAN.




Suggerimento

You can also test SEPA direct debit payments using the [Modalità di prova](../payment_providers.html#payment-providers-test-mode).

Vedi anche

[Online payments](../payment_providers.html)

## Online payments with SDD¶

Customers selecting SDD as a payment method are prompted to enter their IBAN to complete the [SEPA Direct Debit mandate](../accounting/payments/batch_sdd.html#accounting-batch-sdd-sdd-mandates).

The SDD mandate is then automatically created in Draft based on the provided IBAN. To validate the information, customers must confirm each new mandate with a successful bank transfer of the expected amount **using the specified payment reference (communication)**. Once this initial payment is received and reconciled, the mandate is automatically validated and updated to the Active status. Once a mandate is active, it is reused for all subsequent payments made with the SDD payment method. You can then collect them by [uploading them to your online banking interface](../accounting/payments/batch_sdd.html#accounting-batch-sdd-xml).

Vedi anche

[SEPA Direct Debit (SDD) customer payments](../accounting/payments/batch_sdd.html)

Nota

SDD is also available as a payment method through other providers, such as [Adyen](adyen.html) and [Buckaroo](buckaroo.html). In these cases, SDD mandates are handled externally by the payment provider.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers/sdd.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](adyen.html "Adyen") |
  * [precedente](wire_transfer.html "Wire transfers") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Addebito Diretto SEPA


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