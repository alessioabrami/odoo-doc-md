# Audience targeting — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](workflow_activities.html "Campaign workflow activities") |
  * [precedente](../marketing_automation.html "Automazione marketing") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Audience targeting



# Audience targeting¶

The Target and Filter fields on the campaign form, also referred to as the _domain_ , contain the parameters used to define the target audience for the campaign’s reach (i.e., the unique contact records in the database, and imported list, etc.).

  * Target: specifies the type of records available for use in the campaign, such as Lead/Opportunity, Event Registration, Contact, The assigned records model determines the fields that are available throughout the campaign, including the fields available in the Filter section, and in dynamic placeholders.

  * Save as Favorite Filter: saves the current Filter for future use with the current Target model, and can be managed from the Marketing Automation app ‣ Configuration ‣ Favorite Filters menu.

  * Unicity based on: specifies the Target model field where duplicates should be avoided. Traditionally, the Email field is used, but any available field can be used.

  * Filter: contains an interactive form with configurable logic to further refine the targeting parameters under the chosen Target model. See more details in the Defining filters section.

  * Include archived: allows or disallows the inclusion of archived records in the target audience.




Suggerimento

A Responsible user can be assigned to the campaign by activating [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html#developer-mode).

Nota

Each activity in a campaign’s workflow can target a subset of the target audience; see the [Campaign workflow activities](workflow_activities.html) documentation for more information.

## Defining filters¶

The default campaign Filter configuration is set to Match all records, indicating that the campaign is targeting **all** records of the Target model.

To refine the Filter rules of a campaign, click the ➕ Add condition button to reveal a new row with configurable rule parameters. See the [Search, filter, and group records](../../essentials/search.html#search-custom-filters) documentation for more information on how to create filter rules.

At the bottom of the filter rules is a # record(s) button, which indicates the total number of records targeted by this domain. Select the # record(s) button to open a Selected records pop-up window, in which the targeted records can be viewed.

Suggerimento

Attiva la modalità sviluppatore per rivelare il nome tecnico e il tipo di dati di ogni campo così come la casella di testo # Editor codice al di sotto delle regole del filtro per visualizzare e modificare manualmente il dominio.

Example

To target all leads and opportunities from the _CRM_ app that are in the _New_ stage, and have an expected revenue greater than $1,000, the following should be entered:

  * Target: `Lead/Opportunity`

  * Unicity based on: `Email (Lead/Opportunity)`

  * Filter: Match all 🔽 (down arrow) of the following rules:

    1. Stage is in New

    2. Ricavi previsti > `1.000`

    3. qualsiasi 🔽 (freccia giù) di:

       * Tipo = Lead

       * Tipo = Opportunità




With the above configuration, the campaign targets 157 record(s).

Vedi anche

  * [Domain developer documentation](../../../developer/reference/backend/orm.html#reference-orm-domains)

  * [Campaign workflow activities](workflow_activities.html)

  * [Testing/running campaigns](testing_running.html)

  * [Campaign metrics](understanding_metrics.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/marketing_automation/target_audience.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](workflow_activities.html "Campaign workflow activities") |
  * [precedente](../marketing_automation.html "Automazione marketing") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Marketing](../../marketing.html) »
  * [Automazione marketing](../marketing_automation.html) »
  * Audience targeting


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