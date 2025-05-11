# After-Sales services — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](close_tickets.html "Close tickets") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * After-Sales services



# After-Sales services¶

_After-Sales_ services can be configured in the _Helpdesk_ application for individual teams. Once enabled, users can issue refunds, generate coupons, process returns, and schedule repairs or field service interventions directly from a ticket.

## Set up after-sales services¶

Start by enabling the after-sales services on a specific _Helpdesk_ team, by going to Helpdesk app ‣ Configuration ‣ Helpdesk Teams and click on the team the services should be applied to. Then, scroll to the After-Sales section on the team’s settings page, and choose which of the following options to enable:

  * Refunds: issues credit notes to refund a customer, or adjust the remaining amount due.

  * Coupons: offers discounts and free products through an existing coupon program.

  * Returns: initiates a product return from a customer through a reverse transfer.

  * Repairs: creates repair orders for broken or faulty products.

  * Field Service: plans onsite intervention through the _Field Service_ application.




The services that are enabled can vary based on the type of support a team provides.¶

Pericolo

Since all the after-sales services in Odoo require integration with other applications, enabling any of them may result in the installation of additional modules or applications. Installing a new application on a One-App-Free database triggers a 15-day trial. At the end of the trial, if a paid subscription has not been added to the database, it will no longer be accessible.

## Issue refund with credit note¶

A _credit note_ is a document issued to a customer informing them that they have been credited a certain amount of money. They can be used to provide a full refund to a customer, or to adjust any remaining amount due. While they are usually created through the _Accounting_ or _Invoicing_ applications, they can be created through a _Helpdesk_ ticket, as well.

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

Once the credit note has been posted, a Credit Notes smart button is added to the _Helpdesk_ ticket.

Vedi anche

[Note di credito e rimborsi](../../../finance/accounting/customer_invoices/credit_notes.html)

## Generate coupons from a ticket¶

Coupons can be used to alter the price of products or orders. Conditional rules define the usage constraints of a coupon. _Coupon Programs_ are configured in the _Sales_ , _Point of Sale_ , or _Website_ applications.

Importante

The _eCommerce_ module **must** be installed to create coupon codes from the _Website_.

To generate a coupon, open a _Helpdesk_ ticket and click on the Coupon button in the top-left corner. Select an option from the Coupon Program drop-down menu in the Generate a Coupon pop-up window that appears.

Nota

> To create a new Coupon Program, navigate to Sales app ‣ Products ‣ Discount & Loyalty and click New. To make the program available to share with _Helpdesk_ customers, the Program Type **must** be set to Coupons. This generates single-use coupon codes that grant immediate access to rewards and discounts.

Coupon programs can also be created in the _Point of Sale_ application or _Website_ application. Refer to [discount and loyalty programs](../../../sales/sales/products_prices/loyalty_discount.html) for more information.

Click on the Valid Until field, and use the pop-up calendar to select an expiration date for this coupon code. If this field is left blank, the code does **not** expire.

Click Send by Email to compose an email to send to the customer with the coupon code.

Nota

When emailing a coupon code, **all** the followers of the ticket are added as recipients to the email. Additional recipients can be added to the email as well, in the Recipients field of the Compose Email pop-up window. If an expiration date was selected for the code, it is included in the message template.

Click Get Share Link to generate a link to send directly to the customer. Doing so opens a Share Coupons pop-up window. Click the Copy button next to the Share Link field and paste the results to any communication with the customer. When the customer uses the link, the code is automatically applied to their cart.

After a Coupon Code has been generated, a Coupons smart button is added to the top of the ticket; click the smart button to view the coupon code, expiration date, and additional information.

Vedi anche

  * [Coupons](https://www.youtube.com/watch?v=KW5cZHg10jQ)

  * [Discount and loyalty programs](../../../sales/sales/products_prices/loyalty_discount.html)




## Facilitate a product return with a reverse transfer¶

Returns are completed through _reverse transfers_ , which generate new warehouse operations for the returning products. Click the Return button in the top-left corner of a ticket to open the Reverse Transfer pop-up window.

Importante

The Return button **only** appears on a ticket if the customer has a recorded delivery in the database.

Select a Sales Order or Delivery to Return to identify the products that need to be returned.

By default, the quantity matches the validated quantity from the delivery order. Update the Quantity field, if necessary. To remove a line, click the 🗑️ (trash can) icon.

Select a Return Location where the items should be directed after the return is completed.

Click Return to confirm the return. This generates a new warehouse operation for the incoming returned products.

Use the breadcrumbs to return to the helpdesk ticket. A new Return smart button can now be accessed at the top of the ticket.

Vedi anche

[Returns and refunds](../../../sales/sales/products_prices/returns.html)

## Send products for repair from a ticket¶

If the ticket is related to an issue with a faulty or broken product, a _repair order_ can be created from the _Helpdesk_ ticket, and managed through the _Repairs_ application.

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

Once a user creates a repair order from a _Helpdesk_ ticket, they can access it through the ticket’s Repair smart button, or from a link in the chatter, even if they do not have access rights to the _Repair_ application.

## Create field service task from a ticket¶

On-site interventions can be planned from a ticket and managed through the _Field Service_ application. Customers with [portal access](../../../general/users/portal.html) are able to track the progress of a _Field Service_ task just as they would a _Helpdesk_ ticket.

Suggerimento

To change the default _Field Service_ project for the team, go to Helpdesk app ‣ Configuration ‣ Helpdesk Teams to select a Team. Scroll to the After-Sales section, and choose a project under Field Service.

To create a new _Field Service_ task, navigate to a Helpdesk ticket. Click Plan Intervention to open the Create a Field Service task pop-up window.

Confirm or update the task Title.

The Project field on the Create a Field Service task pop-up window defaults to the same _Field Service_ project that was identified on the team’s settings page. To change the project for this specific task, select one from the Project field.

If applicable, select a Worksheet Template from the drop-down menu.

Nota

 _Field Service Worksheets_ are reports that detail the work completed during an on-site task. When work is completed, worksheets are signed by the customer to confirm the job is done and the customer is satisfied.

If the _Field Service_ project assigned to the _Helpdesk_ team has worksheets enabled, and has a default template assigned, that template automatically appears in the Worksheet Template drop-down field. Even so, the field can be edited, and another template can be selected.

If the _Field Service_ project does **not** have worksheets enabled, the Worksheet Template field does not appear on the Create a Field Service task pop-up window.

Click Create Task or Create & View Task.

After the task is created, a Tasks smart button is added to the ticket, linking the Field Service task to the ticket.

Vedi anche

[Field Service](https://www.odoo.com/slides/slide/advanced-settings-862?fullscreen=1)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/helpdesk/advanced/after_sales.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](close_tickets.html "Close tickets") |
  * [precedente](../advanced.html "Avanzato") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
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