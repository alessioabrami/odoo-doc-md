# Master production schedule — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_center_time_off.html "Work center time off") |
  * [precedente](../workflows.html "Workflow") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Master production schedule



# Master production schedule¶

In Odoo’s _Manufacturing_ app, the _master production schedule_ (MPS) is used to manually plan manufacturing orders (MOs) and purchase orders (POs), based on forecasted quantities of products and components.

By considering the impact of confirmed MOs and POs, along with manually adjusted demand forecasts, the MPS can be used to manage long-term product replenishment. This ensures the continued availability of the necessary products and components.

Since the MPS allows for manual intervention, it is useful for replenishing products where the demand of existing sales orders (SOs) does **not** reflect probable future demand.

Example

A retail store sells artificial _Christmas trees_ during the holiday season. It is currently September, and the store has less than ten Christmas tree MOs confirmed for the month of December.

Despite the number of confirmed MOs, the procurement manager knows that the demand for Christmas trees in December is going to be much higher, once the holiday season starts. As a result, they manually enter a greater demand in the MPS, so they can properly replenish the product in time for the increase in customer demand.

Importante

It is essential to remember that the MPS is a **MANUAL** tool. Adding a product to the MPS does not cause it to be manufactured or purchased automatically. The MPS simply suggests the amount of the product that should be replenished, but requires user input to create the MOs or POs that are used to replenish it.

For this reason, it is recommended that the MPS **NOT** be used alongside reordering rules for the same product. Because reordering rules are an automated workflow, they conflict with the manual replenishment method of MPS. Using both, in unison, can lead to inaccurate forecasts and the creation of unnecessary replenishment orders.

## Enable and configure MPS¶

To use the MPS feature, navigate to Manufacturing app ‣ Configuration ‣ Settings, and tick the Master Production Schedule checkbox in the Planning section. Finally, click Save.

After enabling the Master Production Schedule feature, two new fields appear under it on the Settings page: Time Range and Number of Columns.

The Time Range field is used to select the period of time over which planning takes place, and offers three options: Monthly, Weekly, and Daily. For example, if Monthly is selected, the MPS plans the production requirements of products and components on a monthly basis.

The Number of Columns field is used to specify the quantity of the selected Time Range units shown on the MPS page. For example, if the Time Range field is set to Monthly, and `12` is entered in the Number of Columns field, the MPS shows one column for the next 12 months, starting with the current month.

If the values of the Time Range or Number of Columns fields are altered, click Save again to save the changes.

## MPS dashboard¶

To open the MPS, navigate to Manufacturing app ‣ Planning ‣ Master Production Schedule. The MPS view appears as follows:

The grey column on the left side of the screen shows a section for every product added to the MPS, with each product section being broken down into smaller rows. The information shown in the rows depends on the filters selected in the Search… bar drop-down menu at the top of the page. The default categories that appear in the rows are:

  * [Product] by [unit] __: the forecasted stock quantity at the beginning of each time period.[Product] and __are selectable buttons which open the product’s page, or the forecast report for the product, respectively.

  * \- Forecasted Demand: the demand forecast, which is entered manually. This represents an estimate of the demand for the product during each time period.

  * \- Indirect Demand Forecast: while this is a default category, it **only** appears for products that are components of other products. It represents the demand for the component from existing MOs.

  * \+ Suggested Replenishment: the quantity of the product that is suggested to be replenished through MOs or POs. To the right of the category title is a Replenish button, which is used to manually replenish the product, based on the quantity suggested to be replenished.

The «Replenish» button on the «+ Suggested Replenishment» row.¶

  * = Forecasted Stock: the quantity of the product forecasted to be in stock at the end of each time period, assuming that suggested replenishment numbers are fulfilled.




Altogether, these default categories form an equation:

\\[\text{Forecasted Demand} + \text{Suggested Replenishment} = \text{Forecasted Stock}\\]

In the case of components, the Indirect Demand Forecast is taken into account as well.

The \- Forecasted Demand and \+ Suggested Replenishment fields can be edited for any of the time periods to the right of the product column. Doing so changes the equation, and updates the value displayed in the Forecasted Stock field.

Changing the value in the \+ Suggested Replenishment field also makes an __(reset) button appear to the left of the field. Click the __(reset) button next to the field to reset its value back to the one calculated by the MPS.

Importante

While the MPS can be used with only the default categories enabled, it is advisable to also enable the Actual Demand category. This is done by clicking the __(down arrow) on the right side of the Search… bar, and enabling the Actual Demand option under the Rows header.

With the Actual Demand option enabled, the \- Forecasted Demand category changes to the \- Actual / Forecasted Demand category. In addition to the manually entered forecasted demand, this category also displays the confirmed demand for the product, which is based on confirmed SOs.

Each column to the right of the products column lists one unit of the time period selected in the _Time Range_ field on the _Manufacturing_ app _Settings_ page (ex. months). The number of time period columns corresponds to the value entered in the _Number of Columns_ field.

The first time period column represents the current time period. For example, if the MPS is configured to use months, the first column displays data for the current month. On this first column, the \+ Suggested Replenishment field appears in one of five colors:

  * Green: a replenishment order must be generated to keep stock at the Safety Stock Target.

  * Gray: a replenishment order has already been generated to keep stock at the Safety Stock Target.

  * Yellow: a replenishment order has already been generated, but the quantity it was created for is not enough to keep stock at the Safety Stock Target.

  * Red: a replenishment order has already been generated, but the quantity it was created for puts the amount of stock above the Safety Stock Target.




The \+ Suggested Replenishment field appears white, if no replenishment order has been generated, and it is not necessary to generate one at the current moment.

## Aggiungi prodotto¶

To use MPS to manage the replenishment of a product, navigate to Manufacturing app ‣ Planning ‣ Master Production Schedule. At the top of the MPS page, click Add a Product to open the Add a Product pop-up window.

Importante

Products **must** be properly configured to be replenished through the MPS.

In the case of manufactured products, the _Manufacture_ route must be selected in the _Routes_ section of the _Inventory_ tab, on the product’s form.

In the case of products that are purchased, the _Buy_ route must be selected in the _Routes_ section of the _Inventory_ tab, on the product’s form. Additionally, a vendor and the price they sell the product for must also be specified on the _Purchase_ tab.

On the pop-up window, select the product to add in the Product drop-down menu. If the product is replenished through manufacturing, select the product’s BoM in the Bill of Materials field.

Nota

Selecting a BoM when adding a product to the MPS also adds any components listed on the BoM. If it is not necessary to manage the replenishment of components through the MPS, simply leave the Bill of Materials field blank.

If the database is configured with multiple warehouses, a Production Warehouse field appears on the Add a Product pop-up window. Use this field to specify which warehouse the product is replenished to.

In the Safety Stock Target field, specify the minimum quantity of the product that should be kept available for orders at all times. For example, if there should always be 20 units of the product available for order fulfillment, enter `20` in the Safety Stock Target field.

In the Minimum to Replenish field, enter the minimum product quantity for orders created to replenish the product. For example, if `5` is entered in this field, replenishment orders for the product include a minimum of five units.

In the Maximum to Replenish field, enter the maximum product quantity for orders created to replenish the product. For example, if `100` is entered in this field, replenishment orders for the product include a maximum of 100 units.

Finally, click Save to add the product to the MPS. The product now appears on the MPS page each time it is opened. If a BoM was selected in the Bill of Materials field of the Add a Product pop-up window, any components listed on the BoM appear on the page, as well.

### Edit a product¶

After adding a product to the MPS, it may be necessary to change the replenishment values entered on the Add a Product pop-up window. To do so, click the # ≤…≤ # button to the immediate right of the Replenish button, on the \+ Suggested Replenishment row, below the product’s name.

Nota

The first and second number displayed on the # ≤…≤ # button correspond to the values entered in the Minimum to Replenish and Maximum to Replenish fields when adding the product to the MPS.

For example, if `5` was entered in the Minimum to Replenish field, and `100` was entered in the Maximum to Replenish field, the button appears as 5 ≤…≤ 100.

Clicking the # ≤…≤ # button opens the Edit Production Schedule pop-up window. This pop-up window is the same as the Add a Product pop-up window, except that the Product and Bill of Materials fields cannot be edited.

On the Edit Production Schedule pop-up window, enter the desired values in the Safety Stock Target, Minimum to Replenish, and Maximum to Replenish fields. Then, click Save to save the changes.

### Remove a product¶

To remove a product from the MPS, tick the checkbox to the left of its name. Then, click the __ Actions button at the top of the screen, and select Delete from the resulting drop-down menu. Finally, click Ok on the Confirmation pop-up window.

Deleting a product from the MPS removes it, along with all of its data. If the product is re-added, its replenishment values must be reconfigured.

## MPS replenishment¶

Products in the MPS can be replenished in one of three ways:

  * Click the Replenish button at the top of the screen to generate replenishment orders for every product below its Safety Stock Target for the current month.

  * Click the Replenish button on the right side of the \+ Suggested Replenishment row of a specific product, to generate a replenishment order for that specific product.

  * Tick the checkbox to the left of the product name of one or more products. Then, click the __ Actions button at the top of the screen, and select Replenish from the resulting drop-down menu. Doing so generates a replenishment order for each selected product.




The type of replenishment order generated corresponds to the route selected on the _Inventory_ tab of the product’s form:

  * If the _Buy_ route is selected, an RfQ is generated to replenish the product. RfQs can be selected by navigating to the Purchase app. Any RfQ generated by the MPS lists MPS in its Source Document field.

  * If the _Manufacture_ route is selected, an MO is generated to replenish the product. MOs can be selected by navigating to Manufacturing app ‣ Operations ‣ Manufacturing Orders. Any MO generated by the MPS lists MPS in its Source Document field.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/manufacturing/workflows/use_mps.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](work_center_time_off.html "Work center time off") |
  * [precedente](../workflows.html "Workflow") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Master production schedule


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
  *[MO]: manufacturing order
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
  *[MOs]: manufacturing orders
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