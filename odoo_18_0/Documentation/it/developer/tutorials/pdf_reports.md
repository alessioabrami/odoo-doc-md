# Build PDF Reports — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_theme.html "Build a website theme") |
  * [precedente](mixins.html "Reuse code with mixins") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Build PDF Reports



# Build PDF Reports¶

Importante

This tutorial is an extension of the [Server framework 101](server_framework_101.html) tutorial. Make sure you have completed it and use the `estate` module you have built as a base for the exercises in this tutorial.

We were previously [introduced to QWeb](server_framework_101/14_qwebintro.html) where it was used to build a kanban view. Now we will expand on one of QWeb’s other main uses: creating PDF reports. A common business requirement is the ability to create documents to send to customers and to use internally. These reports can be used to summarize and display information in an organized template to support the business in different ways. Odoo can additionally add our company’s header and footer to our reports with minimal extra effort.

The documentation related to this topic can be found in [QWeb Templates](../reference/frontend/qweb.html#reference-qweb), [QWeb Reports](../reference/backend/reports.html#reference-reports-report), and the [Report Actions (ir.actions.report)](../reference/backend/actions.html#reference-actions-report) section of the Actions reference.

## File Structure¶

The bulk of a PDF report is its QWeb template. It also typically needs a corresponding `ir.actions.report` to include the report within a module’s business logic. There is no strict rule for the file names or where they are located, but these two parts are typically stored in 2 separate files within a `report` folder at the top level of your module’s directory. If a module has many or multiple long report templates, then they are often organized logically across different files named after the report(s) they contain. All actions for the reports are usually stored in the same file ending with `_reports.xml`, regardless of the number of reports it contains.

Therefore, it is expected that your work tree will look something like this:
    
    
    estate
    ├── models
    │   ├── *.py
    │   └── __init__.py
    ├── report
    │   ├── estate_property_templates.xml
    │   └── estate_property_reports.xml
    ├── security
    │   └── ir.model.access.csv
    ├── views
    │   └── *.xml
    ├── __init__.py
    └── __manifest__.py
    

Don’t forget to add whatever files your template and action view will be into to your `__manifest__.py`. In this case, you will want to add the files to the `data` list and remember that the files listed in a manifest are loaded sequentially!

## Basic Report¶

Nota

**Goal** : at the end of this section, we will be able to print a report that displays all offers for a property.

In our real estate example there are many useful reports that we could create. One simple report we can create is one that displays all of a property’s offers.

### Report Data¶

Before we do anything we first need some data to populate our reports or else this tutorial won’t be very interesting. When creating reports, you will need some data to test your report code and check that the resulting look is as expected. It is a good idea to test with data that will cover most or all of your expected use cases. A good representation set for our simple report is:

  * At least 3 properties where 1 is «sold», 1 is «offer received» and 1 is «new».

  * At least 2-3 offers for our «sold» and «offer received» properties




If you don’t have a set of data like this already, you can either:

  * Complete the [Define module data](define_module_data.html) tutorial (if you haven’t done so already) and add the extra cases to your demo data (you may need to create a new database to load in the demo data).

  * Manually create the data in your database.

  * Copy this [data file](https://github.com/odoo/technical-training-solutions/blob/18.0-J_reports/estate/data/estate_demo.xml) into a new directory (data) in your estate module and copy [these lines](https://github.com/odoo/technical-training-solutions/blob/18.0-J_reports/estate/__manifest__.py#L21-L23) into your __manifest__.py file (you may need to create a new database to load in the demo data).




Before continuing, click through your data in your database and make sure your data is as expected. Of course you can add the data after you write your report code, but then you will not be able to incrementally test portions of your code as you write it. This can make checking for mistakes and debugging your code more difficult in the long run for complicated reports.

### Minimal Template¶

A minimal viable template is viewable under the «Minimal viable template» section of the [Report template](../reference/backend/reports.html#reference-reports-templates) documentation. We can modify this example to build our minimal property offers template file:
    
    
    <?xml version="1.0" encoding="UTF-8" ?>
    <odoo>
        <template id="report_property_offers">
            <t t-foreach="docs" t-as="property">
                <t t-call="web.html_container">
                    <t t-call="web.external_layout">
                        <div class="page">
                            <h2>
                                <span t-field="property.name"/>
                            </h2>
                            <div>
                                <strong>Expected Price: </strong>
                                <span t-field="property.expected_price"/>
                            </div>
                            <table class="table">
                                <thead>
                                    <tr>
                                        <th>Price</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <t t-set="offers" t-value="property.mapped('offer_ids')"/>
                                    <tr t-foreach="offers" t-as="offer">
                                        <td>
                                            <span t-field="offer.price"/>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </t>
                </t>
            </t>
        </template>
    </odoo>
    

Most of the Odoo specific (i.e. non-HTML) items in our file are explained in the minimal viable template section. Some additional features in our template are:

  * The use of the `class="table"` attribute, so our table has some nice formatting. Twitter Bootstrap (we’re using its table class in this case), and Font Awesome (useful for adding icons) classes can be used in your report template.

  * The use of `t-set`, `t-value`, `t-foreach`, and `t-as` so that we can loop over all the `offer_ids`.




If you are already familiar with website templating engines, then the QWeb directives (i.e. the `t-` commands) probably don’t need much explanation and you can just look at its [documentation](../reference/frontend/qweb.html#reference-qweb) and skip ahead to the next subsection.

Otherwise you are encouraged to read more about them ( [Wikipedia](https://en.wikipedia.org/wiki/Template_processor) has a good high level description), but the general idea is that QWeb provides the ability to dynamically generate web code based on Odoo data and simple commands. I.e. QWeb can access recordset data (and methods) and process simple programming operations such as setting and accessing temporary variables. For example, in the above example:

  * `t-set` creates a temporary variable called «offers» that has its value set by `t-value` to the current `estate.property` recordset’s `offer_ids`.

  * The `t-foreach` and `t-as` usage is the equivalent to the Python:



    
    
    for offer in offers:
    

### Report Action¶

Now that we have a template, we need to make it accessible in our app via a `ir.actions.report`. A practical example of `ir.actions.report` is [here](https://github.com/odoo/odoo/blob/0e12fa135882cd5095dbf15fe2f64231c6a84336/addons/event/report/event_event_reports.xml#L20-L30) corresponding to [this template](https://github.com/odoo/odoo/blob/0e12fa135882cd5095dbf15fe2f64231c6a84336/addons/event/report/event_event_templates.xml#L5). Its contents are all explained in [the documentation](../reference/backend/actions.html#reference-actions-report).

An `ir.actions.report` is primarily used via the Print menu of a model’s view. In the practical example, the `binding_model_id` specifies which model’s views the report should show, and Odoo will auto-magically add it for you. Another common use case of the report action is to link it to a button as we learned in [Chapter 9: Ready For Some Action?](server_framework_101/09_actions.html). This is handy for reports that only make sense under specific conditions. For example, if we wanted to make a «Final Sale» report, then we can link it to a «Print Sale Info» button that appears in the form view only when the property is «Sold».

You may have noticed or are wondered why our report template loops through a recordset. When our template is passed more than one record, it can produce one PDF report for all the records. Using the Print menu in the list view with multiple records selected will demonstrate this.

### Make a Report¶

Finally, you now know where to create your files and how the content of the files should look. Happy report making!

Exercise

Make a report.

  * Add the property offers report from the minimal template subsection to the Print menu of the Property views.

  * Improve the report by adding more data. Refer to the **Goal** of this section to see what additional data you can add and feel free to add even more.

  * Bonus: Make an extra flexible report by adding in some logic so that when there are no offers on a property then we don’t create a table and instead write something about how there are no offers yet. Hint: you will need to use `t-if` and `t-else`.




Remember to check that your PDF reports match your data as expected.

## Sub-templates¶

Nota

**Goal** : at the end of this section, we will have a sub-template that we use in 2 reports.

There are two main reasons for using sub-templates. One is to make the code easier to read when working with extra-long or complicated templates. The other is to reuse code where possible. Our simple property offers report is useful, but listing property offers information can be useful for more than just one report template. One example is a report that lists all of a salesman’s properties” offers.

See if you can understand how to call a sub-template by reading the [documentation](../reference/frontend/qweb.html#reference-qweb-sub-templates) on it and/or by looking at an [example](https://github.com/odoo/odoo/blob/0e12fa135882cd5095dbf15fe2f64231c6a84336/addons/portal/static/src/xml/portal_chatter.xml#L147-L160) (remember QWeb uses the same control flows regardless if it is for a report or a view in Odoo.)

Exercise

Create and use a sub-template.

  * Split the table portion of the offers into its own template. Remember to check that your original report still prints correctly afterwards.

  * Add a new report for `res.users` that allows you to print all of the Real Estate Properties that are visible in their form view (i.e. in the «Settings» app). Include the offers for each of those saleman’s properties in the same report. Hint: since the `binding_model_id` in this case will not be within the estate module, you will need to use `ref="base.model_res_users"`.

Your end result should look similar to the image in the **Goal** of this section.




Remember to check that your reports match your data as expected!

## Report Inheritance¶

Nota

**Goal** : at the end of this section, we will inherit the property report in the `estate_account` module.

Inheritance in QWeb uses the same `xpath` elements as [views inheritance](../reference/user_interface/view_records.html#reference-view-records-inheritance). A QWeb template refers to its parent template in a different way though. It is even easier to do by just adding the `inherit_id` attribute to the `template` element and setting it equal to the _module.parent_template_id_.

We didn’t add any new fields to any of the estate models in `estate_account`, but we can still add information to our existing property report. For example, we know that any «Sold» properties will already have an invoice created for them, so we can add this information to our report.

Exercise

Inherit a report.

  * Extend the property report to include some information about the invoice. You can look at the **Goal** of this section for inspiration (i.e. print a line when the property is Done, otherwise print nothing).




Again, remember to check that your reports match your data as expected!

## Additional Features¶

All the following extra features are described further in the [QWeb Reports](../reference/backend/reports.html#reference-reports-report) documentation, including how to implement each of them.

### Translations¶

We all know Odoo is used in multiple languages thanks to automated and manual translating. QWeb reports are no exception! Note that sometimes the translations do not work properly if there are unnecessary spaces in your template’s text content, so try to avoid them when possible (especially leading spaces).

### Reports are web pages¶

You probably are tired of hearing that QWeb creates HTML, but we’re saying it again! One of the neat features of reports being written in QWeb is they can be viewed within the web browser. This can be useful if you want to embed a hyperlink that leads to a specific report. Note that the usual security checks will still apply to prevent unauthorized users from accessing the reports.

### Barcodes¶

Odoo has a built-in barcode image creator that allows for barcodes to be embedded in your reports. Check out the corresponding [code](https://github.com/odoo/odoo/blob/0e12fa135882cd5095dbf15fe2f64231c6a84336/addons/web/controllers/main.py#L2044-L2046) to see all the supported barcode types.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/tutorials/pdf_reports.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](website_theme.html "Build a website theme") |
  * [precedente](mixins.html "Reuse code with mixins") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Build PDF Reports


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
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