# Safeguard your code with unit tests — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](importable_modules.html "Write importable modules") |
  * [precedente](restrict_data_access.html "Restrict access to data") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Safeguard your code with unit tests



# Safeguard your code with unit tests¶

Importante

This tutorial is an extension of the [Server framework 101](server_framework_101.html) tutorial. Make sure you have completed it and use the `estate` module you have built as a base for the exercises in this tutorial.

**Reference** : [Odoo’s Test Framework: Learn Best Practices](https://www.youtube.com/watch?v=JEIscps0OOQ) (Odoo Experience 2020) on YouTube.

Writing tests is a necessity for multiple reasons. Here is a non-exhaustive list:

  * Ensure code will not be broken in the future

  * Define the scope of your code

  * Give examples of use cases

  * It is one way to technically document the code

  * Help your coding by defining your goal before working towards it




## Running Tests¶

Before knowing how to write tests, we need to know how to run them.
    
    
    $ odoo-bin -h
    Usage: odoo-bin [options]
    
    Options:
    --version             show program's version number and exit
    -h, --help            show this help message and exit
    
    [...]
    
    Testing Configuration:
      --test-file=TEST_FILE
                          Launch a python test file.
      --test-enable       Enable unit tests.
      --test-tags=TEST_TAGS
                          Comma-separated list of specs to filter which tests to
                          execute. Enable unit tests if set. A filter spec has
                          the format: [-][tag][/module][:class][.method] The '-'
                          specifies if we want to include or exclude tests
                          matching this spec. The tag will match tags added on a
                          class with a @tagged decorator (all Test classes have
                          'standard' and 'at_install' tags until explicitly
                          removed, see the decorator documentation). '*' will
                          match all tags. If tag is omitted on include mode, its
                          value is 'standard'. If tag is omitted on exclude
                          mode, its value is '*'. The module, class, and method
                          will respectively match the module name, test class
                          name and test method name. Example: --test-tags
                          :TestClass.test_func,/test_module,external  Filtering
                          and executing the tests happens twice: right after
                          each module installation/update and at the end of the
                          modules loading. At each stage tests are filtered by
                          --test-tags specs and additionally by dynamic specs
                          'at_install' and 'post_install' correspondingly.
      --screencasts=DIR   Screencasts will go in DIR/{db_name}/screencasts.
      --screenshots=DIR   Screenshots will go in DIR/{db_name}/screenshots.
                          Defaults to /tmp/odoo_tests.
    
    $ # run all the tests of account, and modules installed by account
    $ # the dependencies already installed are not tested
    $ # this takes some time because you need to install the modules, but at_install
    $ # and post_install are respected
    $ odoo-bin -i account --test-enable
    $ # run all the tests in this file
    $ odoo-bin --test-file=addons/account/tests/test_account_move_entry.py
    $ # test tags can help you filter quite easily
    $ odoo-bin --test-tags=/account:TestAccountMove.test_custom_currency_on_account_1
    

## Integration Bots¶

Nota

This section is only for Odoo employees and people that are contributing to `github.com/odoo`. We highly recommend having your own CI otherwise.

When a test is written, it is important to make sure it always passes when modifications are applied to the source code. To automate this task, we use a development practice called Continuous Integration (CI). This is why we have some bots running all the tests at different moments. Whether you are working at Odoo or not, if you are trying to merge something inside `odoo/odoo`, `odoo/enterprise`, `odoo/upgrade` or on odoo.sh, you will have to go through the CI. If you are working on another project, you should think of adding your own CI.

### Runbot¶

**Reference** : the documentation related to this topic can be found in [Runbot FAQ](https://runbot.odoo.com/doc).

Most of the tests are run on [Runbot](https://runbot.odoo.com/) every time a commit is pushed on GitHub.

You can see the state of a commit/branch by filtering on the runbot dashboard.

A **bundle** is created for each branch. A bundle consists of a configuration and batches.

A **batch** is a set of builds, depending on the parameters of the bundle. A batch is green (i.e. passes the tests) if all the builds are green.

A **build** is when we launch a server. It can be divided in sub-builds. Usually there are builds for the community version, the enterprise version (only if there is an enterprise branch but you can force the build), and the migration of the branch. A build is green if every sub-build is green.

A **sub-build** only does some parts of what a full build does. It is used to speed up the CI process. Generally it is used to split the post install tests in 4 parallel instances. A sub-build is green if all the tests are passing and there are no errors/warnings logged.

Nota

  * All tests are run regardless of the modifications done. Correcting a typo in an error message or refactoring a whole module triggers the same tests. All modules will be installed as well. This means something might not work even if the Runbot is green, i.e. your changes depend on a module that the module the changes are in doesn’t depend on.

  * The localization modules (i.e. country-specific modules) are not installed on Runbot (except the generic one). Some modules with external dependencies can also be excluded.

  * There is a nightly build running additional tests: module operations, localization, single module installs, multi-builds for nondeterministic bugs, etc. These are not kept in the standard CI to shorten the time of execution.




You can also login to a build built by Runbot. There are 3 users usable: `admin`, `demo` and `portal`. The password is the same as the login. This is useful to quickly test things on different versions without having to build it locally. The full logs are also available; these are used for monitoring.

### Robodoo¶

You will most likely have to gain a little bit more experience before having the rights to summon robodoo, but here are a few remarks anyways.

Robodoo is the guy spamming the CI status as tags on your PRs, but he is also the guy that kindly integrates your commits into the main repositories.

When the last batch is green, the reviewer can ask robodoo to merge your PR (it is more a `rebase` than a `merge`). It will then go to the mergebot.

### Mergebot¶

[Mergebot](https://mergebot.odoo.com/) is the last testing phase before merging a PR.

It will take the commits in your branch not yet present on the target, stage it and rerun the tests one more time, including the enterprise version even if you are only changing something in community.

This step can fail with a `Staging failed` error message. This could be due to

  * a nondeterministic bug that is already on the target. If you are an Odoo employee, you can check those here: <https://runbot.odoo.com/runbot/errors>

  * a nondeterministic bug that you introduced but wasn’t detected in the CI before

  * an incompatibility with another commit merged right before and what you are trying to merge

  * an incompatibility with the enterprise repository if you only did changes in the community repo




Always check that the issue does not come from you before asking the merge bot to retry: rebase your branch on the target and rerun the tests locally.

## Modules¶

Because Odoo is modular, the tests need to be also modular. This means tests are defined in the module that adds the functionality you are adding in, and tests cannot depend on functionality coming from modules your module doesn’t depend on.

**Reference** : the documentation related to this topic can be found in [Special Tags](../reference/backend/testing.html#reference-testing-tags).
    
    
    from odoo.tests.common import TransactionCase
    from odoo.tests import tagged
    
    # The CI will run these tests after all the modules are installed,
    # not right after installing the one defining it.
    @tagged('post_install', '-at_install')  # add `post_install` and remove `at_install`
    class PostInstallTestCase(TransactionCase):
        def test_01(self):
            ...
    
    @tagged('at_install')  # this is the default
    class AtInstallTestCase(TransactionCase):
        def test_01(self):
            ...
    

If the behavior you want to test can be changed by the installation of another module, you need to ensure that the tag `at_install` is set; otherwise, you can use the tag `post_install` to speed up the CI and ensure it is not changed if it shouldn’t.

## Writing a test¶

**Reference** : the documentation related to this topic can be found in [Python unittest](https://docs.python.org/3/library/unittest.html) and [Testing Odoo](../reference/backend/testing.html#reference-testing).

Here are a few things to take into consideration before writing a test

  * The tests should be independent of the data currently in the database (including demo data)

  * Tests should not impact the database by leaving/changing residual data. This is usually done by the test framework by doing a rollback. Therefore, you must never call `cr.commit` in a test (nor anywhere else in the business code).

  * For a bug fix, the test should fail before applying the fix and pass after.

  * Don’t test something that is already tested elsewhere; you can trust the ORM. Most of the tests in business modules should only test the business flows.

  * You shouldn’t need to flush data into the database.




Nota

Remember that `onchange` only applies in the Form views, not by changing the attributes in python. This also applies in the tests. If you want to emulate a Form view, you can use `odoo.tests.common.Form`.

The tests should be in a `tests` folder at the root of your module. Each test file name should start with `test_` and be imported in the `__init__.py` of the test folder. You shouldn’t import the test folder/module in the `__init__.py` of the module.
    
    
    estate
    ├── models
    │   ├── *.py
    │   └── __init__.py
    ├── tests
    │   ├── test_*.py
    │   └── __init__.py
    ├── __init__.py
    └── __manifest__.py
    

All the tests should extend `odoo.tests.common.TransactionCase`. You usually define a `setUpClass` and the tests. After writing the `setUpClass`, you have an `env` available in the class and can start interacting with the ORM.

These test classes are built on top of the `unittest` python module.
    
    
    from odoo.tests.common import TransactionCase
    from odoo.exceptions import UserError
    from odoo.tests import tagged
    
    # The CI will run these tests after all the modules are installed,
    # not right after installing the one defining it.
    @tagged('post_install', '-at_install')
    class EstateTestCase(TransactionCase):
    
        @classmethod
        def setUpClass(cls):
            # add env on cls and many other things
            super(EstateTestCase, cls).setUpClass()
    
            # create the data for each tests. By doing it in the setUpClass instead
            # of in a setUp or in each test case, we reduce the testing time and
            # the duplication of code.
            cls.properties = cls.env['estate.property'].create([...])
    
        def test_creation_area(self):
            """Test that the total_area is computed like it should."""
            self.properties.living_area = 20
            self.assertRecordValues(self.properties, [
               {'name': ..., 'total_area': ...},
               {'name': ..., 'total_area': ...},
            ])
    
    
        def test_action_sell(self):
            """Test that everything behaves like it should when selling a property."""
            self.properties.action_sold()
            self.assertRecordValues(self.properties, [
               {'name': ..., 'state': ...},
               {'name': ..., 'state': ...},
            ])
    
            with self.assertRaises(UserError):
                self.properties.forbidden_action_on_sold_property()
    

Nota

For better readability, split your tests into multiple files depending on the scope of the tests. You can also have a Common class that most of the tests should inherit from; this common class can define the whole setup for the module. For instance, in [account](https://github.com/odoo/odoo/blob/18.0/addons/account/tests/common.py).

Exercise

Update the code so no one can:

  * Create an offer for a sold property

  * Sell a property with no accepted offers on it




and create tests for both of these cases. Additionally check that selling a property that can be sold is correctly marked as sold after selling it.

Exercise

Someone keeps breaking the reset of Garden Area and Orientation when you uncheck the Garden checkbox. Make sure it doesn’t happen again.

Suggerimento

Tip: remember the note about `Form` a little bit above.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/tutorials/unit_tests.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](importable_modules.html "Write importable modules") |
  * [precedente](restrict_data_access.html "Restrict access to data") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Safeguard your code with unit tests


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