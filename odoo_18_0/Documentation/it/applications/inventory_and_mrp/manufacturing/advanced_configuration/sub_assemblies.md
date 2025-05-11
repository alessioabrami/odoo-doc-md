# Multilevel BoMs — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](using_work_centers.html "Work centers") |
  * [precedente](kit_shipping.html "Kits") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Multilevel BoMs



# Multilevel BoMs¶

Use a multilevel bill of materials (BoM) when a manufactured product is part of another assembly. This method nests BoMs within other BoMs, organizing complex products while simplifying manufacturing by defining each procurement and production step separately.

Sublevel BoMs (subassemblies or semifinished products) streamline these production workflows, and are beneficial when the subassembly is used across multiple finished products (meaning they’d appear on multiple top-level BoMs). The more complicated a product is to build or procure, the more value a multilevel BoM can provide. Because of this, component and subassembly replenishment planning is vital to ensuring multilevel BoMs run smoothly.

## Why replenishment planning is important¶

[Replenishment](../../inventory/warehouses_storage/replenishment.html) is critical for multilevel BoMs to prevent bottlenecks, manage lead times, and optimize inventory. Without it, missing components can halt production, delay orders, and increase costs. A well-planned replenishment strategy ensures [just-in-time availability](../../inventory/warehouses_storage/replenishment/reordering_rules.html), [automates procurement](../../inventory/warehouses_storage/replenishment/reordering_rules.html), balances stock levels, and keeps supply chains efficient. This minimizes delays, reduces manual effort, and ensures smooth manufacturing.

Manufacturing orders (MO)s that come from a BoM require all components to be available before the MO can be completed. The Component Status for that MO provides this information. Learn how to [check an MO’s component status](../basic_setup/bill_configuration.html).

## Create a multilevel BoM¶

To set up a multilevel BoM, the top-level product and sublevel products’s BoMs must be created. If starting from scratch, build the BoMs from the bottom up. Start with the lowest-level product BoMs, then include those products as components in higher-level BoMs.

Example

A printed circuit board (PCB) for a custom keyboard is composed of hundreds of electronic components, such as transistors, resistors, and capacitors. Instead of listing all of those components out, a sublevel product and BoM for a `PCB` is created, to track the quantities of transistors and other small components, without needing to overcrowd the top-level BoM for the custom keyboard by listing them. Instead, the custom keyboard’s BoM consists of an assortment of components and sublevel BoMs alike, like key caps, switches, the PCB, and keyboard plate.

[Learn how to build a simple bill of materials](../basic_setup/bill_configuration.html). For the PCB, this would include the transistors, resistors, and other components.

After the sublevel products (like the PCB, key caps, and keyboard plate) are fully configured, create the top-level product by navigating to Manufacturing app ‣ Products ‣ Products, and then selecting New. From here, configure the product’s specifications as needed.

Once the top-level product (the keyboard) is configured, click the Bill of Materials smart button on the product form, and then select New to make a BoM for the top-level product. Add the sublevel products to this BoM, along with any other necessary components.

## Gestisci la pianificazione della produzione¶

The two options below are two of the best ways to manage manufacturing order automation for products with multilevel BoMs.

Nota

Complex BoMs are specifically used to manage products that require manufactured components. If a BoM is being created to organize components or bundle sellable products, [use a kit](kit_shipping.html) instead.

To automatically trigger manufacturing orders for sublevel products after confirming a manufacturing order for the main product, there are two options:

  * **Option 1 (recommended):** Create _Reordering Rules_ for the sublevel products and set both the minimum and maximum needed stock quantities to `0`.

  * **Option 2:** Activate the Replenish on Order (MTO) and Manufacture routes under the Inventory tab of the sublevel product’s product form.




Vedi anche

  * [Reordering rules](../../inventory/warehouses_storage/replenishment/reordering_rules.html)

  * [Replenish on order (MTO)](../../inventory/warehouses_storage/replenishment/mto.html)




Option 1 is more flexible than Option 2 and is recommended. Reordering rules do not directly link demand to replenishment, allowing stock to be unreserved and reassigned as needed. The Replenish on Order (MTO) route, however, uniquely links sublevel and top-level products, reserving quantities for the confirmed top-level manufacturing order.

In both methods, sublevel products must be fully manufactured before starting the top-level product.

## Multilevel BoM setup flow¶

The following section details how to set up multilevel BoMs, set the initial inventory, establish a 0/0/1 reordering rule (the recommended production plan), configure lead times, and set up production options.

Creating a 0/0/1 reordering rule for the sublevel products (minimum stock set at zero, maximum stock set at zero, reorder one automatically) regardless of whether they are a component or subassembly is the recommended approach for managing a multilevel BoM. This setup uses the **Inventory** , **Manufacturing** , and **Purchase** apps.

Importante

This is only one example of how to set up a multilevel BoM in Odoo. Consider any unique circumstances that need to be addressed during the configuration, and make sure they are included in the setup. If any specific help is needed during setup, consider purchasing a [success pack](https://www.odoo.com/pricing-packs).

### Create the BoMs¶

Follow the steps in the Create a multilevel BoM section to build the BoMs.

Make sure to build the multilevel BoM from the bottom up. Start by creating the lowest-level component products in Odoo, then the subassembly products that those are used for, then the BoM for that subassembly, and repeat until every level of the multilevel BoM is created.

### Set the initial inventory¶

Nota

If there’s no initial inventory to configure, then skip this section and begin configuring the procurement method for the multilevel BoM.

Update the quantity on hand for each of the products configured in the prior step (both components, subassemblies, and the final product). To do this, open the **Inventory** app, and then find the products with filters, the search bar, or scrolling, and then click on them to open their product form. From here, click the On Hand smart button, [select the variant](../../../sales/sales/products_prices/products/variants.html) if that was configured, and then enter the quantity on hand.

Vedi anche

[Inventory adjustments](../../inventory/warehouses_storage/inventory_management/count_products.html)

### Configure the procurement method¶

Now it is time to pick the procurement method this multilevel BoM uses. The two options below are preferred, but unique circumstances may lead to another procurement method making more sense.

  * **Option 1 (recommended):** Create _Reordering Rules_ for the sublevel products and set both the minimum and maximum needed stock quantities to `0`.

  * **Option 2:** Activate the Replenish on Order (MTO) and Manufacture routes under the Inventory tab of the sublevel product’s product form.




Vedi anche

  * [Reordering rules](../../inventory/warehouses_storage/replenishment/reordering_rules.html)

  * [Replenish on order (MTO)](../../inventory/warehouses_storage/replenishment/mto.html)




Reordering rules are recommended because they do not tie the manufactured product to a specific sales order, allowing that manufactured product to fulfill a different sales order if the original gets cancelled.

Making the product to order is not recommended because the manufactured product cannot be used to fulfill another sales order. However, this could be helpful if strict tracking is necessary for the business.

### Enter vendor and manufacturing lead times¶

Vendor and manufacturing lead times are used by Odoo to coordinate production and procurement actions to fulfill orders on time. Set vendor lead times for components that are purchased. These can appear at any level in a multilevel BoM except the final product. Set manufacturing lead times for products that are built using a BoM. These can appear at any level in a multilevel BoM except the lowest level (when individual components are procured).

Vedi anche

[Lead times](../../inventory/warehouses_storage/replenishment/lead_times.html)

### Build out operations to handle the production flow¶

First, determine the current manufacturing flow for the business, then match the corresponding Odoo setup. The list below are only some of the configuration pieces that could be involved in this step.

  * **Manufacturing Steps** : Consider how many manufacturing steps are taken (one-, two-, or three-step manufacturing).

  * **Work Centers** : Decide if any [work centers](using_work_centers.html) need to be configured.

  * **Master Production Schedule** : If manually planned manufacturing orders are needed (e.g., to handle seasonal demand), make a [master production schedule](../workflows/use_mps.html) (MPS).




Suggerimento

Manufacturing operations is an art and a science, so configuring an established flow into Odoo is the recommended approach for this step. Read more about [manufacturing in Odoo](../../manufacturing.html)

### Configuration summary¶

At the end of this process, the multilevel BoM is configured, and the top-level product has its inventory counts, procurement method set, procurement lead times, and manufacturing operations configured. From here, sales orders can include the top-level product, automatic procurement through vendors or manufacturing can begin, the top-level product can be included in an **eCommerce** store.

Vedi anche

  * [Creare preventivi](../../../sales/sales/sales_quotations/create_quotations.html)

  * [Catalogo](../../../websites/ecommerce/products/catalog.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/sub_assemblies.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](using_work_centers.html "Work centers") |
  * [precedente](kit_shipping.html "Kits") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Multilevel BoMs


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