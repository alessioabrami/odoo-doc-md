# Indonesia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](italy.html "Italia") |
  * [precedente](india.html "India") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Indonesia



# Indonesia¶

## E-Faktur Module¶

The **E-Faktur Module** is installed by default with the Indonesian localization module. It allows one to generate a CSV file for one tax invoice or for a batch of tax invoices to upload to the **Tax Office e-Faktur** application.

### NPWP/NIK settings¶

  * **Your Company**

This information is used in the FAPR line in the effect file format. You need to set a VAT number on the related partner of your Odoo company. If you don’t, it won’t be possible to create an e-Faktur from an invoice.

  * **Your Clients**

You need to set the checkbox _ID PKP_ to generate e-fakturs for a customer. You can use the VAT field on the customer’s contact to set the NPWP needed to generate the e-Faktur file. If your customer does not have an NPWP, just enter the NIK in the same VAT field.




### Utilizzo¶

#### Generate Tax Invoice Serial Number¶

  1. Go to Accounting ‣ Customers ‣ e-Faktur. In order to be able to export customer invoices as e-Faktur for the Indonesian government, you need to put here the ranges of numbers you were assigned by the government. When you validate an invoice, a number will be assigned based on these ranges. Afterwards, you can filter the invoices still to export in the invoices list and click on _Action_ , then on _Download e-Faktur_.

  2. After receiving new serial numbers from the Indonesian Revenue Department, you can create a set of tax invoice serial numbers group through this list view. You only have to specify the Min and Max of each serial numbers” group and Odoo will format the number automatically to a 13-digits number, as requested by the Indonesia Tax Revenue Department.

  3. There is a counter to inform you how many unused numbers are left in that group.




#### Generate e-faktur csv for a single invoice or a batch invoices¶

  1. Create an invoice from Accounting ‣ Customers ‣ Invoices. If the invoice customer’s country is Indonesia and the customer is set as _ID PKP_ , Odoo will allow you to create an e-Faktur.

  2. Set a Kode Transaksi for the e-Faktur. There are constraints related to the Kode transaksi and the type of VAT applied to invoice lines.

  3. Odoo will automatically pick the next available serial number from the e-Faktur number table (see the section above) and generate the e-faktur number as a concatenation of Kode Transaksi and serial number. You can see this from the invoice form view under the page _Extra Info_ in the box _Electronic Tax_.

  4. Once the invoice is posted, you can generate and download the e-Faktur from the _Action_ menu item _Download e-faktur_. The checkbox _CSV created_ will be set.

  5. You can select multiple invoices in list view and generate a batch e-Faktur .csv.




#### Kode Transaksi FP (Transaction Code)¶

The following codes are available when generating an e-Faktur. \- 01 Kepada Pihak yang Bukan Pemungut PPN (Customer Biasa) \- 02 Kepada Pemungut Bendaharawan (Dinas Kepemerintahan) \- 03 Kepada Pemungut Selain Bendaharawan (BUMN) \- 04 DPP Nilai Lain (PPN 1%) \- 06 Penyerahan Lainnya (Turis Asing) \- 07 Penyerahan yang PPN-nya Tidak Dipungut (Kawasan Ekonomi Khusus/ Batam) \- 08 Penyerahan yang PPN-nya Dibebaskan (Impor Barang Tertentu) \- 09 Penyerahan Aktiva (Pasal 16D UU PPN)

#### Correct an invoice that has been posted and downloaded: Replace Invoice feature¶

  1. Cancel the original wrong invoice in Odoo. For instance, we will change the Kode Transakski from 01 to 03 for the INV/2020/0001.

  2. Create a new invoice and set the cancelled invoice in the _Replace Invoice_ field. In this field, we can only select invoices in _Cancel_ state from the same customer.

  3. As you validate, Odoo will automatically use the same e-Faktur serial number as the cancelled and replaced invoice replacing the third digit of the original serial number with _1_ (as requested to upload a replacement invoice in the e-Faktur app).




#### Correct an invoice that has been posted but not downloaded yet: Reset e-Faktur¶

  1. Reset the invoice to draft and cancel it.

  2. Click on the button _Reset e-Faktur_ on the invoice form view.

  3. The serial number will be unassigned, and we will be able to reset the invoice to draft, edit it and re-assign a new serial number.




## QRIS QR code on invoices¶

[QRIS](https://qris.online/homepage/) is a digital payment system that allows customers to make payments by scanning the QR code from their preferred e-wallet.

Importante

According to the [QRIS API documentation](https://qris.online/api-doc/create-invoice.php), QRIS expires after 30 minutes. Due to this restriction, the QR code is not included in reports sent to customers and is only available on the customer portal.

### Activate QR codes¶

Go to Accounting ‣ Configuration ‣ Settings. Under the Customer Payments section, activate the QR Codes feature.

### QRIS bank account configuration¶

Go to Contacts ‣ Configuration ‣ Bank Accounts and select the bank account for which you want to activate QRIS. Set the QRIS API Key and QRIS Merchant ID based on the information provided by QRIS.

Importante

The account holder’s country must be set to `Indonesia` on its contact form.

Vedi anche

[Conti bancari e di cassa](../accounting/bank.html)

### Bank journal configuration¶

Go to Accounting ‣ Configuration ‣ Journals, open the bank journal, then fill out the Account Number and Bank under the Journal Entries tab.

### Issue invoices with QRIS QR codes¶

When creating a new invoice, open the Other Info tab and set the Payment QR-code option to `QRIS`.

Ensure that the Recipient Bank is the one you configured, as Odoo uses this field to generate the QRIS QR code.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/indonesia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](italy.html "Italia") |
  * [precedente](india.html "India") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Indonesia


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