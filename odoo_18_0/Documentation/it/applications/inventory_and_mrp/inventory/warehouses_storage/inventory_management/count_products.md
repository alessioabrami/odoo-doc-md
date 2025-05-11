# Inventory adjustments — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cycle_counts.html "Cycle counts") |
  * [precedente](use_locations.html "Ubicazioni") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Inventory management](../inventory_management.html) »
  * Inventory adjustments



# Inventory adjustments¶

In any warehouse management system, the recorded inventory counts in the database might not always match the actual inventory counts in the warehouse. Discrepancy between counts can be due to damage, human error, theft, or other factors. As such, inventory adjustments must be made to reconcile the differences, and ensure that the recorded counts in the database match the actual counts in the warehouse.

## Inventory Adjustments page¶

To view the Inventory Adjustments page, navigate to Inventory app ‣ Operations ‣ Physical Inventory.

The Inventory Adjustments page lists all products that are currently in stock.

Nota

Only products with a quantity greater than zero are listed on the Inventory Adjustments page. To view product lines with zero current quantity, go to Inventory app ‣ Reporting ‣ Stock.

For each product line, the following information is listed:

  * Location: the specific location in the warehouse where a product is stored. This column is **only** visible if [Storage Locations](use_locations.html) are enabled.

  * Favorite: identifies products that have been favorited.

  * Product: the product whose quantity is listed on the inventory adjustment line.

  * Lot/Serial Number: the tracking identifier assigned to the specific product listed. It can contain letters, numbers, or a combination of both.




Nota

If a specific product has a quantity of more than `1.00` in stock, and more than one serial number, or lot number, assigned to it, each uniquely-identified product is displayed on its own product line with its own lot/serial number, displayed under the Lot/Serial Number column.

  * Expiration Date: the date on which the goods with this serial number are due to expire.

  * Last Count Date: the last time the quantity was updated.

  * Package: the package containing the quantity listed.

  * On Hand Quantity: the quantity of the product currently recorded in the database.

  * Unit: the _unit of measure_ in which the product is measured. Unless otherwise specified (e.g., in Pounds or Ounces), the default UoM is Units.

  * Counted Quantity: the real quantity counted during an inventory count. This field is left blank by default but can be changed, depending on if it matches the On Hand Quantity or not.

  * Difference: the difference between the On Hand Quantity and Counted Quantity, once an inventory adjustment is made. The difference is automatically calculated after every inventory adjustment.

  * Scheduled Date: the date at which a count should be made. If not otherwise specified, this date will default to the 31st of December of the current year.

  * User: the person assigned to the count in the database. This can either be the person physically counting the inventory, or applying the count in the database.




Suggerimento

Additional columns are hidden by default. To reveal these columns, click the __(adjust) icon to the far right of the form’s top row, and reveal any desired column by ticking the checkbox next to that option.

### Create an inventory adjustment¶

To create a new inventory adjustment from the Inventory Adjustments page, click New. Doing so creates a new, blank inventory adjustment line at the bottom of the page.

Suggerimento

Inventory adjustments can also be created from the Forecasted Report on an individual product record. To open the report, navigate to a product record and click the Forecasted smart button. Then, at the top of the page, click Update Quantity, then New.

On this blank inventory adjustment line, click the drop-down menu under the Product column, and select a product. If the selected product is tracked using either lots or serial numbers, the desired lot or serial number needs to be chosen from the drop-down menu under the Lot/Serial Number column.

Suggerimento

The inventory adjustment line can also be used to create or record lots and serial numbers.

Next, set the value in the Counted Quantity column to the quantity counted for that product during the inventory adjustment process.

To the right of the Counted Quantity column, the Scheduled Date and User can also be changed via their respective drop-down menus. Changing the Scheduled Date changes the date that the inventory adjustment should be processed on, and selecting a responsible User assigns a user to the specific inventory adjustment for traceability purposes.

Once all changes have been made to the new inventory adjustment line, click away from the line. Doing so saves the adjustment, and moves the line to the top of the page.

If the Counted Quantity is greater than the On Hand Quantity, the value in the Difference column is **green**. If the Counted Quantity is less than the On Hand Quantity, the value in the Difference column is **red**. If the quantities match, and have not been changed at all, no value appears in the Difference column.

At this stage, the count (inventory adjustment) is recorded, but not yet applied. This means that the quantity on hand before the adjustment has not yet been updated to match the new, real counted quantity.

### Apply adjusted count¶

Inventory adjustments can be completed in several ways. The first way is to click the Apply button on the line at the far right of the page. The second way is to tick the checkbox on the far left of the line. Doing so reveals new button options at the top of the page, one of which is an Apply button. Clicking this button instead causes an Inventory Adjustment pop-up window to appear.

From this pop-up menu, a reference or reason can be assigned to the inventory adjustment. By default, the Inventory Reason field is pre-populated with today’s date, the date the adjustment is being made on, but can be changed to reflect whatever reference or reason is desired.

Once ready, click Apply to apply the inventory adjustment.

Nota

Applying an inventory adjustment simultaneously creates a [stock move line (SML)](../reporting/moves_history.html) in the _Moves History_ report for traceability.

## Relocate products¶

Inventory adjustments can also be used to relocate products to different storage locations, or to different packages. To relocate a product, tick the checkbox at the far left of the line for the desired product. At the top of the page, click the Relocate button. Doing so opens a pop-up.

On the resulting pop-up, enter the following information:

  * To Location: the new location for the products.

  * To Package: the new package for the products.

  * Reason for relocation: the reason for the move.




Importante

Product relocations **only** work on internal locations. Products **cannot** be moved between companies.

Only users with _Administrator_ rights can perform product relocations.

## Set to zero¶

Inventory adjustments can also be used to clear inventory counts by setting the quantity to zero. To do this, tick the checkbox at the far left of the line for the desired product. At the top of the page, click the __ Actions button to open a drop-down menu. Click Set to 0. Once this is complete, apply the adjusted count.

## Count products¶

Counting products is a recurring activity in a warehouse. Once a count is complete, go to Inventory app ‣ Operations ‣ Physical Inventory to update the Counted Quantity column for each product line.

On each product line, identify whether the value in the On Hand Quantity column recorded in the database matches the newly-counted value. If the recorded value and the counted value do match, click the __ Set icon at the far right of the product line.

Doing so copies the value from the On Hand Quantity column over to the Counted Quantity column, and sets the value of the Difference column to `0.00`. Subsequently, once applied, an inventory move with `0.00` Quantity Done is recorded in the product’s inventory adjustment history.

If the newly-counted value for a given product does **not** match the value in the On Hand Quantity recorded in the database, instead of clicking the __ Set icon, record the real value in the field in the Counted Quantity column.

To do so, click the field in the Counted Quantity column on the specific inventory adjustment line for the product whose count is being changed. This automatically assigns a Counted Quantity of `0.00`.

To change this value, type in a new value that matches the real, newly-counted value. Then, click away from the line. Doing so saves the adjustment, and automatically adjusts the value in the Difference column.

If the Counted Quantity is greater than the On Hand Quantity, the value in the Difference column is **green**. If the Counted Quantity is less than the On Hand Quantity, the value in the Difference column is **red**. If the quantities match, and have not been changed at all, no value appears in the Difference column.

Subsequently, once applied, a move with the difference between the On Hand Quantity and the Counted Quantity is recorded in the product’s inventory adjustment history.

The Actions menu appears when one or more products” checkboxes are selected. The Actions menu includes the option to Set to quantity on hand, which sets the selected products” Counted Quantity to the On Hand Quantity, and Set to 0, which sets the selected products” Counted Quantity to zero.

Importante

Sometimes a count occurs, but cannot be applied in the database right away. In the time between the actual count and applying the inventory adjustment, product moves can occur. In that case, the on-hand quantity in the database can change and no longer be consistent with the counted quantity. As an extra precaution, Odoo asks for confirmation before applying the inventory adjustment.

## Revert an inventory adjustment¶

To revert the changes made in an inventory adjustment, navigate to Inventory ‣ Reporting ‣ Moves History.

Tick the checkbox at the far left of the line for the desired product. At the top of the page, click the __ Actions button to open a drop-down menu, and click Revert Inventory Adjustment.

Nota

After an inventory adjustment is reverted, the line is not removed from the Moves History report. Instead, an additional line is added, this time with the word `[reverted]` added to the Reference column.

## Change inventory count frequency¶

By default, the _scheduled date_ for inventory adjustments are always scheduled for the 31st of December of the current year. However, for some companies, it is crucial that they have an accurate inventory count at all times. In such cases, the default scheduled date can be modified.

To modify the default scheduled date, go to Inventory app ‣ Configuration ‣ Settings. Then, in the Operations section, locate the Annual Inventory Day and Month setting, which includes a drop-down menu that is set to `31 December` by default.

To change the day, click the `31`, enter a number from `1-31`, depending on the desired month of the year.

Then, to change the month, click December to reveal the drop-down menu, and select the desired month.

Once all desired changes have been made, click Save to save all changes.

### Plan big inventory counts¶

To plan big inventory counts, such as a full count of everything currently in stock, first navigate to Inventory app ‣ Operations ‣ Physical Inventory.

Then, select the desired products to be counted by ticking the checkbox on the far left of each product line.

Suggerimento

To request a count of **all** products currently in stock, tick the checkbox at the top of the table, in the header row next to the Location label. This selects **all** product lines.

Once all desired products have been selected, click the Request a Count button at the top of the page. Doing so opens the Request a Count pop-up window, where the following information can be filled:

  * Inventory Date: the planned date of the count.

  * User: the user responsible for the count.

  * Accounting Date: the date at which the inventory adjustment will be accounted.

  * Count: to leave the on-hand quantity of each product line blank, select Leave Empty. To pre-fill the on-hand quantity of each product line with the current value recorded in the database, select Set Current Value.




Nota

The Leave Empty option forces the employee conducting the audit to manually type in the number they counted, while the Set Current Value option only requires the employee to _verify_ the counted quantity and click Apply.

Finally, once ready, click Confirm to request the count.

Importante

In the Odoo **Barcode** app, users can only view inventory counts that are assigned to _them_ , and are scheduled for _today_ or _earlier_.

Sometimes a count occurs, but cannot be applied in the database right away. In the time between the actual count and applying the inventory adjustment, product moves can occur. In that case, the on-hand quantity in the database can change and no longer be consistent with the counted quantity. As an extra precaution, Odoo asks for confirmation before applying the inventory adjustment.

## Adjustment history¶

Details regarding inventory adjustment can be viewed by clicking the __ History icon.

The user who performed the count is listed in parenthesis in the Reference field, while the user who applied the count is listed in the Done By.

### Inventory audit¶

An inventory audit can be accessed from the Inventory Adjustment page. This audit includes an inventory record both before and after a count is completed, to track what changed.

On the Inventory Adjustment page, tick the checkbox at the top-left of the page to select all of the lines. Then click the Request a Count button. On the pop-up, set Count to Set Current Value, then click Confirm.

After returning to the Inventory Adjustment page, select all of the lines again. Click Print ‣ Count Sheet. The Count Sheet exports in PDF form.

Vedi anche

[Cycle counts](cycle_counts.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/inventory_management/count_products.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cycle_counts.html "Cycle counts") |
  * [precedente](use_locations.html "Ubicazioni") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
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
  *[AVCO]: Average Cost
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
  *[PO]: purchase order
  *[MTO]: Make to Oder
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