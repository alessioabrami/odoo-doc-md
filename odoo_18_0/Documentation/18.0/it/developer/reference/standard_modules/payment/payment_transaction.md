# Payment Transaction — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../cli.html "Command-line interface \(CLI\)") |
  * [precedente](payment_token.html "Payment Token") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Transaction



# Payment Transaction¶

_class _odoo.addons.payment.models.payment_transaction.PaymentTransaction[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L22)¶
    

_compute_reference(_provider_code_ , _prefix =None_, _separator ='-'_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L304)¶
    

Compute a unique reference for the transaction.

The reference corresponds to the prefix if no other transaction with that prefix already exists. Otherwise, it follows the pattern `{computed_prefix}{separator}{sequence_number}` where:

  * `{computed_prefix}` is:

    * The provided custom prefix, if any.

    * The computation result of `_compute_reference_prefix()` if the custom prefix is not filled, but the kwargs are.

    * `'tx-{datetime}'` if neither the custom prefix nor the kwargs are filled.

  * `{separator}` is the string that separates the prefix from the sequence number.

  * `{sequence_number}` is the next integer in the sequence of references sharing the same prefix. The sequence starts with `1` if there is only one matching reference.




Example

  * Given the custom prefix `'example'` which has no match with an existing reference, the full reference will be `'example'`.

  * Given the custom prefix `'example'` which matches the existing reference `'example'`, and the custom separator `'-'`, the full reference will be `'example-1'`.

  * Given the kwargs `{'invoice_ids': [1, 2]}`, the custom separator `'-'` and no custom prefix, the full reference will be `'INV1-INV2'` (or similar) if no existing reference has the same prefix, or `'INV1-INV2-n'` if `n` existing references have the same prefix.




Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **prefix** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom prefix used to compute the full reference.

  * **separator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom separator used to separate the prefix from the suffix.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional values passed to `_compute_reference_prefix()` if no custom prefix is provided.



Ritorna
    

The unique reference for the transaction.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_compute_reference_prefix(_provider_code_ , _separator_ , _** values_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L385)¶
    

Compute the reference prefix from the transaction values.

Note: This method should be called in sudo mode to give access to the documents (invoices, sales orders) referenced in the transaction values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **separator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom separator used to separate parts of the computed reference prefix.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The transaction values used to compute the reference prefix.



Ritorna
    

The computed reference prefix.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_get_specific_create_values(_provider_code_ , _values_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L203)¶
    

Complete the values of the `create` method with provider-specific values.

For a provider to add its own create values, it must overwrite this method and return a dict of values. Provider-specific values take precedence over those of the dict of generic create values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider that handled the transaction.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The original create values.



Ritorna
    

The dict of provider-specific create values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_specific_processing_values(_processing_values_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L457)¶
    

Return a dict of provider-specific values used to process the transaction.

For a provider to add its own processing values, it must overwrite this method and return a dict of provider-specific values based on the generic values returned by this method. Provider-specific values take precedence over those of the dict of generic processing values.

Parametri
    

**processing_values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The generic processing values of the transaction.

Ritorna
    

The dict of provider-specific processing values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_specific_rendering_values(_processing_values_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L471)¶
    

Return a dict of provider-specific values used to render the redirect form.

For a provider to add its own rendering values, it must overwrite this method and return a dict of provider-specific values based on the processing values (provider-specific processing values included).

Parametri
    

**processing_values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The processing values of the transaction.

Ritorna
    

The dict of provider-specific rendering values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_tx_from_notification_data(_provider_code_ , _notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L638)¶
    

Find the transaction based on the notification data.

For a provider to handle transaction processing, it must overwrite this method and return the transaction matching the notification data.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.



Ritorna
    

The transaction, if found.

Tipo di ritorno
    

recordset of `payment.transaction`

_handle_notification_data(_provider_code_ , _notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L626)¶
    

Match the transaction with the notification data, update its state and return it.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.



Ritorna
    

The transaction.

Tipo di ritorno
    

recordset of `payment.transaction`

_process_notification_data(_notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L651)¶
    

Update the transaction state and the provider reference based on the notification data.

This method should usually not be called directly. The correct method to call upon receiving notification data is `_handle_notification_data()`.

For a provider to handle transaction processing, it must overwrite this method and process the notification data.

Note: `self.ensure_one()`

Parametri
    

**notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.

Ritorna
    

None

_send_capture_request(_amount_to_capture =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L534)¶
    

Request the provider handling the transaction to capture the payment.

For partial captures, create a child transaction linked to the source transaction.

For a provider to support authorization, it must override this method and make an API request to capture the payment.

Note: `self.ensure_one()`

Parametri
    

**amount_to_capture** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to capture.

Ritorna
    

The created capture child transaction, if any.

Tipo di ritorno
    

`payment.transaction`

_send_payment_request()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L498)¶
    

Request the provider handling the transaction to make the payment.

This method is exclusively used to make payments by token, which correspond to both the `online_token` and the `offline` transaction’s `operation` field.

For a provider to support tokenization, it must override this method and make an API request to make a payment.

Note: `self.ensure_one()`

Ritorna
    

None

_send_refund_request(_amount_to_refund =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L515)¶
    

Request the provider handling the transaction to refund it.

For a provider to support refunds, it must override this method and make an API request to make a refund.

Note: `self.ensure_one()`

Parametri
    

**amount_to_refund** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to be refunded.

Ritorna
    

The refund transaction created to process the refund request.

Tipo di ritorno
    

recordset of `payment.transaction`

_send_void_request(_amount_to_void =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L555)¶
    

Request the provider handling the transaction to void the payment.

For partial voids, create a child transaction linked to the source transaction.

For a provider to support authorization, it must override this method and make an API request to void the payment.

Note: `self.ensure_one()`

Parametri
    

**amount_to_void** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to be voided.

Ritorna
    

The created void child transaction, if any.

Tipo di ritorno
    

payment.transaction

_set_authorized(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L684)¶
    

Update the transactions” state to `authorized`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `authorized`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “authorized”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_canceled(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L719)¶
    

Update the transactions” state to `cancel`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `cancel`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “canceled”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_done(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L701)¶
    

Update the transactions” state to `done`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `done`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “done”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_error(_state_message_ , _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L737)¶
    

Update the transactions” state to `error`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `error`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “error”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_pending(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/addons/payment/models/payment_transaction.py#L667)¶
    

Update the transactions” state to `pending`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `pending`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “pending”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/standard_modules/payment/payment_transaction.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../cli.html "Command-line interface \(CLI\)") |
  * [precedente](payment_token.html "Payment Token") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Transaction


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