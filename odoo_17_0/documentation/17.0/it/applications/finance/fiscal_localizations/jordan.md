# Giordania — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kenya.html "Kenya") |
  * [precedente](italy.html "Italia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Giordania



# Giordania¶

## Moduli¶

The following modules are installed automatically with the Jordanian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Jordan - Accounting | `l10n_jo` | Jordanian [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages), complete with the Jordanian chart of accounts, taxes, tax report, and fiscal positions  
Jordan E-Invoicing | `l10n_jo_edi` | Integration module for JoFotara to support Jordanian e-invoicing requirements  
  
Nota

In some cases, such as when upgrading to a version with additional modules, it is possible that modules may not be installed automatically. Any missing modules can be manually [installed](../../general/apps_modules.html#general-install).

## Localization overview¶

The Jordanian localization package ensures compliance with Jordanian fiscal and accounting regulations. It includes tools for managing taxes, fiscal positions, reporting, and a predefined chart of accounts tailored to Jordan’s standards.

The Jordanian localization package provides the following key features to ensure compliance with local fiscal and accounting regulations:

  * [Piano dei conti](../accounting/get_started/chart_of_accounts.html): a predefined structure tailored to Jordanian accounting standards

  * Imposte: pre-configured tax rates, including standard VAT, zero-rated, and exempt options

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../accounting/taxes/fiscal_positions.html): automated tax adjustments based on customer or supplier registration status

  * Tax reporting: detailed overview of your net tax liability

  * E-invoicing (JoFotara): integration for electronic invoicing in line with Jordanian government requirements




### Imposte¶

The following [taxes](../accounting/taxes.html) are available by default with the Jordanian localization package:

  * standard sales tax (16%): applied to most goods and services within Jordan.

  * exempt transactions: for sales and services not subject to VAT, such as financial services or healthcare.

  * export tax (0%): zero-rated tax applied to goods and services exported outside Jordan.




### Tax reporting¶

The [VAT summary](../accounting/reporting/tax_returns.html) provides a detailed breakdown of taxable, zero-rated, and exempt transactions. Like other [financial reports](../accounting/reporting.html), the VAT summary can be filtered by period, compared against other periods, and exported in Excel and PDF formats, ensuring compliance with Jordanian tax laws.

## E-invoicing with JoFotara¶

E-invoicing with JoFotara is integrated with Odoo, ensuring compliance with Jordanian government’s technical and legal requirements for electronic invoicing. The JoFotara integration in Odoo directly connects with the Jordanian e-invoicing platform, allowing companies to:

  * generate compliant electronic invoices

  * submit invoices in real time for validation

  * track invoice statuses directly within Odoo




The integration requires first creating an account with JoFotara, then generating API credentials, and finally entering those credentials in your Odoo database to link the two.

[Government manuals](https://istd.gov.jo/EN/List/Electronic_billing_User_Manual) provide instructions for creating an account and generating the API credentials.

### Configurazione¶

#### Link Odoo to JoFotara¶

  1. If you don’t already have an account, create one by going to the [government manuals](https://istd.gov.jo/EN/List/Electronic_billing_User_Manual) page and following the steps in the **Procedure Manual for Joining the Jordanian National Electronic Invoicing System**.

  2. Generate API credentials (Activity Number, Secret Key, and Client ID) by going to the [government manuals](https://istd.gov.jo/EN/List/Electronic_billing_User_Manual) page and following the steps in **Procedure Manual for Linking to the Jordanian National Electronic Invoicing System**.

  3. In your Odoo database, go to Accounting ‣ Configuration ‣ Settings. In the Electronic Invoicing (Jordan) section, enter the API credentials generated previously:

     * Activity Number (income source sequence)

     * JoFotara Secret Key

     * JoFotara Client ID

  4. Enter the Taxpayer type:

     * Unregistered in the sales tax: for businesses not registered for sales tax. No tax on the invoice line is required.

     * Registered in the sales tax: for businesses registered under the standard sales tax system. One tax computed as a percentage is required per invoice line.

     * Registered in the special sales tax: for businesses subject to special sales tax regulations. One tax computed as a percentage and one fixed tax per invoice line are required per invoice.

  5. fai clic su Salva.




Suggerimento

If the Electronic Invoicing (Jordan) section is missing from the Settings, make sure the Jordan E-Invoicing module is [installed](../../general/apps_modules.html#general-install).

#### Company and customers¶

The JoFotara invoicing workflow requires address information related to the company that sends the invoices and the customers who receive them:

  1. Go to Settings ‣ Users & Companies ‣ Companies and select the company that will use JoFotara.

  2. Fill in the Company Name, Tax ID (TIN), and Country. If desired, fill in additional optional fields such as Street, City, State, and ZIP.

Importante

     * The Country must be set to Jordan.

     * The Company Name must match the name that is registered with the Income and Sales Tax Department (ISTD).

     * The company’s Currency must be set to JOD.

  3. Go to Accounting ‣ Customers ‣ Customers.

  4. For each customer whose invoices will be sent to JoFotara, click on the customer to open the form view, and complete the Country and Tax ID. If desired, fill in additional optional fields such as Street, City, State, and ZIP.




### Sending invoices to JoFotara via Odoo¶

Once the company has been linked with JoFotara and the company and customers have been properly configured, invoices can be sent to JoFotara via Odoo:

  1. Go to Accounting ‣ Customers ‣ Invoices and open a confirmed (posted) invoice.

  2. Click Send & Print.

  3. In the Send window, select Send JoFotara e-invoice and click Send & Print.




When an invoice is sent to JoFotara, Odoo does the following:

  * generates the invoice in the required format (UBL 1.2)

  * submits the invoice to JoFotara for validation

  * receives the QR code from JoFotara on the invoice’s PDF




Suggerimento

  * Multiple invoices can be [sent at once](../accounting/customer_invoices.html#accounting-invoice-sending) to JoFotara.

  * From the Invoices list view, filter the invoices by their JoFotara State to see the invoices that have either been sent or not been sent to JoFotara.

  * In the __( adjust settings) menu, add the JoFotara State and JoFotara Error fields to see the sending state and any errors in the list view, respectively.




Importante

There is an inherent difference in how values are approximated in Odoo and ISTD due to the differing system architectures. JOD values in Odoo are stored and approximated to three decimals, whereas ISTD expects values to have nine decimals. As a result, an insignificant difference is inevitable and arises between the values stores in Odoo and the values reported to ISTD, which can have an error margin of <0.01.

#### JoFotara State¶

The JoFotara State field in the Other Info tab of confirmed invoices reflects the current state of the document in JoFotara. It can be changed manually to reflect the actual state of the invoices in cases where a technical error or timeout prevents Odoo from updating it automatically.

#### Validating QR codes (Sanad app)¶

To validate the QR code received from JoFotara on the invoice, follow these steps:

  1. Install the [Sanad app](https://www.sanad.gov.jo/Default/en).

  2. Navigate to More.

  3. Click on Validate document and scan the QR code.

  4. Review results.




#### Debit and credit notes¶

To send a debit or credit note to JoFotara, first create the [debit](../accounting/customer_invoices/credit_notes.html#accounting-credit-notes-issue-debit-note) or [credit note](../accounting/customer_invoices/credit_notes.html#accounting-credit-notes-issue-credit-note). In the Print and Send window, click Send via JoFotara to submit it for real-time validation. Upon successful validation, the QR code from JoFotara is embedded in the debit or credit note PDF.

Nota

Ensure that the Reason for generating a debit/credit note aligns with ISTD regulations.

#### Sconti¶

JoFotara does not support negative quantities or negative prices on invoice lines. As a result, global discount and fixed amount discount functionality are not supported.

Discounts must be applied **per invoice line as a percentage** instead of as a global discount or fixed amount.

Avvertimento

Attempting to submit invoices to JoFotara with negative invoice lines will result in validation errors.

Vedi anche

[Discount types](../../sales/sales/products_prices/prices/pricing.html#sales-pricing-discount-button)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/jordan.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kenya.html "Kenya") |
  * [precedente](italy.html "Italia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Giordania


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Interchange
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
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[OTP]: one-time password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: Chart of Accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: Automated Clearing House
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales