# Authorize.Net — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](buckaroo.html "Buckaroo") |
  * [precedente](asiapay.html "AsiaPay") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Authorize.Net



# Authorize.Net¶

[Authorize.Net](https://www.authorize.net/) is a United States-based online payment solution provider, allowing businesses to accept **credit cards**.

## Configurazione¶

Vedi anche

  * [Enabling a payment provider](../payment_providers.html#payment-providers-add-new)




### Credentials tab¶

Odoo needs your **API Credentials & Keys** to connect with your Authorize.Net account, which comprise:

  * **API Login ID** : The ID solely used to identify the account with Authorize.Net.

  * **API Transaction Key**

  * **API Signature Key**

  * **API Client Key**




To retrieve them, log into your Authorize.Net account, go to Account ‣ Settings ‣ Security Settings ‣ API Credentials & Keys, generate your **Transaction Key** and **Signature Key** , and paste them on the related fields in Odoo. Then, click on **Generate Client Key**.

Importante

To test Authorize.Net with a _sandbox_ account, change the State to Test Mode. We recommend doing this on a test Odoo database, rather than on your main database.

If you use the Test Mode with a regular account, it results in the following error: _The merchant login ID or password is invalid or the account is inactive_.

### Configuration tab¶

#### Place a hold on a card¶

With Authorize.Net, you can enable the [manual capture](../payment_providers.html#payment-providers-manual-capture). If enabled, the funds are reserved for 30 days on the customer’s card, but not charged yet.

Avvertimento

After **30 days** , the transaction is **voided automatically** by Authorize.Net.

Vedi anche

  * [Online payments](../payment_providers.html)




## ACH payments (USA only)¶

ACH is an electronic funds transfer system used between bank accounts in the United States.

### Configurazione¶

To give customers the possibility to pay using ACH, [sign up for Authorize.Net eCheck’s service](https://www.authorize.net/payments/echeck.html). Once eCheck is activated, duplicate the previously configured Authorize.Net payment provider on Odoo by going to Accounting ‣ Configuration ‣ Payment Providers ‣ Authorize.net. Then, click the cog icon (⛭) and select Duplicate. Change the provider’s name to differentiate both versions (e.g., `Authorize.net - Banks`).

When ready, change the provider’s State to Enabled for a regular account or Test Mode for a sandbox account.

## Import an Authorize.Net statement¶

### Export from Authorize.Net¶

Modello

[`Download the Excel import template.`](../../../_downloads/c61874efc4dd43ccc23268a2a42abe08/authorize-net-magic-sheet.xlsx)

  * Log in to Authorize.Net.

  * Go to Account ‣ Statements ‣ eCheck.Net Settlement Statement.

  * Define an export range using an _opening_ and _closing_ batch settlement. All transactions within the two batch settlements will be exported to Odoo.

  * Select all transactions within the desired range, copy them, and paste them into the Report 1 Download sheet of the Excel import template.




Example

In this case, the first batch (01/01/2021) of the year belongs to the settlement of 12/31/2020, so the **opening** settlement is from 12/31/2020.

Once the data is in the Report 1 Download sheet:

  * Go to the Transaction Search tab on Authorize.Net.

  * Under the Settlement Date section, select the previously used range of batch settlement dates in the From: and To: fields and click Search.

  * When the list has been generated, click Download to File.

  * In the pop-up window, select Expanded Fields with CAVV Response/Comma Separated, enable Include Column Headings, and click Submit.

  * Open the text file, select All, copy the data, and paste it into the Report 2 Download sheet of the Excel import template.

  * Transit lines are automatically filled in and updated in the transit for report 1 and transit for report 2 sheets of the Excel import template. Make sure all entries are present, and **if not** , copy the formula from previously filled-in lines of the transit for report 1 or 2 sheets and paste it into the empty lines.




Importante

To get the correct closing balance, **do not remove** any line from the Excel sheets.

### Import into Odoo¶

To import the data into Odoo:

  * Open the Excel import template.

  * Copy the data from the transit for report 2 sheet and use _paste special_ to only paste the values in the Odoo Import to CSV sheet.

  * Look for _blue_ cells in the Odoo Import to CSV sheet. These are chargeback entries without any reference number. As they cannot be imported as such, go to Authorize.Net ‣ Account ‣ Statements ‣ eCheck.Net Settlement Statement.

  * Look for Charge Transaction/Chargeback, and click it.

  * Copy the invoice description, paste it into the Label cell of the Odoo Import to CSV sheet, and add `Chargeback /` before the description.

  * If there are multiple invoices, add a line into the Excel import template for each invoice and copy/paste the description into each respective Label line.




Nota

For **combined chargeback/returns** in the payouts, create a new line in the Excel import template for each invoice.

Example

  * Next, delete _zero transaction_ and _void transaction_ line items, and change the format of the Amount column in the Odoo Import to CSV sheet to _Number_.

  * Go back to eCheck.Net Settlement Statement ‣ Search for a Transaction and search again for the previously used batch settlements dates.

  * Verify that the batch settlement dates on eCheck.Net match the related payments” dates found in the Date column of the Odoo Import to CSV.

  * If it does not match, replace the date with the one from eCheck.Net. Sort the column by _date_ , and make sure the format is `MM/DD/YYYY`.

  * Copy the data - column headings included - from the Odoo Import to CSV sheet, paste it into a new Excel file, and save it using the CSV format.

  * Open the Accounting app, go to Configuration ‣ Journals, tick the Authorize.Net box, and click Favorites ‣ Import records ‣ Load file. Select the CSV file and upload it into Odoo.




Suggerimento

List of [eCheck.Net return codes](https://support.authorize.net/knowledgebase/Knowledgearticle/?code=000001293)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/payment_providers/authorize.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](buckaroo.html "Buckaroo") |
  * [precedente](asiapay.html "AsiaPay") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Online payments](../payment_providers.html) »
  * Authorize.Net


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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer