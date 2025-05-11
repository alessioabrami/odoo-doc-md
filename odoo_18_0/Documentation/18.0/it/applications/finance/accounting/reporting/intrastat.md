# Intrastat — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](data_inalterability.html "Data inalterability check report") |
  * [precedente](budget.html "Budget") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Intrastat



# Intrastat¶

Intrastat is the data collection and statistics production system for goods traded among EU member states. It collects data on:

  * Commercial transactions of goods for use, consumption, investment, or resale with ownership transfer;

  * Goods movements without transfer of ownership (e.g., stock relocations or moves of goods before or after outsourced production or processing, and after maintenance or repair);

  * Returns of goods.




Nota

Although the Intrastat system continues to be used, the term Intrastat is not used in the [latest legislation](http://data.europa.eu/eli/reg/2019/2152/2022-01-01), referring instead to _intra-Union trade in goods statistics_.

Vedi anche

[Eurostat Statistics Explained - Glossary: Intrastat](https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Intrastat)

## General configuration¶

Enable the Intrastat report by going to Accounting ‣ Configuration ‣ Settings. Under the Customer Invoices section, tick Intrastat and then Save.

### Default transaction codes: invoice and refund¶

You can set a default transaction code for all newly created invoice and refund transactions. Under Accounting ‣ Configuration ‣ Settings, select a Default invoice transaction code and/or a Default refund transaction code and then Save. The code will be set automatically on all respective invoice lines.

### Region code¶

The region code is **only used by Belgian companies**. Under Accounting ‣ Configuration ‣ Settings, select the Company Intrastat Region where the company is located and then Save.

Suggerimento

If your warehouses are located in more than one region, you can define the region code at the level of each warehouse instead. To do so, go to Inventory ‣ Configuration ‣ Warehouses, select a warehouse, set its Intrastat region, and then Save.

## Configurazione prodotto¶

All products must be properly configured to be included in the Intrastat report.

### Codice merce¶

Commodity codes are internationally recognized reference numbers used to classify goods depending on their **nature**. Intrastat uses the [Combined Nomenclature](https://taxation-customs.ec.europa.eu/customs-4/calculation-customs-duties/customs-tariff/combined-nomenclature_en).

To add a commodity code, go to Accounting ‣ Customers ‣ Products and select a product. Under the Accounting tab, set the product’s Commodity Code.

Vedi anche

[National Bank of Belgium - Intrastat commodity codes](https://www.nbb.be/en/statistics/foreign-trade/nomenclature-and-codes)

### Quantity: weight and supplementary unit¶

Depending on the nature of the goods, it is necessary to specify either the product’s weight in kilos (without packaging) or the product’s supplementary unit, such as square meter (`m2`), number of items (`p/st`), liter (`l`), or gram (`g`).

To add a product’s weight or supplementary unit, go to Accounting ‣ Customers ‣ Products and select a product. Under the Accounting tab, depending on the commodity code set, either fill in the product Weight or its Supplementary Units.

### Country of origin¶

To add the product’s country of origin, go to Accounting ‣ Customers ‣ Products and select a product. Under the Accounting tab, set the Country of Origin.

## Invoices and bills configuration¶

Once products are properly configured, several settings must be configured on the invoices and bills you create.

### Transaction code¶

Transaction codes are used to identify a transaction’s nature. Default transaction codes can be set for invoice and refund transactions.

To set a transaction code on an invoice line, create an invoice or a bill, click the columns selection button, tick Intrastat, and use the newly-added Intrastat column to select a transaction code.

Vedi anche

[National Bank of Belgium - Intrastat: Nature of transactions from January 2022](https://www.nbb.be/doc/dd/onegate/data/new_natures_of_transaction_2022_en.pdf)

### Partner country¶

The partner country represents the vendor’s country for bills and the customer’s country for invoices. It is automatically filled in using the country set in the contact’s Country field.

To edit the partner country manually, create an invoice or a bill, click the Other Info tab, and select the Intrastat Country.

### Transport code¶

The transport code identifies the presumed **mode of transport** used to send the goods (arrival or dispatch).

To add the transport code, create an invoice or a bill, go to the Other info tab, and select the Intrastat Transport Mode.

### Value of the goods¶

The value of a good is the untaxed Subtotal (Price multiplied by Quantity) of an invoice line.

## Partner configuration¶

Two fields from the partner’s contact form are used with Intrastat: VAT and Country. The country can be manually set on the invoice or bill.

## Generate the Intrastat report¶

Generate the report by going to Accounting ‣ Reporting ‣ Audit Reports: Intrastat Report. It is automatically computed based on the default configuration and the information found on the products, invoices and bills, and partners.

Export the report as a PDF, XLSX, or XML file to post it to your legal administration.

Each report line refers to a single invoice line and contains the following information:

  * Invoice or bill reference number;

  * System, which is a code automatically generated depending on whether the document is an invoice (dispatch) or a bill (arrival);

  * Country, which is the vendor’s country for arrivals and the customer’s country for dispatches;

  * Transaction Code;

  * (If your company is located in Belgium) Region Code;

  * Commodity Code;

  * Origin Country;

  * Partner VAT;

  * Transport Code;

  * [Incoterm Code](../customer_invoices/incoterms.html);

  * Weight;

  * Supplementary Units; and

  * Value, which is always expressed in euros even if the original invoice or bill used another currency.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/reporting/intrastat.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](data_inalterability.html "Data inalterability check report") |
  * [precedente](budget.html "Budget") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Intrastat


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