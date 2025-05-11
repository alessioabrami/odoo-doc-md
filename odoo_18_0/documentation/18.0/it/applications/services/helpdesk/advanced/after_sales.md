# After-Sales services — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](close_tickets.html "Close tickets") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * After-Sales services



# After-Sales services¶

_After-Sales_ services can be configured in the **Helpdesk** application for individual teams. Once enabled, users can issue refunds, generate coupons, process returns, and schedule repairs or field service interventions directly from a ticket.

## Set up after-sales services¶

Start by enabling the after-sales services on a specific **Helpdesk** team, by going to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and click on the team the services should be applied to. Then, scroll to the After-Sales section on the team’s settings page, and choose which of the following options to enable:

  * Refunds: issues credit notes to refund a customer, or adjust the remaining amount due.

  * Coupons: offers discounts and free products through an existing coupon program.

  * Returns: initiates a product return from a customer through a reverse transfer.

  * Repairs: creates repair orders for broken or faulty products.

  * Field Service: plans onsite intervention through the **Field Service** application.




The services that are enabled can vary based on the type of support a team provides.¶

Pericolo

Since all the after-sales services in Odoo require integration with other applications, enabling any of them may result in the installation of additional modules or applications. Installing a new application on a One-App-Free database triggers a 15-day trial. At the end of the trial, if a paid subscription has not been added to the database, it will no longer be accessible.

## Issue refund with credit note¶

A _credit note_ is a document issued to a customer informing them that they have been credited a certain amount of money. They can be used to provide a full refund to a customer, or to adjust any remaining amount due. While they are usually created through the **Accounting** or **Invoicing** applications, they can be created through a **Helpdesk** ticket, as well.

Importante

Invoices **must** be posted before a credit note can be generated.

To create a credit note, navigate to a ticket on the Helpdesk app, and click the Refund button in the top-left corner of the ticket form. This opens a Refund pop-up window.

Fill out the fields with the necessary information:

>   * Sales Order: if a sales order was referenced on the original ticket, it automatically populates in this field.
> 
>   * Product: the product the ticket is about. If an item is selected in this field, only the sales orders, deliveries, and invoices including this product can be selected.
> 
>   * Lot/Serial Number: this field is **only** visible if the Product selected has associated lot or serial numbers.
> 
>   * Invoices to Refund: this field is **required**. If no invoices are available in the drop-down, it indicates this customer currently has no posted invoices, or the Product has no related invoices.
> 
>   * Reason displayed on Credit Note: this field automatically populates with the ticket number, though it can be edited with additional information.
> 
>   * Journal: the accounting journal where the credit note should be posted. After an invoice is selected, this field defaults to the journal listed on the original invoice, though it can be changed, if necessary.
> 
>   * Reversal date: when this field is clicked, use the pop-up calendar that appears to select a date for the credit note invoice. This field is **required**.
> 
> 


After the necessary fields are filled in, click Reverse or Reverse and Create Invoice.

Reverse creates a credit note in a draft state that can be edited before it is posted. This option can be used to provide a partial refund.

Reverse and Create Invoice creates a credit note that is automatically posted as well as an invoice in a draft state. The invoice contains the same information as the original invoice, though this information can be altered.

Once the credit note has been posted, a Credit Notes smart button is added to the **Helpdesk** ticket.

Vedi anche

[Note di credito e rimborsi](../../../finance/accounting/customer_invoices/credit_notes.html)

## Generate coupons from a ticket¶

Coupons can be used to alter the price of products or orders. Conditional rules define the usage constraints of a coupon. _Coupon Programs_ are configured in the **Sales** , **Point of Sale** , or **Website** applications.

Importante

The **eCommerce** module **must** be installed to create coupon codes from the **Website**.

To generate a coupon, open a **Helpdesk** ticket and click on the Coupon button in the top-left corner. Select an option from the Coupon Program drop-down menu in the Generate a Coupon pop-up window that appears.

Nota

> To create a new Coupon Program, navigate to Sales app ‣ Products ‣ Discount & Loyalty and click New. To make the program available to share with **Helpdesk** customers, the Program Type **must** be set to Coupons. This generates single-use coupon codes that grant immediate access to rewards and discounts.

Coupon programs can also be created in the **Point of Sale** or **Website** applications. Refer to [discount and loyalty programs](../../../sales/sales/products_prices/loyalty_discount.html) for more information.

Click on the Valid Until field, and use the pop-up calendar to select an expiration date for this coupon code. If this field is left blank, the code does **not** expire.

Click Send by Email to compose an email to send to the customer with the coupon code.

Click Get Share Link to generate a link to send directly to the customer. Doing so opens a Share Coupons pop-up window. Click the Copy button next to the Share Link field and paste the results to any communication with the customer. When the customer uses the link, the code is automatically applied to their cart.

After a Coupon Code has been generated, a Coupons smart button is added to the top of the ticket; click the smart button to view the coupon code, expiration date, and additional information.

Vedi anche

  * [Coupons](https://www.youtube.com/watch?v=KW5cZHg10jQ)

  * [Discount and loyalty programs](../../../sales/sales/products_prices/loyalty_discount.html)




## Return products¶

Returns are completed through _reverse transfers_ , which generate new warehouse operations for the returning products. Click the Return button at the top of a ticket to open the Return pop-up window.

Importante

The Return button **only** appears on a ticket if the customer has a recorded delivery in the database.

Select a Sales Order or Delivery to Return to identify the products that need to be returned.

By default, the quantity matches the validated quantity from the delivery order. Update the Quantity field, if necessary. To remove a line, click the __(trash) icon.

Select a Return Location where the items should be directed after the return is completed.

To confirm the return, click Return. This generates a new warehouse operation for the incoming returned products.

To exchange the received item with a new one, click Return for Exchange. Doing so generates a warehouse operation in Odoo to deliver the replacement product.

Use the breadcrumbs to return to the helpdesk ticket. A new Return smart button can now be accessed at the top of the ticket.

Vedi anche

[Returns and refunds](../../../sales/sales/products_prices/returns.html)

## Send products for repair from a ticket¶

If the ticket is related to an issue with a faulty or broken product, a _repair order_ can be created from the **Helpdesk** ticket, and managed through the **Repairs** application.

To create a new repair order, open a Helpdesk ticket and click on the Repair button in the top-left corner. This opens a Repair Reference form.

Fill out the fields with the necessary information:

>   * Customer: this field carries over from the ticket, though a new contact can been selected from the drop-down menu.
> 
>   * Product to Repair: if a product was specified in the Product field on the ticket, it is added to this field automatically. If not, click into the field to select a product from the drop-down menu.
> 
>   * Lot/Serial: this field is **only** visible if the products being repaired are tracked, via lot or serial numbers.
> 
>   * Return: return order from which the product to be repaired comes from.
> 
>   * Under Warranty: if this box is checked, the sale price for all products from the repair order are set to zero.
> 
>   * Scheduled Date: this field defaults to the current date. To select a new date, click into the field and select a date using the drop-down calendar.
> 
>   * Responsible: assign a user from the drop-down menu to manage the repair.
> 
>   * Tags: click into this field to assign an existing tag or create a new one. Multiple tags can be assigned.
> 
> 


If parts are required for the repair, they can be added in the Parts tab. Additional information for the internal repair team can be added to the Repair Notes tab.

Once the form is complete, click Confirm Repair. To create, edit, and send a quote for this repair, click Create Quotation.

A Repairs smart button is then added to the ticket, linking to the repair order.

Suggerimento

Once a user creates a repair order from a **Helpdesk** ticket, they can access it through the ticket’s Repair smart button, or from a link in the chatter, even if they do not have access rights to the **Repair** application.

## Create field service task from a ticket¶

On-site interventions can be planned from a ticket and managed through the **Field Service** application. Customers with [portal access](../../../general/users/portal.html) are able to track the progress of a **Field Service** task the same as they would a **Helpdesk** ticket.

Suggerimento

To change the default **Field Service** project for the team, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams to select a Team. Scroll to the After-Sales section, and choose a project under Field Service.

To create a new **Field Service** task, navigate to a Helpdesk ticket. Click Plan Intervention to open the Create a Field Service task pop-up window.

Confirm or update the task Title.

The Project field on the Create a Field Service task pop-up window defaults to the same **Field Service** project that was identified on the team’s settings page. To change the project for this specific task, select one from the Project field.

If applicable, select a Worksheet Template from the drop-down menu.

Nota

 _Field Service Worksheets_ are reports that detail the work completed during an on-site task. When work is completed, worksheets are signed by the customer to confirm the job is done and the customer is satisfied.

If the **Field Service** project assigned to the **Helpdesk** team has worksheets enabled, and has a default template assigned, that template automatically appears in the Worksheet Template drop-down field. Even so, the field can be edited, and another template can be selected.

If the **Field Service** project does **not** have worksheets enabled, the Worksheet Template field does not appear on the Create a Field Service task pop-up window.

Click Create Task or Create & View Task.

After the task is created, a Tasks smart button is added to the ticket, linking the Field Service task to the ticket.

Vedi anche

[Field Service](https://www.odoo.com/slides/slide/advanced-settings-862?fullscreen=1)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/services/helpdesk/advanced/after_sales.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](close_tickets.html "Close tickets") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * After-Sales services


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
  *[EDI]: Electronic Data Exchange
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
  *[RFQs]: requests for quotation
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