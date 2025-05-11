# Ponto — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](enablebanking.html "Abilitare la Banca") |
  * [precedente](saltedge.html "Salt Edge") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Conti bancari e di cassa](../../bank.html) »
  * [Sincronizzazione bancaria](../bank_synchronization.html) »
  * Ponto



# Ponto¶

**Ponto** è un servizio che permette ad aziende e professionisti di aggregare i loro conti in un unico luogo e di vedere direttamente tutte le loro transazioni all’interno di un’unica app. È una soluzione di terze parti che sta ampliando continuamente il numero di istituti bancari che possono essere sincronizzati con Odoo.

**Odoo** can synchronize directly with your bank to get all bank statements imported automatically into your database.

Ponto è un fornitore di terze parti a pagamento che può gestire la sincronizzazione tra i conti bancari e Odoo.

Vedi anche

  * ../sincronizzazione bancaria

  * ../transazioni




## Configurazione¶

### Collega i tuoi conti bancari con Ponto¶

  1. Go to [Ponto’s website (https://myponto.com)](https://myponto.com/).

  2. Crea un account se non ne hai ancora uno

  3. Una volta effettuato l’accesso, creare una _organizzazione_.

  4. Andare su Accounts ‣ Live e cliccare su Add account. Potrebbe essere necessario aggiungere prima le **Informazioni di fatturazione**.

  5. Selezionate il vostro Paese, i vostri istituti bancari, date il vostro consenso a Ponto e seguite i passaggi sullo schermo per collegare il vostro conto bancario al vostro conto Ponto.

  6. Aggiungete tutti i conti bancari che volete sincronizzare con il vostro database Odoo e passate ai passi successivi.




### Collega il tuo account Ponto con il tuo database Odoo¶

  1. Andare su Contabilità ‣ Configurazione ‣ Aggiungi un conto bancario.

  2. Cercate il vostro istituto e selezionatelo, in modo da poter verificare che il fornitore terzo sia Ponto.

  3. Fare clic su Connect e seguire la procedura.

  4. Selezionare **tutti i conti** a cui si vuole accedere e sincronizzare in Odoo, anche quelli provenienti da altri istituti bancari.

  5. Completa il flusso




Nota

È necessario autorizzare tutti i conti a cui si vuole accedere in Odoo, ma Odoo filtrerà i conti in base all’istituzione selezionata nel secondo passaggio.

### Aggiorna le tue credenziali di sincronizzazione¶

Per aggiornare le credenziali di Ponto o modificare le impostazioni di sincronizzazione, attivare la modalità sviluppatore 1, andare su Contabilità ‣ Configurazione ‣ Sincronizzazione online e selezionare l’istituzione da cui si desidera recuperare gli altri conti. Fare clic su Recupera conti per avviare il flusso.

Nota

Durante l’aggiornamento, selezionare **tutti i conti** che si desidera sincronizzare, anche quelli provenienti da altri istituti bancari.

### Recupera nuovi account¶

Per aggiungere nuovi conti online alla connessione, attivare la modalità sviluppatore 1, andare su Contabilità ‣ Configurazione ‣ Sincronizzazione online e selezionare l’istituzione da cui si desidera recuperare gli altri conti. Fare clic su Recupera conti per avviare il flusso.

Nota

Non dimenticate di mantenere l’autorizzazione per i conti esistenti (per tutti gli istituti che avete sincronizzato con Ponto).

## FAQ¶

### Dopo la mia sincronizzazione, non appare alcun account¶

L’utente ha selezionato un istituto dall’elenco e non ha autorizzato alcun conto di questo istituto.

### Ho un errore che indica che la mia autorizzazione è scaduta.¶

Ogni **6 mesi** (180 giorni) è necessario autorizzare nuovamente la connessione tra il conto bancario e Ponto. Questa operazione deve essere effettuata dal sito web di Ponto <[https://myponto.com](https://myponto.com/)>`_. Se non si esegue questa operazione, la sincronizzazione si interrompe per questi conti.

### Ho alcuni errori con la mia istituzione beta¶

Ponto fornisce istituzioni in _beta_ , queste istituzioni non sono direttamente supportate da Odoo e vi consigliamo di contattare direttamente Ponto.

Importante

L’utilizzo di un’istituzione in fase beta è vantaggioso per Ponto, in quanto consente di avere un feedback reale sulla connessione con l’istituzione.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/bank/bank_synchronization/ponto.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](enablebanking.html "Abilitare la Banca") |
  * [precedente](saltedge.html "Salt Edge") |
  * [Odoo 17.0 documentazione](../../../../../index-2.html) »
  * [Documentazione Utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Conti bancari e di cassa](../../bank.html) »
  * [Sincronizzazione bancaria](../bank_synchronization.html) »
  * Ponto


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