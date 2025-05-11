# Patching code — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](error_handling.html "Error handling") |
  * [precedente](hooks.html "Hooks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Patching code



# Patching code¶

Sometimes, we need to customize the way the UI works. Many common needs are covered by some supported API. For example, all registries are good extension points: the field registry allows adding/removing specialized field components, or the main component registry allows adding components that should be displayed all the time.

However, there are situations for which it is not sufficient. In those cases, we may need to modify an object or a class in place. To achieve that, Odoo provides the utility function `patch`. It is mostly useful to override/update the behavior of some other component/piece of code that one does not control.

## Description¶

The patch function is located in `@web/core/utils/patch`:

patch(_objToPatch_ , _extension_)¶
    

Parametri
    

  * **objToPatch** (`object()`) – the object that should be patched

  * **extension** (`object()`) – an object mapping each key to an extension



Ritorna
    

a function to remove the patch

The `patch` function modifies in place the `objToPatch` object (or class) and applies all key/value described in the `extension` object. An unpatch function is returned, so it can be used to remove the patch later if necessary.

Most patch operations provide access to the parent value by using the native `super` keyword (see below in the examples).

## Patching a simple object¶

Here is a simple example of how an object can be patched:
    
    
    import { patch } from "@web/core/utils/patch";
    
    const object = {
      field: "a field",
      fn() {
        // do something
      },
    };
    
    patch(object, {
      fn() {
        // do things
      },
    });
    

When patching functions, we usually want to be able to access the `parent` function. To do so, we can simply use the native `super` keyword:
    
    
    patch(object, {
      fn() {
        super.fn(...arguments);
        // do other things
      },
    });
    

Avvertimento

`super` can only be used in a method not a function. This means that the following constructs are invalid for javascript.
    
    
    const obj = {
      a: function () {
        // Throws: "Uncaught SyntaxError: 'super' keyword unexpected here"
        super.a();
      },
      b: () => {
        // Throws: "Uncaught SyntaxError: 'super' keyword unexpected here"
        super.b();
      },
    };
    

Getters and setters are supported too:
    
    
    patch(object, {
      get number() {
        return super.number / 2;
      },
      set number(value) {
        super.number = value;
      },
    });
    

## Patching a javascript class¶

The `patch` function is designed to work with anything: object or ES6 class.

However, since javascript classes work with the prototypal inheritance, when one wishes to patch a standard method from a class, then we actually need to patch the `prototype`:
    
    
    class MyClass {
      static myStaticFn() {...}
      myPrototypeFn() {...}
    }
    
    // this will patch static properties!!!
    patch(MyClass, {
      myStaticFn() {...},
    });
    
    // this is probably the usual case: patching a class method
    patch(MyClass.prototype, {
      myPrototypeFn() {...},
    });
    

Also, Javascript handles the constructor in a special native way which makes it impossible to be patched. The only workaround is to call a method in the original constructor and patch that method instead:
    
    
    class MyClass {
      constructor() {
        this.setup();
      }
      setup() {
        this.number = 1;
      }
    }
    
    patch(MyClass.prototype, {
      setup() {
        super.setup(...arguments);
        this.doubleNumber = this.number * 2;
      },
    });
    

Avvertimento

It is impossible to patch directly the `constructor` of a class!

## Patching a component¶

Components are defined by javascript classes, so all the information above still holds. For these reasons, Owl components should use the `setup` method, so they can easily be patched as well (see the section on [best practices](owl_components.html#frontend-owl-best-practices)).
    
    
    patch(MyComponent.prototype, {
      setup() {
        useMyHook();
      },
    });
    

## Removing a patch¶

The `patch` function returns its counterpart. This is mostly useful for testing purposes, when we patch something at the beginning of a test, and unpatch it at the end.
    
    
    const unpatch = patch(object, { ... });
    // test stuff here
    unpatch();
    

## Applying the same patch to multiple objects¶

It could happen that one wants to apply the same patch to multiple objects but because of the way the `super` keyword works, the `extension` can only be used for patching once and cannot be copied/cloned ([check the documentation of the keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super#description)). A function returning the object used to patch can be used to make it unique.
    
    
    const obj1 = {
      method() {
        doSomething();
      },
    };
    
    const obj2 = {
      method() {
        doThings();
      },
    };
    
    function createExtensionObj() {
      return {
        method() {
          super.method();
          doCommonThings();
        },
      };
    }
    
    patch(obj1, createExtensionObj());
    patch(obj2, createExtensionObj());
    

Avvertimento

If an `extension` is based on another then the two extensions should be applied separately. Do not copy/clone an extension.
    
    
    const object = {
      method1() {
        doSomething();
      },
      method2() {
        doAnotherThing();
      },
    };
    
    const ext1 = {
      method1() {
        super.method1();
        doThings();
      },
    };
    
    const invalid_ext2 = {
      ...ext1, // this will not work: super will not refer to the correct object in methods coming from ext1
      method2() {
        super.method2();
        doOtherThings();
      },
    };
    
    patch(object, invalid_ext2);
    object.method1(); // throws: Uncaught TypeError: (intermediate value).method1 is not a function
    
    const valid_ext2 = {
      method2() {
        super.method2();
        doOtherThings();
      },
    };
    
    patch(object, ext1); // first patch base extension
    patch(object, valid_ext2); // then the new one
    object.method1(); // works as expected
    

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/frontend/patching_code.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](error_handling.html "Error handling") |
  * [precedente](hooks.html "Hooks") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * Patching code


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