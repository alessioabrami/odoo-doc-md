# Tax return (VAT declaration) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_carryover.html "Tax carryover") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Tax return (VAT declaration)



# Tax return (VAT declaration)¶

Companies with a registered VAT number must submit a **tax return** on a monthly or quarterly basis, depending on their turnover and the registration regulation. A tax return - or VAT return - gives the tax authorities information about the taxable transactions made by the company. The **output tax** is charged on the number of goods and services sold by a business, while the **input tax** is the tax added to the price when goods or services are purchased. Based on these values, the company can calculate the tax amount they have to pay or be refunded.

Nota

You can find additional information about VAT and its mechanism on this page from the European Commission: [«What is VAT?»](https://ec.europa.eu/taxation_customs/business/vat/what-is-vat_en).

## Prerequisiti¶

### Periodicità dichiarazione fiscale¶

The configuration of the **Tax Return Periodicity** allows Odoo to compute your tax return correctly and also to send you a reminder to never miss a tax return deadline.

To do so, go to Accounting ‣ Configuration ‣ Settings. Under the Tax Return Periodicity, you can set:

  * Periodicity: define here whether you submit your tax return on a monthly or quarterly basis;

  * Reminder: define when Odoo should remind you to submit your tax return;

  * Journal: select the journal in which to record the tax return.




Nota

This is usually configured during the [app’s initial set up](../get_started.html).

### Griglie imposta¶

Odoo generates tax reports based on the Tax Grids settings that are configured on your taxes. Therefore, it is crucial to make sure that all recorded transactions use the right taxes. You can see the Tax Grids by opening the Journal Items tab of any invoice and bill.

To configure your tax grids, go to Accounting ‣ Configuration ‣ Taxes, and open the tax you want to modify. There, you can edit your tax settings, along with the tax grids that are used to record invoices or credit notes.

Nota

Taxes and reports are usually already pre-configured in Odoo: a [fiscal localization package](../../fiscal_localizations.html#fiscal-localizations-packages) is installed according to the country you select at the creation of your database.

## Close a tax period¶

### Data chiusura fiscale¶

Any new transaction whose accounting date prior to the Tax Lock Date has its tax values moved to the next open tax period. This is useful to make sure that no change can be made to a report once its period is closed.

Therefore, we recommend locking your tax date before working on your Closing Journal Entry. This way, other users cannot modify or add transactions that would have an impact on the Closing Journal Entry, which can help you avoid some tax declaration errors.

To check the current Tax Lock Date, or to edit it, go to Accounting ‣ Accounting ‣ Actions: Lock Dates.

### Resoconto fiscale¶

Once all the transactions involving taxes have been posted for the period you want to report, open the Tax Report by going to Accounting ‣ Reporting ‣ Tax Report. Select the period you want to declare using the date filter to have an overview of the tax report. From the report, click PDF or XLSX to download the desired format of the tax report. To save the report to the Documents app, click the __( down arrow) icon, then click Save. Select the format to Export to, the Documents Name, the Folder to store it in, and add any Tags.

The report includes all the values to report to the tax authorities, along with the amount to be paid or refunded.

Nota

If you forgot to lock your tax date before clicking on Closing Journal Entry, then Odoo automatically locks your fiscal period on the same date as the accounting date of your entry. This safety mechanism can prevent some fiscal errors, but it is advised to lock your tax date manually before, as described above.

Vedi anche

  * [Imposte](../taxes.html)

  * [Esordiente](../get_started.html)

  * [Fiscal localizations](../../fiscal_localizations.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/reporting/tax_returns.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](tax_carryover.html "Tax carryover") |
  * [precedente](../reporting.html "Rendiconto") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Rendiconto](../reporting.html) »
  * Tax return (VAT declaration)


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