# Payment Provider — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_token.html "Payment Token") |
  * [precedente](payment_method.html "Payment Method") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Provider



# Payment Provider¶

_class _odoo.addons.payment.models.payment_provider.PaymentProvider[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L14)¶
    

_compute_feature_support_fields()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L218)¶
    

Compute the feature support fields based on the provider.

Feature support fields are used to specify which additional features are supported by a given provider. These fields are as follows:

  * `support_express_checkout`: Whether the «express checkout» feature is supported. `False` by default.

  * `support_manual_capture`: Whether the «manual capture» feature is supported. `False` by default.

  * `support_refund`: Which type of the «refunds» feature is supported: `None`, `'full_only'`, or `'partial'`. `None` by default.

  * `support_tokenization`: Whether the «tokenization feature» is supported. `False` by default.




For a provider to specify that it supports additional features, it must override this method and set the related feature support fields to the desired value on the appropriate `payment.provider` records.

Ritorna
    

None

_get_compatible_providers(_company_id_ , _partner_id_ , _amount_ , _currency_id =None_, _force_tokenization =False_, _is_express_checkout =False_, _is_validation =False_, _report =None_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L454)¶
    

Search and return the providers matching the compatibility criteria.

The compatibility criteria are that providers must: not be disabled; be in the company that is provided; support the country of the partner if it exists; be compatible with the currency if provided. If provided, the optional keyword arguments further refine the criteria.

Parametri
    

  * **company_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The company to which providers must belong, as a `res.company` id.

  * **partner_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The partner making the payment, as a `res.partner` id.

  * **amount** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to pay. `0` for validation transactions.

  * **currency_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The payment currency, if known beforehand, as a `res.currency` id.

  * **force_tokenization** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether only providers allowing tokenization can be matched.

  * **is_express_checkout** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the payment is made through express checkout.

  * **is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

  * **report** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The report in which each provider’s availability status and reason must be logged.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional data. This parameter is not used here.



Ritorna
    

The compatible providers.

Tipo di ritorno
    

payment.provider

_get_redirect_form_view(_is_validation =False_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L654)¶
    

Return the view of the template used to render the redirect form.

For a provider to return a different view depending on whether the operation is a validation, it must override this method and return the appropriate view.

Note: `self.ensure_one()`

Parametri
    

**is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

Ritorna
    

The view of the redirect form template.

Tipo di ritorno
    

record of `ir.ui.view`

_get_validation_amount()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L607)¶
    

Return the amount to use for validation operations.

For a provider to support tokenization, it must override this method and return the validation amount. If it is `0`, it is not necessary to create the override.

Note: `self.ensure_one()`

Ritorna
    

The validation amount.

Tipo di ritorno
    

[float](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")

_get_validation_currency()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L621)¶
    

Return the currency to use for validation operations.

The validation currency must be supported by both the provider and the payment method. If the payment method is not passed, only the provider’s supported currencies are considered. If no suitable currency is found, the provider’s company’s currency is returned instead.

For a provider to support tokenization and specify a different validation currency, it must override this method and return the appropriate validation currency.

Note: `self.ensure_one()`

Ritorna
    

The validation currency.

Tipo di ritorno
    

recordset of `res.currency`

_is_tokenization_required(_** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L582)¶
    

Return whether tokenizing the transaction is required given its context.

For a module to make the tokenization required based on the payment context, it must override this method and return whether it is required.

Parametri
    

**kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The payment context. This parameter is not used here.

Ritorna
    

Whether tokenizing the transaction is required.

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

_should_build_inline_form(_is_validation =False_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L594)¶
    

Return whether the inline payment form should be instantiated.

For a provider to handle both direct payments and payments with redirection, it must override this method and return whether the inline payment form should be instantiated (i.e. if the payment should be direct) based on the operation (online payment or validation).

Parametri
    

**is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

Ritorna
    

Whether the inline form should be instantiated.

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

_get_removal_values()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_provider.py#L695)¶
    

Return the values to update a provider with when its module is uninstalled.

For a module to specify additional removal values, it must override this method and complete the generic values with its specific values.

Ritorna
    

The removal values to update the removed provider with.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/reference/standard_modules/payment/payment_provider.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_token.html "Payment Token") |
  * [precedente](payment_method.html "Payment Method") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Provider


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