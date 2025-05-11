# Conti bancari e di cassa — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank/bank_synchronization.html "Sincronizzazione bancaria") |
  * [precedente](payments/trusted_accounts.html "Trusted accounts \(send money\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Conti bancari e di cassa



# Conti bancari e di cassa¶

È possibile gestire tutti i conti bancari o di cassa di cui hai bisogno dal tuo database. Una configurazione appropriata permette di avere tutti i dati bancari aggiornati e pronti per la [riconciliazione](bank/reconciliation.html) con le registrazioni contabili.

In Odoo Accounting, ogni conto bancario ha un giornale dedicato, impostato per registrare tutte le voci in un conto dedicato. Sia il giornale che il conto vengono creati e configurati automaticamente ogni volta che si aggiunge un conto bancario.

Nota

I giornali e i conti di cassa devono essere configurati manualmente.

I giornali bancari sono visualizzati per impostazione predefinita nel Cruscotto contabile sotto forma di schede che includono pulsanti di azione.

## Gestire conti bancari e di cassa¶

### Collegare una banca per al sincronizzazione automatica¶

Per collegare un conto bancario al tuo database, vai su Contabilità ‣ Configurazione ‣ Aggiungi una banca: Conto, seleziona la tua banca dall’elenco, fai clic su Collega e segui le istruzioni.

Vedi anche

:doc:banca/sincronizzazione_bancaria

### Crea un conto bancario¶

Se il vostro istituto bancario non è disponibile in Odoo o se non volete collegare il vostro conto bancario al database, potete configurare il vostro conto bancario manualmente.

Per aggiungere manualmente un conto bancario, apri l’app Contabilità ‣ Configurazione ‣ Aggiungi un conto bancario, fai clic su Registra transazioni manualmente (in basso a destra), completa le informazioni relative alla banca e fai clic su Crea.

Nota

  * Odoo rileva automaticamente il tipo di conto bancario (ad esempio, l’IBAN) e abilita alcune funzioni di conseguenza.

  * È disponibile un giornale bancario predefinito che può essere utilizzato per configurare il tuo conto bancario andando su :menuselection:Contabilità –> Configurazione –> Contabilità: Giornali –> Banca. Aprilo e modifica i vari campi per adattarli alle informazioni del tuo conto bancario.




### Crea un giornale di cassa¶

Per creare un nuovo giornale di cassa, andare su Contabilità ‣ Configurazione ‣ Contabilità: Diari”, fare clic su :guilabel:`Crea e selezionare Cassa nel campo Tipo.

Per ulteriori informazioni sui campi delle informazioni contabili, leggi la sezione bank_accounts/configuration di questa pagina.

Nota

È disponibile un giornale di cassa predefinito che può essere utilizzato subito. È possibile esaminarlo andando su :menuselezione:`Contabilità --> Configurazione --> Contabilità: Giornali --> Cassa`.

### Modificare un giornale bancario o di cassa esistente¶

Per modificare un giornale bancario esistente, accedere a :menuselezione:`Contabilità –> Configurazione –> Contabilità: Giornali” e selezionare il giornale che si desidera modificare.

## Configurazione¶

È possibile modificare le informazioni contabili e il numero di conto bancario in base alle proprie esigenze.

Vedi anche

  * :doc:inizia/multi_valuta

  * banca/transazioni

  * [Configurazione bancaria](https://www.youtube.com/watch?v=tVhhXw-VnGE)




### Conto di sospensione¶

Le transazioni degli estratti conto bancari vengono registrate sul conto provvisorio finché non vengono riconciliate. In qualsiasi momento, il saldo del conto provvisorio nel libro mastro mostra il saldo delle transazioni non ancora riconciliate.

Nota

Quando effettui la riconciliazione di una transazione, la registrazione contabile viene modificata per sostituire il conto bancario provvisorio con il conto del movimento contabile con cui viene riconciliato. Di solito, si tratta di un conto ricevute in sospeso o conto pagamenti se la riconciliazione avviene con un pagamento registrato oppure il conto di debito o credito se la riconciliazione avviene direttamente con una fattura cliente/fornitore.

### Conto economico¶

Il Conto profitti viene utilizzato per registrare un profitto quando il saldo finale di una cassa differisce da quello calcolato dal sistema, mentre il Conto perdite viene utilizzato per registrare una perdita quando il saldo finale di una cassa differisce da quello calcolato dal sistema.

### Valuta¶

Puoi modificare la valuta utilizzata per inserire le transazioni.

Vedi anche

:doc:inizia/multi_valuta

### Numero di conto¶

Se hai bisogno di **modificare i dettagli del conto bancario** , fai clic sulla freccia link esterno accanto al tuo Numero di conto. Sulla pagina del conto, fai clic sulla freccia link esterno accanto alla tua Banca e aggiorna le informazioni. Questi dettagli vengono utilizzati al momento della registrazione dei pagamenti.

### Alimentazioni bancarie¶

I flussi bancari definiscono il modo di registrazione delle transazioni bancarie. Tre sono le opzioni disponibili:

  * Ancora non definito, da selezionare quando non si sa ancora se si intende sincronizzare il conto bancario con il database o meno.

  * Importazione (CAMT, CODA, CSV, OFX, QIF), che dovrebbe essere selezionato se vuoi importare gli estratti conto bancari e le transazioni in un formato diverso

  * Sincronizzazione bancaria automatica, da selezionare se la banca è sincronizzata con il database.




Vedi anche

  * :doc:banca/sincronizzazione_bancaria

  * banca/transazioni




## Conti in sospeso¶

Per impostazione predefinita, i pagamenti in Odoo non creano registrazioni contabili, ma possono essere facilmente configurati per creare registrazioni utilizzando **conti in sospeso**.

  * Un **conto ricevute in sospeso** è il conto in cui vengono registrati i pagamenti in entrata fino a quando non vengono collegati alle transazioni bancarie in entrata.

  * Un **conto ricevute in sospeso** è il conto in cui vengono registrati i pagamenti in uscita fino a quando non vengono collegati alle transazioni bancarie in uscita.




Di solito, questi conti sono di [tipo](get_started/chart_of_accounts.html#chart-of-account-type) Attività correnti e Passività correnti.

I pagamenti registrati in Odoo vengono registrati nei conti ricevute in sospeso o conti aperti finché non vengono riconciliati. In qualsiasi momento, il saldo del conto delle ricevute in sospeso nel libro mastro mostra il saldo dei pagamenti in entrata registrati che non sono ancora stati riconciliati, mentre il saldo del conto dei pagamenti in sospeso nel libro mastro mostra il saldo dei pagamenti in uscita registrati che non sono ancora stati riconciliati.

### Configurazione dei registri di banca e di cassa¶

Per configurare i pagamenti e creare registrazioni contabili, è necessario configurare conti in sospeso per i metodi di pagamento del registro. Puoi farlo per qualsiasi registro di [tipo](get_started/chart_of_accounts.html#chart-of-account-type) Banca o Cassa.

Per configurare i conti in sospeso per il registro di un metodo di pagamento, apri il modulo Contabilità ‣ Configurazione ‣ Registri e seleziona un registro di banca o di cassa. Nelle schede Pagamenti in entrata e Pagamenti in uscita, imposta Conti ricevute in sospeso e Conti pagamenti in sospeso per ogni metodo di pagamento per cui vuoi creare registrazioni contabili.

Nota

  * Se il conto principale del registro viene aggiunto come conto per le ricevute in sospeso o per i pagamenti in sospeso, quando viene registrato un pagamento, lo stato della fattura viene impostato direttamente su Pagato.

  * Se il conto delle ricevute in sospeso o dei pagamenti in sospeso per un metodo di pagamento non viene riempito, la registrazione di un pagamento con quel metodo specifico non creerà alcuna voce nel registro.




  * [Sincronizzazione bancaria](bank/bank_synchronization.html)
    * [Salt Edge](bank/bank_synchronization/saltedge.html)
    * [Ponto](bank/bank_synchronization/ponto.html)
    * [Abilitare la Banca](bank/bank_synchronization/enablebanking.html)
  * [Transazioni](bank/transactions.html)
  * [Riconciliazione bancaria](bank/reconciliation.html)
  * [Modelli di riconciliazione](bank/reconciliation_models.html)
  * [Trasferimenti interni](bank/internal_transfers.html)
  * [Gestire un conto bancario in una valuta straniera](bank/foreign_currency.html)
  * [Gestione dei prestiti](bank/loans.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/bank.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank/bank_synchronization.html "Sincronizzazione bancaria") |
  * [precedente](payments/trusted_accounts.html "Trusted accounts \(send money\)") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Conti bancari e di cassa


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