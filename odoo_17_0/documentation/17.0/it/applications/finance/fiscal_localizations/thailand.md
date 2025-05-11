# Thailandia — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vietnam.html "Vietnam") |
  * [precedente](switzerland.html "Svizzera") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Thailandia



# Thailandia¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the 🇹🇭 Thailand localization package to get all the features of the Thai localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Thailand - Accounting | `l10n_th` | [Pacchetto localizzazione fiscale predefinito](../fiscal_localizations.html#fiscal-localizations-packages)  
Thailand - Accounting Reports | `l10n_th_reports` | Country-specific accounting reports  
  
## Chart of accounts and taxes¶

Odoo’s fiscal localization package for Thailand includes the following taxes:

  * VAT 7%

  * VAT-exempted

  * Imposte alla fonte

  * Withholding income tax




## Resoconto FISCALE¶

Odoo allows users to generate Excel files to submit their VAT to the **Revenue Department** of Thailand.

### Sales and purchase tax report¶

To generate a sales and purchase tax report, go to Accounting ‣ Reporting ‣ Tax Report. Select a specific time or time range on the tax report, and click VAT-202-01 (xlsx) for purchase tax and VAT-202-02 (xlsx) for sales tax.

### Withholding PND tax report¶

PND report data displays the summarized amounts of the applicable **withholding corporate income tax returns (domestic)** from vendor bills under the PND53 (TH) and PND3 (TH) tax reports. It is installed by default with the Thai localization.

Nota

Withholding corporate income tax returns (domestic) is the tax used in case the company has withheld the tax from “**Personal (PND3)** ” or “**Corporate (PND53)** ” services provided such as rental, hiring, transportation, insurance, management fee, consulting, etc.

The PND tax report allows users to generate a CSV file for bills to upload on the [RDprep for Thailand e-Filling application](https://efiling.rd.go.th/rd-cms/).

To generate a PND CSV file, go to Accounting ‣ Reporting ‣ Tax Report, select a specific time or time range on the tax report, and click PND3 or PND53.

This generates the `Tax Report PND3.csv` and `Tax Report PND53.csv` files that lists all the vendor bill lines with the applicable withholding tax.

Avvertimento

Odoo cannot generate the PND or PDF report or **withholding tax certificate** directly. The generated `Tax Report PND3.csv` and `Tax Report PND53.csv` files must be exported to an external tool to convert them into a **withholding PND** report or a **PDF** file.

## Tax invoice¶

The **tax invoice PDF** report can be generated from Odoo through the **Invoicing** module. Users have the option to print PDF reports for normal invoices and tax invoices. To print out **tax invoices** , users can click on Print Invoices in Odoo. Regular invoices can be printed as **commercial invoices** by clicking on Cog button (⚙️) ‣ Print ‣ Commercial Invoice.

### Headquarter/Branch number settings¶

You can inform a company’s **Headquarters** and **Branch number** in the **Contacts** app. Once in the app, open the **contact form** of the company and under the Sales & Purchase tab:

  * If the contact is identified as a branch, input the **Branch number** in the Company ID field.

  * If the contact is a **Headquarters** , leave the Company ID field **blank**.




Suggerimento

This information is used in the **tax invoice** PDF report and PND **tax report** export.

## PromptPay QR code on invoices¶

The **PromptPay QR code** is a QR code that can be added to invoices to allow customers to pay their bills using the PromptPay-supported bank mobile application. The QR code is generated based on the **invoice amount** and one of the following **merchant information** :

  * Ewallet ID

  * Merchant Tax ID

  * Numero di cellulare




### Activate QR codes¶

Go to Accounting ‣ Configuration ‣ Settings. Under the Customer Payments section, activate the QR Codes feature.

### PromptPay QR bank account configuration¶

Go to Contacts ‣ Configuration ‣ Bank Accounts and select the bank account for which you want to activate PromptPay QR. Set the Proxy Type and fill in the Proxy Value field depending on the chosen type.

Importante

  * The account holder’s city is mandatory.

  * The Include Reference checkbox doesn’t work for PromptPay QR codes.




Vedi anche

[Conti bancari e di cassa](../accounting/bank.html)

### Bank journal configuration¶

Go to Accounting ‣ Configuration ‣ Journals, open the bank journal, then fill in the Account Number and Bank under the Journal Entries tab.

### Issue invoices with PromptPay QR code¶

When creating a new invoice, open the Other Info tab and set the Payment QR-code option to EMV Merchant-Presented QR-code.

Ensure that the Recipient Bank is the one you configured, as Odoo uses this field to generate the PromptPay QR code.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/thailand.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vietnam.html "Vietnam") |
  * [precedente](switzerland.html "Svizzera") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Thailandia


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
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*