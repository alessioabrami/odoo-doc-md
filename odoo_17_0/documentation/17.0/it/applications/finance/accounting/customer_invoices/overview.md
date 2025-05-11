# Processi di fatturazione — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_addresses.html "Indirizzi di consegna e di fatturazione") |
  * [precedente](../customer_invoices.html "Fatture cliente") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Processi di fatturazione



# Processi di fatturazione¶

A seconda dell’azienda e dell’applicazione utilizzata, esistono diversi modi per automatizzare la creazione di fatture clienti in Odoo. Di solito, le bozze di fattura vengono create dal sistema (con le informazioni provenienti da altri documenti come l’ordine di vendita o i contratti) e il contabile deve solo convalidare le bozze di fattura e inviare le fatture in batch (per posta ordinaria o elettronica).

A seconda della tua attività, puoi optare per una delle seguenti modalità di creazione delle bozze di fattura:

## Vendite¶

### Ordine di vendita ‣ Fattura¶

Nella maggior parte delle aziende, gli addetti alle vendite creano preventivi che diventano ordini di vendita una volta convalidati. In seguito, vengono create delle bozze di fattura basate sull’ordine di vendita. Sono disponibili diverse opzioni come:

  * Fattura manuale: utilizza un pulsante sull’ordine di vendita per attivare la bozza di fattura

  * Fattura prima della consegna: fattura l’intero ordine prima di attivare l’ordine di consegna

  * Fattura basata sull’ordine di consegna: vedi sezione successiva




La fattura prima della consegna è solitamente utilizzata dall’applicazione E-commerce quando il cliente paga al momento dell’ordine e noi consegniamo successivamente. (prepagata)

Per la maggior parte degli altri casi d’uso, ti consigliamo di fatturare manualmente. Permette al venditore di attivare la fattura su richiesta con le seguenti opzioni: fatturare l’intero ordine, fatturare una percentuale (anticipo), fatturare alcune righe, fatturare un anticipo fisso.

Questo processo è valido sia per i servizi che per i prodotti fisici.

Vedi anche

  * [Fatture proforma](../../../sales/sales/invoicing/proforma.html)




### Ordine di vendita ‣ Ordine di consegna ‣ Fattura¶

I rivenditori e gli e-commerce di solito fatturano in base agli ordini di consegna, invece che in base all’ordine di vendita. Questo approccio è adatto alle aziende in cui le quantità consegnate possono differire da quelle ordinate: alimenti (fattura basata sui kg effettivi).

In questo modo, se consegni un ordine parziale, fatturerai solo ciò che hai realmente consegnato. Se si effettuano ordini arretrati (consegna parziale e il resto in un secondo momento), il cliente riceverà due fatture, una per ogni ordine di consegna.

Vedi anche

  * [Fatture basate su quantità ordinate o consegnate](../../../sales/sales/invoicing/invoicing_policy.html)




### Ordine e-commerce ‣ Fattura¶

Un ordine e-commerce attiverà anche la creazione dell’ordine quando sarà completamente pagato. Se si consente il pagamento degli ordini tramite assegno o bonifico bancario, Odoo crea solo un ordine e la fattura viene attivata una volta ricevuto il pagamento.

## Contratti¶

### Contratti regolari ‣ Fatture¶

Se si utilizzano i contratti, è possibile attivare la fatturazione in base al tempo e al materiale speso, alle spese o alle linee fisse di servizi/prodotti. Ogni mese, il venditore emette la fattura in base alle attività previste dal contratto.

Le attività possono essere:

  * prodotti/servizi fissi, provenienti da un ordine di vendita collegato a questo contratto

  * materiali acquistati (che verranno rifatturati)

  * tempo e materiale in base alle schede orarie o agli acquisti (subappalto)

  * spese come quelle di viaggio e alloggio che vengono rifatturate al cliente




È possibile fatturare alla fine del contratto o emettere fatture intermedie. Questo approccio è utilizzato dalle società di servizi che fatturano principalmente in base al tempo e al materiale. Le aziende di servizi che fatturano a prezzo fisso utilizzano un normale ordine di vendita.

Vedi anche

  * [Fatture basate su tempo e materiali](../../../sales/sales/invoicing/time_materials.html)

  * [Reinvoice expenses to customers](../../../sales/sales/invoicing/expense.html)

  * [Fatturare milestone di progetto](../../../sales/sales/invoicing/milestone.html)




### Contratti ricorrenti ‣ Fatture¶

Per gli abbonamenti, la fattura viene emessa periodicamente e automaticamente. La frequenza della fatturazione e i servizi/prodotti fatturati sono definiti nel contratto.

Vedi anche

  * [Abbonamenti](../../../sales/subscriptions.html)




## Altri¶

### Creare una fattura manualmente¶

Gli utenti possono anche creare le fatture manualmente senza utilizzare contratti od ordini di vendita. È un approccio consigliato se non si deve gestire il processo di vendita (preventivi) o la consegna dei prodotti o servizi.

Anche se la fattura viene generata da un ordine di vendita, in casi eccezionali potrebbe essere necessario creare le fatture manualmente:

  * se devi creare un rimborso

  * se devi applicare uno sconto

  * se devi modificare una fattura creata da un ordine di vendita

  * se devi fatturare qualcosa non collegato al tuo business principale




### Moduli specifici¶

È possibile genere fatture in bozza grazie ad alcuni moduli specifici:

  * **abbonamento** : fattura i membri ogni anno

  * **riparazioni** : fattura i servizi post vendita




### Risequenziare le fatture¶

Rimane la possibilità di sequenziare le fatture, ma con alcune limitazioni:

  1. La funzionalità non funziona quando le registrazioni sono precedenti a una data di blocco.

  2. La funzionalità non funziona se la sequenza non è coerente con il mese della registrazione.

  3. Non funziona se la sequenza porta a un duplicato.

  4. L’ordine della fattura rimane invariato.

  5. È utile per chi utilizza una numerazione di un altro software e vuole continuare l’anno in corso senza ricominciare dall’inizio.




### Digitalizzare le fatture con il riconoscimento ottico dei caratteri (OCR)¶

La **digitalizzazione delle fatture** è il processo di codifica automatica delle fatture cartacee tradizionali in moduli fattura della contabilità.

Odoo utilizza le tecnologie OCR e di intelligenza artificiale per riconoscere il contenuto dei documenti. I moduli per le fatture dei fornitori e dei clienti vengono creati e popolati automaticamente in base alle fatture scansionate.

Vedi anche

  * [AI-powered document digitization](../vendor_bills/invoice_digitization.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/overview.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_addresses.html "Indirizzi di consegna e di fatturazione") |
  * [precedente](../customer_invoices.html "Fatture cliente") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Processi di fatturazione


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