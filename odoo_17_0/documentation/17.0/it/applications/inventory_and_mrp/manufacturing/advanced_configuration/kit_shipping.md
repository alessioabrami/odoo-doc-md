# Kits — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sub_assemblies.html "Manage semi-finished products") |
  * [precedente](product_variants.html "Managing BoMs for product variants") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Kits



# Kits¶

In Odoo, a _kit_ is a type of bill of materials (BoM) that can be manufactured and sold. Kits are sets of unassembled components sold to customers. They may be sold as standalone products, and are also useful tools for managing more complex bills of materials (BoMs).

Nota

To use, manufacture, and sell kits, both the Manufacturing and Inventory apps need to be installed.

## Create the kit as a product¶

To use a kit as a sellable product, or as a component organization tool, the kit should first be created as a product.

To create a kit product, go to Inventory app ‣ Products ‣ Products, and then click New.

Then, assign a name to the new kit product. Next, set the kit’s product type depending on inventory tracking needs and accounting requirements. To do this, under the General Information tab, set the Product Type to either Consumable or Storable.

The kit’s components must also be configured as products via Inventory app ‣ Products ‣ Products. These components require no specific configuration.

### Consumable kit setup details¶

Consumable products do not have inventory tracking. Consider setting the kit as a consumable product when the kit is used in other manufacturing processes or when tracking inventory for the kit itself is not needed.

  * **Recommended for Continental Accounting** : If costs are expensed immediately upon purchase, then setting the kit’s type to _consumable_ is recommended.

  * **Replenishment via Components** : Inventory count is managed at the component level, so reordering rules must be set to individual components.

  * **Selling & Stock Constraints**: Kits cannot be sold if any required component is out of stock. Since availability depends on individual components, a sales order may appear valid, but delivery can be delayed if components are unavailable.




### Storable kit setup details¶

Storable products have detailed tracking and inventory management since they are expected to be _stored_ once they are created. Consider setting the kit as a storable product when the kit is a tangible product or warehouse and inventory tracking is essential.

  * **Recommended for Angle-Saxon Accounting** : If the Cost of Goods Sold (COGS) needs to be recorded in journals, then setting the kit’s type to _storable_ is recommended.

  * **Component Purchase Constraints** : Only the kit’s minimum required components can be added to an **eCommerce** cart unless the option to [continue selling](../../../websites/ecommerce/products.html) is disabled.

  * **No Kit Serial Numbers** : Serial number tracking does not track the kit, only its shipped components.

  * **Reordering Rule Recommendation** : Reordering rules should be set at the component-level.

  * **Stock Replenishment Recommendation** : Stock replenishment should also be done at the component-level.




### Kit setup similarities¶

Regardless of which setup is used, there are some similarities between the two options.

  * **No Kit-Level Stock Adjustments** : Stock adjustments cannot be handled at the kit-level.

  * **Kit Value Does Not Change** : The stock’s value is the same whether the kit is consumable or storable.

  * **Kit Internal Transfers** : An internal transfer for the kit breaks it into components.




## Set up the kit BoM¶

After fully configuring the kit product and its components, a new BoM can be created for the kit product.

To do so, go to Manufacturing app ‣ Products ‣ Bills of Materials, and then click New. Next to the Product field, click the drop-down menu to reveal a list of products, and then select the previously configured kit product.

Then, for the BoM Type field, click the Kit option. Finally, under the Components tab, click Add a line, and add each desired component, and specify their quantities under the Quantity column.

Once ready, click Save to save the newly created BoM.

If the kit is solely being used as a sellable product, then only components need to be added under the Components tab, and configuring manufacturing operations is not necessary.

Nota

When a kit is sold as a product, it appears as a single line item on the quotation and sales order. However, on delivery orders, each component of the kit is listed.

## Use kits to manage complex BoMs¶

Kits can also be used for complex BoMs. This method nests BoMs within other BoMs, organizing complex products while simplifying manufacturing by defining each procurement and production step separately.

Sublevel BoMs (subassemblies or semi-finished products) streamline these workflows, helping with traceability efforts.

Vedi anche

[Manage semi-finished products](sub_assemblies.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/advanced_configuration/kit_shipping.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sub_assemblies.html "Manage semi-finished products") |
  * [precedente](product_variants.html "Managing BoMs for product variants") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Configurazione avanzata](../advanced_configuration.html) »
  * Kits


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
  *[MO]: manufacturing order
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
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