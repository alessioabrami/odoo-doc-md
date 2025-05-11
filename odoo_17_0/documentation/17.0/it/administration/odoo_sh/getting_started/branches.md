# Filiali — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](builds.html "Build") |
  * [precedente](create.html "Creare un progetto") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Filiali



# Filiali¶

## Panoramica¶

La visualizzazione dei rami offre una panoramica dei vari rami che compongono un archivio.

## Fasi¶

Odoo.sh offre tre fasi diverse per i rami: produzione, staging e sviluppo.

È possibile modificare la fase di un ramo trascinandolo e rilasciandolo all’interno della sezione desiderata.

### Produzione¶

Si tratta del ramo che contiene il codice utilizzato per l’esecuzione del database di produzione. È possibile avere un solo ramo di produzione.

Quando esegui un nuovo commit in questo ramo, il server di produzione viene aggiornato con il codice della nuova revisione per poi essere riavviato.

Se le modifiche richiedono l’aggiornamento di un modulo, come una modifica in una vista modulo e vuoi che venga eseguito automaticamente, aumenta il numero della versione del modulo nel manifesto (___manifest__.py_). In seguito, la piattaforma si occuperà di eseguire l’aggiornamento durante il quale l’istanza sarà temporaneamente non disponivile per motivi di manutenzione.

Il metodo equivale a eseguire un aggiornamento del modulo tramite il menu delle app o attraverso l’opzione `-u` della [riga di comando](../../../developer/reference/cli.html).

Nel caso in cui le modifiche nel commit impediscano al server di riavviarsi oppure se l’aggiornamento dei moduli fallisce, il server verrà ripristinato automaticamente alla revisione del codice precedente e il database verrà ripristinato alla versione precedente l’aggiornamento. Avrai ancora accesso al registro dell’aggiornamento che non è andato a buon fine così da poter risolvere il problema.

I dati demo non vengono caricati in quanto non vengono utilizzati in un database di produzione. I test di unità non vengono eseguiti perché aumenterebbero il tempo di non disponibilità del database di produzione durante gli aggiornamenti.

I partner che utilizzato progetti di prova devono essere consapevoli del fatto che il loro ramo di produzione, così come i rami di staging, verranno reimpostati automaticamente alla fase di sviluppo dopo 30 giorni.

### Staging¶

I rami di staging servono a testare le nuove funzionalità utilizzando i dati di produzione senza compromettere il database di produzione corrente con record di prova. Verranno creati database che sono duplicati neutralizzati del database di produzione.

La neutralizzazione include:

  * la disabilitazione delle azioni programmate. Se vuoi provarle, puoi attivare manualmente le azioni o riabilitarle. Tieni presente che la piattaforma le eseguirà in maniera meno frequente se nessuno utilizza il database, al fine di risparmiare risorse.

  * La disabilitazione delle e-mail in uscita intercettandole con un mailcatcher. Viene fornita anche una interfaccia oer visualizzare le e-mail inviate dal tuo database. In questo modo, non devi preoccuparti dell’invio di e-mail di prova ai tuoi contatti.

  * La configurazione di fornitori di servizi di pagamento e di spedizione in modalità test.

  * Disabilitare servizi IAP




L’ultimo database verrà conservato a vita, quelli più vecchi appartenenti allo stesso ramo potrebbero essere cestinati per fare spazio ai nuovi. Sarà valido per 3 mesi dopo i quali dovrai ricostruire il ramo. Se modifichi le impostazioni o le viste nei database, assicurati di documentare le modifiche o scriverle nei moduli del ramo utilizzando file dati XML sovrascrivendo le configurazioni o le viste predefinite.

In Odoo, i unit test non vengono eseguiti perché si basano su dati di prova che non vengono caricati nel database di produzione, Nel futuro, se Odoo supporterà l’esecuzione di unit test senza utilizzare dati di prova, Odoo.sh valuterà la possibilità di eseguire i test su database di staging.

### Sviluppo¶

I rami di sviluppo creano nuovi database utilizzando dati di prova per eseguire unit test. I moduli installati sono quelli inclusi nei rami. È possibile modificare l’elenco dei moduli da installare dalle [Impostazioni di progetto](settings.html#odoosh-gettingstarted-settings-modules-installation).

Al momento dell’esecuzione di un commit in uno dei rami, verrà avviato un nuovo server con un database creato da capo e la nuova revisione del ramo. I dati di prova vengono caricati e in seguito vengono eseguiti unit test in maniera predefinita. Il processo permette di verificare che le modifiche non compromettano nessuna delle funzionalità testate. Se lo desideri, è possibile disabilitare i test o consentire test specifici da eseguire con tag personalizzati dalle impostazioni del ramo.

Le e-mail, simili a i rami di staging, non vengono inviate ma sono intercettate da un mailcatcher e le azioni programmate non vengono eseguite quando il database non è in uso.

I database creati per i rami di sviluppo saranno attivi per 3 giorni all’incirca. Dopodiché, possono essere eliminati per fare spazio a nuovi database senza preavviso.

### Unificare i rami¶

È possibile unire i rami facilmente, trascinandoli e rilasciandoli.

Al fine di testare le modifiche dei rami di sviluppo con i dati di produzione, è possibile:

  * unire il ramo di sviluppo con il ramo di staging, trascinandolo e rilasciandolo nel ramo di staging desiderato.

  * Trascinare e rilasciare il ramo di sviluppo nella sezione titolo staging per renderlo un ramo.




Quando le ultime modifiche saranno pronte per la produzione, è possibile trascinare e rilasciare il ramo di staging nel ramo di produzione per unirli e distribuire le nuove funzionalità in produzione.

Se sei abbastanza coraggioso, puoi unire i rami di sviluppo con il ramo di produzione. Significa saltare la convalida delle modifiche con i dati di oroduzione attraverso un ramo di staging.

Puoi unire i rami di sviluppo e i rami di staging tra loro.

Per unire i rami, ovviamente è anche possibile utilizzare `git merge` direttamente nella stazione di lavoro. Odoo.sh riceverà una notifica quando le nuove revisioni verranno integrate nei rami.

L’unione di un ramo di staging con un ramo di produzione comporta solo l’unione del codice sorgente: qualsiasi modifica relativa alle impostazioni realizzata nei database di staging non viene trasferita al database di produzione.

Se le impostazioni del test cambiano nei rami di staging e vuoi che vengano applicate in produzione, puoi:

  * scrivere le modifiche relative alle impostazioni in un file dati XML che sostituiranno le impostazioni o le viste predefinite nei rami. In seguito, la versione del modulo aumenterà nel manifesto (___manifest__.py_) per attivare l’aggiornamento del modulo al momento dell’unione del ramo di staging con il ramo di produzione. Questa è la pratica più adatta per ottenere una migliore scalabilità degli sviluppi in quanto utilizzerai le funzionalità di versionamento Git per tutte le modifiche relative alle impostazioni e quindi otterrai tracciabilità delle modifiche apportate.

  * Trasferire manualmente le modifiche dal database di staging a quello di produzione tramite la funzione copia/incolla.




## Schede¶

### Storia¶

Una panoramica della cronologia del ramo:

  * i messaggi dei commit e i rispettivi autori;

  * i vari eventi collegati alla piattaforma, come le modifiche di fase, le importazioni dei database, il ripristino di backup.




Nell’angolo in alto a destra, viene visualizzato lo stato di ogni evento. Può fornire informazioni su operazioni in corso sul database (installazione, aggiornamento, importazione backup…) o i risultati (feedback test, importazione backup riuscita…). Quando un’operazione avviene con successo, è possibile accedere al database grazie al pulsante _connessione_.

### E-mail¶

Questa scheda contiene il mailcatcher e mostra una panoramica delle e-mail inviate al tuo database. Il mailcatcher è disponibile per i rami di sviluppo e staging in quanto le e-mail del database di produzione vengono davvero inviate e non solo intercettate.

### Shell¶

Accesso all’interprete dei comandi (shell) nel contenitore. È possibile eseguire comandi linux di base (`ls`, `top`) e aprire una shell nel database digitando `psql`.

Puoi aprire più schede e trascinarle e rilasciarle per organizzare il layout come preferisci, ad esempio una accanto all’altra.

Nota

Non sono garantite istanze shell di lunga durata. Le shell non attive possono essere scollegate in qualsiasi momento per liberare altre risorse.

### Redattore¶

Ambiente di sviluppo integrato online (IDE) per modificare il codice sorgente. È possibile aprire terminali, console Python e anche console Odoo Shell.

Puoi aprire più schede e trascinarle e rilasciarle per organizzare il layout come preferisci, ad esempio una accanto all’altra.

### Monitoraggio¶

Il presente link contiene varie metriche di monitoraggio per il build attuale.

È possibile ingrandire, modificare l’intervallo di tempo o selezionare una metrica specifica per ogni grafico. Le annotazioni nei grafici ti aiutano a individuare i cambiamenti nel build (importazione database, esecuzione git, ecc.).

### Log¶

Un visualizzatore per dare un’occhiata ai registri del server.

Sono disponibili vari registri:

  * install.log: i registri relativi all’installazione del database. Nel ramo di sviluppo, sono inclusi i registri dei test.

  * pip.log: i registri dell’installazione delle dipendenze Python.

  * odoo.log: i registri per il server in esecuzione.

  * update.log: i registri per gli aggiornamenti del database.

  * pg_long_queries.log: i registri delle query psql che richiedono un periodo di tempo insolito.




Se vengono aggiunte nuove righe ai registri,

È possibile mettere in pausa il recupero dei registri facendo clic sul pulsante corrispondente nell’angolo in alto a destra della vista. Il recupero viene interrotto automaticamente dopo 5 minuti. È possibile riavviarlo utilizzando il pulsante di avvio.

### Backup¶

Elenco dei backup disponibili per il download e il ripristino, la possibilità di eseguire un backup manuale e importare un database.

Odoo.sh esegue backup giornalieri del database di produzione e nello specifico: 7 al giorno, 4 a settimana e 3 mensili. Ogni backup include il dump del database, il filestore (allegati, campi binari), registri e sessioni.

Per i database di staging e sviluppo il backup non viene eseguito. Ciononostante, hai la possibilità di ripristinare un backup del database di produzione nei rami di staging, a scopo di test o per recuperare manualmente dati che sono stati eliminati accidentalmente dal database di produzione stesso.

L’elenco contiene i backup salvati nel server che ospita il tuo database di produzione. Il server conserva solo backup di un mese: 7 giornalieri e 4 settimanali.

I server dedicati al backup conservano gli stessi backup e 3 backup mensili aggiuntivi. Per ripristinare o scaricare uno di questi, [contattaci all’indirizzo](https://www.odoo.com/help).

Se unisci un commit che aggiorna la versione di uno o più moduli (in `__manifest__.py`) o le dipendenze python collegate (in `requirements.txt`), Odoo.sh eseguirà un backup in automatico (contrassegnate dal tipo di aggiornamento nell’elenco) perché il contenitore verrà modificato dall’installazione di nuovi pacchetti pip o il database verrà modificato con l’aggiornamento del modulo attivato in seguito. In questi due casi, realizziamo un backup in quanto potrebbero verificarsi problemi.

Se unisci un commit che modifica solamente una parte del codice, senza apportare le modifiche citate in precedenza, Odoo.sh non effettuerà nessun backup perché né il contenitore né il database verranno modificati quindi la piattaforma lo ritiene un comportamento abbastanza sicuro. Come ulteriore precauzione, puoi eseguire un backup manualmente prima di apportare notevoli modifiche alle risorse di produzione in caso qualcosa vada storto (i backup manuali sono disponibili per una settimana circa). Per evitare l’abuso, limitiamo i backup manuali a 5 al giorno.

La funzionalità _Importa database_ accetta archivi database nei formati forniti da:

  * il gestore standard di database Odoo (disponibile per server Odoo on-premise su `/web/database/manager`)

  * Il gestore online di database Odoo.

  * Il pulsante di download del backup Odoo.sh nella finestra «Backup».

  * Il pulsante di download del dump Odoo.sh nella [Vista build](builds.html#odoosh-gettingstarted-builds).




### Aggiorna¶

Disponibile per i rami di produzione e staging per progetti validi.

Vedi anche

[Documentazione aggiornamento](../../upgrade.html)

### Impostazioni¶

Qui puoi trovare un paio di impostazioni che si applicano solo al ramo selezionato.

**Comportamento a seguito di un nuovo commit**

Per i rami di sviluppo e di staging, è possibile modificare il comportamento del ramo dopo aver ricevuto un nuovo commit. Per impostazione predefinita, un ramo di sviluppo porterà alla creazione di un nuovo build e un ramo di staging aggiornerà il build precedente (vedi Fase di produzione). Si tratta di una pratica utile se la funzionalità sulla quale stai lavorando richiede una configurazione particolare, per evitare di doverla configurare manualmente per ogni commit. Se scegli un nuovo build per un ramo di staging, ogni volta che viene eseguito un commit verrà creata una nuova copia dal build di produzione. Un ramo che passa da staging a sviluppo verrà impostato automaticamente su «Non fare nulla».

**Installazione dei moduli**

Scegli i moduli da installare automaticamente per i build di sviluppo.

  * _Installa solo i miei moduli_ installerà solo i moduli del ramo. Si tratta di un’impostazione predefinita. I [moduli secondari](../advanced/submodules.html#odoosh-advanced-submodules) sono esclusi.

  * _Installazione completa (tutti i moduli)_ installerà i moduli del ramo, i moduli inclusi nei moduli secondari e tutti i moduli standard di Odoo. Durante l’esecuzione dell’installazione completa, il gruppo di test è disabilitato.

  * _Installa un elenco di moduli_ installerà solo i moduli specificati nell’inserimento in basso all’opzione. I nomi corrispondono ai nomi tecnici dei moduli e devono essere separati da virgole.




Se i test sono abilitati, l’insieme di moduli standard Odoo può impiegare fino ad 1 ora. L’impostazione si applica solo ai build di sviluppo. I build di staging duplicano il build di produzione e il build di produzione installa solo la base.

**Gruppo di test**

Per i rami di sviluppo, puoi scegliere di abilitare o disabilitare il gruppo di test, abilitato per impostazione predefinita. Se abilitato, puoi limitarlo specificando i [tag del test](../../../developer/reference/backend/testing.html#developer-reference-testing-selection).

**Versione Odoo**

Solo per i rami di sviluppo, è possibile modificare la versione di Odoo se vuoi testare il codice aggiornato o sviluppare funzionalità mentre il database di produzione è in fase di aggiornamento.

Inoltre, per ogni versione hai due opzioni relative all’aggiornamento del codice.

  * Puoi scegliere di beneficiare delle ultime correzioni di bug, sicurezza e prestazioni automatiche. Le fonti del server Odoo verranno aggiornate settimanalmente. Questa è «l’ultima» opzione.

  * Puoi scegliere di fissare le fonti Odoo in una revisione specifica selezionandole dall’elenco delle date. Le revisioni scadranno dopo 3 mesi. Riceverai una notifica via e-mail quando la data di scadenza sarà vicina e se non agisci verrai portato automaticamente all’utlima revisione.




**Domini personalizzati**

Qui puoi configurare domini aggiuntivi per il ramo selezionato. È possibile aggiungere altri domini _< name>.odoo.com_ o i tuoi domini personalizzati. Nell’ultimo caso, è necessario:

  * essere proprietario o acquistare il nome di dominio;

  * aggiungere il nome di dominio all’elenco;

  * configurare il nome di dominio con un record `CNAME` impostato come nome di dominio del database di produzione dal gestore dei nomi di dominio del registrar.




Ad esempio, per associare _www.mycompany.com_ al tuo database _mycompany.odoo.com_ :

  * in Odoo.sh, aggiungi _www.mycompany.com_ tra i domini personalizati dalle impostazioni di progetto,

  * nel gestore dei nomi di dominio (ad es. _godaddy.com_ , _gandi.net_ , _ovh.com_) imposta un record `CNAME` per _www.mycompany.com_ con _mycompany.odoo.com_ come valore.




I domini semplici (ad es. _mycompany.com_) non sono accettati:

  * possono essere configurati solo utilizzando record `A`;

  * i record `A` accettano solo indirizzi IP come valori;

  * l’indirizzo IP del tuo database può cambiare a seguito di un aggiornamento, del fallimento dell’hardware o del desiderio di ospitare il database in un altro Paese o continente.




Di conseguenza, i domini semplici possono smettere di funzionare a causa delle modifiche apportate all’indirizzo IP.

Inoltre, se vorresti far funzionare sia _mycompany.com_ che _www.mycompany.com_ con il tuo database, il fatto che il primo rimandi al secondo, fa parte delle [migliori pratiche SEO](https://support.google.com/webmasters/answer/7451184?hl=en) (consulta la pagina _Fornire la versione di un URL per raggiunger un documento_) per avere un URL dominante. Di conseguenza, puoi configurare solo _mycompany.com_ per il reindirizzamento verso _www.mycompany.com_. La maggior parte dei gestori di dominio hanno la funzionalitò per configurare il reindirizzamento, nota come reindirizzamento web.

**HTTPS/SSL**

Se il reindirizzamento viene configurato correttamente, la piattaforma genererà, nel giro di un’ora, un certificato SSL in automatico con [Let’s Encrypt](https://letsencrypt.org/about/) e il tuo dominio sarà accessibile attraverso HTTPS.

Dato che non è possibile attualmente configurare le tue certificazioni SSL sulla piattaforma Odoo.sh, stiamo considerando di sviluppare la funzionalità se la richiesta è notevole.

**Conformità SPF e DKIM**

Nel caso in cui il dominio degli indirizzi e-mail degli utenti utilizzi un dominio SPF (Sender Policy Framework) o DKIM (DomainKeys Identified Mail), non dimenticare di autorizzare Odoo come host di invio nelle impsotazioni del nome di dominio per aumentare il tasso di recapito delle e-mail in uscita. Le fase di configurazione vengono spiegate nella documentazione relativa a [SPF](../../../applications/general/email_communication/email_domain.html#email-domain-spf) and :ref:`DKIM<email-domain-dkim> `.

Avvertimento

Se dimentichi di configurare il tuo SPF o DKIM per autorizzare Odoo come host di invio, può causare la consegna delle e-mail come spam nelle caselle di posta dei contatti.

## Comandi shell¶

Nell’angolo in alto a destra della vista, sono disponibili vari comandi shell.

Ogni comando può essere copiato negli appunti e utilizzato in un terminale e alcuni di loro possono essere utilizzati direttamente su Odoo.sh facendo clic sul pulsante _run_. In questo caso una finestra popup richiederà all’utente di definire eventuali segnaposto come `<URL>`, `<PATH>`, …

### Clonare¶

Scarica l’archivio Git.
    
    
    $ git clone --recurse-submodules --branch master git@github.com:odoo/odoo.git
    

Clona l’archivio _odoo/odoo_.

  * `--recurse-submodules`: scarica i moduli secondari del tuo archivio. Vengono scaricati anche i moduli secondari inclusi nei moduli secondari.

  * `--branch`: verifica un ramo specifico dell’archiviso, in questo caso _master_.




Il pulsante _run_ non è disponibile per questo comando, in quanto è progettato per essere utilizzato sui tuoi dispositivi.

### Fork¶

Crea un nuovo ramo basato sul ramo attuale.
    
    
    $ git checkout -b feature-1 master
    

Crea un nuovo ramo chiamato _feature-1_ basato sul ramo _master_ e in seguito lo verifica.
    
    
    $ git push -u origin feature-1
    

Carica il nuovo ramo _feature-1_ nell’archivio remoto.

### Accorpa¶

Unisce il ramo attuale con un altro ramo.
    
    
    $ git merge staging-1
    

Unisce il ramo _staging-1_ al ramo attuale.
    
    
    $ git push -u origin master
    

Carica le modifiche appena aggiunte nel ramo _master_ nell’archivio remoto.

### SSH¶

#### Imposta¶

Per utilizzare SSH, è necessario configurare la chiave pubblica SHH del tuo profilo (se non è stato già fatto). Per farlo, segui questi step:

  1. [genera una nuova chiave SSH](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key);

  2. [copia la chiave SSH negli appunti](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) (vale solo per il primo step);

  3. incolla il contenuto copiato nelle chiavi SSH del tuo profilo e fai clic su «Aggiungi»

  4. La chiave dovrebbe apparire in basso




#### Connessione¶

Per connetterti ai build utilizzando ssh, utilizza il seguente comando in un terminale:
    
    
    $ ssh <build_id>@<domain>
    

Troverai una scelta rapida per il comando nella scheda SSH nell’angolo in alto a destra.

Se disponi dei [diritti di accesso corretti](settings.html#odoosh-gettingstarted-settings-collaborators) per il progetto, ti sarà garantito l’accesso ssh al build.

Nota

Connessioni ssh di lunga durata non sono garantite. Le connessioni inattive verranno scollegate per liberare risorse.

### Modulo secondario¶

Aggiungi un ramo da un altro archivio nel tuo ramo corrente come _modulo secondario_.

I _moduli secondari_ consentono di utilizzare moduli da altri archivi nei progetti.

La funzione dei moduli secondari è descritta in dettaglio nel capitolo [Moduli secondari](../advanced/submodules.html#odoosh-advanced-submodules) della documentazione.
    
    
    $ git submodule add -b master <URL> <PATH>
    

Aggiunge il ramo _master_ dell’archivio _< URL>_ come modulo secondario nel percorso _< PATH>_ nel ramo corrente.
    
    
    $ git commit -a
    

Conferma tutti i cambiamenti attuali.
    
    
    $ git push -u origin master
    

Carica le modifiche appena aggiunte nel ramo _master_ nell’archivio remoto.

### Elimina¶

Elimina un ramo dall’archivio.
    
    
    $ git push origin :master
    

Elimina il ramo nell’archivio remoto.
    
    
    $ git branch -D master
    

Elimina il ramo dalla copia locale dell’archivio.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/odoo_sh/getting_started/branches.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](builds.html "Build") |
  * [precedente](create.html "Creare un progetto") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Gestire i database](../../../administration.html) »
  * [Odoo.sh](../../odoo_sh.html) »
  * [Esordiente](../getting_started.html) »
  * Filiali


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: Acquisti in-app
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