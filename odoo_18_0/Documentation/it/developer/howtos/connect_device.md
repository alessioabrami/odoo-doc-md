# Connect with a device — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](upgrade_custom_db.html "Upgrade a customized database") |
  * [precedente](translations.html "Translating Modules") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Connect with a device



# Connect with a device¶

IoT Drivers allow any Odoo module to communicate in real-time with any device connected to the IoT Box. Communication with the IoT Box goes both ways, so the Odoo client can send commands to and receive information from any of the supported devices.

To add support for a device, all we need is:

  * an `Interface`, to detect connected devices of a specific type

  * a `Driver`, to communicate with an individual device




At each boot, the IoT Box will load all of the Interfaces and Drivers that can be located on the connected Odoo instance. Each module can contain an `iot_handlers` directory that will be copied to the IoT Box. The structure of this directory is the following
    
    
    your_module
    ├── ...
    └── iot_handlers
        ├── drivers
        │   ├── DriverName.py
        │   └── ...
        │
        └── interfaces
            ├── InterfaceName.py
            └── ...
    

## Detect Devices¶

Devices connected to the IoT Box are detected through `Interfaces`. There is an Interface for each supported connection type (USB, Bluetooth, Video, Printers, Serial, etc.). The interface maintains a list of detected devices and associates them with the right Driver.

Supported devices will appear both on the IoT Box Homepage that you can access through its IP address and in the IoT module of the connected Odoo instance.

### Interface¶

The role of the Interface is to maintain a list of devices connected through a determined connection type. Creating a new interface requires

  * Extending the `Interface` class

  * Setting the `connection_type` class attribute

  * Implementing the `get_devices` method, that should return a dictionary containing data about each detected device. This data will be given as argument to the constructors and `supported` method of the Drivers.




Nota

Setting the `_loop_delay` attribute will modify the interval between calls to `get_devices`. By default, this interval is set to 3 seconds.
    
    
    from odoo.addons.hw_drivers.interface import Interface
    
    class InterfaceName(Interface):
        connection_type = 'ConnectionType'
    
        def get_devices(self):
            return {
                'device_identifier_1': {...},
                ...
            }
    

### Driver¶

Once the interface has retrieved the list of detected devices, it will loop through all of the Drivers that have the same `connection_type` attribute and test their respective `supported` method on all detected devices. If the supported method of a Driver returns `True`, an instance of this Driver will be created for the corresponding device.

Nota

`supported` methods of drivers are given a priority order. The `supported` method of a child class will always be tested before the one of its parent. This priority can be adjusted by modifying the `priority` attribute of the Driver.

Creating a new Driver requires:

  * Extending `Driver`

  * Setting the `connection_type` class attribute.

  * Setting the `device_type`, `device_connection` and `device_name` attributes.

  * Defining the `supported` method



    
    
    from odoo.addons.hw_drivers.driver import Driver
    
    class DriverName(Driver):
        connection_type = 'ConnectionType'
    
        def __init__(self, identifier, device):
            super(NewDriver, self).__init__(identifier, device)
            self.device_type = 'DeviceType'
            self.device_connection = 'DeviceConnection'
            self.device_name = 'DeviceName'
    
        @classmethod
        def supported(cls, device):
            ...
    

## Communicate With Devices¶

Once your new device is detected and appears in the IoT module, the next step is to communicate with it. Since the box only has a local IP address, it can only be reached from the same local network. Communication, therefore, needs to happen on the browser-side, in JavaScript.

The process depends on the direction of the communication: \- From the browser to the box, through Actions \- From the box to the browser, through Longpolling

Both channels are accessed from the same JS object, the `DeviceProxy`, which is instantiated using the IP of the IoT Box and the device identifier.
    
    
    var DeviceProxy = require('iot.DeviceProxy');
    
    var iot_device = new DeviceProxy({
        iot_ip: iot_ip,
        identifier: device_identifier
    });
    

### Actions¶

Actions are used to tell a selected device to execute a specific action, such as taking a picture, printing a receipt, etc.

Nota

It must be noted that no “answer” will be sent by the box on this route, only the request status. The answer to the action, if any, has to be retrieved via the longpolling.

An action can be performed on the DeviceProxy Object.
    
    
    iot_device.action(data);
    

In your driver, define an `action` method that will be executed when called from an Odoo module. It takes the data given during the call as argument.
    
    
    def action(self, data):
        ...
    

### Longpolling¶

When any module in Odoo wants to read data from a specific device, it creates a listener identified by the IP/domain of the box and the device identifier and passes it a callback function to be called every time the device status changes. The callback is called with the new data as argument.
    
    
    iot_device.add_listener(this._onValueChange.bind(this));
    
    _onValueChange: function (result) {
        ...
    }
    

In the Driver, an event is released by calling the `device_changed` function from the `event_manager`. All callbacks set on the listener will then be called with `self.data` as argument.
    
    
    from odoo.addons.hw_drivers.event_manager import event_manager
    
    class DriverName(Driver):
        connection_type = 'ConnectionType'
    
        def methodName(self):
            self.data = {
                'value': 0.5,
                ...
            }
            event_manager.device_changed(self)
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/howtos/connect_device.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](upgrade_custom_db.html "Upgrade a customized database") |
  * [precedente](translations.html "Translating Modules") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Connect with a device


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