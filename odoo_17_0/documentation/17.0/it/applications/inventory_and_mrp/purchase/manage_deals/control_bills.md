# Bill control policies — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Manage vendor bills") |
  * [precedente](calls_for_tenders.html "Call for tenders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Bill control policies



# Bill control policies¶

In Odoo’s _Purchase_ app, the _bill control_ policy determines the quantities billed by vendors on every purchase order (PO), for either ordered or received quantities.

The policy selected in the _Purchase_ app settings acts as the default value, and is applied to any new product created.

## Configurazione¶

To configure the _bill control_ policy, navigate to Purchase app ‣ Configuration ‣ Settings, and scroll down to the Invoicing section. Under Bill Control, select either Ordered quantities or Received quantities. Then, click Save.

  * Ordered quantities: creates a vendor bill as soon as a PO is confirmed. The products and quantities in the PO are used to generate a draft bill.

  * Received quantities: a bill is created only _after_ part of the total order has been received. The products and quantities received are used to generate a draft bill. An error message appears if creation of a vendor bill is attempted without receiving anything.




Nota

If a specific product should use a different control policy than selected in the _Purchase_ app settings, the Bill Control policy for that product can be changed from its product form.

To do that, navigate to Purchase app ‣ Products ‣ Products, and select a product. From the product form, click the Purchase tab. Under the Vendor Bills section, modify the selection in the Control Policy field.

## Corrispondenza a tre vie¶

The _3-way matching_ feature ensures vendor bills are only paid once some (or all) of the products included in the PO have been received.

To activate _3-way matching_ , navigate to Purchase app ‣ Configuration ‣ Settings, and scroll down to the Invoicing section. Then, tick the checkbox for 3-way matching to enable the feature, and click Save.

Importante

The 3-way matching feature **only** works with the Bill Control policy set to Received quantities.

### Pay vendor bills with 3-way matching¶

When _3-way matching_ is enabled, vendor bills display a Should Be Paid field under the Other Info tab. When a new vendor bill is created, the field is set to Yes, since a bill **cannot** be created until at least some of the products included in a PO have been received.

To create a vendor bill from a PO, navigate to Purchase app ‣ Orders ‣ Purchase Orders. From the Purchase Orders page, select the desired PO from the list. Then, click Create Bill. Doing so opens a new draft Vendor Bill form, in the Draft stage. Click the Other Info tab, and locate the Should Be Paid field.

Importante

The PO selected from the list **must not** be billed yet, or an Invalid Operation pop-up window appears. This occurs for POs with a Received quantities policy, and a Fully Billed Billing Status.

Click the drop-down menu next to Should Be Paid to view the available options: Yes, No, and Exception.

Nota

If the total quantity of products from a PO has not been received, Odoo only includes the products that _have_ been received in the draft vendor bill.

Draft vendor bills can be edited to increase the billed quantity, change the price of the products in the bill, and add additional products to the bill.

If the draft bill’s information is changed, the Should Be Paid field status is set to Exception. This means that Odoo notices the discrepancy, but does not block the changes or display an error message, since there might be a valid reason for making changes to the draft bill.

To process the vendor bill, select a date in the Bill Date field, and click Confirm, followed by Register Payment.

This opens a Register Payment pop-up window. From this window, accounting information is pre-populated based on the database’s accounting settings. Click Create Payment to process the vendor bill.

Once payment has been registered for a vendor bill, and the bill displays the green Paid banner, the Should Be Paid field status is set to No.

Suggerimento

The Should Be Paid status on bills is automatically set by Odoo. However, the status can be manually changed by clicking the field’s drop-down menu inside the Other Info tab.

## View a purchase order’s billing status¶

Once a PO is confirmed, its Billing Status can be viewed under the Other Information tab on the PO form.

To view the Billing Status of a PO, navigate to Purchase app ‣ Orders ‣ Purchase Orders, and select a PO to view.

Click the Other Information tab, and locate the Billing Status field.

The table below details the different values the Billing Status field could read, and when they are displayed, depending on the _Bill Control_ policy used.

Stato fatturazione | Su quantità ricevute | Su quantità ordinate  
---|---|---  
Nulla da fatturare | PO confirmed; no products received | _Not applicable_  
In attesa di fatturazione | All/some products received; bill not created | PO confirmed  
Completamente fatturato | All/some products received; draft bill created | Draft bill created  
  
Vedi anche

[Manage vendor bills](manage.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/purchase/manage_deals/control_bills.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](manage.html "Manage vendor bills") |
  * [precedente](calls_for_tenders.html "Call for tenders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Acquisti](../../purchase.html) »
  * [Manage deals](../manage_deals.html) »
  * Bill control policies


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