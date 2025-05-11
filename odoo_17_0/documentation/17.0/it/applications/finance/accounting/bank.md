# Conti bancari e di cassa — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank/bank_synchronization.html "Sincronizzazione bancaria") |
  * [precedente](payments/trusted_accounts.html "Trusted accounts \(send money\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Conti bancari e di cassa



# Conti bancari e di cassa¶

È possibile gestire tutti i conti bancari o di cassa necessari nel database. Configurarli bene permette di avere tutti i dati bancari aggiornati e pronti per la :doc:riconciliazione <banca/riconciliazione> con le voci del giornale.

In Odoo Accounting, ogni conto bancario ha un giornale dedicato, impostato per registrare tutte le voci in un conto dedicato. Sia il giornale che il conto vengono creati e configurati automaticamente ogni volta che si aggiunge un conto bancario.

Nota

I giornali e i conti di cassa devono essere configurati manualmente.

I giornali bancari sono visualizzati per impostazione predefinita nel Cruscotto contabile sotto forma di schede che includono pulsanti di azione.

## Gestire i conti bancari e di cassa¶

### Collegate la vostra banca per la sincronizzazione automatica¶

Per collegare il tuo conto bancario al tuo database, vai su :menuselection:Contabilità –> Configurazione –> Banche: Aggiungi un conto bancario, seleziona la tua banca nell’elenco, fai clic su :guilabel:Collega e segui le istruzioni.

Vedi anche

:doc:banca/sincronizzazione_bancaria

### Crea un conto bancario¶

Se il vostro istituto bancario non è disponibile in Odoo o se non volete collegare il vostro conto bancario al database, potete configurare il vostro conto bancario manualmente.

Per aggiungere manualmente un conto bancario, andare su Contabilità ‣ Configurazione ‣ Banche: Aggiungi un conto bancario, cliccare su Crea (in basso a destra) e compilare il modulo.

Nota

  * Odoo rileva automaticamente il tipo di conto bancario (ad esempio, l’IBAN) e abilita alcune funzioni di conseguenza.

  * È disponibile un giornale bancario predefinito che può essere utilizzato per configurare il tuo conto bancario andando su :menuselection:Contabilità –> Configurazione –> Contabilità: Giornali –> Banca. Aprilo e modifica i vari campi per adattarli alle informazioni del tuo conto bancario.




### Crea un giornale di cassa¶

Per creare un nuovo giornale di cassa, andare su Contabilità ‣ Configurazione ‣ Contabilità: Diari”, fare clic su :guilabel:`Crea e selezionare Cassa nel campo Tipo.

Per ulteriori informazioni sui campi delle informazioni contabili, leggere la sezione Configurazione di questa pagina.

Nota

È disponibile un giornale di cassa predefinito che può essere utilizzato subito. È possibile esaminarlo andando su :menuselezione:`Contabilità --> Configurazione --> Contabilità: Giornali --> Cassa`.

### Modificare un giornale bancario o di cassa esistente¶

Per modificare un giornale bancario esistente, accedere a :menuselezione:`Contabilità –> Configurazione –> Contabilità: Giornali” e selezionare il giornale che si desidera modificare.

## Configurazione¶

È possibile modificare le informazioni contabili e il numero di conto bancario in base alle proprie esigenze.

Vedi anche

  * :doc:inizia/multi_valuta

  * banca/transazioni




### Conto di sospensione¶

Le transazioni dell’estratto conto bancario sono registrate sul Conto spese fino a quando la riconciliazione finale non consente di trovare il conto giusto.

### Conto economico¶

Il Conto profitti viene utilizzato per registrare un profitto quando il saldo finale di una cassa differisce da quello calcolato dal sistema, mentre il Conto perdite viene utilizzato per registrare una perdita quando il saldo finale di una cassa differisce da quello calcolato dal sistema.

### Valuta¶

È possibile modificare la valuta utilizzata per inserire le dichiarazioni.

Vedi anche

:doc:inizia/multi_valuta

### Numero di conto¶

Se è necessario **modificare le coordinate bancarie** , fare clic sulla freccia del collegamento esterno accanto al proprio Numero di conto. Nella nuova pagina, fare clic sulla freccia del collegamento esterno accanto a Bank e aggiornare le informazioni bancarie di conseguenza. Questi dati vengono utilizzati per la registrazione dei pagamenti.

### Alimentazioni bancarie¶

Flussi bancari definisce come vengono registrati gli estratti conto. Sono disponibili tre opzioni:

  * Ancora non definito, da selezionare quando non si sa ancora se si intende sincronizzare il conto bancario con il database o meno.

  * Importa (CAMT, CODA, CSV, OFX, QIF), da selezionare se si desidera importare l’estratto conto utilizzando un formato diverso.

  * Sincronizzazione bancaria automatica, da selezionare se la banca è sincronizzata con il database.




Vedi anche

  * :doc:banca/sincronizzazione_bancaria

  * banca/transazioni




## Conti in sospeso¶

Per impostazione predefinita, i pagamenti vengono registrati attraverso conti transitori denominati **conti in sospeso** , prima di essere registrati sul vostro conto bancario.

  * Un **conto per i pagamenti in sospeso** è il luogo in cui vengono registrati i pagamenti in uscita fino a quando non vengono collegati a un prelievo dall’estratto conto bancario.

  * Un **conto ricevute in sospeso** è il luogo in cui vengono registrati i pagamenti in entrata fino a quando non vengono collegati a un deposito dall’estratto conto bancario.




Questi conti devono essere di [tipo](get_started/chart_of_accounts.html#chart-of-account-type) Current Assets.

Nota

Lo spostamento da un conto in sospeso a un conto bancario avviene automaticamente quando si riconcilia il conto bancario con un estratto conto.

### Configurazione predefinita degli account¶

I conti in sospeso sono definiti per impostazione predefinita. Se necessario, è possibile aggiornarli andando in Contabilità ‣ Configurazione ‣ Impostazioni ‣ Conti predefiniti e aggiornare i conti Conto ricevute in sospeso e Conto pagamenti in sospeso.

### Configurazione dei giornali di banca e cassa¶

È inoltre possibile impostare conti in sospeso specifici per qualsiasi giornale con l’opzione [type](get_started/chart_of_accounts.html#chart-of-account-type) Bank o Cash.

Dal Dashboard contabile, fare clic sul menu ⋮ del giornale che si desidera configurare e fare clic su Configurazione, quindi aprire la scheda Pagamenti in entrata/uscita. Per visualizzare la colonna dei conti in sospeso, fare clic sul pulsante di commutazione e selezionare la voce Conti in sospeso degli incassi/pagamenti, quindi aggiornare il conto.

Nota

  * Se non si specifica un conto dei pagamenti in sospeso o un conto degli incassi in sospeso per un giornale specifico, Odoo utilizza i conti in sospeso predefiniti.

  * Se il conto bancario principale è aggiunto come conto per le ricevute in sospeso o per i pagamenti in sospeso, quando viene registrato un pagamento, lo stato della fattura o del conto viene impostato direttamente su Pagato.




  * [Sincronizzazione bancaria](bank/bank_synchronization.html)
    * [Salt Edge](bank/bank_synchronization/saltedge.html)
    * [Ponto](bank/bank_synchronization/ponto.html)
    * [Abilitare la Banca](bank/bank_synchronization/enablebanking.html)
  * [Transazioni](bank/transactions.html)
  * [Riconciliazione bancaria](bank/reconciliation.html)
  * [Modelli di riconciliazione](bank/reconciliation_models.html)
  * [Gestire un conto bancario in una valuta straniera](bank/foreign_currency.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/bank.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank/bank_synchronization.html "Sincronizzazione bancaria") |
  * [precedente](payments/trusted_accounts.html "Trusted accounts \(send money\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
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