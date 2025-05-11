# How-to guides — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](howtos/scss_tips.html "Write lean easy-to-maintain CSS") |
  * [precedente](tutorials/website_theme/06_going_live.html "Chapter 6 - Going live") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Developer](../developer.html) »
  * How-to guides



# How-to guides¶

  * Write lean easy-to-maintain CSS
    * [Browser defaults](howtos/scss_tips.html#browser-defaults)
    * [HTML tags](howtos/scss_tips.html#html-tags)
    * Utility classes
      * [Handling utility-classes verbosity](howtos/scss_tips.html#handling-utility-classes-verbosity)
  * Customize a field
    * [Subclass an existing field component](howtos/javascript_field.html#subclass-an-existing-field-component)
    * [Create a new field component](howtos/javascript_field.html#create-a-new-field-component)
  * Customize a view type
    * [Subclass an existing view](howtos/javascript_view.html#subclass-an-existing-view)
    * [Create a new view from scratch](howtos/javascript_view.html#create-a-new-view-from-scratch)
  * [Create a client action](howtos/javascript_client_action.html)
  * Create a standalone Owl application
    * [Overview](howtos/standalone_owl_application.html#overview)
    * [1\. Root component](howtos/standalone_owl_application.html#root-component)
    * [2\. Creating an assets bundle containing our code](howtos/standalone_owl_application.html#creating-an-assets-bundle-containing-our-code)
    * [3\. XML view that calls the assets bundle](howtos/standalone_owl_application.html#xml-view-that-calls-the-assets-bundle)
    * [4\. Controller that renders the view](howtos/standalone_owl_application.html#controller-that-renders-the-view)
  * Use Owl components on the portal and website
    * [Overview](howtos/frontend_owl_components.html#overview)
    * [1\. Creating the Owl component](howtos/frontend_owl_components.html#creating-the-owl-component)
    * [2\. Adding your component to the `web.assets_frontend` bundle](howtos/frontend_owl_components.html#adding-your-component-to-the-web-assets-frontend-bundle)
    * [3\. Adding an `<owl-component>` tag to a page](howtos/frontend_owl_components.html#adding-an-owl-component-tag-to-a-page)
    * Points of caution
      * [Layout shift](howtos/frontend_owl_components.html#layout-shift)
      * [Poorer indexing by search engines](howtos/frontend_owl_components.html#poorer-indexing-by-search-engines)
    * When to use Owl components on the portal and website
      * [When you don’t care about SEO](howtos/frontend_owl_components.html#when-you-don-t-care-about-seo)
      * [When you need strong interactivity](howtos/frontend_owl_components.html#when-you-need-strong-interactivity)
  * [Website themes](howtos/website_themes.html)
    * Setup
      * [Install](howtos/website_themes/setup.html#install)
      * Databases
        * Structure
          * [Models](howtos/website_themes/setup.html#models)
          * Fields
            * [Classic fields](howtos/website_themes/setup.html#classic-fields)
            * [Relational fields](howtos/website_themes/setup.html#relational-fields)
          * Views
            * [Backend vs. Frontend](howtos/website_themes/setup.html#backend-vs-frontend)
            * [Static vs. Dynamic](howtos/website_themes/setup.html#static-vs-dynamic)
            * [Standard vs. Inherited](howtos/website_themes/setup.html#standard-vs-inherited)
        * Import an existing database
          * Dump
            * [Odoo SaaS](howtos/website_themes/setup.html#odoo-saas)
            * [Odoo.sh](howtos/website_themes/setup.html#odoo-sh)
          * [Move filestore](howtos/website_themes/setup.html#move-filestore)
          * [Database setup](howtos/website_themes/setup.html#database-setup)
      * Getting started
        * [Running Odoo](howtos/website_themes/setup.html#running-odoo)
        * [Shell script](howtos/website_themes/setup.html#shell-script)
        * [Sign in](howtos/website_themes/setup.html#sign-in)
        * [Developer mode](howtos/website_themes/setup.html#developer-mode)
    * Theming
      * Theme module
        * [Technical naming](howtos/website_themes/theming.html#technical-naming)
        * [File structure](howtos/website_themes/theming.html#file-structure)
        * [Initialization](howtos/website_themes/theming.html#initialization)
        * [Declaration](howtos/website_themes/theming.html#declaration)
      * Default options
        * Odoo variables
          * [Global](howtos/website_themes/theming.html#global)
          * Fonts
            * [Google fonts](howtos/website_themes/theming.html#google-fonts)
            * [Custom fonts](howtos/website_themes/theming.html#custom-fonts)
          * [Colors](howtos/website_themes/theming.html#colors)
          * [Gradients](howtos/website_themes/theming.html#gradients)
        * Bootstrap variables
          * Font sizes
            * [Text style](howtos/website_themes/theming.html#text-style)
            * Sizing classes
              * [Heading and body text](howtos/website_themes/theming.html#heading-and-body-text)
              * [Display headings](howtos/website_themes/theming.html#display-headings)
        * [Website settings](howtos/website_themes/theming.html#website-settings)
        * Views
          * [Presets](howtos/website_themes/theming.html#presets)
      * Assets
        * [Styles](howtos/website_themes/theming.html#styles)
        * [Interactivity](howtos/website_themes/theming.html#interactivity)
    * Layout
      * [Default](howtos/website_themes/layout.html#default)
      * XPath
        * [Expressions](howtos/website_themes/layout.html#expressions)
        * [Position](howtos/website_themes/layout.html#position)
      * [QWeb](howtos/website_themes/layout.html#qweb)
      * Custom fields
        * [Declaration](howtos/website_themes/layout.html#declaration)
        * [Back-end](howtos/website_themes/layout.html#back-end)
        * [Front-end](howtos/website_themes/layout.html#front-end)
      * Background
        * [Colors](howtos/website_themes/layout.html#colors)
        * [Image/pattern](howtos/website_themes/layout.html#image-pattern)
      * Header
        * Standard
          * [Desktop template](howtos/website_themes/layout.html#desktop-template)
          * [Mobile template](howtos/website_themes/layout.html#mobile-template)
        * [Custom](howtos/website_themes/layout.html#custom)
        * Components
          * [Logo](howtos/website_themes/layout.html#logo)
          * [Menu](howtos/website_themes/layout.html#menu)
          * [Sign in](howtos/website_themes/layout.html#sign-in)
          * [User dropdown](howtos/website_themes/layout.html#user-dropdown)
          * [Language selector](howtos/website_themes/layout.html#language-selector)
          * [Call to action](howtos/website_themes/layout.html#call-to-action)
          * [Navbar toggler](howtos/website_themes/layout.html#navbar-toggler)
      * Footer
        * [Standard](howtos/website_themes/layout.html#website-themes-layout-footer-standard)
        * [Custom](howtos/website_themes/layout.html#website-themes-layout-footer-custom)
      * [Copyright](howtos/website_themes/layout.html#copyright)
      * [Drop zone](howtos/website_themes/layout.html#drop-zone)
      * Responsive
        * [Font sizes](howtos/website_themes/layout.html#font-sizes)
        * [Column sizes](howtos/website_themes/layout.html#column-sizes)
        * [Visibility conditions](howtos/website_themes/layout.html#visibility-conditions)
    * Navigation
      * [Default](howtos/website_themes/navigation.html#default)
      * Menu item
        * [New window](howtos/website_themes/navigation.html#new-window)
        * [External Links](howtos/website_themes/navigation.html#external-links)
        * [Anchor](howtos/website_themes/navigation.html#anchor)
      * [Dropdown menu](howtos/website_themes/navigation.html#dropdown-menu)
      * Mega menu
        * [Custom template](howtos/website_themes/navigation.html#custom-template)
    * Pages
      * [Default pages](howtos/website_themes/pages.html#default-pages)
      * Theme pages
        * [`noupdate` attribute](howtos/website_themes/pages.html#noupdate-attribute)
        * [Header overlay](howtos/website_themes/pages.html#header-overlay)
        * [Page templates](howtos/website_themes/pages.html#page-templates)
    * Media
      * Images
        * [Declaration](howtos/website_themes/media.html#declaration)
        * Use
          * [Regular images](howtos/website_themes/media.html#regular-images)
          * [Background images](howtos/website_themes/media.html#background-images)
          * [Company logo](howtos/website_themes/media.html#company-logo)
      * [Videos](howtos/website_themes/media.html#videos)
      * [Icons](howtos/website_themes/media.html#icons)
    * Building blocks
      * [File structure](howtos/website_themes/building_blocks.html#file-structure)
      * Layout
        * [Wrapper](howtos/website_themes/building_blocks.html#wrapper)
        * Elements
          * [Sizing](howtos/website_themes/building_blocks.html#sizing)
          * [Colors](howtos/website_themes/building_blocks.html#colors)
          * Features
            * [Non-editable areas](howtos/website_themes/building_blocks.html#non-editable-areas)
            * [Backgrounds](howtos/website_themes/building_blocks.html#backgrounds)
            * [Text highlights](howtos/website_themes/building_blocks.html#text-highlights)
        * Grid layout
          * [Use](howtos/website_themes/building_blocks.html#use)
          * [Items in a grid](howtos/website_themes/building_blocks.html#items-in-a-grid)
          * [Grid item padding](howtos/website_themes/building_blocks.html#grid-item-padding)
      * [Compatibility system](howtos/website_themes/building_blocks.html#compatibility-system)
      * Custom snippet
        * [Template](howtos/website_themes/building_blocks.html#template)
        * Options
          * [Template](howtos/website_themes/building_blocks.html#website-themes-building-blocks-custom-options-template)
          * Binding
            * [data-selector](howtos/website_themes/building_blocks.html#data-selector)
            * [data-target](howtos/website_themes/building_blocks.html#data-target)
            * [data-exclude](howtos/website_themes/building_blocks.html#data-exclude)
            * [data-drop-in](howtos/website_themes/building_blocks.html#data-drop-in)
            * [data-drop-near](howtos/website_themes/building_blocks.html#data-drop-near)
            * [data-js](howtos/website_themes/building_blocks.html#data-js)
          * Layout & fields
            * [`<we-title>`](howtos/website_themes/building_blocks.html#we-title)
            * [`<we-row>`](howtos/website_themes/building_blocks.html#we-row)
            * [`<we-button>`](howtos/website_themes/building_blocks.html#we-button)
            * [`<we-select>`](howtos/website_themes/building_blocks.html#we-select)
            * [`<we-button-group>`](howtos/website_themes/building_blocks.html#we-button-group)
            * [`<we-checkbox>`](howtos/website_themes/building_blocks.html#we-checkbox)
            * [`<we-range>`](howtos/website_themes/building_blocks.html#we-range)
            * [`<we-input>`](howtos/website_themes/building_blocks.html#we-input)
            * [`<we-colorpicker>`](howtos/website_themes/building_blocks.html#we-colorpicker)
          * Methods
            * Built-in methods
              * [Selection](howtos/website_themes/building_blocks.html#selection)
              * [Events](howtos/website_themes/building_blocks.html#events)
            * [Custom methods](howtos/website_themes/building_blocks.html#custom-methods)
        * Dynamic Content templates
          * [Call the template](howtos/website_themes/building_blocks.html#call-the-template)
          * [Examples](howtos/website_themes/building_blocks.html#examples)
    * Shapes
      * Background shapes
        * Standard
          * Colors mapping
            * [Switch colors mapping](howtos/website_themes/shapes.html#switch-colors-mapping)
            * [Add extra colors mapping](howtos/website_themes/shapes.html#add-extra-colors-mapping)
        * Custom
          * [Attachment](howtos/website_themes/shapes.html#attachment)
          * [SCSS](howtos/website_themes/shapes.html#scss)
          * [Add the option](howtos/website_themes/shapes.html#add-the-option)
          * [Use it into your pages](howtos/website_themes/shapes.html#use-it-into-your-pages)
    * Gradients
      * [Standard](howtos/website_themes/gradients.html#standard)
      * [Custom](howtos/website_themes/gradients.html#custom)
    * Animations
      * [On appearance](howtos/website_themes/animations.html#on-appearance)
      * [On scroll](howtos/website_themes/animations.html#on-scroll)
      * [On hover](howtos/website_themes/animations.html#on-hover)
    * Forms
      * [Default form](howtos/website_themes/forms.html#default-form)
      * [Actions](howtos/website_themes/forms.html#actions)
      * [Success](howtos/website_themes/forms.html#success)
    * Translations
      * Frontend
        * [Default pages](howtos/website_themes/translations.html#default-pages)
        * Translatable strings
          * [t-att- / t-attf-](howtos/website_themes/translations.html#t-att-t-attf)
          * [Exception: t-value / t-valuef](howtos/website_themes/translations.html#exception-t-value-t-valuef)
          * [Mixing translatable and non-translatable](howtos/website_themes/translations.html#mixing-translatable-and-non-translatable)
      * [Backend](howtos/website_themes/translations.html#backend)
      * [Export](howtos/website_themes/translations.html#export)
      * [PO file](howtos/website_themes/translations.html#po-file)
      * [Import](howtos/website_themes/translations.html#import)
    * Going live
      * Module import
        * [Odoo SaaS](howtos/website_themes/going_live.html#odoo-saas)
        * [Odoo.sh](howtos/website_themes/going_live.html#odoo-sh)
      * [What’s next?](howtos/website_themes/going_live.html#what-s-next)
  * Web Services
    * [XML-RPC Library](howtos/web_services.html#xml-rpc-library)
    * [JSON-RPC Library](howtos/web_services.html#json-rpc-library)
  * Multi-company Guidelines
    * [Company-dependent fields](howtos/company.html#company-dependent-fields)
    * [Multi-company consistency](howtos/company.html#multi-company-consistency)
    * [Default company](howtos/company.html#default-company)
    * [Views](howtos/company.html#views)
    * [Security rules](howtos/company.html#security-rules)
  * Create customized reports
    * [Create a model](howtos/create_reports.html#create-a-model)
    * [Populate the model](howtos/create_reports.html#populate-the-model)
    * [Use the model](howtos/create_reports.html#use-the-model)
    * [Extra tips](howtos/create_reports.html#extra-tips)
  * Accounting localization
    * [Installation procedure](howtos/accounting_localization.html#installation-procedure)
    * [Building a localization module](howtos/accounting_localization.html#building-a-localization-module)
    * Chart of Accounts
      * [Account tags](howtos/accounting_localization.html#account-tags)
      * [Accounts](howtos/accounting_localization.html#accounts)
      * [Account groups](howtos/accounting_localization.html#account-groups)
      * [Taxes](howtos/accounting_localization.html#taxes)
      * [Tax Report](howtos/accounting_localization.html#tax-report)
      * [Fiscal positions](howtos/accounting_localization.html#fiscal-positions)
    * [Final steps](howtos/accounting_localization.html#final-steps)
    * [Accounting reports](howtos/accounting_localization.html#accounting-reports)
  * Translating Modules
    * [Exporting translatable term](howtos/translations.html#exporting-translatable-term)
    * [Implicit exports](howtos/translations.html#implicit-exports)
    * Explicit exports
      * [Variables](howtos/translations.html#variables)
      * [Blocks](howtos/translations.html#blocks)
      * [Plural](howtos/translations.html#plural)
      * [Read vs Run Time](howtos/translations.html#read-vs-run-time)
  * Connect with a device
    * Detect Devices
      * [Interface](howtos/connect_device.html#interface)
      * [Driver](howtos/connect_device.html#driver)
    * Communicate With Devices
      * [Actions](howtos/connect_device.html#actions)
      * [Longpolling](howtos/connect_device.html#longpolling)
  * Upgrade a customized database
    * [Step 1: Stop the developments](howtos/upgrade_custom_db.html#step-1-stop-the-developments)
    * [Step 2: Request an upgraded database](howtos/upgrade_custom_db.html#step-2-request-an-upgraded-database)
    * Step 3: Empty database
      * [Make custom modules installable](howtos/upgrade_custom_db.html#make-custom-modules-installable)
      * [Test and fixes](howtos/upgrade_custom_db.html#test-and-fixes)
      * [Clean the code](howtos/upgrade_custom_db.html#clean-the-code)
      * [Standard tests](howtos/upgrade_custom_db.html#standard-tests)
    * Step 4: Upgraded database
      * Migrate the data
        * [Running and testing upgrade scripts](howtos/upgrade_custom_db.html#running-and-testing-upgrade-scripts)
      * [Test the custom modules](howtos/upgrade_custom_db.html#test-the-custom-modules)
    * [Step 5: Testing and rehearsal](howtos/upgrade_custom_db.html#step-5-testing-and-rehearsal)
    * [Step 6: Production upgrade](howtos/upgrade_custom_db.html#step-6-production-upgrade)



## Frontend development¶

#### [Write lean easy-to-maintain CSSFollow this guide to keep the technical debt of your CSS code under control. ](howtos/scss_tips.html)#### [Customize a fieldLearn how to customize field components in the web framework. ](howtos/javascript_field.html)#### [Customize a view typeLearn how to customize view types in the web framework. ](howtos/javascript_view.html)#### [Create a client actionLearn how to create client actions in the web framework. ](howtos/javascript_client_action.html)#### [Create a standalone Owl applicationLearn how to create a public-facing Owl application outside of the web client using a controller and the web framework. ](howtos/standalone_owl_application.html)#### [Use Owl components on the portal and websiteLearn how to use Owl components on the portal and website. ](howtos/frontend_owl_components.html)#### [Website themesLearn how to customize your website by creating a custom theme. ](howtos/website_themes.html)

## Server-side development¶

#### [Web servicesLearn more about Odoo’s web services. ](howtos/web_services.html)#### [Multi-company guidelinesLearn how to manage multiple companies and deal with the records-related specificities of a multi-company environment. ](howtos/company.html)#### [Create customized reportsLearn how to create customized reports with SQL Views. ](howtos/create_reports.html)#### [Accounting localizationLearn how to build a localization module, create bank operation models and dynamic reports. ](howtos/accounting_localization.html)#### [Translating modulesLearn how to provide translation abilities to your module. ](howtos/translations.html)#### [Connect with a deviceLearn how to enable a module to detect and communicate with an IoT device. ](howtos/connect_device.html)

## Custom development¶

#### [Upgrade a customized databaseLearn how to upgrade a customized database, as well as the code and data of its custom modules. ](howtos/upgrade_custom_db.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](howtos/scss_tips.html "Write lean easy-to-maintain CSS") |
  * [precedente](tutorials/website_theme/06_going_live.html "Chapter 6 - Going live") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Developer](../developer.html) »
  * How-to guides