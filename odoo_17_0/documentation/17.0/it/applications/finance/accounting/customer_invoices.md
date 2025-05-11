# Fatture cliente — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_invoices/overview.html "Processi di fatturazione") |
  * [precedente](taxes/B2B_B2C.html "Tariffe B2B \(imposte escluse\) e B2C \(imposte incluse\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture cliente



# Fatture cliente¶

Una fattura al cliente è un documento emesso da un’azienda per i prodotti e/o i servizi venduti a un cliente. Registra i crediti nel momento in cui vengono inviati ai clienti. Le fatture dei clienti possono includere gli importi dovuti per i beni e/o i servizi forniti, le imposte di vendita applicabili, le spese di spedizione e di gestione e altri oneri. Odoo supporta diversi flussi di lavoro per la fatturazione e il pagamento.

Vedi anche

[Processi di fatturazione](customer_invoices/overview.html)

Dalla bozza di fattura al resoconto di profitti e perdite, il processo prevede diverse fasi una volta che le merci (o i servizi) sono stati ordinati/spediti (o resi) a un cliente, a seconda della politica di fatturazione:

  * Creazione fattura

  * Conferma fattura

  * Invio fattura

  * Pagamento e riconciliazione

  * Controllo pagamenti

  * Rendiconto




## Creazione fattura¶

Le fatture in bozza possono essere create direttamente da documenti come ordini di vendita o di acquisto oppure manualmente dal registro Fatture clienti nella dashboard della contabilità.

Una fattura deve contenere le informazioni necessarie per consentire al cliente di pagare tempestivamente i beni e i servizi offerti. Assicurati che i seguenti campi siano adeguatamente compilati:

  * Cliente: quando viene selezionato un cliente, Odoo estrae automaticamente le informazioni dal record del cliente, come l’indirizzo della fattura, i [termini di pagamento preferiti](customer_invoices/payment_terms.html), [posizioni di bilancio](taxes/fiscal_positions.html), conto di credito e altro per poi aggiungerle alla fattura. Per modificare i valori per questa specifica fattura, modificali direttamente sulla fattura stessa. Per modificarli per le fatture future, modifica i valori nel record del contatto.

  * Data fattura: se non viene impostato manualmente, questo campo viene impostato automaticamente come data corrente al momento della conferma.

  * Scadenza oppure [termini di pagamento](customer_invoices/payment_terms.html): per specificare quando il cliente deve pagare la fattura.

  * Journal: Is automatically set and can be changed if needed.

  * [Currency](get_started/multi_currency.html)

  * Product: Click Add a line to add a product.

  * Quantità

  * Prezzo

  * [Imposte](taxes.html) (se applicabile)




Suggerimento

Per visualizzare l’importo totale della fattura in parole, apri l’applicazione Contabilità ‣ Configurazione ‣ Impostazioni e attiva l’opzione Importo totale della fattura in lettere.

The Journal Items tab displays the accounting entries created. Additional invoice information such as the Customer Reference, [Fiscal Positions](taxes/fiscal_positions.html), [Incoterms](customer_invoices/incoterms.html), and more can be added or modified in the Other Info tab.

Nota

Inizialmente, Odoo crea le fatture nello stato di Bozza. Le fatture in bozza non hanno un impatto sulla contabilità fino alla loro conferma.

Vedi anche

[Fatture proforma](../../sales/sales/invoicing/proforma.html)

## Conferma fattura¶

Click Confirm when the document is completed. The document’s status changes to Posted, and a journal entry is generated based on the invoice configuration. On confirmation, Odoo assigns each invoice a unique number from a defined [sequence](customer_invoices/sequence.html).

Nota

  * Una volta confermata, una fattura non può più essere aggiornata. Se necessario, fai clic su Reimposta a bozza se hai bisogno di modificarla.

  * If required, invoices and other journal entries can be locked once posted using the [Lock posted entries with hash](reporting/data_inalterability.html#data-inalterability-lock) feature.




## Invio fattura¶

To send the invoice to the customer, click Send & Print. A Configure your document layout pop-up window will appear if a [default invoice layout](../../studio/pdf_reports.html#studio-pdf-reports-default-layout) hasn’t been customized. Then, select how to send this invoice to the customer in the Send window.

To send and print multiple invoices, go to Accounting ‣ Customers ‣ Invoices and select them. Then click the __ Actions menu and select Send & Print. A banner will appear on the selected invoices to indicate they are part of an ongoing send and print batch. This helps prevent the process from being triggered manually again, as it may take some time to complete for exceptionally large batches.

## Pagamento e riconciliazione¶

In Odoo, una fattura è considerata Pagata quando la registrazione contabile associata è stata riconciliata con una transazione bancaria corrispondente.

Vedi anche

  * [Pagamenti](payments.html)

  * [Riconciliazione bancaria](bank/reconciliation.html)




## Controllo pagamenti¶

Le [azioni di follow-up](payments/follow_up.html) di Odoo aiutano le aziende a seguire le fatture dei clienti. È possibile impostare diverse azioni per ricordare ai clienti di pagare le loro fatture in sospeso, a seconda dell’entità del ritardo. Queste azioni sono raggruppate in livelli di follow-up che si attivano quando una fattura è in ritardo di un certo numero di giorni. Se ci sono più fatture scadute per lo stesso cliente, le azioni vengono eseguite sulla fattura più scaduta.

## Rendiconto¶

### Rendiconti partner¶

#### Partitario clienti/fornitori¶

Il Partitario clienti/fornitori mostra il saldo di clienti e fornitori. Per accedervi, segui il menu Contabilità ‣ Rendicontazione ‣ Partitario clienti/fornitori.

#### Crediti esigibili¶

Per esaminare le fatture in sospeso dei clienti e le relative scadenze, utilizza il resoconto [Crediti esigibili](reporting.html#accounting-reporting-aged-receivable). Per accedervi, vai su Contabilità ‣ Rendicontazione ‣ Crediti esigibili.

#### Debiti scaduti¶

Per esaminare le fatture dei fornitori in sospeso e le relative scadenze, utilizza il resoconto [Debiti scaduti](reporting.html#accounting-reporting-aged-payable). Per accedervi, vai su Contabilità ‣ Rendicontazione ‣ Debiti scaduti.

### Conto economico¶

Il rendiconto relativo a [profitti e perdite](reporting.html#accounting-reporting-profit-and-loss) mostra i dettagli di spese ed entrate.

### Stato patrimoniale¶

Lo [stato patrimoniale](reporting.html#accounting-reporting-balance-sheet) riassume le attività, le passività e il patrimonio netto dell’azienda in un determinato momento.

  * [Processi di fatturazione](customer_invoices/overview.html)
  * [Indirizzi di consegna e di fatturazione](customer_invoices/customer_addresses.html)
  * [Termini di pagamento e piani di rateizzazione](customer_invoices/payment_terms.html)
  * [Termini e condizioni predefiniti](customer_invoices/terms_conditions.html)
  * [Sconti di cassa e riduzioni fiscali](customer_invoices/cash_discounts.html)
  * [Note di credito e rimborsi](customer_invoices/credit_notes.html)
  * [Arrotondamento di cassa](customer_invoices/cash_rounding.html)
  * [Risconti passivi](customer_invoices/deferred_revenues.html)
  * [Fatturazione elettronica (EDI)](customer_invoices/electronic_invoicing.html)
  * [Sequenza fattura](customer_invoices/sequence.html)
  * [Posta ordinaria](customer_invoices/snailmail.html)
  * [Codici QR EPC](customer_invoices/epc_qr_code.html)
  * [Termini di resa](customer_invoices/incoterms.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_invoices/overview.html "Processi di fatturazione") |
  * [precedente](taxes/B2B_B2C.html "Tariffe B2B \(imposte escluse\) e B2C \(imposte incluse\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Fatture cliente


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