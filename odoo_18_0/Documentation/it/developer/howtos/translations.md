# Translating Modules — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](connect_device.html "Connect with a device") |
  * [precedente](accounting_localization.html "Accounting localization") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Translating Modules



# Translating Modules¶

This section explains how to provide translation abilities to your module.

Nota

If you want to contribute to the translation of Odoo itself, please refer to the [Odoo Wiki page](https://github.com/odoo/odoo/wiki/Translations).

## Exporting translatable term¶

A number of terms in your modules are implicitly translatable. As a result, even if you haven’t done any specific work towards translation, you can export your module’s translatable terms and may find content to work with.

Translations export is performed via the administration interface by logging into the backend interface and opening Settings ‣ Translations ‣ Import / Export ‣ Export Translations

  * leave the language to the default (new language/empty template)

  * select the [PO File](https://en.wikipedia.org/wiki/Gettext#Translating) format

  * select your module

  * click Export and download the file




This gives you a file called `_yourmodule_.pot` which should be moved to the `_yourmodule_ /i18n/` directory. The file is a _PO Template_ which simply lists translatable strings and from which actual translations (PO files) can be created. PO files can be created using [msginit](https://www.gnu.org/software/gettext/manual/gettext.html#Creating), with a dedicated translation tool like [POEdit](https://poedit.net/) or by simply copying the template to a new file called `_language_.po`. Translation files should be put in `_yourmodule_ /i18n/`, next to `_yourmodule_.pot`, and will be automatically loaded by Odoo when the corresponding language is installed (via Settings ‣ Translations ‣ Languages)

Nota

translations for all loaded languages are also installed or updated when installing or updating a module

## Implicit exports¶

Odoo automatically exports translatable strings from «data»-type content:

  * in non-QWeb views, all text nodes are exported as well as the content of the `string`, `help`, `sum`, `confirm` and `placeholder` attributes

  * QWeb templates (both server-side and client-side), all text nodes are exported except inside `t-translation="off"` blocks, the content of the `title`, `alt`, `label` and `placeholder` attributes are also exported

  * for [`Field`](../reference/backend/orm.html#odoo.fields.Field "odoo.fields.Field"), unless their model is marked with `_translate = False`:

    * their `string` and `help` attributes are exported

    * if `selection` is present and a list (or tuple), it’s exported

    * if their `translate` attribute is set to `True`, all of their existing values (across all records) are exported

  * help/error messages of `_constraints` and `_sql_constraints` are exported




## Explicit exports¶

When it comes to more «imperative» situations in Python code or Javascript code, Odoo cannot automatically export translatable terms so they must be marked explicitly for export. This is done by wrapping a literal string in a function call.

In Python, the wrapping function is `odoo.api.Environment._()` and `odoo.tools.translate._()`:
    
    
    title = self.env._("Bank Accounts")
    
    # old API for backward-compatibility
    from odoo.tools import _
    title = _("Bank Accounts")
    

In JavaScript, the wrapping function is generally `odoo.web._t()`:
    
    
    title = _t("Bank Accounts");
    

Avvertimento

Only literal strings can be marked for exports, not expressions or variables. For situations where strings are formatted, this means the format string must be marked, not the formatted string

The lazy version of `_` and `_t` is the `odoo.tools.translate.LazyTranslate` factory in python and `odoo.web._lt()` in javascript. The translation lookup is executed only at rendering and can be used to declare translatable properties in class methods of global variables.
    
    
    from odoo.tools import LazyTranslate
    _lt = LazyTranslate(__name__)
    LAZY_TEXT = _lt("some text")
    

Nota

Translations of a module are **not** exposed to the front end by default and thus are not accessible from JavaScript. In order to achieve that, the module name has to be either prefixed with `website` (just like `website_sale`, `website_event` etc.) or explicitly register by implementing `_get_translation_frontend_modules_name()` for the `ir.http` model.

This could look like the following:
    
    
    from odoo import models
    
    class IrHttp(models.AbstractModel):
        _inherit = 'ir.http'
    
        @classmethod
        def _get_translation_frontend_modules_name(cls):
            modules = super()._get_translation_frontend_modules_name()
            return modules + ['your_module']
    

### Context¶

To translate, the translation function needs to know the _language_ and the _module_ name. When using `Environment._` the language is known and you may pass the module name as a parameter, otherwise it’s extracted from the caller.

In case of `odoo.tools.translate._`, the language and the module are extracted from the context. For this, we inspect the caller’s local variables. The drawback of this method is that it is error-prone: we try to find the context variable or `self.env`, however these may not exist if you use translations outside of model methods; i.e. it does not work inside regular functions or python comprehensions.

Lazy translations are bound to the module during their creation and the language is resolved when evaluating using `str()`. Note that you can also pass a lazy translation to `Envionrment._` to translate it without any magic language resolution.

### Variables¶

**Don’t** the extract may work but it will not translate the text correctly:
    
    
    _("Scheduled meeting with %s" % invitee.name)
    

**Do** set the dynamic variables as a parameter of the translation lookup (this will fallback on source in case of missing placeholder in the translation):
    
    
    _("Scheduled meeting with %s", invitee.name)
    

### Blocks¶

**Don’t** split your translation in several blocks or multiples lines:
    
    
    # bad, trailing spaces, blocks out of context
    _("You have ") + len(invoices) + _(" invoices waiting")
    _t("You have ") + invoices.length + _t(" invoices waiting");
    
    # bad, multiple small translations
    _("Reference of the document that generated ") + \
    _("this sales order request.")
    

**Do** keep in one block, giving the full context to translators:
    
    
    # good, allow to change position of the number in the translation
    _("You have %s invoices wainting") % len(invoices)
    _.str.sprintf(_t("You have %s invoices wainting"), invoices.length);
    
    # good, full sentence is understandable
    _("Reference of the document that generated " + \
      "this sales order request.")
    

### Plural¶

**Don’t** pluralize terms the English-way:
    
    
    msg = _("You have %(count)s invoice", count=invoice_count)
    if invoice_count > 1:
      msg += _("s")
    

**Do** keep in mind every language has different plural forms:
    
    
    if invoice_count > 1:
      msg = _("You have %(count)s invoices", count=invoice_count)
    else:
      msg = _("You have one invoice")
    

### Read vs Run Time¶

**Don’t** invoke translation lookup at server launch:
    
    
    ERROR_MESSAGE = {
      # bad, evaluated at server launch with no user language
      'access_error': _('Access Error'),
      'missing_error': _('Missing Record'),
    }
    
    class Record(models.Model):
    
      def _raise_error(self, code):
        raise UserError(ERROR_MESSAGE[code])
    

**Don’t** invoke translation lookup when the javascript file is read:
    
    
    # bad, js _t is evaluated too early
    var core = require('web.core');
    var _t = core._t;
    var map_title = {
        access_error: _t('Access Error'),
        missing_error: _t('Missing Record'),
    };
    

**Do** use lazy translation lookup method:
    
    
    ERROR_MESSAGE = {
      'access_error': _lt('Access Error'),
      'missing_error': _lt('Missing Record'),
    }
    
    class Record(models.Model):
    
      def _raise_error(self, code):
        # translation lookup executed at error rendering
        raise UserError(ERROR_MESSAGE[code])
    

or **do** evaluate dynamically the translatable content:
    
    
    # good, evaluated at run time
    def _get_error_message(self):
      return {
        access_error: _('Access Error'),
        missing_error: _('Missing Record'),
      }
    

**Do** in the case where the translation lookup is done when the JS file is _read_ , use `_lt` instead of `_t` to translate the term when it is _used_ :
    
    
    # good, js _lt is evaluated lazily
    var core = require('web.core');
    var _lt = core._lt;
    var map_title = {
        access_error: _lt('Access Error'),
        missing_error: _lt('Missing Record'),
    };
    

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/howtos/translations.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](connect_device.html "Connect with a device") |
  * [precedente](accounting_localization.html "Accounting localization") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Translating Modules


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