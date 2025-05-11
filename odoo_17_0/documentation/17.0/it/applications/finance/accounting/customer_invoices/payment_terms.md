# Termini di pagamento e piani di rateizzazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](terms_conditions.html "Termini e condizioni predefiniti") |
  * [precedente](customer_addresses.html "Indirizzi di consegna e di fatturazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Termini di pagamento e piani di rateizzazione



# Termini di pagamento e piani di rateizzazione¶

I **termini di pagamento** specificano tutte le condizioni di pagamento di una vendita per garantire che i clienti paghino le loro fatture in modo corretto e puntuale.

I termini di pagamento sono generalmente definiti su documenti quali ordini di vendita, fatture dei clienti e fatture dei fornitori. I termini di pagamento riguardano:

  * data/date di scadenza

  * sconti per pagamento anticipato

  * qualsiasi altra condizione relativa al pagamento




Un **piano di pagamento** consente ai clienti di pagare una fattura in parti, con gli importi e le date di pagamento definiti in anticipo dal venditore.

Example

Pagamento immediato
    

Il pagamento completo è dovuto il giorno dell’emissione della fattura.

15 giorni (o Net 15)
    

Il pagamento completo deve essere effettuato 15 giorni dopo la data della fattura.

21 MFI
    

Il pagamento completo deve essere effettuato entro il 21 del mese successivo alla data della fattura.

anticipo 30% data fattura fine mese
    

Il 30% è dovuto il giorno dell’emissione della fattura. Il saldo è dovuto alla fine del mese successivo.

2% 10, netto 30 EOM
    

Uno [sconto di cassa](cash_discounts.html) del 2% se il pagamento viene ricevuto nell’arco di dieci giorni. Altrimenti, il pagamento completo è dovuto alla fine del mese che segue la data di fattura.

Nota

  * Non bisogna confondere i termini di pagamento con [le fatture di acconto](../../../sales/sales/invoicing/down_payment.html). Se per un ordine specifico si emettono più fatture al cliente, non si tratta né di un termine di pagamento né di un piano di rateizzazione, ma di una politica di fatturazione.

  * Questa pagina parla della funzionalità _termini di pagamento_ e non dei [termini e condizioni](terms_conditions.html) che possono essere usati per dichiarare obbligazioni contrattuali riguardo l’utilizzo di contenuti, politiche di reso e altre che riguardano la vendita di beni e servizi.




Vedi anche

  * [Odoo tutorial: termini di pagamento](https://www.odoo.com/slides/slide/payment-terms-1679)

  * [Sconti di cassa e riduzioni fiscali](cash_discounts.html)




## Configurazione¶

Per creare nuovi termini di pagamento, segui questi step:

  1. Apri il modulo Contabilità ‣ Configurazione ‣ Termini di pagamento e fai clic su Nuovo.

  2. Inserisci un nome nel campo Termini di pagamento. Questo campo è il nome visualizzato sia internamente che sugli ordini di vendita.

  3. Spunta la casella Sconto anticipato e inserisci la percentuale di sconto, i giorni di sconto e la [riduzione fiscale](cash_discounts.html#cash-discounts-tax-reductions) nei rispettivi campi per aggiungere uno [sconto di cassa](cash_discounts.html), se desiderato.

  4. Nella sezione Termini di scadenza, aggiungi un insieme di regole (termini) per definire cosa bisogna pagare ed entro quale data. La definizione dei termini calcola automaticamente le date di scadenza dei pagamenti. Questo è particolarmente utile per gestire i **piani di rateizzazione** (termini di pagamento con più termini).

Per aggiungere un termine, fai clic su Aggiungi riga, stabilisci il valore e il tipo di sconto nei campi Dovuto e poi riempi i campi Dopo per determinare la data di scadenza.

  5. Inserisci il testo da mostrare sul documento (ordine di vendita, fattura, ecc.) nella casella di testo grigia, nella colonna Anteprima.

  6. Spunta la casella Mostra date versamento per visualizzare, se lo desideri, la ripartizione di ogni pagamento e la relativa data di scadenza nel rapporto di fatturazione.




Suggerimento

Al contrario, specifica un numero di giorni _prima della fine del mese_ , usa un valore negativo nel campo Dopo.

Per testare la corretta configurazione dei termini di pagamento, inserisci una data per la fattura nella riga Esempio per generare i pagamenti da ricevere con le rispettive date di scadenza utilizzando questi termini di pagamento.

Importante

I termini sono calcolati in ordine di scadenza.

Example

Nell’esempio seguente, il 30% è dovuto il giorno dell’emissione e il restante 70% è dovuto alla fine del mese successivo.

## Utilizzare i termini di pagamento¶

I termini di pagamento possono essere definiti utilizzando il campo Termini di pagamento su:

  * **Contatti:** per configurare automaticamente termini di pagamento predefiniti sui nuovi ordini di vendita, fatture cliente o fornitore di un contatto. È possibile modificarli dal modello del contatto, sotto la scheda Vendite e acquisti.

  * **Preventivi/ordini di vendita** : per impostare automaticamente termini di pagamento specifici su tutte le fatture generate da un preventivo o da un ordine di vendita.




I termini di pagamento possono essere stabiliti utilizzando il campo Data di scadenza con l’elenco a discesa dei Termini su:

  * **Fatture cliente** : per impostare termini di pagamento specifici su una fattura.

  * **Fatture fornitore:** per impostare termini di pagamento specifici su una fattura fornitore.




Suggerimento

L’impostazione dei termini di pagamento su una fattura di un fornitore è utile soprattutto per gestire le condizioni di un fornitore con più rate o sconti. Altrimenti, è sufficiente impostare manualmente la **data di scadenza**. Se i termini di pagamento sono già definiti, svuotare il campo per selezionare una data.

## Registrazioni contabili¶

Le fatture con termini di pagamento specifici generano diverse _registrazioni contabili_ , con un _movimento contabile_ per ogni _scadenza_ calcolata.

Questo rende più semplice attività di [follow-up](../payments/follow_up.html) e [riconciliazione](../bank/reconciliation.html) perché Odoo tiene in considerazione ogni data di scadenza e non solo la data di scadenza del saldo. Inoltre, aiuta a ottenere un [resoconto dei crediti esigibili](../customer_invoices.html#accounting-invoices-aging-report) accurato.

Example

In questo esempio, è stata emessa una fattura di 1000 dollari con i seguenti termini di pagamento: _il 30% è dovuto il giorno dell’emissione e il restante 70% è dovuto alla fine del mese successivo_.

Account | Data di scadenza | Dare | Avere  
---|---|---|---  
Conto di credito | 21 febbraio | 300 |   
Conto di credito | 31 marzo | 700 |   
Vendite prodotto |  |  | 1000  
  
I 1.000 $ addebitati al conto crediti sono suddivisi in due registrazioni distinte del registro. Entrambe hanno una propria data di scadenza.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/payment_terms.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](terms_conditions.html "Termini e condizioni predefiniti") |
  * [precedente](customer_addresses.html "Indirizzi di consegna e di fatturazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Termini di pagamento e piani di rateizzazione


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