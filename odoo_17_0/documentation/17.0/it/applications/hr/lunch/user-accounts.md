# Manage user accounts — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](management.html "Lunch management") |
  * [precedente](orders.html "Ordini") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Manage user accounts



# Manage user accounts¶

In Odoo’s _Lunch_ application, users pay for products directly from their _Lunch_ app account. For funds to appear in their account, a _Lunch_ app manager **must** transfer funds into each user’s account.

Importante

To add funds and manage user accounts, the user must have Administrator access rights set for the _Lunch_ application. This is verified by navigating to Settings app ‣ → Manage Users. Then, click on a user to view their various settings and access rights.

For more information, refer to the [Access rights](../../general/users/access_rights.html) documentation.

The _Lunch_ application does **not** directly interface in any way with software or products linked to any monetary accounts or billing. Money **cannot** be transferred from users” bank accounts, nor can users” credit cards be charged.

Odoo’s _Lunch_ application **only** allows for manual entries of cash exchanges that are handled by the _Lunch_ app manager. It is up to each individual company to create the method with which lunch accounts are replenished.

Example

Some examples of how money can be organized and transferred within a company:

  * Cash is handed to the _Lunch_ app manager, who then updates the user’s account.

  * Money is automatically deducted from the user’s paychecks, then the _Lunch_ app manager updates the account when paychecks are issued. This requires [adding a salary attachment](../payroll/payslips.html#payroll-worked-days-inputs) for the user’s payslip in the _Payroll_ app.

  * Companies can sell «lunch tickets» at a set price (for example, one ticket costs $5.00). Users can purchase tickets from a _Lunch_ app manager, who then updates the user’s account.




## Movimenti di cassa¶

To add funds to user accounts, each cash move must be individually logged. To view all cash move records, or create a new cash move, navigate to Lunch app ‣ Manager ‣ Cash Moves. Doing so reveals the Cash Moves dashboard.

On the Cash Moves dashboard, all cash moves are presented in a default list view, displaying each record’s Date, User, Description, and Amount. The total of all the cash moves is displayed at the bottom of the Amount column.

### Add funds¶

To add funds to a lunch account, click the New button, located in the top-left corner of the Cash Moves dashboard.

A blank Cash Moves form loads. Enter the following information on the form:

  * User: select the user depositing cash into their account from the drop-down menu. If the user is not in the database, they can be created by typing their name in the User field, and clicking either Create «user» or Create and edit… to create the user and edit the Create User form.

  * Date: using the calendar popover, select the date the transaction occurred.

  * Amount: enter the amount being added to the lunch account.

  * Description: enter a brief description of the transaction.




## Controlla conti¶

An overview of every transaction in the _Lunch_ app, including all cash deposits and purchases, can be viewed on the main _Control Accounts_ dashboard. To access this dashboard, navigate to Lunch app ‣ Manager ‣ Control Accounts.

All transactions are grouped By Employee, and listed alphabetically by the user’s first name. At the end of the user’s name, a number appears. This indicates the number of individual records logged for that user.

The default view is to have all individual transactions hidden. To view all transactions for a user, click the ▶ (triangle) icon to the left of the desired name to expand that specific group.

Each record includes the Date, User, Description, and Amount.

Importante

This list only displays the various transactions within the _Lunch_ app, and does **not** allow modifications to be made to any records listed.

Cash moves can be modified, but **only** from the Cash Moves dashboard, not from the Control Accounts dashboard.

It is **not** possible to modify any product-related records.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/lunch/user-accounts.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](management.html "Lunch management") |
  * [precedente](orders.html "Ordini") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Mensa](../lunch.html) »
  * Manage user accounts


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
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
  *[POS]: Punto vendita
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte