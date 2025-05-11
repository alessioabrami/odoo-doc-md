# Bill of materials — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](one_step_manufacturing.html "One-step manufacturing") |
  * [precedente](configure_manufacturing_product.html "Manufacturing product configuration") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * Bill of materials



# Bill of materials¶

A _bill of materials_ (or _BoM_ for short) documents specific components, along with their respective quantities, that are needed to produce or repair a product. In Odoo, BoMs serve as blueprints for manufactured goods and kits, and often include production operations and step-by-step guidelines, as well.

## BoM setup¶

To create a BoM, go to Manufacturing app ‣ Products ‣ Bills of Materials and click New.

Next, set the BoM Type to Manufacture this Product.

Then, specify required components and, if necessary, define any manufacturing operations.

Suggerimento

Individual BoMs can also be quickly accessed or created by clicking the Bill of Materials smart button on any product form, as accessible through the _Sales_ , _Inventory_ , and _Manufacturing_ apps, as well as through any internal links where a product is referenced (such as in a field or a line item).

BoM for `Drawer`, displaying the **Components** tab.¶

Vedi anche

  * [Kits](../advanced_configuration/kit_shipping.html)

  * [Basic subcontracting](../subcontracting/subcontracting_basic.html)




### Componenti¶

In the Components tab of a BoM, specify components used to manufacture the product by clicking Add a line. From the Components drop-down menu, select from existing products or create a new product by typing the name and selecting either the Create » « option to quickly add the line item, or the Create and edit… option to add the component and continue to its configuration form.

Optionally, access additional fields by clicking the __(settings adjust) icon to the far-right of the Components tab. Tick the checkboxes for the following features to enable these columns:

  * Apply on Variants: specify which [product variant](../advanced_configuration/product_variants.html) each component is used in. When the field is left blank, the component is used in all product variants.



  * Consumed in Operation: specify the operation using the component. Useful for determining manufacturing readiness.

  * Manual Consumption: tick the checkbox to force operators to check the Consumed checkbox on a manufacturing order (MO).

Not doing so triggers the Consumption Warning error message, where the consumed component quantity must be manually inputted. Otherwise, the operation cannot be completed.




### Operazioni¶

Add an _operation_ to a BoM to specify instructions for production and register time spent on an operation. To use this feature, first enable the _Work Orders_ feature by going to Manufacturing app ‣ Configuration ‣ Settings. In the Operations section, tick the Work Orders checkbox to enable the feature.

Vedi anche

[Work order dependencies](../advanced_configuration/work_order_dependencies.html)

Next, navigate to the BoM by going to Manufacturing app ‣ Products ‣ Bill of Materials and selecting the desired BoM. To add a new operation, go to the Operations tab, and click Add a line.

Doing so opens the Create Operations pop-up window, where the various fields of the operation are configured:

  * Operation: name of the operation.

  * Work Center: select existing locations to perform the operation, or create a new work center by typing the name and selecting the Create » « option.

  * Apply on Variants: specify if this operation is only available for certain product variants. If the operation applies to all product variants, leave this field blank.

Vedi anche

[Configuring BoMs for product variants](../advanced_configuration/product_variants.html)

  * Duration Computation: choose how time spent on the operation is tracked. Opt for Compute based on tracked time to use the operation’s time tracker or Set duration manually if operators can record and modify time themselves.

Choosing the Compute based on tracked time option enables the Based on last __ work orders option, which automatically estimates the time to complete this operation based on the last few operations. Choosing Set duration manually enables the Default Duration field instead.

  * Default Duration: estimated amount of time to complete the operation; used for [planning manufacturing orders](https://www.youtube.com/watch?v=TK55jIq00pc) and determining [work center availability](https://www.youtube.com/watch?v=3YwFlD97Bio).

  * Company: specify the company the BoM is available in.




Include operation details in the Work Sheet tab. Choose PDF to attach a file or Google Slide with _public_ access to share a link. Select Text to type instructions in the Description text field.

Suggerimento

Type `/` for a list of formatting options and features, including ChatGPT.

Finally, click Save & Close to close the pop-up window. To add more operations, click Save & New and repeat the same steps above to configure another operation.

Nota

Each operation is unique, as it is always exclusively linked to one BoM.

Suggerimento

After creating an operation, click the Copy Existing Operations button to choose an operation to duplicate.

#### Istruzioni¶

Importante

To add detailed instructions to operations, the _Quality_ app must be installed.

Add specific instructions to an existing operation by clicking the operation’s __(list) icon in the Instructions column. The number in the Instructions column shows the number of existing detailed instructions there are for the operation.

On the Steps dashboard, click New to open a blank quality control point form where the new manufacturing step can be created. Here, give the specific instruction a Title and set the Type to Instructions. In the Instructions tab of the form, write out the directions for the step in the operation.

Nota

Further customizations can be made here on this form, beyond ordinary instructions, to also include specific types of quality control points that carry specific (or complex) conditions. For more details about quality control points refer the [Instruction check](../../quality/quality_check_types/instructions_check.html) documentation.

### Varie¶

The Miscellaneous tab contains more BoM configurations to customize procurement, calculate costs, and define how components are consumed.

  * Manufacturing Readiness: choosing When components for the 1st operation are available shows the Component Status as a **green** Not Available, when only the components that are consumed in the first operation are in stock. This indicates that although not all components are available, operators can at least begin with the first operation. Choosing When all components are available displays a **red** Not Available component status unless all components are in available.

Suggerimento

Specify which operation consumes each component on the BoM in the Manual Consumption field.

  * Version: displays the current BoM version, visible with the Odoo _PLM_ app installed for managing BoM changes.

  * Flexible Consumption: specifies if components used can deviate from the quantity defined on the BoM. Choose Blocked if operators **must** adhere strictly to the BoM quantity. Otherwise, choose Allowed or Allowed with Warning.

  * Routing: select the preferred warehouse’s manufacturing operation type for products produced in multiple warehouses. If left blank, this warehouse’s `Manufacturing` operation type is used by default.

  * Analytic Distribution: select pre-created [analytic distribution models](../../../finance/accounting/reporting/analytic_accounting.html) from the list to automatically record the cost of manufacturing products in the chosen journal.

  * Manuf Lead Time: define the number of days needed to complete a MO from the date of confirmation.

  * Days to prepare Manufacturing Order: number of days needed to replenish components, or manufacture sub-assemblies of the product.




Vedi anche

  * [Analytic distribution](../../../finance/accounting/reporting/analytic_accounting.html)

  * [Lead times](../../inventory/warehouses_storage/replenishment/lead_times.html)




## Add by-products to BoMs¶

A _by-product_ is a residual product that is created during production in addition to the main product of a BoM. Unlike the primary product, there can be more than one by-product on a BoM.

To add by-products to a BoM, first enable the _By-Products_ feature in Manufacturing app ‣ Configuration ‣ Settings. In the Operations section, tick the checkbox for By-Products to enable the feature.

Once the feature is enabled, add by-products to a BoM by clicking the By-products tab. Click Add a line, and fill in the By-product, Quantity, and Unit of Measure. Optionally, specify a Produced in Operation for the by-product.

Example

The by-product, `Mush`, is created in the `Grind grapes` operation when producing `Red Wine`.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/basic_setup/bill_configuration.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](one_step_manufacturing.html "One-step manufacturing") |
  * [precedente](configure_manufacturing_product.html "Manufacturing product configuration") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * Bill of materials


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
  *[FBM]: Fulfilled By Merchant
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