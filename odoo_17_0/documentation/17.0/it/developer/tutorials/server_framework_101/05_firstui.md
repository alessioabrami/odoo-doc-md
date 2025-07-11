# Chapter 5: Finally, Some UI To Play With — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](06_basicviews.html "Chapter 6: Basic Views") |
  * [precedente](04_securityintro.html "Chapter 4: Security - A Brief Introduction") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 5: Finally, Some UI To Play With



# Chapter 5: Finally, Some UI To Play With¶

Now that we’ve created our new [model](03_basicmodel.html) and its corresponding [access rights](04_securityintro.html), it is time to interact with the user interface.

At the end of this chapter, we will have created a couple of menus in order to access a default list and form view.

## Data Files (XML)¶

**Reference** : the documentation related to this topic can be found in [Data Files](../../reference/backend/data.html#reference-data).

In [Chapter 4: Security - A Brief Introduction](04_securityintro.html), we added data through a CSV file. The CSV format is convenient when the data to load has a simple format. When the format is more complex (e.g. load the structure of a view or an email template), we use the XML format. For example, this [help field](https://github.com/odoo/odoo/blob/09c59012bf80d2ccbafe21c39e604d6cfda72924/addons/crm/views/crm_lost_reason_views.xml#L61-L69) contains HTML tags. While it would be possible to load such data through a CSV file, it is more convenient to use an XML file.

The XML files must be added to the same folders as the CSV files and defined similarly in the `__manifest__.py`. The content of the data files is also sequentially loaded when a module is installed or updated, therefore all remarks made for CSV files hold true for XML files. When the data is linked to views, we add them to the `views` folder.

In this chapter, we will load our first action and menus through an XML file. Actions and menus are standard records in the database.

Nota

When performance is important, the CSV format is preferred over the XML format. This is the case in Odoo where loading a CSV file is faster than loading an XML file.

In Odoo, the user interface (actions, menus and views) is largely defined by creating and composing records defined in an XML file. A common pattern is Menu > Action > View. To access records the user navigates through several menu levels; the deepest level is an action which triggers the opening of a list of the records.

## Actions¶

**Reference** : the documentation related to this topic can be found in [Actions](../../reference/backend/actions.html).

Nota

**Goal** : at the end of this section, an action should be loaded in the system. We won’t see anything yet in the UI, but the file should be loaded in the log:
    
    
    INFO rd-demo odoo.modules.loading: loading estate/views/estate_property_views.xml
    

Actions can be triggered in three ways:

  1. by clicking on menu items (linked to specific actions)

  2. by clicking on buttons in views (if these are connected to actions)

  3. as contextual actions on object




We will only cover the first case in this chapter. The second case will be covered in a [later chapter](09_actions.html) while the last is the focus of an advanced topic. In our Real Estate example, we would like to link a menu to the `estate.property` model, so we are able to create a new record. The action can be viewed as the link between the menu and the model.

A basic action for our `test_model` is:
    
    
    <record id="test_model_action" model="ir.actions.act_window">
        <field name="name">Test action</field>
        <field name="res_model">test_model</field>
        <field name="view_mode">tree,form</field>
    </record>
    

  * `id` is an [external identifier](../../glossary.html#term-external-identifier). It can be used to refer to the record (without knowing its in-database identifier).

  * `model` has a fixed value of `ir.actions.act_window` ([Window Actions (ir.actions.act_window)](../../reference/backend/actions.html#reference-actions-window)).

  * `name` is the name of the action.

  * `res_model` is the model which the action applies to.

  * `view_mode` are the views that will be available; in this case they are the list (tree) and form views. We’ll see [later](14_qwebintro.html) that there can be other view modes.




Examples can be found everywhere in Odoo, but [this](https://github.com/odoo/odoo/blob/09c59012bf80d2ccbafe21c39e604d6cfda72924/addons/crm/views/crm_lost_reason_views.xml#L57-L70) is a good example of a simple action. Pay attention to the structure of the XML data file since you will need it in the following exercise.

Exercise

Add an action.

Create the `estate_property_views.xml` file in the appropriate folder and define it in the `__manifest__.py` file.

Create an action for the model `estate.property`.

Restart the server and you should see the file loaded in the log.

## Menus¶

**Reference** : the documentation related to this topic can be found in [Shortcuts](../../reference/backend/data.html#reference-data-shortcuts).

Nota

**Goal** : at the end of this section, three menus should be created and the default view is displayed:

To reduce the complexity in declaring a menu (`ir.ui.menu`) and connecting it to the corresponding action, we can use the `<menuitem>` shortcut .

A basic menu for our `test_model_action` is:
    
    
    <menuitem id="test_model_menu_action" action="test_model_action"/>
    

The menu `test_model_menu_action` is linked to the action `test_model_action`, and the action is linked to the model `test_model`. As previously mentioned, the action can be seen as the link between the menu and the model.

However, menus always follow an architecture, and in practice there are three levels of menus:

  1. The root menu, which is displayed in the App switcher (the Odoo Community App switcher is a dropdown menu)

  2. The first level menu, displayed in the top bar

  3. The action menus




The easiest way to define the structure is to create it in the XML file. A basic structure for our `test_model_action` is:
    
    
    <menuitem id="test_menu_root" name="Test">
        <menuitem id="test_first_level_menu" name="First Level">
            <menuitem id="test_model_menu_action" action="test_model_action"/>
        </menuitem>
    </menuitem>
    

The name for the third menu is taken from the name of the `action`.

Exercise

Add menus.

Create the `estate_menus.xml` file in the appropriate folder and define it in the `__manifest__.py` file. Remember the sequential loading of the data files ;-)

Create the three levels of menus for the `estate.property` action created in the previous exercise. Refer to the **Goal** of this section for the expected result.

Restart the server and **refresh the browser**1. You should now see the menus, and you’ll even be able to create your first real estate property advertisement!

## Fields, Attributes And View¶

Nota

**Goal** : at the end of this section, the selling price should be read-only and the number of bedrooms and the availability date should have default values. Additionally the selling price and availability date values won’t be copied when the record is duplicated.

The reserved fields `active` and `state` are added to the `estate.property` model.

So far we have only used the generic view for our real estate property advertisements, but in most cases we want to fine tune the view. There are many fine-tunings possible in Odoo, but usually the first step is to make sure that:

  * some fields have a default value

  * some fields are read-only

  * some fields are not copied when duplicating the record




In our real estate business case, we would like the following:

  * The selling price should be read-only (it will be automatically filled in later)

  * The availability date and the selling price should not be copied when duplicating a record

  * The default number of bedrooms should be 2

  * The default availability date should be in 3 months




### Some New Attributes¶

Before moving further with the view design, let’s step back to our model definition. We saw that some attributes, such as `required=True`, impact the table schema in the database. Other attributes will impact the view or provide default values.

Exercise

Add new attributes to the fields.

Find the appropriate attributes (see [`Field`](../../reference/backend/orm.html#odoo.fields.Field "odoo.fields.Field")) to:

  * set the selling price as read-only

  * prevent copying of the availability date and the selling price values




Restart the server and refresh the browser. You should not be able to set any selling prices. When duplicating a record, the availability date should be empty.

### Default Values¶

Any field can be given a default value. In the field definition, add the option `default=X` where `X` is either a Python literal value (boolean, integer, float, string) or a function taking a model and returning a value:
    
    
    name = fields.Char(default="Unknown")
    last_seen = fields.Datetime("Last Seen", default=fields.Datetime.now)
    

The `name` field will have the value “Unknown” by default while the `last_seen` field will be set as the current time.

Exercise

Set default values.

Add the appropriate default attributes so that:

  * the default number of bedrooms is 2

  * the default availability date is in 3 months




Tip: this might help you: [`today()`](../../reference/backend/orm.html#odoo.fields.Date.today "odoo.fields.Date.today")

Check that the default values are set as expected.

### Reserved Fields¶

**Reference** : the documentation related to this topic can be found in [Reserved Field names](../../reference/backend/orm.html#reference-orm-fields-reserved).

A few field names are reserved for pre-defined behaviors. They should be defined on a model when the related behavior is desired.

Exercise

Add active field.

Add the `active` field to the `estate.property` model.

Restart the server, create a new property, then come back to the list view… The property will not be listed! `active` is an example of a reserved field with a specific behavior: when a record has `active=False`, it is automatically removed from any search. To display the created property, you will need to specifically search for inactive records.

Exercise

Set a default value for active field.

Set the appropriate default value for the `active` field so it doesn’t disappear anymore.

Note that the default `active=False` value was assigned to all existing records.

Exercise

Add state field.

Add a `state` field to the `estate.property` model. Five values are possible: New, Offer Received, Offer Accepted, Sold and Canceled. It must be required, should not be copied and should have its default value set to “New”.

Make sure to use the correct type!

The `state` will be used later on for several UI enhancements.

Now that we are able to interact with the UI thanks to the default views, the next step is obvious: we want to define [our own views](06_basicviews.html).

1
    

A refresh is needed since the web client keeps a cache of the various menus and views for performance reasons.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/server_framework_101/05_firstui.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](06_basicviews.html "Chapter 6: Basic Views") |
  * [precedente](04_securityintro.html "Chapter 4: Security - A Brief Introduction") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Server framework 101](../server_framework_101.html) »
  * Chapter 5: Finally, Some UI To Play With


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous Integration