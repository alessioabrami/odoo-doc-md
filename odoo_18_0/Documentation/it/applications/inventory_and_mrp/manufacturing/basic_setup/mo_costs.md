# Manufacturing order costs — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced_configuration.html "Configurazione avanzata") |
  * [precedente](three_step_manufacturing.html "Three-step manufacturing") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * Manufacturing order costs



# Manufacturing order costs¶

The ability to accurately calculate the cost of manufacturing a product is critical when determining product profitability. Odoo’s **Manufacturing** app simplifies this calculation by automatically calculating the cost to complete each manufacturing order (MO), as well as the average production cost of a product, based on all completed MOs.

Importante

Odoo’s Manufacturing app distinguishes between the _MO cost_ and the _real cost_ of an MO.

The MO cost represents how much it _should_ cost to complete an MO, based on the configuration of the product’s bill of materials (BoM). This takes into account the cost and quantity of components, as well as the cost of completing the necessary operations.

The real cost represents how much it _actually_ costs to complete the MO. A few factors can cause the real cost to differ from the MO cost. For example, an operation may take longer to complete than estimated, a greater component quantity might be needed than was specified on the BoM, or the price of components may change during manufacturing.

## Cost configuration¶

Odoo computes MO costs based on the configuration of the BoM used to manufacture a product. This calculation includes the cost and quantity of components and operations listed on the BoM, in addition to the operating costs of the work centers where those operations are carried out, and the amount paid to each employee who works on an operation.

### Component cost¶

Component cost is calculated automatically, based on the average purchase cost of a component across all purchase orders (POs). To view a component’s cost, navigate to Inventory app –> Products –> Products, and select a component product. The cost is displayed in the Cost field of the General Information tab, on the component’s product form.

It is possible to set the cost of a component manually, by clicking the Cost field on the component’s product form and entering a value. However, any future POs for the component override a manually entered value, resetting the Cost field back to an automatically computed value.

### Work center cost¶

To set the operating cost for a specific work center, navigate to Manufacturing app ‣ Configuration ‣ Work Centers, and select a work center.

To set the cost of operating the work center for one hour, enter a value in the per workcenter field, located beside the Cost per hour section on the work center’s General Information tab.

To set the hourly cost of each employee that operates the work center, enter a value in the per employee field, located beside the Cost per hour section on the work center’s General Information tab. For example, if `25.00` is entered in the per employee field, it costs $25.00 per hour for _each_ employee working at the work center.

Importante

The value entered in the per employee field is only used to calculate the MO cost, which is the estimated cost of completing the MO.

The actual cost of completing the MO is represented by the real cost. Instead of using the value entered in the per employee field, the real cost is calculated using the hourly cost specific to each employee.

For example, if the per employee cost of a work center is “$50.00”, and an employee with an hourly cost of “$60.00” completes a work order there, the MO cost (estimated) is calculated using the $50/hr cost, while the real cost is calculated using the $60/hr cost.

See the employee cost section below for information on how to set the cost for specific employees.

### Employee cost¶

To set the hourly cost for a specific employee, navigate to the Employees app, and select an employee. On the employee’s form, select the Settings tab, and enter the employee’s rate in the Hourly Cost field of the Application Settings section.

Importante

As detailed in the work center cost section above, the value entered in the Hourly Cost field on the employee’s form is used to calculate the real cost of an MO. The estimated cost of an MO, referred to as the MO cost, uses the per employee cost set on each work center’s form.

### BoM configuration¶

Configuring a BoM so Odoo can accurately calculate the cost of MOs that use it requires two steps. First, components **must** be added, and the required quantity specified. Second, operations **must** be added, along with the work centers where they are carried out.

Begin by navigating to Manufacturing app ‣ Products ‣ Bills of Materials. Select a BoM, or create a new one by clicking New.

In the Components tab of the BoM form, add each component by clicking Add a line, selecting the component from the drop-down menu in the Component column, and entering the quantity in the Quantity column.

In the Operations tab, add an operation by clicking Add a line to open the Create Operations pop-up window. Enter a title for the operation in the Operation field.

Select the Work Center where the operation is carried out. Then, add a Default Duration, which is the estimated amount of time the operation takes to complete.

By default, the Duration Computation field is set to Set duration manually, which means that the number entered in Default Duration field is always used as the expected duration of the operation.

Selecting Compute based on tracked time causes Odoo to automatically compute the Default Duration based on a certain number of work orders, which is set in the Based on field. Before there are work orders to compute this duration, the value in the Default Duration field is used instead.

The hourly cost of operating the work center, and the duration of the operation, are used to calculate the operation’s cost.

Finally, click Save & Close to add the operation to the BoM, and close the Create Operations pop-up window. Alternatively, click Save & New to add the operation to the BoM, and open a blank Create Operations pop-up window to add another operation.

Vedi anche

For a full overview of BoM configuration, see the documentation on [bills of materials](bill_configuration.html).

## MO overview¶

Each MO has an _overview_ page, which lists a variety of information about the MO, including MO cost and real cost. To view the overview for an MO, navigate to Manufacturing app ‣ Operations ‣ Manufacturing Orders, and select an MO. Then, click the __ Overview smart button at the top of the MO.

Both the MO cost and real cost take into account the cost and quantity of components, as well as the cost of completing each work order. The overview page lists a row for each of these values, with the sum of them listed at the bottom of the MO Cost and Real Cost columns.

Before work begins on an MO, the MO Cost and Real Cost columns display the same costs. This is the _estimated_ cost of completing the MO.

However, once work commences, the values in the Real Cost column may begin to diverge from the values in the MO Cost column. This happens if a different component quantity is used than was listed on the MO, the duration of a work order is different than expected, or the hourly cost of the employee performing a work order differs from the employee cost set on the work center.

Once the MO has been completed by clicking Produce All, the values in the MO Cost column update to match those displayed in the Real Cost column.

## Average manufacturing cost¶

In addition to the cost of each individual MO for a product, Odoo also tracks the average cost of manufacturing the product, taking into account the cost of every completed MO. To view this, navigate to Inventory app ‣ Products ‣ Products, and select a product.

The manufacturing cost of the product is displayed per unit of measure in the Cost field, located in the General Information tab. The value continues to update as the costs of additional MOs are factored into the average cost.

To the right of the Cost field is a Compute Price from BoM button, which only appears for products with at least one BoM. Click this button to reset the cost of the product to the expected cost, which only takes into account the components and operations listed on the BoM.

Importante

Be aware that clicking Compute Price from BoM does not set the price permanently. The cost continues to update based on the average of the BoM price and the real cost of any future MOs.

Example workflow: manufacturing cost

Golf product manufacturer _Fairway Fields_ produces a variety of golf products, including an indoor _putting green_. They have configured a BoM for the putting green, so Odoo automatically calculates the manufacturing cost of each putting green MO.

The BoM lists two components:

  * One unit of _green felt_ , which costs $20.00.

  * One unit of a _rubber pad_ , which costs $30.00.




The BoM also lists four operations, all of which are carried out at _Assembly Station 1_ , which has an hourly operating cost of $30.00. Those operations are as follows:

  * _Cut felt_ : default duration of seven minutes, for a total cost of $3.50.

  * _Cut rubber pad_ : default duration of five minutes, for a total cost of $2.50.

  * _Attach pad to felt_ : default duration of 15 minutes, for a total cost of $7.50.

  * _Cut holes_ : default duration of three minutes, for a total cost of $1.50.




Altogether, the components required to produce one putting green cost $50.00, and the operations required cost $15.00, for a total manufacturing cost of $65.00. This cost is reflected in the Cost field on the putting green’s product form.

Fairway Fields confirms an MO for one putting green. Before manufacturing starts, the MO overview lists a cost of `$65.00` in both the MO Cost and Real Cost fields.

Manufacturing begins, and the operations take ten minutes longer than expected, for a total manufacturing time of 40 minutes. This deviation from the BoM is reflected on the MO overview, which now lists a Real Cost of `$70.00`.

Once manufacturing is finished, and the MO is marked as _Done_ , the MO overview updates again, so the values in the MO Cost and Real Cost columns match, each displaying a value of `$70.00`.

On the putting green’s product page, the Cost field now displays a cost of `$67.50`, the average of the original cost of $65.00 and the real cost of $70.00 from the MO.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/basic_setup/mo_costs.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../advanced_configuration.html "Configurazione avanzata") |
  * [precedente](three_step_manufacturing.html "Three-step manufacturing") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Basic setup](../basic_setup.html) »
  * Manufacturing order costs


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