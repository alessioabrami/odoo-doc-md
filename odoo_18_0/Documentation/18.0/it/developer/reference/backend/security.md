# Security in Odoo — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](performance.html "Performance") |
  * [precedente](module.html "Module Manifests") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Security in Odoo



# Security in Odoo¶

Aside from manually managing access using custom code, Odoo provides two main data-driven mechanisms to manage or restrict access to data.

Both mechanisms are linked to specific users through _groups_ : a user belongs to any number of groups, and security mechanisms are associated to groups, thus applying security mechanisms to users.

_class _res.groups¶
    

name¶
    

serves as user-readable identification for the group (spells out the role / purpose of the group)

category_id¶
    

The _module category_ , serves to associate groups with an Odoo App (~a set of related business models) and convert them into an exclusive selection in the user form.

implied_ids¶
    

Other groups to set on the user alongside this one. This is a convenience pseudo-inheritance relationship: it’s possible to explicitly remove implied groups from a user without removing the implier.

comment¶
    

Additional notes on the group e.g.

## Access Rights¶

_Grants_ access to an entire model for a given set of operations. If no access rights matches an operation on a model for a user (through their group), the user doesn’t have access.

Access rights are additive, a user’s accesses are the union of the accesses they get through all their groups e.g. given a user who is part of group A granting read and create access and a group B granting update access, the user will have all three of create, read, and update.

_class _ir.model.access¶
    

name¶
    

The purpose or role of the group.

model_id¶
    

The model whose access the ACL controls.

group_id¶
    

The `res.groups` to which the accesses are granted, an empty `group_id` means the ACL is granted to _every user_ (non-employees e.g. portal or public users).

The `perm__method_` attributes grant the corresponding CRUD access when set, they are all unset by default.

perm_create¶
    

perm_read¶
    

perm_write¶
    

perm_unlink¶
    

## Record Rules¶

Record rules are _conditions_ which must be satisfied in order for an operation to be allowed. Record rules are evaluated record-by-record, following access rights.

Record rules are default-allow: if access rights grant access and no rule applies to the operation and model for the user, the access is granted.

_class _ir.rule¶
    

name¶
    

The description of the rule.

model_id¶
    

The model to which the rule applies.

groups¶
    

The `res.groups` to which access is granted (or not). Multiple groups can be specified. If no group is specified, the rule is _global_ which is treated differently than «group» rules (see below).

global¶
    

Computed on the basis of `groups`, provides easy access to the global status (or not) of the rule.

domain_force¶
    

A predicate specified as a [domain](orm.html#reference-orm-domains), the rule allows the selected operations if the domain matches the record, and forbids it otherwise.

The domain is a _python expression_ which can use the following variables:

`time`
    

Python’s [`time`](https://docs.python.org/3/library/time.html#module-time "\(in Python v3.13\)") module.

`user`
    

The current user, as a singleton recordset.

`company_id`
    

The current user’s currently selected company as a single company id (not a recordset).

`company_ids`
    

All the companies to which the current user has access as a list of company ids (not a recordset), see [Security rules](../../howtos/company.html#howto-company-security) for more details.

The `perm__method_` have completely different semantics than for `ir.model.access`: for rules, they specify which operation the rules applies _for_. If an operation is not selected, then the rule is not checked for it, as if the rule did not exist.

All operations are selected by default.

perm_create¶
    

perm_read¶
    

perm_write¶
    

perm_unlink¶
    

### Global rules versus group rules¶

There is a large difference between global and group rules in how they compose and combine:

  * Global rules _intersect_ , if two global rules apply then _both_ must be satisfied for the access to be granted, this means adding global rules always restricts access further.

  * Group rules _unify_ , if two group rules apply then _either_ can be satisfied for the access to be granted. This means adding group rules can expand access, but not beyond the bounds defined by global rules.

  * The global and group rulesets _intersect_ , which means the first group rule being added to a given global ruleset will restrict access.




Pericolo

Creating multiple global rules is risky as it’s possible to create non-overlapping rulesets, which will remove all access.

## Field Access¶

An ORM [`Field`](orm.html#odoo.fields.Field "odoo.fields.Field") can have a `groups` attribute providing a list of groups (as a comma-separated string of [external identifiers](../../glossary.html#term-external-identifiers)).

If the current user is not in one of the listed groups, he will not have access to the field:

  * restricted fields are automatically removed from requested views

  * restricted fields are removed from [`fields_get()`](orm.html#odoo.models.Model.fields_get "odoo.models.Model.fields_get") responses

  * attempts to (explicitly) read from or write to restricted fields results in an access error




## Security Pitfalls¶

As a developer, it is important to understand the security mechanisms and avoid common mistakes leading to insecure code.

### Unsafe Public Methods¶

Any public method can be executed via a [RPC call](../external_api.html#api-external-api-calling-methods) with the chosen parameters. The methods starting with a `_` are not callable from an action button or external API.

On public methods, the record on which a method is executed and the parameters can not be trusted, ACL being only verified during CRUD operations.
    
    
    # this method is public and its arguments can not be trusted
    def action_done(self):
        if self.state == "draft" and self.env.user.has_group('base.manager'):
            self._set_state("done")
    
    # this method is private and can only be called from other python methods
    def _set_state(self, new_state):
        self.sudo().write({"state": new_state})
    

Making a method private is obviously not enough and care must be taken to use it properly.

### Bypassing the ORM¶

You should never use the database cursor directly when the ORM can do the same thing! By doing so you are bypassing all the ORM features, possibly the automated behaviours like translations, invalidation of fields, `active`, access rights and so on.

And chances are that you are also making the code harder to read and probably less secure.
    
    
    # very very wrong
    self.env.cr.execute('SELECT id FROM auction_lots WHERE auction_id in (' + ','.join(map(str, ids))+') AND state=%s AND obj_price > 0', ('draft',))
    auction_lots_ids = [x[0] for x in self.env.cr.fetchall()]
    
    # no injection, but still wrong
    self.env.cr.execute('SELECT id FROM auction_lots WHERE auction_id in %s '\
               'AND state=%s AND obj_price > 0', (tuple(ids), 'draft',))
    auction_lots_ids = [x[0] for x in self.env.cr.fetchall()]
    
    # better
    auction_lots_ids = self.search([('auction_id','in',ids), ('state','=','draft'), ('obj_price','>',0)])
    

#### SQL injections¶

Care must be taken not to introduce SQL injections vulnerabilities when using manual SQL queries. The vulnerability is present when user input is either incorrectly filtered or badly quoted, allowing an attacker to introduce undesirable clauses to a SQL query (such as circumventing filters or executing `UPDATE` or `DELETE` commands).

The best way to be safe is to never, NEVER use Python string concatenation (+) or string parameters interpolation (%) to pass variables to a SQL query string.

The second reason, which is almost as important, is that it is the job of the database abstraction layer (psycopg2) to decide how to format query parameters, not your job! For example psycopg2 knows that when you pass a list of values it needs to format them as a comma-separated list, enclosed in parentheses !
    
    
    # the following is very bad:
    #   - it's a SQL injection vulnerability
    #   - it's unreadable
    #   - it's not your job to format the list of ids
    self.env.cr.execute('SELECT distinct child_id FROM account_account_consol_rel ' +
               'WHERE parent_id IN ('+','.join(map(str, ids))+')')
    
    # better
    self.env.cr.execute('SELECT DISTINCT child_id '\
               'FROM account_account_consol_rel '\
               'WHERE parent_id IN %s',
               (tuple(ids),))
    

This is very important, so please be careful also when refactoring, and most importantly do not copy these patterns!

Here is a memorable example to help you remember what the issue is about (but do not copy the code there). Before continuing, please be sure to read the online documentation of pyscopg2 to learn of to use it properly:

  * [The problem with query parameters](http://initd.org/psycopg/docs/usage.html#the-problem-with-the-query-parameters)

  * [How to pass parameters with psycopg2](http://initd.org/psycopg/docs/usage.html#passing-parameters-to-sql-queries)

  * [Advanced parameter types](http://initd.org/psycopg/docs/usage.html#adaptation-of-python-values-to-sql-types)

  * [Psycopg documentation](https://www.psycopg.org/docs/sql.html)




### Unescaped field content¶

When rendering content using JavaScript and XML, one may be tempted to use a `t-raw` to display rich-text content. This should be avoided as a frequent [XSS](https://en.wikipedia.org/wiki/Cross-site_scripting) vector.

It is very hard to control the integrity of the data from the computation until the final integration in the browser DOM. A `t-raw` that is correctly escaped at the time of introduction may no longer be safe at the next bugfix or refactoring.
    
    
    QWeb.render('insecure_template', {
        info_message: "You have an <strong>important</strong> notification",
    })
    
    
    
    <div t-name="insecure_template">
        <div id="information-bar"><t t-raw="info_message" /></div>
    </div>
    

The above code may feel safe as the message content is controlled but is a bad practice that may lead to unexpected security vulnerabilities once this code evolves in the future.
    
    
    // XSS possible with unescaped user provided content !
    QWeb.render('insecure_template', {
        info_message: "You have an <strong>important</strong> notification on " \
            + "the product <strong>" + product.name + "</strong>",
    })
    

While formatting the template differently would prevent such vulnerabilities.
    
    
    QWeb.render('secure_template', {
        message: "You have an important notification on the product:",
        subject: product.name
    })
    
    
    
    <div t-name="secure_template">
        <div id="information-bar">
            <div class="info"><t t-esc="message" /></div>
            <div class="subject"><t t-esc="subject" /></div>
        </div>
    </div>
    
    
    
    .subject {
        font-weight: bold;
    }
    

#### Creating safe content using `Markup`¶

See the [official documentation](https://markupsafe.palletsprojects.com/) for explanations, but the big advantage of `Markup` is that it’s a very rich type overrinding [`str`](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") operations to _automatically escape parameters_.

This means that it’s easy to create _safe_ html snippets by using `Markup` on a string literal and «formatting in» user-provided (and thus potentially unsafe) content:
    
    
    >>> Markup('<em>Hello</em> ') + '<foo>'
    Markup('<em>Hello</em> &lt;foo&gt;')
    >>> Markup('<em>Hello</em> %s') % '<foo>'
    Markup('<em>Hello</em> &lt;foo&gt;')
    

though it is a very good thing, note that the effects can be odd at times:
    
    
    >>> Markup('<a>').replace('>', 'x')
    Markup('<a>')
    >>> Markup('<a>').replace(Markup('>'), 'x')
    Markup('<ax')
    >>> Markup('<a&gt;').replace('>', 'x')
    Markup('<ax')
    >>> Markup('<a&gt;').replace('>', '&')
    Markup('<a&amp;')
    

Suggerimento

Most of the content-safe APIs actually return a `Markup` with all that implies.

The `escape` method (and its alias `html_escape`) turns a `str` into a `Markup` and escapes its content. It will not escape the content of a `Markup` object.
    
    
    def get_name(self, to_html=False):
        if to_html:
            return Markup("<strong>%s</strong>") % self.name  # escape the name
        else:
            return self.name
    
    >>> record.name = "<R&D>"
    >>> escape(record.get_name())
    Markup("&lt;R&amp;D&gt;")
    >>> escape(record.get_name(True))
    Markup("<strong>&lt;R&amp;D&gt;</strong>")  # HTML is kept
    

When generating HTML code, it is important to separate the structure (tags) from the content (text).
    
    
    >>> Markup("<p>") + "Hello <R&D>" + Markup("</p>")
    Markup('<p>Hello &lt;R&amp;D&gt;</p>')
    >>> Markup("%s <br/> %s") % ("<R&D>", Markup("<p>Hello</p>"))
    Markup('&lt;R&amp;D&gt; <br/> <p>Hello</p>')
    >>> escape("<R&D>")
    Markup('&lt;R&amp;D&gt;')
    >>> _("List of Tasks on project %s: %s",
    ...     project.name,
    ...     Markup("<ul>%s</ul>") % Markup().join(Markup("<li>%s</li>") % t.name for t in project.task_ids)
    ... )
    Markup('Liste de tâches pour le projet &lt;R&amp;D&gt;: <ul><li>First &lt;R&amp;D&gt; task</li></ul>')
    
    >>> Markup("<p>Foo %</p>" % bar)  # bad, bar is not escaped
    >>> Markup("<p>Foo %</p>") % bar  # good, bar is escaped if text and kept if markup
    
    >>> link = Markup("<a>%s</a>") % self.name
    >>> message = "Click %s" % link  # bad, message is text and Markup did nothing
    >>> message = escape("Click %s") % link  # good, format two markup objects together
    
    >>> Markup(f"<p>Foo {self.bar}</p>")  # bad, bar is inserted before escaping
    >>> Markup("<p>Foo {bar}</p>").format(bar=self.bar)  # good, sorry no fstring
    

When working with translations, it is especially important to separate the HTML from the text. The translation methods accepts a `Markup` parameters and will escape the translation if it gets receives at least one.
    
    
    >>> Markup("<p>%s</p>") % _("Hello <R&D>")
    Markup('<p>Bonjour &lt;R&amp;D&gt;</p>')
    >>> _("Order %s has been confirmed", Markup("<a>%s</a>") % order.name)
    Markup('Order <a>SO42</a> has been confirmed')
    >>> _("Message received from %(name)s <%(email)s>",
    ...   name=self.name,
    ...   email=Markup("<a href='mailto:%s'>%s</a>") % (self.email, self.email)
    Markup('Message received from Georges &lt;<a href=mailto:george@abitbol.example>george@abitbol.example</a>&gt;')
    

### Escaping vs Sanitizing¶

Importante

Escaping is always 100% mandatory when you mix data and code, no matter how safe the data

**Escaping** converts _TEXT_ to _CODE_. It is absolutely mandatory to do it every time you mix _DATA/TEXT_ with _CODE_ (e.g. generating HTML or python code to be evaluated inside a `safe_eval`), because _CODE_ always requires _TEXT_ to be encoded. It is critical for security, but it’s also a question of correctness. Even when there is no security risk (because the text is 100% guarantee to be safe or trusted), it is still required (e.g. to avoid breaking the layout in generated HTML).

Escaping will never break any feature, as long as the developer identifies which variable contains _TEXT_ and which contains _CODE_.
    
    
    >>> from odoo.tools import html_escape, html_sanitize
    >>> data = "<R&D>" # `data` is some TEXT coming from somewhere
    
    # Escaping turns it into CODE, good!
    >>> code = html_escape(data)
    >>> code
    Markup('&lt;R&amp;D&gt;')
    
    # Now you can mix it with other code...
    >>> self.website_description = Markup("<strong>%s</strong>") % code
    

**Sanitizing** converts _CODE_ to _SAFER CODE_ (but not necessary _safe_ code). It does not work on _TEXT_. Sanitizing is only necessary when _CODE_ is untrusted, because it comes in full or in part from some user-provided data. If the user-provided data is in the form of _TEXT_ (e.g. the content from a form filled by a user), and if that data was correctly escaped before putting it in _CODE_ , then sanitizing is useless (but can still be done). If however, the user-provided data was **not escaped** , then sanitizing will **not** work as expected.
    
    
    # Sanitizing without escaping is BROKEN: data is corrupted!
    >>> html_sanitize(data)
    Markup('')
    
    # Sanitizing *after* escaping is OK!
    >>> html_sanitize(code)
    Markup('<p>&lt;R&amp;D&gt;</p>')
    

Sanitizing can break features, depending on whether the _CODE_ is expected to contain patterns that are not safe. That’s why `fields.Html` and `tools.html_sanitize()` have options to fine-tune the level of sanitization for styles, etc. Those options have to be carefully considered depending on where the data comes from, and the desired features. The sanitization safety is balanced against sanitization breakages: the safer the sanitisation the more likely it is to break things.
    
    
    >>> code = "<p class='text-warning'>Important Information</p>"
    # this will remove the style, which may break features
    # but is necessary if the source is untrusted
    >>> html_sanitize(code, strip_classes=True)
    Markup('<p>Important Information</p>')
    

### Evaluating content¶

Some may want to `eval` to parse user provided content. Using `eval` should be avoided at all cost. A safer, sandboxed, method `safe_eval` can be used instead but still gives tremendous capabilities to the user running it and must be reserved for trusted privileged users only as it breaks the barrier between code and data.
    
    
    # very bad
    domain = eval(self.filter_domain)
    return self.search(domain)
    
    # better but still not recommended
    from odoo.tools import safe_eval
    domain = safe_eval(self.filter_domain)
    return self.search(domain)
    
    # good
    from ast import literal_eval
    domain = literal_eval(self.filter_domain)
    return self.search(domain)
    

Parsing content does not need `eval`

Language | Data type | Suitable parser  
---|---|---  
Python | int, float, etc. | int(), float()  
Javascript | int, float, etc. | parseInt(), parseFloat()  
Python | dict | json.loads(), ast.literal_eval()  
Javascript | object, list, etc. | JSON.parse()  
  
### Accessing object attributes¶

If the values of a record needs to be retrieved or modified dynamically, one may want to use the `getattr` and `setattr` methods.
    
    
    # unsafe retrieval of a field value
    def _get_state_value(self, res_id, state_field):
        record = self.sudo().browse(res_id)
        return getattr(record, state_field, False)
    

This code is however not safe as it allows to access any property of the record, including private attributes or methods.

The `__getitem__` of a recordset has been defined and accessing a dynamic field value can be easily achieved safely:
    
    
    # better retrieval of a field value
    def _get_state_value(self, res_id, state_field):
        record = self.sudo().browse(res_id)
        return record[state_field]
    

The above method is obviously still too optimistic and additional verifications on the record id and field value must be done.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/backend/security.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](performance.html "Performance") |
  * [precedente](module.html "Module Manifests") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Server framework](../backend.html) »
  * Security in Odoo


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