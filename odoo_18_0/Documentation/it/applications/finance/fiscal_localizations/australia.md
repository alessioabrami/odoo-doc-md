# Australia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](austria.html "Austria") |
  * [precedente](argentina.html "Argentina") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Australia



# Australia¶

## Moduli¶

Nome | Nome tecnico | Descrizione  
---|---|---  
Australia - Accounting | `l10n_au` | The base accounting module for the Australian localization. It is installed automatically when the Australia [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) is selected. This module also installs the ABA Credit Transfer module.  
Australian Reports - Accounting | `l10n_au_reports` | Adds the Taxable Payments Annual Report (TPAR) and the Business Activity Statement (BAS) report. It is installed automatically when the Australia [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) is selected.  
Australia - Payroll | `l10n_au_hr_payroll` | The base [payroll](../../hr/payroll/payroll_localizations/australia.html#payroll-l10n-au-payroll) module for the Australian localization.  
Australia - Payroll with Accounting | `l10n_au_hr_payroll_account` | Contains the necessary accounting data for the Australian payroll rules. It is installed automatically when the [Payroll Entries option](../../hr/payroll.html#payroll-accounting) is enabled.  
Employment Hero Payroll | `l10n_employment_hero` | Synchronizes all pay runs from [Employment Hero](../../hr/payroll/payroll_localizations/australia.html#payroll-l10n-au-employment-hero) with Odoo’s journal entries.  
  
## Contabilità¶

### Taxes and GST¶

In Australia, the standard **Goods and Services Tax (GST)** rate is 10%, but different rates and exemptions exist for specific categories of goods and services.

Nota

The taxes impact the BAS report.

#### Mappatura imposte¶

Within the Australian localization, tax names encompass the tax rate as an integral part of their naming convention. Despite the high number of [taxes](../accounting/taxes.html) configured in Odoo, their rates are often similar (0% or 10%).

##### GST sales taxes¶

The **GST sales** taxes available in Odoo are listed below.

GST name | Descrizione | Etichetta su fatture  
---|---|---  
10% GST | GST Sales | 10% GST  
0% EX | GST Free on Export Sales | 0% GST Free  
0% F | GST Free Sales | 0% Exempt  
0% INP | Input Taxed Sales | 0% Input Taxed Sales  
100% Adj | This is for adjustment, amounts can be modified to fit your needs | Tax Adjustments (Sales)  
  
##### GST purchase taxes¶

The **GST purchase** taxes available in Odoo are listed below.

GST name | Descrizione | Etichetta su fatture  
---|---|---  
10% GST | GST Purchases | 10% GST  
10% C | Capital Purchases | 10% Capital Purchases  
10% INP | Purchases for Input Taxed Sales | 10% Purchases for Input Taxed Sales  
10% PRIV | Purchases for private use or not deductible | 10% Purchases for Private Use  
0% F | GST Free Purchases | 0% GST Free  
0% TPS | Purchase (Taxable Imports) - Tax Paid Separately | 0% GST Paid Separately  
100% ONLY | GST Only on Imports | GST Only on Imports  
100% Adj | Tax Adjustments (Purchases) | Tax Adjustments (Purchases)  
100% DGST | Deferred GST Liability | 100% DGST  
No ABN | Tax Withheld for Partners without ABN | Withholding Tax for No ABN  
PAYGW - W3 | Other amounts withheld (excluding any amount shown at W2 or W4) | Other Amounts Withheld (W3)  
  
###### Varianti¶

Businesses from certain industries need to report payments made to subcontractors from relevant services during the financial year. Odoo combines the use of taxes and fiscal positions to report these payments on the TPAR. In order to be compliant with the TPAR’s obligations, two variants of the main purchase taxes are available in Odoo, but they are inactive by default.

Example

For the _10% GST_ tax, the variants are:

Nome imposta | Descrizione | Reports impacted | Default status  
---|---|---|---  
10% GST | Default 10% GST tax | BAS | Attivo  
10% GST TPAR | TPAR variant of the tax, if the contractor provided an ABN |  BAS TPAR | Non attivo  
10% GST TPAR NO ABN | TPAR variant of the tax, if the contractor did not provide an ABN |  BAS TPAR | Non attivo  
  
#### Deferred GST¶

Odoo allows companies under the [Deferred Goods and Services Tax (DGST) scheme](https://www.ato.gov.au/businesses-and-organisations/gst-excise-and-indirect-taxes/gst/in-detail/rules-for-specific-transactions/international-transactions/deferred-gst?=redirected_deferredGSTscheme) to automate their deferred GST flows.

##### Configurazione¶

It is recommended to:

  * go to Accounting ‣ Configuration ‣ Settings and set the Tax Return Periodicity to monthly (= monthly BAS); and

  * create a new journal to store all deferred GST entries by going to Accounting ‣ Configuration ‣ Journals ‣ New, and selecting Miscellaneous as its Type when configuring it.




By default, a tax (_100% DGST_ , inactive by default) and an account (_21340 Deferred GST Liability_) are available for Australian companies. Activate the tax by going to Accounting ‣ Configuration ‣ Taxes. Search for the Name `100% DGST` (remove the default filter if necessary), and click the Activate toggle switch.

##### Flow¶

###### 1\. Importing goods: purchase order and vendor bill¶

When importing goods from abroad, the GST liability can now be deferred for companies under the DGST scheme. On the purchase order, select the 0% TPS tax (tax paid separately) for the relevant order lines.

###### 2\. Recording the DGST balance on the BAS report¶

When the Australian Taxation Office (ATO) is advised electronically of the aggregated liability for the company by the Integrated Cargo System (ICS), the GST balance deferred during the previous month becomes available on the ATO’s BAS portal.

Importante

Odoo does not yet fetch the DGST balance automatically from the ATO. A manual entry with the liability amount needs to be created in Odoo. We recommend using a new journal for this purpose since deferrals will be recurring.

Go to Accounting ‣ Journal Entries ‣ New. On the first journal item line, add the Account `21340 Deferred GST Liability` and the deferred GST balance as a Credit. To resume the example shown above, we credit $2,000 and save.

An auto-balancing line is created, along with journal items correctly assigning the right values in the BAS Tax Grids. Sections _G11_ , _G18_ , _7A_ , and _ONLY_ are updated correctly.

After posting the journal entry, the BAS report displays the correct values for each section, along with the DGST offset.

### Report¶

#### Business Activity Statement (BAS)¶

The **BAS report** is a critical tax reporting requirement for businesses registered for GST in Australia. The BAS is used to report and remit various taxes to the ATO. With the Odoo BAS feature, businesses can report on the following:

  * GST

  * PAYG tax withheld

  * DGST




Access the report from the Accounting dashboard by clicking BAS Report (AU) under the Miscellaneous Operations section.

The base and tax amounts are collected from the **tax grid** , which is pre-configured in the system. The tax grid can also be manually set up for any additional special use-case of GST (e.g., wine equalization tax). Once the tax for each account is set up, the system automatically slots journal items into the correct tax category. This ensures the BAS report is accurate and reflective of the business’s financial activities.

Besides the GST sections, the BAS report also includes the **PAYG** tax withheld components (_W1_ to _W5_ , then _summary, section 4_). This integration ensures that all payroll-related withholding taxes are accurately captured and reflected within the report.

The module incorporates built-in rules that facilitate the automatic calculation of taxes for types W1 to W5. For a detailed walkthrough and more information on the calculation process for these taxes, refer to the [Payroll section](../../hr/payroll/payroll_localizations/australia.html#payroll-l10n-au-payroll).

##### Chiusura¶

When it is time to file the tax return with the ATO, click Closing Entry. The tax return period can be configured under Accounting ‣ Configuration ‣ Settings ‣ Tax Return Periodicity. The start date of the tax return period can also be defined on the report itself through the period button (___period_ _year_).

Vedi anche

:doc:`Chiusura dell’anno <../contabilità/rendicontazione/fine anno>

Nota

Odoo uses calendar quarters rather than the Australian FY quarters, which means _July to September_ is _Q3_ in Odoo.

Before closing the entry for the first time, the default **GST payable account** and **GST receivable account** need to be set. A notification pops up and redirects the user to the tax groups configuration.

Once the GST payable and GST receivable accounts are set up, the BAS report generates an accurate journal closing entry automatically, which balances out the GST balance with the GST clearing account.

The balance between GST receivable and payable is set against the tax clearing account defined on the tax group. The amount to be paid to or received from the ATO can be reconciled against a bank statement.

Importante

The BAS report is not directly submitted to the ATO. Odoo helps you automatically compute the necessary values in each section, with the possibility to audit them to better understand the history behind these numbers. Businesses can copy these values and enter them on the [ATO portal](https://www.ato.gov.au/businesses-and-organisations/preparing-lodging-and-paying/business-activity-statements-bas/how-to-lodge-your-bas).

#### Taxable Payments Annual Report (TPAR)¶

Odoo allows businesses to report payments made to contractors or subcontractors during the financial year. This is done by generating a **TPAR**. If you are unsure your business needs this report, refer to the [ATO’s TPAR web page](https://www.ato.gov.au/businesses-and-organisations/preparing-lodging-and-paying/reports-and-returns/taxable-payments-annual-report).

Access the TPAR in Odoo by going to Accounting ‣ Reporting ‣ Taxable Payments Annual Reports (TPAR).

##### Configurazione¶

First, it is required to assign fiscal positions to your contractors before billing them to update the TPAR. To do so, go to Accounting ‣ Vendors ‣ Vendors, select a contractor, and set a Fiscal Position under the Sales & Purchase tab.

Based on the chosen fiscal position, the correct tax mapping will apply to the contractor’s vendor bills.

The TPAR includes the following information from contractors:

  * ABN

  * Total GST (the total tax paid)

  * Gross Paid (the amounts are displayed after a vendor bill has been marked as paid)

  * Tax Withheld (displayed if the contractor is registered with a fiscal position set to TPAR without ABN)




The TPAR can be exported to multiple formats: PDF, XLSX, and TPAR.

### Remittance advice¶

A remittance advice is a document used as proof of payment to a business. In Odoo, it can be accessed by going to Accounting ‣ Vendors ‣ Payments, selecting the payment(s), and clicking Print ‣ Payment Receipt.

### Fatturazione elettronica¶

#### Peppol¶

Odoo is compliant with Australia’s [Peppol requirements](https://peppol.org/learn-more/country-profiles/australia/). Set up your customers and vendors by going to Accounting ‣ Customers ‣ Customers or Vendors ‣ Vendors, selecting one, clicking the Accounting tab, and configuring the Electronic Invoicing section as needed.

Importante

Validating an invoice or credit note for a partner on the Peppol network will download a compliant XML file that can be manually uploaded to your Peppol network. Odoo is currently in the process of becoming an access point for the ANZ region.

### ABA files for batch payments¶

An ABA file is a digital format developed by the [Australian Banking Association](https://www.ausbanking.org.au/). It is designed for business customers to facilitate bulk payment processing by uploading a single file from their business management software.

The main advantage of using ABA files is to improve payment and matching efficiency. This is achieved by consolidating numerous payments into one file for batch processing, which can be submitted to all Australian banks.

#### Configurazione¶

##### Pagamenti raggruppati¶

Go to Accounting ‣ Configuration ‣ Settings and enable Batch Payments.

##### Bank journal¶

Go to Accounting ‣ Configuration ‣ Journals and select the Bank journal. Enter the Account Number, click Create and edit…, and fill in the following fields:

  * Bank

  * BSB

  * Account Holder




Then, toggle on the Send Money switch and click Save & Close.

Nota

Using the Currency field is optional.

Back on the Journal Entries tab, fill in the following fields under the ABA section:

  * BSB: the BSB code from the bank account is used to fill in this field.

  * Financial Institution Code: the official 3-letter abbreviation of the bank (e.g., `WBC` for Westpac)

  * Supplying User Name: 6-digit number provided by the bank. Contact your bank or check its website if you do not know it.

  * APCA Identification Number: 6-digit number provided by the bank. Contact your bank or check its website if you do not know it.

  * Include Self Balancing Transaction: selecting this option adds an additional
    

«self-balancing» transaction to the end of the ABA file, which is required by some banks.




##### Customers” and vendors” bank accounts¶

Go to Accounting ‣ Customers ‣ Customers or Accounting ‣ Vendors ‣ Vendors and select a customer or vendor. Open the Accounting tab, and, under the Bank Accounts section, click Add a line to fill in their:

  * Account Number

  * Bank

  * BSB

  * Account Holder




Then, toggle on the Send Money switch and click Save & Close.

#### Generating an ABA file¶

To generate an ABA file, create a vendor bill, confirm it, and ensure the vendor’s banking information is set up correctly.

Next, click Pay on the vendor bill, and select, for the following fields:

  * Journal: Bank

  * Payment Method: ABA Credit Transfer

  * Recipient Bank Account: the vendor’s account number




Once payments are created, go to Accounting ‣ Vendors ‣ Payments, select the payments to be included in the batch, and click Create Batch. Verify all information is correct and click Validate. Once validated, the ABA file is available in the **chatter** on the right.

After uploading the file to your bank’s portal, an ABA transaction line will appear in your bank feed at the following bank feed iteration. You will need to reconcile it against the **batch payment** made in Odoo.

## Industry-specific features¶

### Starshipit shipping¶

Starshipit is a shipping service operator that facilitates the integration of Australasian shipping couriers with Odoo. Refer to the [Starshipit documentation](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/starshipit_shipping.html) for detailed information.

Vedi anche

[Starshipit Odoo webinar recording](https://www.youtube.com/watch?v=TcDWnoYLXWg)

### Buy Now, Pay Later solutions¶

_Buy Now, Pay Later_ solutions are popular payment methods for eShops in Australia. Some of these solutions are available via [Stripe](https://stripe.com/en-au/payments/payment-methods) and [AsiaPay](https://www.asiapay.com.au/payment.html#option).

Vedi anche

  * [Stripe payment provider](../payment_providers/stripe.html)

  * [AsiaPay payment provider](../payment_providers/asiapay.html)




### POS terminals¶

To establish a direct connection between Odoo and a POS terminal in Australia, a **Stripe** payment terminal is required. Odoo supports the **EFTPOS** payment solution in Australia.

Nota

A Stripe payment terminal is not required to use Odoo as the main POS system. However, without one, cashiers must manually enter the final payment amount on the terminal.

Vedi anche

  * [Stripe payment provider](../payment_providers/stripe.html)

  * [Stripe payment terminal](../../sales/point_of_sale/payment_methods/terminals/stripe.html)

  * [Stripe.com terminal documentation](https://stripe.com/docs/terminal)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/australia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](austria.html "Austria") |
  * [precedente](argentina.html "Argentina") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Australia


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
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation