# Tax return (VAT declaration) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_carryover.html "Tax carryover") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Tax return (VAT declaration)



# Tax return (VAT declaration)¶

Companies with a registered VAT number must submit a **tax return** on a monthly or quarterly basis, depending on their turnover and the registration regulation. A tax return - or VAT return - gives the tax authorities information about the taxable transactions made by the company. The **output tax** is charged on the number of goods and services sold by a business, while the **input tax** is the tax added to the price when goods or services are purchased. Based on these values, the company can calculate the tax amount they have to pay or be refunded.

Nota

You can find additional information about VAT and its mechanism on this page from the European Commission: [«What is VAT?»](https://ec.europa.eu/taxation_customs/business/vat/what-is-vat_en).

## Prerequisiti¶

### Periodicità dichiarazione fiscale¶

The configuration of the **Tax Return Periodicity** allows Odoo to compute your tax return correctly and also to send you a reminder to never miss a tax return deadline.

To do so, go to Accounting ‣ Configuration ‣ Settings. Under the Tax Return Periodicity, you can set:

  * Periodicity: define here whether you submit your tax return on a monthly or quarterly basis;

  * Reminder: define when Odoo should remind you to submit your tax return;

  * Journal: select the journal in which to record the tax return.




Nota

This is usually configured during the [app’s initial set up](../get_started.html).

### Griglie imposta¶

Odoo generates tax reports based on the Tax Grids settings that are configured on your taxes. Therefore, it is crucial to make sure that all recorded transactions use the right taxes. You can see the Tax Grids by opening the Journal Items tab of any invoice and bill.

To configure your tax grids, go to Accounting ‣ Configuration ‣ Taxes, and open the tax you want to modify. There, you can edit your tax settings, along with the tax grids that are used to record invoices or refunds.

Nota

Taxes and reports are usually already pre-configured in Odoo: a [fiscal localization package](../../fiscal_localizations.html#fiscal-localizations-packages) is installed according to the country you select at the creation of your database.

## Close a tax period¶

### Tax lock date¶

Any new transaction whose accounting date prior to the Lock Tax Return date has its tax values moved to the next open tax period. This is useful to make sure that no change can be made to a report once its period is closed.

Therefore, we recommend locking your tax date before working on your Closing Journal Entry. This way, other users cannot modify or add transactions that would have an impact on the Closing Journal Entry, which can help you avoid some tax declaration errors.

To check the current Lock Tax Return date, or to edit it, go to Accounting ‣ Accounting ‣ Lock Dates.

### Dichiarazione IVA¶

Once all the transactions involving taxes have been posted for the period you want to report, open the Tax Return report by going to Accounting ‣ Reporting ‣ Tax Return. Select the period you want to declare using the date filter to have an overview of the tax return. Then, click Closing Entry to create a tax closing journal entry. Odoo automatically proposes the details of the journal entry. Make any necessary changes and click Post.

From the report, click PDF to download a PDF of the tax return. Alternatively, click the __( gear) icon, then click Download Excel to download an XLSX of the tax return. To save the report to the Documents app, click the __( gear) icon, then click Copy to Documents. Select the format to Export to, the Documents Name, the Folder to store it in, and add any Tags.

The report includes all the values to report to the tax authorities, along with the amount to be paid or refunded.

Nota

If you forgot to lock your tax date before clicking on Closing Journal Entry, then Odoo automatically locks your fiscal period on the same date as the accounting date of your entry. This safety mechanism can prevent some fiscal errors, but it is advised to lock your tax date manually before, as described above.

Vedi anche

  * [Imposte](../taxes.html)

  * [Per iniziare](../get_started.html)

  * [Fiscal localizations](../../fiscal_localizations.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/reporting/tax_returns.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_carryover.html "Tax carryover") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Tax return (VAT declaration)


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
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
  *[POS]: point of sale
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
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
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