# Import vendor pricelist — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reordering.html "Configure reordering rules") |
  * [precedente](../products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Import vendor pricelist



# Import vendor pricelist¶

Set vendor prices to auto-populate requests for quotations (RFQs) or purchase orders (POs) with the unit price, once the product is added, which reduces errors and saves time.

In Odoo, vendor pricelists can be added individually on the product form, or imported in bulk, via an XLSX or CSV file.

Importante

Please review this [import guide](../../../essentials/export_import_data.html) before uploading vendor pricelists.

## On product form¶

To manually add the vendor price on the product form, go to the Purchase app ‣ Products ‣ Products, and click the desired product.

Nota

Product forms are accessible from multiple apps, such as **Sales** , **Inventory** , and **Manufacturing**.

In the Purchase tab of the product form, input the vendor and their price, to have this information auto-populate on a request for quotation each time the product is listed.

Vedi anche

[Vendor pricelist on product form](../manage_deals/rfq.html#purchase-manage-deals-vendor-pricelist)

## Import vendor pricelist¶

To import vendor pricelists, ensure the XLSX or CSV file is accurately completed. The best way to obtain a correctly formatted template, including product names, references, and vendor details, is to first export a pricelist from the database.

Modify the exported file, as needed, then import it back into the Odoo database.

### Export pricelist¶

To export a pricelist, go to Purchase app ‣ Configuration ‣ Vendor Pricelists.

On the page, tick the checkbox(es) for the desired vendor pricelists.

Then, click the __ Actions button that appears, and choose __ Export from the drop-down menu.

In the resulting pop-up window, fields listed under the Fields to export section are included in the exported file. To add more fields, find the desired field in the Available fields section, and click the __(plus) icon to the right of the field.

Nota

To update to existing records, tick the I want to update data (import-compatible export) checkbox, and refer to the section on the External ID field.

For details on commonly-used fields for importing vendor pricelists, see the Common fields section.

Select the desired Export Format: XLSX or CSV.

To save the selected fields as a template, click the Template field, and select New template from the drop-down menu. Type the name of the new template, and click the __(save) icon. After that, the template is a selectable option when clicking the Template field.

Finally, click Export.

Nota

With [developer mode](../../../general/developer_mode.html#developer-mode) turned on, the column names of the exported file display the _field name_ with the _technical name_ in parenthesis.

Example

Export vendor pricelist in XLSX format. It includes Product Template and other fields in the Fields to export section.¶

#### ID esterno¶

_External ID_ is a unique identifier used to update existing vendor pricelists. Without it, imported records create new entries, instead of updating existing ones. Including this field in the XLSX or CSV, indicates the line replaces an existing vendor pricelist in the Odoo database.

Example

`Ready Mat` appears twice because the external ID was omitted during the price update from `$790` to `$780`.¶

To look-up the External ID for a vendor pricelist, tick the I want to update data (import-compatible export) checkbox at the top of the Export Data pop-up window.

Nota

Selecting External ID from the Available fields section with the I want to update data (import-compatible export) checkbox ticked results in an export file with two columns containing the external ID.

#### Common fields¶

Below is a list of commonly-used fields when importing vendor pricelists:

Field name definitions¶ Field name | Used for | Field in Odoo database | Technical name of field  
---|---|---|---  
Fornitore | The only required field for creating a vendor pricelist record. This field specifies the vendor associated with the product. | Vendor field in the vendor pricelist of the product form. | `partner_id`  
Modello prodotto | The Odoo product the vendor pricelist entry is related to. | Product field in the vendor pricelist. | `product_tmpl_id`  
Quantità | The minimum quantity required to receive the product at the specified price. | Quantity field in the vendor pricelist. (If not visible, enable it by clicking the __(adjust) icon, and tick the Quantity checkbox) | `min_qty`  
Prezzo unitario | The purchase price for the product from the vendor. | Price field in the vendor pricelist. | `price`  
Tempo di consegna | [Number of days](../../inventory/warehouses_storage/replenishment/lead_times.html#inventory-warehouses-storage-purchase-lt) before receiving the product after confirming a purchase order. | Delivery Lead Time field on the vendor pricelist. | `delay`  
Sequenza | Defines the order of vendors in the pricelist when multiple vendors are available. For example, if `Azure Interior` is listed first and Wood Corner second, their sequences would be `1` and `2`. | N/D | `sequence`  
Azienda | Name of company the product belongs to. | Company field in the vendor pricelist. | `company_id`  
External ID | Unique ID of a record used to update existing vendor pricelists. | N/D | `id`  
  
### Importa record¶

With a template downloaded, fill out the XLSX or CSV file with the necessary information. After inputting everything, import the file back into the Odoo database, by going to Purchase app ‣ Configuration ‣ Vendor Pricelists.

On the page, click the __(gear) icon in the top-left corner. In the drop-down menu that appears, click Import records.

Then, click Upload File in the upper-left corner, and after selecting the XLSX or CSV file, confirm the correct fields, and click Import.

Vedi anche

  * [Esportare e importare dati](../../../essentials/export_import_data.html)

  * Common fields




#### Formatting import file¶

To understand how to format import files for vendor pricelists, consider the following example.

  * `Storage Box` (Reference: `E-COM08`) is sold by `Wood Corner` for `$10`.

  * `Large Desk` (Reference: `E-COM09`) has no records in the vendor pricelist.




An import file is created to do the following:

  * Update the price for `Wood Corner` from `$10` to `$13`.

  * Add pricelist for `Storage Box`: the vendor, `Ready Mat` intends to sell the product for `$14`.

  * Add pricelist for `Large Desk`: vendor is `Wood Corner`, price is `$1299`.

  * Add pricelist for `Large Desk`: vendor is `Azure Interior`, price is `$1399`.


Vendor pricelist data¶ ID | company_id | delay | price | product_tmpl_id | sequenza | partner_id  
---|---|---|---|---|---|---  
product.product_supplierinfo_3 | My Company (San Francisco) | 3 | 13.00 | [E-COM08] Storage Box | 4 | Wood Corner  
| My Company (San Francisco) | 3 | 14.00 | [E-COM08] Storage Box | 5 | Ready Mat  
| My Company (San Francisco) | 2 | 1299.00 | [E-COM09] Large Desk | 6 | Wood Corner  
| My Company (San Francisco) | 4 | 1399.00 | [E-COM09] Large Desk | 7 | Azure Interior  
  
Nota

The _technical field name_ was used to create this information.

Nota

Download the sample files for reference:

  * [`Sample XLSX import file`](../../../../_downloads/54322bb572bfefb8d336adac3919288c/pricelist-example.xlsx)

  * [`Sample CSV import file`](../../../../_downloads/d233051feebacc1f52f8f43e2ac51f99/pricelist-example.csv)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/purchase/products/pricelist.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reordering.html "Configure reordering rules") |
  * [precedente](../products.html "Prodotti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Prodotti](../products.html) »
  * Import vendor pricelist


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management
  *[PO]: purchase order
  *[MTO]: Make to Order
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
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
  *[SVL]: stock move layer
  *[JIT]: just-in-time