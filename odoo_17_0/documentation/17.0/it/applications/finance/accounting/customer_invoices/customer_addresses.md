# Indirizzi di consegna e di fatturazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_terms.html "Termini di pagamento e piani di rateizzazione") |
  * [precedente](overview.html "Processi di fatturazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Indirizzi di consegna e di fatturazione



# Indirizzi di consegna e di fatturazione¶

Spesso le aziende hanno più sedi ed è frequente che la fattura del cliente venga inviata a un indirizzo e la consegna a un altro. La funzione **Indirizzi cliente** di Odoo è stata progettata per gestire questo scenario, rendendo facile specificare quale indirizzo utilizzare per ogni caso.

Vedi anche

[Processi di fatturazione](overview.html)

## Configurazione¶

Per specificare gli indirizzi di fatturazione di consegna di un ordine di vendita, vai su Contabilità ‣ Configurazione ‣ Impostazioni. Nella sezione Fatture fornitore, attiva gli Indirizzi cliente e fai clic su Salva.

Sui preventivi e sugli ordini di vendita ora sono presenti i campi Indirizzo di fatturazione e Indirizzo di consegna. Se nel [record del contatto](../../../sales/sales/send_quotations/different_addresses.html#sales-send-quotations-contact-form-config) è presente un indirizzo di fatturazione o di consegna, per impostazione predefinita, il campo corrispondente utilizza quell’indirizzo ma è possibile utilizzare l’indirizzo di qualsiasi contatto.

Vedi anche

Per maggiori informazioni, consulta la documentazione [Configurazione di un modulo di contatto](../../../sales/sales/send_quotations/different_addresses.html#sales-send-quotations-contact-form-config).

## Fatturare e spedire a indirizzi diversi¶

Gli ordini di consegna e le distinte di consegna utilizzano l’indirizzo configurato come Indirizzo di consegna sull’ordine di vendita. Per impostazione predefinita, i resoconti sulle fatture mostrano sia l’indirizzo di spedizione che quello di fatturazione per garantire al cliente che la consegna sarà effettuata all’indirizzo corretto.

Anche le e-mail possono essere destinate a indirizzi diversi. Il preventivo e l’ordine di vendita vengono inviati all’indirizzo e-mail principale del contatto ma la fattura viene inviata all’indirizzo e-mail dell’indirizzo scelto come Indirizzo di fatturazione sull’ordine di vendita.

Nota

  * I resoconti, come la distinta di consegna e il rendiconto della fattura, possono essere [personalizzati utilizzando Studio](../../../studio/pdf_reports.html).

  * Se scegli l’opzione [Invia per posta](snailmail.html) quando fai clic su Invia e stampa, la fattura verrà inviata all’indirizzo di fatturazione.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/customer_addresses.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_terms.html "Termini di pagamento e piani di rateizzazione") |
  * [precedente](overview.html "Processi di fatturazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Indirizzi di consegna e di fatturazione


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