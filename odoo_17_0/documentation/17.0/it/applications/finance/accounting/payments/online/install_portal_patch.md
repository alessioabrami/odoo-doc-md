# Install the patch to disable online invoice payment — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../checks.html "Controlli") |
  * [precedente](../online.html "Online payments") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Pagamenti](../../payments.html) »
  * [Online payments](../online.html) »
  * Install the patch to disable online invoice payment



# Install the patch to disable online invoice payment¶

Following recent changes in Odoo 16, you might be warned that disabling the Invoice Online Payment setting will uninstall modules. If you want to disable the feature without uninstalling modules, follow the steps below to install the module **Payment - Account / Invoice Online Payment Patch**.

Nota

If your Odoo database is created after the module **Payment - Account / Invoice Online Payment Patch** was released, you don’t have anything to do.

To check if the module is already installed, go to Apps, remove the `Apps` filter, and search for `account_payment`. If the module **Payment - Account / Invoice Online Payment Patch** is present and marked as installed, your Odoo database is already up-to-date and you are able to disable the feature without side-effect.

## Update Odoo to the latest release¶

The possibility to disable the Invoice Online Payment setting without side-effect is made available through a new Odoo module; to be able to install it, you must make sure that your Odoo source code is up-to-date.

If you use Odoo on Odoo.com or Odoo.sh platform, your code is already up-to-date and you can proceed to the next step.

If you use Odoo with an on-premise setup or through a partner, you must update your installation as detailed in [this documentation page](../../../../../administration/on_premise/update.html), or by contacting your integrating partner.

## Update the list of available modules¶

New modules must be _discovered_ by your Odoo instance to be available in the **Apps** menu.

To do so, activate the [developer mode](../../../../general/developer_mode.html#developer-mode), and go to Apps ‣ Update Apps List. A wizard will ask for confirmation.

## Install the module Invoice Online Payment Patch¶

Avvertimento

You should never install new modules in your production database without first testing them in a duplicate or staging environment. For Odoo.com customers, a duplicate database can be created from the database management page. For Odoo.sh users, you should use a staging or duplicate database. For on-premise users, you should use a staging environment—contact your integrating partner for more information regarding how to test a new module in your particular setup.

The module should now be available in your Apps menu. Remove the `Apps` filter and search for `account_payment`; the module Payment - Account / Invoice Online Payment Patch should be available for installation. If you cannot find the module after having updated the list of available modules, it means your Odoo source code is not up-to-date; refer to step one of this page.

Once the module is installed, disabling the feature will work as intended and will not ask you to uninstall installed applications or modules.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/online/install_portal_patch.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../checks.html "Controlli") |
  * [precedente](../online.html "Online payments") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Pagamenti](../../payments.html) »
  * [Online payments](../online.html) »
  * Install the patch to disable online invoice payment


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