# Note di credito e rimborsi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](cash_discounts.html "Sconti di cassa e riduzioni fiscali") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Note di credito e rimborsi



# Note di credito e rimborsi¶

Una nota di credito/debito è un documento inviato a un cliente per informarlo che gli è stato _accreditato/addebitato_ un determinato importo.

Diversi sono i casi d’uso che possono portare alla creazione di una nota di credito:

>   * un errore in una fattura
> 
>   * un reso di beni o un rifiuto dei servizi
> 
>   * i beni consegnati sono danneggiati.
> 
> 


Le note di debito sono meno comuni, ma sono utilizzate con maggior frequenza per tenere traccia dei debiti dovuti dai clienti o dai fornitori a causa di modifiche alle fatture confermate dei clienti o alle fatture dei fornitori.

Nota

L’emissione di una nota di credito/debito è l’unico metodo legale per annullare, rimborsare o modificare una fattura convalidata. Assicurati di **registrare il pagamento** se il cliente ha rimborsato il venditore e/o convalida il [reso](../../../sales/sales/products_prices/returns.html) se si tratta di un prodotto stoccabile.

## Creare una nota di credito cliente¶

Nella maggior parte dei casi, le note di credito vengono create direttamente dalle fatture corrispondenti. Per farlo, apri l’app Contabilità ‣ Clienti ‣ Fatture, apri la Fattura corrispondente e fai clic su Nota di credito.

Nella finestra Nota di credito, inserisci il Ragione visualizzata nella nota di credito e aggiorna il Registro e la Data di storno se necessario. Esistono due opzioni:

  * fai clic su Storna per aprire una bozza di nota di credito con i dettagli esatti della fattura originale. Aggiorna il Prodotto e la Quantità e fai clic su Conferma. Quest’opzione ti permette di effettuare rimborsi parziali o modificare la nota di credito.

  * Fai clic su Storna e crea fattura per creare una nota di credito, convalidarla automaticamente e riconciliarla con la fattura correlata per poi aprire una nuova bozza di fattura precompilata con i dettagli esatti della fattura originale.




Per creare una nota di credito da zero, apri il modulo Contabilità ‣ Clienti ‣ Note di credito e fai clic su Nuova. Completare una nota di credito è come completare una [fattura](../customer_invoices.html#accounting-invoice-creation).

Nota

La sequenza di una nota di credito inizia con `R` ed è seguita dal relativo numero di documento (ad es., RINV/2025/0004 è associata alla fattura INV/2025/0004).

## Creare una nota di debito cliente¶

Per creare una nota di debito, vai su Contabilità ‣ Clienti ‣ Fatture e segui questi step:

  1. Seleziona le fatture desiderate, fai clic su __ Azioni e seleziona Crea nota di debito.

  2. Nella finestra Crea nota di debito, inserisci la Ragione e aggiorna i campi Usa registro specifico e Data nota di debito se necessario.

  3. Attiva l’opzione Copia righe per copiare le righe della fattura e fai clic su Crea nota di debito.

  4. Nella nota di debito, aggiorna il Prodotto e la Quantità e fai clic su Conferma.




Suggerimento

Per creare una nota di debito dalla vista modulo della fattura, fai clic sull’icona __(ingranaggio) e seleziona Nota di debito.

## Registrare un rimborso fornitore¶

I rimborsi dei fornitori o le note di credito dei fornitori vengono registrate allo stesso modo delle note di credito:

Per registrare un rimborso fornitore o una nota di credito fornitore direttamente dalla fattura fornitore corrispondente, vai su Contabilità ‣ Fornitori ‣ Fatture fornitore, apri la fattura corrispondente e fai clic su Nota di credito.

Per registrarla da zero, vai su Contabilità ‣ Fornitori ‣ Rimborso e fai clic su Nuovo.

## Registrare una nota di debito fornitore¶

Le note di debito dei fornitori vengono registrate allo stesso modo delle note di debito emesse per i clienti.

Per registrare una nota di debito, vai su Contabilità ‣ Fornitori ‣ Fatture fornitore e seleziona le fatture desiderate. Fai clic su __ Azioni e seleziona Crea nota di debito.

Suggerimento

Per creare una nota di debito dalla vista modulo della fattura fornitore, fai clic sull’icona __(ingranaggio) e seleziona Nota di debito.

## Registrazioni contabili¶

La creazione di una nota di credito/debito da una fattura cliente/fornitore genera uno **storno** che annulla le registrazioni contabili dalla fattura originale.

Example

La registrazione contabile di una fattura:

La registrazione contabile della nota di credito generata per stornare la fattura originale di cui sopra:

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/credit_notes.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](cash_discounts.html "Sconti di cassa e riduzioni fiscali") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Note di credito e rimborsi


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