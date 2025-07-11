# Master the web framework — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](master_odoo_web_framework/01_build_clicker_game.html "Chapter 1: Build a Clicker game") |
  * [precedente](discover_js_framework/02_build_a_dashboard.html "Chapter 2: Build a dashboard") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Master the web framework



# Master the web framework¶

  * [Chapter 1: Build a Clicker game](master_odoo_web_framework/01_build_clicker_game.html)
  * [Chapter 2: Create a Gallery View](master_odoo_web_framework/02_create_gallery_view.html)
  * [Chapter 3: Customize a kanban view](master_odoo_web_framework/03_customize_kanban_view.html)



This tutorial is designed for those who have completed the [Discover the web framework](discover_js_framework.html) tutorial and are looking to deepen their knowledge of the web framework. It is organized in four independent projects, each focusing on different features of Odoo.

Nota

Each of these chapters can be done independantly, in any order. Also, be aware that some of them cover a lot of material, so they may be quite long.

The first project is about building a [clicker game](https://en.wikipedia.org/wiki/Incremental_game). While working on it, you will learn various aspects of the web framework: systray, command palette, dialogs, notifications, customizing existing components and much more.

The second project is focused on an important category of components: fields. Field components represent the value of a field for a record, they appear in many places in the web client: in form views, obviously, but also in kanban and list views, and may even be used alone, without a view. Due to their importance, it makes sense to learn how to create and manipulate such components.

In the context of the web framework, views usually refers to the javascript implementation of a component that represents one or many records, depending on a description (`ir.ui.view`). Such components are actually quite complicated and usually requires various sub systems (a renderer, a model, a controller, a arch parser, …). In chapter 3, we create a new view from scratch to represent a list of images.

Finally, the last project in chapter 4 is about customizing an existing view (a kanban view) by adding a search panel on its left. It is interesting to see how one can take existing code, and modify it to suit our needs. Also, it is a realistic project, that will feature many common issues that arises while working on Odoo.

## Setup¶

  1. Clone the [official Odoo tutorials repository](https://github.com/odoo/tutorials) and switch to the branch `17.0`.

  2. Add the cloned repository to your [`--addons-path`](../reference/cli.html#cmdoption-odoo-bin-addons-path).

  3. Start a new Odoo database and install the modules for each chapter that you want to work on: `awesome_clicker` (for chapter 1), `awesome_fields` (for chapter 2), `awesome_gallery` (for chapter 3) or `awesome_kanban` (for chapter 4).




## Content¶

  * [Chapter 1: Build a Clicker game](master_odoo_web_framework/01_build_clicker_game.html)

  * [Chapter 2: Create a Gallery View](master_odoo_web_framework/02_create_gallery_view.html)

  * [Chapter 3: Customize a kanban view](master_odoo_web_framework/03_customize_kanban_view.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/master_odoo_web_framework.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](master_odoo_web_framework/01_build_clicker_game.html "Chapter 1: Build a Clicker game") |
  * [precedente](discover_js_framework/02_build_a_dashboard.html "Chapter 2: Build a dashboard") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Master the web framework


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language