# Subappalto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subcontracting/subcontracting_basic.html "Basic subcontracting") |
  * [precedente](shop_floor/shop_floor_tracking.html "Shop Floor time tracking") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Produzione](../manufacturing.html) »
  * Subappalto



# Subappalto¶

In manufacturing, _subcontracting_ is the process of a company engaging a third-party manufacturer, or subcontractor, to manufacture products that are then sold by the contracting company.

Subcontracting provides a variety of benefits for both the contracting company and the subcontractor.

For the contracting company, subcontracting allows them to sell a wide variety of manufactured products, without having to worry about investing in and maintaining the equipment and labor required to handle the manufacturing themselves.

This helps contracting companies stay flexible throughout economic cycles, as they can easily increase or decrease their engagements with subcontractors, as necessitated by the current moment. It also means they are able to focus on tasks they excel at, while delegating more specialized work to subcontractors.

On the other side of the relationship, subcontracting allows subcontractors to specialize in more niche areas of production, which might not be as profitable outside the bounds of a subcontracting engagement. In certain arrangements, it also provides them with the flexibility to choose which projects they accept or decline, and how many they work on at any given time.

In Odoo, companies can configure their subcontracting workflows based on a variety of different factors, including how components are sourced, and what happens to finished products once they are manufactured.

#### [Basic subcontractingSubcontract products without supplying the subcontractor with components. ](subcontracting/subcontracting_basic.html)#### [Resupply subcontractorShip components to a subcontractor each time a PO for a subcontracted product is confirmed. ](subcontracting/subcontracting_resupply.html)#### [Dropship to subcontractorDropship components to a subcontractor each time a PO for a subcontracted product is confirmed. ](subcontracting/subcontracting_dropship.html)

## Configurazione¶

To enable subcontracting in Odoo, navigate to Manufacturing app ‣ Configuration ‣ Settings, and tick the checkbox next to the Subcontracting setting, under the Operations heading. Then, click Save.

With subcontracting enabled, a few different features become available in Odoo:

  * On bills of materials (BoMs), the _BoM Type_ field now includes a _Subcontracting_ option. Enabling the _Subcontracting_ BoM type designates the BoM’s product as a subcontracted product, which means Odoo knows that it is produced by a subcontractor, and not by the company that owns the Odoo database.

  * Two subcontracting routes become available in the _Inventory_ app, and can be assigned to specific products, on the _Inventory_ tab of their product pages:

    * _Resupply Subcontractor on Order_

    * _Dropship Subcontractor on Order_




## Subcontracting workflows¶

In Odoo, there are three subcontracting workflows, the main difference between them being _how_ the subcontractor obtains the necessary components:

  * In the _basic_ subcontracting workflow, the subcontractor is fully responsible for obtaining the components. This workflow is outlined in the [Basic subcontracting](subcontracting/subcontracting_basic.html) documentation.

  * In the _Resupply Subcontractor on Order_ workflow, the contracting company sends the components from their warehouse to the subcontractor. This workflow is outlined in the [Resupply subcontractor](subcontracting/subcontracting_resupply.html) documentation.

  * In the _Dropship Subcontractor on Order_ workflow, the contracting company purchases the components from a vendor, and has them delivered directly to the subcontractor. This workflow is outlined in the [Dropship to subcontractor](subcontracting/subcontracting_dropship.html) documentation.




In addition to how a subcontractor obtains components, it is also necessary to consider why a product is being subcontracted, as well as what happens to products once they are manufactured by the subcontractor.

In terms of why a product is being subcontracted, the two main reasons are to fulfill a customer order, or to replenish the quantity of stock on-hand.

In terms of what happens to products once they are manufactured, they can either be shipped to the contracting company, or dropshipped directly to an end customer.

Each of the three subcontracting workflows described above can be configured to facilitate any of these possibilities, and the methods for doing so are outlined in their respective documentation.

## Subcontracted product valuation¶

The valuation of a subcontracted product depends upon a few different variables:

  * The cost of the required components, if provided by the contracting company; from here on referred to as `C`.

  * The price paid to the subcontractor for the service of manufacturing the subcontracted product; from here on referred to as `M`.

  * The cost of shipping components to the subcontractor, and having them shipped back to the contracting company; from here on referred to as `S`.

  * The cost of dropshipping, if the components are shipped by the subcontractor to the end customer; from here on referred to as `D`.

  * Any other associated costs, like import taxes, etc.; from here on referred to as `x`.




Therefore, the total valuation of a subcontracted product (`P`) can be represented by the following equation:

\\[P = C + M + S + D + x\\]

It is important to note that not every subcontracted product valuation will include all of these variables. For example, if the product is not dropshipped to the end customer, then there is no need to factor in the cost of dropshipping.

  * Basic subcontracting
    * Configurazione
      * [Configure product](subcontracting/subcontracting_basic.html#configure-product)
      * [Configure BoM](subcontracting/subcontracting_basic.html#configure-bom)
    * Basic subcontracting workflow
      * [Create SO](subcontracting/subcontracting_basic.html#create-so)
      * [Process PO](subcontracting/subcontracting_basic.html#process-po)
      * Process receipt or dropship order
        * [Process receipt](subcontracting/subcontracting_basic.html#process-receipt)
        * [Process dropship order](subcontracting/subcontracting_basic.html#process-dropship-order)
      * [Process delivery order](subcontracting/subcontracting_basic.html#process-delivery-order)
  * Basic subcontracting lead times
    * Configurazione
      * [Product delivery lead time](subcontracting/basic_subcontracting_lead_times.html#product-delivery-lead-time)
    * [Lead time workflow](subcontracting/basic_subcontracting_lead_times.html#lead-time-workflow)
  * Resupply subcontractor
    * Configurazione
      * [Configure product](subcontracting/subcontracting_resupply.html#configure-product)
      * [Configure BoM](subcontracting/subcontracting_resupply.html#configure-bom)
      * [Configure components](subcontracting/subcontracting_resupply.html#configure-components)
    * Resupply subcontractor on order workflow
      * [Create SO](subcontracting/subcontracting_resupply.html#create-so)
      * [Process PO](subcontracting/subcontracting_resupply.html#process-po)
      * [Process Resupply Subcontractor order](subcontracting/subcontracting_resupply.html#process-resupply-subcontractor-order)
      * Process receipt or dropship order
        * [Process receipt](subcontracting/subcontracting_resupply.html#process-receipt)
        * [Process dropship order](subcontracting/subcontracting_resupply.html#process-dropship-order)
      * [Process delivery order](subcontracting/subcontracting_resupply.html#process-delivery-order)
  * Resupply subcontracting lead times
    * Configurazione
      * [Product delivery lead time](subcontracting/resupply_subcontracting_lead_times.html#product-delivery-lead-time)
      * [Product manufacturing lead time](subcontracting/resupply_subcontracting_lead_times.html#product-manufacturing-lead-time)
      * [Resupply subcontracting workflow](subcontracting/resupply_subcontracting_lead_times.html#resupply-subcontracting-workflow)
  * Dropship to subcontractor
    * Configurazione
      * [Configure product](subcontracting/subcontracting_dropship.html#configure-product)
      * [Configure bill of materials](subcontracting/subcontracting_dropship.html#configure-bill-of-materials)
      * [Configure Components](subcontracting/subcontracting_dropship.html#configure-components)
    * Dropship subcontractor on order workflow
      * [Create an SO](subcontracting/subcontracting_dropship.html#create-an-so)
      * [Process subcontractor PO](subcontracting/subcontracting_dropship.html#process-subcontractor-po)
      * [Confirm vendor RfQ](subcontracting/subcontracting_dropship.html#confirm-vendor-rfq)
      * [Process Dropship Subcontractor order](subcontracting/subcontracting_dropship.html#process-dropship-subcontractor-order)
      * [Process receipt or dropship order](subcontracting/subcontracting_dropship.html#process-receipt-or-dropship-order)
      * [Process delivery order](subcontracting/subcontracting_dropship.html#process-delivery-order)
  * Dropship subcontracting lead times
    * Configurazione
      * [Product delivery lead time](subcontracting/dropship_subcontracting_lead_times.html#product-delivery-lead-time)
      * [Product manufacturing lead time](subcontracting/dropship_subcontracting_lead_times.html#product-manufacturing-lead-time)
      * [Component delivery lead time](subcontracting/dropship_subcontracting_lead_times.html#component-delivery-lead-time)
    * [Dropship subcontracting workflow](subcontracting/dropship_subcontracting_lead_times.html#dropship-subcontracting-workflow)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/subcontracting.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](subcontracting/subcontracting_basic.html "Basic subcontracting") |
  * [precedente](shop_floor/shop_floor_tracking.html "Shop Floor time tracking") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Supply Chain](../../inventory_and_mrp.html) »
  * [Produzione](../manufacturing.html) »
  * Subappalto


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