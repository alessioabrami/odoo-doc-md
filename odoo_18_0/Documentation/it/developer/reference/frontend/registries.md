# Registries — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](services.html "Services") |
  * [precedente](owl_components.html "Owl components") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Registries



# Registries¶

Registries are (ordered) key/value maps. They are the main web client extension points: many features provided by the Odoo javascript framework simply look up into a registry whenever it needs a definition for some object (such as fields, views, client actions or services). Customizing the web client is then simply done by adding specific values in the correct registry.
    
    
    import { Registry } from "@web/core/registry";
    
    const myRegistry = new Registry();
    
    myRegistry.add("hello", "odoo");
    
    console.log(myRegistry.get("hello"));
    

A useful feature of registries is that they maintain a set of sub registries, obtained by the `category` method. If the sub registry does not exist yet, it is created on the fly. All registries used by the web client are obtained in such a way from one root registry, exported in `@web/core/registry`.
    
    
    import { registry } from "@web/core/registry";
    
    const fieldRegistry = registry.category("fields");
    const serviceRegistry = registry.category("services");
    const viewRegistry = registry.category("views");
    

## Registry API¶

_class _Registry()¶
    

Creates a new registry. Note that a registry is an event bus, so one can listen to the `UPDATE` event if necessary. Registries are ordered: the `getAll` method returns a list of values ordered according to their sequence number.

Registry.add(_key_ , _value_[, _options_])¶
    

Parametri
    

  * **key** (`string()`) – key for the new entry

  * **value** (`any()`) – value for the new entry

  * **options** (`Object()`) – options

  * **[options.force]** (`boolean()`) – do not throw if key already exists

  * **[options.sequence]** (`number()`) – sequence number (useful to order entries)



Ritorna
    

Registry

Inserts a value at a specific key. If the key is already used, this method throws an error (unless the option `force` is set to true). The option `sequence` is useful to insert the value at a specific position. This method also triggers an `UPDATE` event.

Returns the same registry, so `add` method calls can be chained.

Registry.get(_key_[, _defaultValue_])¶
    

Parametri
    

  * **key** (`string()`) – key for the entry

  * **any** (`defaultValue()`) – return value if no entry for key exists




Returns the value corresponding to the `key` argument. If the registry does not contain that key, this method returns `defaultValue` if given, or throws an error otherwise.

Registry.contains(_key_)¶
    

Parametri
    

  * **key** (`string()`) – key for the entry



Ritorna
    

boolean

Returns `true` if `key` is present in the registry

Registry.getAll()¶
    

Ritorna
    

any[]

Returns the list of all elements in the registry. It is ordered according to the sequence numbers.

Registry.remove(_key_)¶
    

Parametri
    

  * **key** (`string()`) – the key for the entry that should be removed




Removes a key/value pair from the registry. This operation triggers an `UPDATE` event.

Registry.category(_subcategory_)¶
    

Parametri
    

  * **subcategory** (`string()`) – the name for the sub category



Ritorna
    

Registry

Returns the sub registry associated with the `subcategory`. If it does not exist yet, the sub registry is created on the fly.

## Reference List¶

Category | Content  
---|---  
effects | implementation for all available effects  
formatters | utility functions to format values (mostly used for field values)  
main_components | top level components  
parsers | utility functions to parse values (mostly used for field values)  
services | all services that should be activated  
systray | components displayed in the systray zone in the navbar  
user_menuitems | menu items displayed in the user menu (top right of navbar)  
  
### Effect registry¶

The `effects` registry contains the implementations of all available effects. See the section on the [effect service](services.html#frontend-services-effect-registry) for more details.

### Formatter registry¶

The `formatters` registry contains functions to format values. Each formatter has the following API:

format(_value_[, _options_])¶
    

Parametri
    

  * **value** (`T | false()`) – a value of a specific type, or `false` if no value is given

  * **options** (`Object()`) – various options



Ritorna
    

string

Formats a value and returns a string

Vedi anche

  * Parsers registry




### Main components registry¶

The main component registry (`main_components`) is useful for adding top level components in the web client. The webclient has a `MainComponentsContainer` as direct child. This component is basically a live representation of the ordered list of components registered in the main components registry.

API
    
    
    
    interface {
        Component: Owl Component class
        props?: any
    }
    

For example, the `LoadingIndicator` component can be added in the registry like this:
    
    
    registry.category("main_components").add("LoadingIndicator", {
      Component: LoadingIndicator,
    });
    

### Parser registry¶

The `parsers` registry contains functions to parse values. Each parser has the following API:

parse(_value_[, _options_])
    

Parametri
    

  * **value** (`string()`) – a string representing a value

  * **options** (`Object()`) – various options (parser specific)



Ritorna
    

T a valid value

Parses a string and returns a value. If the string does not represent a valid value, parsers can fail and throw errors.

Vedi anche

  * Formatters registry




### Service registry¶

The service registry (category: `services`) contains all [services](services.html#frontend-services) that should be activated by the Odoo framework.
    
    
    import { registry } from "@web/core/registry";
    
    const myService = {
        dependencies: [...],
        start(env, deps) {
            // some code here
        }
    };
    
    registry.category("services").add("myService", myService);
    

### Systray registry¶

The systray is the zone on the right of the navbar that contains various small components, that usually display some sort of information (like the number of unread messages), notifications and/or let the user interact with them.

The `systray` registry contains a description of these systray items, as objects with the following three keys:

  * `Component`: the component class that represents the item. Its root element should be a `<li>` tag, otherwise it might not be styled properly.

  * `props (optional)`: props that should be given to the component

  * `isDisplayed (optional)`: a function that takes the [env](framework_overview.html#frontend-framework-environment) and returns a boolean. If true, the systray item is displayed. Otherwise it is removed.




For example:
    
    
    import { registry } from "@web/core/registry";
    
    class MySystrayItem extends Component {
        // some component ...
    }
    
    registry.category("systray").add("myAddon.myItem", {
        Component: MySystrayItem,
    });
    

The systray registry is an ordered registry (with the `sequence` number):
    
    
    const item = {
        Component: MySystrayItem
    };
    registry.category("systray").add("myaddon.some_description", item, { sequence: 43 });
    

The sequence number defaults to 50. If given, this number will be used to order the items. The lowest sequence is on the right and the highest sequence is on the left in the systray menu.

### Usermenu registry¶

The user menu registry (category: `user_menuitems`) contains all menu items that are shown when opening the user menu (the navbar element with the user name, on the top right).

User menu items are defined by a function taking the [env](framework_overview.html#frontend-framework-environment) and returning a plain object, containing the following information:

  * `description` : the menu item text,

  * `href` : (optional) if given (and truthy), the item text is put in a `a` tag with given attribute href,

  * `callback` : callback to call when the item is selected,

  * `hide`: (optional) indicates if the item should be hidden (default: `false`),

  * `sequence`: (optional) determines the rank of the item among the other dropwdown items (default: 100).




The user menu calls all the functions defining items every time it is opened.

Example:
    
    
    import { registry } from "@web/core/registry";
    
    registry.category("user_menuitems").add("my item", (env) => {
        return {
            description: env._t("Technical Settings"),
            callback: () => { env.services.action_manager.doAction(3); },
            hide: (Math.random() < 0.5),
        };
    });
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/reference/frontend/registries.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](services.html "Services") |
  * [precedente](owl_components.html "Owl components") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Registries


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