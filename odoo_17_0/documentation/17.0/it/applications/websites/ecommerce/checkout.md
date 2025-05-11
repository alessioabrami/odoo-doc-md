# Check-out — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments.html "Fornitori di pagamento") |
  * [precedente](cart.html "Aggiungi al carrello") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Check-out



# Check-out¶

You can customize the **checkout steps** , add more content using the **website builder** , and enable additional features such as **express checkout** and **sign in/up at checkout**.

You can use **building blocks** to add content at any step of the checkout process. To do so, from any **checkout page** , go to Edit ‣ Blocks, and drag and drop **building blocks** to the page.

Nota

Note that content added through building blocks is **specific** to each step.

## Checkout steps¶

### Review order: promo code (and subtotal)¶

If you have enabled Discounts, Loyalty, & Gift Card in the settings (Website ‣ Configuration ‣ Settings ‣ Shop - Products), you can enable the Promo Code field (Edit ‣ Customize) from any checkout page. Customers can then redeem gift cards and promotional codes at the Review Order step.

Furthermore, you can display the subtotal with discounts applied by enabling Show Discount in Subtotal.

### Address: B2B fields¶

Optional TIN/VAT and Company Name fields can be added to the Billing Address form for B2B customers, at the Address step. To add the fields, go to Edit ‣ Customize from any checkout page, and enable Show B2B fields.

### Request extra info (additional step)¶

You can request Extra Info from the customer by adding an Extra Info step between the Address and Confirm Order steps. To do so, go to Edit ‣ Customize from any checkout page, and enable Extra Step Option.

The Extra Info step is an online form linked to the quotation or sales order of the customer. The information added during that step can be found on the quotation or sales order of the customer from the back end, in the **Sales** app.

When enabled, you can remove, add, and modify fields of the form by clicking on Edit in the top-right corner, and then clicking on any of the form’s fields. All customization options, as well as the \+ Field button to add new fields, are available at the bottom of the Customize menu under the Field section.

### Confirm order: terms and conditions¶

You can ask customers to agree to the Terms & Conditions in order to confirm their order by enabling Accept Terms & Conditions under Edit ‣ Customize on any checkout page.

## Express checkout¶

You can enable a Buy Now button on products” pages which instantly takes the customer to the Confirm Order checkout page, instead of adding the product to the cart. To do so, go to Website ‣ Configuration ‣ Settings ‣ Shop - Checkout Process section and tick Buy Now. Alternatively, the Buy Now button can also be enabled from any product’s page by going Edit ‣ Customize, in the Cart section.

The button can be found next to the Add to Cart button on the product’s page.

## Guest and signed-in checkout¶

It is possible to introduce a **checkout policy** under which customers can either checkout as **guests** or **signed-in users only**. Customers can also checkout as guest, and **optionally sign up later** in order to track their order, if enabled.

To select a policy, go to Website ‣ Configuration ‣ Settings ‣ Shop - Checkout Process. You can choose between:

  * Optional: allows guests to checkout and later register from the **order confirmation** email to track their order;

  * Disabled (buy as guest): customers can only checkout as guests;

  * Mandatory (no guest checkout): customers can only checkout if they have signed-in.




Vedi anche

  * [Customer accounts](customer_accounts.html)

  * [Accedere al portale](../../general/users/portal.html)




### B2B access restriction¶

If you wish to restrict checkout only to **selected B2B customers** , enable Mandatory (no guest checkout) and go to Website ‣ eCommerce ‣ Customers. Select the customer you wish to **grant access to** , click Action ‣ Grant portal access, and click Grant Access.

Suggerimento

Settings are **website-specific** , which means you can set up a B2C website allowing **guest** checkout, and another for B2B customers with **mandatory sign-in**.

Nota

Users can only have one portal access per **email**. They _cannot_ be granted access to two different portals with the same **email address**.

### Shared customer accounts¶

If you enable Shared Customer Accounts under Website ‣ Configuration ‣ Settings ‣ Privacy section, you can allow or disallow access to _all_ websites for one same account.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/ecommerce/checkout.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments.html "Fornitori di pagamento") |
  * [precedente](cart.html "Aggiungi al carrello") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Check-out


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
  *[CSV]: Valori separati da virgola
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement