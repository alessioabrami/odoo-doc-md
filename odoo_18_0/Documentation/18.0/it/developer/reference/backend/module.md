# Module Manifests — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](security.html "Security in Odoo") |
  * [precedente](reports.html "QWeb Reports") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Module Manifests



# Module Manifests¶

## Manifest¶

The manifest file serves to declare a python package as an Odoo module and to specify module metadata.

It is a file called `__manifest__.py` and contains a single Python dictionary, where each key specifies module metadatum.
    
    
    {
        'name': "A Module",
        'version': '1.0',
        'depends': ['base'],
        'author': "Author Name",
        'category': 'Category',
        'description': """
        Description text
        """,
        # data files always loaded at installation
        'data': [
            'views/mymodule_view.xml',
        ],
        # data files containing optionally loaded demonstration data
        'demo': [
            'demo/demo_data.xml',
        ],
    }
    

Available manifest fields are:

`name` (`str`, required)
    

the human-readable name of the module

`version` (`str`)
    

this module’s version, should follow [semantic versioning](https://semver.org/) rules

`description` (`str`)
    

extended description for the module, in reStructuredText

`author` (`str`)
    

name of the module author

`website` (`str`)
    

website URL for the module author

`license` (`str`, defaults: `LGPL-3`)
    

distribution license for the module. Possible values:

  * `GPL-2`

  * `GPL-2 or any later version`

  * `GPL-3`

  * `GPL-3 or any later version`

  * `AGPL-3`

  * `LGPL-3`

  * `Other OSI approved licence`

  * `OEEL-1` (Odoo Enterprise Edition License v1.0)

  * `OPL-1` (Odoo Proprietary License v1.0)

  * `Other proprietary`



`category` (`str`, default: `Uncategorized`)
    

classification category within Odoo, rough business domain for the module.

Although using [existing categories](https://github.com/odoo/odoo/blob/18.0/odoo/addons/base/data/ir_module_category_data.xml) is recommended, the field is freeform and unknown categories are created on-the-fly. Category hierarchies can be created using the separator `/` e.g. `Foo / Bar` will create a category `Foo`, a category `Bar` as child category of `Foo`, and will set `Bar` as the module’s category.

`depends` (`list(str)`)
    

Odoo modules which must be loaded before this one, either because this module uses features they create or because it alters resources they define.

When a module is installed, all of its dependencies are installed before it. Likewise dependencies are loaded before a module is loaded.

Nota

Module `base` is always installed in any Odoo instance. But you still need to specify it as dependency to make sure your module is updated when `base` is updated.

`data` (`list(str)`)
    

List of data files which must always be installed or updated with the module. A list of paths from the module root directory

`demo` (`list(str)`)
    

List of data files which are only installed or updated in _demonstration mode_

`auto_install` (`bool` or `list(str)`, default: `False`)
    

If `True`, this module will automatically be installed if all of its dependencies are installed.

It is generally used for «link modules» implementing synergetic integration between two otherwise independent modules.

For instance `sale_crm` depends on both `sale` and `crm` and is set to `auto_install`. When both `sale` and `crm` are installed, it automatically adds CRM campaigns tracking to sale orders without either `sale` or `crm` being aware of one another.

If it is a list, it must contain a subset of the dependencies. This module will automatically be installed as soon as all the dependencies in the subset are installed. The remaining dependencies will be automatically installed as well. If the list is empty, this module will always be automatically installed regardless of its dependencies and these will be installed as well.

`external_dependencies` (`dict(key=list(str))`)
    

A dictionary containing python and/or binary dependencies.

For python dependencies, the `python` key must be defined for this dictionary and a list of python modules to be imported should be assigned to it.

For binary dependencies, the `bin` key must be defined for this dictionary and a list of binary executable names should be assigned to it.

The module won’t be installed if either the python module is not installed in the host machine or the binary executable is not found within the host machine’s PATH environment variable.

`application` (`bool`, default: `False`)
    

Whether the module should be considered as a fully-fledged application (`True`) or is just a technical module (`False`) that provides some extra functionality to an existing application module.

`assets` (`dict`)
    

A definition of how all static files are loaded in various assets bundles. See the [assets](../frontend/assets.html#reference-assets) page for more details on how to describe bundles.

`installable` (`bool` default: `True`)
    

Whether a user should be able to install the module from the Web UI or not.

`maintainer` (`str`)
    

Person or entity in charge of the maintenance of this module, by default it is assumed that the author is the maintainer.

`{pre_init, post_init, uninstall}_hook` (`str`)
    

Hooks for module installation/uninstallation, their value should be a string representing the name of a function defined inside the module’s `__init__.py`.

`pre_init_hook` takes a cursor as its only argument, this function is executed prior to the module’s installation.

`post_init_hook` takes a cursor and a registry as its arguments, this function is executed right after the module’s installation.

`uninstall_hook` takes a cursor and a registry as its arguments, this function is executed after the module’s uninstallation.

These hooks should only be used when setup/cleanup required for this module is either extremely difficult or impossible through the api.

`active` (`bool`)
    

Deprecated. Replaced by `auto_install`.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/backend/module.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](security.html "Security in Odoo") |
  * [precedente](reports.html "QWeb Reports") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Module Manifests


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
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