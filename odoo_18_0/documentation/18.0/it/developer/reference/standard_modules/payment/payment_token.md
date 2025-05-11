# Payment Token — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_transaction.html "Payment Transaction") |
  * [precedente](payment_provider.html "Payment Provider") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Token



# Payment Token¶

_class _odoo.addons.payment.models.payment_token.PaymentToken[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L9)¶
    

_get_available_tokens(_providers_ids_ , _partner_id_ , _is_validation =False_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L120)¶
    

Return the available tokens linked to the given providers and partner.

For a module to retrieve the available tokens, it must override this method and add information in the kwargs to define the context of the request.

Parametri
    

  * **providers_ids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – The ids of the providers available for the transaction.

  * **partner_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The id of the partner.

  * **is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the transaction is a validation operation.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Locally unused keywords arguments.



Ritorna
    

The available tokens.

Tipo di ritorno
    

payment.token

_build_display_name(_* args_, _max_length =34_, _should_pad =True_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L145)¶
    

Build a token name of the desired maximum length with the format `•••• 1234`.

The payment details are padded on the left with up to four padding characters. The padding is only added if there is enough room for it. If not, it is either reduced or not added at all. If there is not enough room for the payment details either, they are trimmed from the left.

For a module to customize the display name of a token, it must override this method and return the customized display name.

Note: `self.ensure_one()`

Parametri
    

  * **args** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – The arguments passed by QWeb when calling this method.

  * **max_length** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The desired maximum length of the token name. The default is `34` to fit the largest IBANs.

  * **should_pad** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the token should be padded.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional data used in overrides of this method.



Ritorna
    

The padded token name.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_get_specific_create_values(_provider_code_ , _values_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L62)¶
    

Complete the values of the `create` method with provider-specific values.

For a provider to add its own create values, it must overwrite this method and return a dict of values. Provider-specific values take precedence over those of the dict of generic create values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider managing the token.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The original create values.



Ritorna
    

The dict of provider-specific create values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_handle_archiving()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L108)¶
    

Handle the archiving of tokens.

For a module to perform additional operations when a token is archived, it must override this method.

Ritorna
    

None

get_linked_records_info()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_token.py#L184)¶
    

Return a list of information about records linked to the current token.

For a module to implement payments and link documents to a token, it must override this method and add information about linked document records to the returned list.

The information must be structured as a dict with the following keys:

  * `description`: The description of the record’s model (e.g. «Subscription»).

  * `id`: The id of the record.

  * `name`: The name of the record.

  * `url`: The url to access the record.




Note: `self.ensure_one()`

Ritorna
    

The list of information about the linked document records.

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/reference/standard_modules/payment/payment_token.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_transaction.html "Payment Transaction") |
  * [precedente](payment_provider.html "Payment Provider") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Token


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