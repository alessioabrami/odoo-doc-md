# Managing BoMs for product variants — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kit_shipping.html "Kits") |
  * [precedente](../advanced_configuration.html "Configurazione avanzata") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Managing BoMs for product variants



# Managing BoMs for product variants¶

Odoo allows one bill of materials (BoM) to be used for multiple variants of the same product. Having a consolidated BoM for a product with variants saves time by preventing the need to manage multiple BoMs.

## Activate product variants¶

To activate the product variants feature, navigate to Inventory app ‣ Configuration ‣ Settings, and scroll down to the Products section. Then, click the checkbox to enable the Variants option. After that, click Save to apply the setting.

For more information on configuring product variants, refer to the [product variants](../../../sales/sales/products_prices/products/variants.html) documentation.

## Create custom product attributes¶

Once the product variants feature is activated, create and edit product attributes on the Attributes page.

The Attributes page is accessible either from Inventory app ‣ Configuration ‣ Settings by clicking the Attributes button, or by clicking Inventory app ‣ Configuration ‣ Attributes.

Once on the Attributes page, either click into an existing attribute, or click Create to create a new one. Clicking Create reveals a new, blank form for customizing an attribute. For an existing attribute, click Edit on its form to make changes.

Assign an Attribute Name, and choose a category from the Category field’s drop-down menu. Then, select the desired options next to the Display Type and Variants Creation Mode fields. Once the desired options are selected, click Add a line under the Attribute Values tab to add a new value.

Suggerimento

Included on the Value row is a Is custom value checkbox. If selected, this value will be recognized as a custom value, which allows customers to type special customization requests upon ordering a custom variant of a product.

Example

Once all desired Values have been added, click Save to save the new attribute.

## Add product variants on the product form¶

Created attributes can be applied on specific variants for particular products. To add product variants to a product, navigate to the product form by going to Inventory app ‣ Products ‣ Products. To make changes to the product, click Edit. Then, click the Variants tab.

Under the Attribute header, click Add a line to add a new attribute, and select one to add from the drop-down menu.

Then, under the Values header, click the drop-down menu to choose from the list of existing values. Click on each desired value to add them, and repeat this process for any additional attributes that should be added to the product.

Once finished, click Save to save changes.

Suggerimento

BoM products with multiple variants that are manufactured in-house should either have a **0,0 reordering rule** set up, or have their replenishment routes set to _Replenish on Order (MTO)_.

## Apply BoM components to product variants¶

Next, create a new BoM. Or, edit an existing one, by going to Manufacturing app ‣ Products ‣ Bills of Materials. Then, click Create to open a new Bills of Materials form to configure from scratch.

Add a product to the BoM by clicking the drop-down menu in the Product field and selecting the desired product.

Then, add components by clicking Add a line under the Component section of the Components tab, and choosing the desired components from the drop-down menu.

Choose the desired values in the Quantity and Product Unit of Measure columns. Then, choose the desired values in the Apply on Variants column.

Nota

The Apply on Variants option to assign components to specific product variants on the BoM is available once the Variants setting is activated from the Inventory application. If the Apply on Variants field is not immediately visible, activate it from the additional options menu (three-dots icon, to the right of the header row).

Each component can be assigned to multiple variants. Components with no variants specified are used in every variant of the product. The same principle applies when configuring operations and by-products.

When defining variant BoMs by component assignment, the Product Variant field in the main section of the BoM should be left blank. This field is _only_ used when creating a BoM specifically for one product variant.

When all desired configurations have been made to the BoM, click Save at the top of the form to save changes.

Suggerimento

For components that only apply for specific variants, choose which operations the components should be consumed in. If the Consumed in Operation column is _not_ immediately visible, activate it from the additional options menu (three-dots icon, to the right of the header row).

## Sell and manufacture variants of BoM products¶

To sell and manufacture variants of BoM products to order, navigate to Sales app ‣ Create to create a new quotation.

### Sell variant of BoM product¶

Once on the blank Quotation form, click the drop-down next to the Customer field to add a customer.

Then, under the Order Lines tab, click Add a product, and select the previously-created BoM product with variants from the drop-down menu. Doing so reveals a Configure a product pop-up.

From the pop-up window, click the desired attribute options to configure the correct variant of the product to manufacture. Then, click the green + or - icons next to the `1` to change the quantity to sell and manufacture, if desired.

Once all the specifications have been chosen, click Add. This will change the pop-up to a second Configure pop-up, where available optional products will appear, if they have been created previously.

Once ready, click Confirm to close the pop-up.

Then, click Save to save all changes, and click Confirm at the top of the Quotation form to create and confirm a new sales order (SO).

### Manufacture variant of BoM product¶

Once the SO is confirmed, a Manufacturing smart button appears at the top of the SO form. Click the Manufacturing smart button to open the Manufacturing Order form.

On this form, under the Components tab, the appropriate components for the chosen variant are listed. And, depending on the variant, different components will be listed. To see any mandatory or optional Operation steps, click the Work Orders tab.

To enter the tablet view work order screen, click the tablet icon to the right of the row for the desired operation to be completed.

From the tablet view, click Mark as Done as the operation progresses to complete the operation steps.

Alternatively, click the Mark as Done button at the top of the manufacturing order form to complete the order.

Then, navigate back to the SO via the breadcrumbs at the top of the page.

Now that the product has been manufactured, click the Delivery smart button to deliver the product to the customer. From the Delivery Order form, click Validate, then click Apply to deliver the product.

To finish the sale, click back to the SO via the breadcrumbs at the top of the page again. Then, click Create Invoice followed by Create Invoice again to invoice the customer for the order.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/product_variants.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](kit_shipping.html "Kits") |
  * [precedente](../advanced_configuration.html "Configurazione avanzata") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Managing BoMs for product variants


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
  *[BoM]: bill of materials
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
  *[BoMs]: bills of material
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
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