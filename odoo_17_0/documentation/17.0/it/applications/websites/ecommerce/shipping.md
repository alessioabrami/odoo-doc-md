# Spedizione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](order_handling.html "Order handling") |
  * [precedente](payments.html "Fornitori di pagamento") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Spedizione



# Spedizione¶

Odoo eCommerce allows you to configure various shipping methods, enabling customers to choose their preferred option at checkout. These methods include external providers, custom options such as flat-rate or free shipping, local carriers via [Sendcloud](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping.html) or [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-rules), and in-store pickup.

## External provider integration¶

To handle product delivery, you can connect your database to [third-party shipping carriers](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html) like [FedEx](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/fedex.html), [UPS](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/ups_credentials.html), or [DHL](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dhl_credentials.html). A shipping connector links to these providers, automating [tracking labels](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/labels.html) and shipping processes.

To enable a third-party shipping provider, go to Website ‣ Configuration ‣ Settings, scroll to the Shipping section, select the desired shipping provider(s), and Save.

Go to Website ‣ Configuration ‣ Shipping Methods and select the shipping method in the list to [configure it](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method).

Vedi anche

[Third-party shipping carriers](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html)

Importante

The field used to define additional fees **must** be filled **in your third-party shipping provider account** , even if you do not plan to charge customers any additional fee. If you do not want to apply a fee, enter `0`. If the field is left empty, the delivery price cannot be calculated, and an error message prompts the customer to select an alternative shipping method.

### Margin on delivery rate¶

To add an additional fee to the base shipping rate (e.g., to cover extra costs), log into your carrier account and set the desired fee in the related field. The shipping connector retrieves this fee and includes it in the final price at checkout. Contact your carrier for further assistance with this configuration.

Alternatively, enter `0` in your third-party shipping provider account, then set the fee in Odoo. To do so, access the desired [shipping method’s form](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) and enter the fee in the Margin on Rate field to add a percentage to the shipping costs and/or the Additional margin field to add a fixed amount.

Importante

The field used to define additional fees cannot be left empty in your third-party shipping provider account.

## Custom shipping method¶

Custom shipping methods must be created, for example:

  * to integrate shipping carriers through [Sendcloud](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping.html);

  * to configure specific rules (e.g., to offer free shipping for orders above a specific amount) for a specific provider;

  * to configure [Fixed Price](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-fixed) shipping or shipping [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-rules).




To create a custom shipping method, go to Website ‣ Configuration ‣ Shipping Methods, click New and fill in the [fields](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-shipping-methods-details).

In the Provider field, select [Based on Rules](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-rules), [Fixed Price](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-fixed), or [Pickup in store](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration.html#inventory-shipping-pickup) if the shiping method does not involve any specific provider.

Suggerimento

Upon [configuring](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) a shipping method, you can:

  * restrict it [to a specific website](../website/configuration/multi_website.html) by selecting it in Website field;

  * use the Destination availability tab to filter the delivery carriers displayed based on the customer’s area;

  * click the Test Environment smart button to switch to the Production Environment, then click Unpublished to Publish the shipping method and make it available to website visitors.




## In-store pickup¶

To allow customers to reserve products online and pay for/collect them in person at the store, go to Website ‣ Configuration ‣ Settings, scroll to the Shipping section, enable On Site Payments & Picking, and Save.

Then, click Customize Pickup Sites, select the shipping method or click New to create a new one and [configure](../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/third_party_shipper.html#inventory-shipping-receiving-configure-delivery-method) the fields. Make sure the Provider field is set to Pickup in store.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/websites/ecommerce/shipping.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](order_handling.html "Order handling") |
  * [precedente](payments.html "Fornitori di pagamento") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Spedizione


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