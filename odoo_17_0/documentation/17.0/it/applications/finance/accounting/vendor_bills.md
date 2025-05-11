# Fatture fornitore — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_bills/invoice_digitization.html "AI-powered document digitization") |
  * [precedente](customer_invoices/incoterms.html "Termini di resa") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture fornitore



# Fatture fornitore¶

Vendor bills can be registered either **manually** or **automatically** in Odoo. The Aged Payable report provides an overview of all outstanding bills to help ensure timely payment of the correct amounts.

Vedi anche

  * Tutorial [Registering a vendor bill](https://www.odoo.com/slides/slide/register-a-vendor-bill-6582)

  * [Manage vendor bills](../../inventory_and_mrp/purchase/manage_deals/manage.html)




## Bill creation¶

### Manuale¶

To create a vendor bill manually, go to Accounting ‣ Vendors ‣ Bills and click New.

Suggerimento

Alternatively, it is possible to create a vendor bill from the Accounting dashboard:

  * either click Create Manually on the Vendor Bills journal;

  * or click the __(vertical ellipsis) icon of the Vendor Bills journal, then Bill under the New section.




### Automaticamente¶

Vendor bills can be automatically created by **sending an email** to an [email alias](vendor_bills/invoice_digitization.html#invoice-digitization-email-alias) associated with the purchase journal, or by **uploading a PDF** in Accounting ‣ Vendors ‣ Bills and then clicking Upload.

Nota

  * Once the bill is uploaded, the PDF document appears on the right side of the screen, making it easy to fill in the bill information.

  * Bills can be [digitized](vendor_bills/invoice_digitization.html) for automatic completion.

  * Services such as digitizing scanned or PDF vendor bills in Odoo require [In-App Purchase (IAP)](../../essentials/in_app_purchase.html) credit or tokens.




## Bill completion¶

Whether the bill is created manually or automatically, make sure the following fields are appropriately completed:

  * Vendor: Odoo automatically fills in some information based on the information on the vendor’s contact record as well as previous purchase orders and bills.

  * Bill Reference: Add the sales order reference provided by the vendor. This field is used to [match](payments.html#accounting-payments-payments-matching) the products when they are received.

  * Auto-Complete: Select a past bill/purchase order to complete the document automatically. The Vendor field should be completed before completing this field.

  * Bill Date: Select the document’s issuance date.

  * Accounting Date: Update the document’s accounting registration date if needed.

  * Payment Reference: The Memo field automatically includes the payment reference once the payment is registered.

  * Recipient Bank: Indicates the account number to which the payment will be made. This field is required when paying via batch payment files (such as [NACHA](../fiscal_localizations/united_states.html#l10n-us-ach-electronic-transfers) and [SEPA](payments/pay_sepa.html)).

  * Due Date or Payment Terms must be specified for the bill payment.

  * Journal: Select which journal should record the bill and in which [currency](get_started/multi_currency.html).




Nota

Multiple bills for the same purchase order may be issued if the vendor is on back-order and sends invoices as products are shipped or if the vendor sends partial bills or requests a deposit. In this case, multiple bills may have the same Bill Reference.

## Bill confirmation¶

Click Confirm when the document is completed. The status changes to Posted, and a journal entry is generated based on the vendor bill information. On confirmation, Odoo assigns each vendor bill a unique number from a defined [sequence](vendor_bills/sequence.html).

Nota

Once confirmed, a vendor bill can no longer be updated. Click Reset to draft if changes are required.

## Pagamento e riconciliazione¶

To register a payment, click on Register Payment. In the Register Payment window, select the Journal, the Payment Method, the Amount, and the Currency.

When the Amount paid is less than the total remaining amount on the vendor bill, the payment is [partial](payments.html#accounting-payments-partial-payment), and the Payment Difference field displays the outstanding balance.

The Memo field is filled automatically if the Payment Reference has been set correctly on the vendor bill. If the field is empty, select the vendor invoice number as a reference.

Then click Create payment. An In Payment/Partial banner appears on the bill until it is [reconciled](bank/reconciliation.html) and its status updates to Paid.

Vedi anche

  * [Pagamenti](payments.html)

  * [Riconciliazione bancaria](bank/reconciliation.html)




## Aged payable report¶

To get an overview of the open vendor bills and their due dates, go to Accounting ‣ Reporting ‣ Aged payable.

Click the __(right arrow) icon next to a vendor to view the details of all their outstanding bills, including the due dates and amounts.

Nota

Click PDF or XLSX to generate a PDF or XLSX file, respectively.

  * [AI-powered document digitization](vendor_bills/invoice_digitization.html)
  * [Non-current assets and fixed assets](vendor_bills/assets.html)
  * [Deferred expenses](vendor_bills/deferred_expenses.html)
  * [Vendor bill sequence](vendor_bills/sequence.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/vendor_bills.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vendor_bills/invoice_digitization.html "AI-powered document digitization") |
  * [precedente](customer_invoices/incoterms.html "Termini di resa") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture fornitore


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