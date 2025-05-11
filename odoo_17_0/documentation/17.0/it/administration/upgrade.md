# Aggiorna — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](neutralized_database.html "Database neutralizzato") |
  * [precedente](on_premise/community_to_enterprise.html "Passare da Community a Enterprise") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Aggiorna



# Aggiorna¶

Un aggiornamento comporta lo spostamento di un database da una versione più vecchia a una più recente (ad es. da Odoo 16.0 a Odoo 18.0). Aggiornamenti regolari sono cruciali in quanto ogni versione offre nuove funzionalità, correzione di bug e patch di sicurezza. L’utilizzo di una [versione supportata](supported_versions.html) è fortemente consigliato. Ogni versione maggiore è supportata per tre anni.

In base al tipo di hosting e alla versione di Odoo utilizzata, l’aggiornamento di un database potrebbe essere **obbligatorio**.

Odoo OnlineOdoo.shOn-premise

  * Se un database è su una **versione maggiore** (ad es. 16.0, 17.0, 18.0), l’aggiornamento è obbligatorio ogni due anni.

  * Se un database è su una **versione minore** (ad es., 17.1, 17.2, 17.4), l’aggiornamento è obbligatorio un paio di settimane dopo il rilascio della versione successiva. Di solito, le versioni minori vengono rilasciate ogni due mesi.




Dopo i tre anni iniziali di supporto, avrai altri due anni per completare l’aggiornamento. Riceverai una notifica se sarà necessario aggiornare il tuo database.

Puoi continuare a utilizzare la stessa versione all’infinito anche se non è consigliato. Tieni a mente che quanto minore è il divario tra le versioni, tanto più facile sarà eseguire l’aggiornamento.

Automatic upgrades: Odoo Online's Rolling Release process

Riceverai una notifica nel tuo database alcune settimane prima dell’esecuzione automatica di un aggiornamento obbligatorio. Hai il controllo del processo fino alla data di scadenza.

Nel concreto, il team di aggiornamento di Odoo esegue un aggiornamento di prova invisibile di ogni database che dovrebbe essere aggiornato. Se il test riesce e dura meno di 20 minuti, puoi eseguire l’aggiornamento direttamente dal database. Se il test fallisce, puoi testare un aggiornamento utilizzando il [database manager](https://www.odoo.com/my/databases).

Se devi aggiornare Odoo, è fortemente consigliato richiedere un database di prova aggiornato e testarlo .

Se prima della data limite indicata non viene eseguita nessuna azione, verrà automaticamente effettuato l’aggiornamento alla versione successiva.

Un aggiornamento non copre:

>   * Il passaggio ad una versione precedente di Odoo
> 
>   * [Il cambiamento di versione](on_premise/community_to_enterprise.html) (ad es., da Community a Enterprise)
> 
>   * [Il cambiamento del tipo di hosting](hosting.html#hosting-change-solution) (ad es., da on-premise a Odoo Online)
> 
>   * La migrazione da un altro ERP a Odoo.
> 
> 


Avvertimento

Se il tuo database contiene moduli personalizzati, non può essere aggiornato fino al momento in cui sarà disponibile una versione per i moduli personalizzati corrispondente alla versione desiderata di Odoo. Per i clienti che gestiscono i propri moduli personalizzati, consigliamo di parallelizzare il processo richiedendo un database aggiornato <upgrade-request-test>mentre [viene aggiornato anche il codice sorgente dei moduli personalizzati](../developer/howtos/upgrade_custom_db.html).

## L’aggiornamento in breve¶

  1. Richiedi un database di prova aggiornato (consulta la sezione Ottenere un database di prova aggiornato).

  2. Se possibile, aggiorna il codice sorgente del modulo personalizzato per renderlo compatibile con la nuova versione di Odoo (consulta la pagina [Upgrade a customized database](../developer/howtos/upgrade_custom_db.html)).

  3. Testa a fondo il database aggiornato (consulta la sezione Testare una nuova versione del database).

  4. Segnala qualsiasi problema riscontrato durante il test di Odoo accedendo alla [pagina di supporto per poi selezionare «Un problema relativo al mio futuro aggiornamento (sto testando un aggiornamento)»](https://www.odoo.com/help?stage=migration).

  5. Una volta che tutti i problemi sono stati risolti e sei sicuro che il database aggiornato possa essere utilizzato come database principale senza problemi, pianifica l’aggiornamento del database di produzione.

  6. Richiedi l’aggiornamento per il database di produzione rendendolo non disponibile per il tempo necessario al completamento del processo (consulta la sezione Aggiornare il database di produzione).

  7. Segnala qualsiasi problema riscontrato durante il test di Odoo accedendo alla [pagina di supporto per poi selezionare «Un problema relativo al mio upgrade (produzione)»](https://www.odoo.com/help?stage=post_upgrade).




## Ottenere un database di prova aggiornato¶

La [pagina di aggiornamento](https://upgrade.odoo.com/) è la piattaforma principale per richiedere un database aggiornato. Tuttavia, in base al tipo di hosting, puoi eseguire l’aggiornamento dalla riga di comando (on-premise), dal [gestore di database Odoo Online](https://www.odoo.com/my/databases) oppure dal [Odoo.sh project](https://www.odoo.sh/project).

Nota

La piattaforma di aggiornamento segue la stessa [Informativa sulla privacy](https://www.odoo.com/privacy) degli altri servizi Odoo.com. Consulta il [Regolamento Generale Protezione Dati](https://www.odoo.com/gdpr) per sapere di più sul modo in cui Odoo gestisce i tuoi dati e la tua privacy.

Odoo OnlineOdoo.shOn-premise

I database Odoo Online possono essere aggiornati manualmente attraverso il [gestore di database](https://www.odoo.com/my/databases).

La pagina di gestione dei database mostra tutti i database associati all’account dell’utente. I database non aggiornati alla versione più recente di Odoo vengono visualizzati con una freccia in un’icona a forma di cerchio accanto al loro nome indicando la possibilità di eseguire l’aggiornamento.

Fai clic sull’icona con **una freccia in un cerchio** per avviare il processo di aggiornamento. Nella finestra pop-up, inserisci:

  * La **versione** di Odoo che vuoi ottenere con l’aggiornamento, di solito l’ultima versione

  * L’indiri

  * Lo Scopo dell’aggiornamento che viene impostato automaticamente su Test per la prima richiesta di aggiornamento




La dicitura Aggiornamento in corso viene visualizzata accanto al nome del database fino al completamento. Una volta che il processo è stato completato, verrà inviato un’e-mail all’indirizzo fornito contenente il link al database di prova aggiornato. È possibile accedere al database anche attraverso la pagina di gestione degli stessi facendo clic sulla freccia a discesa che si trova a sinistra del nome del database.

Odoo.sh viene integrato con la piattaforma di aggiornamento per semplificare il processo.

In seguito, **l’ultimo back-up automatico giornaliero di produzione** viene inviato alla piattaforma di aggiornamento.

Una volta che la piattaforma di aggiornamento ha completato l’aggiornamento del back-up e lo ha caricato nel branch, viene attivata la _modalità speciale*_ : ogni volta che si esegue **il push del commit** sul branch, si verifica una **operazione di ripristino** del back-up aggiornato e un **aggiornamento di tutti i moduli personalizzati**. L’attività permette di testare i moduli personalizzati su una copia incontaminata del database aggiornato. Il file di registro del processo di aggiornamento può essere trovato nella nuova build di staging andando su `~/logs/upgrade.log`.

Importante

Nei database con moduli personalizzati installati, il codice sorgente deve essere aggiornato con la versione di destinazione di Odoo prima che l’aggiornamento venga eseguito. Se non ce ne sono, la modalità «aggiorna su commit» viene saltata, il database aggiornato viene costruito non appena verrà trasferito dalla piattaforma di aggiornamento e si uscirà dalla modalità di aggiornamento.

Consulta la pagina [Upgrade a customized database](../developer/howtos/upgrade_custom_db.html) per maggiori informazioni.

Il processo di aggiornamento standard può essere avviato inserendo la seguente riga di comando nel dispositivo che ospita il database:
    
    
    $ python <(curl -s https://upgrade.odoo.com/upgrade) test -d <your db name> -t <target version>
    

Nota

Questo comando ha alcuni requisiti per l’ambiente in cui viene eseguito:

  * alcuni comandi esterni che devono essere forniti dal sistema operativo, normalmente trovati in qualsiasi distribuzione Linux (compresa WSL). Se uno o più di essi mancano, viene visualizzato un errore;

  * L’utente del sistema che esegue il comando deve essere configurato con accesso al database. Per questo requisito, consulta la documentazione PostgreSQL relativa al [client environment](https://www.postgresql.org/docs/current/libpq-envars.html) oppure la sezione [client password file](https://www.postgresql.org/docs/current/libpq-pgpass.html).

  * Lo script deve essere in grado di raggiungere uno o più server della piattaforma di aggiornamento sia sulla porta TCP 443 che su qualsiasi porta TCP nell’intervallo tra 32768 e 60999. Questo può essere in conflitto con il firewall restrittivo e potrebbe essere necessario aggiungere un’eccezione alla configurazione del firewall.




Il seguente comando può essere utilizzato per visualizzare il supporto generale e i comandi principali:
    
    
    $ python <(curl -s https://upgrade.odoo.com/upgrade) --help
    

Un database di test aggiornato può essere richiesto anche attraverso la [pagina di aggiornamento](https://upgrade.odoo.com/).

Importante

Nei database in cui sono installati moduli personalizzati, il codice sorgente deve essere aggiornato alla versione di destinazione di Odoo prima che l’aggiornamento possa essere eseguito. Consulta la pagina [Upgrade a customized database](../developer/howtos/upgrade_custom_db.html) per maggiori informazioni.

Nota

  * Per motivi di sicurezza, solo la persona che ha inviato la richiesta di aggiornamento può scaricarlo.

  * Per motivi di archiviazione, la copia del database viene inviata al server di aggiornamento senza un filestore. Pertanto, il database aggiornato non contiene il filestore di produzione.

  * Prima di ripristinare il database aggiornato, il filestore deve essere unito al filestore di produzione per essere in grado di eseguire test nelle condizioni che saranno anche quelle della nuova versione.

  * Il database aggiornato contiene:

    * Il file `dump.sql` contiene il database aggiornato

    * Una cartella `filestore` contenente file estratti dai record del database come allegati (se ce ne sono) e nuovi file Odoo standard dalla versione Odoo di destinazione (ad es., nuove immagini, icone, loghi dei fornitori di pagamento, ecc.). Questa è la cartella che deve unita al filestore di produzione per ottenere il filestore completamente aggiornato.




Nota

È possibile richiedere database di prova multipli se vuoi provare un aggiornamento più di una volta.

Nota

Quando una richiesta di aggiornamento viene completata, un resoconto relativo all’aggiornamento viene allegato all’e-mail di aggiornamento riuscito ed è disponibile nell’app Comunicazioni per gli utenti che fanno parte del gruppo «Amministrazione/Impostazioni». Il resoconto fornisce informazioni importanti sui cambiamenti introdotti dalla nuova versione.

## Testare la nuova versione del database¶

È essenziale testare il database di prova aggiornato per assicurarti di non essere bloccato con le attività giornaliere a causa di cambiamenti relativi a viste, comportamenti o messaggi di errore una volta che l’aggiornamento è live.

Nota

I database di prova sono neutralizzati e alcune funzionalità vengono disattivate per evitare di avere un impatto sul database di produzione:

  1. Le azioni programmate sono disattivate.

  2. I server e-mail in uscita vengono disabilitati archiviando quelli esistenti e aggiungendone uno falso.

  3. I fornitori di pagamento ed i corrieri vengono ripristinati all’ambiente di test.

  4. La sincronizzazione bancaria viene disattivata. Se vuoi testare la sincronizzazione, contatta il tuo fornitore per ottenere credenziali sandbox.




Ti consigliamo di testare il maggior numero possibile di flussi aziendali per assicurarti che funzionino correttamente e per acquisire maggiore familiarità con la nuova versione.

Elenco test di base

  * Ci sono viste disattivate nel database di prova ma attive nel database di produzione?

  * Le viste che utilizzi di solito vengono ancora visualizzate correttamente?

  * I tuoi rendiconti (fatture, ordini di vendita, ecc,) vengono generati correttamente?

  * Le pagine del tuo sito web funzionano correttamente?

  * Sei capace di creare e modificare record? (Ordini di vendita, fatture, acquisti, utenti, contatti, aziende, ecc.)

  * Stai riscontrando problemi con i modelli e-mail?

  * Stai riscontrando problemi con traduzioni salvate?

  * I tuoi filtri di ricerca sono ancora presenti?

  * Puoi esportare i dati?




Example of end-to-end testing

  * Controllare un prodotto a caso nel tuo catalogo e comparare i dati di test e produzione per verificare tutto è la stessa cosa (categoria prodotto, prezzo di vendita, costo, fornitore, conti, percorsi, ecc.).

  * Acquistare il prodotto (app Acquisti).

  * Confermare la ricezione del prodotto (app Magazzino).

  * Verificare che il percorso per ricevere il prodotto sia lo stesso nel database di produzione (app Magazzino).

  * Vendere il prodotto (app Vendite) ad un cliente casuale.

  * Aprire il database del cliente (app Clienti), selezionare un cliente (o azienda) e verificare i dati.

  * Spedire il prodotto (app Magazzino).

  * Verificare che il percorso per spedire il prodotto sia lo stesso nel database di produzione (app Magazzino).

  * Convalidare la fattura del cliente (app Fatturazione o Contabilità).

  * Accreditare la fattura (emettere una nota di credito) e verificare se si comporta come nel database di produzione.

  * Controllare i risultati dei rendiconti (app Contabilità).

  * Controllare di tanto in tanto le imposte, valute, i conti bancari e l’anno fiscale (app Contabilità).

  * Realizzare un ordine online (app Sito web) dalla selezione prodotti nel negozio fino al processo di pagamento e verificare che tutto venga eseguito come nel database di produzione.




Il presente elenco **non** è esaustivo. Estendi l’esempio alle altre applicazioni in base all’utilizzo di Odoo.

Se riscontri problemi durante la fase di test del database di prova aggiornato, è possibile richiedere il supporto di Odoo accedendo alla [pagina di supporto per poi selezionare «Un problema relativo al mio futuro aggiornamento (sto testando un aggiornamento)»](https://www.odoo.com/help?stage=migration). In qualsiasi caso, è essenziale segnalare qualsiasi problema riscontrato durante la fase di test per correggerlo prima di aggiornare il database di produzione.

Potresti riscontrare differenze significative con viste, funzionalità, campi e modelli standard durante la fase di prova. Tali modifiche non possono essere annullate caso per caso. Tuttavia, se una modifica introdotta da una nuova versione impatta una personalizzazione, è responsabilità del manutentore del modulo personalizzato renderla compatibile con la nuova versione di Odoo.

Suggerimento

Non dimenticare di testare:

  * Integrazioni con software esterni (EDI, API, ecc.)

  * I flussi di lavoro tra varie applicazioni (vendite online con e-commerce convertendo un lead direttamente in ordine di vendita, consegna dei prodotti, ecc.)

  * Esportazione dati

  * Azioni automatiche

  * Le azioni del server nel menu azioni dalle viste modulo o selezionando più record dalle viste elenco




## Aggiornare il database di produzione¶

Una volta che i test sono stati completati e sei sicuro di utilizzare il database aggiornato come database principale senza problemi, è il momento di pianificare il giorno per la messa in funzione.

Il tuo database di produzione non sarà disponibile durante l’aggiornamento. Di conseguenza, consigliamo di pianificare l’aggiornamento in un momento in cui l’utilizzo del database è minimo.

Dato che il tuo database e gli script di aggiornamento standard sono in continua evoluzione, è consigliato richiedere frequentemente un altro database di prova aggiornato per garantire che il processo di aggiornamento avvenga ancora con successo, specialmente se il tempo necessario al completamento è elevato. **Inoltre, consigliamo di provare completamente il processo di aggiornamento il giorno prima di aggiornare il database di produzione**.

Importante

Andare in produzione senza prima testare potrebbe portare a:

  * Fallimento degli utenti nel sistemare le modifiche e le nuove funzionalità

  * Interruzioni dell’attività (ad es., non avere più la possibilità di convalidare un’azione)

  * Esperienza utente ridotta (ad es., un sito web e-commerce che non funziona correttamente)




L’aggiornamento di un database di produzione è simile all’aggiornamento di un database di prova ma con poche eccezioni.

Odoo OnlineOdoo.shOn-premise

Il processo è simile all’ottenimento di un database di prova aggiornato, a eccezione dell’opzione scopo che dovrebbe essere impostata su Produzione invece di Test.

Avvertimento

Una volta richiesto l’aggiornamento, il database non sarà disponibile fino al completamento. Quando il processo sarà completo, non sarà possibile ripristinare la vecchia versione.

Il processo è simile all’ottenimento di un database di prova aggiornato sul branch di Produzione.

Il processo **viene attivato non appena viene realizzato un nuovo commit** sul branch. Questo consente di sincronizzare il processo di aggiornamento con la distribuzione del codice sorgente dei moduli personalizzati aggiornato. Se non ci sono moduli personalizzati, il processo di aggiornamento viene attivato immediatamente.

Importante

Il database non è disponibile durante il processo. Se qualcosa va storto, la piattaforma ripristina automaticamente l’aggiornamento, come nel caso di un aggiornamento regolare. In caso di successo, effettua un back-up del database prima che l’aggiornamento venga creato.

L’aggiornamento dei moduli personalizzati deve avvenire con successo per completare l’intero processo di aggiornamento. Assicurati che lo stato dell’aggiornamento di staging sia riuscito prima di testarlo in produzione. Maggiori informazioni su come aggiornare i moduli personalizzati possono essere trovati alla pagina [Upgrade a customized database](../developer/howtos/upgrade_custom_db.html).

Il comando per aggiornare un database alla produzione è simile all’aggiornamento di un database di prova tranne per l’argomento `test` che deve essere sostituito da `production`:
    
    
    $ python <(curl -s https://upgrade.odoo.com/upgrade) production -d <your db name> -t <target version>
    

Un database di produzione aggiornato può essere richiesto anche attraverso la [pagina di aggiornamento](https://upgrade.odoo.com/).

Una volta che il database è stato caricato, qualsiasi modifica apportata al database di produzione **non** sarà presente nel database aggiornato. È per questo che consigliamo di non utilizzarlo durante il processo di aggiornamento.

Importante

Al momento della richiesta di un database aggiornato per motivi di produzione, la copia viene inviata senza filestore. Per cui, il filestore del database aggiornato deve essere unito al filestore di produzione prima di distribuire la nuova versione.

In caso di problemi con il database di produzione, è possibile richiedere assistenza a Odoo accedendo alla [pagina di supporto per poi selezionare «Un problema relativo al mio upgrade (produzione)»](https://www.odoo.com/help?stage=post_upgrade).

## Accordo sul livello dei servizi (SLA)¶

Con Odoo Enterprise, l’aggiornamento di un database alla versione più recente di Odoo è **gratuito** , compreso il supporto richiesto per rettificare potenziali discrepanze nel database aggiornato.

Le informazioni sui servizi di aggiornamento incluse nella licenza Enterprise sono disponibili nel [Contratto di abbonamento a Odoo Enterprise](../legal/terms/enterprise.html#upgrade). Tuttavia, la presente sezione chiarisce quali servizi di aggiornamento puoi aspettarti.

### Servizi di aggiornamento coperti dallo SLA¶

I database ospitati su piattaforme cloud Odoo (Odoo Online e Odoo.sh) o ospitati autonomamente (On-Premise) possono beneficiare dei servizi di aggiornamento in qualsiasi momento per:

  * aggiornare tutte le **applicazioni standard** ;

  * aggiornare tutte le **personalizzazioni create con l’app Studio** se Studio è ancora installato e l’abbonamento relativo è ancora attivo;

  * aggiornare tutti gli **sviluppi e personalizzazioni coperti da un abbonamento per la manutenzione delle personalizzazioni**.




I servizi di aggiornamento sono limitati alla conversione e all’adattamento tecnico di un database (moduli standard e dati) per renderlo compatibile con la versione di destinazione dell’aggiornamento stesso.

### Servizi di aggiornamento non coperti dallo SLA¶

I seguenti servizi legati all’aggiornamento **non** sono inclusi:

  * **pulizia** di dati e configurazioni pre-esistenti durante l’aggiornamento;

  * l’aggiornamento di **moduli aggiuntivi non coperti da un contratto di manutenzione** , creati in-house o da terze parti inclusi partner Odoo

  * **formazione** sull’utilizzo di funzionalità della versione aggiornata e flussi di lavoro.




Vedi anche

  * [Documentazione Odoo.sh](odoo_sh.html)

  * [Versioni di Odoo supportate](supported_versions.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/upgrade.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](neutralized_database.html "Database neutralizzato") |
  * [precedente](on_premise/community_to_enterprise.html "Passare da Community a Enterprise") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Aggiorna


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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
  *[LIFO]: Last In, First Out
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