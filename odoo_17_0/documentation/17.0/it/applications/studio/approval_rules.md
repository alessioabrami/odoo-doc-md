# Regole di approvazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../general.html "Impostazioni generali") |
  * [precedente](pdf_reports.html "Reportistica in PDF") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di approvazione



# Regole di approvazione¶

Le regole di approvazione vengono utilizzate per automatizzare i processi di approvazione delle azioni. Ti permettono di definire i criteri quando è richiesta un’approvazione prima che venga eseguita un’azione utilizzando un pulsante.

## Configurazione¶

Per aggiungere regole di approvazione con Studio, segui questi passaggi:

  1. [apri studio](../studio.html#studio-access) e passa alla [vista](views.html) richiesta

  2. Select the button for which you want to add approval rules.

  3. In the Properties tab on the left, enable the Set approval rules feature.

  4. Specify the Allowed Group to limit the approval permission to a specific user group.

  5. Select the Responsible user to create an activity for a specific user when approval is requested from them.

  6. Select the Users to notify via internal note.

  7. Add a Description to be displayed in the Approval dialog.




Optionally, you can also add conditions for the approval rule to be applied by clicking the __( filter) icon next to the Allowed Group field.

To add another rule, click Add an approval rule. When there are multiple approval rules, you can:

  * enable Exclusive Approval to require approvers to be different users;

  * change the Notification Order of the approval rule so that the Responsible and Users to notify are only notified when the previous rule has been approved, and their approval is required. If the approval rules have the same Notification Order, all users are notified at the same time when the first approval is requested.




Click the __( trash) icon next to the Allowed Group field to delete the approval rule.

Suggerimento

Puoi creare [gruppi utente](../general/users/access_rights.html#access-rights-groups) specifici per le approvazioni.

## Usa¶

Once approval rules have been defined for a button:

  * A **user avatar** icon is displayed next to the button’s label for each approval rule that has been defined.

>   * When an unauthorized user clicks the button, an error message is displayed in the top-right corner and an activity is created for the user specified in the Responsible field.

  * Only users from the group defined in the Allowed Group field are authorized to approve or reject the action.




Gli utenti autorizzati possono:

  * approve and perform the action by clicking the button;

  * approve the action and allow another user to perform it by clicking the **user avatar** icon next to the button’s label, then clicking the __( Approve) button in the dialog that opens;

  * reject the action by clicking the **user avatar** icon next to the button’s label, then clicking the __( Reject) button in the dialog that opens.




Suggerimento

  * The user who approved/rejected the action can revoke their decision by clicking the **user avatar** icon next to the button’s label, then clicking the __( Revoke) button.

  * Approvals are tracked in the record’s chatter. An approval entry is also created every time a Studio approval-related action is performed. To access the approval entries, [activate the developer mode](../general/developer_mode.html) and go to Settings ‣ Technical ‣ Studio Approval Entries.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/studio/approval_rules.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../general.html "Impostazioni generali") |
  * [precedente](pdf_reports.html "Reportistica in PDF") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di approvazione


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation