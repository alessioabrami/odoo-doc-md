# Changelog — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../data.html "Data Files") |
  * [precedente](../orm.html "ORM API") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Server framework](../../backend.html) »
  * [ORM API](../orm.html) »
  * Changelog



# Changelog¶

## Odoo version 18.0¶

  * Searching by name is now implemented as `_search_display_name` like all other fields. See [#174967](https://github.com/odoo/odoo/pull/174967).

  * New methods to check access rights and rules now combine both access rights and rules: `check_access`, `has_access` and `_filtered_access`. See [#179148](https://github.com/odoo/odoo/pull/179148).

  * Translations are made available from the `Environment` with [#174844](https://github.com/odoo/odoo/pull/174844).




## Odoo Online version 17.4¶

  * The internal operator `inselect` is removed. The alternative is to use `in` with a Query or SQL object. [#171371](https://github.com/odoo/odoo/pull/171371).




## Odoo Online version 17.3¶

  * We can now group by date parts numbers in `read_group`, `_read_group` and domains with [#159528](https://github.com/odoo/odoo/pull/159528).




## Odoo Online version 17.2¶

  * The `group_operator` attribute of [`Field`](../orm.html#odoo.fields.Field "odoo.fields.Field") is renamed into `aggregator` with [#127353](https://github.com/odoo/odoo/pull/127353).

  * We can now group/aggregate/order by related no-store field with [#127353](https://github.com/odoo/odoo/pull/127353).




## Odoo Online version 17.1¶

  * Method `_flush_search()` has been deprecated with [#144747](https://github.com/odoo/odoo/pull/144747). The flushing of fields is now done by [`execute_query()`](../orm.html#odoo.api.Environment.execute_query "odoo.api.Environment.execute_query"), and is based on metadata put in the [`SQL`](../orm.html#odoo.tools.SQL "odoo.tools.SQL") object by `_search()` and other low-level ORM methods that build such objects. Those methods are also responsible for checking the access rights on the fields that are used in the SQL object.




## Odoo version 17.0¶

  * Introduce an [`SQL`](../orm.html#odoo.tools.SQL "odoo.tools.SQL") wrapper object to make SQL composition easier and safer with respect to SQL injections. Methods of the ORM now use it internally. Introduced by [#134677](https://github.com/odoo/odoo/pull/134677).




## Odoo Online version 16.4¶

  * Method `name_get()` has been deprecated with [#122085](https://github.com/odoo/odoo/pull/122085). Read field `display_name` instead.




## Odoo Online version 16.3¶

  * Method [`_read_group()`](../orm.html#odoo.models.Model._read_group "odoo.models.Model._read_group") has a new signature with [#110737](https://github.com/odoo/odoo/pull/110737)




## Odoo Online version 16.2¶

  * Refactor the implementation of searching and reading methods to be able to combine both in a minimal number of SQL queries. We introduce two new methods [`search_fetch()`](../orm.html#odoo.models.Model.search_fetch "odoo.models.Model.search_fetch") and [`fetch()`](../orm.html#odoo.models.Model.fetch "odoo.models.Model.fetch") that take advantage of the combination. More details can be found on the pull request [#112126](https://github.com/odoo/odoo/pull/112126).




## Odoo version 16.0¶

  * Translations for translated fields are stored as JSONB values with [#97692](https://github.com/odoo/odoo/pull/97692) and [#101115](https://github.com/odoo/odoo/pull/101115). Code translations are no longer stored into the database. They become static and are extracted from the PO files when needed.

  * [`search_count()`](../orm.html#odoo.models.Model.search_count "odoo.models.Model.search_count") takes the `limit` argument into account with [#95589](https://github.com/odoo/odoo/pull/95589). It limits the number of records to count, improving performance when a partial result is acceptable.




## Odoo Online version 15.4¶

  * New API for flushing to the database and invalidating the cache with [#87527](https://github.com/odoo/odoo/pull/87527). New methods have been added to `odoo.models.Model` and `odoo.api.Environment`, and are less confusing about what is actually done in each case. See the section [SQL Execution](../orm.html#reference-orm-sql).




## Odoo Online version 15.3¶

  * The argument `args` is renamed to `domain` for [`search()`](../orm.html#odoo.models.Model.search "odoo.models.Model.search"), [`search_count()`](../orm.html#odoo.models.Model.search_count "odoo.models.Model.search_count") and `_search()`. [#83687](https://github.com/odoo/odoo/pull/83687)

  * [`filtered_domain()`](../orm.html#odoo.models.Model.filtered_domain "odoo.models.Model.filtered_domain") conserves the order of the current recordset. [#83687](https://github.com/odoo/odoo/pull/83687)

  * [`browse()`](../orm.html#odoo.models.Model.browse "odoo.models.Model.browse") does not accept [`str`](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") as `ids`. [#83687](https://github.com/odoo/odoo/pull/83687)

  * The methods `fields_get_keys()` and `get_xml_id()` on [`Model`](../orm.html#odoo.models.Model "odoo.models.Model") are deprecated. [#83687](https://github.com/odoo/odoo/pull/83687)

  * The method `_mapped_cache()` is removed. [#83687](https://github.com/odoo/odoo/pull/83687)

  * Remove the `limit` attribute of [`One2many`](../orm.html#odoo.fields.One2many "odoo.fields.One2many") and [`Many2many`](../orm.html#odoo.fields.Many2many "odoo.fields.Many2many"). [#83687](https://github.com/odoo/odoo/pull/83687)




## Odoo Online version 15.2¶

  * Specific index types on fields: With [#83274](https://github.com/odoo/odoo/pull/83274) and [#83015](https://github.com/odoo/odoo/pull/83015), developers can now define what type of indexes can be used on fields by PostgreSQL. See the [index property](../orm.html#reference-fields) of `odoo.fields.Field`.

  * The `_sequence` attribute of [`Model`](../orm.html#odoo.models.Model "odoo.models.Model") is removed. Odoo lets PostgreSQL use the default sequence of the primary key. [#82727](https://github.com/odoo/odoo/pull/82727)

  * The method `_write()` does not raise an error for non-existing records. [#82727](https://github.com/odoo/odoo/pull/82727)

  * The `column_format` and `deprecated` attributes of [`Field`](../orm.html#odoo.fields.Field "odoo.fields.Field") are removed. [#82727](https://github.com/odoo/odoo/pull/82727)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/backend/orm/changelog.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../data.html "Data Files") |
  * [precedente](../orm.html "ORM API") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Server framework](../../backend.html) »
  * [ORM API](../orm.html) »
  * Changelog


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
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