# Configurazione sistema — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_gateway.html "Gateway di posta elettronica") |
  * [precedente](update.html "Aggiornamenti per correzione bug") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Configurazione sistema



# Configurazione sistema¶

In questa pagina vengono descritti gli step di base per configurare Odoo in produzione oppure su un server con connessione internet. Segue l”[installazione](../on_premise.html) e generalmente non è necessario per un sistema di sviluppo non esposto su internet.

Avvertimento

Se stai configurando un server pubblico, assicurati di leggere i nostri suggerimenti sulla sicurezza!

## dbfilter¶

Odoo è un sistema multi-tenant: un singolo sistema Odoo potrebbe eseguire e servire un certo numero di istanze del database. È anche altamente personalizzabile, con personalizzazioni (a partire dai moduli caricati) in base al «database attuale».

Non è un problema quando si lavora con il back-end (client web) come utente aziendale connesso: il database può essere selezionato una volta effettuato l’accesso e le personalizzazioni vengono caricate in seguito.

Tuttavia, è un problema per gli utenti non registrati (portale, sito web) che non sono legati ad un database: Odoo ha bisogno di sapere quale database utilizzare per il caricamento della pagina del sito web o per l’esecuzione dell’operazione. Se la multi-tenancy non viene utilizzata il problema non si pone in quanto esiste solo un database da utilizzare ma se vi sono più database accessibili, Odoo necessita di una regola per sapere quale utilizzare.

Questo è uno degli scopi del [`--db-filter`](../../developer/reference/cli.html#cmdoption-odoo-bin-db-filter): specificare in che modo il database debba essere selezionato in base al nome host (dominio) che si sta richiedendo. Il valore è un”[espressione regolare](https://docs.python.org/3/library/re.html), che include possibilmente il nome host inserito in maniera dinamica (`%h`) oppure il primo sottodominio (`%d`) attraverso il quale si sta accedendo al sistema.

Per i server che ospitano vari database in produzione, specialmente se viene utilizzato `website`, **bisogna** configurare dbfilter, altrimenti alcune opzioni non funzioneranno correttamente.

### Configurazione modelli¶

  * Mostra solo i database con nomi che iniziano con “mycompany”




nel [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config-file) imposta:
    
    
    [options]
    dbfilter = ^mycompany.*$
    

  * Mostra solo i database che corrispondono al primo sottodominio dopo `www`: ad esempio il database «mycompany» verrà mostrato se la richiesta in entrata è stata inviata a `www.mycompany.com` oppure `mycompany.co.uk` ma non per `www2.mycompany.com` o `helpdesk.mycompany.com`.




nel [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config-file) imposta:
    
    
    [options]
    dbfilter = ^%d$
    

Nota

La configurazione di un [`--db-filter`](../../developer/reference/cli.html#cmdoption-odoo-bin-db-filter) adeguato è una parte importante per la sicurezza dell’installazione. Una volta che funziona correttamente e che corrisponde ad un solo database per nome host, è fortemente consigliato bloccare l’accesso alle schermate del gestore del database e utilizzare il parametro di avvio `--no-database-list` per evitare di elencare i database e bloccare l’accesso alle schermate di gestione. Consulta anche la pagina sicurezza.

## PostgreSQL¶

Per impostazione predefinita, PostgreSQL consente solo la connessione tramite socket UNIX e connessioni di loopback (da «host locale», lo stesso dispositivo sui cui è installato il server PostgreSQL).

È possibile utilizzare il socket UNIX se vuoi che Odoo e PostgreSQL siano eseguiti sullo stesso dispositivo e se non viene fornito nessun host questa sarà l’impostazione predefinita. Se vuoi che Odoo e PostgreSQL siano eseguiti su dispositivi diversi 1 sarà necessario [ascoltare le interfacce di rete](https://www.postgresql.org/docs/12/static/runtime-config-connection.html) 2, ovvero:

  * accettare solamente connessioni loopback e [utilizzare un tunnel SSH](https://www.postgresql.org/docs/12/static/ssh-tunnels.html) tra il dispositivo su cui viene eseguito Odoo e quello su cui viene eseguito PostgreSQL. IN seguito, configurare Odoo per la connessione all’estremità corrispondente del tunnel;

  * accettare connessioni al dispositivo su cui è installato Odoo, possibilmente tramite SSL (consultare [Impostazioni connessione PostgreSQL](https://www.postgresql.org/docs/12/static/runtime-config-connection.html) per i dettagli), per poi configurare Odoo per la connessione alla rete.




### Esempio di configurazione¶

  * Autorizzare la connessione TCP su localhost;

  * Autorizzare la connessione TCP dalla rete 192.168.1.x.




In `/etc/postgresql/<YOUR POSTGRESQL VERSION>/main/pg_hba.conf` configura:
    
    
    # IPv4 local connections:
    host    all             all             127.0.0.1/32            md5
    host    all             all             192.168.1.0/24          md5
    

In `/etc/postgresql/<YOUR POSTGRESQL VERSION>/main/postgresql.conf` configura:
    
    
    listen_addresses = 'localhost,192.168.1.2'
    port = 5432
    max_connections = 80
    

### Configurare Odoo¶

Per impostazione predefinita, Odoo si connette al postgres locale su un socket UNIX tramite la porta 5432. Questo può essere sostituito utilizzando [l’impostazione del database](../../developer/reference/cli.html#reference-cmdline-server-database) quando la distribuzione Postgres non è locale e/o non utilizza le impostazioni predefinite dell’installazione.

I [programmi di installazione](packages.html) creeranno automaticamente un nuovo utente (`odoo`) configurandolo come utente del database.

  * Le pagine di gestione del database sono protette dall’impostazione `admin_passwd` che può essere selezionata utilizzando esclusivamente i file di configurazione e viene verificata prima di modificare il database. Deve essere impostata su un valore generato in modo casuale per garantire che terzi non possano utilizzare questa interfaccia.

  * Tutte le operazioni del database usano le [opzioni del database](../../developer/reference/cli.html#reference-cmdline-server-database) compresa la pagina di gestione del database. Per far sì che la pagina di gestione del database funzioni è necessario che l’utente PostgreSQL abbia i diritti `createdb`.

  * Gli utenti possono eliminare database in autonomia. Affinché la pagina di gestione dei database sia completamente non funzionale, l’utente PostgreSQL deve essere creato con `no-createdb` e il database deve appartenere ad un utente PostgreSQL diverso.

Avvertimento

L’utente PostgreSQL _non deve_ essere un utente con privilegi avanzati.




#### Esempio di configurazione¶

  * Collegati ad un server PostgreSQL su 192.168.1.2

  * Porta 5432

  * Utilizza un account utente «Odoo»

  * Con «pwd» come password

  * Filtra solo i db che hanno un nome che inizia con «mycompany»




nel [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config-file) imposta:
    
    
    [options]
    admin_passwd = mysupersecretpassword
    db_host = 192.168.1.2
    db_port = 5432
    db_user = odoo
    db_password = pwd
    dbfilter = ^mycompany.*$
    

### SSL tra Odoo e PostgreSQL¶

A partire da Odoo 11.0, è possibile stabilire una connessione SSL tra Odoo e PostgreSQL. In Odoo db_sslmode controlla la sicurezza SSL della connessione con il valore scelto fra “disable”, “allow”, “prefer”, “require”, “verify-ca” o “verify-full”.

[Documentazione PostgreSQL](https://www.postgresql.org/docs/12/static/libpq-ssl.html)

## Server integrato¶

Odoo include server HTTP, cron e live-chat che utilizzano il multi-threading oppure il multi-processing.

Il server **multi-threaded** è un server più semplice utilizzato in primo luogo per sviluppi, dimostrazioni e per la compatibilità con vari sistemi operativi (incluso Windows). Per ogni nuova richiesta HTTP, viene generato un nuovo thread anche per connessioni di lunga durata come websocket. Vengono generati anche thread cron daemon. A causa di una limitazione di Python (GIL), l’hardware non viene utilizzato nel migliore dei modi.

Il server multithreaded è il server predefinito anche per container docker. Viene selezionato quando l’opzione [`--workers`](../../developer/reference/cli.html#cmdoption-odoo-bin-workers) non viene selezionata o impostata a `0`.

Il server **multi-processing** è un server completo utilizzato principalmente per la produzione. Non è sottoposto alle stesse limitazioni di Python (GIL) per quanto riguarda l’uso delle risorse, quindi sfrutta al meglio l’hardware. Al momento dell’avvio del server viene creato un pool di worker. Le nuove richieste HTTP vengono messe in coda dal SO fino al momento in cui ci saranno worker pronti a elaborarle. Su un’altra porta viene generato un worker aggiuntivo HTTP guidato dagli eventi per la chat dal vivo. Inoltre, vengono generati anche worker cron extra. Un process reaper configurabile monitora l’uso delle risorse e può bloccare/riavviare i worker non funzionanti.

Il server multi-processo è opzionale. Viene selezionato impostando l’opzione [`--workers`](../../developer/reference/cli.html#cmdoption-odoo-bin-workers) con un numero intero non nullo.

Nota

Il server multi-processing non è disponibile su Windows perché altamente personalizzato per i server Linux.

### Calcolo del numero di worker¶

  * Regola generale: (#CPU * 2) + 1

  * I worker cron necessitano un CPU

  * 1 worker ~= 6 utenti in contemporanea




### Calcolo dimensioni memoria¶

  * Consideriamo che il 20% delle richieste sono richieste pesanti mentre l’80% sono semplici

  * Si stima che un worker pesante, quando tutti i campi calcolati sono ben progettati così come le richieste SQL, consumi circa 1GB di RAM

  * Si stima che worker più leggero, nello stesso scenario, consumi circa 150MB di RAM




RAM necessaria = #worker * ( (light_worker_ratio * light_worker_ram_estimation) + (heavy_worker_ratio * heavy_worker_ram_estimation) )

### LiveChat¶

Nel multi-processing, viene avviato automaticamente un worker LiveChat dedicato che ascolta [`--gevent-port`](../../developer/reference/cli.html#cmdoption-odoo-bin-gevent-port). Per impostazione predefinita, le richieste HTTP continueranno ad accedere ai worker HTTP normali e non al worker LiveChat. Devi sviluppare una proxy davanti Odoo e redirigere le richieste in entrata, il cui percorso inizia con `/websocket/`, verso il worker della LiveChat. Inoltre, devi avviare Odoo in [`--proxy-mode`](../../developer/reference/cli.html#cmdoption-odoo-bin-proxy-mode) affinché utilizzi le intestazioni clienti reali (come nome host, schema e IP) invece di quelli del proxy.

### Esempio di configurazione¶

  * Server con 4 CPU, 8 Thread

  * 60 utenti concorrenti

  * 60 utenti / 6 = 10 <\- numero teorico di worker necessari

  * (4 * 2) + 1 = 9 <\- numero massimo teorico di worker

  * Utilizzeremo 8 worker + 1 per cron. Utilizzeremo anche un sistema di monitoraggio per misurare il caricamento della cpu e verificare che sia tra 7 e 7.5.

  * RAM = 9 * ((0.8*150) + (0.2*1024)) ~= 3GB RAM for Odoo




nel [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config-file):
    
    
    [options]
    limit_memory_hard = 1677721600
    limit_memory_soft = 629145600
    limit_request = 8192
    limit_time_cpu = 600
    limit_time_real = 1200
    max_cron_threads = 1
    workers = 8
    

## HTTPS¶

Odoo trasmette le informazioni di autenticazione tramite testo non crittografato indipendentemente dal tipo di accesso ovvero sito web/client web o servizio web. Questo significa che una distribuzione sicura di Odoo deve utilizzare HTTPS3. La terminazione SSL può essere implementata tramite qualsiasi proxy di terminazione SSL ma richiede la seguente configurazione:

  * Attiva il [`proxy mode`](../../developer/reference/cli.html#cmdoption-odoo-bin-proxy-mode) in Odoo. Da attivare solamente se Odoo si trova dietro un proxy invertito.

  * Configura la proxy di terminazione SSL ([Esempio di terminazione Nginx](https://nginx.com/resources/admin-guide/nginx-ssl-termination/)).

  * Configura il proxy ([Esempio proxy Nginx](https://nginx.com/resources/admin-guide/reverse-proxy/)).

  * Il tuo proxy di terminazione SSL deve reindirizzare automaticamente anche le connessioni non sicure verso una porta sicura.




### Esempio di configurazione¶

  * Reindirizza le richieste HTTP verso HTTPS

  * Richieste proxy verso Odoo




nel [file di configurazione](../../developer/reference/cli.html#reference-cmdline-config-file) imposta:
    
    
    proxy_mode = True
    

nel `/etc/nginx/sites-enabled/odoo.conf` configura:
    
    
    #odoo server
    upstream odoo {
      server 127.0.0.1:8069;
    }
    upstream odoochat {
      server 127.0.0.1:8072;
    }
    map $http_upgrade $connection_upgrade {
      default upgrade;
      ''      close;
    }
    
    # http -> https
    server {
      listen 80;
      server_name odoo.mycompany.com;
      rewrite ^(.*) https://$host$1 permanent;
    }
    
    server {
      listen 443 ssl;
      server_name odoo.mycompany.com;
      proxy_read_timeout 720s;
      proxy_connect_timeout 720s;
      proxy_send_timeout 720s;
    
      # SSL parameters
      ssl_certificate /etc/ssl/nginx/server.crt;
      ssl_certificate_key /etc/ssl/nginx/server.key;
      ssl_session_timeout 30m;
      ssl_protocols TLSv1.2;
      ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
      ssl_prefer_server_ciphers off;
    
      # log
      access_log /var/log/nginx/odoo.access.log;
      error_log /var/log/nginx/odoo.error.log;
    
      # Redirect websocket requests to odoo gevent port
      location /websocket {
        proxy_pass http://odoochat;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection $connection_upgrade;
        proxy_set_header X-Forwarded-Host $http_host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Real-IP $remote_addr;
    
        add_header Strict-Transport-Security "max-age=31536000; includeSubDomains";
        proxy_cookie_flags session_id samesite=lax secure;  # requires nginx 1.19.8
      }
    
      # Redirect requests to odoo backend server
      location / {
        # Add Headers for odoo proxy mode
        proxy_set_header X-Forwarded-Host $http_host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_redirect off;
        proxy_pass http://odoo;
    
        add_header Strict-Transport-Security "max-age=31536000; includeSubDomains";
        proxy_cookie_flags session_id samesite=lax secure;  # requires nginx 1.19.8
      }
    
      # common gzip
      gzip_types text/css text/scss text/plain text/xml application/xml application/json application/javascript;
      gzip on;
    }
    

### Protezione avanzata HTTPS¶

Aggiungi l’intestazione `Strict-Transport-Security` a tutte le richieste per evitare che i browser inviino richieste HTTP semplici a questo dominio. Sarà necessario mantenere sempre un servizio HTTPS funzionante con un certificato valido su questo dominio, altrimenti gli utenti visualizzeranno avvisi di sicurezza o potrebbero non essere in grado di accedervi.

Forza le connessioni HTTPS per un anno per ogni visitatore in NGINX con la riga:
    
    
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains";
    

È possibile definire una configurazione aggiuntiva per il cookie `session_id`. La bandiera `Secure` può essere aggiunta per garantire che non venga mai trasmesso via HTTP e `SameSite=Lax` per impedire [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) autenticati.
    
    
    # requires nginx 1.19.8
    proxy_cookie_flags session_id samesite=lax secure;
    

## Odoo come applicazione WSGI¶

È possibile montare Odoo come applicazione [WSGI](https://wsgi.readthedocs.org/) standard. Odoo fornisce la base per uno script launcher WSGI come `odoo-wsgi.example.py`. Lo script dovrebbe essere personalizzato (possibilmente dopo averlo copiato dalla cartella di configurazione) per effettuare la configurazione direttamente in `odoo.tools.config` invece di farlo attravero la riga di comando o il file di configurazione.

Tuttavia, il server WSGI esporrà solamente l’endpoint HTTP principale per il client web, il sito web e l’API del servizio web. Siccome Odoo non controlla più la creazione dei worker, non è possibile configurare cron o worker per la chat dal vivo.

### Worker cron¶

È necessario avviare uno dei server Odoo integrati a fianco del server WSGI per elaborare i lavori cron. Il server in question deve essere configurato per elaborare solo i cron e non le richieste HTTP utilizzando l’opzione [`--no-http`](../../developer/reference/cli.html#cmdoption-odoo-bin-no-http) cli oppure l’impostazione `http_enable = False` del file di configurazione.

Sui sistemi di tipo Linux, è consigliato utilizzare un server multi-processing rispetto al multi-threading per beneficiare di un uso hardware e una stabilità migliori, ad esempio utilizzando le opzioni cli [`--workers=-1`](../../developer/reference/cli.html#cmdoption-odoo-bin-workers) e [`--max-cron-threads=n`](../../developer/reference/cli.html#cmdoption-odoo-bin-max-cron-threads).

### LiveChat¶

L’utilizzo di un server WSGI compatibile con gevent è richiesto per la corretta esecuzione delle funzionalità della chat dal vivo. Il server dovrebbe essere in grado di gestire diverse connessioni simultanee di lunga durata ma non ha bisogno di una grande potenza di elaborazione. Tutte le richieste i cui percorsi iniziano con `/websocket/` dovrebbero essere reindirizzate a quel server. Per tutte le altre richieste deve essere utilizzato un server WSGI regolare (basato su thread/processo).

Il server cron di Odoo può anche essere utilizzato per rispondere alle richieste della chat dal vivo. È sufficiente deselezionare l’opzione cli [`--no-http`](../../developer/reference/cli.html#cmdoption-odoo-bin-no-http) dal server cron e assicurarsi che le richieste il cui percorso inizia con `/websocket/` siano indirizzate al server, su [`--http-port`](../../developer/reference/cli.html#cmdoption-odoo-bin-http-port) (server multi-threading) oppure su [`--gevent-port`](../../developer/reference/cli.html#cmdoption-odoo-bin-gevent-port) (server multi-processing).

## Servire file statici e allegati¶

Per ragioni legate alla comodità di sviluppo, Odoo serve direttamente tutti i file statici e gli allegati nei propri moduli. Questo potrebbe non essere ideale in termini di prestazioni e i file statici, in generale, devono essere serviti da un server HTTP statico a sua volta.

### Servire file statici¶

I file statici Odoo si trovano nella cartella `static/` di ogni modulo, quindi i file statici possono essere serviti intercettando tutte le richieste verso `/_MODULE_ /static/_FILE_` e individuando il modulo giusto (e file) nei vari percorsi di accesso ai componenti aggiuntivi.

È consigliato configurare l’intestazione `Content-Security-Policy: default-src 'none'` su tutte le immagini consegnate dal server web. Non è strettamente necessario in quanto gli utenti non possono modificare/inserire del contenuto nella cartella `static/` dei moduli e le immagini esistenti sono definitive (non recuperano nuove risorse in autonomia). Tuttavia, è una buona pratica.

Utilizzando la configurazione NGINX (https), è necessario aggiungere i seguenti blocchi `map` e `location` per servire i file statici tramite NGINX.
    
    
    map $sent_http_content_type $content_type_csp {
        default "";
        ~image/ "default-src 'none'";
    }
    
    server {
        # the rest of the configuration
    
        location @odoo {
            # copy-paste the content of the / location block
        }
    
        # Serve static files right away
        location ~ ^/[^/]+/static/.+$ {
            # root and try_files both depend on your addons paths
            root ...;
            try_files ... @odoo;
            expires 24h;
            add_header Content-Security-Policy $content_type_csp;
        }
    }
    

Le direttive `root` e `try_files` dipendono dall’installazione, nello specifico dal [`--addons-path`](../../developer/reference/cli.html#cmdoption-odoo-bin-addons-path).

Example

Debian packageGit sources

Nel caso in cui Odoo sia stato installato tramite **pacchetti Debian** per le versioni Community ed Enterprise e che l”[`--addons-path`](../../developer/reference/cli.html#cmdoption-odoo-bin-addons-path) sia `'/usr/lib/python3/dist-packages/odoo/addons'`.

Il `root` e `try_files` devono corrispondere a:
    
    
    root /usr/lib/python3/dist-packages/odoo/addons;
    try_files $uri @odoo;
    

Diciamo che Odoo è stato installato tramite **fonti** , che gli archivi git sia della versione Community che Enterprise sono stati clonati rispettivamente in `/opt/odoo/community` e `/opt/odoo/enterprise` e che il [`--addons-path`](../../developer/reference/cli.html#cmdoption-odoo-bin-addons-path) corrisponde a `'/opt/odoo/community/odoo/addons,/opt/odoo/community/addons,/opt/odoo/enterprise'`.

Il `root` e `try_files` devono corrispondere a:
    
    
    root /opt/odoo;
    try_files /community/odoo/addons$uri /community/addons$uri /enterprise$uri @odoo;
    

### Servire degli allegati¶

Gli allegati sono file archiviati nel filestore il cui accesso è regolamentato da Odoo. Non è possibile accedervi direttamente tramite un server web statico in quanto l’accesso richiede diversi lookup nel database per determinare dove vengono archiviati i file e se l’utente attuale può accedervi o meno.

Tuttavia, una volta che il file è stato localizzato e i diritti di accesso verificati da Odoo, è una buona idea servire il file utilizzando un server web statico invece di Odoo. Affinché Odoo deleghi il servizio dei file al server web statico, le estensioni [X-Sendfile](https://tn123.org/mod_xsendfile/) (apache) o [X-Accel](https://www.nginx.com/resources/wiki/start/topics/examples/x-accel/) (nginx) devono essere abilitate e configurate sul server web statico. Una volta eseguita la configurazione, avvia Odoo con la bandiera CLI [`--x-sendfile`](../../developer/reference/cli.html#cmdoption-odoo-bin-x-sendfile) CLI flag (la bandiera è utilizzata sia per X-Sendfile che X-Accel).

Nota

  * L’estensione X-Sendfile per apache (e server web compatibili) non richiede nessuna configurazione aggiuntiva.

  * L’estensione X-Accel per NGINX **richiede** una configurazione aggiuntiva:
        
        location /web/filestore {
            internal;
            alias /path/to/odoo/data-dir/filestore;
        }
        

Nel caso in cui non si conosca il percorso del filestore, avvia Odoo con l’opzione [`--x-sendfile`](../../developer/reference/cli.html#cmdoption-odoo-bin-x-sendfile) e vai sull’URL `/web/filestore` direttamente tramite Odoo (non aprire l’URL tramite NGINX). In seguito, comparirà un avviso con un messaggio contenente le impostazioni di cui hai bisogno.




## Sicurezza¶

Per iniziare, ricordati che la protezione di un sistema informatico è un processo continuo e non un’operazione singola. In qualsiasi momento, sarai sicuro tanto quanto il link più debole.

La seguente sezione non corrisponde ad una lista definitiva di misure che ti aiuteranno ad evitare problemi relativi alla sicurezza. Si tratta solamente di un riassunto delle principali azioni da includere nel piano di sicurezza. Il resto verrà dalle migliori pratiche di sicurezza per il tuo sistema operativo e per la distribuzione, migliori pratiche in termini di utenti, password, gestione degli accessi, ecc.

Quando implementi un server con accesso a internet, assicurati di prendere in considerazione i seguenti argomenti:

  * configura sempre una password forte per l’amministratore super-admin e limita l’accesso alle pagine di gestione del database non appena configuri il sistema. Consulta la sezione Sicurezza gestione database.

  * Scegli nomi utente unici e password forti per tutti gli account di tipo amministratore e per ogni database. Non utilizzare «admin» come nome utente. Non utilizzare tali dati per operazioni giornaliere ma solo per controllare/gestire l’installazione. Non utilizzare _mai_ qualsiasi password predefinita come admin/admin, nemmeno per databse di test/staging.

  * **Non** installare dati demo su server con accesso a internet. I database con dati demo contengono nomi utente e password predefiniti che possono essere utilizzati per accedere ai tuoi sistemi e causare problemi significativi, anche su sistemi di staging/dev.

  * Utilizza i filtri database appropriati ( [`--db-filter`](../../developer/reference/cli.html#cmdoption-odoo-bin-db-filter)) per limitare la visibilità dei tuoi database secondo il nome host. Consulta la sezione dbfilter. Potresti anche utilizzare [`-d`](../../developer/reference/cli.html#cmdoption-odoo-bin-d) per fornire la tua lista (separata da virgole) di database disponibili da filtrare invece di lasciare che il sistema li recuperi tutti dal backend del database.

  * Una volta che il `db_name` e il `dbfilter` sono stati configurati e corrispondono ad un solo database per nome host, devi impostare l’opzione `list_db` su `Falso` per evitare di elencare interamente i database e bloccare l’accesso alle pagine di gestione del database stesso (mostrato come opzione riga di comando [`--no-database-list`](../../developer/reference/cli.html#cmdoption-odoo-bin-no-database-list))

  * Assicurati che l’utente PostgreSQL ([`--db_user`](../../developer/reference/cli.html#cmdoption-odoo-bin-r)) _non_ sia un super-user e che i tuoi database appartengano ad un utente diverso. Ad esempio, potrebbero appartenere dal super-user `postgres` se stai utilizzando un `db_user` dedicato non privilegiato. Consulta anche la sezione Configurare Odoo.

  * Aggiorna regolarmente le installazioni installando le ultime versioni, sia tramite GitHub che scaricandole da <https://www.odoo.com/page/download> oppure [http://nightly.odoo.com](http://nightly.odoo.com/).

  * Configura il server in modalità multi-process con le limitazioni adatte corrispondenti all’uso tipico (memoria/CPU/timeout). Consulta anche la sezione Server integrato.

  * Esegui Odoo dietro un server web fornendo una terminazione HTTPS con un certificato SSL valido per evitare attacchi di tipo eavesdropping su comunicazioni in testo non crittografato. I certificati SSL sono economici ed esistono molte opzioni gratuite. Configura il proxy web per limitare la dimensione delle richieste, configura timeout appropriati e abilita l’opzione [`proxy mode`](../../developer/reference/cli.html#cmdoption-odoo-bin-proxy-mode). Consulta anche la sezione HTTPS.

  * Se hai bisogno di abilitare l’accesso SSH remoto ai tuoi server, assicurati di configurare una password forte per **tutti** gli account e non solo `root`. È fortemente consigliato disattivare completamente autenticazioni basate su password e consentire solo autenticazioni con chiave pubblica. Considera anche la possibilità di limitare l’accesso tramite un VPN, consentendo solo IP verificati nel firewall e/o eseguire un sistema di rilevamento di forza bruta come `fail2ban` o equivalenti.

  * Prendi in considerazione anche l’installazione di un limitatore di velocità appropriato sul proxy o firewall per evitare attacchi di tipo forza bruta e denial of service. Consulta anche la sezione Bloccare attacchi di forza bruta per misure specifiche.

Molti fornitori di rete forniscono la mitigazione automatica per attacchi di tipo Distributed Denial of Service (DDoS) ma si tratta spesso di un servizio opzionale quindi dovresti parlare con loro.

  * Laddove possibile, ospita le istanze di dimostrazione/test/staging destinate al pubblico su vari dispositivi diversi da quelli di produzione. Applica le stesse misure di sicurezza utilizzate per la produzione.

  * Se il server Odoo destinato al pubblico ha accesso a risorse o servizi di rete interni sensibili (ad es. tramite VLAN privata), implementa regole firewall appropriate per proteggere le risorse interne. In questo modo si garantisce che il server Odoo non possa essere utilizzato accidentalmente (o come risultato di azioni di utenti malintenzionati) per accedere o interrompere tali risorse interne. Generalmente, questo può essere effettuato applicando una regola DENY in uscita predefinita e in seguito autorizzando esplicitamente l’accesso solo a risorse interne di cui il server Odoo ha bisogno. È possibile utilizzare anche [Systemd IP traffic access control](http://0pointer.net/blog/ip-accounting-and-access-lists-with-systemd.html) per implementare il controllo dell’accesso alla rete per processo.

  * Se il server Odoo destinato al pubblico si trova dietro un Web Application Firewall, un bilanciatore di carico, un servizio di protezione DdoS trasparente (come CloudFlare) o un dispositivo simile a livello di rete, potresti voler evitare l’accesso diretto al sistema Odoo. In generale, è difficile mantenere segreti gli indirizzi IP dell’endpoint dei server Odoo. Ad esempio, possono apparire nei registri del server web quando si consultano i sistemi pubblici o nelle intestazioni delle e-mail inviate da Odoo. In una situazione simile, potresti voler configurare il firewall in modo che gli endpoint non siano accessibili pubblicamente ad eccezione gli indirizzi IP specifici del WAF, del bilanciatore o del servizio proxy. I fornitori di servizi come CloudFlare di solito mantengono un elenco pubblico degli intervali dell’indirizzo IP proprio per questo motivo.

  * Se sei l’host di più clienti, isola i dati e i file dei clienti utilizzando contenitori o tecniche «jail» appropriati.

  * Configura back-up giornalieri dei database e dei dati filestore per poi copiarli in un server di archiviazione remota che non è accessibile dal server stesso.

  * La distribuzione di Odoo su Linux è fortemente consigliata rispetto a Windows. Se scegli di utilizzare comunque una piattaforma Windows, è necessario condurre un’analisi approfondita del server in materia di sicurezza, che non rientra nell’ambito di questa guida.




### Bloccare attacchi di forza bruta¶

Per sviluppi su internet, gli attacchi di forza bruta alle password degli utenti sono molto comuni e questa minaccia non dovrebbe essere ignorata per i server Odoo. Ad ogni tentativo di accesso, Odoo crea una voce di registro e riporta il risultato: successo o fallimento, insieme al login di destinazione e all’IP di origine.

Le voci di registro avranno la seguente struttura.

Accesso non riuscito:
    
    
    2018-07-05 14:56:31,506 24849 INFO db_name odoo.addons.base.res.res_users: Login failed for db:db_name login:admin from 127.0.0.1
    

Accesso riuscito:
    
    
    2018-07-05 14:56:31,506 24849 INFO db_name odoo.addons.base.res.res_users: Login successful for db:db_name login:admin from 127.0.0.1
    

I registri possono essere analizzati facilmente grazie ad un sistema di prevenzione delle intrusioni come `fail2ban`.

Ad esempio, la definizione del seguente filtro fail2ban deve corrispondere ad un accesso non riuscito:
    
    
    [Definition]
    failregex = ^ \d+ INFO \S+ \S+ Login failed for db:\S+ login:\S+ from <HOST>
    ignoreregex =
    

Questo potrebbe essere utilizzato con una definizione jail per bloccare l’IP attaccato su HTTP(S).

Ecco come potrebbe apparire il blocco dell’IP per 15 minuti al momento dell’individuazione di 10 tentativi di accesso falliti dallo stesso indirizzo IP in 1 minuto:
    
    
    [odoo-login]
    enabled = true
    port = http,https
    bantime = 900  ; 15 min ban
    maxretry = 10  ; if 10 attempts
    findtime = 60  ; within 1 min  /!\ Should be adjusted with the TZ offset
    logpath = /var/log/odoo.log  ;  set the actual odoo log path here
    

### Sicurezza gestore database¶

Configurare Odoo ha menzionato `admin_passwd`.

L’impostazione viene utilizzata su tutte le pagine di gestione dei database (per creare, eliminare, eseguire il dump o ripristinare un database).

Se le pagine di gestione non sono accessibili, è necessario impostare l’opzione `list_db` su `Falso` per bloccare l’accesso a tutte le pagine di gestione e selezione del database.

Avvertimento

È fortemente consigliato disabilitare il Gestore di database per ogni sistema su internet! È concepito come uno strumento di sviluppo/dimostrazione per rendere più semplice e rapida la creazione e gestione di database. Non è progettato per l’uso in produzione e potrebbe esporre funzionalità agli utenti malintenzionati. Inoltre, non è progettato per gestire grandi database e potrebbe attivare limiti di memoria.

Sui sistemi di produzione, le operazioni di gestione dei database devono essere sempre eseguite dall’amministratore di sistema compreso il provisioning di nuovi database e i backup automatici.

Assicurati di configurare un parametro `db_name` appropriato (e a scelta, anche `dbfilter`) così il sistema può determinare il database di destinazione per ogni richiesta, altrimenti gli utenti verranno bloccati in quanto non gli sarà consentito di scegliere in autonomia il database.

Se le pagine di gestione devono essere accessibili solo da una serie di dispositivi selezionati, utilizza le funzionalità del server proxy per bloccare l’accesso a tutti i percorsi che iniziano con `/web/database` eccetto (forse) `/web/database/selector` che mostra la pagina di selezione dei database.

Se la pagina di gestione del database deve essere accessibile, l’impostazione `admin_passwd` deve essere modificata dall”`admin` predefinito: la password viene controllata prima di consentire operazioni di modifica del database.

La password deve essere conservata in modo sicuro e dovrebbe essere generata in maniera casuale, ad esempio.
    
    
    $ python3 -c 'import base64, os; print(base64.b64encode(os.urandom(24)))'
    

che genera una stringa stampabile pseudocasuale di 32 caratteri.

### Ripristinare la password master¶

Potrebbero essevi istanze per le quali la password master è stata smarrita o è compromessa e deve essere reimpostata. Il seguente processo è per gli amministratori di sistema di un database Odoo on-premise e spiega in maniera dettagliata come resettare manualmente e ri-crittografare la password master.

Vedi anche

Per maggiori informazioni relative alla modifica della password di un account Odoo.com, consulta la seguente documentazione: [Modificare la password dell’account Odoo.com](../odoo_accounts.html#odoocom-change-password).

Quando viene creato un nuovo database on-premise, viene generata una password master casuale. Odoo consiglia di utilizzare la password per proteggere il database. La password viene implementata per impostazione predefinita, quindi esiste una password master sicura per ogni distribuzione Odoo on-premise.

Avvertimento

Al momento della creazione di un database Odoo on-premise, l’installazione è accessibile a chiunque su internet fino a quando viene configurata la password per proteggere il database.

La password master viene specificata nel file di configurazione di Odoo (`odoo.conf` oppure `odoorc` (file nascosto)). La password master di Odoo è necessari aper modificare, creare o eliminare un database attraverso l’interfaccia utente grafica (GUI).

#### Individuare file di configurazione¶

Per prima cosa, apri il file di configurazione Odoo (`odoo.conf` o `odoorc` (file nascosto)).

WindowsLinux

Il file di configurazione si trova in: `c:\ProgramFiles\Odoo{VERSION}\server\odoo.conf`

In base al tipo di installazione di Odoo sul dispositivo Linux, il file di configurazione potrebbe essere situato in uno dei seguenti due posti:

  * Pacchetto installazione: `/etc/odoo.conf`

  * Fonte installazione: `~/.odoorc`




#### Modificare password vecchie¶

Una volta che è stato aperto il file appropriato, procedi con la modifica della password precedente nel file di configurazione, sostituendola con una password temporanea.

Graphical user interfaceCommand-line interface

Dopo aver individuato il file di configurazione, aprilo utilizzando una (GUI). È possibile farlo facendo semplicemente doppio clic sul file. In seguito, il dispositivo dovrebbe disporre di una GUI predefinita tramite cui aprire il file.

Successivamente, modifica la riga della password master `admin_passwd = $pbkdf2-sha…` in `admin_passwd = newpassword1234`, ad esempio. La password può essere di qualsiasi tipo purché sia salvato temporaneamente. Assicurati di modificare tutti i caratteri dopo `=`.

Example

La riga appare come segue: `admin_passwd = $pbkdf2-sh39dji295.59mptrfW.9z6HkA$w9j9AMVmKAP17OosCqDxDv2hjsvzlLpF8Rra8I7p/b573hji540mk/.3ek0lg%kvkol6k983mkf/40fjki79m`

La riga modificata appare come segue: `admin_passwd = newpassword1234`

Modifica la riga della password master utilizzando il comando Unix descritto dettagliatamente in basso.

Collegati al terminale del server Odoo tramite il protocollo Secure Shell (SSH) e modifica il file di configurazione. Per modificare il file di configurazione, inserisci il seguente comando: **sudo nano /etc/odoo.conf**

Dopo aver aperto il file di configurazione, modifica la riga della password master `admin_passwd = $pbkdf2-sha…` in `admin_passwd = newpassword1234`. La password può essere di qualsiasi tipo purché sia salvato temporaneamente. Assicurati di modificare tutti i caratteri dopo `=`.

Example

La riga appare come segue: `admin_passwd = $pbkdf2-sh39dji295.59mptrfW.9z6HkA$w9j9AMVmKAP17OosCqDxDv2hjsvzlLpF8Rra8I7p/b573hji540mk/.3ek0lg%kvkol6k983mkf/40fjki79m`

La riga modificata appare come segue: `admin_passwd = newpassword1234`

Importante

È fondamentale che la password venga modificata invece di procedere con il ripristino aggiungendo il punto e virgola `;` all’inizio della riga. Questo garantisce che il database venga protetto durante l’intero processo di ripristino della password.

#### Riavviare il server Odoo¶

Dopo aver configurato la password temporanea, è richiesto il **riavvio** del server Odoo.

Graphical user interfaceCommand-line interface

Per prima cosa, al fine di riavviare il server Odoo, digita `servizi` nella barra di Ricerca di Windows. In seguito, seleziona l’applicazione Servizi e scorri fino a Odoo.

In seguito, fai clic su Odoo e seleziona Avvia o Riavvia. L’azione riavvia manualmente il server Odoo.

Riavvia il server Odoo digitando il comando: **sudo service odoo15 restart**

Nota

Modifica il numero dopo `odoo` per adeguarti alla versione specifica del server.

#### Utilizzare l’interfaccia web per ricrittografare la password¶

Per prima cosa, vai su `/web/database/manager` oppure `http://server_ip:port/web/database/manager` utilizzando un browser.

Nota

Sostituisci `server_ip` con l’indirizzo IP del database. Sostituisci `port` con la porta numerata dalla quale è possibile accedere al database.

In seguito, fai clic su Configura password master e inserisci la password temporanea scelta in precedenza nel campo Password master. Dopo questo step, digita una Nuova password master. La Nuova password master viene sottoposta a hash (oppure è crittografata) una volta cliccato il pulsante Contina.

A questo punto, la password è stata reimpostata con successo e una versione con hash della nuova password apparirà nel file di configurazione.

Vedi anche

Per maggiori informazioni sulla sicurezza del database Odoo, consulta la documentazione: Sicurezza gestore database.

## Browser supportati¶

Odoo supports the latest version of the following browsers.

  * Google Chrome

  * Mozilla Firefox

  * Microsoft Edge

  * Apple Safari




1
    

per aver aver installazioni multiple di Odoo usa lo stesso database PostgreSQL o per fornire più risorse informatiche a entrambi i software.

2
    

tecnicamente è possibile utilizzare uno strumento come [socat](http://www.dest-unreach.org/socat/) can per eseguire il proxy dei socket UNIX nelle reti ma questo riguarda principalmente i software che possono essere utilizzati solo su socket UNIX.

3
    

oppure essere accessibile solo tramite una rete interna con commutazione di pacchetto ma richiede commutazioni sicure, protezione contro [ARP spoofing](https://en.wikipedia.org/wiki/ARP_spoofing) e preclude l’utilizzo del Wi-Fi. Anche su reti sicure con commutazione di pacchetto, è consigliata la distribuzione su HTTPS ed è possibile avere costi ridotti in quanto è più semplice ottenere certificati «auto-firmati» in un ambiente più controllato rispetto a internet.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/administration/on_premise/deploy.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_gateway.html "Gateway di posta elettronica") |
  * [precedente](update.html "Aggiornamenti per correzione bug") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Gestire i database](../../administration.html) »
  * [On-premise](../on_premise.html) »
  * Configurazione sistema


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
  *[EDI]: Electronic Data Exchange
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
  *[FBM]: Fulfilled by Merchant
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
  *[RUT]: Rol Único Tributario
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Construction Industry Scheme
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions