# Conessione sistema IoT a Odoo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot_advanced.html "Avanzato") |
  * [precedente](windows_iot.html "Windows virtual IoT") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Conessione sistema IoT a Odoo



# Conessione sistema IoT a Odoo¶

## Prerequisiti¶

Per collegare il sistema IoT a un database Odoo, è necessario soddisfare i seguenti prerequisiti:

  * app Internet of Things (IoT) [installata](../apps_modules.html#general-install);

  * il sistema IoT deve essere collegato alla rete;

  * il computer collegato a Odoo deve essere collegato alla stessa rete del sistema IoT.




Nota

È consigliato collegare il sistema IoT a un’istanza di **produzione** , in quanto altri tipi di ambienti potrebbero causare problemi (ad es., con la [generazione del certificato HTTPS](iot_advanced/https_certificate_iot.html#iot-https-certificate-iot-iot-eligibility)).

Vedi anche

  * [Box IoT](iot_box.html)

  * [Windows virtual IoT](windows_iot.html)




## Connessione¶

Il sistema IoT può essere collegato al database Odoo utilizzando un codice di abbinamento o un token di connessione.

### Connessione con un codice di abbinamento¶

Nota

  * Il codice di abbinamento viene visualizzato per un massimo di 5 minuti dopo l’avvio del sistema IoT. Se il codice non è più visibile, riavvia il sistema IoT o [riavvia il servizio virtuale IoT di Windows](windows_iot.html#iot-windows-iot-restart) per visualizzare nuovamente il codice di abbinamento. In alternativa, collega il sistema IoT al database utilizzando un token di connessione.

  * Il codice di abbinamento non viene visualizzato se il sistema IoT è già collegato a un database (ad esempio, un database di prova).




  1. Recupera il codice di abbinamento del sistema IoT:

IoT boxWindows virtual IoT

Collega la box IoT a un monitor o a una stampante esterna. Se la box IoT era già collegata, riavviala staccando la spina per qualche secondo e reinseriscila.

     * Monitor esterno: Il codice di abbinamento dovrebbe essere visualizzato sullo schermo pochi minuti dopo il riavvio della box.

     * Stampante: Il codice di abbinamento dovrebbe essere stampato automaticamente.

Suggerimento

Se alla box IoT non è collegato alcun monitor o stampante esterna, accedi alla [pagina principale della box IoT](iot_box.html#iot-iot-box-homepage) e il codice verrà visualizzato nella sezione Codice di abbinamento.

Sul computer in cui è installato l’IoT virtuale di Windows, apri la pagina principale del sistema IoT in un browser aprendo l’URL `http://localhost:8069`. Successivamente, scorri fino alla sezione Codice di abbinamento.

  2. In Odoo, apri l’app IoT e fai clic su Collega.

  3. Nella finestra pop-up Collega una box IoT che appare, inserisci il Codice di abbinamento.

  4. Fai clic su Abbina.




### Connessione con un token¶

  1. In Odoo, apri l’app IoT e fai clic su Collega.

  2. Nella finestra pop-up Collega una box IoT che appare, copia il Token.

  3. Accedi alla pagina principale della [box IoT](iot_box.html#iot-iot-box-homepage) oppure della [Windows virtual IoT](windows_iot.html#iot-windows-iot-homepage).

  4. Nella sezione Database Odoo connesso, fai clic su Configura.

  5. Incolla il token nel campo Token server e fai clic su Collega.




## Modulo sistema IoT¶

Una volta che il sistema IoT viene collegato al database Odoo, nell’app IoT verrà visualizzato come scheda. Fai clic sull’indirizzo IP nella scheda per accedere alla pagina principale della [box IoT](windows_iot.html#iot-windows-iot-homepage) oppure della [Windows virtual IoT](iot_box.html#iot-iot-box-homepage). Fai clic sulla scheda per accedere all’elenco di [dispositivi](devices.html) collegati al sistema IoT.

Suggerimento

[Attiva la modalità sviluppatore](../developer_mode.html#developer-mode) per accedere alle informazioni tecniche del sistema IoT, come Identificatore, Indirizzo dominio e Versione immagine.

Nota

Per impostazione predefinita, i driver vengono [aggiornati](iot_advanced/updating_iot.html#iot-updating-iot-handlers) ogni volta che il sistema IoT viene riavviato. Per disattivare gli aggiornamenti automatici, deseleziona l’opzione Aggiornamento driver automatico.

## Risoluzione problemi¶

### Il codice di abbinamento non appare o non funziona¶

Il codice di abbinamento potrebbe non apparire o essere stampato nelle seguenti circostanze:

  * il sistema IoT non è collegato a Internet;

  * il sistema IoT è già collegato a un databse Odoo;

  * il tempo di visualizzazione del codice di abbinamento è scaduto. Riavvia la box IoT oppure [riavvia il servizio Windows virtual IoT](windows_iot.html#iot-windows-iot-restart) per visualizzare di nuovo il codice di abbinamento;

  * la versione dell’immagine del sistema IoT è troppo vecchia e deve essere [aggiornata](iot_advanced/updating_iot.html#iot-updating-iot-image-code).




### Sistema IoT collegato ma non appare nel database¶

Il sistema IoT potrebbe impiegare alcuni minuti per riavviarsi quando si connette a un database. Se dopo alcuni minuti non viene ancora visualizzato:

  * verifica che il sistema IoT possa raggiungere il database e che il server non utilizzi un ambiente multi-database;

  * riavvia la box IoT oppure [riavvia il servizio Windows virtual IoT](windows_iot.html#iot-windows-iot-restart).




### Box IoT collegata al database Odoo ma non raggiungibile¶

Verifica che il sistema IoT e il computer che esegue il database di Odoo siano collegati alla stessa rete.

### Pagina principale Windows virtual IoT non accessibile da un altro dispositivo¶

Verifica la [Configurazione Firewall Windows](windows_iot.html#iot-windows-iot-firewall).

### Sistema IoT scolelgato dal database dopo l’aggiornamento di Odoo¶

[Aggiorna l’immagine del sistema IoT](iot_advanced/updating_iot.html#iot-updating-iot-image-code) installando la scheda della box IoT oppure [disinstallando il programma del Windows virtual IoT](windows_iot.html#iot-windows-iot-uninstall) e [installa di nuovo](windows_iot.html#iot-windows-iot-installation) l’ultimo pacchetto per Windows **che corrisponde alla versione del tuo database**.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/connect.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot_advanced.html "Avanzato") |
  * [precedente](windows_iot.html "Windows virtual IoT") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Conessione sistema IoT a Odoo


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