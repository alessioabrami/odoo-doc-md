# Web Controllers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mixins.html "Mixins and Useful Classes") |
  * [precedente](testing.html "Testing Odoo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Web Controllers



# Web Controllers¶

## Controllers¶

Controllers need to provide extensibility, much like [`Model`](orm.html#odoo.models.Model "odoo.models.Model"), but can’t use the same mechanism as the pre-requisites (a database with loaded modules) may not be available yet (e.g. no database created, or no database selected).

Controllers thus provide their own extension mechanism, separate from that of models:

Controllers are created by [inheriting](https://docs.python.org/3/tutorial/classes.html#tut-inheritance "\(in Python v3.13\)") from `Controller`. Routes are defined through methods decorated with `route()`:
    
    
    class MyController(odoo.http.Controller):
        @route('/some_url', auth='public')
        def handler(self):
            return stuff()
    

To _override_ a controller, [inherit](https://docs.python.org/3/tutorial/classes.html#tut-inheritance "\(in Python v3.13\)") from its class and override relevant methods, re-exposing them if necessary:
    
    
    class Extension(MyController):
        @route()
        def handler(self):
            do_before()
            return super(Extension, self).handler()
    

  * decorating with `route()` is necessary to keep the method (and route) visible: if the method is redefined without decorating, it will be «unpublished»

  * the decorators of all methods are combined, if the overriding method’s decorator has no argument all previous ones will be kept, any provided argument will override previously defined ones e.g.:
        
        class Restrict(MyController):
            @route(auth='user')
            def handler(self):
                return super(Restrict, self).handler()
        

will change `/some_url` from public authentication to user (requiring a log-in)




## API¶

### Routing¶

@odoo.http.route(_route =None_, _** routing_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L660)¶
    

Decorate a controller method in order to route incoming requests matching the given URL and options to the decorated method.

Avvertimento

It is mandatory to re-decorate any method that is overridden in controller extensions but the arguments can be omitted. See `Controller` for more details.

Parametri
    

  * **route** (_Union_ _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _,__Iterable_ _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]__]_) – The paths that the decorated method is serving. Incoming HTTP request paths matching this route will be routed to this decorated method. See [werkzeug routing documentation](http://werkzeug.pocoo.org/docs/routing/) for the format of route expressions.

  * **type** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The type of request, either `'json'` or `'http'`. It describes where to find the request parameters and how to serialize the response.

  * **auth** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – 

The authentication method, one of the following:

    * `'user'`: The user must be authenticated and the current request will be executed using the rights of the user.

    * `'bearer'`: The user is authenticated using an «Authorization» request header, using the Bearer scheme with an API token. The request will be executed with the permissions of the corresponding user. If the header is missing, the request must belong to an authentication session, as for the «user» authentication method.

    * `'public'`: The user may or may not be authenticated. If he isn’t, the current request will be executed using the shared Public user.

    * `'none'`: The method is always active, even if there is no database. Mainly used by the framework and authentication modules. The request code will not have any facilities to access the current user.

  * **methods** (_Iterable_ _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – A list of http methods (verbs) this route applies to. If not specified, all methods are allowed.

  * **cors** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The Access-Control-Allow-Origin cors directive value.

  * **csrf** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether CSRF protection should be enabled for the route. Enabled by default for `'http'`-type requests, disabled by default for `'json'`-type requests.

  * **readonly** (_Union_ _[_[_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _,__Callable_ _[__[__registry_ _,__request_ _]__,_[_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)") _]__]_) – Whether this endpoint should open a cursor on a read-only replica instead of (by default) the primary read/write database.

  * **handle_params_access_error** (_Callable_ _[__[_[_Exception_](https://docs.python.org/3/library/exceptions.html#Exception "\(in Python v3.13\)") _]__,__Response_ _]_) – Implement a custom behavior if an error occurred when retrieving the record from the URL parameters (access error or missing error).




### Request¶

The request object is automatically set on `odoo.http.request` at the start of the request.

_class _odoo.http.Request(_httprequest_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1434)¶
    

Wrapper around the incoming HTTP request with deserialized request parameters, session utilities and request dispatching logic.

update_env(_user =None_, _context =None_, _su =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1499)¶
    

Update the environment of the current request.

Parametri
    

  * **user** (int or `res.users record`) – optional user/user id to change the current user

  * **context** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – optional context dictionary to change the current context

  * **su** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – optional boolean to change the superuser mode




update_context(_** overrides_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1511)¶
    

Override the environment context of the current request with the values of `overrides`. To replace the entire context, please use `update_env()` instead.

csrf_token(_time_limit =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1573)¶
    

Generates and returns a CSRF token for the current session

Parametri
    

**time_limit** (_Optional_ _[_[_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)") _]_) – the CSRF token should only be valid for the specified duration (in second), by default 48h, `None` for the token to be valid as long as the current user’s session is.

Ritorna
    

ASCII token string

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

validate_csrf(_csrf_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1595)¶
    

Is the given csrf token valid ?

Parametri
    

**csrf** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The token to validate.

Ritorna
    

`True` when valid, `False` when not.

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

default_lang()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1626)¶
    

Returns default user language according to request specification

Ritorna
    

Preferred language if specified or “en_US”

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

get_http_params()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1634)¶
    

Extract key=value pairs from the query string and the forms present in the body (both application/x-www-form-urlencoded and multipart/form-data).

Ritorna
    

The merged key-value pairs.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

make_response(_data_ , _headers =None_, _cookies =None_, _status =200_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1690)¶
    

Helper for non-HTML responses, or HTML responses with custom response headers or cookies.

While handlers can just return the HTML markup of a page they want to send as a string if non-HTML data is returned they need to create a complete response object, or the returned data will not be correctly interpreted by the clients.

Parametri
    

  * **data** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – response body

  * **status** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – http status code

  * **headers** (`[(name, value)]`) – HTTP headers to set on the response

  * **cookies** ([_collections.abc.Mapping_](https://docs.python.org/3/library/collections.abc.html#collections.abc.Mapping "\(in Python v3.13\)")) – cookies to set on the client



Ritorna
    

a response object.

Tipo di ritorno
    

`Response`

make_json_response(_data_ , _headers =None_, _cookies =None_, _status =200_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1713)¶
    

Helper for JSON responses, it json-serializes `data` and sets the Content-Type header accordingly if none is provided.

Parametri
    

  * **data** – the data that will be json-serialized into the response body

  * **status** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – http status code

  * **headers** (_List_ _[__(_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _,_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _)__]_) – HTTP headers to set on the response

  * **cookies** ([_collections.abc.Mapping_](https://docs.python.org/3/library/collections.abc.html#collections.abc.Mapping "\(in Python v3.13\)")) – cookies to set on the client



Tipo di ritorno
    

`Response`

not_found(_description =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1732)¶
    

Shortcut for a [HTTP 404](http://tools.ietf.org/html/rfc7231#section-6.5.4) (Not Found) response

render(_template_ , _qcontext =None_, _lazy =True_, _** kw_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1754)¶
    

Lazy render of a QWeb template.

The actual rendering of the given template will occur at then end of the dispatching. Meanwhile, the template and/or qcontext can be altered or even replaced by a static response.

Parametri
    

  * **template** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – template to render

  * **qcontext** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Rendering context to use

  * **lazy** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – whether the template rendering should be deferred until the last possible moment

  * **kw** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – forwarded to werkzeug’s Response object




reroute(_path_ , _query_string =None_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1772)¶
    

Rewrite the current request URL using the new path and query string. This act as a light redirection, it does not return a 3xx responses to the browser but still change the current URL.

_class _odoo.http.JsonRPCDispatcher(_request_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2123)¶
    

_classmethod _is_compatible_with(_request_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2131)¶
    

Determine if the current request is compatible with this dispatcher.

dispatch(_endpoint_ , _args_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2135)¶
    

[JSON-RPC 2](http://www.jsonrpc.org/specification) over HTTP.

Our implementation differs from the specification on two points:

  1. The `method` member of the JSON-RPC request payload is ignored as the HTTP path is already used to route the request to the controller.

  2. We only support parameter structures by-name, i.e. the `params` member of the JSON-RPC request payload MUST be a JSON Object and not a JSON Array.




In addition, it is possible to pass a context that replaces the session context via a special `context` argument that is removed prior to calling the endpoint.

Successful request:
    
    
    --> {"jsonrpc": "2.0", "method": "call", "params": {"arg1": "val1" }, "id": null}
    
    <-- {"jsonrpc": "2.0", "result": { "res1": "val1" }, "id": null}
    

Request producing a error:
    
    
    --> {"jsonrpc": "2.0", "method": "call", "params": {"arg1": "val1" }, "id": null}
    
    <-- {"jsonrpc": "2.0", "error": {"code": 1, "message": "End user error message.", "data": {"code": "codestring", "debug": "traceback" } }, "id": null}
    

handle_error(_exc : [Exception](https://docs.python.org/3/library/exceptions.html#Exception "\(in Python v3.13\)")_) → [collections.abc.Callable](https://docs.python.org/3/library/collections.abc.html#collections.abc.Callable "\(in Python v3.13\)")[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2183)¶
    

Handle any exception that occurred while dispatching a request to a `type='json'` route. Also handle exceptions that occurred when no route matched the request path, that no fallback page could be delivered and that the request `Content-Type` was json.

Parametri
    

**exc** – the exception that occurred.

Ritorna
    

a WSGI application

_class _odoo.http.HttpDispatcher(_request_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2059)¶
    

_classmethod _is_compatible_with(_request_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2062)¶
    

Determine if the current request is compatible with this dispatcher.

dispatch(_endpoint_ , _args_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2066)¶
    

Perform http-related actions such as deserializing the request body and query-string and checking cors/csrf while dispatching a request to a `type='http'` route.

See `load()` method for the compatible endpoint return types.

handle_error(_exc : [Exception](https://docs.python.org/3/library/exceptions.html#Exception "\(in Python v3.13\)")_) → [collections.abc.Callable](https://docs.python.org/3/library/collections.abc.html#collections.abc.Callable "\(in Python v3.13\)")[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L2095)¶
    

Handle any exception that occurred while dispatching a request to a `type='http'` route. Also handle exceptions that occurred when no route matched the request path, when no fallback page could be delivered and that the request `Content-Type` was not json.

Parametri
    

**exc** ([_Exception_](https://docs.python.org/3/library/exceptions.html#Exception "\(in Python v3.13\)")) – the exception that occurred.

Ritorna
    

a WSGI application

### Response¶

_class _odoo.http.Response(_* args_, _** kw_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1310)¶
    

Outgoing HTTP response with body, status, headers and qweb support. In addition to the [`werkzeug.wrappers.Response`](https://werkzeug.palletsprojects.com/en/stable/wrappers/#werkzeug.wrappers.Response "\(in Werkzeug v3.1.x\)") parameters, this class’s constructor can take the following additional parameters for QWeb Lazy Rendering.

Parametri
    

  * **template** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – template to render

  * **qcontext** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Rendering context to use

  * **uid** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – User id to use for the ir.ui.view render call, `None` to use the request’s user (the default)




these attributes are available as parameters on the Response object and can be altered at any time before rendering

Also exposes all the attributes and methods of [`werkzeug.wrappers.Response`](https://werkzeug.palletsprojects.com/en/stable/wrappers/#werkzeug.wrappers.Response "\(in Werkzeug v3.1.x\)").

_classmethod _load(_result_ , _fname ='<function>'_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1337)¶
    

Convert the return value of an endpoint into a Response.

Parametri
    

  * **result** (_Union_ _[__Response_ _,__werkzeug.wrappers.BaseResponse_ _,_[_werkzeug.exceptions.HTTPException_](https://werkzeug.palletsprojects.com/en/stable/exceptions/#werkzeug.exceptions.HTTPException "\(in Werkzeug v3.1.x\)") _,_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _,_[_bytes_](https://docs.python.org/3/library/stdtypes.html#bytes "\(in Python v3.13\)") _,__NoneType_ _]_) – The endpoint return value to load the Response from.

  * **fname** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The endpoint function name wherefrom the result emanated, used for logging.



Ritorna
    

The created `Response`.

Tipo di ritorno
    

Response

Solleva
    

[**TypeError**](https://docs.python.org/3/library/exceptions.html#TypeError "\(in Python v3.13\)") – When `result` type is none of the above- mentioned type.

render()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1379)¶
    

Renders the Response’s template, returns the result.

flatten()[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1384)¶
    

Forces the rendering of the response’s template, sets the result as response body and unsets `template`

set_cookie(_key_ , _value =''_, _max_age =None_, _expires =- 1_, _path ='/'_, _domain =None_, _secure =False_, _httponly =False_, _samesite =None_, _cookie_type ='required'_)[[sorgente]](https://github.com/odoo/odoo/blob/18.0/odoo/http.py#L1393)¶
    

The default expires in Werkzeug is None, which means a session cookie. We want to continue to support the session cookie, but not by default. Now the default is arbitrary 1 year. So if you want a cookie of session, you have to explicitly pass expires=None.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer/reference/backend/http.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mixins.html "Mixins and Useful Classes") |
  * [precedente](testing.html "Testing Odoo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Web Controllers


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