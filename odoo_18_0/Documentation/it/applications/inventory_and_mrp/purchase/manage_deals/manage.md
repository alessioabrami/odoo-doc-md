# Manage vendor bills — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzato") |
  * [precedente](control_bills.html "Bill control policies") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Manage vendor bills



# Manage vendor bills¶

A _vendor bill_ is an invoice received for products and/or services purchased by a company from a vendor. Vendor bills record payables as they arrive from vendors, and can include amounts owed for the goods and/or services purchased, sales taxes, freight and delivery charges, and more.

In Odoo, a vendor bill can be created at different points in the purchasing process, depending on the _bill control_ policy chosen in the _Purchase_ app’s settings.

## Bill control policies¶

To configure the default bill control policy, navigate to Purchase app ‣ Configuration ‣ Settings, and scroll to the Invoicing section.

The Bill Control feature lists two policy options: Ordered quantities and Received quantities.

The policy selected acts as the default for any new product created. Each policy acts as follows:

  * Ordered quantities: creates a vendor bill as soon as a purchase order is confirmed. The products and quantities in the purchase order are used to generate a draft bill.

  * Received quantities: a bill is only created **after** all (or part) of the total order has been received. The products and quantities received are used to generate a draft bill.




Once a policy is selected, click Save to save the changes.

Suggerimento

If a product needs a different control policy than the one set in the _Purchase_ app settings, that product’s control policy can be overridden by going to the Purchase tab on a product form, and selecting the desired policy in the Control Policy field.

### Corrispondenza a tre vie¶

The _3-way matching_ policy ensures vendor bills are only paid once all (or some) products in a purchase order (PO) have been received.

To activate 3-way matching, navigate to Purchase app ‣ Configuration ‣ Settings, and scroll to the Invoicing section.

Tick the checkbox next to 3-way matching, and click Save.

Importante

The 3-way matching feature is **only** intended to work with the Bill Control policy set to Received quantities.

## Create and manage vendor bills on receipts¶

When products are received into a company’s warehouse, receipts are created. Once the company processes the received quantities, they can choose to create a vendor bill directly from the warehouse receipt form.

Depending on the bill control policy chosen in the settings, vendor bill creation is completed at different steps of the procurement process.

### Quantità ordinate¶

To create and manage vendor bills for receipts with the _Bill Control_ policy set to _Ordered Quantities_ , first navigate to the Purchase app, and click New from the Requests for Quotation dashboard.

Doing so opens a new Request for Quotation (RfQ) form. On the blank RfQ form, add a Vendor, and click Add a line under the Product tab to add products to the order.

On the product line, select a product from the drop-down menu in the Product field, and enter the quantity to order in the Quantity field.

Once ready, click Confirm Order to confirm the RfQ into a PO.

Then, click Create Bill to create a vendor bill. This opens a Vendor Bill form in the Draft state. From here, add a billing date in the Bill Date field.

Once ready, confirm the bill by clicking Confirm on the Vendor Bill page.

Suggerimento

Since the bill control policy is set to _Ordered quantities_ , the draft bill can be confirmed as soon as it is created, before any products have been received.

Once a payment has been received, click Register Payment at the top of the bill to record it.

Doing so causes a Register Payment pop-up window to appear, wherein a payment Journal can be chosen, and a Payment Method selected.

Additionally, the bill Amount, Payment Date, and Memo (Reference Number) can be edited from this pop-up window, if necessary.

Once ready, click Create Payment to finish creating the Vendor Bill. Doing so displays a green Paid banner on the RfQ form.

### Quantità ricevute¶

To create and manage vendor bills for receipts with the bill control policy set to _Received quantities_ , first navigate to the Purchase app, and click New.

Doing so opens a new RfQ form. On the blank RfQ form, add a Vendor, and click Add a line under the Product tab to add products to the order.

On the product line, select a product from the drop-down menu in the Product field, and enter the quantity to order in the Quantity field.

Once ready, click Confirm Order to confirm the RfQ into a PO.

Importante

When using the _Received quantities_ control policy, clicking Create Bill before any products are received causes an Invalid Operation pop-up window to appear.

Odoo requires at least partial quantities of the items included in the PO to be received in order to create a vendor bill.

On the PO, click the Receipt smart button to view the warehouse receipt form.

From here, click Validate to register the Done (received) quantities.

Then, navigate back to the PO, via the breadcrumb, and click Create Bill.

This opens a Vendor Bill form in the Draft state. From here, add a billing date in the Bill Date field. Once ready, confirm the bill by clicking Confirm at the top of the draft.

Once a payment has been received, click Register Payment at the top of the bill to record it.

Doing so causes a Register Payment pop-up window to appear, wherein a payment Journal can be chosen, and a Payment Method selected.

Additionally, the bill Amount, Payment Date, and Memo (Reference Number) can be edited from this pop-up window, if necessary.

Once ready, click Create Payment to finish creating the Vendor Bill. Doing so displays a green Paid banner on the RfQ form.

## Manage vendor bills in Accounting¶

Vendor bills can also be created directly from the _Accounting_ app, without having to create a purchase order first.

Navigate to Accounting app ‣ Vendors ‣ Bills, and click New. Doing so reveals a blank Vendor Bill form.

Add a vendor in the Vendor field. Then, in the Invoice Lines tab, click Add a line to add products.

Select a product from the drop-down menu in the Product field, and enter the quantity to order in the Quantity field.

Select a Bill Date, and configure any other necessary information. Finally, click Confirm to confirm the bill.

Once confirmed, click the Journal Items tab to view the Account journals. These journals are populated based on the configuration on the corresponding Vendor and Product forms.

If necessary, click Credit Note to add a credit note to the bill. Additionally, a Bill Reference number can be added.

Once ready, click Register Payment, followed by Create Payment, to complete the Vendor Bill.

Suggerimento

To link a draft bill to an existing purchase order, click the drop-down menu next to Auto-Complete _before_ clicking Confirm, and select a PO from the menu.

The bill auto-populates with the information from the chosen PO.

## Batch billing¶

Vendor bills can be processed and managed in batches in the _Accounting_ app.

Navigate to Accounting app ‣ Vendors ‣ Bills. Then, click the checkbox in the top-left corner, beside the Number column, under the New button.

This selects all existing vendor bills with a Status of Posted or Draft.

Click the __ Print button to print the selected invoices or bills.

Click Register Payment to create and process payments for multiple vendor bills at once.

Nota

Only payments with their Status listed as Posted can be billed in batches. Payments in the Draft stage **must** be posted before they can be included in a batch billing.

Clicking Register Payment opens a Register Payment pop-up window. From the pop-up window, select the Journal the bills should post to, choose a Payment Date, and select a Payment Method.

There is also the option to Group Payments together from this pop-up window, as well. If this checkbox is ticked, only one payment is created, instead of one per bill. This option only appears if the _Batch Payments_ feature is enabled in the settings of the Accounting app.

Once ready, click the Create Payment button. This creates a list of journal entries on a separate page. The journal entries on this list are all tied to their corresponding vendor bills.

Vedi anche

[Bill control policies](control_bills.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/purchase/manage_deals/manage.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced.html "Avanzato") |
  * [precedente](control_bills.html "Bill control policies") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Manage vendor bills


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
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock move layers
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
  *[SVL]: stock move layer
  *[JIT]: just-in-time