# Shapes — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gradients.html "Gradients") |
  * [precedente](building_blocks.html "Building blocks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Shapes



# Shapes¶

Shapes are handy if you want to add personality to your website.

In this chapter, you will learn how to add standard and custom background and image shapes.

## Background shapes¶

Background shapes are SVG files that you can add as a decorative background in your different sections. Each shape has one or several customizable colors, and some of them are animated.

Avvertimento

Odoo’s default shapes use the Odoo default colors palette map as reference. This way, colors will be automatically adapted to a new palette everytime it changes:
    
    
    default_palette = {
        '1': '#3AADAA',
        '2': '#7C6576',
        '3': '#F6F6F6',
        '4': '#FFFFFF',
        '5': '#383E45',
    }
    

### Standard¶

A large selection of default background shapes is available.

**Use**
    
    
    <section data-oe-shape-data="{'shape':'web_editor/Zigs/06'}">
        <div class="o_we_shape o_web_editor_Zigs_06"/>
        <div class="container">
            <!-- Content -->
         </div>
    </section>
    

`data-oe-shape-data` is a JSON object containing information about your shape like the location of the SVG file, the repeat and flip options, etc.

For example, you can **flip the shape** horizontally or vertically by using the X or Y axis like this:
    
    
    <section data-oe-shape-data="{'shape':'web_editor/Zigs/06','flip':[x,y]}">
        <div class="o_we_shape o_we_flip_x o_we_flip_y o_web_editor_Zigs_06"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

#### Colors mapping¶

You can also change the default colors mapping of your shape either by switching colors in the current map or by creating a alternate map without modifying the initial one.

##### Switch colors mapping¶

First, we can use a shape like this:
    
    
    <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" preserveAspectRatio="none" width="100%" height="100%">
        <defs>
            <svg id="zigs06_top" viewBox="0 0 30 30" preserveAspectRatio="xMinYMin meet" fill="#383E45" width="100%">
                <path d="M30,7.9C22.5,7.9,22.5,20,15,20S7.5,7.9,0,7.9V0h30V7.9z"/>
            </svg>
            <svg id="zigs06_bottom" viewBox="0 0 30 30" preserveAspectRatio="xMinYMax meet" fill="#FFFFFF" width="100%">
                <path d="M0,22.1C7.5,22.1,7.5,10,15,10s7.5,12.1,15,12.1V30H0V22.1z"/>
            </svg>
        </defs>
        <svg>
            <use xlink:href="#zigs06_top"/>
            <use xlink:href="#zigs06_bottom"/>
        </svg>
    </svg>
    

Here, we use `#383E45` and `#FFFFFF` which corresponds to the 5th and 4th colors in the Odoo’s default color palette.

The shape is declared as follows in SCSS:

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    'Zigs/06': ('position': bottom, 'size': 30px 100%, 'colors': (4, 5), 'repeat-x': true),
    

The blackish color is used at the top (`c5`), the lightish (`c4`) at the bottom and in between, the shape is simply transparent.

We are going to rewrite the `colors` map with some `key: value` couples:

**With color palette reference and custom color**

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
     $o-bg-shapes: change-shape-colors-mapping('web_editor', 'Zigs/06', (4: 3, 5: rgb(187, 27, 152)))
    

**Or just with references**

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
     $o-bg-shapes: change-shape-colors-mapping('web_editor', 'Zigs/06', (4: 3, 5: 1));
    

The `c4` (white) will be replaced by `c3` (whitish) and `c5` (black) by `c1` (white).

**Results**

##### Add extra colors mapping¶

Adding extra color mapping allows you to add a color variant to the template of a shape while keeping the original.

`/website_airproof/static/src/scss/boostrap_overridden.scss`¶
    
    
    $o-bg-shapes: add-extra-shape-colors-mapping('web_editor', 'Zigs/06', 'second', (4: 3, 5: 1));
    
    
    
    <section data-oe-shape-data="{'shape':'web_editor/Zigs/06'}">
        <div class="o_we_shape o_web_editor_Zigs_06 o_second_extra_shape_mapping"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

### Custom¶

Sometimes, your design might require creating one or several custom shapes.

Firstly, you need to create an SVG file for your shape.

`/website_airproof/static/shapes/hexagons/01.svg`¶
    
    
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="86" height="100">
        <polygon points="0 25, 43 0, 86 25, 86 75, 43 100, 0 75" style="fill: #3AADAA;"/>
    </svg>
    

Make sure to use colors from the default Odoo palette for your shape (as explained above).
    
    
    default_palette = {
        '1': '#3AADAA',
        '2': '#7C6576',
        '3': '#F6F6F6',
        '4': '#FFFFFF',
        '5': '#383E45',
    }
    

#### Attachment¶

Declare your shape file.

`/website_airproof/data/shapes.xml`¶
    
    
    <record id="shape_hexagon_01" model="ir.attachment">
        <field name="name">01.svg</field>
        <field name="datas" type="base64" file="website_airproof/static/shapes/hexagons/01.svg"/>
        <field name="url">/web_editor/shape/illustration/hexagons/01.svg</field>
        <field name="public" eval="True"/>
    </record>
    

Field | Description  
---|---  
name | Name of the shape  
datas | Path to the shape  
url | The location of your shape in the web editor. The file is automatically duplicated in `/web_editor/shape/illustration` by the Website Builder.  
public | Makes the shape available for later editing.  
  
#### SCSS¶

Define the styles of your shape.

`/website_airproof/static/src/scss/primary_variables.scss`¶
    
    
    $o-bg-shapes: map-merge($o-bg-shapes,
        (
            'illustration': map-merge(
                map-get($o-bg-shapes, 'illustration') or (),
                (
                    'hexagons/01': ('position': center center, 'size': auto 100%, 'colors': (1), 'repeat-x': true, 'repeat-y': true),
                ),
            ),
        )
    );
    

Key | Description  
---|---  
File location | `hexagons/01` corresponds to the location of your file in the `shapes` folder.  
position | Defines the position of your shape.  
size | Defines the size of your shape.  
colors | Defines the color c* you want it to have (this will override the color you specified in your SVG).  
repeat-x | Defines if the shape is repeated horizontally. This key is optional and only needs to be defined if set to `true`.  
repeat-y | Defines if the shape is repeated vertically. This key is optional and only needs to be defined if set to `true`.  
  
#### Add the option¶

Lastly, add your shape to the list of shapes available on the Website Builder.

`/website_airproof/views/snippets/options.xml`¶
    
    
    <template id="snippet_options_background_options" inherit_id="website.snippet_options_background_options" name="Shapes">
        <xpath expr="//*[hasclass('o_we_shape_menu')]/*[last()]" position="after">
            <we-select-page string="Theme">
                <we-button data-shape="illustration/hexagons/01" data-select-label="Hexagon 01"/>
            </we-select-page>
        </xpath>
    </template>
    

#### Use it into your pages¶

In your XML pages, you can use your shape in the same way as the others.
    
    
    <section class="..." data-oe-shape-data="{'shape': 'illustration/hexagons/01', 'colors': 'c4': '#8595A2', 'c5': 'rgba(0, 255, 0)'}">
        <div class="o_we_shape o_illustration_hexagons_01"/>
        <div class="container">
            <!-- Content -->
        </div>
    </section>
    

You can also redefine colors using the `data-oe-shape-data attribute`, but this is optional.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/website_themes/shapes.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gradients.html "Gradients") |
  * [precedente](building_blocks.html "Building blocks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Shapes


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