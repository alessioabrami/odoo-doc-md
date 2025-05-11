# Silverfin integration — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customize.html "Custom reports") |
  * [precedente](data_inalterability.html "Data inalterability check report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Silverfin integration



# Silverfin integration¶

[Silverfin](https://www.silverfin.com/) is a third-party service provider that offers a cloud platform for accountants.

Odoo and Silverfin provide an integration to automate the synchronization of data.

## Configurazione¶

To configure this integration, you need to input the following data into your Silverfin account:

  * user’s email address

  * Odoo API key

  * URL of the Odoo database

  * name of your Odoo database




### Odoo API key¶

You can create Odoo external API keys either for a single database (hosting: Odoo Online, On-premise, and Odoo.sh) or for all databases managed by a single user (hosting: Odoo Online).

Importante

  * These API keys are personal and provide full access to your user account. Store it securely.

  * You can copy the API key only at its creation. It is not possible to retrieve it later.

  * If you need it again, create a new API key (and delete the old one).




Vedi anche

[External API](../../../../developer/reference/external_api.html)

#### Per database¶

To add an API key to a **single** database, connect to the database, enable the [developer mode](../../../general/developer_mode.html#developer-mode), click on the user menu, and then My Profile / Preferences. Under the Account Security tab, click on New API Key, confirm your password, give a descriptive name to your new key, and copy the API key.

Vedi anche

[API Keys](../../../../developer/reference/external_api.html#api-external-api-keys)

#### For all databases (fiduciaries)¶

To add an API key to **all** databases managed by a single user at the same time **(the easiest method for fiduciaries)** , navigate to [Odoo’s website](https://www.odoo.com/) and sign in with your administrator account. Next, open [your account security settings in developer mode](https://www.odoo.com/my/security?debug=1), click on New API Key, confirm your password, give a descriptive name to your new key, and copy the new API key.

Suggerimento

Open the [database manager](https://www.odoo.com/my/databases) to view all databases that will be linked to the single API key.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/reporting/silverfin.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customize.html "Custom reports") |
  * [precedente](data_inalterability.html "Data inalterability check report") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Silverfin integration


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