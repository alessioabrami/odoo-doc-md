# Blanket orders — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](calls_for_tenders.html "Call for tenders") |
  * [precedente](rfq.html "Richieste di preventivo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Blanket orders



# Blanket orders¶

Blanket orders are long-term purchase agreements between a company and a vendor to deliver products on a recurring basis with predetermined pricing.

Blanket orders are helpful when products are consistently purchased from the same vendor, but in different quantities, and at different times.

By simplifying the ordering process, blanket orders not only save time, they also save money, since they can be advantageous when negotiating bulk pricing with vendors.

## Create a new blanket order¶

To create blanket orders, enable the _Purchase Agreements_ feature from the _Purchase_ app settings. Navigate to Purchase app ‣ Configuration ‣ Settings, and under the Orders section, click the checkbox for Purchase Agreements. Then click Save to implement the changes.

Nota

In addition to creating blanket orders, the _Purchase Agreements_ setting also allows users to create alternative requests for quotation (RfQs).

To create a blanket order, go to Purchase app ‣ Orders ‣ Blanket Orders, and click New. This opens a new blanket order form.

Configure the following fields in the new blanket order form to establish predetermined rules for the recurring long-term agreement:

  * Purchase Representative: the user assigned to this specific blanket order. By default, this is the user who created the agreement; the user can be changed directly from the drop-down menu next to this field.

  * Agreement Type: the type of purchase agreement this blanket order is classified as. In Odoo, blanket orders are the only official purchase agreement.

  * Vendor: the supplier to whom this agreement is tied, either once or on a recurring basis. The vendor can be selected directly from the drop-down menu next to this field.

  * Currency: the agreed-upon currency to be used for this exchange. If multiple currencies have been activated in the database, the currency can be changed from the drop-down menu next to this field.

  * Agreement Deadline: the date that this purchase agreement will be set to expire on. If this blanket order should not expire, leave this field blank.

  * Ordering Date: the date that this blanket order should be placed on if a new quotation is created directly from the blanket order form. If a new quotation is created, this value automatically populates the _Order Deadline_ field on the RfQ.

  * Delivery Date: the expected delivery date that the products included in an RfQ are expected, if created directly from a blanket order form. If a new quotation is created, this value automatically populates the _Expected Arrival_ field on the RfQ.

  * Source Document: the source purchase order (PO) that this blanket order is tied to. If this blanket order should not be tied to any existing PO, leave this field blank.

  * Company: the company assigned to this specific blanket order. By default, this is the company that the user creating the blanket order is listed under. If the database is not a multi-company database, this field **cannot** be changed, and defaults to the only company listed in the database.




Once all relevant fields have been filled out, click Add a line to add products under the Product column. Then, in the Quantity column, change the quantity of each product, and set a price in the Unit Price column.

Importante

When adding products to a new blanket order, the pre-existing prices of products are not automatically added to the product lines. Instead, the prices **must** be manually assigned, by changing the value in the Unit Price column to an agreed-upon price with the listed vendor. Otherwise, the price will remain `0`.

To view and change the default purchase agreement settings for blanket orders directly from the blanket order form, click the ➡️ (right arrow) icon that becomes visible when hovering over the Agreement Type field, where Blanket Order is listed. This navigates to the blanket order settings.

From here, the settings for blanket orders can be edited. Under the Agreement Type section, the name of the Agreement Type can be changed, and the Agreement Selection Type can be changed, as well. There are two options that can be activated for the type of selection:

  * Select only one RfQ (exclusive): when a purchase order is confirmed, the remaining purchase orders are canceled.

  * Select multiple RfQ (non-exclusive): when a purchase order is confirmed, remaining purchase orders are **not** canceled. Instead, multiple purchase orders are allowed.




Under the Data For New Quotations section, the Lines and Quantities fields can be edited. Doing so sets how new quotations should be populated when using this purchase agreement.

There are two options that can be activated for Lines:

  * Use lines of agreement: when creating a new quotation, the product lines pre-populate with the same products listed on the blanket order, if said blanket order is chosen for the new quotation.

  * Do not create RfQ lines automatically: when creating a new quotation, **and** selecting an existing blanket order, the settings carry over to the new quotation, but the product lines do **not** populate.




And, there are two options that can be activated for Quantities:

  * Use quantities of agreement: when creating a new quotation, the product quantities listed on the blanket order pre-populate on the product lines, if said blanket order is chosen for the new quotation.

  * Set quantities manually: when creating a new quotation, **and** selecting an existing blanket order, the product lines pre-populate, but all quantities are set to `0`. The quantities **must** be manually set by the user.




Once any desired changes have been made, click New (via the breadcrumbs, at the top of the page) to navigate back to the blanket order form. Then, click Confirm to save this new purchase agreement.

Once confirmed, the blanket order’s stage (in the upper-right corner) changes from Draft to Ongoing, meaning this agreement can be selected and used when creating new RfQs.

Suggerimento

After creating and confirming a blanket order, products, quantities, and prices can still be edited, added, and removed from the purchase agreement.

## Create a new RfQ from the blanket order¶

After confirming a blanket order, new quotations can be created directly from the blanket order form. RfQs using this form are pre-populated with information based on the rules set in the form. Additionally, new quotations are automatically linked to this blanket order form, via the RFQs/Orders smart button at the top-right of the form.

To create a new quotation from the blanket order form, click the New Quotation button. This opens a new RfQ, that is pre-populated with the correct information, depending on the settings configured on the blanket order form.

From the new RfQ form, click Send by Email to compose and send an email to the listed vendor. Click Print RFQ to generate a printable PDF of the quotation; or, once ready, click Confirm Order to confirm the PO.

Once the PO has been confirmed, click back to the blanket order form (via the breadcrumbs, at the top of the page). From the blanket order form, there is now one RfQ listed in the RFQs/Orders smart button at the top-right of the form. Click the RFQs/Orders smart button to see the PO that was just created.

## Rifornimenti¶

Once a blanket order is confirmed, a new vendor line is added under the Purchase tab of the products included in the order.

This makes blanket orders useful with [automated replenishment](../products/reordering.html), because information about the Vendor, Price, and the Agreement are referenced on the vendor line. This information dictates when, where, and at what price the product should be replenished.

Vedi anche

[Call for tenders](calls_for_tenders.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/manage_deals/blanket_orders.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](calls_for_tenders.html "Call for tenders") |
  * [precedente](rfq.html "Richieste di preventivo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Blanket orders


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
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
  *[RFQs]: Requests for Quotations
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure