# Server framework 101 — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](server_framework_101/01_architecture.html "Chapter 1: Architecture Overview") |
  * [precedente](setup_guide.html "Setup guide") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Server framework 101



# Server framework 101¶

  * [Chapter 1: Architecture Overview](server_framework_101/01_architecture.html)
  * [Chapter 2: A New Application](server_framework_101/02_newapp.html)
  * [Chapter 3: Models And Basic Fields](server_framework_101/03_basicmodel.html)
  * [Chapter 4: Security - A Brief Introduction](server_framework_101/04_securityintro.html)
  * [Chapter 5: Finally, Some UI To Play With](server_framework_101/05_firstui.html)
  * [Chapter 6: Basic Views](server_framework_101/06_basicviews.html)
  * [Chapter 7: Relations Between Models](server_framework_101/07_relations.html)
  * [Chapter 8: Computed Fields And Onchanges](server_framework_101/08_compute_onchange.html)
  * [Chapter 9: Ready For Some Action?](server_framework_101/09_actions.html)
  * [Chapter 10: Constraints](server_framework_101/10_constraints.html)
  * [Chapter 11: Add The Sprinkles](server_framework_101/11_sprinkles.html)
  * [Chapter 12: Inheritance](server_framework_101/12_inheritance.html)
  * [Chapter 13: Interact With Other Modules](server_framework_101/13_other_module.html)
  * [Chapter 14: A Brief History Of QWeb](server_framework_101/14_qwebintro.html)
  * [Chapter 15: The final word](server_framework_101/15_final_word.html)



Welcome to the Server framework 101 tutorial! If you reached this page that means you are interested in the development of your own Odoo module. It might also mean that you recently joined the Odoo company for a rather technical position. In any case, your journey to the technical side of Odoo starts here.

The goal of this tutorial is for you to get an insight of the most important parts of the Odoo development framework while developing your own Odoo module to manage real estate assets. The chapters should be followed in their given order since they cover the development of a new Odoo application from scratch in an incremental way. In other words, each chapter depends on the previous one.

Importante

Before going further, make sure you have prepared your development environment with the [setup guide](setup_guide.html).

Ready? Let’s get started!

  * [Chapter 1: Architecture Overview](server_framework_101/01_architecture.html)

  * [Chapter 2: A New Application](server_framework_101/02_newapp.html)

  * [Chapter 3: Models And Basic Fields](server_framework_101/03_basicmodel.html)

  * [Chapter 4: Security - A Brief Introduction](server_framework_101/04_securityintro.html)

  * [Chapter 5: Finally, Some UI To Play With](server_framework_101/05_firstui.html)

  * [Chapter 6: Basic Views](server_framework_101/06_basicviews.html)

  * [Chapter 7: Relations Between Models](server_framework_101/07_relations.html)

  * [Chapter 8: Computed Fields And Onchanges](server_framework_101/08_compute_onchange.html)

  * [Chapter 9: Ready For Some Action?](server_framework_101/09_actions.html)

  * [Chapter 10: Constraints](server_framework_101/10_constraints.html)

  * [Chapter 11: Add The Sprinkles](server_framework_101/11_sprinkles.html)

  * [Chapter 12: Inheritance](server_framework_101/12_inheritance.html)

  * [Chapter 13: Interact With Other Modules](server_framework_101/13_other_module.html)

  * [Chapter 14: A Brief History Of QWeb](server_framework_101/14_qwebintro.html)

  * [Chapter 15: The final word](server_framework_101/15_final_word.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/server_framework_101.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](server_framework_101/01_architecture.html "Chapter 1: Architecture Overview") |
  * [precedente](setup_guide.html "Setup guide") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [Tutorials](../tutorials.html) »
  * Server framework 101


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language