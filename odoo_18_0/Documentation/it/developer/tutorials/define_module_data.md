# Define module data — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](restrict_data_access.html "Restrict access to data") |
  * [precedente](master_odoo_web_framework/03_customize_kanban_view.html "Chapter 3: Customize a kanban view") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Define module data



# Define module data¶

Importante

This tutorial is an extension of the [Server framework 101](server_framework_101.html) tutorial. Make sure you have completed it and use the `estate` module you have built as a base for the exercises in this tutorial.

## Data Types¶

### Master Data¶

Master data is usually part of the technical or business requirements for the module. In other words, such data is often necessary for the module to work properly. This data will always be installed when installing the module.

We already met technical data previously since we have defined [views](../reference/user_interface/view_records.html) and [actions](../reference/backend/actions.html). Those are one kind of master data.

On top of technical data, business data can be defined, e.g. countries, currencies, units of measure, as well as complete country localization (legal reports, tax definitions, chart of account), and much more…

### Demo Data¶

In additional to master data, which are requirements for a module to work properly, we also like having data for demonstration purposes:

  * Help the sales representatives make their demos quickly.

  * Have a set of working data for developers to test new features and see how these new features look with data they might not have added themselves.

  * Test that the data is loaded correctly, without raising an error.

  * Setup most of the features to be used quickly when creating a new database.




Demo data is automatically loaded when you start the server if you don’t explicitly say you don’t want it. This can be done in the database manager or with the command line.
    
    
    $ ./odoo-bin -h
    Usage: odoo-bin [options]
    
    Options:
    --version             show program's version number and exit
    -h, --help            show this help message and exit
    
    Common options:
      [...]
      --without-demo=WITHOUT_DEMO
                          disable loading demo data for modules to be installed
                          (comma-separated, use "all" for all modules). Requires
                          -d and -i. Default is none
    [...]
    
    $ ./odoo-bin --addons-path=... -d db -i account --without-demo=all
    

## Data Declaration¶

### Manifest¶

**Reference** : the documentation related to this topic can be found in [Module Manifests](../reference/backend/module.html#reference-module-manifest).

Data is declared either in CSV or in XML. Each file containing data must be added in the manifest for them to be loaded.

The keys to use in the manifest to add new data are `data` for the master data and `demo` for the demo data. Both values should be a list of strings representing the relative paths to the files declaring the data.

Usually, demo data is in a `demo` folder, views and actions are in a `views` folder, security related data is in a `security` folder, and other data is in a `data` folder.

If your work tree looks like this:
    
    
    estate
    ├── data
    │   └── master_data.xml
    ├── demo
    │   └── demo_data.xml
    ├── models
    │   ├── *.py
    │   └── __init__.py
    ├── security
    │   └── ir.model.access.csv
    ├── views
    │   └── estate_property_offer_views.xml
    ├── __init__.py
    └── __manifest__.py
    

Your manifest should look like this:
    
    
    # -*- coding: utf-8 -*-
    
    {
        "name": "Real Estate",
        "depends": [
            ...
        ],
        "data": [
            "security/ir.model.access.csv",  # CSV and XML files are loaded at the same place
            "views/estate_property_offer_views.xml",  # Views are data too
            "data/master_data.xml",  # Split the data in multiple files depending on the model
        ],
        "demo": [
            "demo/demo_data.xml",
        ]
        "application": True,
    }
    

### CSV¶

**Reference** : the documentation related to this topic can be found in [CSV data files](../reference/backend/data.html#reference-data-csvdatafiles).

The easiest way to declare simple data is by using the CSV format. This is however limited in terms of features: use it for long lists of simple models, but prefer XML otherwise.
    
    
    id,field_a,field_b,related_id:id
    id1,valueA1,valueB1,module.relatedid
    id2,valueA2,valueB2,module.relatedid
    

Suggerimento

Your IDE has probably an extension to have a syntax highlighting of the CSV files

  * [Atom](https://atom.io/packages/rainbow-csv).

  * [PyCharm/IntelliJ](https://plugins.jetbrains.com/plugin/10037-csv-plugin).

  * [Vim](https://github.com/mechatroner/rainbow_csv).

  * [Visual Studio](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv).




Exercise

Add some standard Real Estate Property Types for the `estate` module: Residential, Commercial, Industrial and Land. These should always be installed.

### XML¶

**Reference** : the documentation related to this topic can be found in [Data Files](../reference/backend/data.html#reference-data).

When the data to create is more complex it can be useful, or even necessary, to do it in XML.
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="field_a">valueA1</field>
        <field name="field_b">valueB1</field>
      </record>
    
      <record id="id2" model="tutorial.example">
        <field name="field_a">valueA2</field>
        <field name="field_b">valueB2</field>
      </record>
    </odoo>
    

Exercise

Create some demo data for the `estate` module.

Field | Values | Values  
---|---|---  
name | Big Villa | Trailer home  
state | New | Cancelled  
description | A nice and big villa | Home in a trailer park  
postcode | 12345 | 54321  
date_availability | 2020-02-02 | 1970-01-01  
expected_price | 1,600,000 | 100,000  
selling_price |  | 120,000  
bedrooms | 6 | 1  
living_area | 100 | 10  
facades | 4 | 4  
garage | True | False  
garden | True |   
garden_area | 100000 |   
garden_orientation | South |   
  
#### Data Extension¶

During the Core Training, we saw in the [Chapter 12: Inheritance](server_framework_101/12_inheritance.html) chapter we could inherit (extend) an existing view. This was a special case of data extension: any data can be extended in a module.

When you are adding new fields to an existing model in a new module, you might want to populate those fields on the records created in the modules you are depending on. This is done by giving the `xml_id` of the record you want to extend. It won’t replace it, in this case we will set the `field_c` to the given value for both records.
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="field_c">valueC1</field>
      </record>
    
      <record id="id2" model="tutorial.example">
        <field name="field_c">valueC2</field>
      </record>
    </odoo>
    

#### `ref`¶

Related fields can be set using the `ref` key. The value of that key is the `xml_id` of the record you want to link. Remember the `xml_id` is composed of the name of the module where the data is first declared, followed by a dot, followed by the `id` of the record (just the `id` works too if you are in the module declaring it).
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="related_id" ref="module.relatedid"/>
      </record>
    </odoo>
    

Exercise

Create some demo data offers for the properties you created.

Create offers using the partners defined in `base`

Partner | Estate | Price | Validity  
---|---|---|---  
Azure Interior | Big Villa | 10000 | 14  
Azure Interior | Big Villa | 1500000 | 14  
Deco Addict | Big Villa | 1500001 | 14  
  
Exercise

Ensure both of your demo properties are created with their Property Type set to Residential.

#### `eval`¶

The value to assign to a field is not always a simple string and you might need to compute it. It can also be used to optimize the insertion of related values, or because a constraint forces you to add the related values in batch. See :Add X2many fields.
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="year" eval="datetime.now().year+1"/>
      </record>
    </odoo>
    

Exercise

The offers you added should always be in a date relative to the installation of the module.

#### `search`¶

Sometimes, you need to call the ORM to do a `search`. This is not feasible with the CSV format.
    
    
    <odoo>
      <record id="id1" model="account.move.line">
        <field name="account_id" search="[
          ('user_type_id', '=', ref('account.data_account_type_direct_costs')),
          ('company_id', '=', obj().env.company.id)]
        "/>
      </record>
    </odoo>
    

In this code snippet, it is needed because the master data depends on the localization installed.

#### `function`¶

You might also need to execute python code when loading data.
    
    
    <function model="tutorial.example" name="action_validate">
        <value eval="[ref('demo_invoice_1')]"/>
    </function>
    

Exercise

Validate one of the demo data offers by using the «Accept Offer» button. Refuse the others.

### Add X2many fields¶

**Reference** : the documentation related to this topic can be found in [`Command`](../reference/backend/orm.html#odoo.fields.Command "odoo.fields.Command").

If you need to add related data in a One2many or a Many2many field, you can do so by using the [`Command`](../reference/backend/orm.html#odoo.fields.Command "odoo.fields.Command") methods.
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="related_ids" eval="[
            Command.create({
                'name': 'My name',
            }),
            Command.create({
                'name': 'Your name',
            }),
            Command.link(ref('model.xml_id')),
        ]"/>
      </record>
    </odoo>
    

Exercise

Create one new Property, but this time with some offers created directly inside the One2many field linked to the Offers.

## Accessing the data¶

Avvertimento

You should never access demo data outside of the demo data declaration, not even in tests.

There are multiple ways to access the master/demo data.

In python code, you can use the `env.ref(self, xml_id, raise_if_not_found=True)` method. It returns the recordset linked to the `xml_id` you specify.

In XML, you can use the `ref` key like this
    
    
    <odoo>
      <record id="id1" model="tutorial.example">
        <field name="related_id" ref="module.relatedid"/>
      </record>
    </odoo>
    

It will call the ref method, and store the id of the record returned on the field `related_id` of the record of type `tutorial.example` with id `id1`.

In CSV, the title of the column must be suffixed with `:id` or `/id`.
    
    
    id,parent_id:id,name
    "child1","module.parent","Name1"
    "child2","module.parent","Name2"
    "child3","module.parent","Name3"
    

In SQL, it is more complicated, see the advanced section.

Avvertimento

Data can always be deleted by the user. Always code defensively, taking this into account.

## Advanced¶

### What is the XML id?¶

Because we don’t want a column `xml_id` in every single SQL table of the database, we need a mechanism to store it. This is done with the `ir.model.data` model.

It contains the name of the record (the `xml_id`) along with the module in which it is defined, the model defining it, and the id of it.

### No update¶

The records created with the `noupdate` flag won’t be updated when upgrading the module that created them, but it will be created if it didn’t exist yet.

Nota

`odoo-bin -i module` will bypass this setting and always load the data. But normally one shouldn’t do this on a production database.
    
    
    <odoo noupdate="1">
      <record id="id1" model="model">
        <field name="fieldA" eval="True"/>
      </record>
    </odoo>
    

### Import as SQL¶

In some cases, it makes sense to do the import directly in SQL. This is however discouraged as it bypasses all the features of the ORM, computed fields (including metadata) and python constraints.

Nota

Generally using raw SQL also bypasses ACLs and increases the risks of injections.

**Reference** : [Security in Odoo](../reference/backend/security.html#reference-security)

  * It can help to speed the import time by a lot [with huge files](https://github.com/odoo/enterprise/blob/d46cceef8c594b9056d0115edb7169e207a5986f/product_unspsc/hooks.py#L19).

  * For more complex imports like for the [translations](https://github.com/odoo/odoo/blob/e1f8d549895cd9c459e6350430f30d541d02838a/odoo/addons/base/models/ir_translation.py#L24).

  * It can be necessary to [initialize the database](https://github.com/odoo/odoo/blob/e1f8d549895cd9c459e6350430f30d541d02838a/odoo/addons/base/data/base_data.sql).




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/tutorials/define_module_data.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](restrict_data_access.html "Restrict access to data") |
  * [precedente](master_odoo_web_framework/03_customize_kanban_view.html "Chapter 3: Customize a kanban view") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Define module data


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