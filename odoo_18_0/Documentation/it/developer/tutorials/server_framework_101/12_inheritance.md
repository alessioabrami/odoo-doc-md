# Chapter 12: Inheritance — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](13_other_module.html "Chapter 13: Interact With Other Modules") |
  * [precedente](11_sprinkles.html "Chapter 11: Add The Sprinkles") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 12: Inheritance



# Chapter 12: Inheritance¶

A powerful aspect of Odoo is its modularity. A module is dedicated to a business need, but modules can also interact with one another. This is useful for extending the functionality of an existing module. For example, in our real estate scenario we want to display the list of a salesperson’s properties directly in the regular user view.

But before going through the specific Odoo module inheritance, let’s see how we can alter the behavior of the standard CRUD (Create, Retrieve, Update or Delete) methods.

## Python Inheritance¶

Nota

**Goal** : at the end of this section:

  * It should not be possible to delete a property which is not new or cancelled.




  * When an offer is created, the property state should change to “Offer Received”

  * It should not be possible to create an offer with a lower price than an existing offer




In our real estate module, we never had to develop anything specific to be able to do the standard CRUD actions. The Odoo framework provides the necessary tools to do them. In fact, such actions are already included in our model thanks to classical Python inheritance:
    
    
    from odoo import fields, models
    
    class TestModel(models.Model):
        _name = "test_model"
        _description = "Test Model"
    
        ...
    

Our `class TestModel` inherits from [`Model`](../../reference/backend/orm.html#odoo.models.Model "odoo.models.Model") which provides [`create()`](../../reference/backend/orm.html#odoo.models.Model.create "odoo.models.Model.create"), [`read()`](../../reference/backend/orm.html#odoo.models.Model.read "odoo.models.Model.read"), [`write()`](../../reference/backend/orm.html#odoo.models.Model.write "odoo.models.Model.write") and [`unlink()`](../../reference/backend/orm.html#odoo.models.Model.unlink "odoo.models.Model.unlink").

These methods (and any other method defined on [`Model`](../../reference/backend/orm.html#odoo.models.Model "odoo.models.Model")) can be extended to add specific business logic:
    
    
    from odoo import fields, models
    
    class TestModel(models.Model):
        _name = "test_model"
        _description = "Test Model"
    
        ...
    
        @api.model
        def create(self, vals):
            # Do some business logic, modify vals...
            ...
            # Then call super to execute the parent method
            return super().create(vals)
    

The decorator [`model()`](../../reference/backend/orm.html#odoo.api.model "odoo.api.model") is necessary for the [`create()`](../../reference/backend/orm.html#odoo.models.Model.create "odoo.models.Model.create") method because the content of the recordset `self` is not relevant in the context of creation, but it is not necessary for the other CRUD methods.

It is also important to note that even though we can directly override the [`unlink()`](../../reference/backend/orm.html#odoo.models.Model.unlink "odoo.models.Model.unlink") method, you will almost always want to write a new method with the decorator [`ondelete()`](../../reference/backend/orm.html#odoo.api.ondelete "odoo.api.ondelete") instead. Methods marked with this decorator will be called during [`unlink()`](../../reference/backend/orm.html#odoo.models.Model.unlink "odoo.models.Model.unlink") and avoids some issues that can occur during uninstalling the model’s module when [`unlink()`](../../reference/backend/orm.html#odoo.models.Model.unlink "odoo.models.Model.unlink") is directly overridden.

In Python 3, `super()` is equivalent to `super(TestModel, self)`. The latter may be necessary when you need to call the parent method with a modified recordset.

Pericolo

  * It is very important to **always** call `super()` to avoid breaking the flow. There are only a few very specific cases where you don’t want to call it.

  * Make sure to **always** return data consistent with the parent method. For example, if the parent method returns a `dict()`, your override must also return a `dict()`.




Exercise

Add business logic to the CRUD methods.

  * Prevent deletion of a property if its state is not “New” or “Cancelled”




Tip: create a new method with the [`ondelete()`](../../reference/backend/orm.html#odoo.api.ondelete "odoo.api.ondelete") decorator and remember that `self` can be a recordset with more than one record.

  * At offer creation, set the property state to “Offer Received”. Also raise an error if the user tries to create an offer with a lower amount than an existing offer.




Tip: the `property_id` field is available in the `vals`, but it is an `int`. To instantiate an `estate.property` object, use `self.env[model_name].browse(value)` ([example](https://github.com/odoo/odoo/blob/136e4f66cd5cafe7df450514937c7218c7216c93/addons/gamification/models/badge.py#L57))

## Model Inheritance¶

**Reference** : the documentation related to this topic can be found in [Inheritance and extension](../../reference/backend/orm.html#reference-orm-inheritance).

In our real estate module, we would like to display the list of properties linked to a salesperson directly in the Settings / Users & Companies / Users form view. To do this, we need to add a field to the `res.users` model and adapt its view to show it.

Odoo provides two _inheritance_ mechanisms to extend an existing model in a modular way.

The first inheritance mechanism allows modules to modify the behavior of a model defined in an another module by:

  * adding fields to the model,

  * overriding the definition of fields in the model,

  * adding constraints to the model,

  * adding methods to the model,

  * overriding existing methods in the model.




The second inheritance mechanism (delegation) allows every record of a model to be linked to a parent model’s record and provides transparent access to the fields of this parent record.

In Odoo, the first mechanism is by far the most used. In our case, we want to add a field to an existing model, which means we will use the first mechanism. For example:
    
    
    from odoo import fields, models
    
    class InheritedModel(models.Model):
        _inherit = "inherited.model"
    
        new_field = fields.Char(string="New Field")
    

A practical example where two fields are added to a model can be found [here](https://github.com/odoo/odoo/blob/60e9410e9aa3be4a9db50f6f7534ba31fea3bc29/addons/account_fleet/models/account_move.py#L39-L47).

By convention, each inherited model is defined in its own Python file. In our example, it would be `models/inherited_model.py`.

Exercise

Add a field to Users.

  * Add the following field to `res.users`:


Field | Type  
---|---  
property_ids | One2many inverse of the field that references the salesperson in `estate.property`  
  
  * Add a domain to the field so it only lists the available properties.




In the next section let’s add the field to the view and check that everything is working well!

## View Inheritance¶

**Reference** : the documentation related to this topic can be found in [Inheritance](../../reference/user_interface/view_records.html#reference-view-records-inheritance).

Nota

**Goal** : at the end of this section, the list of available properties linked to a salesperson should be displayed in their user form view

Instead of modifying existing views in place (by overwriting them), Odoo provides view inheritance where children “extension” views are applied on top of root views. These extension can both add and remove content from their parent view.

An extension view references its parent using the `inherit_id` field. Instead of a single view, its `arch` field contains a number of `xpath` elements that select and alter the content of their parent view:
    
    
    <record id="inherited_model_view_form" model="ir.ui.view">
        <field name="name">inherited.model.form.inherit.test</field>
        <field name="model">inherited.model</field>
        <field name="inherit_id" ref="inherited.inherited_model_view_form"/>
        <field name="arch" type="xml">
            <!-- find field description and add the field
                 new_field after it -->
            <xpath expr="//field[@name='description']" position="after">
              <field name="new_field"/>
            </xpath>
        </field>
    </record>
    

`expr`
    

An [XPath](https://w3.org/TR/xpath) expression selecting a single element in the parent view. Raises an error if it matches no element or more than one

`position`
    

Operation to apply to the matched element:

`inside`
    

appends `xpath`’s body to the end of the matched element

`replace`
    

replaces the matched element with the `xpath`’s body, replacing any `$0` node occurrence in the new body with the original element

`before`
    

inserts the `xpath`’s body as a sibling before the matched element

`after`
    

inserts the `xpaths`’s body as a sibling after the matched element

`attributes`
    

alters the attributes of the matched element using the special `attribute` elements in the `xpath`’s body

When matching a single element, the `position` attribute can be set directly on the element to be found. Both inheritances below have the same result.
    
    
    <xpath expr="//field[@name='description']" position="after">
        <field name="idea_ids" />
    </xpath>
    
    <field name="description" position="after">
        <field name="idea_ids" />
    </field>
    

An example of a view inheritance extension can be found [here](https://github.com/odoo/odoo/blob/691d1f087040f1ec7066e485d19ce3662dfc6501/addons/account_fleet/views/account_move_views.xml#L3-L17).

Exercise

Add fields to the Users view.

Add the `property_ids` field to the `base.view_users_form` in a new notebook page.

Tip: an example an inheritance of the users” view can be found [here](https://github.com/odoo/odoo/blob/691d1f087040f1ec7066e485d19ce3662dfc6501/addons/gamification/views/res_users_views.xml#L5-L14).

Inheritance is extensively used in Odoo due to its modular concept. Do not hesitate to read the corresponding documentation for more info!

In the [next chapter](13_other_module.html), we will learn how to interact with other modules.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/tutorials/server_framework_101/12_inheritance.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](13_other_module.html "Chapter 13: Interact With Other Modules") |
  * [precedente](11_sprinkles.html "Chapter 11: Add The Sprinkles") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 12: Inheritance


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous Integration
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