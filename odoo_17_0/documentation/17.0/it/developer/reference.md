# Reference — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](reference/backend.html "Server framework") |
  * [precedente](howtos/upgrade_custom_db.html "Upgrade a customized database") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Developer](../developer.html) »
  * Reference



# Reference¶

  * Server framework
    * [ORM API](reference/backend/orm.html)
      * [Changelog](reference/backend/orm/changelog.html)
      * [Models](reference/backend/orm.html#models)
      * [Fields](reference/backend/orm.html#fields)
      * [Recordsets](reference/backend/orm.html#recordsets)
      * [Method decorators](reference/backend/orm.html#module-odoo.api)
      * [Environment](reference/backend/orm.html#environment)
      * [Common ORM methods](reference/backend/orm.html#common-orm-methods)
      * [Inheritance and extension](reference/backend/orm.html#inheritance-and-extension)
      * [Error management](reference/backend/orm.html#module-odoo.exceptions)
    * Data Files
      * [Structure](reference/backend/data.html#structure)
      * [Core operations](reference/backend/data.html#core-operations)
      * [Shortcuts](reference/backend/data.html#shortcuts)
      * [CSV data files](reference/backend/data.html#csv-data-files)
    * Actions
      * [Bindings](reference/backend/actions.html#bindings)
      * [Window Actions (`ir.actions.act_window`)](reference/backend/actions.html#window-actions-ir-actions-act-window)
      * [URL Actions (`ir.actions.act_url`)](reference/backend/actions.html#url-actions-ir-actions-act-url)
      * [Server Actions (`ir.actions.server`)](reference/backend/actions.html#server-actions-ir-actions-server)
      * [Report Actions (`ir.actions.report`)](reference/backend/actions.html#report-actions-ir-actions-report)
      * [Client Actions (`ir.actions.client`)](reference/backend/actions.html#client-actions-ir-actions-client)
      * [Automated Actions (`ir.cron`)](reference/backend/actions.html#automated-actions-ir-cron)
    * QWeb Reports
      * [Report template](reference/backend/reports.html#report-template)
      * [Paper Format](reference/backend/reports.html#paper-format)
      * [Custom Reports](reference/backend/reports.html#custom-reports)
      * [Custom fonts](reference/backend/reports.html#custom-fonts)
      * [Reports are web pages](reference/backend/reports.html#reports-are-web-pages)
    * Module Manifests
      * [Manifest](reference/backend/module.html#manifest)
    * Security in Odoo
      * [Access Rights](reference/backend/security.html#access-rights)
      * [Record Rules](reference/backend/security.html#record-rules)
      * [Field Access](reference/backend/security.html#field-access)
      * [Security Pitfalls](reference/backend/security.html#security-pitfalls)
    * Performance
      * [Profiling](reference/backend/performance.html#profiling)
      * [Database population](reference/backend/performance.html#database-population)
      * [Good practices](reference/backend/performance.html#good-practices)
    * Testing Odoo
      * [Testing Python code](reference/backend/testing.html#testing-python-code)
      * [Testing JS code](reference/backend/testing.html#testing-js-code)
      * [Integration Testing](reference/backend/testing.html#integration-testing)
      * [Performance Testing](reference/backend/testing.html#performance-testing)
    * Web Controllers
      * [Controllers](reference/backend/http.html#controllers)
      * [API](reference/backend/http.html#api)
    * Mixins and Useful Classes
      * [Messaging features](reference/backend/mixins.html#messaging-features)
      * [Website features](reference/backend/mixins.html#website-features)
      * [Others](reference/backend/mixins.html#others)
  * Web framework
    * Framework Overview
      * [Introduction](reference/frontend/framework_overview.html#introduction)
      * [Code structure](reference/frontend/framework_overview.html#code-structure)
      * [WebClient Architecture](reference/frontend/framework_overview.html#webclient-architecture)
      * [Environment](reference/frontend/framework_overview.html#environment)
      * [Building Blocks](reference/frontend/framework_overview.html#building-blocks)
      * [Context](reference/frontend/framework_overview.html#context)
      * [Python Interpreter](reference/frontend/framework_overview.html#python-interpreter)
      * [Domains](reference/frontend/framework_overview.html#domains)
      * [Bus](reference/frontend/framework_overview.html#bus)
      * [Browser Object](reference/frontend/framework_overview.html#browser-object)
      * [Debug mode](reference/frontend/framework_overview.html#debug-mode)
    * Assets
      * [Asset types](reference/frontend/assets.html#asset-types)
      * [Bundles](reference/frontend/assets.html#bundles)
      * [Lazy loading](reference/frontend/assets.html#lazy-loading)
      * [The asset model (`ir.asset`)](reference/frontend/assets.html#the-asset-model-ir-asset)
    * Javascript Modules
      * [Plain Javascript files](reference/frontend/javascript_modules.html#plain-javascript-files)
      * [Native Javascript Modules](reference/frontend/javascript_modules.html#native-javascript-modules)
      * [Odoo Module System](reference/frontend/javascript_modules.html#odoo-module-system)
    * Owl components
      * [Using Owl components](reference/frontend/owl_components.html#using-owl-components)
      * [Best practices](reference/frontend/owl_components.html#best-practices)
      * [Reference List](reference/frontend/owl_components.html#reference-list)
    * Registries
      * [Registry API](reference/frontend/registries.html#registry-api)
      * [Reference List](reference/frontend/registries.html#reference-list)
    * Services
      * [Defining a service](reference/frontend/services.html#defining-a-service)
      * [Using a service](reference/frontend/services.html#using-a-service)
      * [Reference List](reference/frontend/services.html#reference-list)
    * Hooks
      * [useAssets](reference/frontend/hooks.html#useassets)
      * [useAutofocus](reference/frontend/hooks.html#useautofocus)
      * [useBus](reference/frontend/hooks.html#usebus)
      * [usePager](reference/frontend/hooks.html#usepager)
      * [usePosition](reference/frontend/hooks.html#useposition)
      * [useSpellCheck](reference/frontend/hooks.html#usespellcheck)
    * Patching code
      * [Description](reference/frontend/patching_code.html#description)
      * [Patching a simple object](reference/frontend/patching_code.html#patching-a-simple-object)
      * [Patching a javascript class](reference/frontend/patching_code.html#patching-a-javascript-class)
      * [Patching a component](reference/frontend/patching_code.html#patching-a-component)
      * [Removing a patch](reference/frontend/patching_code.html#removing-a-patch)
      * [Applying the same patch to multiple objects](reference/frontend/patching_code.html#applying-the-same-patch-to-multiple-objects)
    * Error handling
      * [Errors in JavaScript](reference/frontend/error_handling.html#errors-in-javascript)
      * [Lifecycle of errors within the Odoo JS framework](reference/frontend/error_handling.html#lifecycle-of-errors-within-the-odoo-js-framework)
      * [Avoid throwing errors as much as possible](reference/frontend/error_handling.html#avoid-throwing-errors-as-much-as-possible)
      * [Catching errors](reference/frontend/error_handling.html#catching-errors)
      * [Error free control flow](reference/frontend/error_handling.html#error-free-control-flow)
      * [When to throw errors](reference/frontend/error_handling.html#when-to-throw-errors)
    * Javascript Reference
      * [Overview](reference/frontend/javascript_reference.html#overview)
      * [Web client](reference/frontend/javascript_reference.html#web-client)
      * [Loading Javascript Code](reference/frontend/javascript_reference.html#loading-javascript-code)
      * [Registries](reference/frontend/javascript_reference.html#registries)
      * [Services](reference/frontend/javascript_reference.html#services)
      * [Notifications](reference/frontend/javascript_reference.html#notifications)
      * [Systray](reference/frontend/javascript_reference.html#systray)
      * [Translation management](reference/frontend/javascript_reference.html#translation-management)
      * [Session](reference/frontend/javascript_reference.html#session)
      * [Views](reference/frontend/javascript_reference.html#views)
      * [Fields](reference/frontend/javascript_reference.html#fields)
      * [Client actions](reference/frontend/javascript_reference.html#client-actions)
    * Mobile JavaScript
      * [Introduction](reference/frontend/mobile.html#introduction)
      * [How does it work?](reference/frontend/mobile.html#how-does-it-work)
      * [How to use it?](reference/frontend/mobile.html#how-to-use-it)
    * QWeb Templates
      * [Data output](reference/frontend/qweb.html#data-output)
      * [Conditionals](reference/frontend/qweb.html#conditionals)
      * [Loops](reference/frontend/qweb.html#loops)
      * [attributes](reference/frontend/qweb.html#attributes)
      * [setting variables](reference/frontend/qweb.html#setting-variables)
      * [calling sub-templates](reference/frontend/qweb.html#calling-sub-templates)
      * [Advanced Output](reference/frontend/qweb.html#advanced-output)
      * [Python](reference/frontend/qweb.html#id3)
      * [Javascript](reference/frontend/qweb.html#javascript)
    * Odoo Editor
      * [Powerbox](reference/frontend/odoo_editor.html#powerbox)
  * User interface
    * View records
      * [Generic structure](reference/user_interface/view_records.html#generic-structure)
      * [View types](reference/user_interface/view_records.html#view-types)
      * [Fields](reference/user_interface/view_records.html#fields)
      * [Inheritance](reference/user_interface/view_records.html#inheritance)
      * [Model commons](reference/user_interface/view_records.html#model-commons)
    * View architectures
      * [Generic architecture](reference/user_interface/view_architectures.html#generic-architecture)
      * [Python expression](reference/user_interface/view_architectures.html#python-expression)
      * [Form](reference/user_interface/view_architectures.html#form)
      * [Settings](reference/user_interface/view_architectures.html#settings)
      * [List](reference/user_interface/view_architectures.html#list)
      * [Search](reference/user_interface/view_architectures.html#search)
      * [Kanban](reference/user_interface/view_architectures.html#kanban)
      * [QWeb](reference/user_interface/view_architectures.html#qweb)
      * [Graph](reference/user_interface/view_architectures.html#graph)
      * [Pivot](reference/user_interface/view_architectures.html#pivot)
      * [Calendar](reference/user_interface/view_architectures.html#calendar)
      * [Activity](reference/user_interface/view_architectures.html#activity)
      * [Cohort](reference/user_interface/view_architectures.html#cohort)
      * [Grid](reference/user_interface/view_architectures.html#grid)
      * [Gantt](reference/user_interface/view_architectures.html#gantt)
      * [Map](reference/user_interface/view_architectures.html#map)
    * SCSS inheritance
      * [Overview](reference/user_interface/scss_inheritance.html#overview)
      * [SCSS’s `!default` directive](reference/user_interface/scss_inheritance.html#scss-s-default-directive)
      * [Odoo’s SCSS inheritance system](reference/user_interface/scss_inheritance.html#odoo-s-scss-inheritance-system)
    * UI icons
      * [Icons](reference/user_interface/icons.html#icons)
      * [RTL adaptations](reference/user_interface/icons.html#rtl-adaptations)
  * Standard modules
    * Accounting
      * [Account Tag](reference/standard_modules/account/account_account_tag.html)
      * [Account](reference/standard_modules/account/account_account.html)
      * [Fiscal Position](reference/standard_modules/account/account_fiscal_position.html)
      * [Account Group](reference/standard_modules/account/account_group.html)
      * [Report](reference/standard_modules/account/account_report.html)
      * [Report Line](reference/standard_modules/account/account_report_line.html)
      * [Taxes](reference/standard_modules/account/account_tax.html)
      * [Tax Repartitions](reference/standard_modules/account/account_tax_repartition.html)
    * Payment
      * [Payment Method](reference/standard_modules/payment/payment_method.html)
      * [Payment Provider](reference/standard_modules/payment/payment_provider.html)
      * [Payment Token](reference/standard_modules/payment/payment_token.html)
      * [Payment Transaction](reference/standard_modules/payment/payment_transaction.html)
  * Command-line interface (CLI)
    * [Help & version](reference/cli.html#help-version)
    * [Running the server](reference/cli.html#running-the-server)
    * Testing Configuration
      * [Database](reference/cli.html#database)
      * [Emails](reference/cli.html#emails)
      * [Internationalisation](reference/cli.html#internationalisation)
      * [Advanced Options](reference/cli.html#advanced-options)
    * [Configuration file](reference/cli.html#configuration-file)
    * [Shell](reference/cli.html#shell)
    * [Neutralize](reference/cli.html#neutralize)
    * [Scaffolding](reference/cli.html#scaffolding)
    * [Database Population](reference/cli.html#database-population)
    * Cloc
      * [Command-line options](reference/cli.html#command-line-options)
      * [Processed files](reference/cli.html#processed-files)
      * [Identifying Extra Modules](reference/cli.html#identifying-extra-modules)
      * [Error Handling](reference/cli.html#error-handling)
    * [TSConfig Generator](reference/cli.html#tsconfig-generator)
  * Upgrades
    * Upgrade scripts
      * [Writing upgrade scripts](reference/upgrades/upgrade_scripts.html#writing-upgrade-scripts)
      * [Phases of upgrade scripts](reference/upgrades/upgrade_scripts.html#phases-of-upgrade-scripts)
    * Upgrade utils
      * [Installation](reference/upgrades/upgrade_utils.html#installation)
      * [Using upgrade utils](reference/upgrades/upgrade_utils.html#using-upgrade-utils)
      * [Util functions](reference/upgrades/upgrade_utils.html#util-functions)
  * External API
    * Connection
      * [Configuration](reference/external_api.html#configuration)
      * [Logging in](reference/external_api.html#logging-in)
    * Calling methods
      * [List records](reference/external_api.html#list-records)
      * [Count records](reference/external_api.html#count-records)
      * [Read records](reference/external_api.html#read-records)
      * [List record fields](reference/external_api.html#list-record-fields)
      * [Search and read](reference/external_api.html#search-and-read)
      * [Create records](reference/external_api.html#create-records)
      * [Update records](reference/external_api.html#update-records)
      * [Delete records](reference/external_api.html#delete-records)
      * [Inspection and introspection](reference/external_api.html#inspection-and-introspection)
  * Extract API
    * Overview
      * [Version](reference/extract_api.html#version)
      * [Flow](reference/extract_api.html#flow)
    * Parse
      * [Routes](reference/extract_api.html#routes)
      * [Request](reference/extract_api.html#request)
      * [Response](reference/extract_api.html#response)
    * Get results
      * [Routes](reference/extract_api.html#extract-api-get-result)
      * [Request](reference/extract_api.html#id2)
      * [Response](reference/extract_api.html#id3)
    * [Integration Testing](reference/extract_api.html#integration-testing)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](reference/backend.html "Server framework") |
  * [precedente](howtos/upgrade_custom_db.html "Upgrade a customized database") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Developer](../developer.html) »
  * Reference