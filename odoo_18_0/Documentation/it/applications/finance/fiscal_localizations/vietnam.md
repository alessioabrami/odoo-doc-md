# Vietnam — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](employment_hero.html "Libro paga Employment Hero") |
  * [precedente](uruguay.html "Uruguay") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Vietnam



# Vietnam¶

## Moduli¶

The following modules are installed automatically with the Vietnamese localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Vietnam - Accounting | `l10n_vn` | This module includes the default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages).  
Vietnam - E-invoicing | `l10n_vn_edi_viettel` | This module includes the features required for integration with SInvoice.  
  
Nota

In some cases, such as when upgrading to a version with additional modules, it is possible that modules may not be installed automatically. Any missing modules can be manually [installed](../../general/apps_modules.html#general-install).

## Azienda¶

To use all the features of this fiscal localization, the following fields are required on the [company record](../../general/companies.html):

  * Nome

  * Address, including the City, State, Zip Code, and Country.

>     * In the Street field, enter the street name, number, and any additional address information.
> 
>     * In the Street 2 field, enter the neighborhood.

  * Tax ID: tax identification number.




## E-invoicing with SInvoice¶

[SInvoice](https://www.sinvoice.vn/) is an e-invoice service platform provided by Viettel, one of the biggest e-invoice service providers in Vietnam. Odoo supports integration with SInvoice to submit invoices generated in Odoo.

### Configurazione¶

#### SInvoice platform¶

To send electronic invoices to SInvoice, the following must be created on [SInvoice](https://www.sinvoice.vn/):

  * SInvoice account

  * Invoice template

  * Invoice symbol

  * Invoice issuance notice




##### SInvoice registration¶

To create an account, go to [SInvoice](https://www.sinvoice.vn/) and register for the desired plan. Fill in the form that opens to be contacted by [SInvoice](https://www.sinvoice.vn/) to create an account.

Once you have an account, log into [SInvoice](https://www.sinvoice.vn/) using your Username and Password.

##### Invoice template creation¶

  1. On the left side of the overview page, in the Release management menu, click Create business information.

  2. In the Update key information step, fill in the following fields and other optional information if needed: Unit name, Address, Contact person, Type of representative documents.

  3. Click Update.

  4. In the Look up digital certificate step, click Add new to add a digital certificate.

  5. Select the Branch/Enterprise and the Type of digital certificate, then fill in the required fields for each type:

>      * Supplier: CloudCA
> 
>      * Signer ID: CloudCA
> 
>      * Digital Certificate: CloudCA
> 
>      * How to download file: HSM
> 
>      * File Upload: HSM, USB-TOKEN

  6. Click Generate key pair to generate encryption keys for authentication, and Save.

  7. In the Manage invoice templates step, add a new Invoice template.

  8. Select the Invoice type and fill in the Invoice template code, Invoice template name, and other optional information if needed.

  9. Click Update.




Vedi anche

[SInvoice documentation on electronic invoice template creation](https://www.sinvoice.vn/2021/02/hdsd-tai-lieu-nghiep-vu-tao-mau-hoa-don-dien-tu.html?debug=1)

##### Invoice symbol creation¶

On the left side of the main screen, in the Release management menu, click Invoice symbol and follow these steps:

  1. Click Add new and select the Invoice template.

  2. Set the Status to Active to activate the symbol and fill in the Invoice symbol.

  3. Enable Stop automatic sending to tax authorities and Default for built-in API based on preference.

  4. fai clic su Salva.




##### Invoice issuance notice¶

On the left side of the main screen, in the Release management menu, click Create issuance notice and follow these steps:

  1. Click Add new, select the Name of the business unit to issue an e-invoice and the Tax agency name. Based on the business unit and tax agency selected, the Tax code, Address, Phone number, and Separator used are automatically filled and uneditable.

  2. Click Select the invoice type for issuance, and then select and fill in the following information :

     * Invoice type: The invoice type on which to declare an issuance notice.

     * Invoice template: Select from the list of templates available based on the invoice type.

     * Symbol: Select from the list of symbols available based on the invoice type.

     * Quantity: Total number of invoices to issue for the selected type. Based on the type and template selected, this field is filled in automatically. It can be changed if needed.

     * Start date of use: The date from which the invoice template, range, and quantity are used for the issuance notice.

  3. Click Save and select more invoice types if necessary by repeating the steps above. Click Save to finish drafting the notice.

  4. Click Send to tax authorities for approval. Once approved, the notice’s Status is changed to Active.




#### Odoo database¶

##### Link Odoo to SInvoice¶

To connect Odoo with SInvoice, go to Accounting ‣ Configuration ‣ Settings. In the Vietnamese Integration section, fill in your SInvoice Username and Password. Add a Default symbol to generate a prefix for the invoice number managed in SInvoice if needed.

##### Modello fattura¶

To create SInvoice templates, go to Accounting ‣ Configuration ‣ Templates. Click New and add a Template code and a Template Invoice Type. The Template code is the initial sequence of digits in the name assigned by SInvoice. For example, if the invoice template is `1/001 - Hóa đơn GTGT - ND123`, the Template code is `1/001`. The SInvoice templates in Odoo must match the ones in SInvoice.

To add Invoice Symbols, click Add a new line.

### Sending invoices to SInvoice¶

Invoices can be sent to SInvoice once they have been confirmed. To do so, follow the [invoice sending](../accounting/customer_invoices.html#accounting-invoice-sending) steps. In the Send popup, enable Send to SInvoice and click Send & Print.

Once the invoice has been successfully submitted to SInvoice, the SInvoice Status field in the SInvoice tab of the invoice is updated to Sent. The SInvoice Number, Issue Date, Secret Code and eInvoice Number fields are also updated. The same information is available on SInvoice.

#### Replacement or adjustment invoices¶

A replacement invoice is issued to correct an invoice that has **yet to be tax declared** , whereas an adjustment invoice is issued to correct one that has **already been tax declared**. Follow these steps to issue a replacement or adjustment invoice:

  1. Open the invoice and click Credit Note.

  2. In the Credit Note popup, fill in the following fields:

     * Reason displayed on Credit Note

     * Adjustment type

     * Agreement Name

     * Agreement Date

     * Journal

     * Reversal date

  3. Click Reverse and Create Invoice to issue a replacement invoice, or Reverse to issue an adjustment invoice.




The SInvoice Status in the SInvoice invoice tab is updated to Replaced for a replacement invoice or Adjusted for an adjustment invoice.

#### Invoice cancellation¶

If an invoice needs to be canceled, open the invoice and click Request Cancel. In the Invoice Cancellation popup, enter the cancellation Reason, Agreement Name, and Agreement Date, and click Request Cancellation.

The SInvoice Status in the SInvoice invoice tab is updated to Canceled.

## QR banking codes¶

Vietnamese QR banking is a payment service platform that allows customers to make instant domestic payments to individuals and merchants in Vietnamese dong via online and mobile banking.

### Configurazione¶

To activate QR banking codes, go to Accounting ‣ Configuration ‣ Settings and enable QR Codes in the Customer Payments section.

#### Conto bancario¶

To activate QR banking for a bank account, go to Contacts ‣ Configuration ‣ Bank Accounts and select the bank account. Fill in the Bank Identifier Code, Proxy Type (based on the information used to identify the Merchant Account, such as the card number and bank account numbers), and Proxy Value fields.

Enable Include Reference to include the invoice number in the QR code.

Importante

  * The account holder’s country must be set to `Vietnam`, and their city must be specified on the contact form.

  * The [account number](../accounting/bank.html#accounting-bank-account-number) and bank must be set on the Bank journal.




Vedi anche

[Conti bancari e di cassa](../accounting/bank.html)

### Generating QR codes on invoices¶

When creating a new invoice, open the Other Info tab and select EMV Merchant-Presented QR-code in the Payment QR-code field.

Nota

Ensure the Recipient Bank is configured, as Odoo uses this field to generate QR codes.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/vietnam.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](employment_hero.html "Libro paga Employment Hero") |
  * [precedente](uruguay.html "Uruguay") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Vietnam


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
  *[FBM]: Fulfilled by Merchant
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
  *[PAC]: fornitori autorizzati
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
  *[CIS]: Central Invoice System
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