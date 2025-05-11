# Fatture fornitore — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_bills/invoice_digitization.html "AI-powered document digitization") |
  * [precedente](customer_invoices/incoterms.html "Termini di resa") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture fornitore



# Fatture fornitore¶

Vendor bills can be registered either **manually** or **automatically** in Odoo. The Aged Payable report provides an overview of all outstanding bills to help ensure timely payment of the correct amounts.

Vedi anche

  * Tutorial [Registering a vendor bill](https://www.odoo.com/slides/slide/register-a-vendor-bill-6582)

  * [Manage vendor bills](../../inventory_and_mrp/purchase/manage_deals/manage.html)

  * [Note di credito e rimborsi](customer_invoices/credit_notes.html)




## Bill creation¶

### Manuale¶

To create a vendor bill manually, go to Accounting ‣ Vendors ‣ Bills and click New.

Suggerimento

Alternatively, it is possible to create a vendor bill from the Accounting dashboard:

  * either click New on the Vendor Bills journal;

  * or click the __(vertical ellipsis) icon of the Vendor Bills journal, then Bill under the New section.




### Automaticamente¶

Vendor bills can be automatically created through various methods:

  * Emailing to an [email alias](vendor_bills/invoice_digitization.html#invoice-digitization-email-alias) associated with the purchase journal. If the email does not contain a valid file, an automatic response notifies the sender that no document was received.

  * Uploading a PDF: To upload a bill, go to Accounting ‣ Vendors ‣ Bills, then click Upload.




Nota

  * Once the bill is uploaded, the PDF document appears on the right side of the screen, making it easy to fill in the bill information.

  * Bills can be [digitized](vendor_bills/invoice_digitization.html) for automatic completion.

  * Services such as digitizing scanned or PDF vendor bills in Odoo require [In-App Purchase (IAP)](../../essentials/in_app_purchase.html) credits.




To automatically post bills from selected vendors, go to Accounting ‣ Vendors ‣ Vendors and select the relevant vendor. In the Accounting tab, under the Automation section, update the Auto-post bills field with one of the following options:

  * Always

  * Ask after 3 validations without edits

  * Never




## Bill completion¶

Whether the bill is created manually or automatically, make sure the following fields are appropriately completed:

  * Vendor: Odoo automatically fills in some information based on the information on the vendor’s contact record as well as previous purchase orders and bills.

  * Bill Reference: Add the sales order reference provided by the vendor. This field is used to [match](payments.html#accounting-payments-payments-matching) the products when they are received.

  * Auto-Complete: Select a past bill/purchase order to complete the document automatically. The Vendor field should be completed before completing this field.

  * Bill Date: Select the document’s issuance date.

  * Accounting Date: Update the document’s accounting registration date if needed.

  * Payment Reference: The Memo field automatically includes the payment reference once the payment is registered.

  * Recipient Bank: Indicates the account number to which the payment will be made. This field is required when paying via batch payment files (such as [NACHA](../fiscal_localizations/united_states.html#l10n-us-ach-electronic-transfers) and [SEPA](payments/pay_sepa.html)).

  * Due Date or Payment Terms must be specified for the bill payment.

  * Journal: Select which journal should record the bill and in which [currency](get_started/multi_currency.html).




Nella scheda Righe fattura:

  * Prodotto: fai clic su Aggiungi riga, poi cerca e seleziona il prodotto.

  * Quantità

  * Prezzo

  * [Imposte](taxes.html) (se applicabile)




Suggerimento

If the bill line does not correspond to an existing product in the database, click the __(bars) icon to enter a description for the bill line without linking it to a product.

To access the product catalog and view all items in an organized display, click [Catalog](../../inventory_and_mrp/inventory/warehouses_storage/inventory_management/product_catalog.html). When the products and quantities are selected, click Back to Bill to return to the vendor bill; the selected catalog items will appear in the vendor bill lines.

Nota

Multiple bills for the same purchase order may be issued if the vendor is on back-order and sends invoices as products are shipped or if the vendor sends partial bills or requests a deposit. In this case, multiple bills may have the same Bill Reference.

## Bill confirmation¶

Click Confirm when the document is completed. The status changes to Posted, and a journal entry is generated based on the vendor bill information. On confirmation, Odoo assigns each vendor bill a unique number from a defined [sequence](vendor_bills/sequence.html).

Nota

Once confirmed, a vendor bill can no longer be updated. Click Reset to draft if changes are required.

## Pagamento e riconciliazione¶

To register a payment, click on Pay. In the Pay window, select the Journal, the Payment Method, the Amount, and the Currency.

When the Amount paid is less than the total remaining amount on the vendor bill, the payment is [partial](payments.html#accounting-payments-partial-payment), and the Payment Difference field displays the outstanding balance.

The Memo field is filled automatically if the Payment Reference has been set correctly on the vendor bill. If the field is empty, select the vendor invoice number as a reference.

Then click Create payment. An In Payment/Partial banner appears on the bill until it is [reconciled](bank/reconciliation.html) and its status updates to Paid.

Vedi anche

  * [Pagamenti](payments.html)

  * [Riconciliazione bancaria](bank/reconciliation.html)




## Aged payable report¶

To get an overview of the open vendor bills and their due dates, go to Accounting ‣ Reporting ‣ Aged payable.

Click the __(right arrow) icon next to a vendor to view the details of all their outstanding bills, including the due dates and amounts.

Nota

Click PDF or XLSX to generate a PDF or XLSX file, respectively.

  * [AI-powered document digitization](vendor_bills/invoice_digitization.html)
  * [Non-current assets and fixed assets](vendor_bills/assets.html)
  * [Deferred expenses](vendor_bills/deferred_expenses.html)
  * [Vendor bill sequence](vendor_bills/sequence.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/vendor_bills.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_bills/invoice_digitization.html "AI-powered document digitization") |
  * [precedente](customer_invoices/incoterms.html "Termini di resa") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture fornitore


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[API]: application programming interfaces
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
  *[POS]: point of sale
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