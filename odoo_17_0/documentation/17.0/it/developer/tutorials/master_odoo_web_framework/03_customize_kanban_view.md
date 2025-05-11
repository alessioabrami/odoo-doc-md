# Chapter 3: Customize a kanban view — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../define_module_data.html "Define module data") |
  * [precedente](02_create_gallery_view.html "Chapter 2: Create a Gallery View") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Master the web framework](../master_odoo_web_framework.html) »
  * Chapter 3: Customize a kanban view



# Chapter 3: Customize a kanban view¶

We have gained an understanding of the numerous capabilities offered by the web framework. As a next step, we will customize a kanban view. This is a more complicated project that will showcase some non trivial aspects of the framework. The goal is to practice composing views, coordinating various aspects of the UI, and doing it in a maintainable way.

Bafien had the greatest idea ever: a mix of a kanban view and a list view would be perfect for your needs! In a nutshell, he wants a list of customers on the left of the CRM kanban view. When you click on a customer on the left sidebar, the kanban view on the right is filtered to only display leads linked to that customer.

Goal

Solutions

The solutions for each exercise of the chapter are hosted on the [official Odoo tutorials repository](https://github.com/odoo/tutorials/commits/17.0-master-odoo-web-framework-solutions/awesome_kanban).

## 1\. Create a new kanban view¶

Since we are customizing the kanban view, let us start by extending it and using our extension in the kanban view of CRM.

  1. Create a new empty component that extends the `KanbanController` component from `@web/views/kanban/kanban_controller`.

  2. Create a new view object and assign all keys and values from `kanbanView` from `@web/views/kanban/kanban_view`. Override the Controller key by putting your newly created controller.

  3. Register it in the views registry under `awesome_kanban`.

  4. Update the crm kanban arch in `awesome_kanban/views/views.xml` to use the extended view. This can be done by specifying the `js_class` attribute in the kanban node.




Vedi anche

[Example: Create a new view by extending a pre-existing one](https://github.com/odoo/odoo/blob/0a59f37e7dd73daff2e9926542312195b3de4154/addons/todo/static/src/views/todo_conversion_form/todo_conversion_form_view.js)

## 2\. Create a CustomerList component¶

We will need to display a list of customers, so we might as well create the component.

  1. Create a `CustomerList` component which only displays a `div` with some text for now.

  2. It should have a `selectCustomer` prop.

  3. Create a new template extending (XPath) the kanban controller template `web.KanbanView` to add the `CustomerList` next to the kanban renderer. Give it an empty function as `selectCustomer` for now.

Suggerimento

You can use this xpath inside the template to add a div before the renderer component.
         
         <xpath expr="//t[@t-component='props.Renderer']" position="before">
            ...
         </xpath>
         

  4. Subclass the kanban controller to add `CustomerList` in its sub-components.

  5. Make sure you see your component in the kanban view.




Vedi anche

[Template inheritance](../../reference/frontend/qweb.html#reference-qweb-template-inheritance)

## 3\. Load and display data¶

  1. Modify the `CustomerList` component to fetch a list of all customers in `onWillStart`.

  2. Display the list in the template with a `t-foreach`.

  3. Whenever a customer is selected, call the `selectCustomer` function prop.




Vedi anche

  * [Example: fetching records from a model](https://github.com/odoo/odoo/blob/986c00c1bd1b3ca16a04ab25f5a2504108136112/addons/project/static/src/views/burndown_chart/burndown_chart_model.js#L26-L31)




## 4\. Update the main kanban view¶

  1. Implement `selectCustomer` in the kanban controller to add the proper domain.

Suggerimento

Since it is not trivial to interact with the search view, here is a snippet to create a filter:
         
         this.env.searchModel.createNewFilters([{
               description: partner_name,
               domain: [["partner_id", "=", partner_id]],
               isFromAwesomeKanban: true, // this is a custom key to retrieve our filters later
         }])
         

  2. By clicking on multiple customers, you can see that the old customer filter is not replaced. Make sure that by clicking on a customer, the old filter is replaced by the new one.

Suggerimento

You can use this snippet to get the customers filters and toggle them.
         
         const customerFilters = this.env.searchModel.getSearchItems((searchItem) =>
               searchItem.isFromAwesomeKanban
         );
         
         for (const customerFilter of customerFilters) {
            if (customerFilter.isActive) {
                  this.env.searchModel.toggleSearchItem(customerFilter.id);
            }
         }
         

  3. Modify the template to give the real function to the `CustomerList` `selectCustomer` prop.




Nota

You can use [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) to make sure that the custom `isFromAwesomeKanban` key will not collide with keys any other code might add to the object.

## 5\. Only display customers which have an active order¶

There is a `opportunity_ids` field on `res.partner`. Let us allow the user to filter results on customers with at least one opportunity.

  1. Add an input of type checkbox in the `CustomerList` component, with a label «Active customers» next to it.

  2. Changing the value of the checkbox should filter the list of customers.




## 6\. Add a search bar to the customer list¶

Add an input above the customer list that allows the user to enter a string and to filter the displayed customers, according to their name.

Suggerimento

You can use the `fuzzyLookup` from `@web/core/utils/search` function to perform the filter.

Vedi anche

  * [Code: The fuzzylookup function](https://github.com/odoo/odoo/blob/235fc69280a18a5805d8eb84d76ada91ba49fe67/addons/web/static/src/core/utils/search.js#L41-L54)

  * [Example: Using fuzzyLookup](https://github.com/odoo/odoo/blob/1f4e583ba20a01f4c44b0a4ada42c4d3bb074273/addons/web/static/tests/core/utils/search_test.js#L17)




## 7\. Refactor the code to use `t-model`¶

To solve the previous two exercises, it is likely that you used an event listener on the inputs. Let us see how we could do it in a more declarative way, with the [t-model](https://github.com/odoo/owl/blob/master/doc/reference/input_bindings.md) directive.

  1. Make sure you have a reactive object that represents the fact that the filter is active (something like `this.state = useState({ displayActiveCustomers: false, searchString: ''})`).

  2. Modify the code to add a getter `displayedCustomers` which returns the currently active list of customers.

  3. Modify the template to use `t-model`.




## 8\. Paginate customers!¶

  1. Add a [pager](../../reference/frontend/owl_components.html#frontend-pager) in the `CustomerList`, and only load/render the first 20 customers.

  2. Whenever the pager is changed, the customer list should update accordingly.




This is actually pretty hard, in particular in combination with the filtering done in the previous exercise. There are many edge cases to take into account.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/master_odoo_web_framework/03_customize_kanban_view.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../define_module_data.html "Define module data") |
  * [precedente](02_create_gallery_view.html "Chapter 2: Create a Gallery View") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Master the web framework](../master_odoo_web_framework.html) »
  * Chapter 3: Customize a kanban view


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration