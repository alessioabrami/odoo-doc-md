# Windows virtual IoT — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](connect.html "Conessione sistema IoT a Odoo") |
  * [precedente](iot_box.html "Box IoT") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Windows virtual IoT



# Windows virtual IoT¶

Per iniziare a utilizzare la Windows virtual IoT:

  1. assicurati di rispettare tutti i prerequisiti

  2. installa la Windows virtual IoT su un computer Windows

  3. configura il Firewall Windows

  4. collega i tuoi [dispositivi](devices.html) alla Windows virtual IoT

  5. [collega la Windows virtual IoT al tuo database Odoo](connect.html).




## Prerequisiti¶

È necessario rispettare i seguenti prerequisiti prima di configurare e usare la Windows virtual IoT:

  * [abbonamento box IoT](../iot.html#iot-iot-iot-subscription) valido

  * aggiornamento e versione recente di Windows (ad es. (i.e., Windows 10 or Windows 11) installato su un pc Windows (laptop, desktop o server).




Nota

  * MRP devices, including cameras and measurement tools, are not compatible with Windows virtual IoT.

  * È anche possibile creare una Windows Virtual Machine in un computer MacOS/Linux. Tuttavia, l’opzione non è supportata da Odoo e non verrà fornita nessun tipo di assistenza per individuare i problemi.




## Installazione¶

Per installare la Windows virtual IoT su un computer Windows:

  1. accedi alla [pagina di download di Odoo](https://odoo.com/download) e scarica il pacchetto di installazione di Odoo per Windows **che corrisponde dalla versione del tuo database**

  2. apri il file `.exe` scaricato, consenti all’app di apportare modifiche al dispositivo, seleziona una lingua e fai clic su OK

  3. fai clic su Avanti e poi su Concordo per accettare i termini e condizioni e continuare

  4. seleziona IoT Odoo dall’elenco a discesa Seleziona il tipo di installazione. Bisogna selezionare i seguenti componenti: Server Odoo, IoT Odoo, Nginx WebServer e Ghostscript interpreter.

  5. verifica di avere lo spazio richiesto sul computer e fai clic su Avanti

  6. nella Cartella di destinazione, inserisci C:\odoo e fai clic su Installa

Avvertimento

Non installare la Windows virtual IoT di Odoo in nessuna directory utente Windows perché può causare problemi con la [Creazione certificato HTTPS](iot_advanced/https_certificate_iot.html#iot-https-certificate-iot-generation).

  7. una volta che l’installazione è stata completata, fai clic su Avanti

  8. configura il GPL Ghostscript: fai clic su Avanti, accetta i termini e condizioni, fai clic su Installa e poi su Termina

  9. fai clic su Avanti, Avanti e Termina per completare la configurazione. La pagina principale del sistema IoT si apre automaticamente in un browser web con l’URL `http://localhost:8069`.

Suggerimento

se il browser web non mostra nulla, riavvia il servizio Windows virtual IoT

  10. verifica di avere l’accesso alla pagina principale del sistema IoT in un browser web:

     * sul computer della Windows virtual IoT e

     * su un altro dispositivo **sulla stessa rete del sistema IoT** accedendo all’URL `http://xxx:8069` (dove `xxx` è l’indirizzo IP del sistema IoT).

     * su un altro dispositivo **sulla stessa rete del sistema IoT** accedendo all’URL `https://xxx` (dove `xxx` è l’indirizzo IP del sistema IoT) da testare per la connessione [HTTPS](iot_advanced/https_certificate_iot.html).

Suggerimento

Se non riesci ad accedere alla pagina principale del sistema IoT da un altro dispositivo, crea una regola Windows Firewall per consentire la comunicazione tramite la porta `8069`.




## Configurazione Firewall Windows¶

I firewall aiutano a mantenere i dispositivi sicuri, ma a volte possono bloccare le connessioni legittime. Se la Windows virtual IoT non è accessibile sulla LAN, ad esempio da un altro dispositivo, ciò potrebbe essere dovuto a un firewall che blocca la connessione. Per evitare questo problema, configura le eccezioni per il rilevamento della rete nelle impostazioni del sistema operativo o del firewall.

Nota

Se sul computer Windows è installato un software firewall di terze parti, consulta la documentazione del software per configurare le eccezioni del firewall.

Per creare una regola su Windows Defender e consentire la comunicazione attraverso la porta `8069`, procedi come segue:

  1. cerca `firewall` nel menu start di Windows e seleziona l’applicazione Windows Defender Firewall with Advanced Security

  2. nella parte a sinistra della finestra, seleziona regole inbound

  3. nella parte a destra della finestra, nella sezione Azioni, fai clic su Nuova regola

  4. nella Procedura guidata nuova regola inbound che si pare, seleziona il tipo di Porta della regola e fai clic su Avanti

  5. sulla pagina Protocolli e Porte, assicurati di aver selezionato TCP e Porte locali specificate, inserisci i seguenti valori nel campo `8069, 80, 443` e fai clic su Avanti

Nota

Potrebbero essere necessarie altre porte a seconda dei dispositivi IoT. Ad esempio, per il terminale di pagamento [Worldline](../../sales/point_of_sale/payment_methods/terminals/worldline.html) è necessario aggiungere la porta `9050`

  6. nella pagina Azioni, seleziona Consenti connessione e fai clic su Avanti

  7. sulla pagina Profilo, disattiva qualsiasi tipo di connessione che non si applica al tuo computer Windows e fai clic su Avanti

  8. sulla pagina Nome, fornisci un Nome (ad es., `Odoo`) e, se vuoi, una breve Descrizione e poi fai clic su Termina.




Vedi anche

[Documentazione regole Windows Firewall](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/rules)

## Pagina principale Windows virtual IoT¶

Per accedere alla pagina principale della Windows virtual IoT, accedi all’URL `http://localhost:8069` sul computer della Windows virtual IoT oppure apri un browser web da un altro computer **sulla stessa rete del sistema IoT** e accedi all’URL `http://xxx:8069` (dove `xxx` è l’indirizzo IP del sistema IoT).

Una volta che la Windows virtual IoT [è stata collegata al database Odoo](connect.html), è possibile accedere alla pagina principale da Odoo aprendo l’app IoT e facendo clic sull’URL mostrato sulla scheda del sistema IoT.

Nota

Assicurati che il Windows Firewall sia configurato per consentire l’accesso.

## Collegare dispositivi¶

La maggior parte dei [dispositivi](devices.html) si collega automaticamente al computer Windows utilizzato per la Windows Virtual IoT attraverso [Windows Plug and Play (PnP)](https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/introduction-to-plug-and-play). Tuttavia, se Windows non riconosce il dispositivo automaticamente dopo il collegamento, l’amministratore potrebbe aver bisogno di installare manualmente i driver appropriati.

Suggerimento

Dopo aver collegato i dispositivi al computer, ricarica la :ref:pagina principale del sistema IoT <iot/windows-iot/homepage>` per verificare che il dispositivo compaia nell’elenco. Se il dispositivo non appare, [ricarica i gestori](iot_advanced/updating_iot.html#iot-updating-iot-handlers) dalla pagina principale del sistema IoT.

## Riavviare Windows virtual IoT¶

Per riavviare manualmente il server Windows IoT, cerca `services` nel menu start di Windows e seleziona l’app Servizi. Scorri in basso fino al servizio odoo-server-xxx (dove `xxx` è la versione Odoo), fai clic destro e seleziona Start o Restart.

## Disinstallare Windows virtual IoT¶

Per disinstallare la Windows virtual IoT, [disinstalla](https://support.microsoft.com/en-us/windows/uninstall-or-remove-apps-and-programs-in-windows-4b55f974-2cc6-2d2b-d092-5905080eaf98#ID0EBD=Windows_11) il programma Odoo dal tuo pc Windows. Conferma la disinstallazione e completa gli step nella finestra di dialogo Odoo Uninstall.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/windows_iot.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](connect.html "Conessione sistema IoT a Odoo") |
  * [precedente](iot_box.html "Box IoT") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Windows virtual IoT


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