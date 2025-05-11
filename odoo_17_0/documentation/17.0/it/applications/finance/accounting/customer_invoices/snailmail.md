# Posta ordinaria — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epc_qr_code.html "Codici QR EPC") |
  * [precedente](sequence.html "Sequenza fattura") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Posta ordinaria



# Posta ordinaria¶

L’invio tramite posta ordinaria può essere una strategia efficace per catturare l’attenzione delle persone, soprattutto quando le loro caselle di posta elettronica sono sovraccariche. Con Odoo, hai la possibilità di inviare fatture e resoconti di follow-up per posta in tutto il mondo dal tuo database.

## Configurazione¶

Vai su Contabilità ‣ Configurazione ‣ Impostazioni ‣ Fatture cliente per attivare la Posta ordinaria.

Per renderla una funzione predefinita, seleziona Invia per posta nella sezione Opzioni di invio predefinite.

## Inviare fatture tramite posta¶

Apri la fattura, clicca su Invia e stampa e seleziona Invia per posta. Prima di inviare la lettera, accertati che l’indirizzo del cliente sia impostato correttamente, compreso il Paese.

Importante

Il documento deve rispettare le seguenti regole per superare la convalida prima di essere inviato:

  * I margini devono essere di **5 mm** su tutti i lati. Poiché Odoo forza i margini esterni riempiendoli di bianco prima dell’invio tramite posta ordinaria, può accadere che il testo personalizzato dell’utente venga tagliato se sporge dai margini. Per controllare i margini, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode), apri le Impostazioni generali ‣ Funzioni tecniche ‣ sezione Rendiconti: formato carta.

  * Un quadrato di **15 mm per 15 mm** nell’angolo in basso a sinistra deve rimanere libero.

  * L’area del francobollo deve essere chiara ([`scarica il modello PDF`](../../../../_downloads/5b14d01e129cc51a32303602599b291f/snailmail-template.pdf) per maggiori dettagli).

  * Pingen (il fornitore di servizi di Odoo per posta ordinaria) analizza l’area per elaborare l’indirizzo, quindi se qualcosa viene scritto al di fuori dell’area, non viene conteggiato come parte dell’indirizzo.




## Tariffazione¶

La posta ordinaria è un servizio di [Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html) che richiede l’utilizzo di timbri prepagati (=crediti) per funzionare. L’invio di un documento equivale all’utilizzo di un timbro.

Per comprare dei timbri, apri l’app Contabilità ‣ Configurazione ‣ Impostazioni ‣ Fatture cliente: posta ordinaria, fai clic su Compra crediti o vai su Impostazioni ‣ Acquisti In-App: Odoo IAP, e fai clic su Mostra i miei servizi.

Vedi anche

[Informativa sulla privacy IAP di Odoo](https://iap.odoo.com/privacy#header_4)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/snailmail.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](epc_qr_code.html "Codici QR EPC") |
  * [precedente](sequence.html "Sequenza fattura") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Posta ordinaria


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