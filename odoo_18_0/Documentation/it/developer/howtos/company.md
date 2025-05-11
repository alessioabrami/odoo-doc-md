# Multi-company Guidelines — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](create_reports.html "Create customized reports") |
  * [precedente](web_services.html "Web Services") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Multi-company Guidelines



# Multi-company Guidelines¶

Avvertimento

This tutorial requires good knowledge of Odoo. Please refer to the [Server framework 101](../tutorials/server_framework_101.html) tutorial first if needed.

As of version 13.0, a user can be logged in to multiple companies at once. This allows the user to access information from multiple companies, but also to create/edit records in a multi-company environment.

If not managed correctly, it may be the source of a lot of inconsistent multi-company behaviors. For instance, a user logged in to both companies A and B could create a sales order in company A and add products belonging to company B to it. It is only when the user logs out from company B that access errors will occur for the sales order.

To correctly manage multi-company behaviors, Odoo’s ORM provides multiple features:

  * Company-dependent fields

  * Multi-company consistency

  * Default company

  * Views

  * Security rules




## Company-dependent fields¶

When a record is available from multiple companies, we must expect that different values will be assigned to a given field depending on the company from which the value is set.

For the field of the same record to support several values, it must be defined with the attribute `company_dependent` set to `True`.
    
    
    from odoo import api, fields, models
    
    class Record(models.Model):
        _name = 'record.public'
    
        info = fields.Text()
        company_info = fields.Text(company_dependent=True)
        display_info = fields.Text(string='Infos', compute='_compute_display_info')
    
        @api.depends_context('company')
        def _compute_display_info(self):
            for record in self:
                record.display_info = record.info + record.company_info
    

Nota

The `_compute_display_info` method is decorated with `depends_context('company')` (see [`depends_context`](../reference/backend/orm.html#odoo.api.depends_context "odoo.api.depends_context")) to ensure that the computed field is recomputed depending on the current company (`self.env.company`).

When a company-dependent field is read, the current company is used to retrieve its value. In other words, if a user is logged in to companies A and B with A as the main company and creates a record for company B, the value of company-dependent fields will be that of company A.

To read the values of company-dependent fields set by another company than the current one, we need to ensure the company we are using is the correct one. This can be done with [`with_company()`](../reference/backend/orm.html#odoo.models.Model.with_company "odoo.models.Model.with_company"), which updates the current company.
    
    
    # Accessed as the main company (self.env.company)
    val = record.company_dependent_field
    
    # Accessed as the desired company (company_B)
    val = record.with_company(company_B).company_dependent_field
    # record.with_company(company_B).env.company == company_B
    

Avvertimento

Whenever you are computing/creating/… things that may behave differently in different companies, you should make sure whatever you are doing is done in the right company. It doesn’t cost much to always use `with_company` to avoid problems later.
    
    
    @api.onchange('field_name')
    def _onchange_field_name(self):
     self = self.with_company(self.company_id)
     ...
    
    @api.depends('field_2')
    def _compute_field_3(self):
     for record in self:
       record = record.with_company(record.company_id)
       ...
    

## Multi-company consistency¶

When a record is made shareable between several companies by the means of a `company_id` field, we must take care that it cannot be linked to the record of another company through a relational field. For instance, we do not want to have a sales order and its invoice belonging to different companies.

To ensure this multi-company consistency, you must:

  * Set the class attribute `_check_company_auto` to `True`.

  * Define relational fields with the attribute `check_company` set to `True` if their model has a `company_id` field.




On each [`create()`](../reference/backend/orm.html#odoo.models.Model.create "odoo.models.Model.create") and [`write()`](../reference/backend/orm.html#odoo.models.Model.write "odoo.models.Model.write"), automatic checks will be triggered to ensure the multi-company consistency of the record.
    
    
    from odoo import fields, models
    
    class Record(models.Model):
        _name = 'record.shareable'
        _check_company_auto = True
    
        company_id = fields.Many2one('res.company')
        other_record_id = fields.Many2one('other.record', check_company=True)
    

Nota

The field `company_id` must not be defined with `check_company=True`.

Model._check_company(_fnames =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/models.py#L4319)¶
    

Check the companies of the values of the given field names.

Parametri
    

**fnames** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – names of relational fields to check

Solleva
    

[**UserError**](../reference/backend/orm.html#odoo.exceptions.UserError "odoo.exceptions.UserError") – if the `company_id` of the value of any field is not in `[False, self.company_id]` (or `self` if `res_company`).

For `res_users` relational fields, verifies record company is in `company_ids` fields.

User with main company A, having access to company A and B, could be assigned or linked to records in company B.

Avvertimento

The `check_company` feature performs a strict check! It means that if a record has no `company_id` (i.e., the field is not required), it cannot be linked to a record whose `company_id` is set.

Nota

When no domain is defined on the field and `check_company` is set to `True`, a default domain is added: `['|', '('company_id', '=', False), ('company_id', '=', company_id)]`

## Default company¶

When the field `company_id` is made required on a model, a good practice is to set a default company. It eases the setup flow for the user or even guarantees its validity when the company is hidden from view. Indeed, the company is usually hidden if the user does not have access to multiple companies (i.e., when the user does not have the group `base.group_multi_company`).
    
    
    from odoo import api, fields, models
    
    class Record(models.Model):
        _name = 'record.restricted'
        _check_company_auto = True
    
        company_id = fields.Many2one(
            'res.company', required=True, default=lambda self: self.env.company
        )
        other_record_id = fields.Many2one('other.record', check_company=True)
    

## Views¶

As stated in above, the company is usually hidden from view if the user does not have access to multiple companies. This is assessed with the group `base.group_multi_company`.
    
    
    <record model="ir.ui.view" id="record_form_view">
        <field name="name">record.restricted.form</field>
        <field name="model">record.restricted</field>
        <field name="arch" type="xml">
            <form>
                <sheet>
                    <group>
                        <group>
                            <field name="company_id" groups="base.group_multi_company"/>
                            <field name="other_record_id"/>
                        </group>
                    </group>
                </sheet>
            </form>
        </field>
    </record>
    

## Security rules¶

When working with records shared across companies or restricted to a single company, we must take care that a user does not have access to records belonging to other companies.

This is achieved with security rules based on `company_ids`, which contain the current companies of the user (the companies the user checked in the multi-company widget).
    
    
    <!-- Shareable Records -->
    <record model="ir.rule" id="record_shared_company_rule">
        <field name="name">Shared Record: multi-company</field>
        <field name="model_id" ref="model_record_shared"/>
        <field name="global" eval="True"/>
        <field name="domain_force">
            ['|', ('company_id', '=', False), ('company_id', 'in', company_ids)]
        </field>
    </record>
    
    
    
    <!-- Company-restricted Records -->
    <record model="ir.rule" id="record_restricted_company_rule">
        <field name="name">Restricted Record: multi-company</field>
        <field name="model_id" ref="model_record_restricted"/>
        <field name="global" eval="True"/>
        <field name="domain_force">
            [('company_id', 'in', company_ids)]
        </field>
    </record>
    

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/company.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](create_reports.html "Create customized reports") |
  * [precedente](web_services.html "Web Services") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Multi-company Guidelines


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