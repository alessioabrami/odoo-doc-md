# Call for tenders — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](purchase_templates.html "Purchase templates") |
  * [precedente](blanket_orders.html "Blanket orders") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Call for tenders



# Call for tenders¶

Sometimes, companies might want to invite vendors to submit offers for similar goods or services all at once. This helps companies select the cheapest, fastest vendors for their specific business needs.

In Odoo, this can be done by creating alternative requests for quotation (RfQs) for different vendors. Once a response is received from each vendor, the product lines from each RfQ can be compared, and a decision can be made for which products to purchase from which vendors.

Nota

Sometimes referred to as a _call for tender_ , this process is primarily used by organizations in the public sector, who are legally bound to use it when making a purchase. However, private companies can also use alternative RfQs to spend money efficiently.

## Configurazione¶

To create alternative RfQs, the _Purchase Agreements_ feature **must** be enabled in the _Purchase_ app settings. To enable the feature, navigate to Purchase app ‣ Configuration ‣ Settings. Under the Orders section, click the checkbox for Purchase Agreements.

Then, click Save to apply the change.

## Create an RfQ¶

To create a new RfQ, follow the instructions in the [Richieste di preventivo](rfq.html) documentation.

Vedi anche

[Odoo Tutorial: Purchase Basics and Your First Request for Quotation](https://www.youtube.com/watch?v=o_uI718P1Dc)

## Create alternative RfQs¶

Once a PO is created and sent to a vendor, alternative RfQs can be created for additional vendors to compare prices, delivery times, and other factors, to help make a decision for the order.

To create alternative RfQs from the original, click the Alternatives tab. Then, click Create Alternative. When clicked, a Create alternative pop-up window appears.

From this window, select an alternative vendor from the drop-down menu next to the Vendor field, to whom the alternative quotation is assigned.

Next to this, there is a Copy Products checkbox that is selected by default. When selected, the product quantities of the original RfQ are copied over to the alternative. For this first alternative quotation, leave the checkbox checked. Once finished, click Create Alternative. This opens a new RfQ form.

Since the Create Alternative checkbox was left checked, the new form is already pre-populated with the same products, quantities, and other details as the previous, original RfQ.

Nota

When the Copy Products checkbox is selected while creating an alternative quotation, additional products do **not** need to be added, unless desired.

However, if a chosen vendor is listed in the Vendor column under a specific product form included in the order, the values set on the product form carry over to the RfQ, and **must** be changed manually, if necessary.

Once ready, create a second alternative quotation by clicking the Alternatives tab, followed by Create Alternative.

This opens the Create alternative pop-up window. Once again, choose a different vendor from the drop-down menu next to Vendor. For this particular RfQ, however, _uncheck_ the Copy Products checkbox. Doing so removes all products on the new alternative RfQ, leaving it blank. The specific products which should be ordered from this particular vendor can be added in as needed.

Once ready, click Create Alternative.

Suggerimento

If an alternative quotation should be removed from the Alternatives tab, they can be individually removed by clicking on the X (remove) icon at the end of their row.

This creates a third, new RfQ. But, since the product quantities of the original RfQ were **not** copied over, the product lines are empty, and new products can be added as needed by clicking Add a product, and selecting the desired products from the drop-down menu.

Once the desired number of specific products are added, click Send by Email.

This opens a Compose Email pop-up window, wherein the message to the vendor can be customized, and attachments can be added, if necessary. Once ready, click Send.

From this newest form, click the Alternatives tab. Under this tab, all three RfQs can be seen in the Reference column. Additionally, the vendors are listed under the Vendor column, and the order Total (and Status) of the orders are in the rows, as well.

The date in the Expected Arrival column is calculated for each vendor, based on any pre-configured lead times in the vendor and product forms.

## Link new RfQ to existing quotations¶

Even if a quotation is not created directly from the Alternatives tab of another RfQ, it can still be linked to existing RfQs.

To do that, begin by creating a new RfQ. Navigate to Purchase app ‣ New. Fill out the RfQ, according to the previous instructions.

Then, once ready, click the Alternatives tab. Since this new RfQ was created separately, there are no other orders linked yet.

However, to link this RfQ with existing alternatives, click Link to Existing RfQ on the first line in the Vendor column.

This opens an Add: Alternative POs pop-up window. Select the desired previously-created RfQs, and click Select. All of these orders are now copied to this RfQ, and can be found under the Alternatives tab.

Suggerimento

If a large number of POs are being processed, and the previous POs can’t be located, click the __(chevron) icon to the right of the search bar, at the top of the pop-up window.

Then, under the Group By section, click Vendor. Vendors are displayed in their own nested drop-down lists, and each vendor’s list can be expanded to view open POs for that vendor.

## Compare product lines¶

Alternative RfQs can be compared side-by-side, in order to determine which vendors offer the best deals on the products included in the orders.

To compare alternative RfQs, navigate to the Purchase app, and select one of the previously-created RfQs.

Then, click the Alternatives tab to see all linked RfQs. Next, under the Create Alternative option, click Compare Product Lines. This navigates to the Compare Order Lines page.

The Compare Order Lines page, by default, groups by Product. Each product included in any of the RfQs is displayed in its own nested drop-down list, and features all of the PO numbers in the Reference column.

Nota

To remove product lines from the Compare Order Lines page, click Clear at the far-right end of that product line’s row.

Doing so removes this specific product as a selectable option from the page, and changes the Total price of that product on the page to `0`.

Additionally, on the RfQ form, in which that product was included, its ordered quantity is also changed to `0`.

Once the best offers have been identified, individual products can be selected by clicking the Choose button at the end of each corresponding row.

Once all desired products have been chosen, click Requests for Quotation (in the breadcrumbs, at the top of the page) to navigate back to an overview of all RfQs.

## Cancel (or keep) alternatives¶

Once the desired products have been chosen from the Compare Order Lines page, the remaining RfQs, from which no products were chosen, can be cancelled.

The cost in the Total column for each product that wasn’t chosen is automatically set to `0`, indicated at the far-right of each corresponding row.

Although they haven’t been cancelled yet, this indicates that each of those orders can be cancelled without having an effect on the other live orders, once those orders have been confirmed.

To confirm an RfQ for which products were selected, click into an RfQ, and click Confirm Order.

This causes a What about the alternative Requests for Quotations? pop-up window to appear.

To view a detailed form of one of the RfQs listed, click the line item for that quotation. This opens an Open: Alternative POs pop-up window, from which all details of that particular RfQ can be viewed.

Once ready, click Close to close the pop-up window.

In the What about the alternative Requests for Quotations? pop-up window, two options are presented: Cancel Alternatives and Keep Alternatives.

If this PO should **not** be confirmed, click Discard.

Selecting Cancel Alternatives automatically cancels the alternative RfQs. Selecting Keep Alternatives keeps the alternative RfQs open, so they can still be accessed, if any additional product quantities need to be ordered later.

Once all products are ordered, select Cancel Alternatives from whichever PO is open at that time.

Finally, using the breadcrumbs at the top of the page, click Requests for Quotation to navigate back to an overview of all RfQs.

The cancelled orders can be seen, greyed out and listed with a Cancelled status, under the Status column at the far-right of their respective rows.

Now that all product quantities have been ordered, the purchase process can be completed, and the products can be received into the warehouse.

Vedi anche

[Blanket orders](blanket_orders.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/inventory_and_mrp/purchase/manage_deals/calls_for_tenders.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](purchase_templates.html "Purchase templates") |
  * [precedente](blanket_orders.html "Blanket orders") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Call for tenders


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
  *[EDI]: Electronic Data Exchange
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
  *[FBM]: Fulfilled by Merchant
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
  *[JIT]: just-in-time