# Mobile JavaScript — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](qweb.html "QWeb Templates") |
  * [precedente](javascript_reference.html "Javascript Reference") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Mobile JavaScript



# Mobile JavaScript¶

## Introduction¶

In Odoo 10.0 we released a mobile app which allows you to access all **Odoo apps** (even your customized modules).

The application is a combination of **Odoo Web** and **Native Mobile components**. In other words it is a Odoo Web instance loaded inside a native, mobile, WebView container.

This page documents how you can access mobile native components like Camera, Vibration, Notification and Toast through Odoo Web (via JavaScript). For this, you do not need to be a mobile developer, if you know Odoo JavaScript API you can access all available mobile features.

Avvertimento

These features work with **Odoo Enterprise 10.0+** only

## How does it work?¶

Internal workings of the mobile application:

Of course, it is a web page that loads on a Mobile Native Web container. But it is integrated in such a way that you can access native resources from your web JavaScript.

WebPages (Odoo Web) is on the top of each layer, where the second layer is a Bridge between Odoo Web (JS) and the native mobile components.

When any call from JavaScript is triggered it passes through Bridge and Bridge passes it to the native invoker to perform that action.

When the native component has done its work, it is passed to the Bridge again and you get the output in JavaScript.

Process time taken by the Native component depends on what you are requesting from the Native resources. For example the Camera or GPS Location.

## How to use it?¶

Just like the Odoo Web Framework, the Mobile API can be used anywhere by getting the object from **web_mobile.rpc**

The mobile RPC object provides a list of methods that are available (this only works with the mobile app).

Check if the method is available and then execute it.

### Methods¶

Nota

Each of the methods returns a JQuery Deferred object which returns a data JSON dictionary

#### Show Toast in device¶

showToast()¶
    

Parametri
    

  * **args** (`object()`) – **message** text to display




A toast provides simple feedback about an operation in a small popup. It only fills the amount of space required for the message and the current activity remains visible and interactive.
    
    
    mobile.methods.showToast({'message': 'Message sent'});
    

#### Vibrating device¶

vibrate()¶
    

Parametri
    

  * **args** (`object()`) – Vibrates constantly for the specified period of time (in milliseconds).




Vibrate mobile device with given duration.
    
    
    mobile.methods.vibrate({'duration': 100});
    

#### Show snackbar with action¶

showSnackBar()¶
    

Parametri
    

  * **args** (`object()`) – (_required_) **Message** to show in snackbar and action **button label** in Snackbar (optional)



Ritorna
    

`True` if the user clicks on the Action button, `False` if SnackBar auto dismissed after some time.

Snackbars provide lightweight feedback about an operation. They show a brief message at the bottom of the screen on mobile or in the lower left corner on larger devices. Snackbars appear above all the other elements on the screen and only one can be displayed at a time.
    
    
    mobile.methods.showSnackBar({'message': 'Message is deleted', 'btn_text': 'Undo'}).then(function(result){
        if(result){
            // Do undo operation
        }else{
            // Snack Bar dismissed
        }
    });
    

#### Showing notification¶

showNotification()¶
    

Parametri
    

  * **args** (`object()`) – **title** (first row) of the notification, **message** (second row) of the notification, in a standard notification.




A notification is a message you can display to the user outside of your application’s normal UI. When you tell the system to issue a notification, it first appears as an icon in the notification area. To see the details of the notification, the user opens the notification drawer. Both the notification area and the notification drawer are system-controlled areas that the user can view at any time.
    
    
    mobile.showNotification({'title': 'Simple Notification', 'message': 'This is a test for a simple notification'})
    

#### Create contact in device¶

addContact()¶
    

Parametri
    

  * **args** (`object()`) – Dictionary with contact details. Possible keys (name, mobile, phone, fax, email, website, street, street2, country_id, state_id, city, zip, parent_id, function and image)




Create a new device contact with the given contact details.
    
    
    var contact = {
        'name': 'Michel Fletcher',
        'mobile': '9999999999',
        'phone': '7954856587',
        'fax': '765898745',
        'email': 'michel.fletcher@agrolait.example.com',
        'website': 'http://www.agrolait.com',
        'street': '69 rue de Namur',
        'street2': false,
        'country_id': [21, 'Belgium'],
        'state_id': false,
        'city': 'Wavre',
        'zip': '1300',
        'parent_id': [8, 'Agrolait'],
        'function': 'Analyst',
        'image': '<<BASE 64 Image Data>>'
    }
    
    mobile.methods.addContact(contact);
    

#### Scanning barcodes¶

scanBarcode()¶
    

Ritorna
    

Scanned `code` from any barcode

The barcode API detects barcodes in real-time, on the device, in any orientation.

The barcode API can read the following barcode formats:

  * 1D barcodes: EAN-13, EAN-8, UPC-A, UPC-E, Code-39, Code-93, Code-128, ITF, Codabar

  * 2D barcodes: QR Code, Data Matrix, PDF-417, AZTEC



    
    
    mobile.methods.scanBarcode().then(function(code){
        if(code){
            // Perform operation with the scanned code
        }
    });
    

#### Switching account in device¶

switchAccount()¶
    

Use switchAccount to switch from one account to another on the device.
    
    
    mobile.methods.switchAccount();
    

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/frontend/mobile.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](qweb.html "QWeb Templates") |
  * [precedente](javascript_reference.html "Javascript Reference") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Mobile JavaScript


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