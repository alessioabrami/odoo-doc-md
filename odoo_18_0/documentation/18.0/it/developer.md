# Developer — Odoo 18.0 documentazione

### Navigazione

  * [indice](genindex.html "Indice generale")
  * [moduli](py-modindex.html "Indice del modulo Python") |
  * [successivo](developer/tutorials.html "Tutorials") |
  * [precedente](administration/odoo_accounts.html "Account odoo.com") |
  * [Odoo 18.0 documentazione](index-2.html) »
  * Developer



# Developer¶

  * [Tutorials](developer/tutorials.html)
    * Setup guide
      * [Adapt the environment for the tutorials](developer/tutorials/setup_guide.html#adapt-the-environment-for-the-tutorials)
      * Run the server
        * [Launch with `odoo-bin`](developer/tutorials/setup_guide.html#launch-with-odoo-bin)
        * [Log in to Odoo](developer/tutorials/setup_guide.html#log-in-to-odoo)
      * [Enable the developer mode](developer/tutorials/setup_guide.html#enable-the-developer-mode)
      * Extra tools
        * [Useful Git commands](developer/tutorials/setup_guide.html#useful-git-commands)
        * [Code Editor](developer/tutorials/setup_guide.html#code-editor)
        * [Administrator tools for PostgreSQL](developer/tutorials/setup_guide.html#administrator-tools-for-postgresql)
        * [Python Debugging](developer/tutorials/setup_guide.html#python-debugging)
    * [Server framework 101](developer/tutorials/server_framework_101.html)
      * Chapter 1: Architecture Overview
        * [Multitier application](developer/tutorials/server_framework_101/01_architecture.html#multitier-application)
        * Odoo modules
          * [Composition of a module](developer/tutorials/server_framework_101/01_architecture.html#composition-of-a-module)
          * [Module structure](developer/tutorials/server_framework_101/01_architecture.html#module-structure)
        * [Odoo Editions](developer/tutorials/server_framework_101/01_architecture.html#odoo-editions)
      * Chapter 2: A New Application
        * [The Real Estate Advertisement module](developer/tutorials/server_framework_101/02_newapp.html#the-real-estate-advertisement-module)
        * [Prepare the addon directory](developer/tutorials/server_framework_101/02_newapp.html#prepare-the-addon-directory)
      * Chapter 3: Models And Basic Fields
        * [Object-Relational Mapping](developer/tutorials/server_framework_101/03_basicmodel.html#object-relational-mapping)
        * Model fields
          * [Types](developer/tutorials/server_framework_101/03_basicmodel.html#types)
          * [Common Attributes](developer/tutorials/server_framework_101/03_basicmodel.html#common-attributes)
          * [Automatic Fields](developer/tutorials/server_framework_101/03_basicmodel.html#automatic-fields)
      * Chapter 4: Security - A Brief Introduction
        * [Data Files (CSV)](developer/tutorials/server_framework_101/04_securityintro.html#data-files-csv)
        * [Access Rights](developer/tutorials/server_framework_101/04_securityintro.html#access-rights)
      * Chapter 5: Finally, Some UI To Play With
        * [Data Files (XML)](developer/tutorials/server_framework_101/05_firstui.html#data-files-xml)
        * [Actions](developer/tutorials/server_framework_101/05_firstui.html#actions)
        * [Menus](developer/tutorials/server_framework_101/05_firstui.html#menus)
        * Fields, Attributes And View
          * [Some New Attributes](developer/tutorials/server_framework_101/05_firstui.html#some-new-attributes)
          * [Default Values](developer/tutorials/server_framework_101/05_firstui.html#default-values)
          * [Reserved Fields](developer/tutorials/server_framework_101/05_firstui.html#reserved-fields)
      * Chapter 6: Basic Views
        * [List](developer/tutorials/server_framework_101/06_basicviews.html#list)
        * [Form](developer/tutorials/server_framework_101/06_basicviews.html#form)
        * Search
          * [Domains](developer/tutorials/server_framework_101/06_basicviews.html#domains)
      * Chapter 7: Relations Between Models
        * [Many2one](developer/tutorials/server_framework_101/07_relations.html#many2one)
        * [Many2many](developer/tutorials/server_framework_101/07_relations.html#many2many)
        * [One2many](developer/tutorials/server_framework_101/07_relations.html#one2many)
      * Chapter 8: Computed Fields And Onchanges
        * Computed Fields
          * [Dependencies](developer/tutorials/server_framework_101/08_compute_onchange.html#dependencies)
          * [Inverse Function](developer/tutorials/server_framework_101/08_compute_onchange.html#inverse-function)
          * [Additional Information](developer/tutorials/server_framework_101/08_compute_onchange.html#additional-information)
        * Onchanges
          * [Additional Information](developer/tutorials/server_framework_101/08_compute_onchange.html#id1)
        * [How to use them?](developer/tutorials/server_framework_101/08_compute_onchange.html#how-to-use-them)
      * Chapter 9: Ready For Some Action?
        * [Object Type](developer/tutorials/server_framework_101/09_actions.html#object-type)
        * [Action Type](developer/tutorials/server_framework_101/09_actions.html#action-type)
      * Chapter 10: Constraints
        * [SQL](developer/tutorials/server_framework_101/10_constraints.html#sql)
        * [Python](developer/tutorials/server_framework_101/10_constraints.html#python)
      * Chapter 11: Add The Sprinkles
        * [Inline Views](developer/tutorials/server_framework_101/11_sprinkles.html#inline-views)
        * [Widgets](developer/tutorials/server_framework_101/11_sprinkles.html#widgets)
        * List Order
          * [Model](developer/tutorials/server_framework_101/11_sprinkles.html#model)
          * [View](developer/tutorials/server_framework_101/11_sprinkles.html#view)
          * [Manual](developer/tutorials/server_framework_101/11_sprinkles.html#manual)
        * Attributes and options
          * [Form](developer/tutorials/server_framework_101/11_sprinkles.html#form)
          * [List](developer/tutorials/server_framework_101/11_sprinkles.html#list)
          * [Search](developer/tutorials/server_framework_101/11_sprinkles.html#search)
        * [Stat Buttons](developer/tutorials/server_framework_101/11_sprinkles.html#stat-buttons)
      * Chapter 12: Inheritance
        * [Python Inheritance](developer/tutorials/server_framework_101/12_inheritance.html#python-inheritance)
        * [Model Inheritance](developer/tutorials/server_framework_101/12_inheritance.html#model-inheritance)
        * [View Inheritance](developer/tutorials/server_framework_101/12_inheritance.html#view-inheritance)
      * Chapter 13: Interact With Other Modules
        * Concrete Example: Account Move
          * [Link Module](developer/tutorials/server_framework_101/13_other_module.html#link-module)
          * [Invoice Creation](developer/tutorials/server_framework_101/13_other_module.html#invoice-creation)
      * Chapter 14: A Brief History Of QWeb
        * [Concrete Example: A Kanban View](developer/tutorials/server_framework_101/14_qwebintro.html#concrete-example-a-kanban-view)
      * Chapter 15: The final word
        * [Coding guidelines](developer/tutorials/server_framework_101/15_final_word.html#coding-guidelines)
        * [Test on the runbot](developer/tutorials/server_framework_101/15_final_word.html#test-on-the-runbot)
    * [Discover the web framework](developer/tutorials/discover_js_framework.html)
      * Chapter 1: Owl components
        * [Example: a `Counter` component](developer/tutorials/discover_js_framework/01_owl_components.html#example-a-counter-component)
        * [1\. Displaying a counter](developer/tutorials/discover_js_framework/01_owl_components.html#displaying-a-counter)
        * [2\. Extract `Counter` in a sub component](developer/tutorials/discover_js_framework/01_owl_components.html#extract-counter-in-a-sub-component)
        * [3\. A simple `Card` component](developer/tutorials/discover_js_framework/01_owl_components.html#a-simple-card-component)
        * [4\. Using `markup` to display html](developer/tutorials/discover_js_framework/01_owl_components.html#using-markup-to-display-html)
        * [5\. Props validation](developer/tutorials/discover_js_framework/01_owl_components.html#props-validation)
        * [6\. The sum of two `Counter`](developer/tutorials/discover_js_framework/01_owl_components.html#the-sum-of-two-counter)
        * [7\. A todo list](developer/tutorials/discover_js_framework/01_owl_components.html#a-todo-list)
        * [8\. Use dynamic attributes](developer/tutorials/discover_js_framework/01_owl_components.html#use-dynamic-attributes)
        * [9\. Adding a todo](developer/tutorials/discover_js_framework/01_owl_components.html#adding-a-todo)
        * [Theory: Component lifecycle and hooks](developer/tutorials/discover_js_framework/01_owl_components.html#theory-component-lifecycle-and-hooks)
        * [10\. Focusing the input](developer/tutorials/discover_js_framework/01_owl_components.html#focusing-the-input)
        * [11\. Toggling todos](developer/tutorials/discover_js_framework/01_owl_components.html#toggling-todos)
        * [12\. Deleting todos](developer/tutorials/discover_js_framework/01_owl_components.html#deleting-todos)
        * [13\. Generic `Card` with slots](developer/tutorials/discover_js_framework/01_owl_components.html#generic-card-with-slots)
        * [14\. Minimizing card content](developer/tutorials/discover_js_framework/01_owl_components.html#minimizing-card-content)
      * Chapter 2: Build a dashboard
        * [1\. A new Layout](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#a-new-layout)
        * [Theory: Services](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#theory-services)
        * [2\. Add some buttons for quick navigation](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#add-some-buttons-for-quick-navigation)
        * [3\. Add a dashboard item](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#add-a-dashboard-item)
        * [4\. Call the server, add some statistics](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#call-the-server-add-some-statistics)
        * [5\. Cache network calls, create a service](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#cache-network-calls-create-a-service)
        * [6\. Display a pie chart](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#display-a-pie-chart)
        * [7\. Real life update](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#real-life-update)
        * [8\. Lazy loading the dashboard](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#lazy-loading-the-dashboard)
        * [9\. Making our dashboard generic](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#making-our-dashboard-generic)
        * [10\. Making our dashboard extensible](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#making-our-dashboard-extensible)
        * [11\. Add and remove dashboard items](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#add-and-remove-dashboard-items)
        * [12\. Going further](developer/tutorials/discover_js_framework/02_build_a_dashboard.html#going-further)
      * [Setup](developer/tutorials/discover_js_framework.html#setup)
      * [Content](developer/tutorials/discover_js_framework.html#content)
    * [Master the web framework](developer/tutorials/master_odoo_web_framework.html)
      * Chapter 1: Build a Clicker game
        * [1\. Create a systray item](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#create-a-systray-item)
        * [2\. Count external clicks](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#count-external-clicks)
        * [3\. Create a client action](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#create-a-client-action)
        * [4\. Move the state to a service](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#move-the-state-to-a-service)
        * [5\. Use a custom hook](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#use-a-custom-hook)
        * [6\. Humanize the displayed value](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#humanize-the-displayed-value)
        * [7\. Add a tooltip in `ClickValue` component](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-a-tooltip-in-clickvalue-component)
        * [8\. Buy ClickBots](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#buy-clickbots)
        * [9\. Refactor to a class model](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#refactor-to-a-class-model)
        * [10\. Notify when a milestone is reached](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#notify-when-a-milestone-is-reached)
        * [11\. Add BigBots](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-bigbots)
        * [12\. Add a new type of resource: power](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-a-new-type-of-resource-power)
        * [13\. Define some random rewards](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#define-some-random-rewards)
        * [14\. Provide a reward when opening a form view](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#provide-a-reward-when-opening-a-form-view)
        * [15\. Add commands in command palette](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-commands-in-command-palette)
        * [16\. Add yet another resource: trees](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-yet-another-resource-trees)
        * [17\. Use a dropdown menu for the systray item](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#use-a-dropdown-menu-for-the-systray-item)
        * [18\. Use a Notebook component](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#use-a-notebook-component)
        * [19\. Persist the game state](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#persist-the-game-state)
        * [20\. Introduce state migration system](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#introduce-state-migration-system)
        * [21\. Add another type of trees](developer/tutorials/master_odoo_web_framework/01_build_clicker_game.html#add-another-type-of-trees)
      * Chapter 2: Create a Gallery View
        * [1\. Make a hello world view](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#make-a-hello-world-view)
        * [2\. Use the Layout component](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#use-the-layout-component)
        * [3\. Parse the arch](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#parse-the-arch)
        * [4\. Load some data](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#load-some-data)
        * [5\. Solve the concurrency problem](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#solve-the-concurrency-problem)
        * [6\. Reorganize code](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#reorganize-code)
        * [7\. Make the view extensible](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#make-the-view-extensible)
        * [8\. Display images](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#display-images)
        * [9\. Switch to form view on click](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#switch-to-form-view-on-click)
        * [10\. Add an optional tooltip](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#add-an-optional-tooltip)
        * [11\. Add pagination](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#add-pagination)
        * [12\. Validating views](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#validating-views)
        * [13\. Uploading an image](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#uploading-an-image)
        * [14\. Advanced tooltip template](developer/tutorials/master_odoo_web_framework/02_create_gallery_view.html#advanced-tooltip-template)
      * Chapter 3: Customize a kanban view
        * [1\. Create a new kanban view](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#create-a-new-kanban-view)
        * [2\. Create a CustomerList component](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#create-a-customerlist-component)
        * [3\. Load and display data](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#load-and-display-data)
        * [4\. Update the main kanban view](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#update-the-main-kanban-view)
        * [5\. Only display customers which have an active order](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#only-display-customers-which-have-an-active-order)
        * [6\. Add a search bar to the customer list](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#add-a-search-bar-to-the-customer-list)
        * [7\. Refactor the code to use `t-model`](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#refactor-the-code-to-use-t-model)
        * [8\. Paginate customers!](developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.html#paginate-customers)
      * [Setup](developer/tutorials/master_odoo_web_framework.html#setup)
      * [Content](developer/tutorials/master_odoo_web_framework.html#content)
    * Define module data
      * Data Types
        * [Master Data](developer/tutorials/define_module_data.html#master-data)
        * [Demo Data](developer/tutorials/define_module_data.html#demo-data)
      * Data Declaration
        * [Manifest](developer/tutorials/define_module_data.html#manifest)
        * [CSV](developer/tutorials/define_module_data.html#csv)
        * XML
          * [Data Extension](developer/tutorials/define_module_data.html#data-extension)
          * [`ref`](developer/tutorials/define_module_data.html#ref)
          * [`eval`](developer/tutorials/define_module_data.html#eval)
          * [`search`](developer/tutorials/define_module_data.html#search)
          * [`function`](developer/tutorials/define_module_data.html#function)
        * [Add X2many fields](developer/tutorials/define_module_data.html#add-x2many-fields)
      * [Accessing the data](developer/tutorials/define_module_data.html#accessing-the-data)
      * Advanced
        * [What is the XML id?](developer/tutorials/define_module_data.html#what-is-the-xml-id)
        * [No update](developer/tutorials/define_module_data.html#no-update)
        * [Import as SQL](developer/tutorials/define_module_data.html#import-as-sql)
    * Restrict access to data
      * [Groups](developer/tutorials/restrict_data_access.html#groups)
      * [Access Rights](developer/tutorials/restrict_data_access.html#access-rights)
      * [Record Rules](developer/tutorials/restrict_data_access.html#record-rules)
      * Security Override
        * [Bypassing Security](developer/tutorials/restrict_data_access.html#bypassing-security)
        * [Programmatically checking security](developer/tutorials/restrict_data_access.html#programmatically-checking-security)
      * [Multi-company security](developer/tutorials/restrict_data_access.html#multi-company-security)
      * [Visibility != security](developer/tutorials/restrict_data_access.html#visibility-security)
    * Safeguard your code with unit tests
      * [Running Tests](developer/tutorials/unit_tests.html#running-tests)
      * Integration Bots
        * [Runbot](developer/tutorials/unit_tests.html#runbot)
        * [Robodoo](developer/tutorials/unit_tests.html#robodoo)
        * [Mergebot](developer/tutorials/unit_tests.html#mergebot)
      * [Modules](developer/tutorials/unit_tests.html#modules)
      * [Writing a test](developer/tutorials/unit_tests.html#writing-a-test)
    * Write importable modules
      * [Problem statement](developer/tutorials/importable_modules.html#problem-statement)
      * [Module structure](developer/tutorials/importable_modules.html#module-structure)
      * [Deploying the module](developer/tutorials/importable_modules.html#deploying-the-module)
      * Models and basic fields
        * [Default values](developer/tutorials/importable_modules.html#default-values)
      * [Security](developer/tutorials/importable_modules.html#security)
      * [Views](developer/tutorials/importable_modules.html#views)
      * Relations
        * [Many-to-one](developer/tutorials/importable_modules.html#many-to-one)
        * [Many-to-many](developer/tutorials/importable_modules.html#many-to-many)
        * [One-to-many](developer/tutorials/importable_modules.html#one-to-many)
      * Computed and related fields
        * [Computed fields](developer/tutorials/importable_modules.html#computed-fields)
        * [Related fields](developer/tutorials/importable_modules.html#related-fields)
      * Code and business logic
        * [Server actions](developer/tutorials/importable_modules.html#server-actions)
        * Overriding Python models
          * [Via UI elements](developer/tutorials/importable_modules.html#via-ui-elements)
          * [Via automation rules](developer/tutorials/importable_modules.html#via-automation-rules)
        * [Website controllers](developer/tutorials/importable_modules.html#website-controllers)
      * [A sprinkle of JavaScript](developer/tutorials/importable_modules.html#a-sprinkle-of-javascript)
    * [Reuse code with mixins](developer/tutorials/mixins.html)
    * Build PDF Reports
      * [File Structure](developer/tutorials/pdf_reports.html#file-structure)
      * Basic Report
        * [Report Data](developer/tutorials/pdf_reports.html#report-data)
        * [Minimal Template](developer/tutorials/pdf_reports.html#minimal-template)
        * [Report Action](developer/tutorials/pdf_reports.html#report-action)
        * [Make a Report](developer/tutorials/pdf_reports.html#make-a-report)
      * [Sub-templates](developer/tutorials/pdf_reports.html#sub-templates)
      * [Report Inheritance](developer/tutorials/pdf_reports.html#report-inheritance)
      * Additional Features
        * [Translations](developer/tutorials/pdf_reports.html#translations)
        * [Reports are web pages](developer/tutorials/pdf_reports.html#reports-are-web-pages)
        * [Barcodes](developer/tutorials/pdf_reports.html#barcodes)
    * [Build a website theme](developer/tutorials/website_theme.html)
      * Chapter 1 - Theming
        * [Setup](developer/tutorials/website_theme/01_theming.html#setup)
        * [Build your module structure](developer/tutorials/website_theme/01_theming.html#build-your-module-structure)
        * [Declare Odoo variables](developer/tutorials/website_theme/01_theming.html#declare-odoo-variables)
        * [Declare Bootstrap variables](developer/tutorials/website_theme/01_theming.html#declare-bootstrap-variables)
        * [Define presets](developer/tutorials/website_theme/01_theming.html#define-presets)
      * Chapter 2 - Build your website
        * [Create a page](developer/tutorials/website_theme/02_build_website.html#create-a-page)
        * [Add a media](developer/tutorials/website_theme/02_build_website.html#add-a-media)
        * [Add building blocks](developer/tutorials/website_theme/02_build_website.html#add-building-blocks)
        * [Navigation](developer/tutorials/website_theme/02_build_website.html#navigation)
      * Chapter 3 - Customisation, Part I
        * [Add custom SCSS](developer/tutorials/website_theme/03_customisation_part1.html#add-custom-scss)
        * [Add custom JS](developer/tutorials/website_theme/03_customisation_part1.html#add-custom-js)
        * [Create a custom header](developer/tutorials/website_theme/03_customisation_part1.html#create-a-custom-header)
        * [Create a custom footer](developer/tutorials/website_theme/03_customisation_part1.html#create-a-custom-footer)
        * [Create your custom building blocks](developer/tutorials/website_theme/03_customisation_part1.html#create-your-custom-building-blocks)
        * [Create a new dynamic snippets template](developer/tutorials/website_theme/03_customisation_part1.html#create-a-new-dynamic-snippets-template)
      * Chapter 4 - Customisation, Part II
        * [Create a custom background shape](developer/tutorials/website_theme/04_customisation_part2.html#create-a-custom-background-shape)
        * [Add a background gradient](developer/tutorials/website_theme/04_customisation_part2.html#add-a-background-gradient)
        * [Animations](developer/tutorials/website_theme/04_customisation_part2.html#animations)
        * [Forms](developer/tutorials/website_theme/04_customisation_part2.html#forms)
      * Chapter 5 - Dynamic templates
        * [Adapt the shop template](developer/tutorials/website_theme/05_dynamic_templates.html#adapt-the-shop-template)
        * [Adapt the product page template](developer/tutorials/website_theme/05_dynamic_templates.html#adapt-the-product-page-template)
      * Chapter 6 - Going live
        * [Translations](developer/tutorials/website_theme/06_going_live.html#translations)
        * [Module import](developer/tutorials/website_theme/06_going_live.html#module-import)
        * [Conclusion](developer/tutorials/website_theme/06_going_live.html#conclusion)
    * [Learn the server and web frameworks](developer/tutorials.html#learn-the-server-and-web-frameworks)
    * [Expand your knowledge on the server framework](developer/tutorials.html#expand-your-knowledge-on-the-server-framework)
  * [How-to guides](developer/howtos.html)
    * Write lean easy-to-maintain CSS
      * [Browser defaults](developer/howtos/scss_tips.html#browser-defaults)
      * [HTML tags](developer/howtos/scss_tips.html#html-tags)
      * Utility classes
        * [Handling utility-classes verbosity](developer/howtos/scss_tips.html#handling-utility-classes-verbosity)
    * Customize a field
      * [Subclass an existing field component](developer/howtos/javascript_field.html#subclass-an-existing-field-component)
      * [Create a new field component](developer/howtos/javascript_field.html#create-a-new-field-component)
    * Customize a view type
      * [Subclass an existing view](developer/howtos/javascript_view.html#subclass-an-existing-view)
      * [Create a new view from scratch](developer/howtos/javascript_view.html#create-a-new-view-from-scratch)
    * [Create a client action](developer/howtos/javascript_client_action.html)
    * Create a standalone Owl application
      * [Overview](developer/howtos/standalone_owl_application.html#overview)
      * [1\. Root component](developer/howtos/standalone_owl_application.html#root-component)
      * [2\. Creating an assets bundle containing our code](developer/howtos/standalone_owl_application.html#creating-an-assets-bundle-containing-our-code)
      * [3\. XML view that calls the assets bundle](developer/howtos/standalone_owl_application.html#xml-view-that-calls-the-assets-bundle)
      * [4\. Controller that renders the view](developer/howtos/standalone_owl_application.html#controller-that-renders-the-view)
    * Use Owl components on the portal and website
      * [Overview](developer/howtos/frontend_owl_components.html#overview)
      * [1\. Creating the Owl component](developer/howtos/frontend_owl_components.html#creating-the-owl-component)
      * [2\. Adding your component to the `web.assets_frontend` bundle](developer/howtos/frontend_owl_components.html#adding-your-component-to-the-web-assets-frontend-bundle)
      * [3\. Adding an `<owl-component>` tag to a page](developer/howtos/frontend_owl_components.html#adding-an-owl-component-tag-to-a-page)
      * Points of caution
        * [Layout shift](developer/howtos/frontend_owl_components.html#layout-shift)
        * [Poorer indexing by search engines](developer/howtos/frontend_owl_components.html#poorer-indexing-by-search-engines)
      * When to use Owl components on the portal and website
        * [When you don’t care about SEO](developer/howtos/frontend_owl_components.html#when-you-don-t-care-about-seo)
        * [When you need strong interactivity](developer/howtos/frontend_owl_components.html#when-you-need-strong-interactivity)
    * [Website themes](developer/howtos/website_themes.html)
      * Setup
        * [Install](developer/howtos/website_themes/setup.html#install)
        * Databases
          * Structure
            * [Models](developer/howtos/website_themes/setup.html#models)
            * Fields
              * [Classic fields](developer/howtos/website_themes/setup.html#classic-fields)
              * [Relational fields](developer/howtos/website_themes/setup.html#relational-fields)
            * Views
              * [Backend vs. Frontend](developer/howtos/website_themes/setup.html#backend-vs-frontend)
              * [Static vs. Dynamic](developer/howtos/website_themes/setup.html#static-vs-dynamic)
              * [Standard vs. Inherited](developer/howtos/website_themes/setup.html#standard-vs-inherited)
          * Import an existing database
            * Dump
              * [Odoo SaaS](developer/howtos/website_themes/setup.html#odoo-saas)
              * [Odoo.sh](developer/howtos/website_themes/setup.html#odoo-sh)
            * [Move filestore](developer/howtos/website_themes/setup.html#move-filestore)
            * [Database setup](developer/howtos/website_themes/setup.html#database-setup)
        * Getting started
          * [Running Odoo](developer/howtos/website_themes/setup.html#running-odoo)
          * [Shell script](developer/howtos/website_themes/setup.html#shell-script)
          * [Sign in](developer/howtos/website_themes/setup.html#sign-in)
          * [Developer mode](developer/howtos/website_themes/setup.html#developer-mode)
      * Theming
        * Theme module
          * [Technical naming](developer/howtos/website_themes/theming.html#technical-naming)
          * [File structure](developer/howtos/website_themes/theming.html#file-structure)
          * [Initialization](developer/howtos/website_themes/theming.html#initialization)
          * [Declaration](developer/howtos/website_themes/theming.html#declaration)
        * Default options
          * Odoo variables
            * [Global](developer/howtos/website_themes/theming.html#global)
            * Fonts
              * [Google fonts](developer/howtos/website_themes/theming.html#google-fonts)
              * [Custom fonts](developer/howtos/website_themes/theming.html#custom-fonts)
            * [Colors](developer/howtos/website_themes/theming.html#colors)
            * [Gradients](developer/howtos/website_themes/theming.html#gradients)
          * Bootstrap variables
            * Font sizes
              * [Text style](developer/howtos/website_themes/theming.html#text-style)
              * Sizing classes
                * [Heading and body text](developer/howtos/website_themes/theming.html#heading-and-body-text)
                * [Display headings](developer/howtos/website_themes/theming.html#display-headings)
          * [Website settings](developer/howtos/website_themes/theming.html#website-settings)
          * Views
            * [Presets](developer/howtos/website_themes/theming.html#presets)
        * Assets
          * [Styles](developer/howtos/website_themes/theming.html#styles)
          * [Interactivity](developer/howtos/website_themes/theming.html#interactivity)
      * Layout
        * [Default](developer/howtos/website_themes/layout.html#default)
        * XPath
          * [Expressions](developer/howtos/website_themes/layout.html#expressions)
          * [Position](developer/howtos/website_themes/layout.html#position)
        * [QWeb](developer/howtos/website_themes/layout.html#qweb)
        * Custom fields
          * [Declaration](developer/howtos/website_themes/layout.html#declaration)
          * [Back-end](developer/howtos/website_themes/layout.html#back-end)
          * [Front-end](developer/howtos/website_themes/layout.html#front-end)
        * Background
          * [Colors](developer/howtos/website_themes/layout.html#colors)
          * [Image/pattern](developer/howtos/website_themes/layout.html#image-pattern)
        * Header
          * Standard
            * [Desktop template](developer/howtos/website_themes/layout.html#desktop-template)
            * [Mobile template](developer/howtos/website_themes/layout.html#mobile-template)
          * [Custom](developer/howtos/website_themes/layout.html#custom)
          * Components
            * [Logo](developer/howtos/website_themes/layout.html#logo)
            * [Menu](developer/howtos/website_themes/layout.html#menu)
            * [Sign in](developer/howtos/website_themes/layout.html#sign-in)
            * [User dropdown](developer/howtos/website_themes/layout.html#user-dropdown)
            * [Language selector](developer/howtos/website_themes/layout.html#language-selector)
            * [Call to action](developer/howtos/website_themes/layout.html#call-to-action)
            * [Navbar toggler](developer/howtos/website_themes/layout.html#navbar-toggler)
        * Footer
          * [Standard](developer/howtos/website_themes/layout.html#website-themes-layout-footer-standard)
          * [Custom](developer/howtos/website_themes/layout.html#website-themes-layout-footer-custom)
        * [Copyright](developer/howtos/website_themes/layout.html#copyright)
        * [Drop zone](developer/howtos/website_themes/layout.html#drop-zone)
        * Responsive
          * [Font sizes](developer/howtos/website_themes/layout.html#font-sizes)
          * [Column sizes](developer/howtos/website_themes/layout.html#column-sizes)
          * [Visibility conditions](developer/howtos/website_themes/layout.html#visibility-conditions)
      * Navigation
        * [Default](developer/howtos/website_themes/navigation.html#default)
        * Menu item
          * [New window](developer/howtos/website_themes/navigation.html#new-window)
          * [External Links](developer/howtos/website_themes/navigation.html#external-links)
          * [Anchor](developer/howtos/website_themes/navigation.html#anchor)
        * [Dropdown menu](developer/howtos/website_themes/navigation.html#dropdown-menu)
        * Mega menu
          * [Custom template](developer/howtos/website_themes/navigation.html#custom-template)
      * Pages
        * [Default pages](developer/howtos/website_themes/pages.html#default-pages)
        * Theme pages
          * [`noupdate` attribute](developer/howtos/website_themes/pages.html#noupdate-attribute)
          * [Header overlay](developer/howtos/website_themes/pages.html#header-overlay)
          * [Page templates](developer/howtos/website_themes/pages.html#page-templates)
      * Media
        * Images
          * [Declaration](developer/howtos/website_themes/media.html#declaration)
          * Use
            * [Regular images](developer/howtos/website_themes/media.html#regular-images)
            * [Background images](developer/howtos/website_themes/media.html#background-images)
            * [Company logo](developer/howtos/website_themes/media.html#company-logo)
        * [Videos](developer/howtos/website_themes/media.html#videos)
        * [Icons](developer/howtos/website_themes/media.html#icons)
      * Building blocks
        * [File structure](developer/howtos/website_themes/building_blocks.html#file-structure)
        * Layout
          * [Wrapper](developer/howtos/website_themes/building_blocks.html#wrapper)
          * Elements
            * [Sizing](developer/howtos/website_themes/building_blocks.html#sizing)
            * [Colors](developer/howtos/website_themes/building_blocks.html#colors)
            * Features
              * [Non-editable areas](developer/howtos/website_themes/building_blocks.html#non-editable-areas)
              * [Backgrounds](developer/howtos/website_themes/building_blocks.html#backgrounds)
              * [Text highlights](developer/howtos/website_themes/building_blocks.html#text-highlights)
          * Grid layout
            * [Use](developer/howtos/website_themes/building_blocks.html#use)
            * [Items in a grid](developer/howtos/website_themes/building_blocks.html#items-in-a-grid)
            * [Grid item padding](developer/howtos/website_themes/building_blocks.html#grid-item-padding)
        * [Compatibility system](developer/howtos/website_themes/building_blocks.html#compatibility-system)
        * Custom snippet
          * Template
            * [1\. Declaration](developer/howtos/website_themes/building_blocks.html#declaration)
            * [2\. Group creation](developer/howtos/website_themes/building_blocks.html#group-creation)
            * [3\. Snippet addition](developer/howtos/website_themes/building_blocks.html#snippet-addition)
            * [Inner content snippet](developer/howtos/website_themes/building_blocks.html#inner-content-snippet)
          * Options
            * [Template](developer/howtos/website_themes/building_blocks.html#website-themes-building-blocks-custom-options-template)
            * Binding
              * [data-selector](developer/howtos/website_themes/building_blocks.html#data-selector)
              * [data-target](developer/howtos/website_themes/building_blocks.html#data-target)
              * [data-exclude](developer/howtos/website_themes/building_blocks.html#data-exclude)
              * [data-drop-in](developer/howtos/website_themes/building_blocks.html#data-drop-in)
              * [data-drop-near](developer/howtos/website_themes/building_blocks.html#data-drop-near)
              * [data-js](developer/howtos/website_themes/building_blocks.html#data-js)
            * Layout & fields
              * [`<we-title>`](developer/howtos/website_themes/building_blocks.html#we-title)
              * [`<we-row>`](developer/howtos/website_themes/building_blocks.html#we-row)
              * [`<we-button>`](developer/howtos/website_themes/building_blocks.html#we-button)
              * [`<we-select>`](developer/howtos/website_themes/building_blocks.html#we-select)
              * [`<we-button-group>`](developer/howtos/website_themes/building_blocks.html#we-button-group)
              * [`<we-checkbox>`](developer/howtos/website_themes/building_blocks.html#we-checkbox)
              * [`<we-range>`](developer/howtos/website_themes/building_blocks.html#we-range)
              * [`<we-input>`](developer/howtos/website_themes/building_blocks.html#we-input)
              * [`<we-colorpicker>`](developer/howtos/website_themes/building_blocks.html#we-colorpicker)
            * Methods
              * Built-in methods
                * [Selection](developer/howtos/website_themes/building_blocks.html#selection)
                * [Events](developer/howtos/website_themes/building_blocks.html#events)
              * [Custom methods](developer/howtos/website_themes/building_blocks.html#custom-methods)
          * Dynamic Content templates
            * [Call the template](developer/howtos/website_themes/building_blocks.html#call-the-template)
            * [Examples](developer/howtos/website_themes/building_blocks.html#examples)
      * Shapes
        * Background shapes
          * Standard
            * Colors mapping
              * [Switch colors mapping](developer/howtos/website_themes/shapes.html#switch-colors-mapping)
              * [Add extra colors mapping](developer/howtos/website_themes/shapes.html#add-extra-colors-mapping)
          * Custom
            * [Attachment](developer/howtos/website_themes/shapes.html#attachment)
            * [SCSS](developer/howtos/website_themes/shapes.html#scss)
            * [Add the option](developer/howtos/website_themes/shapes.html#add-the-option)
            * [Use it into your pages](developer/howtos/website_themes/shapes.html#use-it-into-your-pages)
      * Gradients
        * [Standard](developer/howtos/website_themes/gradients.html#standard)
        * [Custom](developer/howtos/website_themes/gradients.html#custom)
      * Animations
        * [On appearance](developer/howtos/website_themes/animations.html#on-appearance)
        * [On scroll](developer/howtos/website_themes/animations.html#on-scroll)
        * [On hover](developer/howtos/website_themes/animations.html#on-hover)
      * Forms
        * [Default form](developer/howtos/website_themes/forms.html#default-form)
        * [Actions](developer/howtos/website_themes/forms.html#actions)
        * [Success](developer/howtos/website_themes/forms.html#success)
      * Translations
        * Frontend
          * [Default pages](developer/howtos/website_themes/translations.html#default-pages)
          * Translatable strings
            * [t-att- / t-attf-](developer/howtos/website_themes/translations.html#t-att-t-attf)
            * [Exception: t-value / t-valuef](developer/howtos/website_themes/translations.html#exception-t-value-t-valuef)
            * [Mixing translatable and non-translatable](developer/howtos/website_themes/translations.html#mixing-translatable-and-non-translatable)
        * [Backend](developer/howtos/website_themes/translations.html#backend)
        * [Export](developer/howtos/website_themes/translations.html#export)
        * [PO file](developer/howtos/website_themes/translations.html#po-file)
        * [Import](developer/howtos/website_themes/translations.html#import)
      * Going live
        * Module import
          * [Odoo SaaS](developer/howtos/website_themes/going_live.html#odoo-saas)
          * [Odoo.sh](developer/howtos/website_themes/going_live.html#odoo-sh)
        * [What’s next?](developer/howtos/website_themes/going_live.html#what-s-next)
    * Web Services
      * [XML-RPC Library](developer/howtos/web_services.html#xml-rpc-library)
      * [JSON-RPC Library](developer/howtos/web_services.html#json-rpc-library)
    * Multi-company Guidelines
      * [Company-dependent fields](developer/howtos/company.html#company-dependent-fields)
      * [Multi-company consistency](developer/howtos/company.html#multi-company-consistency)
      * [Default company](developer/howtos/company.html#default-company)
      * [Views](developer/howtos/company.html#views)
      * [Security rules](developer/howtos/company.html#security-rules)
    * Create customized reports
      * [Create a model](developer/howtos/create_reports.html#create-a-model)
      * [Populate the model](developer/howtos/create_reports.html#populate-the-model)
      * [Use the model](developer/howtos/create_reports.html#use-the-model)
      * [Extra tips](developer/howtos/create_reports.html#extra-tips)
    * Accounting localization
      * [Installation procedure](developer/howtos/accounting_localization.html#installation-procedure)
      * [Building a localization module](developer/howtos/accounting_localization.html#building-a-localization-module)
      * Chart of Accounts
        * [Account tags](developer/howtos/accounting_localization.html#account-tags)
        * [Accounts](developer/howtos/accounting_localization.html#accounts)
        * [Account groups](developer/howtos/accounting_localization.html#account-groups)
        * [Taxes](developer/howtos/accounting_localization.html#taxes)
        * [Tax Report](developer/howtos/accounting_localization.html#tax-report)
        * [Fiscal positions](developer/howtos/accounting_localization.html#fiscal-positions)
      * [Final steps](developer/howtos/accounting_localization.html#final-steps)
      * [Accounting reports](developer/howtos/accounting_localization.html#accounting-reports)
    * Translating Modules
      * [Exporting translatable term](developer/howtos/translations.html#exporting-translatable-term)
      * [Implicit exports](developer/howtos/translations.html#implicit-exports)
      * Explicit exports
        * [Context](developer/howtos/translations.html#context)
        * [Variables](developer/howtos/translations.html#variables)
        * [Blocks](developer/howtos/translations.html#blocks)
        * [Plural](developer/howtos/translations.html#plural)
        * [Read vs Run Time](developer/howtos/translations.html#read-vs-run-time)
    * Connect with a device
      * Detect Devices
        * [Interface](developer/howtos/connect_device.html#interface)
        * [Driver](developer/howtos/connect_device.html#driver)
      * Communicate With Devices
        * [Actions](developer/howtos/connect_device.html#actions)
        * [Longpolling](developer/howtos/connect_device.html#longpolling)
    * Upgrade a customized database
      * [Step 1: Stop the developments](developer/howtos/upgrade_custom_db.html#step-1-stop-the-developments)
      * [Step 2: Request an upgraded database](developer/howtos/upgrade_custom_db.html#step-2-request-an-upgraded-database)
      * Step 3: Empty database
        * [Make custom modules installable](developer/howtos/upgrade_custom_db.html#make-custom-modules-installable)
        * [Test and fixes](developer/howtos/upgrade_custom_db.html#test-and-fixes)
        * [Clean the code](developer/howtos/upgrade_custom_db.html#clean-the-code)
        * [Standard tests](developer/howtos/upgrade_custom_db.html#standard-tests)
      * Step 4: Upgraded database
        * Migrate the data
          * [Running and testing upgrade scripts](developer/howtos/upgrade_custom_db.html#running-and-testing-upgrade-scripts)
        * [Test the custom modules](developer/howtos/upgrade_custom_db.html#test-the-custom-modules)
      * [Step 5: Testing and rehearsal](developer/howtos/upgrade_custom_db.html#step-5-testing-and-rehearsal)
      * [Step 6: Production upgrade](developer/howtos/upgrade_custom_db.html#step-6-production-upgrade)
    * [Frontend development](developer/howtos.html#frontend-development)
    * [Server-side development](developer/howtos.html#server-side-development)
    * [Custom development](developer/howtos.html#custom-development)
  * [Reference](developer/reference.html)
    * Server framework
      * [ORM API](developer/reference/backend/orm.html)
        * Changelog
          * [Odoo version 18.0](developer/reference/backend/orm/changelog.html#odoo-version-18-0)
          * [Odoo Online version 17.4](developer/reference/backend/orm/changelog.html#odoo-online-version-17-4)
          * [Odoo Online version 17.3](developer/reference/backend/orm/changelog.html#odoo-online-version-17-3)
          * [Odoo Online version 17.2](developer/reference/backend/orm/changelog.html#odoo-online-version-17-2)
          * [Odoo Online version 17.1](developer/reference/backend/orm/changelog.html#odoo-online-version-17-1)
          * [Odoo version 17.0](developer/reference/backend/orm/changelog.html#odoo-version-17-0)
          * [Odoo Online version 16.4](developer/reference/backend/orm/changelog.html#odoo-online-version-16-4)
          * [Odoo Online version 16.3](developer/reference/backend/orm/changelog.html#odoo-online-version-16-3)
          * [Odoo Online version 16.2](developer/reference/backend/orm/changelog.html#odoo-online-version-16-2)
          * [Odoo version 16.0](developer/reference/backend/orm/changelog.html#odoo-version-16-0)
          * [Odoo Online version 15.4](developer/reference/backend/orm/changelog.html#odoo-online-version-15-4)
          * [Odoo Online version 15.3](developer/reference/backend/orm/changelog.html#odoo-online-version-15-3)
          * [Odoo Online version 15.2](developer/reference/backend/orm/changelog.html#odoo-online-version-15-2)
        * Models
          * [AbstractModel](developer/reference/backend/orm.html#abstractmodel)
          * [Model](developer/reference/backend/orm.html#model)
          * [TransientModel](developer/reference/backend/orm.html#transientmodel)
        * Fields
          * [Basic Fields](developer/reference/backend/orm.html#basic-fields)
          * Advanced Fields
            * [Date(time) Fields](developer/reference/backend/orm.html#date-time-fields)
            * [Relational Fields](developer/reference/backend/orm.html#relational-fields)
            * [Pseudo-relational fields](developer/reference/backend/orm.html#pseudo-relational-fields)
            * [Computed Fields](developer/reference/backend/orm.html#computed-fields)
            * [Related fields](developer/reference/backend/orm.html#related-fields)
          * Automatic fields
            * [Access Log fields](developer/reference/backend/orm.html#access-log-fields)
          * [Reserved Field names](developer/reference/backend/orm.html#reserved-field-names)
        * Recordsets
          * [Field access](developer/reference/backend/orm.html#field-access)
          * [Record cache and prefetching](developer/reference/backend/orm.html#record-cache-and-prefetching)
        * [Method decorators](developer/reference/backend/orm.html#module-odoo.api)
        * Environment
          * [Useful environment methods](developer/reference/backend/orm.html#useful-environment-methods)
          * [Altering the environment](developer/reference/backend/orm.html#altering-the-environment)
          * [SQL Execution](developer/reference/backend/orm.html#sql-execution)
        * Common ORM methods
          * [Create/update](developer/reference/backend/orm.html#create-update)
          * Search/Read
            * [Fields](developer/reference/backend/orm.html#id7)
            * [Search domains](developer/reference/backend/orm.html#search-domains)
          * [Unlink](developer/reference/backend/orm.html#unlink)
          * [Record(set) information](developer/reference/backend/orm.html#record-set-information)
          * Operations
            * [Filter](developer/reference/backend/orm.html#filter)
            * [Map](developer/reference/backend/orm.html#map)
            * [Sort](developer/reference/backend/orm.html#sort)
            * [Grouping](developer/reference/backend/orm.html#grouping)
        * Inheritance and extension
          * [Classical inheritance](developer/reference/backend/orm.html#classical-inheritance)
          * [Extension](developer/reference/backend/orm.html#extension)
          * [Delegation](developer/reference/backend/orm.html#delegation)
          * [Fields Incremental Definition](developer/reference/backend/orm.html#fields-incremental-definition)
        * [Error management](developer/reference/backend/orm.html#module-odoo.exceptions)
      * Data Files
        * [Structure](developer/reference/backend/data.html#structure)
        * Core operations
          * [`record`](developer/reference/backend/data.html#record)
          * [`field`](developer/reference/backend/data.html#field)
          * [`delete`](developer/reference/backend/data.html#delete)
          * [`function`](developer/reference/backend/data.html#function)
        * Shortcuts
          * [`menuitem`](developer/reference/backend/data.html#menuitem)
          * [`template`](developer/reference/backend/data.html#template)
        * [CSV data files](developer/reference/backend/data.html#csv-data-files)
      * Actions
        * [Bindings](developer/reference/backend/actions.html#bindings)
        * [Window Actions (`ir.actions.act_window`)](developer/reference/backend/actions.html#window-actions-ir-actions-act-window)
        * [URL Actions (`ir.actions.act_url`)](developer/reference/backend/actions.html#url-actions-ir-actions-act-url)
        * Server Actions (`ir.actions.server`)
          * [State fields](developer/reference/backend/actions.html#state-fields)
          * [Evaluation context](developer/reference/backend/actions.html#evaluation-context)
        * [Report Actions (`ir.actions.report`)](developer/reference/backend/actions.html#report-actions-ir-actions-report)
        * [Client Actions (`ir.actions.client`)](developer/reference/backend/actions.html#client-actions-ir-actions-client)
        * Scheduled Actions (`ir.cron`)
          * [Advanced use: Batching](developer/reference/backend/actions.html#advanced-use-batching)
          * [Advanced use: Triggers](developer/reference/backend/actions.html#advanced-use-triggers)
          * [Security](developer/reference/backend/actions.html#security)
      * QWeb Reports
        * Report template
          * [Minimal viable template](developer/reference/backend/reports.html#minimal-viable-template)
          * [Translatable Templates](developer/reference/backend/reports.html#translatable-templates)
          * [Barcodes](developer/reference/backend/reports.html#barcodes)
          * [Useful Remarks](developer/reference/backend/reports.html#useful-remarks)
        * [Paper Format](developer/reference/backend/reports.html#paper-format)
        * [Custom Reports](developer/reference/backend/reports.html#custom-reports)
        * [Custom fonts](developer/reference/backend/reports.html#custom-fonts)
        * [Reports are web pages](developer/reference/backend/reports.html#reports-are-web-pages)
      * Module Manifests
        * [Manifest](developer/reference/backend/module.html#manifest)
      * Security in Odoo
        * [Access Rights](developer/reference/backend/security.html#access-rights)
        * Record Rules
          * [Global rules versus group rules](developer/reference/backend/security.html#global-rules-versus-group-rules)
        * [Field Access](developer/reference/backend/security.html#field-access)
        * Security Pitfalls
          * [Unsafe Public Methods](developer/reference/backend/security.html#unsafe-public-methods)
          * Bypassing the ORM
            * [SQL injections](developer/reference/backend/security.html#sql-injections)
          * Unescaped field content
            * [Creating safe content using `Markup`](developer/reference/backend/security.html#creating-safe-content-using-markup)
          * [Escaping vs Sanitizing](developer/reference/backend/security.html#escaping-vs-sanitizing)
          * [Evaluating content](developer/reference/backend/security.html#evaluating-content)
          * [Accessing object attributes](developer/reference/backend/security.html#accessing-object-attributes)
      * Performance
        * Profiling
          * [Enable the profiler](developer/reference/backend/performance.html#enable-the-profiler)
          * [Analyse the results](developer/reference/backend/performance.html#analyse-the-results)
          * Collectors
            * [SQL collector](developer/reference/backend/performance.html#sql-collector)
            * [Periodic collector](developer/reference/backend/performance.html#periodic-collector)
            * [QWeb collector](developer/reference/backend/performance.html#qweb-collector)
            * [Sync collector](developer/reference/backend/performance.html#sync-collector)
          * [Performance pitfalls](developer/reference/backend/performance.html#performance-pitfalls)
        * Good practices
          * [Batch operations](developer/reference/backend/performance.html#batch-operations)
          * [Reduce the algorithmic complexity](developer/reference/backend/performance.html#reduce-the-algorithmic-complexity)
          * [Use indexes](developer/reference/backend/performance.html#use-indexes)
      * Testing Odoo
        * Testing Python code
          * [Running tests](developer/reference/backend/testing.html#running-tests)
          * Test selection
            * [Invocation](developer/reference/backend/testing.html#invocation)
            * [Special tags](developer/reference/backend/testing.html#special-tags)
            * [Examples](developer/reference/backend/testing.html#examples)
        * Testing JS code
          * [Qunit test suite](developer/reference/backend/testing.html#qunit-test-suite)
          * [Testing Infrastructure](developer/reference/backend/testing.html#testing-infrastructure)
          * [Modularity and testing](developer/reference/backend/testing.html#modularity-and-testing)
          * [Adding a new test case](developer/reference/backend/testing.html#adding-a-new-test-case)
          * [Helper functions and specialized assertions](developer/reference/backend/testing.html#helper-functions-and-specialized-assertions)
          * [Best Practices](developer/reference/backend/testing.html#best-practices)
          * [Tips](developer/reference/backend/testing.html#tips)
        * Integration Testing
          * Writing a test tour
            * [Structure](developer/reference/backend/testing.html#structure)
            * [Javascript](developer/reference/backend/testing.html#javascript)
            * [Python](developer/reference/backend/testing.html#python)
          * Writing an onboarding tour
            * [Structure](developer/reference/backend/testing.html#id1)
            * [Javascript](developer/reference/backend/testing.html#id2)
            * [XML](developer/reference/backend/testing.html#xml)
            * [Running onboarding tours](developer/reference/backend/testing.html#running-onboarding-tours)
            * [Tour recorder](developer/reference/backend/testing.html#tour-recorder)
          * Debugging tips
            * Observing test tours in a browser
              * [`watch=True`](developer/reference/backend/testing.html#watch-true)
              * [`debug=True`](developer/reference/backend/testing.html#debug-true)
              * [Run via browser](developer/reference/backend/testing.html#run-via-browser)
            * [Screenshots and screencasts during browser_js tests](developer/reference/backend/testing.html#screenshots-and-screencasts-during-browser-js-tests)
            * [Introspecting / debugging steps](developer/reference/backend/testing.html#introspecting-debugging-steps)
        * Performance Testing
          * [Query counts](developer/reference/backend/testing.html#query-counts)
      * Web Controllers
        * [Controllers](developer/reference/backend/http.html#controllers)
        * API
          * [Routing](developer/reference/backend/http.html#routing)
          * [Request](developer/reference/backend/http.html#request)
          * [Response](developer/reference/backend/http.html#response)
      * Mixins and Useful Classes
        * Messaging features
          * Messaging integration
            * [Basic messaging system](developer/reference/backend/mixins.html#basic-messaging-system)
            * [Logging changes](developer/reference/backend/mixins.html#logging-changes)
            * [Subtypes](developer/reference/backend/mixins.html#subtypes)
            * [Customizing notifications](developer/reference/backend/mixins.html#customizing-notifications)
            * [Overriding defaults](developer/reference/backend/mixins.html#overriding-defaults)
          * Mail alias
            * [Aliases vs. Incoming Mail Gateway](developer/reference/backend/mixins.html#aliases-vs-incoming-mail-gateway)
            * [Alias support integration](developer/reference/backend/mixins.html#alias-support-integration)
          * [Activities tracking](developer/reference/backend/mixins.html#activities-tracking)
        * Website features
          * [Visitor tracking](developer/reference/backend/mixins.html#visitor-tracking)
          * [Website visibility](developer/reference/backend/mixins.html#website-visibility)
          * [Website metadata](developer/reference/backend/mixins.html#website-metadata)
        * Others
          * Customer Rating
            * [Adding rating on your model](developer/reference/backend/mixins.html#adding-rating-on-your-model)
            * [Send rating requests by e-mail](developer/reference/backend/mixins.html#send-rating-requests-by-e-mail)
    * Web framework
      * Framework Overview
        * [Introduction](developer/reference/frontend/framework_overview.html#introduction)
        * [Code structure](developer/reference/frontend/framework_overview.html#code-structure)
        * [WebClient Architecture](developer/reference/frontend/framework_overview.html#webclient-architecture)
        * [Environment](developer/reference/frontend/framework_overview.html#environment)
        * Building Blocks
          * [Registries](developer/reference/frontend/framework_overview.html#registries)
          * [Services](developer/reference/frontend/framework_overview.html#services)
          * [Components and Hooks](developer/reference/frontend/framework_overview.html#components-and-hooks)
        * Context
          * [User Context](developer/reference/frontend/framework_overview.html#user-context)
          * [Action Context](developer/reference/frontend/framework_overview.html#action-context)
        * [Python Interpreter](developer/reference/frontend/framework_overview.html#python-interpreter)
        * [Domains](developer/reference/frontend/framework_overview.html#domains)
        * [Bus](developer/reference/frontend/framework_overview.html#bus)
        * [Browser Object](developer/reference/frontend/framework_overview.html#browser-object)
        * Debug mode
          * [Assets mode](developer/reference/frontend/framework_overview.html#assets-mode)
          * [Tests mode](developer/reference/frontend/framework_overview.html#tests-mode)
      * Assets
        * [Asset types](developer/reference/frontend/assets.html#asset-types)
        * Bundles
          * Operations
            * [`append`](developer/reference/frontend/assets.html#append)
            * [`prepend`](developer/reference/frontend/assets.html#prepend)
            * [`before`](developer/reference/frontend/assets.html#before)
            * [`after`](developer/reference/frontend/assets.html#after)
            * [`include`](developer/reference/frontend/assets.html#include)
            * [`remove`](developer/reference/frontend/assets.html#remove)
            * [`replace`](developer/reference/frontend/assets.html#replace)
          * [Loading order](developer/reference/frontend/assets.html#loading-order)
        * [Lazy loading](developer/reference/frontend/assets.html#lazy-loading)
        * [The asset model (`ir.asset`)](developer/reference/frontend/assets.html#the-asset-model-ir-asset)
      * Javascript Modules
        * [Plain Javascript files](developer/reference/frontend/javascript_modules.html#plain-javascript-files)
        * Native Javascript Modules
          * [Aliased modules](developer/reference/frontend/javascript_modules.html#aliased-modules)
          * [Limitations](developer/reference/frontend/javascript_modules.html#limitations)
        * Odoo Module System
          * [Defining a module](developer/reference/frontend/javascript_modules.html#defining-a-module)
      * Owl components
        * [Using Owl components](developer/reference/frontend/owl_components.html#using-owl-components)
        * [Best practices](developer/reference/frontend/owl_components.html#best-practices)
        * Reference List
          * ActionSwiper
            * [Location](developer/reference/frontend/owl_components.html#location)
            * [Description](developer/reference/frontend/owl_components.html#description)
            * [Props](developer/reference/frontend/owl_components.html#props)
            * [Example: Extending existing components](developer/reference/frontend/owl_components.html#example-extending-existing-components)
          * CheckBox
            * [Location](developer/reference/frontend/owl_components.html#id1)
            * [Description](developer/reference/frontend/owl_components.html#id2)
            * [Props](developer/reference/frontend/owl_components.html#id3)
          * ColorList
            * [Location](developer/reference/frontend/owl_components.html#id4)
            * [Description](developer/reference/frontend/owl_components.html#id5)
            * [Props](developer/reference/frontend/owl_components.html#id6)
          * Dropdown
            * [Location](developer/reference/frontend/owl_components.html#id7)
            * [Description](developer/reference/frontend/owl_components.html#id8)
            * [Dropdown Props](developer/reference/frontend/owl_components.html#dropdown-props)
            * [DropdownItem Props](developer/reference/frontend/owl_components.html#dropdownitem-props)
            * [Nested Dropdown](developer/reference/frontend/owl_components.html#nested-dropdown)
            * [Controlled Dropdown](developer/reference/frontend/owl_components.html#controlled-dropdown)
            * [DropdownGroup](developer/reference/frontend/owl_components.html#dropdowngroup)
          * Notebook
            * [Location](developer/reference/frontend/owl_components.html#id9)
            * [Description](developer/reference/frontend/owl_components.html#id10)
            * [Props](developer/reference/frontend/owl_components.html#id11)
          * Pager
            * [Location](developer/reference/frontend/owl_components.html#id12)
            * [Description](developer/reference/frontend/owl_components.html#id13)
            * [Props](developer/reference/frontend/owl_components.html#id14)
          * SelectMenu
            * [Location](developer/reference/frontend/owl_components.html#id15)
            * [Description](developer/reference/frontend/owl_components.html#id16)
            * [Props](developer/reference/frontend/owl_components.html#id17)
          * TagsList
            * [Location](developer/reference/frontend/owl_components.html#id18)
            * [Description](developer/reference/frontend/owl_components.html#id19)
            * [Props](developer/reference/frontend/owl_components.html#id20)
      * Registries
        * [Registry API](developer/reference/frontend/registries.html#registry-api)
        * Reference List
          * [Effect registry](developer/reference/frontend/registries.html#effect-registry)
          * [Formatter registry](developer/reference/frontend/registries.html#formatter-registry)
          * [Main components registry](developer/reference/frontend/registries.html#main-components-registry)
          * [Parser registry](developer/reference/frontend/registries.html#parser-registry)
          * [Service registry](developer/reference/frontend/registries.html#service-registry)
          * [Systray registry](developer/reference/frontend/registries.html#systray-registry)
          * [Usermenu registry](developer/reference/frontend/registries.html#usermenu-registry)
      * Services
        * [Defining a service](developer/reference/frontend/services.html#defining-a-service)
        * [Using a service](developer/reference/frontend/services.html#using-a-service)
        * Reference List
          * Cookie service
            * [Overview](developer/reference/frontend/services.html#overview)
            * [API](developer/reference/frontend/services.html#api)
          * Effect service
            * [Overview](developer/reference/frontend/services.html#id1)
            * [API](developer/reference/frontend/services.html#id2)
            * Available effects
              * [RainbowMan](developer/reference/frontend/services.html#rainbowman)
            * [How to add an effect](developer/reference/frontend/services.html#how-to-add-an-effect)
            * [Example](developer/reference/frontend/services.html#example)
          * Http Service
            * [Overview](developer/reference/frontend/services.html#id3)
            * [API](developer/reference/frontend/services.html#id4)
            * [Example](developer/reference/frontend/services.html#id5)
          * Notification service
            * [Overview](developer/reference/frontend/services.html#id6)
            * [API](developer/reference/frontend/services.html#id7)
            * [Examples](developer/reference/frontend/services.html#examples)
          * Router Service
            * [Overview](developer/reference/frontend/services.html#id8)
            * [API](developer/reference/frontend/services.html#id9)
          * RPC service
            * [Overview](developer/reference/frontend/services.html#id10)
            * [API](developer/reference/frontend/services.html#id11)
            * [Error Handling](developer/reference/frontend/services.html#error-handling)
          * Scroller service
            * [Overview](developer/reference/frontend/services.html#id12)
            * [API](developer/reference/frontend/services.html#id13)
          * Title Service
            * [Overview](developer/reference/frontend/services.html#id14)
            * [API](developer/reference/frontend/services.html#id15)
          * User service
            * [Overview](developer/reference/frontend/services.html#id16)
            * [API](developer/reference/frontend/services.html#id17)
      * Hooks
        * useAssets
          * [Location](developer/reference/frontend/hooks.html#location)
          * [Description](developer/reference/frontend/hooks.html#description)
        * useAutofocus
          * [Location](developer/reference/frontend/hooks.html#id1)
          * [Description](developer/reference/frontend/hooks.html#id2)
          * [API](developer/reference/frontend/hooks.html#api)
        * useBus
          * [Location](developer/reference/frontend/hooks.html#id3)
          * [Description](developer/reference/frontend/hooks.html#id4)
          * [API](developer/reference/frontend/hooks.html#id5)
        * usePager
          * [Location](developer/reference/frontend/hooks.html#id6)
          * [Description](developer/reference/frontend/hooks.html#id7)
          * [API](developer/reference/frontend/hooks.html#id8)
        * usePosition
          * [Location](developer/reference/frontend/hooks.html#id9)
          * [Description](developer/reference/frontend/hooks.html#id10)
          * [API](developer/reference/frontend/hooks.html#id11)
        * useSpellCheck
          * [Location](developer/reference/frontend/hooks.html#id12)
          * [Description](developer/reference/frontend/hooks.html#id13)
          * [API](developer/reference/frontend/hooks.html#id14)
      * Patching code
        * [Description](developer/reference/frontend/patching_code.html#description)
        * [Patching a simple object](developer/reference/frontend/patching_code.html#patching-a-simple-object)
        * [Patching a javascript class](developer/reference/frontend/patching_code.html#patching-a-javascript-class)
        * [Patching a component](developer/reference/frontend/patching_code.html#patching-a-component)
        * [Removing a patch](developer/reference/frontend/patching_code.html#removing-a-patch)
        * [Applying the same patch to multiple objects](developer/reference/frontend/patching_code.html#applying-the-same-patch-to-multiple-objects)
      * Error handling
        * Errors in JavaScript
          * [The `Error` class](developer/reference/frontend/error_handling.html#the-error-class)
          * [Anything can be thrown](developer/reference/frontend/error_handling.html#anything-can-be-thrown)
          * [Promise rejections are errors](developer/reference/frontend/error_handling.html#promise-rejections-are-errors)
          * [`error` events are not errors](developer/reference/frontend/error_handling.html#error-events-are-not-errors)
        * Lifecycle of errors within the Odoo JS framework
          * [Throwing an error at the top-level of a module](developer/reference/frontend/error_handling.html#throwing-an-error-at-the-top-level-of-a-module)
          * [The error service](developer/reference/frontend/error_handling.html#the-error-service)
          * [The `error_handlers` registry](developer/reference/frontend/error_handling.html#the-error-handlers-registry)
          * [Throwing an error in an Owl component](developer/reference/frontend/error_handling.html#throwing-an-error-in-an-owl-component)
          * Marking errors as handled
            * [`onError`](developer/reference/frontend/error_handling.html#onerror)
            * [Handler in the `error_handlers` registry](developer/reference/frontend/error_handling.html#handler-in-the-error-handlers-registry)
        * Avoid throwing errors as much as possible
          * [Errors are expensive](developer/reference/frontend/error_handling.html#errors-are-expensive)
          * [Throwing errors makes debugging harder](developer/reference/frontend/error_handling.html#throwing-errors-makes-debugging-harder)
          * [Throwing breaks the normal flow of the code](developer/reference/frontend/error_handling.html#throwing-breaks-the-normal-flow-of-the-code)
        * [Catching errors](developer/reference/frontend/error_handling.html#catching-errors)
        * Error free control flow
          * [Return `null` or `undefined`](developer/reference/frontend/error_handling.html#return-null-or-undefined)
          * [Return an object or array](developer/reference/frontend/error_handling.html#return-an-object-or-array)
        * [When to throw errors](developer/reference/frontend/error_handling.html#when-to-throw-errors)
      * Javascript Reference
        * [Overview](developer/reference/frontend/javascript_reference.html#overview)
        * Web client
          * [Single Page Application](developer/reference/frontend/javascript_reference.html#single-page-application)
          * [Overview of web client JS code](developer/reference/frontend/javascript_reference.html#overview-of-web-client-js-code)
          * [What to do if a file is not loaded/updated](developer/reference/frontend/javascript_reference.html#what-to-do-if-a-file-is-not-loaded-updated)
        * Loading Javascript Code
          * [Patching classes](developer/reference/frontend/javascript_reference.html#patching-classes)
        * [Registries](developer/reference/frontend/javascript_reference.html#registries)
        * Services
          * [Using services](developer/reference/frontend/javascript_reference.html#using-services)
          * [Talking to the server](developer/reference/frontend/javascript_reference.html#talking-to-the-server)
        * Notifications
          * [Displaying notifications](developer/reference/frontend/javascript_reference.html#displaying-notifications)
        * Systray
          * [Adding a new Systray Item](developer/reference/frontend/javascript_reference.html#adding-a-new-systray-item)
        * [Translation management](developer/reference/frontend/javascript_reference.html#translation-management)
        * Session
          * [Adding information to the session](developer/reference/frontend/javascript_reference.html#adding-information-to-the-session)
        * [Views](developer/reference/frontend/javascript_reference.html#views)
        * Fields
          * [Decorations](developer/reference/frontend/javascript_reference.html#decorations)
          * [Non-relational fields](developer/reference/frontend/javascript_reference.html#non-relational-fields)
          * [Relational fields](developer/reference/frontend/javascript_reference.html#relational-fields)
          * [Widgets](developer/reference/frontend/javascript_reference.html#widgets)
        * Client actions
          * [Adding a client action](developer/reference/frontend/javascript_reference.html#adding-a-client-action)
      * Mobile JavaScript
        * [Introduction](developer/reference/frontend/mobile.html#introduction)
        * [How does it work?](developer/reference/frontend/mobile.html#how-does-it-work)
        * How to use it?
          * Methods
            * [Show Toast in device](developer/reference/frontend/mobile.html#show-toast-in-device)
            * [Vibrating device](developer/reference/frontend/mobile.html#vibrating-device)
            * [Show snackbar with action](developer/reference/frontend/mobile.html#show-snackbar-with-action)
            * [Showing notification](developer/reference/frontend/mobile.html#showing-notification)
            * [Create contact in device](developer/reference/frontend/mobile.html#create-contact-in-device)
            * [Scanning barcodes](developer/reference/frontend/mobile.html#scanning-barcodes)
            * [Switching account in device](developer/reference/frontend/mobile.html#switching-account-in-device)
      * QWeb Templates
        * [Data output](developer/reference/frontend/qweb.html#data-output)
        * [Conditionals](developer/reference/frontend/qweb.html#conditionals)
        * [Loops](developer/reference/frontend/qweb.html#loops)
        * [attributes](developer/reference/frontend/qweb.html#attributes)
        * [setting variables](developer/reference/frontend/qweb.html#setting-variables)
        * [calling sub-templates](developer/reference/frontend/qweb.html#calling-sub-templates)
        * Advanced Output
          * [Python](developer/reference/frontend/qweb.html#python)
          * [forcing double-escaping](developer/reference/frontend/qweb.html#forcing-double-escaping)
          * [Deprecated output directives](developer/reference/frontend/qweb.html#deprecated-output-directives)
        * Python
          * Exclusive directives
            * [Asset bundles](developer/reference/frontend/qweb.html#asset-bundles)
            * [«smart records» fields formatting](developer/reference/frontend/qweb.html#smart-records-fields-formatting)
          * [Debugging](developer/reference/frontend/qweb.html#debugging)
          * Rendering cache:
            * [Why and when to use `t-cache`?](developer/reference/frontend/qweb.html#why-and-when-to-use-t-cache)
            * [What if there is a `t-cache` inside a `t-cache`?](developer/reference/frontend/qweb.html#what-if-there-is-a-t-cache-inside-a-t-cache)
            * [What is `t-nocache` used for?](developer/reference/frontend/qweb.html#what-is-t-nocache-used-for)
            * [The base of `t-cache`](developer/reference/frontend/qweb.html#the-base-of-t-cache)
            * [`t-cache` and scoped values (`t-set`, `t-foreach`…)](developer/reference/frontend/qweb.html#t-cache-and-scoped-values-t-set-t-foreach)
            * [The base of `t-nocache`](developer/reference/frontend/qweb.html#the-base-of-t-nocache)
            * [`t-nocache` and scoped root values (`t-set`, `t-foreach`…)](developer/reference/frontend/qweb.html#t-nocache-and-scoped-root-values-t-set-t-foreach)
            * [`t-nocache-*` add some primitive values in the cache](developer/reference/frontend/qweb.html#t-nocache-add-some-primitive-values-in-the-cache)
          * Helpers
            * [Request-based](developer/reference/frontend/qweb.html#request-based)
            * [View-based](developer/reference/frontend/qweb.html#view-based)
        * Javascript
          * Exclusive directives
            * [Defining templates](developer/reference/frontend/qweb.html#defining-templates)
            * [Template inheritance](developer/reference/frontend/qweb.html#template-inheritance)
            * [Old inheritance mechanism (deprecated)](developer/reference/frontend/qweb.html#old-inheritance-mechanism-deprecated)
          * [debugging](developer/reference/frontend/qweb.html#id7)
          * [Helpers](developer/reference/frontend/qweb.html#id8)
          * [API](developer/reference/frontend/qweb.html#api)
      * Odoo Editor
        * Powerbox
          * [Modifying the Powerbox](developer/reference/frontend/odoo_editor.html#modifying-the-powerbox)
          * [Opening a custom Powerbox](developer/reference/frontend/odoo_editor.html#opening-a-custom-powerbox)
          * [Filtering commands](developer/reference/frontend/odoo_editor.html#filtering-commands)
          * Reference
            * [Category](developer/reference/frontend/odoo_editor.html#category)
            * [Command](developer/reference/frontend/odoo_editor.html#command)
            * [Options](developer/reference/frontend/odoo_editor.html#options)
    * User interface
      * View records
        * [Generic structure](developer/reference/user_interface/view_records.html#generic-structure)
        * [View types](developer/reference/user_interface/view_records.html#view-types)
        * [Fields](developer/reference/user_interface/view_records.html#fields)
        * Inheritance
          * [View resolution](developer/reference/user_interface/view_records.html#view-resolution)
          * [Inheritance specs](developer/reference/user_interface/view_records.html#inheritance-specs)
          * [Inheritance position](developer/reference/user_interface/view_records.html#inheritance-position)
        * [Model commons](developer/reference/user_interface/view_records.html#model-commons)
      * View architectures
        * [Generic architecture](developer/reference/user_interface/view_architectures.html#generic-architecture)
        * [Python expression](developer/reference/user_interface/view_architectures.html#python-expression)
        * Form
          * [Root attributes](developer/reference/user_interface/view_architectures.html#root-attributes)
          * Semantic components
            * [`field`: display field values](developer/reference/user_interface/view_architectures.html#field-display-field-values)
            * [`label`: display field labels](developer/reference/user_interface/view_architectures.html#label-display-field-labels)
            * [`button`: display action buttons](developer/reference/user_interface/view_architectures.html#button-display-action-buttons)
            * [Chatter widget](developer/reference/user_interface/view_architectures.html#chatter-widget)
            * [Attachments preview widget](developer/reference/user_interface/view_architectures.html#attachments-preview-widget)
          * Structural components
            * [`group`: define columns layouts](developer/reference/user_interface/view_architectures.html#group-define-columns-layouts)
            * [`sheet`: make the layout responsive](developer/reference/user_interface/view_architectures.html#sheet-make-the-layout-responsive)
            * [`notebook` & `page`: add tabbed sections](developer/reference/user_interface/view_architectures.html#notebook-page-add-tabbed-sections)
            * [`newline`: start new group rows](developer/reference/user_interface/view_architectures.html#newline-start-new-group-rows)
            * [`separator`: add horizontal spacing](developer/reference/user_interface/view_architectures.html#separator-add-horizontal-spacing)
            * [`header`: display workflow buttons and a status](developer/reference/user_interface/view_architectures.html#header-display-workflow-buttons-and-a-status)
            * [`footer`: display dialog buttons](developer/reference/user_interface/view_architectures.html#footer-display-dialog-buttons)
            * [Buttons container](developer/reference/user_interface/view_architectures.html#buttons-container)
            * [Title container](developer/reference/user_interface/view_architectures.html#title-container)
        * Settings
          * Components
            * [`app`: declare the application](developer/reference/user_interface/view_architectures.html#app-declare-the-application)
            * [`block`: declare a group of settings](developer/reference/user_interface/view_architectures.html#block-declare-a-group-of-settings)
            * [`setting`: declare the setting](developer/reference/user_interface/view_architectures.html#setting-declare-the-setting)
        * List
          * [Root attributes](developer/reference/user_interface/view_architectures.html#reference-view-architectures-list-root)
          * Components
            * [`field`: display field values](developer/reference/user_interface/view_architectures.html#reference-view-architectures-list-field)
            * [`button`: display action buttons](developer/reference/user_interface/view_architectures.html#reference-view-architectures-list-button)
            * [`groupby`: define group headers](developer/reference/user_interface/view_architectures.html#groupby-define-group-headers)
            * [`header`: display workflow buttons](developer/reference/user_interface/view_architectures.html#header-display-workflow-buttons)
            * [`control` & `create`: add inline create buttons](developer/reference/user_interface/view_architectures.html#control-create-add-inline-create-buttons)
        * Search
          * Components
            * [`field`: filter based on field values](developer/reference/user_interface/view_architectures.html#field-filter-based-on-field-values)
            * [`filter`: create pre-defined filters](developer/reference/user_interface/view_architectures.html#filter-create-pre-defined-filters)
            * [`separator`: separate groups of filters](developer/reference/user_interface/view_architectures.html#separator-separate-groups-of-filters)
            * [`group`: separate groups of filters](developer/reference/user_interface/view_architectures.html#group-separate-groups-of-filters)
            * [`searchpanel`: display search panels](developer/reference/user_interface/view_architectures.html#searchpanel-display-search-panels)
          * [Search defaults](developer/reference/user_interface/view_architectures.html#search-defaults)
        * Kanban
          * [Root attributes](developer/reference/user_interface/view_architectures.html#reference-view-architectures-kanban-root)
          * Components
            * `templates`: define cards structure
              * [Fields](developer/reference/user_interface/view_architectures.html#fields)
              * [Rendering Context](developer/reference/user_interface/view_architectures.html#rendering-context)
              * [Buttons and links](developer/reference/user_interface/view_architectures.html#buttons-and-links)
              * [Widgets](developer/reference/user_interface/view_architectures.html#widgets)
              * [Layouts](developer/reference/user_interface/view_architectures.html#layouts)
            * [`field`: declare more fields to fetch](developer/reference/user_interface/view_architectures.html#field-declare-more-fields-to-fetch)
            * [`header`: display buttons in the control panel](developer/reference/user_interface/view_architectures.html#header-display-buttons-in-the-control-panel)
            * [`progressbar`: show progress bars on top of columns](developer/reference/user_interface/view_architectures.html#progressbar-show-progress-bars-on-top-of-columns)
        * [QWeb](developer/reference/user_interface/view_architectures.html#qweb)
        * [Graph](developer/reference/user_interface/view_architectures.html#graph)
        * [Pivot](developer/reference/user_interface/view_architectures.html#pivot)
        * Calendar
          * [Model Commons](developer/reference/user_interface/view_architectures.html#model-commons)
        * [Activity](developer/reference/user_interface/view_architectures.html#activity)
        * [Cohort](developer/reference/user_interface/view_architectures.html#cohort)
        * Grid
          * [Limitations](developer/reference/user_interface/view_architectures.html#limitations)
          * [Schema](developer/reference/user_interface/view_architectures.html#schema)
          * [Server interactions](developer/reference/user_interface/view_architectures.html#server-interactions)
          * [Server Hooks](developer/reference/user_interface/view_architectures.html#server-hooks)
          * [ACL](developer/reference/user_interface/view_architectures.html#acl)
          * [Context Keys](developer/reference/user_interface/view_architectures.html#context-keys)
        * [Gantt](developer/reference/user_interface/view_architectures.html#gantt)
        * Map
          * [API](developer/reference/user_interface/view_architectures.html#api)
          * [Structural components](developer/reference/user_interface/view_architectures.html#id20)
      * SCSS inheritance
        * [Overview](developer/reference/user_interface/scss_inheritance.html#overview)
        * [SCSS’s `!default` directive](developer/reference/user_interface/scss_inheritance.html#scss-s-default-directive)
        * [Odoo’s SCSS inheritance system](developer/reference/user_interface/scss_inheritance.html#odoo-s-scss-inheritance-system)
      * UI icons
        * [Icons](developer/reference/user_interface/icons.html#icons)
        * [RTL adaptations](developer/reference/user_interface/icons.html#rtl-adaptations)
    * Standard modules
      * Accounting
        * Account Tag
          * [Original definition from `account`](developer/reference/standard_modules/account/account_account_tag.html#original-definition-from-account)
        * Account
          * [Original definition from `account`](developer/reference/standard_modules/account/account_account.html#original-definition-from-account)
        * Fiscal Position
          * [Original definition from `account`](developer/reference/standard_modules/account/account_fiscal_position.html#original-definition-from-account)
        * Account Group
          * [Original definition from `account`](developer/reference/standard_modules/account/account_group.html#original-definition-from-account)
        * Report
          * [Original definition from `account`](developer/reference/standard_modules/account/account_report.html#original-definition-from-account)
        * Report Line
          * [Original definition from `account`](developer/reference/standard_modules/account/account_report_line.html#original-definition-from-account)
        * Taxes
          * [Original definition from `account`](developer/reference/standard_modules/account/account_tax.html#original-definition-from-account)
        * Tax Repartitions
          * [Original definition from `account`](developer/reference/standard_modules/account/account_tax_repartition.html#original-definition-from-account)
      * Payment
        * [Payment Method](developer/reference/standard_modules/payment/payment_method.html)
        * [Payment Provider](developer/reference/standard_modules/payment/payment_provider.html)
        * [Payment Token](developer/reference/standard_modules/payment/payment_token.html)
        * [Payment Transaction](developer/reference/standard_modules/payment/payment_transaction.html)
    * Command-line interface (CLI)
      * [Help & version](developer/reference/cli.html#help-version)
      * [Running the server](developer/reference/cli.html#running-the-server)
      * Testing Configuration
        * [Database](developer/reference/cli.html#database)
        * [Emails](developer/reference/cli.html#emails)
        * [Internationalisation](developer/reference/cli.html#internationalisation)
        * Advanced Options
          * [Developer features](developer/reference/cli.html#developer-features)
          * [HTTP](developer/reference/cli.html#http)
          * [Logging](developer/reference/cli.html#logging)
          * [Multiprocessing](developer/reference/cli.html#multiprocessing)
      * [Configuration file](developer/reference/cli.html#configuration-file)
      * [Shell](developer/reference/cli.html#shell)
      * [Neutralize](developer/reference/cli.html#neutralize)
      * [Scaffolding](developer/reference/cli.html#scaffolding)
      * [Database population](developer/reference/cli.html#database-population)
      * Cloc
        * [Command-line options](developer/reference/cli.html#command-line-options)
        * Processed files
          * [With the `--database` option](developer/reference/cli.html#with-the-database-option)
          * [With the `--path` option](developer/reference/cli.html#with-the-path-option)
        * [Identifying Extra Modules](developer/reference/cli.html#identifying-extra-modules)
        * Error Handling
          * [Max file size exceeded](developer/reference/cli.html#max-file-size-exceeded)
          * [Syntax Error](developer/reference/cli.html#syntax-error)
      * [TSConfig Generator](developer/reference/cli.html#tsconfig-generator)
    * Upgrades
      * Upgrade scripts
        * [Writing upgrade scripts](developer/reference/upgrades/upgrade_scripts.html#writing-upgrade-scripts)
        * [Phases of upgrade scripts](developer/reference/upgrades/upgrade_scripts.html#phases-of-upgrade-scripts)
      * Upgrade utils
        * [Installation](developer/reference/upgrades/upgrade_utils.html#installation)
        * [Using upgrade utils](developer/reference/upgrades/upgrade_utils.html#using-upgrade-utils)
        * Util functions
          * [Modules](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.modules)
          * [Models](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.models)
          * [Fields](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.fields)
          * [Records](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.records)
          * [ORM](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.orm)
          * [SQL](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.pg)
          * [Misc](developer/reference/upgrades/upgrade_utils.html#module-odoo.upgrade.util.misc)
    * External API
      * Connection
        * Configuration
          * [API Keys](developer/reference/external_api.html#api-keys)
          * [Test database](developer/reference/external_api.html#test-database)
        * [Logging in](developer/reference/external_api.html#logging-in)
      * Calling methods
        * List records
          * [Pagination](developer/reference/external_api.html#pagination)
        * [Count records](developer/reference/external_api.html#count-records)
        * [Read records](developer/reference/external_api.html#read-records)
        * [List record fields](developer/reference/external_api.html#list-record-fields)
        * [Search and read](developer/reference/external_api.html#search-and-read)
        * [Create records](developer/reference/external_api.html#create-records)
        * [Update records](developer/reference/external_api.html#update-records)
        * [Delete records](developer/reference/external_api.html#delete-records)
        * Inspection and introspection
          * [`ir.model`](developer/reference/external_api.html#ir-model)
          * [`ir.model.fields`](developer/reference/external_api.html#ir-model-fields)
    * Extract API
      * Overview
        * [Version](developer/reference/extract_api.html#version)
        * [Flow](developer/reference/extract_api.html#flow)
      * Parse
        * [Routes](developer/reference/extract_api.html#routes)
        * [Request](developer/reference/extract_api.html#request)
        * [Response](developer/reference/extract_api.html#response)
      * Get results
        * [Routes](developer/reference/extract_api.html#extract-api-get-result)
        * [Request](developer/reference/extract_api.html#id2)
        * Response
          * Common fields
            * [`feature_result`](developer/reference/extract_api.html#feature-result)
            * [candidate](developer/reference/extract_api.html#candidate)
          * Invoices
            * [`invoice_lines` feature](developer/reference/extract_api.html#invoice-lines-feature)
          * Bank statements
            * [`bank_statement_lines` feature](developer/reference/extract_api.html#bank-statement-lines-feature)
          * [Expense](developer/reference/extract_api.html#expense)
          * [Applicant](developer/reference/extract_api.html#applicant)
      * [Integration Testing](developer/reference/extract_api.html#integration-testing)



Welcome to the developer documentation of Odoo! Whether you’re a seasoned developer or just getting started, you’ll find here all the technical guidance and resources you need for developing Odoo applications. Explore our extensive collection of tutorials, how-to guides, and reference materials to achieve your development goals.

The Odoo development ecosystem is built on a modular and extensible architecture that allows you to extend existing applications or create new ones to meet the specific needs of modern businesses. You can make use of the tools and frameworks provided by Odoo to focus on getting your web application up and running quickly, without needing to reinvent the wheel and worry about the underlying infrastructure.

If you are new to Odoo or web application development, start with the [Server framework 101](developer/tutorials/server_framework_101.html) tutorial.

#### [TutorialsTutorials take you by the hand through hands-on exercises to build skills and familiarity in Odoo development. ](developer/tutorials.html)#### [How-to guidesRecipes that provide a step-by-step guide for addressing real-world problems and use-cases. ](developer/howtos.html)#### [ReferenceTechnical descriptions and factual information on the frameworks and APIs of Odoo. ](developer/reference.html)

Vedi anche

  * [Guide: Contribute to the codebase](contributing/development.html)

  * [Community forums](https://www.odoo.com/forum)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/developer.rst)

### Navigazione

  * [indice](genindex.html "Indice generale")
  * [moduli](py-modindex.html "Indice del modulo Python") |
  * [successivo](developer/tutorials.html "Tutorials") |
  * [precedente](administration/odoo_accounts.html "Account odoo.com") |
  * [Odoo 18.0 documentazione](index-2.html) »
  * Developer


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