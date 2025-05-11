# Reordering rules — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](report.html "Replenishment report") |
  * [precedente](mto.html "Replenish on order \(MTO\)") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rifornimenti](../replenishment.html) »
  * Reordering rules



# Reordering rules¶

_Reordering rules_ are used to keep forecasted stock levels above a certain threshold without exceeding a specified upper limit. This is accomplished by specifying a minimum quantity that stock should not fall below and a maximum quantity that stock should not exceed.

Reordering rules can be configured for each product based on the route used to replenish it. If a product uses the _Buy_ route, then a _request for quotation_ (RFQ) is created when the reordering rule is triggered. If a product uses the _Manufacture_ route, then a _manufacturing order_ (MO) is created instead. This is the case regardless of the selected replenishment route.

Vedi anche

  * [Odoo Tutorials: Automatic Reordering Rules](https://www.youtube.com/watch?v=XEJZrCjoXaU)

  * [Odoo Tutorials: Manual Reordering Rules](https://www.youtube.com/watch?v=deIREJ1FFj4)




To set up reordering rules for the first time, refer to:

  * Reordering rules setup

  * Trigger

  * Preferred route




To understand and optimize replenishment using advanced features, see:

  * Just-in-time logic

  * Visibility days




## Reordering rules setup¶

To configure automatic and manual reordering rules, complete the following:

  1. Product type configuration

  2. Create rule




### Product type configuration¶

A product must be configured correctly to use reordering rules. Begin by navigating to Inventory app ‣ Products ‣ Products, then select an existing product, or create a new one by clicking New.

On the product form, under the General Information tab, set the Product Type to Storable Product. This is necessary because Odoo only tracks stock quantities for storable products, and quantities are needed to trigger reordering rules.

Next, click the Inventory tab and select one or more routes from the Routes section. Doing so tells Odoo which route to use to replenish the product.

If the product is reordered using the Buy route, confirm that the Can be Purchased checkbox is enabled under the product name. This makes the Purchase tab appear. Click on the Purchase tab, and specify at least one vendor, and the price that they sell the product for, so that Odoo knows which company the product should be purchased from.

If the product is replenished using the Manufacture route, it needs to have at least one _bill of materials_ (BoM) associated with it. This is necessary because Odoo only creates manufacturing orders for products with a BoM.

If a BoM does not already exist for the product, select the Bill of Materials smart button at the top of the product form, then click New to configure a new BoM.

### Create new reordering rules¶

To create a new reordering rule, navigate to Inventory app ‣ Operations ‣ Replenishment, then click New, and fill out the following fields for the new reordering rule line item:

  * Product: The product that requires replenishment.

  * Location: The specific location where the product is stored.

  * Min Quantity: The minimum amount of product that should be available. When inventory levels goes below this number, the replenishment is triggered.

  * Max Quantity: The amount of product that should be available after replenishing the product.

  * Multiple Quantity: If the product should be ordered in specific quantities, enter the number that should be ordered. For example, if the Multiple Quantity is set to `5`, and only 3 are needed, 5 products are replenished.




Suggerimento

Reordering rules can also be created from the Reordering Rules smart button on the product form.

Nota

To learn how the On Hand, Forecast, and To Order fields are calculated using on-hand quantities and future demand, see the Just-in-time logic section.

For advanced usage of reordering rules, learn about the following reordering rule fields:

  * Trigger

  * Preferred route

  * Vendor

  * Bill of materials

  * Procurement group

  * Visibility days




Nota

The fields above are not available by default, and must be enabled by selecting the __(adjust) icon in the far-right corner and selecting the desired column from the drop-down menu.

### 0/0/1 reordering rule¶

The _0/0/1_ reordering rule is a specialty rule used to replenish a product that is not kept on-hand, each time a sales order (SO) is confirmed for that product.

Importante

The 0/0/1 reordering rule is similar to the _Replenish on Order (MTO)_ route, in that both workflows are used to replenish a product upon confirmation of an SO.

The main difference between the two methods is that the _Replenish on Order_ route automatically reserves the product for the SO that caused it to be replenished. This means the product **cannot** be used for a different SO.

The 0/0/1 reordering rule does not have this limitation. A product replenished using the rule is not reserved for any specific SO, and can be used as needed.

Another key difference is that replenishment orders created by the _Replenish on Order_ route are linked to the original SO by a smart button at the top of the order. When using the 0/0/1 reordering rule, a replenishment order is created, but is not linked to the original SO.

See the [Replenish on Order (MTO)](mto.html) documentation for a full overview of the MTO route.

To create a 0/0/1 reordering rule, navigate to Inventory app ‣ Products ‣ Products, and select a product.

At the top of the product’s page, click the __ Reordering Rules smart button to open the Reordering Rules page for the product. On the resulting page, click New to begin configuring a new reordering rule.

In the Location field of the new reordering rule, select the location in which replenished products should be stored. By default, this location is set to WH/Stock.

In the Route field, select the route the rule should use to replenish the item. For example, if the product should be purchased from a vendor, select the Buy route.

In the Min Quantity field and Max Quantity field, leave the values set to `0.00`. In the To Order field, enter a value of `1.00`.

With the reordering rule configured using these values, each time an SO causes the forecasted quantity of the product to fall below the Min Quantity of `0.00`, the selected Route is used to replenish the product in one-unit increments, back up to the Max Quantity of `0.00`.

Example

A picture frame is configured with a 0/0/1 reordering rule that uses the _Buy_ route. Zero units of the picture frame are kept on-hand at any given time.

An SO is confirmed for one unit of the picture frame, which causes the forecasted quantity to drop to `-1.00`. This triggers the reordering rule, which automatically creates a PO for one unit of the picture frame.

Once the product is received from the vendor, the forecasted quantity of the picture frame returns to `0.00`. There is now one picture frame on-hand, but it is not reserved for the SO which triggered its purchase. It can be used to fulfill that SO, or reserved for a different order.

## Attivazione¶

A reordering rule’s _trigger_ can be set to _automatic_ or _manual_. While both function the same way, the difference between the two types of reordering rules is how the rule is launched:

  * Auto: A purchase or manufacturing order is automatically created when the forecasted stock falls below the reordering rule’s minimum quantity. By default, the Auto trigger is selected.

  * Manual: The [Replenishment report](report.html) lists products needing replenishment, showing current/forecasted stock, lead times, and arrival dates. Users can review forecasts before clicking _Order Once_.




To enable the Trigger field, go to Inventory app ‣ Operations ‣ Replenishment or Inventory app ‣ Configuration ‣ Reordering Rules. Then, click the __(adjust) icon, located to the far-right of the column titles, and tick the Trigger checkbox.

In the Trigger column, select Auto or Manual. Refer to the sections below to learn about the different types of reordering rules.

### Automatico¶

_Automatic reordering rules_ , enabled by setting the reordering rule’s Trigger field to Auto, generate purchase or manufacturing orders when either:

  1. The scheduler runs, and the _Forecasted_ quantity is below the minimum, or

  2. A sales order is confirmed, and lowers the _Forecasted_ quantity of the product below the minimum.




If the Buy route is selected, then an RFQ is generated. To view and manage RFQs, navigate to Purchase app ‣ Orders ‣ Requests for Quotation.

If the Manufacture route is selected, then an MO is generated. To view and manage MOs, navigate to Manufacturing app ‣ Operations ‣ Manufacturing Orders.

When no route is selected, Odoo selects the Route specified in the Inventory tab of the product form.

Suggerimento

The scheduler is set to run once a day, by default.

To manually trigger a reordering rule before the scheduler runs, ensure [developer mode](../../../../general/developer_mode.html#developer-mode) is enabled, and select Inventory app ‣ Operations ‣ Run Scheduler. Then, click the purple Run Scheduler button on the pop-up window that appears.

Be aware that this also triggers any other scheduled actions.

Example

The product, `Office Lamp`, has an automatic reordering rule set to trigger when the forecasted quantity falls below the Min Quantity of `5.00`. Since the current Forecast is `55.00`, the reordering rule is **not** triggered.

### Manuale¶

_Manual reordering rules_ , configured by setting the reordering rule’s Trigger field to Manual, list a product on the [replenishment dashboard](report.html) when the forecasted quantity falls below a specified minimum. Products on this dashboard are called _needs_ , because they are needed to fulfill upcoming sales orders, for which the forecasted quantity is not enough.

The replenishment dashboard, accessible by navigating to Inventory app ‣ Operations ‣ Replenishment, considers sales order deadlines, forecasted stock levels, and vendor lead times. It displays needs **only** when it is time to reorder items, thanks to the To Reorder filter.

When a product appears on the replenishment dashboard, clicking the Order Once button generates the purchase or manufacturing order with the specified amounts To Order.

## Percorso¶

Odoo allows for multiple routes to be selected as replenishment methods under the Inventory tab on each product form. For instance, it is possible to select both Buy and Manufacture, indicating to Odoo that the product can be bought or manufactured.

Odoo also enables users to set a preferred route for a product’s reordering rule. This is the route that the rule defaults to, if multiple are selected. To select a preferred route, begin by navigating to Inventory app ‣ Configuration ‣ Reordering Rules.

By default, the Route column is hidden on the Reordering Rules page.

Reveal the Route column by selecting the (slider) icon to the far-right of the column titles, and checking the Route option from the drop-down menu that appears.

Click inside of the column on the row of a reordering rule, and a drop-down menu shows all available routes for that rule. Select one to set it as the preferred route.

Importante

If multiple routes are enabled for a product but no preferred route is set for its reordering rule, the product is reordered using the selected route that is listed first on the Inventory tab of the product form.

### Advanced uses¶

Pairing Preferred Route with one of the following fields on the replenishment report unlocks advanced configurations of reordering rules. Consider the following:

  * Vendor: When the selected Preferred Route is Buy, setting the Vendor field to one of the multiple vendors on the vendor pricelist indicates to Odoo that the vendor is automatically populated on RFQs when a reordering rule triggers the creation of a purchase order.



  * Bill of Materials: When the Preferred Route is set to Manufacture, and there are multiple BoMs in use, specifying the desired BoM in the replenishment report, draft manufacturing orders are created with this BoM in use.



  * Procurement Group: This is a way to group related POs or MOs that are tied to fulfilling a specific demand, like an SO or a project. It helps organize and track which orders are linked to a particular demand.

Nota

Procurement groups link replenishment methods to demand, enabling smart buttons to appear when using the [MTO route](mto.html).

Sales order (demand) with a linked purchase order (replenishment method).¶

In the context of reordering rules:

    * Reordering rules do not automatically assign a procurement group, which is why there are no smart buttons that link SOs to POs, unlike the MTO route.

    * To enable smart buttons for products replenished by reordering rules (not MTO), with specific quantities linked to specific demands (e.g. SOs), assign a procurement group.

    * Without a procurement group, demands for the same product can be combined into a single RFQ, even if the reordering rule is executed multiple times for those demands. This allows for more efficient procurement by consolidating demands into fewer orders.

Selecting a procurement group in the Procurement Group field on the replenishment report ensures that all linked orders are grouped under the same demand, based on the defined route.

Exercise

How can you set the _Procurement Group_ , _Vendor_ , and _Preferred Route_ fields on the replenishment report to generate a single RFQ for five different products in sales order SO35, given they share the same vendor, Azure Interior, and ensure other demands for these products are handled separately?

View the answer

    1. Set the Procurement Group to `SO35`, in the reordering rule for all five products. This groups the demands for `SO35` in the same RFQ or MO.

    2. Set the Vendor to `Azure Interior` to ensure the RFQ is created for the same supplier.

    3. Set the Preferred Route to Buy to generate an RFQ.

    4. Click the Order Once button to generate a single RFQ for the five products tied to `SO35`.

After placing the order, remove `SO35` from the Procurement Group field of the five products” reordering rules. This ensures future demands for these products are managed separately and assigned to different RFQs (the usual behavior).




## Just-in-time logic¶

_Just-in-time logic_ in Odoo minimizes storage costs by placing orders precisely to meet deadlines. This is achieved using the forecasted date, which determines when replenishment is necessary to avoid overstocking.

The forecasted date is the **earliest possible date** to receive a product if the replenishment process starts immediately. It is calculated by summing the lead times linked to the replenishment process, such as [vendor lead times](lead_times.html#inventory-warehouses-storage-purchase-lt) and [purchasing delays](lead_times.html#inventory-warehouses-storage-purchase-security-lt) for purchases, or [manufacturing lead times](lead_times.html#inventory-warehouses-storage-manuf-lt) for production. Both automatic and manual reordering rules work this way.

Example

For a product with a 5-day total lead time and a sales order delivery date in 10 days, Odoo waits 5 days to place the order, ensuring it arrives just in time for delivery.

Important considerations:

  * **If this feels risky** , consider adding buffer time or [adjusting lead times](lead_times.html) for more flexibility.

  * While lead times and just-in-time logic provide additional control, **reordering rules work perfectly fine without them**. Keeping delivery dates on sales orders as their _creation date_ ensures purchases are immediately triggered when needed




### Forecasted date and To Order quantity¶

To view the _forecasted date_ , go to the replenishment report and click the __(info) icon for the desired reordering rule. The Replenishment Information pop-up window displays the Forecasted Date and various lead times.

The _forecasted date_ is the total time needed to procure a product in Odoo. It is calculated by summing the lead times linked to the product’s replenishment process. The total of these lead times, added to the current date, determines when Odoo checks for demanded stock.

Importante

The forecasted date is the **earliest possible date** the customer can receive the product if the replenishment process began right **now**. It is calculated by adding all lead times related to the product to the current date.

Example

A manual reordering rule is set up with no minimum or maximum quantities.

  * Vendor lead time is 4 days, the purchase security lead time is 1 day, and the days to purchase is 2 days.

  * Today’s date is November 26.

  * These add up to 7 days, making the forecasted date, December 3rd.




A confirmed SO for 5 units has a delivery date of December 3rd (7 days from today). This demand will appear on the replenishment report today, in the **To Order** field.

However, if the delivery date were later than December 3rd, it would not yet appear on the report. Odoo only displays quantities to replenish when they fall within the forecasted date window, ensuring orders are placed precisely when needed.

The _just-in-time_ logic ensures replenishment happens only when it’s necessary for the forecasted date’s demand, helping avoid overstocking.

Ad esempio:

  * If the forecasted quantity drops below the minimum **on** the forecasted date, replenishment must begin immediately to avoid shortages.

  * If the quantity drops below the minimum **after** the forecasted date, replenishment can wait.




The **To Order** quantity is the total demand on the forecasted date.

By timing purchase orders based on the combined lead times, Odoo optimizes stock levels, keeping inventory minimal while ensuring future requirements are ordered at the last possible moment—strategic procrastination without the stress!

### Common confusion about forecasted quantities¶

SOs due **after** the Forecasted Date are not accounted for in the Forecast quantities of the reordering rule.

They are, however, accounted for on the forecasted report that is opened by clicking the __(graph) icon on the replenishment report, as this one represents the **long-term forecasted quantity**.

Example

Continuing the above example, when the sales order’s deadline is adjusted to December 4th, the Forecast and To Order quantities are zero.¶

Opening the Forecasted Report shows the Forecasted units is `5.00`.¶

## Giorni di visibilità¶

_Visibility days_ enable the ability to determine if additional quantities should be added to the planned replenishment. Odoo checks if forecasted stock on the forecasted date will drop below the minimum in the reordering rule. **Only if** it is time to reorder, visibility days check additional future demand by the specified number of days.

This feature helps consolidate orders by grouping immediate and near-future needs, reducing transport costs and enabling supplier discounts for larger orders.

To set visibility days to incorporate orders for a specified number of days in the future, navigate to Inventory app ‣ Operations ‣ Replenishment, or by clicking the _Reordering Rules_ smart button from the product form.

Next, enable the Visibility Days field by clicking the __(adjust) icon to the far right and choosing the feature from the drop-down menu. Then, enter the desired visibility days.

Importante

The forecasted date is never pushed forward or extended; Odoo only checks the extra visibility days if the stock falls below the minimum threshold on the forecasted date.

### Example where visibility days is triggered¶

A product shipped from Asia has a combined vendor lead time of 30 days and a shipping cost of $100 (including [landed costs](../../product_management/inventory_valuation/landed_costs.html) and tariffs).

  * November 4: Current date. The forecasted date is December 4 (30 days later).

  * SO 1: Requires the product by Dec 4. Odoo places the order today, costing $100.

  * SO 2: Requires the product by Dec 19. Normally, Odoo would order on Nov 19, costing an additional $100.

  * SO 3: Requires the product by Dec 25. Normally, Odoo would order on Nov 25, costing another $100.




Ordering separately for these sales orders totals $300 in shipping costs.

Setting Visibility Days to `20.0` allows Odoo to «look ahead» 20 days from December 4 (SO 1’s forecasted date) to December 24.

  * It groups SO 2’s order with SO 1, reducing shipping costs by consolidating orders.

  * SO 3, which is due on Dec 25, is one day late and is not grouped with the other two orders.




### Counterexample where visibility days is not triggered¶

Considering the example above, if SO 1 does not exist, then:

  * **November 4** : Current date. The forecasted date is December 4 (30 days later).

  * **November 5** : The forecasted date shifts to December 5.

  * SO 2: Requires the product by December 19. Odoo will only trigger the order on November 19, meaning the user will not see a replenishment notification until then.




This shows that visibility days complement just-in-time logic by optimizing it to balance replenishment costs more effectively.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/inventory/warehouses_storage/replenishment/reordering_rules.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](report.html "Replenishment report") |
  * [precedente](mto.html "Replenish on order \(MTO\)") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Warehouses and storage](../../warehouses_storage.html) »
  * [Rifornimenti](../replenishment.html) »
  * Reordering rules


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
  *[RFQs]: Requests for Quotations