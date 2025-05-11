# Create a client action — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](standalone_owl_application.html "Create a standalone Owl application") |
  * [precedente](javascript_view.html "Customize a view type") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Create a client action



# Create a client action¶

A client action triggers an action that is entirely implemented in the client side. One of the benefits of using a client action is the ability to create highly customized interfaces with ease. A client action is typically defined by an OWL component; we can also use the web framework and use services, core components, hooks,…

  1. Create the [client action](../reference/backend/actions.html#reference-actions-client), don’t forget to make it accessible.
         
         <record model="ir.actions.client" id="my_client_action">
             <field name="name">My Client Action</field>
             <field name="tag">my_module.MyClientAction</field>
         </record>
         

  2. Create a component that represents the client action.

`my_client_action.js`¶
         
         /** @odoo-module **/
         
         import { registry } from "@web/core/registry";
         
         import { Component } from  "@odoo/owl";
         
         class MyClientAction extends Component {}
         MyClientAction.template = "my_module.clientaction";
         
         // remember the tag name we put in the first step
         registry.category("actions").add("my_module.MyClientAction", MyClientAction);
         

`my_client_action.xml`¶
         
         <?xml version="1.0" encoding="UTF-8" ?>
         <templates xml:space="preserve">
             <t t-name="awesome_tshirt.clientaction">
                 Hello world
             </t>
         </templates>
         




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos/javascript_client_action.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](standalone_owl_application.html "Create a standalone Owl application") |
  * [precedente](javascript_view.html "Customize a view type") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Create a client action


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration