# Chapter 13: Interact With Other Modules — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](14_qwebintro.html "Chapter 14: A Brief History Of QWeb") |
  * [precedente](12_inheritance.html "Chapter 12: Inheritance") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 13: Interact With Other Modules



# Chapter 13: Interact With Other Modules¶

In the [previous chapter](12_inheritance.html), we used inheritance to modify the behavior of a module. In our real estate scenario, we would like to go a step further and be able to generate invoices for our customers. Odoo provides an Invoicing module, so it would be neat to create an invoice directly from our real estate module, i.e. once a property is set to “Sold”, an invoice is created in the Invoicing application.

## Concrete Example: Account Move¶

Nota

**Goal** : at the end of this section:

  * A new module `estate_account` should be created

  * When a property is sold, an invoice should be issued for the buyer




Any time we interact with another module, we need to keep in mind the modularity. If we intend to sell our application to real estate agencies, some may want the invoicing feature but others may not want it.

### Link Module¶

The common approach for such use cases is to create a “link” module. In our case, the module would depend on `estate` and `account` and would include the invoice creation logic of the estate property. This way the real estate and the accounting modules can be installed independently. When both are installed, the link module provides the new feature.

Exercise

Create a link module.

Create the `estate_account` module, which depends on the `estate` and `account` modules. For now, it will be an empty shell.

Tip: you already did this at the [beginning of the tutorial](02_newapp.html). The process is very similar.

When the `estate_account` module appears in the list, go ahead and install it! You’ll notice that the Invoicing application is installed as well. This is expected since your module depends on it. If you uninstall the Invoicing application, your module will be uninstalled as well.

### Invoice Creation¶

It’s now time to generate the invoice. We want to add functionality to the `estate.property` model, i.e. we want to add some extra logic for when a property is sold. Does that sound familiar? If not, it’s a good idea to go back to the [previous chapter](12_inheritance.html) since you might have missed something ;-)

As a first step, we need to extend the action called when pressing the [“Sold” button](09_actions.html) on a property. To do so, we need to create a [model inheritance](12_inheritance.html) in the `estate_account` module for the `estate.property` model. For now, the overridden action will simply return the `super` call. Maybe an example will make things clearer:
    
    
    from odoo import models
    
    class InheritedModel(models.Model):
        _inherit = "inherited.model"
    
        def inherited_action(self):
            return super().inherited_action()
    

A practical example can be found [here](https://github.com/odoo/odoo/blob/f1f48cdaab3dd7847e8546ad9887f24a9e2ed4c1/addons/event_sale/models/account_move.py#L7-L16).

Exercise

Add the first step of invoice creation.

  * Create a `estate_property.py` file in the correct folder of the `estate_account` module.

  * `_inherit` the `estate.property` model.

  * Override the `action_sold` method (you might have named it differently) to return the `super` call.




Tip: to make sure it works, add a `print` or a debugger breakpoint in the overridden method.

Is it working? If not, maybe check that all Python files are correctly imported.

If the override is working, we can move forward and create the invoice. Unfortunately, there is no easy way to know how to create any given object in Odoo. Most of the time, it is necessary to have a look at its model to find the required fields and provide appropriate values.

A good way to learn is to look at how other modules already do what you want to do. For example, one of the basic flows of Sales is the creation of an invoice from a sales order. This looks like a good starting point since it does exactly what we want to do. Take some time to read and understand the [_create_invoices](https://github.com/odoo/odoo/blob/f1f48cdaab3dd7847e8546ad9887f24a9e2ed4c1/addons/sale/models/sale.py#L610-L717) method. When you are done crying because this simple task looks awfully complex, we can move forward in the tutorial.

To create an invoice, we need the following information:

  * a `partner_id`: the customer

  * a `move_type`: it has several [possible values](https://github.com/odoo/odoo/blob/f1f48cdaab3dd7847e8546ad9887f24a9e2ed4c1/addons/account/models/account_move.py#L138-L147)

  * a `journal_id`: the accounting journal




This is enough to create an empty invoice.

Exercise

Add the second step of invoice creation.

Create an empty `account.move` in the override of the `action_sold` method:

  * the `partner_id` is taken from the current `estate.property`

  * the `move_type` should correspond to a “Customer Invoice”




Tips:

  * to create an object, use `self.env[model_name].create(values)`, where `values` is a `dict`.

  * the `create` method doesn’t accept recordsets as field values.




When a property is set to “Sold”, you should now have a new customer invoice created in Invoicing / Customers / Invoices.

Obviously we don’t have any invoice lines so far. To create an invoice line, we need the following information:

  * `name`: a description of the line

  * `quantity`

  * `price_unit`




Moreover, an invoice line needs to be linked to an invoice. The easiest and most efficient way to link a line to an invoice is to include all lines at invoice creation. To do this, the `invoice_line_ids` field is included in the `account.move` creation, which is a [`One2many`](../../reference/backend/orm.html#odoo.fields.One2many "odoo.fields.One2many"). One2many and Many2many use special “commands” which have been made human readable with the [`Command`](../../reference/backend/orm.html#odoo.fields.Command "odoo.fields.Command") namespace. This namespace represents a triplet command to execute on a set of records. The triplet was originally the only option to do these commands, but it is now standard to use the namespace instead. The format is to place them in a list which is executed sequentially. Here is a simple example to include a One2many field `line_ids` at creation of a `test_model`:
    
    
    from odoo import Command
    
    def inherited_action(self):
        self.env["test_model"].create(
            {
                "name": "Test",
                "line_ids": [
                    Command.create({
                        "field_1": "value_1",
                        "field_2": "value_2",
                    })
                ],
            }
        )
        return super().inherited_action()
    

Exercise

Add the third step of invoice creation.

Add two invoice lines during the creation of the `account.move`. Each property sold will be invoiced following these conditions:

  * 6% of the selling price

  * an additional 100.00 from administrative fees




Tip: Add the `invoice_line_ids` at creation following the example above. For each line, we need a `name`, `quantity` and `price_unit`.

This chapter might be one of the most difficult that has been covered so far, but it is the closest to what Odoo development will be in practice. In the [next chapter](14_qwebintro.html), we will introduce the templating mechanism used in Odoo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/server_framework_101/13_other_module.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](14_qwebintro.html "Chapter 14: A Brief History Of QWeb") |
  * [precedente](12_inheritance.html "Chapter 12: Inheritance") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 13: Interact With Other Modules


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous Integration