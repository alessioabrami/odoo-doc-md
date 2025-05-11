# Deferred expenses — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sequence.html "Vendor bill sequence") |
  * [precedente](assets.html "Non-current assets and fixed assets") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Deferred expenses



# Deferred expenses¶

**Deferred expenses** and **prepayments** (also known as **prepaid expenses**) are both costs that have already occurred for products or services yet to be received.

Such costs are **assets** for the company that pays them since it already paid for products and services but has either not yet received them or not yet used them. The company cannot report them on the current **profit and loss statement** , or _income statement_ , since the payments will be effectively expensed in the future.

These future expenses must be deferred on the company’s balance sheet until the moment in time they can be **recognized** , at once or over a defined period, on the profit and loss statement.

For example, let’s say we pay $1200 at once for one year of insurance. We already pay the cost now but haven’t used the service yet. Therefore, we post this new expense in a _prepayment account_ and decide to recognize it on a monthly basis. Each month, for the next 12 months, $100 will be recognized as an expense.

Odoo Accounting handles deferred expenses by spreading them across multiple entries that are posted periodically.

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
    

By default, Odoo automatically generates the deferral entries when you post a vendor bill. However, you can also choose to generate them manually by selecting the Manually & Grouped option instead.

Calcolo importo
    

Suppose a bill of $1200 must be deferred over 12 months.

  * L’opzione Mese considera 100 $ al mese, proporzionalmente al numero di giorni del mese (ad es., 50 $ per il primo mese se la Data di inizio è impostata sul giorno 15 del mese).

  * L’opzione Mesi interi considera il mese per interno (ad es., 100 $ per il primo mese anche se la Data di inizio è impostata sul giorno 15 del mese). Ciò significa che con l’opzione Mesi interi, l’importo di 100 $ viene riconosciuto nel primo mese parziale, eliminando il bisogno di un 13esimo mese per riconoscere qualsiasi avanzo come nel caso dell’opzione Mesi.

  * L’opzione Giorni considera vari importi in base al numero di giorni in ogni mese (ad es., ~102 $ per gennaio e ~92 $ per febbraio).




## Generare registrazioni differite al momento della convalida¶

Suggerimento

Make sure the Start Date and End Date fields are visible in the Invoice Lines tab. In most cases, the Start Date should be in the same month as the Bill Date. Deferred expense entries are posted from the bill date and are displayed in the report accordingly.

For each line of the bill that should be deferred, specify the start and end dates of the deferral period.

If the Generate Entries field is set to On invoice/bill validation, Odoo automatically generates the deferral entries when the bill is validated. Click on the Deferred Entries smart button to see them.

One entry, dated on the same day as the bill’s accounting date, moves the bill amounts from the expense account to the deferred account. The other entries are deferral entries which will, month after month, move the bill amounts from the deferred account to the expense account to recognize the expense.

Example

You can defer a January bill of $1200 over 12 months by specifying a start date of 01/01/2023 and an end date of 12/31/2023. At the end of August, $800 is recognized as an expense, whereas $400 remains on the deferred account.

## Rendiconto¶

The deferred expense report computes an overview of the necessary deferral entries for each account. To access it, go to Accounting ‣ Reporting ‣ Deferred Expense.

Per visualizzare i movimenti contabili di ogni conto, fai clic sul nome del conto e poi su Movimenti contabili.

Nota

Only bills whose accounting date is before the end of the period of the report are taken into account.

## Generare registrazioni differite raggruppate manualmente¶

Se hai molti risconti passivi e desideri ridurre il numero di registrazioni contabili create, è possibile generare manualmente le registrazioni differite. Per farlo, imposta il campo Genera registrazioni nelle **Impostazioni** su Manuale e raggruppato. Odoo aggrega quindi gli importi differiti in un’unica registrazione.

At the end of each month, go to the Deferred Expenses report and click the Generate Entries button. This generates two deferral entries:

  * One dated at the end of the month which aggregates, for each account, all the deferred amounts of that month. This means that at the end of that period, a part of the deferred expense is recognized.

  * Lo storno della registrazione creata, datata il giorno successivo (cioè il primo giorno del mese successivo) per annullare la voce precedente.




Example

There are two bills:

  * Bill A: $1200 to be deferred from 01/01/2023 to 12/31/2023

  * Bill B: $600 to be deferred from 01/01/2023 to 12/31/2023




Gennaio
    

Alla fine del mese di gennaio, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 31 gennaio:

    * Line 1: Expense account -1200 -600 = **-1800** (cancelling the total of both bills)

    * Line 2: Expense account 100 + 50 = **150** (recognizing 1/12 of bill A and bill B)

    * Riga 3: conto differito 1.800 - 150 = **1.650** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° febbraio è lo storno della registrazione precedente:

    * Riga 1: conto spese **1.800**

    * Riga 2: conto differito **-150**

    * Riga 3: conto spese **-1.650**



Febbraio
    

Alla fine del mese di febbraio, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 28 febbraio:

    * Line 1: Expense account -1200 -600 = **-1800** (cancelling the total of both bills)

    * Line 2: Expense account 200 + 100 = **300** (recognizing 2/12 of bill A and bill B)

    * Riga 3: conto differito 1.800 - 300 = **1.500** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° marzo, lo storno della registrazione precedente.



Da marzo a ottobre
    

Lo stesso calcolo viene effettuato per ogni mese fino a ottobre.

Novembre
    

Alla fine del mese di novembre, dopo aver fatto clic sul pulsante Genera registrazioni, vedrai le seguenti registrazioni:

  * Registrazione 1 datata il 30 novembre:

    * Line 1: Expense account -1200 -600 = **-1800** (cancelling the total of both bills)

    * Line 2: Expense account 1100 + 550 = **1650** (recognizing 11/12 of bill A and bill B)

    * Riga 3: conto differito 1.800 - 1.650 = **150** (importo che deve ancora essere differito in seguito)

  * La registrazione 2 del 1° dicembre, lo storno della registrazione precedente.



Dicembre
    

There is no need to generate entries in December. Indeed, if we do the computation for December, we will have an amount of 0 to be deferred.

In totale
    

Se aggreghiamo tutto, avremo:

  * bill A and bill B

  * due registrazioni (una per il differimento e una per lo storno) per ogni mese da gennaio a novembre.




Therefore, at the end of December, bills A and B are fully recognized as expense only once in spite of all the created entries thanks to the reversal mechanism.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/vendor_bills/deferred_expenses.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sequence.html "Vendor bill sequence") |
  * [precedente](assets.html "Non-current assets and fixed assets") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture fornitore](../vendor_bills.html) »
  * Deferred expenses


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
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto