# AI-powered document digitization — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](assets.html "Non-current assets and fixed assets") |
  * [precedente](../vendor_bills.html "Fatture fornitore") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * AI-powered document digitization



# AI-powered document digitization¶

**Invoice digitization** is the process of converting paper documents into vendor bill and customer invoice forms in your accounting.

Odoo uses OCR and artificial intelligence technologies to recognize the content of the documents. Vendor bill and customer invoice forms are automatically created and populated based on the scanned invoices.

Vedi anche

  * [Test Odoo’s invoice digitization](https://www.odoo.com/app/invoice-automation)

  * [Odoo Tutorials: Vendor Bill Digitization](https://www.odoo.com/slides/slide/vendor-bill-digitization-7065)




## Configurazione¶

In Accounting ‣ Configuration ‣ Settings ‣ Digitization, check the box Document Digitization and choose whether Vendor Bills and Customer Invoices (this includes customer credit notes) should be processed automatically or on demand.

If you enable the Single Invoice Line Per Tax option, only one line is created per tax in the new bill, regardless of the number of lines on the invoice.

## Invoice upload¶

### Upload invoices manually¶

From the Accounting Dashboard, click on the Upload button of your vendor bills journal. Alternatively, go to Accounting ‣ Customers ‣ Invoices or Accounting ‣ Vendors ‣ Bills and select Upload.

### Upload invoices using an email alias¶

You can configure your connected scanner to send scanned documents to an email alias. Emails sent to these aliases are converted into new draft customer invoices or vendor bills.

You can modify the email alias of a journal. To do so, go to the Settings app. Under General Settings: Discuss, enable Custom Email Servers, add an Alias Domain, and Save.

The email alias is now available in the Advanced Settings tab of the journal. Emails sent to this address will be converted automatically into new invoices or bills.

Nota

If you use the [Documents](../../../productivity/documents.html) app, you can automatically send your scanned invoices to the Finance workspace (e.g., `inbox-financial@example.odoo.com`).

The default email aliases `vendor-bills@` and `customer-invoices@` followed by the Alias Domain you set are automatically created for the Vendor Bills and Customer Invoices journals, respectively. Emails sent to these addresses are converted automatically into new invoices or bills.

To change a default email alias, go to Accounting ‣ Configuration ‣ Accounting: Journals. Select the journal you want to edit, click on the Advanced Settings tab, and edit the `Email Alias`.

## Invoice digitization¶

According to your settings, the document is either processed automatically, or you need to click on Send for digitization to do it manually.

Once the data is extracted from the PDF, you can correct it if necessary by clicking on the respective tags (available in Edit mode) and selecting the proper information instead.

## Data recognition with AI¶

It is essential to review and correct (if needed) the information uploaded during digitization. Then, you have to post the document by clicking on Confirm. In this manner, the AI learns, and the system identifies the correct data for future digitizations.

## Tariffazione¶

The **invoice digitization** is an In-App Purchase (IAP) service that requires prepaid credits to work. Digitizing one document consumes one credit.

To buy credits, go to Accounting ‣ Configuration ‣ Settings ‣ Digitization and click on Buy credits, or go to Settings ‣ Odoo IAP and click on View My Services.

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima di scegliere se acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un “app gratuita.

Vedi anche

  * [Our Privacy Policy](https://iap.odoo.com/privacy#header_6)

  * [Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/vendor_bills/invoice_digitization.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](assets.html "Non-current assets and fixed assets") |
  * [precedente](../vendor_bills.html "Fatture fornitore") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * AI-powered document digitization


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
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto