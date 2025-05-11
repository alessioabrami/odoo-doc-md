# Pay with SEPA — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_checks.html "Pay by checks") |
  * [precedente](internal_transfers.html "Trasferimenti interni") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pay with SEPA



# Pay with SEPA¶

SEPA, the Single Euro Payments Area, is a payment-integration initiative of the European Union to simplify bank transfers denominated in euros. SEPA allows you to send payment orders to your bank to automate bank wire transfers.

SEPA is supported by the banks of the 27 EU member states, as well as:

EFTA countries:

  * Iceland;

  * Liechtenstein;

  * Norvegia;

  * Switzerland.




Non-EEA SEPA countries:

  * Andorra;

  * Monaco;

  * San Marino;

  * United Kingdom;

  * Vatican City State.




Non-EEA territories:

  * Saint-Pierre-et-Miquelon;

  * Guernsey;

  * Jersey;

  * Isle of Man.




When paying a bill in Odoo, you can select SEPA mandates as a payment option. At the end of the day, you can generate the SEPA file containing all bank wire transfers and upload it to your online banking interface to process the payments.

By default, the file follows the SEPA Credit Transfer **“pain.001.001.03”** specifications. This is a well-defined standard among banks. However, for Swiss and German companies, other formats are used **“pain.001.001.03.ch.02”** for Switzerland and **“pain.001.003.03”** for Germany.

Once the payments are processed by your bank, you can directly import the account statement in Odoo. The bank reconciliation process will seamlessly match the SEPA orders you sent to your bank with actual bank statements.

## Configurazione¶

### Activate SEPA Credit Transfer (SCT)¶

To pay suppliers with SEPA, you must activate the **SEPA Credit Transfer** setting. To do so, go to Accounting ‣ Configuration ‣ Settings ‣ Vendor Payments: SEPA Credit Transfer (SCT). By activating the setting and filling out your company data, you will be able to use the SCT option when paying your vendor.

Nota

According to the localization package installed, the **SEPA Direct Debit** and **SEPA Credit Transfer** modules may be installed by default. If not, they need to be [installed](../../../general/apps_modules.html#general-install).

### Activate SEPA payment methods on banks¶

From the accounting dashboard, click on the drop-down menu (⋮) on your bank journal and select Configuration. Click the Outgoing Payments tab, and, if not already present, add SEPA Credit Transfer under Payment Method.

Make sure to specify the IBAN account number (domestic account numbers do not work with SEPA) and the BIC (bank identifier code) in the Journal Entries tab.

### Registering payments¶

You can register any vendor payments made with SEPA. To do so, go to Accounting ‣ Vendors ‣ Payments. When creating your payment, select SEPA Credit Transfer as the Payment Method.

The first time you pay a vendor with SEPA, you have to fill in the Recipient Bank Account field with the bank name, IBAN, and BIC (Bank Identifier Code). Odoo automatically verifies if the IBAN format is respected.

For future payments to this vendor, Odoo will automatically suggest you the bank account, but it remains possible to select a new one.

Once your payment is registered, do not forget to confirm it. You can also pay vendor bills from the bill directly using the Register Payment button at the top of a vendor bill. The form is the same, but the payment is directly linked to the bill and will be automatically reconciled with it.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/payments/pay_sepa.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pay_checks.html "Pay by checks") |
  * [precedente](internal_transfers.html "Trasferimenti interni") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Pagamenti](../payments.html) »
  * Pay with SEPA


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