# Fatture cliente — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_invoices/overview.html "Processi di fatturazione") |
  * [precedente](taxes/B2B_B2C.html "Tariffe B2B \(imposte escluse\) e B2C \(imposte incluse\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
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

  * Registro: configurato automaticamente e modificabile se necessario.

  * [Valuta](get_started/multi_currency.html): se la valuta della fattura è diversa da quella dell’azienda, il tasso di cambio viene visualizzato automaticamente.




Nella scheda Righe fattura:

  * Prodotto: fai clic su Aggiungi riga, poi cerca e seleziona il prodotto.

  * Quantità

  * Prezzo

  * [Imposte](taxes.html) (se applicabile)




Per accedere al catalogo prodotto, fai clic su [Catalogo](../../inventory_and_mrp/inventory/warehouses_storage/inventory_management/product_catalog.html). Una volta selezionati prodotto e quantità, fai clic su Torna alla fattura per aprirla. Gli articoli selezionati dal catalogo appariranno nelle righe della fattura.

Suggerimento

Per visualizzare l’importo totale della fattura in parole, apri l’applicazione Contabilità ‣ Configurazione ‣ Impostazioni e attiva l’opzione Importo totale della fattura in lettere.

La scheda Movimenti contabili mostra le registrazioni contabili create. Informazioni aggiuntive sulla fattura come Riferimento cliente, Riferimento pagamento, [Posizioni di bilancio](taxes/fiscal_positions.html), [Temini di resa](customer_invoices/incoterms.html) possono essere aggiunte o modificate nella scheda Altre informazioni.

Nota

Inizialmente, Odoo crea le fatture nello stato di Bozza. Le fatture in bozza non hanno un impatto sulla contabilità fino alla loro conferma.

Vedi anche

[Fatture proforma](../../sales/sales/invoicing/proforma.html)

## Conferma fattura¶

Fai clic su Conferma quando la fattura è completata. Lo stato della fattura passa a Confermata e viene generata una registrazione in base alle impostazioni della fattura stessa. Al momento della conferma, Odoo assegna a ogni fattura un numero unico da una [sequenza](customer_invoices/sequence.html) ben definita.

Nota

  * Una volta confermata, una fattura non può più essere aggiornata. Se necessario, fai clic su Reimposta a bozza se hai bisogno di modificarla.

  * Se richiesto, le fatture e altre registrazioni contabili possono essere bloccate una volta confermate usando la funzionalità [Proteggi registrazioni confermate con hash](reporting/data_inalterability.html#data-inalterability-restricted).




## Invio fattura¶

Per configurare un metodo preferito per l’invio delle fatture a un cliente, apri il modulo Contabilità ‣ Clienti ‣ Clienti e seleziona il cliente. Nella scheda Contabilità del modulo di contatto, seleziona il metodo di invio della fattura preferito nella sezione Fatture cliente.

Nota

L’invio di lettere in Odoo richiede crediti o token per [Acquisti integrati (IAP)](../../essentials/in_app_purchase.html).

Per inviare la fattura al cliente, torna al record della fattura e segui i passaggi:

  1. fai clic su Stampa e invia

  2. Se non hai ancora personalizzato la [struttura predefinita delle fatture](../../studio/pdf_reports.html#studio-pdf-reports-default-layout), apparirà la finestra pop-up Configurazione struttura del documento. Configura il layout e fai clic su Continua.

Nota

     * Il layout del documento può essere modificato in qualsiasi momento nelle impostazioni generali.

     * Per aggiungere un codice QR alla fattura per i pagamenti tramite app, attiva l’opzione codice QR nella finestra Configurazione struttura del documento. Per modificare l’opzione, accedi al menu Contabilità ‣ Configurazione ‣ Impostazioni, scorri fino alla sezione Pagamenti cliente e attiva/disattiva l’opzione Codici QR.

  3. Nella finestra Stampa e invia:

     * Se hai configurato un metodo di invio delle fatture preferito nel modulo di contatto, il metodo verrà selezionato per impostazione predefinita. Selezionane un altro se necessario.

     * Se non hai configurato un metodo di invio delle fatture preferito nel modulo di contatto, scegli il metodo da usare per inviare la fattura al cliente.

  4. Fai clic su Stampa e invia se hai selezionato l’opzione via e-mail oppure fai clic su Stampa.




### Invio di più fatture¶

Per inviare e stampare più fatture, apri il modulo Contabilità ‣ Clienti ‣ Fatture, selezionale nell’elenco Fatture e fai clic su Stampa e invia. La finestra Stampa e invia mostra i metodi di invio delle fatture selezionati in base al metodo preferito.

Alle fatture selezionate viene aggiunto un banner per indicare che fanno parte di un gruppo di invio e stampa in corso. In questo modo si evita che il processo venga nuovamente attivato manualmente, in quanto può richiedere del tempo per essere completato per gruppi eccezionalmente grandi.

Per verificare tutte le fatture che non sono state ancora inviate, apri l’app Contabilità ‣ Clienti ‣ Fatture. Nella vista elenco Fatture, fai clic sulla barra di ricerca e filtra per Non inviata.

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



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/customer_invoices.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](customer_invoices/overview.html "Processi di fatturazione") |
  * [precedente](taxes/B2B_B2C.html "Tariffe B2B \(imposte escluse\) e B2C \(imposte incluse\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
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
  *[FBM]: Fulfilled by Merchant
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
  *[POS]: point of sale
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
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record