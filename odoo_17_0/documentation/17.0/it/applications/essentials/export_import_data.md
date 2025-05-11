# Esportare e importare dati — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](in_app_purchase.html "Acquisti in-app \(IAP\)") |
  * [precedente](contacts/merge.html "Unisci contatti") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Esportare e importare dati



# Esportare e importare dati¶

In Odoo, a volte è necessario esportare o importare dati per l’esecuzione di rendiconti o per la modifica dei dati. In questa pagina troverai informazioni utili sull’esportazione e importazione dei dati all’interno e all’esterno di Odoo.

Importante

A volte, gli utenti visualizzano un errore di tipo «timeout» oppure uno dei loro record non viene elaborato a causa delle dimensioni. Questo può accadere con esportazioni di grandi dimensioni o nel caso in cui il file importato è troppo grande. Per raggirare il limite relativo alle dimensioni dei record, è necessario elaborare esportazioni e/o importazioni in piccoli gruppi.

## Esportare dati da Odoo¶

Quando lavori su un database, a volte è necessario esportare i dati in un file separato. Tale operazione può aiutarti a fare un resoconto delle tue attività anche se Odoo offre uno strumento di rendicontazione preciso e facile da usare, per ogni applicazione disponibile.

Con Odoo, i valori possono essere esportati da qualsiasi campo in qualsiasi record. Per farlo, è necessario attivare la vista elenco (__(list) icon) per gli elementi da esportare e in seguito selezionare i record che dovrebbero essere esportati. Per selezionare un record, spunta la casella di controllo accanto al record corrispondente. Infine, fai clic su __ Actions e in seguito Esporta.

Quando fai clic su Esporta apparirà la finestra a comparsa Esporta dati con diverse opzioni per i dati da esportare:

  1. Se l’opzione È un aggiornamento dati (esportazione esportabile) è contrassegnata, il sistema mostra solamente i campi che possono essere importati. È molto utile per l’aggiornamento di record esistenti. In pratica, funziona come un filtro. Se la casella non viene spuntata, vengono visualizzate più opzioni perché mostra tutti i campi e non solo quelli che possono essere importati.

  2. Durante l’esportazioni, è possibile scegliere tra due formati: `.csv` e `.xls`. Nel formato .csv`, gli elementi vengono separati da una virgola mentre il formato `.xls` raggruppa tutte le informazioni sui fogli di lavoro in un file compresi contenuto e formattazione.

  3. Questi sono gli elementi che possono essere esportati. Utilizza l’icona > (freccia destra) per visualizzare più opzioni relative a campi secondari. Utilizza l’opzione Ricerca in maniera più efficace, fai clic su tutte le frecce > (frecce a destra) per visualizzare tutti i campi.

  4. Il pulsante \+ (segno più) serve ad aggiungere campi all’elenco di Campi da esportare.

  5. L’icona ↕️ (freccia su giù) situata alla sinistra dei campi selezionati può essere utilizzata per spostare i campi su e giù, per modificare l’ordine nel quale vengono visualizzati nel file esportato. Trascina e rilascia gli elementi utilizzando l’icona ↕️ (freccia su giù).

  6. L’icona 🗑️ (cestino) viene utilizzata per rimuovere i campi. Fai clic sull’icona 🗑️ (cestino) per rimuovere un campo.

  7. Per i rendiconti ricorrenti, è utile salvare le configurazioni dell’esportazione. Seleziona tutti i campi di cui hai bisogno e fai clic sull’elenco a discesa del campo modello. Una volta qui, fai clic su Nuovo modello e dai un nome unico all’esportazione appena creata. Fai clic sull’icona 💾 (floppy disk) per salvare le impostazioni. La prossima volta che dovrà esportare lo stesso elenco, seleziona il modello correlato che avevi salvato in precedenta dal menu a discesa.




Suggerimento

È utile conoscere l’identificatore esterno del campo. Ad esempio, il campo Azienda correlata nell’interfaccia utente dell’esportazione corrisponde a _parent_id_ (identificatore esterno). Questo è utile perché in questo modo vengono esportati solo i dati che devono essere modificati e reimportati.

## Importare dati in Odoo¶

L’importazione di dati in Odoo è estremamente utile durante l’implementazione o quando è necessario aggiornare dati in massa. La seguente documentazione spiega come importare dati in un database Odoo.

Avvertimento

Le importazioni sono permanenti e **non** possono essere annullate. Tuttavia, è possibile utilizzare filtri (`creato il` o `ultima modifica`) per individuare i record modificati o creati a seguito dell’importazione.

Suggerimento

Attivando la [modalità sviluppatore](../general/developer_mode.html#developer-mode) le impostazioni di importazione visibili, nel menu a sinistra, saranno diverse. In questo modo, avrai accesso ad un menu Avanzato. Due sono le opzioni incluse nel menu avanzato: Mantieni uno storico durante l’importazione e Consenti la corrispondenza con i sottocampi.

Se il modello utilizza OpenChatter, l’opzione Mantieni uno storico durante l’importazione configura abbonamenti e invia notifiche durante l’importazione che però sarà più lenta.

Se viene selezionata l’opzione Consenti la corrispondenza con i sottocampi, tutti i sottocampi relativi ad un campo specifico verranno utilizzati per la corrispondenza con il campo Odoo durante l’importazione.

### Esordiente¶

I dati possono essere importati su quasliasi oggetto business Odoo che utilizza i formati come Excel (`.xlsx`) o CSV (`.csv`). Sono inclusi: contatti, prodotti, rendiconti bancari, registrazioni contabili e ordini.

Apri la vista dell’oggetto di cui vuoi importare dati/che vuoi popolare e fai clic su ⚙️ (Azioni) ‣ Importa record.

Dopo aver fatto clic su Importa record, Odoo mostra una nuova pagina contenente modelli che possono essere scaricati e popolati con i dati dell’azienda. Tali modelli possono essere importati con un clic, in quanto la mappatura dei dati è già stata effettuata. Per scaricare un modello fai clic su Importa modello per clienti al centro della pagina.

Importante

Al momento dell’importazione di un file di tipo CSV, Odoo fornisce delle opzioni di formattazione. Tali opzioni **nom** appaiono durante l’importazione del tipo di file Excel privato (`.xls`, `.xlsx`).

Sistema le opzioni di _formattazione_ e assicurati che tutte le colonne nel campo Odoo e nella Colonna file siano prive di errori. Infine, fai clic su Importa per importare i dati.

### Adattare un modello¶

Nello strumento di importazione vengono forniti i modelli per l’importazione di dati più comuni (contatti, prodotti, rendiconti bancari, ecc.). Aprili con qualsiasi software che supporta fogli di calcolo (_Microsoft Office_ , _OpenOffice_ , _Google Drive_ , ecc.).

Una volta che il modello è stato scaricato, segui questi step:

  * Aggiungi, elimina e ordina le colonne per adattare al meglio la struttura dei dati.

  * è fortemente consigliato di **non** rimuovere la colonna relativa all”ID esterno (scopri perché nella prossima sezione;

  * configura un ID unico per ogni record trascinando verso il basso la sequenza dell’ID nella colonna ID esterno.




Nota

Quando aggiungi una nuova colonna, Odoo potrebbe non essere in grado di mapparla automaticamente se l’etichetta non corrisponde a nessun campo in Odoo. Tuttavia, puoi mappare nuove colonne manualmente quando provi l’importazione. Cerca il campo corrispondente nel menu a discesa.

In seguito, utilizza l’etichetta del campo nel file d’importazione per assicurarti che le importazioni future avverranno con successo.

Suggerimento

Un altro modo utile per trovare i nomi corretti delle colonne da importare è esportare un file di prova usando i campi che dovrebbero essere importati. In questo modo, se non c’è un modello d’importazione campione, i nomi sono corretti.

### Importare da un’altra applicazione¶

L”ID esterno è un identificatore unico per l’elemento della riga. Per facilitare la transazione a Odoo, non esitare ad utilizzarne uno proveniente da un altro software.

La configurazione di un ID non è obbligatoria durante l’importazione ma aiuta in molti casi:

  * Aggiornamento importazioni: importa lo stesso file varie volte senza creare duplicati

  * importa campi relazione.




Per ricreare le relazioni tra vari record, l’identificatore unico dell’applicazione originale dovrebbe essere utilizzato per mapparla verso la colonna ID esterno in Odoo.

Quando un altro record viene importato ed è collegato al primo, utilizza **XXX/ID** (XXX/ID esterno) per l’identificatore unico originale. Il record può essere anche trovato utilizzando il suo nome.

Avvertimento

È necessario sottolineare che vi sarà un conflitto se due o più record hanno lo stesso _ID esterno_.

### Campi mancanti nella mappatura delle colonne¶

Odoo si impegna a cercare il tipo di campo per ogni colonan all’interno del file importato, in base alle prime dieci righe dei file.

Ad esempio, se c’è una colonna che contiene solo numeri, solo i campi di tipo _intero_ verranno presentati come opzioni.

Anche se questo comportamento sembra essere vantaggioso nella maggior parte dei casi, a volte capita che potrebbe fallire o che la colonna venga mappata ad un campo che non viene proposto per impostazione predefinita.

Se ciò si verifica, controlla l”opzione Mostra campi dei campi relazione (avanzato). In seguito, sarà disponibile una lista completa di campi per ogni colonna.

### Modificare il formato di importazione dei dati¶

Nota

Odoo è in grado di individuare automaticamente se una colonna corrisponde ad una data e cercherà di indovinare il formato da un insieme di formati più utilizzati. Il processo funziona per molti formati ma ci sono anche formati data non riconosciuti. Questo potrebbe causare confusione a causa dell’inversione giorno-mese. È difficile indovinare quale parte del formato data corrisponde al giorno e quale al mese in una data come «01-03-2016».

Durante l’importazione di un file CSV, Odoo fornisce varie opzioni di formattazione.

Per visualizzare il formato data individuato da Odoo nel file puoi controllare il Formato data mostrato quando fai clic su opzioni sotto il selettore di file. Se il formato non è corretto puoi modificarlo a piacimento utilizzando l” _ISO 8601_ per indicare il formato giusto.

Importante

L” _ISO 8601_ è uno standard internazionale che copre lo scambio a livello internazionale oltre alla comunicazione di date e dati temporali. Ad esempio, il formato data dovrebbe essere `AAAA-MM-GG`. Quindi, il 24 luglio 1981 dovrebbe essere scritto così `1981-07-24`.

Suggerimento

Al momento dell’importazione di file Excel (`.xls`, `.xlsx`), tieni a mente l’utilizzo di _celle data_ per memorizzare le date. Questo mantiene i formati data locali per la visualizzazione, indipendentemente dalla formattazione della data in Odoo. Quando importi un file CSV , utilizza la sezione Formattazione per selezionare il formato data delle colonne da importare.

### Importare numeri con simboli di valuta¶

Odoo supporta numeri con parentesi per rappresentare segni negativi così come numeri seguiti da simboli di valuta. Inoltre, Odoo individua automaticamente anche i separatori di centinaia e migliaia. Se viene utilizzato un simbolo valuta non conosciuto da Odoo, potrebbe non essere riconosciuto come numero e l’importazione non va a buon fine.

Nota

Quando importi un file CSV, il menu Formattazione appare nella colonna a sinistra. Tra queste opzioni, è possibile modificare il Separatore delle migliaia.

Esempi di numeri supportati (utilizziamo trentadue mila come esempio):

  * 32.000,00

  * 32000,00

  * 32,000.00

  * -32000.00

  * (32000.00)

  * $ 32.000,00

  * (32000.00 €)




Esempi di formati che non funzionano:

  * ABC 32.000,00

  * $ (32.000,00)




Importante

Una () (parentesi) attorno al numero indica che il numero rappresenta un valore negativo. Il simbolo di valuta **deve** essere posizionato all’interno della parentesi affinché Odoo possa riconoscerlo come un valore valuta negativo.

### Anteprima tabella di importazione non visualizzata correttamente¶

Per impostazione predefinita, l’anteprima di importazione presenta le virgole come separatori e le virgolette come delimitatori di testo. Se il file CSV non presenta queste configurazioni, modifica le impostazioni di Formattazione (visualizzate nella sezione Importa del file CSV dopo aver selezionato il file CSV).

Importante

Se il file CSV presenta una tabulazione come separatore, Odoo **non** riconosce le suddivisioni. Le opzioni relative al formato di file devono essere modificate dall’applicazione Fogli di calcolo. Consulta la seguente sezione Modificare formato file CSV

### Modificare il formato file CSV nell’applicazione Fogli di calcolo¶

Quando modifichi e salvi file CSV in app con fogli di calcolo, le impostazioni locali del tuo pc verranno applicate per la definizione di separatori e delimitatori. Odoo consiglia di utilizzare _OpenOffice_ o _LibreOffice_ , in quanto entrambe le applicazioni consentono di modificare tutte e tre le opzioni (dall’app _LibreOffice_ , vai nella finestra di dialogo “Salva come” ‣ Spunta la casella “Modifica impostazioni filtro” ‣ Salva).

Microsoft Excel ti permette di modificare i dati inseriti al momento del salvataggio (dalla :menuselection:` finestra di dialogo “Salva come” –> fai clic sull’elenco a discesa “Strumenti” –> scheda Inserimento`).

### Differenza tra ID database e ID esterno¶

Alcuni campi stabiliscono collegamenti con altri oggetti. Ad esempio, il Paese di un contatto rappresenta un collegamento ad un record dell’oggetto «Paese». Quando campi simili vengono importati, Odoo dovrà ricreare i collegamenti tra i vari record. Per aiutarti a importare questi campi, Odoo fornisce tre meccanismi.

Importante

È possibile utilizzare **solo un* meccanismo per campo importato.

Ad esempio, per indicare il Paese di un contatto, Odoo propone 3 diversi campi da importare:

  * Paese: il nome o codice del Paese

  * ID Paese/database: ID Odoo unico di un record, definito dall’ID della colonna PostgreSQL

  * ID Paese/esterno: l’ID del record indicato in un’altra applicazione (oppure il file `.XML` da cui è stato importato)




Per il Belgio, ad esempio, puoi usare uno dei 3 metodi per eseguire l’importazione:

  * Paese: `Belgio`

  * ID Paese/databse: `21`

  * ID Paese/esterno: `base.be`




In basse alle necessità dell’azienda è possibile utilizzare uno dei tre metodi per fare riferimento ai record in relazioni. Di seguito, spieghiamo quando usare i vari metodi a seconda delle necessità:

  * usa Paese: questo è il metodo più facile quando i dati provengono da file CSV creati manualmente;

  * usa ID Paese/database: da utilizzare solo se necessario. Principalmente, sono gli sviluppatori ad utilizzarla perché consente di non avere mai conflitti (potresti avere vari record con lo stesso nome ma aventi un unico ID database)

  * usa ID Paese/esterno: usa l” _ID esterno_




Quando utilizzi _ID esterni_ , importa file CSV con la colonna ID esterno che definisce l” _ID esterno_ di ogni record importato. In seguito, si può fare riferimento al record con colonne come `Campo/ID esterno`. I seguenti file CSV forniscono un esempio per prodotti e categorie.

  * [`File CSV per categorie`](../../_downloads/b00ebfcb154b6770ed0398d1a9aeb3bd/External_id_3rd_party_application_product_categories.csv)

  * [`File CSV per prodotti`](../../_downloads/c3355b134fea5ce15f88558701029667/External_id_3rd_party_application_products.csv)




### Importare campi relazione¶

In Odoo, un oggetto è sempre legato a molti altri oggetti (ad es. un prodotto è collegato a categorie prodotto, attributi, fornitori, ecc.). Per importare relazioni di questo tipo è necessario prima importare i record dell’oggetto in questione dal relativo menu a elenco.

È possibile farlo utilizzando il nome del record correlato oppure l’ID a seconda delle circostanze. L’ID viene utilizzato quando due record hanno lo stesso nome. In questo caso, aggiungi `/ ID` alla fine del titolo della colonna (ad es. per gli attributi prodotto: `Attributi prodotto/Attributo/ID`).

#### Opzioni per corrispondenze multiple sui campi¶

Ad esempio, se ci sono due categorie prodotto aventi come nome principale `Vendibile` (ad es. `Prodotti vari/Vendibili` e `Altri prodotti/Vendibili`), la convalida viene interrotta ma i dati potrebbero ancora essere importati. Tuttavia, Odoo consiglia di non importare i dati perché verranno tutti collegati alla prima categoria di tipo `Vendibile` presente nell’elenco _Categoria prodotto_ (`Prodotti vari/Vendibili`). Odoo, invece, consiglia di modificare uno dei valori duplicati o la gerarchia della categoria prodotto.

Tuttavia, se l’azienda non desidera modificare la configurazione delle categorie prodotto, Odoo suggerisce di utilizzare l” _ID esterno_ per il campo “Categoria”.

#### Importare campi relazione many2many¶

I tag dovrebbero essere separati da una virgola senza spazi. Ad esempio, se è necessario collegare un cliente a due tag: `Produttore` e `Rivenditore`, è necessario registrare “Produttore,Rivenditore” nella stessa colonna del file CSV.

  * [`File CSV per Produttore, Rivenditore`](../../_downloads/3e57aa5f999e49c58169bf4ac7eb0afb/m2m_customers_tags.csv)




#### Importare relazioni one2many¶

Se un’azienda vuole importare un ordine di vendita con più righe, è **fondamentale** inserire una riga specifica nel file CSV per ogni riga d’ordine. La prima riga d’ordine viene importata sulla stessa riga come informazioni relative all’ordine. Qualsiasi riga aggiuntiva necessità di una riga extra che non presenta informazioni nei campi relativi all’ordine.

Di seguito, un file CSV con alcuni preventivi che possono essere importati, in base a dati di prova:

  * [`File per alcuni preventivi`](../../_downloads/bdf01933a07f1490224f9d53de24764b/purchase.order_functional_error_line_cant_adpat.csv)




Il seguente file CSV mostra come importare ordini di acquisto con le relative righe d’ordine:

  * [`Ordini d'acquisto con le rispettive righe d'ordine`](../../_downloads/a72f76fb9667dfb8c2795ec523e6f4b3/o2m_purchase_order_lines.csv)




Il seguente file CSV mostra come importare clienti e i rispettivi contatti:

  * [`Clienti e relativi contatti`](../../_downloads/e4356873a7ad7151783745c8228f370a/o2m_customers_contacts.csv)




### Importare record più volte¶

Se un file importato contiente una delle colonne ID esterno o ID database, i record che sono già stati importati vengono modificati invece di essere creati di nuovo. Questa funzione è di grande aiuto in quanto permette agli utenti di importare lo stesso file CSV più volte anche dopo aver apportato modifiche tra le due importazioni.

Odoo si occupa di creare o modificare ogni record che sia nuovo o meno.

Questa funzionalità consente ad un’azienda di utilizzare lo _Strumento importa/esporta_ per modificare un insieme di record in un’app fogli di calcolo.

### Valori non forniti per un campo specifico¶

Se tutti i campi non sono configurati nel file CSV, Odoo assegna il valore predefinito ad ogni campo non definito. Tuttavia, se i campi sono privi di valori nel file CSV, il campo sarà vuoto invece di assegnare il valore predefinito.

### Esportare/importare varie tabelle da un applicazione SQL in Odoo¶

Se è necessario importare dati da varie tabelle, le relazioni devono essere ricreate tra i record appartenenti a tabelle diverse. Ad esempio, se le aziende e le persone vengono importate, il link tra ogni persona e l’azienda per la quale lavorano deve essere riprodotto.

Per gestire le relazioni tra tabelle, usa la struttura `ID esterno` di Odoo. L” `ID esterno` di un record è l’identificatore unico del record stesso in un’altra applicazione, L” `ID esterno` deve essere unico tra tutti i record di tutti gli oggetti. È una buona pratica per prefissare `ID esterno` con il nome dell’applicazione o della tabella (come “company_1”, “person_1” - invece di “1”).

Supponiamo che ci sia un database SQL con due tabelle che devono essere importate: aziende e persone. Ogni persona appartiene ad un’azienda, quindi il collegamento tra la persona e l’azienda per la quale lavora deve essere ricreato.

Testa l’esempio con un [`campione di database PostgreSQL`](../../_downloads/6a43d52743cdb4f58e92cdf08131b012/database_import_test.sql).

Per prima cosa, esporta le aziende e i loro _ID esterni_. In PSQL, digita il seguente comando:
    
    
    > copy (select 'company_'||id as "External ID",company_name as "Name",'True' as "Is a Company" from companies) TO '/tmp/company.csv' with CSV HEADER;
    

Il comando SQL genera il seguente file CSV
    
    
    External ID,Name,Is a Company
    company_1,Bigees,True
    company_2,Organi,True
    company_3,Boum,True
    

Per creare il file CSV per le persone collegate alle aziende usa il seguente comando SQL in PSQL:
    
    
    > copy (select 'person_'||id as "External ID",person_name as "Name",'False' as "Is a Company",'company_'||company_id as "Related Company/External ID" from persons) TO '/tmp/person.csv' with CSV
    

It produces the following CSV file:
    
    
    External ID,Name,Is a Company,Related Company/External ID
    person_1,Fabien,False,company_1
    person_2,Laurence,False,company_1
    person_3,Eric,False,company_2
    person_4,Ramsy,False,company_3
    

Nel file, Fabien e Laurence sono dipendenti dell’azienda Bigees (`company_1`) ed Eric lavora per l’azienda Organi. La relazione tra persone e aziende viene realizzata utilizzando l” _ID esterno_ delle aziende. L” _ID esterno_ viene prefissato dal nome della tabella per evitare conflitti ID tra persone e aziende (`person_1` e `company_1` condividono lo stesso ID 1 nel database originale).

I due file prodotti sono pronti per essere importati in Odoo senza modifiche. Dopo aver importato i due file CSV, ci sono quattro contatti e tre aziende (i primi due contatti sono collegati alla prima azienda). Tieni a mente di importare prima le aziende ed in seguito i dipendenti.

## Aggiornare dati in Odoo¶

I dati esistenti possono essere aggiornati in massa attraverso l’importazione se l”ID esterno è lo stesso.

### Preparare l’esportazione dei dati¶

Per aggiornare dati tramite importazione, accedi ai dati da aggiornare e seleziona l”|elenco| per attivare la vista corrispondente. All’estrema sinistra dell’elenco, spunta la casella di controllo di ogni record da aggiornare. In seguito, fai clic su |azioni| e seleziona __ Esporta dal menu a discesa.

Nella finestra pop-up Esporta dati che si apre, spunta la casella dal nome È un aggiornamento dati (compatibile con l’importazione). L” _ID esterno_ verrà incluso automaticamente nell’esportazione. In aggiunta, limita l’elenco dei Campi da esportare **solo** a quelli effettivamente importabili.

Nota

Il campo ID esterno **non** appare nell’elenco Campi da esportare a meno che non venga aggiunto manualmente ma è comunque incluso nell’esportazione. Tuttavia, se la casella È un aggiornamento dati (compatibile con l’importazione) è spuntata, verrà incluso nell’esportazione.

Seleziona i campi richiesti da includere nell’esportazione utilizzando le opzioni nella finestra pop-up e poi fai clic su Esporta.

### Importare dati aggiornati¶

In seguito all’esportazione, modifica i dati nel file. Quando il file è pronto, può essere importato seguendo lo stesso processo di una normale importazione di dati.

Pericolo

Durante l’aggiornamento dei dati, è estremamente importante che l” _ID esterno_ sia coerente poiché serve al sistema per identificare un record. Se un ID viene alterato o eliminato, il sistema potrebbe aggiungere un record duplicato invece di aggiornare quello esistente.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/essentials/export_import_data.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](in_app_purchase.html "Acquisti in-app \(IAP\)") |
  * [precedente](contacts/merge.html "Unisci contatti") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Esportare e importare dati


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
  *[CSV]: Valori separati da virgola