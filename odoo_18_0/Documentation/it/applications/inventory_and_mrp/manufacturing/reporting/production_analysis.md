# Production analysis — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../purchase.html "Acquisti") |
  * [precedente](oee.html "Overall equipment effectiveness") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Rendiconto](../reporting.html) »
  * Production analysis



# Production analysis¶

The _Production Analysis_ report provides statistics about products manufactured using Odoo’s _Manufacturing_ app. The report is useful when trying to understand production costs, manufacturing durations, and other important statistics about manufactured products.

To open the Production Analysis report, navigate to Manufacturing app ‣ Reporting ‣ Production Analysis.

Importante

The Production Analysis report is one of many reports available across the Odoo app suite. This documentation only covers the measures specific to the Production Analysis report, along with a few use case examples.

For a full overview of the basic features available in most Odoo reports, see the documentation on [reporting essentials](../../../essentials/reporting.html).

## Misure¶

_Measures_ are the datasets that can be selected in the Production Analysis report. Each dataset represents a specific statistic about MOs in the database. Choose a measure by clicking the Measures __button, and selecting one of the options from the drop-down menu:

The options displayed in the Measures __drop-down menu, and the order they appear in, differ depending on the filters, groupings, and comparisons enabled in the Search… bar. By default, the available measures appear as follows:

  * Average Employee Cost/Unit: the average cost paid to employees to produce one unit of the product.

  * By-Products Total Cost: the total value of all by-products created by manufacturing the product.

  * Component Cost/Unit: the average cost of the components required to produce one unit of the product.

  * Cost/Unit: the average cost of producing one unit of the product, including component, employee, operation, and subcontracting costs.

  * Duration of Operations/Unit: the average total duration of operations required to produce one unit of the product.

  * Quantity Demanded: the total number of units of the product included in MOs.

  * Quantity Produced: the total number of units of the product that have actually been produced.

  * Total Component Cost: the total amount spent on the product’s components, across every MO for the product.

  * Total Cost: the total amount spent manufacturing every unit of the product produced so far.

  * Total Duration of Operations: the cumulative duration of every operation completed while manufacturing the product.

  * Total Employee Cost: the cumulative amount paid to employees to manufacture the product.

  * Total Operation Cost: the cumulative amount spent on operations required to produce the product.

  * Total Operation Cost/Unit: the average cost of the operations required to produce one unit of the product.

  * Total Subcontracting Cost: the cumulative amount paid to subcontractors to produce the product.

  * Total Subcontracting Cost/Unit: the average cost of engaging a subcontractor to produce one unit of the product.

  * Yield Percentage (%): the total quantity of the product produced versus the total quantity demanded, represented as a percentage.

  * Count: the total count of MOs created for the product.




Suggerimento

Only one measure can be selected at a time when one of the __(graph view) options is enabled. However, multiple measures, and varying group-by criteria (on the x and y axes), can be selected when using the __(pivot table).

## Use case: compare products¶

One of the best uses for the Production Analysis report is comparing statistics about two or more products. This is accomplished by entering the products into the Search… bar, then selecting the necessary measure, filter, and grouping, to see the desired data.

Example

Toy manufacturer _Tommy’s Toys_ is trying to reduce their manufacturing operation costs. To accomplish this, they have decided to identify redundant products and cease manufacturing the ones with higher operational costs.

Two of the toys that have been singled out for analysis are the _pogo stick_ and _moon shoes_. Tommy’s Toys believes these two toys are so similar that they can stop manufacturing one, without significantly impacting their product offering.

To compare operation costs for the toys, business analyst Mike opens the Manufacturing app, and navigates to the Production Analysis page. In the Search… bar, he enters the names of both products. Then, he opens the Search… bar drop-down menu, and clicks Product in the Group By section.

Below the Search… bar, Mike clicks on the Measures __drop-down menu, and selects the Total Operation Cost/Unit option. Finally, he selects the __(bar chart) graph type.

With these options selected, the Production Analysis report shows a bar chart for the current year, with one bar for each product, signifying the average operation cost for one unit of the product.

With this data, Mike is able to see that the average operation cost for the moon shoes is almost twice the cost of the pogo stick. Using this insight, Tommy’s Toys decides to cease production of moon shoes, thus lowering their average cost of manufacturing operations.

## Use case: compare time periods¶

The Production Analysis report can also be used to compare data for two different time periods. This is accomplished using the options in the Comparison section of the Search… bar.

Example

Furniture company _Fanny’s Furnishings_ wants to compare their production costs for the first and second quarters of 2024, to see which products they spent the most money producing in each quarter.

To compare the two time periods, shop floor supervisor Adam opens the Manufacturing app, and navigates to the Production Analysis page. He begins by selecting the __(pie chart) graph type option at the top of the page.

Importante

The Comparison feature is meant to be used with the __(pie chart) graph type, or the __(pivot) view.

A Comparison option can still be selected with the other view types enabled, but doing so does not change the way data is displayed on the report.

Next, Adam selects the Total Cost option from the Measures __drop-down menu. This option displays the total amount spent producing each product.

In the Search… bar drop-down menu, he leaves the 2024 filter enabled in the End Date section, and enables the Q2 filter as well. With both of these time periods selected, the pie chart shows data for the second quarter of 2024.

Finally, Adam selects the End Date: Previous Period option in the Comparison section of the Search… bar. Doing so causes the pie chart to be split into an inner circle, and an outer ring.

The outer ring shows data for the selected time period, quarter two of 2024. The inner circle shows data for the previous time period, quarter one of 2024.

Nota

If End Date: Previous Year is selected instead of End Date: Previous Period, the inner circle shows data for the selected time period, one _year_ previous.

In the case of this example, it would show data for quarter two of 2023.

Using this report, Adam can see that the products with the highest total cost for quarter two are the _bicycle_ and _tricycle_. On the other hand, in quarter one, the _roller skates_ had the highest total cost.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/reporting/production_analysis.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../purchase.html "Acquisti") |
  * [precedente](oee.html "Overall equipment effectiveness") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Rendiconto](../reporting.html) »
  * Production analysis


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
  *[MO]: manufacturing order
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
  *[API]: Application programming interface
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
  *[SOs]: sales orders
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
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: manufacturing orders
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
  *[CIS]: Construction Industry Scheme
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
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs