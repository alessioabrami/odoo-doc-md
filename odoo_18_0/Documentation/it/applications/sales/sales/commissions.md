# Commissione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](amazon_connector.html "Integrazione con Amazon") |
  * [precedente](products_prices/loyalty_discount.html "Discount and loyalty programs") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Commissione



# Commissione¶

Commissions are a powerful tool to motivate sales team members. They incentivize performance, boost productivity, and encourage healthy competition. The _Commissions_ feature in Odoo’s **Sales** application provides a way to reward salespeople or sales teams based on their performance. This feature supports the creation of flexible, measurable commission structures that align with business goals, whether that means driving revenue, volume, profit, or recurring contracts.

## Configurazione¶

To enable the _Commissions_ feature, navigate to Sales app ‣ Configuration ‣ Settings. Scroll to the Invoicing section, and tick the Commissions checkbox. Then, click Save. Doing so causes a new Commissions menu to appear in the menu bar. To create a new commission plan, navigate to Commissions ‣ Comission Plans and click New.

## Commission plan structure¶

Each commission plan is comprised of several components:

  * Based on: Determines whether commissions are awarded based on progress toward Targets or Achievements

  * per: Indicates whether the plan applies to individual salespeople or an entire sales team

  * Target Frequency: Sets how often targets reset: **Monthly** , **Quarterly** , or **Yearly**.

  * Achievements: Determines what is being measured toward commissions.




### Target-based commission plans¶

In a _Target_ based commission plan, commissions are awarded based on the percentage of sales targets reached. Target based plans are ideal for setting clear, measurable goals, such as invoicing a specific amount in sales per quarter, then rewarding sales people progressively based on how close they come to reaching or exceeding that goal.

Suggerimento

Target based plans differ from _Achievement_ based plans because they are based on reaching a fixed, predefined goal. They focus on goal-based incentives and performance milestones.

To configure a new target based commission plan, navigate to the Sales app ‣ Commissions ‣ Commission Plans, then click New. Click in the Based on drop-down menu and select Targets. Then, select an option in the per field.

In the On Target Commission field, set the payout amount for reaching `100%` of the target. Update the Effective Period fields to confirm the dates for this plan. Then, update the Target Frequency field based on how often the targets should be set and evaluated.

  * _Monthly_ : short term goals with frequent payouts.

  * _Quarterly_ : aligns with business cycles and provides mid-range objectives.

  * _Yearly_ : long term sales goals for strategic planning.




After the Target Frequency field is updated, the Targets tab updates with a list of the appropriate time frame. For each Period, enter a Target goal.

On the Achievements tab, add one or more Achievement metric for this plan by clicking Add a new achievement.

Click the Sales People tab to assign this plan to the appropriate staff. Click either Add a new Sales Person to add them individually, or Add Multiple Salespersons to bulk add several at once.

Nota

The Add Multiple Salespersons button is only available if [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html) is active.

### Livelli¶

To provide additional incentive, _commission levels_ can be added to _Target_ based plans. These tiers allow salespeople to earn varying commission amounts based on their performance levels. Levels can start at `0%` and increase incrementally. This allows for salespeople to earn commission even if they do not achieve `100%` of the target, as well as the ability to achieve over `100%` of the target. Commission levels can be set from the Commissions tab when creating a commission plan.

If no levels are added above 100%, salespeople are **not** able to earn above the stated commission.

Example

In the plan below, the levels start at `0%`, and continue until `300%`. If a salesperson exceeds `100%` of the expected target, their expected payout continues to increase up to `300%`.

### Achievement-based commission plans¶

In a _Achievement_ based commission plan, salespeople earn a percentage of their invoice value as commission. Target based plans are ideal for rewarding sales activity consistently, regardless of specific goals. For example, offering a `5%` commission on all invoiced amounts, regardless of how much is sold.

Suggerimento

Achievement based plans differ from _Target_ based plans because they are calculated based on actual achievements using a flat, consistent rate. They are beneficial for ongoing, non-goal based compensation plans.

To configure a new target based commission plan, navigate to the Sales app ‣ Commissions ‣ Commission Plans, then click New. Click in the Based on drop-down and select Achievements. Then, select an option in the per field.

Update the Effective Period fields to confirm the dates for this plan. Then, update the Target Frequency field based on how often the targets should be set and evaluated.

On the Achievements tab, add one or more Achievement metric for this plan by clicking Add a new achievement.

Click the Sales People tab to assign this plan to the appropriate staff. Click either Add a new Sales Person to add them individually, or Add Multiple Salespersons to bulk add several at once.

### Traguardi¶

Performance can be measured in several ways in performance plans. These are configured in the Achievements tab of each plan.

  * Amount Sold: the total value of sales orders (SOs).

  * Amount Invoiced: the total value of confirmed invoices.

  * Quantity Sold: the total number of units sold via SOs.

  * Quantity Invoiced: the total number of units invoiced.

  * Margin: the profit margin (selling price minus cost price).

  * MRR: the new _Monthly Recurring Revenue_ from subscription sales. this option is **only** available if the [Subscriptions](../subscriptions.html) app is installed.




Nota

Regardless of what the plan is Based on, each plan needs both _Achievements_ and _Targets_ configured.

## Plan approval¶

After confirming the details of the new plan, click Approve. This moves the plan from the Draft stage into the Approved stage.

Importante

Commissions plans in the Approved stage **cannot** be edited. To edit an approved plan, it must first be Reset to Draft.

After a plan is approved, Odoo automatically tracks performance and calculates commissions based on the established parameters.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/commissions.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](amazon_connector.html "Integrazione con Amazon") |
  * [precedente](products_prices/loyalty_discount.html "Discount and loyalty programs") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Commissione


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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