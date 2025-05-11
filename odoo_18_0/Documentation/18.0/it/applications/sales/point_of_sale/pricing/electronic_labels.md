# Electronic shelf labels — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment_methods.html "Metodo di pagamento") |
  * [precedente](cash_rounding.html "Arrotondamento di cassa") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Electronic shelf labels



# Electronic shelf labels¶

Electronic shelf labels allow you to display product information like prices and barcodes on store shelves and to synchronize them remotely from the backend. This removes the need to print new labels when product information changes.

Nota

Odoo uses electronic labels from [Pricer](https://www.pricer.com/).

## Configurazione¶

### Pricer setup¶

  1. [Get in touch with Pricer](https://www.pricer.com/contact) to create and configure your Pricer account.

  2. Create your stores: one pricer store equates to one physical store.

  3. Link as many transceivers as needed to the Pricer store(s).

  4. Create the following variables to share product information between your Odoo database system and Pricer. These variables act like placeholders on the label template.

     * `itemId`: this holds the unique internal identifier assigned to each product

     * `itemName`: the actual name of the product

     * `price`: the selling price of the product, including any applicable taxes

     * `presentation`: the template name used in Pricer for displaying the product information on the label

     * `currency`: the currency of your company (e.g., USD, EUR)

     * `barcode`: the barcode number associated with each product

Importante

The names for these variables must be **identical** in your Pricer database.

  5. Create a template named `NORMAL`. This template is used to display information on your digital tags.




Once your account, stores, variables, and template are configured on Pricer, you can proceed with the setup of your Odoo database.

Importante

The account associated with your Pricer store must have access to send API requests to Pricer.

### Configurare Odoo¶

As a pre-requisite, [activate](../../../general/apps_modules.html#general-install) the POS Pricer module _(technical name: pos_pricer)_ to have all the required features to use Pricer electronic tags.

Once the module is activated, configure your pricer stores and associate Pricer tags with your products.

#### Pricer stores¶

Similarly to the configuration in Pricer, you need to create one pricer store per physical location. To do so, go to Point of Sale ‣ Configuration ‣ Pricer Stores, click New, and fill in the line with the required information:

  * Store Name: you can put any name of your liking.

  * Pricer Tenant Name: the name of your company account in Pricer, usually followed by `-country_code`. This value is provided by Pricer.

  * Pricer Login: the login of your Pricer account.

  * Pricer Password: the password of your Pricer account.

  * Pricer Store ID: the ID of the related Pricer store as defined on your Pricer database.




Nota

  * The Pricer Tags column is updated automatically when a label is linked to a product.

  * The Last Update and Last Update Status columns are updated automatically when the tags are updated.




#### Etichette Pricer¶

For a label to display specific product information, the label needs to be associated with the product. To do so:

  1. Open the product form by going to Point of Sale ‣ Products ‣ Products and clicking New or selecting an existing product.

Nota

If you are creating a new product, configure and save it before associating any Pricer tags.

  2. Go to the Sales tab, scroll to the Pricer section, and select the corresponding Pricer Store.

  3. Fill in the Pricer tags ids field by copying the label’s ID from the label itself or scanning its barcode.

Nota

Pricer tag IDs are composed of a letter followed by 16 digits.




Suggerimento

  * We recommended using a barcode scanner to speed up the encoding process.

  * When setting up Pricer with Odoo for the first time, it is recommended that you configure only one product first. Before configuring more products, ensure you can display their information on a Pricer tag.




Now that you have a product associated with a Pricer tag, we can send its information to Pricer.

### Practical application¶

Odoo automatically sends requests to Pricer to synchronize the tags every 12 hours if you make any modifications to:

>   * Product name, price, barcode, or customer taxes
> 
>   * Valuta
> 
>   * Associated Pricer store or Pricer tags
> 
> 


To force the update, activate the [developer mode](../../../general/developer_mode.html#developer-mode). Then:

  1. Go to Point of Sale ‣ Configuration ‣ Pricer Store.

  2. Select the desired store(s).

  3. Click Update tags to update all tags affected by changes to:

     * Product name, price, barcode, or customer taxes

     * Valuta

     * Associated Pricer store or Pricer tags




Alternatively, click Update all tags to force the update of every tag, regardless of whether changes were made.

If Pricer has processed and accepted the request, the status field shows Update successfully sent to Pricer. If there is any issue, the system displays an error message.

Avvertimento

If a request sent to Pricer fails, Odoo still considers that the product has been updated. In that case, we recommend forcing the update of all tags.

### Discount labels¶

To display a discount label on a Pricer Tag, you need to link a [pricelist](pricelists.html) to the product variant associated with the tag.

To do so, open the product variant form:

  1. Go to Point of Sale ‣ Products ‣ Product Variants.

  2. Select the product you want to apply a discount to.




Then, set the desired pricelist:

  1. Go to the General Information tab.

  2. Select a pricelist in the Pricer Sales Pricelist field.




Once a pricelist is set, the On Sale Price field appears, showing the Sales Price with the discount applied.

After updating your electronic labels, a `PROMO` tag should appear on the electronic label, displaying both the old, crossed-out price and the discounted price.

Nota

  * Currently, pricelists that offer discounts for purchasing multiple units or derive their prices from other pricelists are not supported.

  * Assigning a pricelist to a product variant only affects the electronic label display. Scanning the product at the point of sale does not automatically apply the discount.




Vedi anche

[Sconti](discounts.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/point_of_sale/pricing/electronic_labels.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../payment_methods.html "Metodo di pagamento") |
  * [precedente](cash_rounding.html "Arrotondamento di cassa") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Pricing features](../pricing.html) »
  * Electronic shelf labels


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
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
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID