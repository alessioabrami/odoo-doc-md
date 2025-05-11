# Gestire un conto bancario in una valuta straniera — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reporting.html "Rendiconto") |
  * [precedente](reconciliation_models.html "Modelli di riconciliazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Gestire un conto bancario in una valuta straniera



# Gestire un conto bancario in una valuta straniera¶

In Odoo, ogni transazione viene registrata nella valuta predefinita dell’azienda e i resoconti sono tutti basati su tale valuta predefinita. Quando si dispone di un conto bancario in una valuta estera, per ogni transazione Odoo memorizza due valori:

  * il debito/credito nella valuta della _azienda_

  * il debito/credito nella valuta del _conto bancario_.




I tassi di cambio vengono aggiornati automaticamente utilizzando i servizi web di un istituto bancario. Per impostazione predefinita, Odoo utilizza i servizi web della Banca Centrale Europea, ma sono disponibili altre opzioni.

## Configurazione¶

### Attivare più valute¶

Per lavorare con più valute, accedi al modulo Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute e spunta Multi valuta. Nella sezione Registra voce tasso di cambio in:, aggiungi un Registro, un Conto utili, un Conto perdite e poi fai clic su Salva.

### Configurare valute¶

Una volta completata la configurazione multi valuta in Odoo, tutte le valute vengono create per impostazione predefinita ma non attivate necessariamente.

Una volta attivate le valute, puoi scegliere di **automatizzare** l’aggiornamento del tasso di cambio oppure continuare a farlo **manualmente**. Per configurare l’aggiornamento del tasso, torna al modulo Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute, seleziona Tassi di cambio automatici, imposta un Intervallo secondo la frequenza desiderata e fai clic su Salva. Puoi anche scegliere il Servizio da cui vuoi ottenere tassi di cambio.

Per aggiornare manualmente i tassi di cambio, fai clic sul pulsante Aggiorna ora (🗘) accanto al campo Prossima esecuzione.

### Crea un nuovo conto bancario¶

Apri l’applicazione Contabilità ‣ Configurazione ‣ Registri e creane uno nuovo. Aggiungi un Nome registro e imposta il Tipo su `Banca`. Nella scheda Registrazioni contabili, aggiungi un **codice breve** , una **valuta** e infine fai clic sul campo Conto bancario per creare un nuovo conto. Nella finestra pop-up per la creazione del conto, inserisci un nome, un codice (ad es.: 550007), imposta il tipo su `Banca e cassa`, configura un tipo di valuta e salva. Una volta tornato al **registro** , fai clic sul campo Numero conto e nella finestra pop-up riempi i campi Numero conto, Banca del tuo conto e salva.

Al momento della creazione del giornale, Odoo collega automaticamente il conto bancario al registro. Puoi trovarlo seguendo il percorso Contabilità ‣ Configurazione ‣ Contabilità: Piano dei conti.

## Fatture fornitore in valuta estera¶

Per pagare una fattura fornitore in una valuta straniera, è sufficiente selezionare la valuta accanto al campo Registro e registrare il pagamento. Odoo crea e registra automaticamente gli **utili/perdite sui cambi** esteri come nuova registrazione contabile.

Nota

È possibile pagare una fattura estera con un’altra valuta. In questo caso, Odoo converte automaticamente le due valute.

## Resoconto utili/perdite sui cambi non realizzati¶

Questo resoconto offre una panoramica di tutti gli importi non realizzati in una valuta estera nel tuo stato patrimoniale e ti permette di sistemare una registrazione o impostare manualmente un tasso di cambio. Per accedere al resoconto, accedi a Rendicontazione ‣ Gestione: Utili/perdite in valuta non realizzati. Da qui, avrai accesso a tutte le registrazioni aperte nel tuo **stato patrimoniale**.

Se desideri utilizzare una valuta diversa rispetto a quella configurata in Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute, fai clic sul pulsante Tassi di cambio e modifica il tasso delle valute estere nel resoconto.

Quando modifichi manualmente i **tassi di cambio** , appare un banner giallo che ti permette di reimpostare il tasso di Odoo. Per farlo, puoi fare semplicemente clic su Ripristina tasso Odoo.

Per aggiornare lo **stato patrimoniale** con l’importo della colonna rettifica, fai clic sul pulsante Registrazione di rettifica. Nella finestra pop-up, scegli un Registro, un Conto spese e un Conto di ricavo per calcolare ed elaborare gli **Utili/perdite non realizzati**.

Puoi impostare la data del resoconto tramite il campo Data. Odoo modifica automaticamente la data di registrazione applicando la data configurata nel campo Data di storno.

Una volta registrata, la colonna rettifica dovrebbe indicare `0.00`, il che significa che tutti **gli utili/perdite non realizzati** sono stati rettificati.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/bank/foreign_currency.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../reporting.html "Rendiconto") |
  * [precedente](reconciliation_models.html "Modelli di riconciliazione") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Gestire un conto bancario in una valuta straniera


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