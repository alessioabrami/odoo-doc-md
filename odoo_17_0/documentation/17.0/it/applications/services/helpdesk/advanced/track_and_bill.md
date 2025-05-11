# Track and bill time — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../../productivity.html "Produttività") |
  * [precedente](close_tickets.html "Close tickets") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * Track and bill time



# Track and bill time¶

Odoo _Helpdesk_ provides teams with the ability to track the amount of hours spent working on a ticket, and to bill a customer for that time. Through integrations with the _Sales_ , _Timesheets_ , _Project_ and _Accounting_ applications, customers can be charged once the work is completed, or before it has even begun.

Avvertimento

Since the _Track & Bill Time_ features require integration with other applications, enabling them may result in the installation of additional modules or applications.

Installing a new application on a _One-App-Free_ database triggers a 15-day trial. At the end of the trial, if a paid subscription has not been added to the database, it will no longer be active or accessible.

## Configure track and bill time features¶

Before a customer can be invoiced for support services, the _Track & Bill Time_ features **must** be enabled on each _Helpdesk_ team individually.

### Enable track and bill time on a helpdesk team¶

To view and enable the _Track & Bill Time_ features on a _Helpdesk_ team, first navigate to Helpdesk app ‣ Configuration ‣ Helpdesk Teams. Then, select a team from the list, or create a [new one](../../helpdesk.html). This reveals a team’s settings page.

On the team’s settings page, scroll to the Track & Bill Time section. Check the boxes labeled Timesheets and Time Billing.

Once the Timesheets box is checked, a new field appears, labeled Project.

Nota

If this is the first time this feature has been enabled on this database, the page may need to be manually saved and refreshed before the Project field appears.

The project selected in this field represents where all the timesheets for this team’s tickets are recorded. Click into the Project drop-down menu to select a project.

To create a new project where the timesheets are recorded, click into the Project drop-down menu, type a name for the project, and then click Create from the drop-down menu beneath.

#### Configure service products¶

When the Time Billing feature is enabled, a new product is created in the _Sales_ app called _Service on Timesheets_. This product can be found under Sales app‣ Products ‣ Products. Then, search for `Service on Timesheets` in the Search… bar. This is the product that is used when invoicing for _post-paid support services_ **after** they have been completed.

Select Service on Timesheets from the product page. This reveals the product detail form. The product is configured with the Product Type set to Service and the Invoicing Policy set to Based on Timesheets. Make any necessary changes to the product record, such as the Cost or Sales Price.

In order to invoice for support services **before** the work has been completed (also known as _prepaid support services_), a separate product with a different invoicing policy must be created.

To create a new service product, go to Sales app ‣ Products ‣ Products, and click New. This reveals a blank product detail form.

On the new product form, add a Product Name, and set the Product Type to Service. Then, set the Invoicing Policy to Prepaid/Fixed Price. This means an invoice can be generated and payment can be received for this product before any timesheets entries have been recorded for these services.

Finally, set the Sales Price, and confirm that the Unit of Measure is set to Hours.

## Invoice prepaid support services¶

When support services are billed on a fixed price, an invoice can be created before any work is completed on the issue. In this case, a service product with the _Invoicing Policy_ set to _Prepaid/Fixed Price_ would be used, just like the section above.

### Create a sales order with prepaid product¶

To invoice a customer for prepaid support services, first create a sales order (SO) with the support services product. To do this, go to Sales app ‣ Orders ‣ Quotations. Then, click New to reveal a blank quotation form.

Then, fill out the quotation form with the customer information.

Go to the Order Lines tab of the quotation and click Add a Product. Then, select the _prepaid services product_ configured in the steps above. Update the Quantity field with the number of hours.

After updating any other necessary information, Confirm the quotation. This converts the quotation into an SO.

### Create and send an invoice for prepaid services¶

Once the SO has been confirmed, click the Create Invoice button. This opens a Create invoices pop-up window.

If no down payment is collected, the Create Invoice type can remain as Regular Invoice. If a [down payment](../../../sales/sales/invoicing/down_payment.html) is collected, choose between either Down payment (percentage) or Down payment (fixed amount).

When the necessary information has been entered, click Create Draft Invoice.

The invoice can then be sent to the customer for payment.

### Create helpdesk ticket for prepaid services¶

To create a _Helpdesk_ ticket for prepaid services, navigate to Helpdesk and click the Tickets button to reveal a specific team’s pipeline. Click New to create a new ticket.

On the blank ticket form, create a ticket Title, and enter the Customer information.

When the customer name is added, the Sales Order Item field automatically populates with the most recent prepaid sales order item that has time remaining.

### Track hours on helpdesk ticket¶

Time spent working on a _Helpdesk_ ticket is tracked on the _Timesheets_ tab on the specific ticket.

On the ticket detail form, click on the Timesheets tab and click Add a line. Choose an Employee, add a Description of the task, and enter the number of Hours Spent.

As new lines are added to Timesheets tab, the Remaining Hours on SO field, at the bottom-right of the tab, is automatically updated.

Nota

If the number of hours on the Timesheets tab exceeds the number of hours sold, the Remaining Hours of SO turns red.

As hours are added to the Timesheets tab, they are automatically updated in the Delivered field on the SO, as well.

## Invoice post-paid support services¶

When support services are billed based on the amount of time spent on an issue, an invoice cannot be created before the total number of hours required to solve the problem have been entered on a timesheet. In this case, a service product with the _Invoicing Policy_ set to _Based on Timesheets_ would be used, like the one created in the section above.

### Create a sales order with a time-tracked product¶

To invoice a customer for post-paid support services, first create a sales order (SO) with the _support services product_. To do this, go to Sales app ‣ Orders ‣ Quotations. Then, click New to reveal a blank quotation form.

Fill out the quotation with the customer information.

On the Order Lines tab, click Add a Product. Select the post-paid services product configured in the steps above. After updating any other necessary information, Confirm the quotation.

Importante

Unlike with the prepaid services quotation, Odoo does **not** allow an invoice to be created at this time. That is because no services have been performed; in other words, nothing has been delivered, therefore, there is nothing to invoice.

### Create a helpdesk ticket for time-tracked services¶

To record a _Timesheet_ entry for time-tracker services, go to the Helpdesk app, and select the appropriate team for which these services apply.

If there is already an existing ticket for this issue, select it from the Kanban view. This opens the ticket details form. If there is no existing ticket for this customer issue, click New to create a new ticket and enter the necessary customer information on the blank ticket details form.

After selecting or creating a ticket, go to the Sales Order Item drop-down menu. Select the SO created in the previous step.

### Track support hours on a ticket¶

In order to create an invoice for a product based on timesheets, hours need to be tracked and recorded. At this point, the service is considered _delivered_. To record hours for this support service, click on the Timesheets tab of the ticket.

Click Add a Line to record a new entry. Select an Employee from the drop-down menu, and record the time spent in the Hours Spent column.

Repeat these steps as needed until all time spent on the issues has been recorded.

### Create an invoice for hours tracked on a ticket¶

After the customer’s issue has been solved, and it is determined no new timesheet entries need to be made, an invoice can be created, and the customer can be billed.

To do this, return to the SO by clicking on the Sales Order smart button at the top of the ticket.

Before creating the invoice, confirm that the number in the Delivered column matches the total number of Hours Spent listed in the Timesheets tab on the ticket.

Then, click Create Invoice. This opens a Create invoice(s) pop-up window.

If no down payment is collected, the Create Invoice type can remain as Regular Invoice. If a down payment is collected, choose between either Down payment (percentage) or Down payment (fixed amount).

Importante

Use the Timesheets Period field if this invoice should **only** include timesheets from a certain time period. If this field is left blank, **all** applicable timesheets that have not yet been invoiced will be included.

When the necessary information has been entered, click Create Draft. The invoice can then be reviewed, edited, and sent to the customer for payment.

Vedi anche

  * [Unità di misura](../../../inventory_and_mrp/inventory/product_management/configure/uom.html)

  * [Acconti](../../../sales/sales/invoicing/down_payment.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/services/helpdesk/advanced/track_and_bill.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../../productivity.html "Produttività") |
  * [precedente](close_tickets.html "Close tickets") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Servizi](../../../services.html) »
  * [Helpdesk](../../helpdesk.html) »
  * [Avanzato](../advanced.html) »
  * Track and bill time


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