# Codici QR EPC — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](incoterms.html "Termini di resa") |
  * [precedente](snailmail.html "Posta ordinaria") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Codici QR EPC



# Codici QR EPC¶

I codici a risposta rapida del Consiglio europeo per i pagamenti, o **codici QR EPC** , sono codici a barre bidimensionali che i clienti possono scansionare con le loro **applicazioni di mobile banking** per effettuare un **bonifico SEPA (SCT)** e pagare istantaneamente le fatture.

Oltre a garantire facilità d’uso e velocità, riduce notevolmente gli errori di digitazione che potrebbero causare problemi di pagamento.

Nota

Questa funzione è disponibile solo per le aziende di alcuni Paesi europei come Austria, Belgio, Finlandia, Germania e Paesi Bassi.

Vedi anche

  * [Conti bancari e di cassa](../bank.html)

  * [Odoo Academy: codici QR Code su fatture per clienti europei](https://www.odoo.com/r/VuU)




## Configurazione¶

Apri l’app Contabilità ‣ Configurazione ‣ Impostazioni e attiva la funzionalità Codici QR nella sezione Pagamenti cliente.

### Configurare il registro del tuo conto bancario¶

Assicurati che il tuo Conto bancario sia correttamente configurato in Odoo con IBAN e BIC.

Per farlo, vai su Contabilità ‣ Configurazione ‣ Registri, apri il tuo registro bancario, inserisci il Numero di conto e la Banca nella colonna Numero conto bancario.

## Emettere fatture con codici QR EPC¶

I codici QR EPC vengono aggiunti automaticamente alle fatture. I clienti la cui banca supporta i pagamenti tramite codici QR EPC potranno scansionare il codice e pagare la fattura.

Apri il modulo Contabilità ‣ Clienti ‣ Fatture e crea una nuova fattura.

Prima di registrarla, apri la scheda Altre informazioni. Odoo riempie automaticamente il campo Banca beneficiario con il tuo IBAN.

Nota

Nella scheda Altre informazioni, il conto indicato nel campo Banca beneficiario viene utilizzato per ricevere i pagamenti del cliente. Odoo popola automaticamente il campo con il tuo IBAN per impostazione predefinita e lo usa per generare il codice QR EPC.

Quando la fattura viene stampata o visualizzata in anteprima, il codice QR viene incluso in fondo.

Suggerimento

Se vuoi emettere una fattura senza codice QR EPC, elimina l’IBAN indicato nel campo Banca destinatario, nella sezione Altre informazioni della fattura.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/epc_qr_code.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](incoterms.html "Termini di resa") |
  * [precedente](snailmail.html "Posta ordinaria") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Codici QR EPC


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