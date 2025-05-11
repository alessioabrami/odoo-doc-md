# Analytic budgets — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](intrastat.html "Intrastat") |
  * [precedente](analytic_accounting.html "Contabilità analitica") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Analytic budgets



# Analytic budgets¶

Managing budgets is an essential part of running a business. Budgets help people become more intentional with how money is spent and direct people to organize and prioritize their work to meet financial goals. They allow the planning of a desired financial outcome and then measure the actual performance against the plan. Odoo manages budgets using both **general** and **analytic accounts**.

## Configurazione¶

Go to Accounting ‣ Configuration ‣ Settings ‣ Analytics section, and enable Budget Management.

### Budgetary positions¶

Budgetary positions are lists of accounts for which you want to keep budgets (typically expense or income accounts).

To define budgetary positions, go to Accounting ‣ Configuration ‣ Management: Budgetary Positions and New. Add a Name to your budgetary position and select the Company it applies to. Click Add a line to add one or more accounts.

Nota

Each budgetary position can have any number of accounts from the chart of accounts, though it must have at least one.

## Caso d’uso¶

Let’s illustrate this with an example.

We just started a project with _Smith & Co_, and we would like to budget the income and expenses of that project. We plan on having a revenue of 1000, and we don’t want to spend more than 700.

First, we need to define what accounts relate to our project’s expenses. Go to Accounting ‣ Configuration ‣ Management: Budgetary positions, and click New to add a position. Add the accounts wherein expenses will be booked.

Let’s repeat the steps to create a budgetary position that reflects the revenue.

### Analytical accounts¶

Odoo needs to know which costs or expenses are relevant to a specified budget, as the above general accounts may be used for different projects. Go to Accounting ‣ Configuration ‣ Analytic Accounting: Analytic Accounts and click New to add a new **Analytic Account** called _Smith & Co_.

The Plan field has to be completed. Plans group multiple analytic accounts; they distribute costs and benefits to analyze business performance. **Analytic Plans** can be created or configured by going to Accounting ‣ Configuration ‣ Analytic Accounting: Analytic Plans.

When creating a new customer invoice and/or vendor bill, you have to refer to this analytic account.

### Define the budget¶

Let’s set our targets. We specified that we expect to gain 1000 with this project, and we would like not to spend more than 700. Go to Accounting ‣ Management: Budgets and click New to create a new budget for _Smith & Co_ project.

First, fill in your Budget Name. Then, select the Period wherein the budget is applicable. Next, add the Budgetary Position you want to track, define the related Analytic Account, and add the Planned Amount.

Nota

When recording a planned amount related to expenses, the amount must be negative.

### Check your budget¶

Go to Accounting ‣ Management: Budgets and find the _Smith & Co_ Project to see how it evolves according to the expenses or income for the related analytic account.

The Practical Amount evolves when a new journal entry related to your analytic account and an account from your budgetary position is created.

The Theoretical Amount represents the amount of money you theoretically could have spent or should have received based on the date. For example, suppose your budget is 1200 for 12 months (January to December), and today is 31 of January. In that case, the theoretical amount will be 100 since this is the actual amount that could have been made.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/reporting/budget.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](intrastat.html "Intrastat") |
  * [precedente](analytic_accounting.html "Contabilità analitica") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Analytic budgets


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
  *[POS]: Point Of Sale
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire