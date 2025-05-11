# Navigation — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages.html "Pages") |
  * [precedente](layout.html "Layout") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Navigation



# Navigation¶

You can easily modify the navigation with the Website Builder to fit your needs.

In this chapter, you will learn how to:

  * Delete and create menu items.

  * Create a dropdown menu.

  * Create a mega menu.




## Default¶

Odoo automatically generates some basic menu items depending on the apps you installed. For example, the Website app adds two items to the main menu. These items are linked to pages, which are also automatically created.

Delete default menu items.

`/website_airproof/data/menu.xml`¶
    
    
    <!-- Contact us -->
    <delete model="website.menu" search="[('url','in', ['/', '/contactus']),
    ('website_id', '=', 1)]"/>
    
    <!-- Shop -->
    <delete model="website.menu" search="[('url','in', ['/', '/shop']),
    ('website_id', '=', 1)]"/>
    

## Menu item¶

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
    <record id="menu_about_us" model="website.menu">
        <field name="name">About us</field>
        <field name="url">/about-us</field>
        <field name="parent_id" search="[
            ('url', '=', '/default-main-menu'),
            ('website_id', '=', 1)]"/>
        <field name="website_id">1</field>
        <field name="sequence" type="int">10</field>
    </record>
    

Field | Description  
---|---  
name | Link text  
url | Value of the href attribute  
parent_id | The menu in which the item will be added.  
website_id | The website on which the item will be added.  
sequence | Defines the link’s position in the top menu.  
  
### New window¶

Open the link’s URL in a new tab.
    
    
    <record id="..." model="website.menu">
        <field name="new_window" eval="True"/>
    </record>
    

### External Links¶

Add a link to an external website.
    
    
    <record id="..." model="website.menu">
        <field name="url">https://www.odoo.com</field>
    </record>
    

### Anchor¶

Link to a specific section of a page.
    
    
    <record id="..." model="website.menu">
        <field name="url">/about-us#our-team</field>
    </record>
    

## Dropdown menu¶

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
    <record id="menu_services" model="website.menu">
        <field name="name">Services</field>
        <field name="website_id">1</field>
        <field name="parent_id" search="[
            ('url', '=', '/default-main-menu'),
            ('website_id', '=', 1)]"/>
        <field name="sequence" type="int">...</field>
    </record>
    

Add an item to a dropdown menu.
    
    
    <record id="menu_services_item_1" model="website.menu">
        <field name="name">Item 1</field>
        <field name="url">/dropdown/item-1</field>
        <field name="website_id">1</field>
        <field name="parent_id" ref="website_airproof.menu_services"/>
        <field name="sequence" type="int">...</field>
    </record>
    

Field | Description  
---|---  
parent_id | The dropdown in which the item will be added.  
  
## Mega menu¶

A mega menu is a dropdown menu with additional possibilities and not just a list of links. In a mega menu, you can use any kind of content (text, images, icons, …).

In Odoo, you can select a mega-menu template in the list. If you don’t need a custom layout, you can re-use the template structure in the `mega_menu_content` field like any static content.

**Declaration**

`/website_airproof/data/menu.xml`¶
    
    
     <record id="menu_mega_menu" model="website.menu">
         <field name="name">Mega Menu</field>
         <field name="parent_id" search="[
             ('url', '=', '/default-main-menu'),
             ('website_id', '=', 1)]"/>
         <field name="website_id">1</field>
         <field name="sequence" type="int">..</field>
         <field name="is_mega_menu" eval="True"/>
         <field name="mega_menu_classes">...</field>
         <field name="mega_menu_content" type="html">
             <section class="s_mega_menu_multi_menus py-4 o_colored_level o_cc o_cc1">
                 <div class="container">
                     <div class="row">
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">First Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Second Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Third Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                         <div class="col-12 col-sm py-2 text-center">
                             <h4 class="o_default_snippet_text">Last Menu</h4>
                             <nav class="nav flex-column">
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 1</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 2</a>
                                 <a href="#" class="nav-link o_default_snippet_text" data-name="Menu Item">Menu Item 3</a>
                             </nav>
                         </div>
                     </div>
                 </div>
             </section>
         </field>
     </record>
    

Field | Description  
---|---  
is_mega_menu | Enable the mega menu feature.  
mega_menu_classes | Custom classes to be added to the main element  
mega_menu_content | The default content of the mega menu  
  
Beside that, you might need to create something more visually advanced with a custom template. Feel free to check how the [standard templates](https://github.com/odoo/odoo/blob/18.0/addons/website/views/snippets/s_mega_menu_odoo_menu.xml) are built in the Odoo source code.

### Custom template¶

Create your own template and add it to the list.

**Layout**

`/website_airproof/views/website_templates.xml`¶
    
    
    <template id="s_mega_menu_airproof" name="Airproof" groups="base.group_user">
        <section class="s_mega_menu_airproof o_cc o_cc1 pt40">
            <!-- Content -->
        </section>
    </template>
    

**Option**

Use the following code to add an option for your new custom mega menu on the Website Builder.

`/website_airproof/data/presets.xml`¶
    
    
    <template id="snippet_options" inherit_id="website.snippet_options" name="Airproof - Mega Menu Options">
        <xpath expr="//*[@data-name='mega_menu_template_opt']/*" position="before">
            <t t-set="_label">Airproof</t>
            <we-button t-att-data-select-label="_label"
                data-select-template="website_airproof.s_mega_menu_airproof"
                data-img="/website_airproof/static/src/img/builder/header_opt.svg"
                t-out="_label"/>
        </xpath>
    </template>
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/howtos/website_themes/navigation.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages.html "Pages") |
  * [precedente](layout.html "Layout") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Navigation


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