# Contabilità analitica — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](budget.html "Analytic budgets") |
  * [precedente](tax_carryover.html "Tax carryover") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Contabilità analitica



# Contabilità analitica¶

Analytic accounting helps you track costs and revenues, as well as analyze the profitability of a project or service. When creating your journal entries, the analytic widget allows the distribution of costs in one or more analytic accounts.

## Configurazione¶

Enable the Analytic Accounting feature by going to Accounting ‣ Configuration ‣ Settings ‣ Analytics.

## Analytic accounts¶

The analytic accounts give an overview of your costs and revenue.

Access your existing analytic accounts by going to Accounting ‣ Configuration ‣ Analytic Accounting: Analytic Accounts. To create a new analytic account, click New, and fill in the required information:

  * Analytic Account: add the name of your analytic account;

  * Customer: select the customer related to your project;

  * Reference: add a reference to make it easier to find the account when you are on your bill;

  * Plan: add an analytic plan;

  * Company: if you are managing multiple companies, select the company for which the analytic account will be used;

  * Currency: select the currency of the analytic account;




Then, fill in your [budget](budget.html) information.

## Analytic plans¶

The analytic plans allow you to analyze your accounting. For example, to track costs and revenues by project or department.

You can access the analytic plans by going to Accounting ‣ Configuration ‣ Analytic Accounting: Analytic Plans. Click New to create a new plan.

The following information must be completed:

  * Parent: link your plan to another Analytic Plan to build a hierarchy between your plans;

  * Default Applicability: decide how your plan behaves in the widget when creating a new journal entry:

>     * Optional: if selected, it is not mandatory to add the analytic plan in the widget;
> 
>     * Mandatory: if selected, an orange bullet is visible in the widget next to the plan until the analytic distribution is done (the bullet then turns to green); it is not possible to confirm the entry if no analytic account is selected;
> 
>     * Unavailable: if selected, the plan is not available in the widget.

  * Color: select the color of the tag related to this specific plan;

  * Company: add the company to which the plan applies;




You can also fine-tune your plans” applicability by filling in the Applicability tab:

  * Domain: choose to which accounting document your plan applies;

  * Financial Accounts Prefix: select the prefix of the account(s) to which this plan should be applied;

  * Product Category: decide to which product category the plan applies;

  * Applicability: decide how your plan behaves in the widget when creating a new journal
    

entry. The applicability you set here always overrides the default applicability.




Two smart buttons are available in the top-right corner:

>   * Subplans: can be created to have a more complex analytic structure. Click the Subplans smart button, and then New to add a subplan;
> 
>   * Analytic Accounts: to reach the analytic accounts related to the plan.
> 
> 


Nota

  * The analytic widget is prefilled based on the applicability, and the Analytic Distribution Models;

  * Each analytic plan must have at least one analytic account.




## Analytic distribution¶

Add a plan in the Analytic column when creating an invoice or bill. This field is mandatory only if you previously linked your analytic plan to at least one analytic account. After adding the plan, a **widget** opens where you can fill in the different information. You can add **tags** to reflect the related analytic accounts and decide how to split the costs between the accounts by modifying the percentage.

### Analytic distribution models¶

The analytic distribution models automatically apply a specific distribution based on defined criteria.

To create a new analytic distribution model, go to Accounting ‣ Configuration ‣ Analytic Distribution Models, click New and set the conditions your model has to meet to automatically apply:

  * Accounts Prefix: this analytic distribution will apply to all financial accounts sharing the prefix specified;

  * Partner: select a partner for which the analytic distribution will be used;

  * Partner Category: this field is not visible by default: add it by clicking on the columns selection button, and tick the Partner Category box. Add the partner category for which the analytic distribution will be used;

  * Product: select a product for which the analytic distribution will be used;

  * Product Category: this field is not visible by default: add it by clicking on the columns selection button, and tick the Product Category box. Select a product category for which the analytic distribution will be used;

  * Analytic: add the analytic accounts and their distribution;

  * Company: select a company for which the analytic distribution will be used;

  * Analytic Distribution: if the above conditions are met, the Analytic plan defined in this field as well as the distribution to be applied between the different analytic accounts is selected automatically on the entry.




Suggerimento

To **mass edit** several entries simultaneously, go to Accounting ‣ Accounting ‣ Journal items, and select the ones that need to be updated. Add the required distribution in the Analytic Distribution column, and click on the floppy disk icon to save. The analytic distribution template pops up, and you can save it for later use.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/reporting/analytic_accounting.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](budget.html "Analytic budgets") |
  * [precedente](tax_carryover.html "Tax carryover") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Contabilità analitica


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
  *[VAT]: Value Added Tax