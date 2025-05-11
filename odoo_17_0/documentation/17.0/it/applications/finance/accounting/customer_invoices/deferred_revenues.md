# Risconti passivi — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](electronic_invoicing.html "Fatturazione elettronica \(EDI\)") |
  * [precedente](cash_rounding.html "Arrotondamento di cassa") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Risconti passivi



# Risconti passivi¶

I **risconti passivi** sono fatture indirizzate ai clienti per beni non ancora consegnati o servizi non ancora resi.

L’azienda non può riportarli nel **conto economico (profitti e perdite)** corrente, poiché i beni e i servizi saranno effettivamente consegnati/erogati in futuro.

I ricavi futuri devono essere rinviati nello stato patrimoniale dell’azienda tra le passività correnti fino a quando non possono essere **riconosciuti** , in una sola volta o in un periodo definito, nel conto economico.

Ad esempio, supponiamo che un’azienda venda una licenza software di 1.200 $ per 1 anno. L’azienda emette immediatamente la fattura cliente, ma non può considerarla ancora acquisita, poiché i mesi futuri di licenza non sono ancora stati consegnati. Pertanto, i nuovi ricavi vengono registrati in un conto risconti passivi e rilevati su base mensile. Ogni mese, per i prossimi 12 mesi, verranno riconosciuti come ricavi 100 $.

Odoo Contabilità gestisce i risconti passivi suddividendoli in più registrazioni che vengono registrate periodicamente.

Nota

Il server verifica una volta al giorno se una registrazione deve essere registrata. In seguito, potrebbero volerci fino a 24 prima di vedere il passaggio da Bozza a Registrata.

## Configurazione¶

Assicurati che le impostazioni predefinite siano state configurate correttamente per il tuo business. Per farlo, vai su Contabilità ‣ Configurazione ‣ Impostazioni. Sono disponibili le seguenti opzioni:

Registro
    

Le registrazioni differite vengono registrate in questo registro.

Conto risconti attivi
    

Expenses are deferred on this Current Asset account until they are recognized.

Conto risconti passivi
    

I ricavi vengono differiti sul conto passività a breve termine fino al momento del riconoscimento.

Generazione registrazioni
    

Per impostazione predefinita, Odoo genera automaticamente le registrazioni differite quando registri una fattura cliente. Tuttavia, puoi anche scegliere di generarle manualmente selezionando l’opzione Manuale e raggruppato.

Calcolo importo
    

Supponiamo che una fattura di 1.200 $ debba essere dilazionata in 12 mesi.

  * L’opzione Mese considera 100 $ al mese, proporzionalmente al numero di giorni del mese (ad es., 50 $ per il primo mese se la Data di inizio è impostata sul giorno 15 del mese).

  * L’opzione Mesi interi considera il mese per interno (ad es., 100 $ per il primo mese anche se la Data di inizio è impostata sul giorno 15 del mese). Ciò significa che con l’opzione Mesi interi, l’importo di 100 $ viene riconosciuto nel primo mese parziale, eliminando il bisogno di un 13esimo mese per riconoscere qualsiasi avanzo come nel caso dell’opzione Mesi.

  * L’opzione Giorni considera vari importi in base al numero di giorni in ogni mese (ad es., ~102 $ per gennaio e ~92 $ per febbraio).




## Generare registrazioni differite al momento della convalida¶

Suggerimento

Assicurati che i campi Data di inizio e Data di fine siano visibili nella scheda Righe fattura. Nella maggior parte dei casi, la Data di inizio dovrebbe essere nello stesso mese della Data fattura. Le registrazioni dei risconti passivi vengono registrate a partire dalla data della fattura e vengono visualizzate di conseguenza nel rendiconto.

Per ogni riga della fattura che deve essere differita, specifica le date di inizio e fine del periodo di differimento.

Se nelle **impostazioni** il campo Genera registrazioni è impostato su Su convalida della fattura cliente/fornitore, Odoo genera automaticamente le registrazioni differite quando la fattura viene convalidata. Fai clic sul pulsante intelligente Registrazioni differite per vederle.

Una registrazione, datata lo stesso giorno della data di contabilizzazione della fattura, sposta gli importi della fattura dal conto delle entrate al conto delle registrazioni. Le altre registrazioni sono registrazioni differite che, mese dopo mese, spostano gli importi delle fatture dal conto differito al conto di ricavo per riconoscere i ricavi.

Example

È possibile differire una fattura di gennaio di 1.200 $ su 12 mesi specificando la data di inizio del 01/01/2023 e la data di fine del 31/12/2023. Alla fine di agosto, 800 $ vengono riconosciuti come entrate, mentre 400 $ rimangono sul conto differito.

## Rendiconto¶

Il Rendiconto risconti passivi calcola una panoramica delle registrazioni differite necessarie per ogni conto. Per accedervi, vai su Contabilità ‣ Rendicontazione ‣ Risconto passivo.

Per visualizzare i movimenti contabili di ogni conto, fai clic sul nome del conto e poi su Movimenti contabili.

Nota

Vengono prese in considerazione solo le fatture la cui data di contabilizzazione è precedente alla fine del periodo di rendicontazione.

## Generare registrazioni differite raggruppate manualmente¶

Se hai molti risconti passivi e desideri ridurre il numero di registrazioni contabili create, è possibile generare manualmente le registrazioni differite. Per farlo, imposta il campo Genera registrazioni nelle **Impostazioni** su Manuale e raggruppato. Odoo aggrega quindi gli importi differiti in un’unica registrazione.

Alla fine di ogni mese, vai su Contabilità ‣ Rendicontazione ‣ Risconto passivo e fai clic sul pulsante Genera registrazioni. Verranno generate due registrazioni differite:

  * Una datata alla fine del mese che aggrega, per ogni conto, tutti gli importi differiti di quel mese. Ciò significa che una parte dei ricavi differiti viene riconosciuta alla fine di quel periodo.

  * Lo storno della registrazione creata, datata il giorno successivo (cioè il primo giorno del mese successivo) per annullare la voce precedente.




Example

Ci sono due fatture:

  * Fattura A: 1.200 $ da differire dal 01/01/2023 al 31/12/2023.

  * Fattura B: 600 $ da differire dal 01/01/2023 al 31/12/2023.




Gennaio
    

Alla fine del mese di gennaio, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 31 gennaio:

    * Riga 1: Conto spese -1.200 -600 = **-1.800** (annullamento del totale di entrambe le fatture)

    * Riga 2: conto spese 100 + 50 = **150** (con rilevazione di 1/12 della fattura A e della fattura B)

    * Riga 3: conto differito 1.800 - 150 = **1.650** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° febbraio è lo storno della registrazione precedente:

    * Riga 1: conto spese **1.800**

    * Riga 2: conto differito **-150**

    * Riga 3: conto spese **-1.650**



Febbraio
    

Alla fine del mese di febbraio, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 28 febbraio:

    * Riga 1: Conto spese -1.200 -600 = **-1.800** (annullamento del totale di entrambe le fatture)

    * Riga 2: conto spese 200 + 100 = **300** (con rilevazione di 2/12 della fattura A e della fattura B)

    * Riga 3: conto differito 1.800 - 300 = **1.500** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° marzo, lo storno della registrazione precedente.



Da marzo a ottobre
    

Lo stesso calcolo viene effettuato per ogni mese fino a ottobre.

Novembre
    

Alla fine del mese di novembre, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 30 novembre:

    * Riga 1: Conto spese -1.200 -600 = **-1.800** (annullamento del totale di entrambe le fatture)

    * Riga 2: conto spese 1.100 + 550 = **1.650** (con rilevazione di 11/12 della fattura A e della fattura B)

    * Riga 3: conto differito 1.800 - 1.650 = **150** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° dicembre, lo storno della registrazione precedente.



Dicembre
    

Non è necessario generare registrazioni nel mese di dicembre. Infatti, se facciamo il calcolo per dicembre, abbiamo un importo pari a 0 da differire.

In totale
    

Se aggreghiamo tutto, avremo:

  * fattura A e fattura B

  * due registrazioni (una per il differimento e una per lo storno) per ogni mese da gennaio a novembre.




Pertanto, alla fine di dicembre, le fatture A e B sono interamente riconosciute come entrate una sola volta, nonostante tutte le scritture create grazie al meccanismo di storno.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/deferred_revenues.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](electronic_invoicing.html "Fatturazione elettronica \(EDI\)") |
  * [precedente](cash_rounding.html "Arrotondamento di cassa") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Risconti passivi


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