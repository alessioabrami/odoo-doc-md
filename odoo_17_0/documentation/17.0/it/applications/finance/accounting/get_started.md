# Esordiente — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_started/cheat_sheet.html "Promemoria contabile") |
  * [precedente](../accounting.html "Contabilità e fatturazione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Esordiente



# Esordiente¶

Quando apri per la prima volta l’applicazione Contabilità di Odoo, verrai accolto dalla Dashboard e da un banner introduttivo che ti mostrerà passo dopo passo il funzionamento dell’applicazione. Il banner di onboarding viene visualizzato finché non scegli di chiuderlo.

Le impostazioni disponibili nel banner di onboarding possono essere modificate in seguito, seguendo il percorso Contabilità ‣ Configurazione ‣ Impostazioni.

Nota

A seguito dell’installazione dell’app Contabilità di Odoo, il **Pacchetto di localizzazione fiscale** appropriato per la tua azienda verrà installato automaticamente, secondo il Paese selezionato al momento della creazione del database. In questo modo, potrai subito iniziare a utilizzare piani contabili, resoconti e imposte. [Fai clic qui](../fiscal_localizations.html#fiscal-localizations-packages) per maggiori informazioni sui Pacchetti di localizzazione fiscale.

## Banner onboarding Contabilità¶

Il banner di onboarding dell’app Contabilità è composto da quattro step:

  1. Periodi contabili

  2. Conto bancario

  3. Imposte

  4. Piano dei conti




### Periodi contabili¶

Stabilisci le date di apertura e chiusura degli **Anni fiscali** , utilizzate per generare automaticamente i rendiconti, e imposta la **Periodicità dichiarazione fiscale** , insieme a un promemoria per non perdere mai una scadenza relativa alla dichiarazione.

Per impostazione predefinita, la data di apertura è fissata al 1° gennaio e la data di chiusura al 31 dicembre, in quanto si tratta dell’uso più comune.

Nota

È possibile modificare le impostazioni tramite il percorso Contabilità ‣ Configurazione ‣ Impostazioni ‣ Periodi fiscali e aggiornare i valori.

### Conto bancario¶

Collega il tuo conto bancario al database per sincronizzare automaticamente tutti gli estratti conto. Per farlo, trova la tua banca nell’elenco, fai clic su Collega e segui le istruzioni sullo schermo.

Nota

[Fai clic qui](bank/bank_synchronization.html) per scoprire di più sulla funzionalità.

Se il tuo istituto bancario non può essere sincronizzato automaticamente, oppure se preferisci non sincronizzarlo con il tuo database, puoi anche configurare il tuo conto bancario manualmente digitandone il nome, facendo clic su Crea conto bancario, per poi riempire il modulo.

  * Nome: il nome del conto, come mostrato in Odoo

  * Numero conto: numero conto corrente (IBAN in Europa)

  * Banca: fai clic su Crea e modifica per configurare i dettagli della banca. Aggiungi il Nome e il Codice identificativo (BIC o SWIFT) dell’istituto bancario.

  * Codice: questo codice è il Codice breve del tuo registro, come mostrato in Odoo. Per impostazione predefinita, Odoo crea un nuovo registro con questo codice breve

  * Registro: questo campo viene visualizzato se si dispone di un registro bancario esistente non ancora collegato a un conto bancario. In tal caso, seleziona il Registro che vuoi utilizzare per registrare le transazioni finanziarie collegate a questo conto bancario o creane uno nuovo facendo clic su Crea e modifica.




Nota

  * Grazie a questo strumento, è possibile aggiungere tutti i conti correnti di cui hai bisogno seguendo il percorso Contabilità ‣ Configurazione ‣ Aggiungi conto bancario.

  * [Fai clic qui](bank.html) per maggiori informazioni sui conti bancari.




### Imposte¶

Questo menu ti permette di creare nuove imposte, (dis)attivare o modificare quelle esistenti. A seconda del [pacchetto di localizzazione](../fiscal_localizations.html) installato nel database, le imposte richieste per il tuo Paese sono configurate automaticamente.

Nota

[Fai clic qui](taxes.html) per avere più informazioni sulla configurazione delle imposte.

### Piano dei conti¶

Grazie a questo menu, puoi aggiungere conti al tuo **Piano dei conti** e indicare i saldi di apertura iniziali.

Le impostazioni di base vengono visualizzate su questa pagina per aiutarti a verificare il tuo Piano dei conti. Per accedere a tutte le impostazioni di un conto, fai clic sul pulsante Visualizza alla fine della riga.

Nota

[Fai clic qui](get_started/chart_of_accounts.html) per scoprire di più su come configurare i Piani contabili.

## Banner onboarding Fatturazione¶

Esiste un altro banner di onboarding che ti aiuta a capire come utilizzare le app Fatturazione e Contabilità di Odoo. Il banner relativo all’app Fatturazione è quello che ti accoglie se scegli di utilizzare l’app correlata.

Se hai già installato l’app Contabilità sul tuo database, puoi accedervi seguendo il percorso Contabilità ‣ Clienti ‣ Fatture.

Il banner di onboarding dell’app Fatturazione è composto da quattro step:

  1. Dati azienda

  2. Struttura documenti

  3. Crea fattura

  4. Pagamenti online




### Dati azienda¶

Aggiungi i dati della tua azienda, come nome, indirizzo, logo, sito web, numero di telefono, indirizzo e-mail e codice fiscale o partita IVA. Questi dati vengono poi visualizzati sui documenti, come le fatture.

Nota

È anche possibile modificare i dettagli dell’azienda accedendo alle Impostazioni ‣ Impostazioni generali, per poi scorrere in basso fino alla sezione Aziende e infine Aggiorna informazioni.

### Struttura documenti¶

Personalizza la [struttura predefinita delle fatture](../../studio/pdf_reports.html#studio-pdf-reports-default-layout).

Nota

È possibile modificare la struttura della fattura tramite il percorso Impostazioni ‣ Impostazioni generali, scorrere in basso fino alla sezione Aziende per poi fare clic su Configura struttura documento.

### Crea fattura¶

Crea la prima fattura.

Suggerimento

Aggiungi il **numero di conto corrente** e un link ai **Termini e condizioni generali** nel piè di pagina. In questo modo, i tuoi contatti potranno trovare online il contenuto completo dei GT&C senza doverli stampare sulle fatture emesse.

### Pagamenti online¶

Inizia a lavorare con Stripe e attiva pagamenti sicuri integrati con carte di credito e di debito all’interno di Odoo.

Suggerimento

Per utilizzare altri servizi di pagamento, accedi all’applicazione Fatturazione –> Configurazione –> Fornitori di pagamenti e [attiva i fornitori desiderati](../payment_providers.html).

Vedi anche

  * [Conti bancari e di cassa](bank.html)

  * [Piano dei conti](get_started/chart_of_accounts.html)

  * :doc:banca/sincronizzazione_bancaria

  * [Fiscal localizations](../fiscal_localizations.html)

  * [Tutorial Odoo: Contabilità e Fatturazione - Per iniziare [video]](https://www.odoo.com/slides/slide/getting-started-1692)




  * [Promemoria contabile](get_started/cheat_sheet.html)
  * [Piano dei conti](get_started/chart_of_accounts.html)
  * [Sistema multi valuta](get_started/multi_currency.html)
  * [Prezzo medio sulla merce resa](get_started/avg_price_valuation.html)
  * [Unità fiscali](get_started/tax_units.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/get_started.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_started/cheat_sheet.html "Promemoria contabile") |
  * [precedente](../accounting.html "Contabilità e fatturazione") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Esordiente


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