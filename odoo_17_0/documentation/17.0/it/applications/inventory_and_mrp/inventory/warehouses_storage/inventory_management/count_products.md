# Inventory adjustments — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cycle_counts.html "Cycle counts") |
  * [precedente](use_locations.html "Ubicazioni") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Inventory management](../inventory_management.html) »
  * Inventory adjustments



# Inventory adjustments¶

In any warehouse management system, the recorded inventory counts in the database might not always match the actual inventory counts in the warehouse. The discrepancy between the two counts can be due to damages, human errors, theft, or other factors. As such, inventory adjustments must be made to reconcile the differences, and ensure that the recorded counts in the database match the actual counts in the warehouse.

## Inventory Adjustments page¶

To view the _Inventory Adjustments_ page, navigate to Inventory app ‣ Operations ‣ Physical Inventory.

In the Inventory Adjustments table, all products that are currently in stock are listed, with each product line containing the following information:

  * Location: the specific location in the warehouse where a product is stored. This field needs to be enabled my going to Inventory app ‣ Configuration ‣ Settings and ticking the Storage Locations checkbox.

  * Product: the product whose quantity is listed on the inventory adjustment line.

  * Lot/Serial Number: the tracking identifier assigned to the specific product listed. It can contain letters, numbers, or a combination of both.

  * UoM: the _unit of measure_ in which the product is measured. Unless otherwise specified (i.e., in Pounds or Ounces), the default UoM is Units.

  * Counted Quantity: the real quantity counted during an inventory count. This field is left blank by default but can be changed, depending on if it matches the On Hand Quantity or not.

  * Difference: the difference between the On Hand Quantity and Counted Quantity, once an inventory adjustment is made. The difference is automatically calculated after every inventory adjustment.




Nota

If a specific product has a quantity of more than `1.00` in stock, and more than one serial number (or lot number) is assigned, each uniquely-identified product is displayed on its own product line with its own lot/serial number, under the Lot/Serial Number column.

The fields below are optional and can be made visible by clicking the __(settings) icon in the top right of the Inventory Adjustments page.

  * Inventory Frequency (Days): the frequency, in days, for inventory counts. The default value of this field is set to `0`.

  * Favorite: adds a clickable star icon next to each product. Adding a favorite will bring the line item to the top of the dashboard.

  * Product Category: the category assigned internally to a specific product. Unless otherwise specified (i.e., as Consumable or Rental), the default _Product Category_ is set to All.

  * Expiration Date: the date a product will expire, if it is a perishable good. Only products that are tracked using lots and serial numbers can be assigned expiration information.

  * Last Count Date: the date on which the last inventory count occurred.

  * Available Quantity: the quantity of a specific product that is currently available, based on any outstanding/uncompleted sales orders, purchase orders, or manufacturing orders that might change the available quantity once fulfilled.

  * On Hand Quantity: the quantity of the product currently recorded in the database.

  * Accounting Date: the date on which the adjustments will be accounted for in the Odoo **Accounting** app.

  * Scheduled Date: the date at which a count should be made. If not otherwise specified, this date defaults to the 31st of December of the current year.

  * User: the person assigned to the count in the database. This can either be the person physically counting the inventory, or applying the count in the database.

  * Company: the company whose database these inventory adjustments are being made on. The company is listed in the top-right corner of the database, next to the user currently logged in.




Suggerimento

Some columns are hidden by default. To reveal these columns, click the __(settings) icon to the far right of the form’s top row, and select any desired column to reveal by clicking the checkbox next to that option.

Vedi anche

  * [Product type](../../product_management/configure/type.html)

  * [Tracking with lots, serial numbers, and expiration dates](../../product_management/product_tracking.html)




### Create an inventory adjustment¶

To create a new inventory adjustment from the Inventory Adjustments page, click New. Doing so creates a new, blank inventory adjustment line at the bottom of the page.

On this blank inventory adjustment line, define the Location where the product is stored. This is necessary to ensure the accuracy of the inventory adjustment, as the same product can be stored in multiple locations.

Next, click the drop-down menu under the Product column, and select a product. If the selected product is tracked using either lots or serial numbers, the desired lot or serial number can also be chosen from the drop-down menu under the Lot/Serial Number column.

Next, set the value in the Counted Quantity column to the quantity counted for that product during the inventory adjustment process.

To the right of the Counted Quantity column, the Scheduled Date and User can also be changed via their respective drop-down menus. Changing the Scheduled Date changes the date that the inventory adjustment should be processed on, and selecting a responsible User assigns a user to the specific inventory adjustment (for traceability purposes).

Once all changes have been made to the new inventory adjustment line, click away from the line. Doing so saves the adjustment, and moves the line to the top of the page.

If the Counted Quantity is greater than the On Hand Quantity, the value in the Difference column is **green**. If the Counted Quantity is less than the On Hand Quantity, the value in the Difference column is **red**. If the quantities match, and haven’t been changed at all, no value appears in the Difference column.

At this stage, the count (inventory adjustment) is recorded, but not yet applied. This means that the quantity on hand before the adjustment has not yet been updated to match the new, real counted quantity.

There are two ways to apply the new inventory adjustment. The first way is to click the __ Apply button on the line at the far right of the page. The second way is to click the checkbox on the far left of the line. Doing so reveals new button options at the top of the page, one of which is an Apply button. Clicking this button instead causes an Inventory Adjustment pop-up window to appear.

From this pop-up menu, a reference or reason can be assigned to the inventory adjustment. By default, the Inventory Reason field is pre-populated with the date the adjustment is being made on, but can be changed to reflect whatever reference or reason is desired.

Once ready, click Apply to apply the inventory adjustment.

Nota

Applying an inventory adjustment simultaneously creates a [stock move line (SML)](../reporting/moves_history.html) in the _Moves History_ report for traceability.

Suggerimento

Sometimes products end up in unexpected or incorrect locations. To quickly move a product to a different storage location, check the box next to the product, and click the Relocate button at the top of the Inventory Adjustments page.

## Count products¶

Counting products (or stock-taking) is a recurring warehouse process to verify the physical quantity of items against internal inventory records. The values recorded on file versus what is actually counted in real life sometimes do not match, so inventory adjustments can be made on the _Inventory Adjustments_ dashboard.

Once a count is complete, go to Inventory app ‣ Operations ‣ Physical Inventory to verify and update product Count Quantities, as it is necessary to do so.

Suggerimento

To print a PDF of a count sheet, first select the desired product checkboxes, and then click the __ Print button that appears at the top of the dashboard. Then, select the Count sheet option in the sub-menu, which will download a PDF detailing the selected products.

On each product line, identify whether the value in the On Hand Quantity column recorded in the database matches the newly-counted value. If the recorded value and the counted value do match, select the product using the checkbox, click the Actions button, then Set to quantity on hand.

Doing so copies the value from the On Hand Quantity column over to the Counted Quantity column, and sets the value of the Difference column to `0.00`. Subsequently, once applied, an inventory move with `0.00` Quantity Done is recorded in the product’s inventory adjustment history.

If the newly-counted value for a given product does **not** match the value in the On Hand Quantity recorded in the database, instead of clicking the Set button, record the real value in the field in the Counted Quantity column.

To do so, click the field in the Counted Quantity column on the specific inventory adjustment line for the product whose count is being changed. This automatically assigns a Counted Quantity of `0.00`.

To change this value, type in a new value that matches the real, newly-counted value. Then, click away from the line. Doing so saves the adjustment, and automatically adjusts the value in the Difference column.

Subsequently, once applied, a move with the difference between the On Hand Quantity and the Counted Quantity is recorded in the product’s inventory adjustment history.

The Actions menu appears when one or more products” checkboxes are selected. The Actions menu includes the option to Set to quantity on hand, which sets the selected products” Counted Quantity to the On Hand Quantity, and Set to 0, which sets the selected products” Counted Quantity to zero.

Importante

Sometimes a count occurs, but cannot be applied in the database right away. In the time between the actual count and applying the inventory adjustment, product moves can occur. In that case, the on-hand quantity in the database can change and no longer be consistent with the counted quantity. As an extra precaution, Odoo asks for confirmation before applying the inventory adjustment.

### Plan inventory counts¶

To plan inventory counts, such as a full count of everything currently in stock, first navigate to Inventory app ‣ Operations ‣ Physical Inventory.

Then, select the desired products to be counted by clicking the checkbox on the far left of each product line.

Suggerimento

To request a count of **all** products currently in stock, click the checkbox at the very top of the table, in the header row next to the Location label. This selects **all** product lines.

Once all desired products have been selected, click the Request a Count button at the top of the page. Doing so opens the Request a Count pop-up window, where the following information can be filled:

  * Inventory Date: the planned date of the count.

  * User: the user responsible for the count.

  * Accounting Date: the date at which the inventory adjustment will be accounted.

  * Count: to leave the on-hand quantity of each product line blank, select Leave Empty. To pre-fill the on-hand quantity of each product line with the current value recorded in the database, select Set Current Value.




Finally, once ready, click Confirm to request the count.

Importante

In the Odoo **Barcode** app, users can only view inventory counts that are assigned to **them** , and are scheduled for **today** or **earlier**.

Vedi anche

[Cycle counts](cycle_counts.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/inventory_management/count_products.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cycle_counts.html "Cycle counts") |
  * [precedente](use_locations.html "Ubicazioni") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Inventory management](../inventory_management.html) »
  * Inventory adjustments


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
  *[MPS]: Master Production Schedule
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
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Oder
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order