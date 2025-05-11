# Certificato HTTPS (IoT) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](updating_iot.html "Aggiornamenti sistema IoT") |
  * [precedente](../iot_advanced.html "Avanzato") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Certificato HTTPS (IoT)



# Certificato HTTPS (IoT)¶

Il protocollo _Hypertext Transfer Protocol Secure_ (HTTPS) rappresenta la versione sicura e crittografata del protocollo _Hypertext Transfer Protocol_ (HTTP) che è il protocollo principale utilizzato per la comunicazione di dati tra un browser web e un sito web. Le comunicazioni verranno protette grazie all’utilizzo di un protocollo di crittografia conosciuto come _Transport Layer Security_ (TLS), precedentemente _Secure Sockets Layer_ (SSL). La sicurezza del protocollo HTTPS si basa sui certificati TLS /SSL che autenticano il fornitore e ne verificano l’identità.

L’utilizzo del protocollo HTTPS è richiesto per la comunicazione con alcuni dispositivi di rete, in particolare per i terminali di pagamento. Se il certificato HTTPS non è valido, alcuni dispositivi non possono interagire con un sistema IoT.

Nota

In questa documentazione e in Odoo, il termine _certificato HTTPS_ fa riferimento a un certificato SSL valido che permette la connessione di un HTTPS.

## Creazione certificato HTTPS¶

Il certificato HTTPS viene generato automaticamente. Quando il sistema IoT viene (ri)avviato (ad es. dopo essere stato collegato al database Odoo), viene inviata una richiesta a [https://www.odoo.com](https://www.odoo.com/) che restituisce il certificato HTTPS se il sistema IoT e il database rispettano i criteri di idoneità:

  * Il database deve essere un’istanza di **produzione**. L’istanza del database non deve essere una copia, un duplicato, un ambiente di staging o di sviluppo.

  * L’abbonamento Odoo deve essere attivo (stato In corso) e avere una riga [abbonamento box IoT](../../iot.html#iot-iot-iot-subscription).




Una volta ricevuto il certificato:

  * l’indirizzo della pagina principale del sistema IoT viene aggiornato con un nuovo URL HTTPS che termina con `.odoo-iot.com`. Fai clic sull’URL per stabilire una connessione HTTPS sicura.

  * Il banner del certificato HTTPS mostra il periodo di validità del certificato. Per visualizzare queste informazioni, fai clic sul pulsante __( ingranaggio) nella pagina principale del sistema IoT.




## Errori e problemi legati alla generazione del certificato HTTPS¶

### Certificato HTTPS non generato¶

Tra le potenziali cause:

  * nessun ref:`abbonamento alla box IoT <iot/iot/iot-subscription>` collegato al tuo account

  * l’abbonamento [alla box IoT](../../iot.html#iot-iot-iot-subscription) è stato aggiunto _dopo_ aver collegato il sistema IoT al database. In questo caso, ricarica la pagina principale del sistema IoT oppure [riavvia](../windows_iot.html#iot-windows-iot-restart) il sistema IoT per rigenerare il certificato HTTPS.

  * il firewall impedisce la corretta generazione del certificato HTTPS. In questo caso, disattiva il firewall finché il certificato non viene generato correttamente.

Nota

Alcuni dispositivi, come i router con firewall integrato, possono impedire la generazione del certificato HTTPS.




### Accesso alla pagina principale del sistema IoT tramite indirizzo IP ma non via URL `xxx.odoo-iot.com`¶

Contatta l’amministratore di sistema o di rete per risolvere il problema. I problemi legati alla rete non rientrano nell’ambito dei servizi di assistenza Odoo.

  * Se il router permette di configurare manualmente il DNS, aggiorna le impostazioni per utilizzare il [DNS di Google](https://developers.google.com/speed/public-dns).

  * Se il router non supporta questo, è necessario aggiornare le impostazioni DNS direttamente su ogni dispositivo che interagisce con i sistema IoT per utilizzare il [DNS di Google](https://developers.google.com/speed/public-dns). Le istruzioni per la configurazione del DNS su dispositivi singoli si trovano sul sito web di ogni fornitore.




Nota

  * Alcuni dispositivi IoT, come i terminali di pagamento, probabilmente non richiedono modifiche al DNS, in quanto sono tipicamente preconfigurati con impostazioni DNS personalizzate.

  * Su alcuni browser, viene visualizzato un codice di errore che menziona il DNS (come `DNS_PROBE_FINISHED_NXDOMAIN`).




### Errori¶

Un codice di errore specifico viene visualizzato sulla pagina principale del sistema IoT se si verificano problemi durante la generazione o la ricezione del certificato HTTPS.

Suggerimento

Quando accedi alla pagina principale del sistema IoT, questo controlla automaticamente la presenza di un certificato HTTPS e tenta di generarne uno se manca. Se compare un errore, aggiorna la pagina per verificare se il problema è stato risolto.

#### `ERR_IOT_HTTPS_CHECK_NO_SERVER`¶

Configurazione del server mancate, ovvero l’istanza Odoo non è [collegata](../connect.html) al sistema IoT.

#### `ERR_IOT_HTTPS_CHECK_CERT_READ_EXCEPTION`¶

Si è verificato un errore durante il tentativo di lettura del certificato HTTPS esistente. Verifica che il file del certificato HTTPS sia leggibile.

#### `ERR_IOT_HTTPS_LOAD_NO_CREDENTIAL`¶

Manca il contratto e/o l”UUID del database dall’IoT.

Verifica che entrambi i valori siano configurati correttamente. Per aggiornarli, [accedi alla pagina principale della box IoT](../iot_box.html#iot-iot-box-homepage) o a quella del [Windows virtual IoT](../windows_iot.html#iot-windows-iot-homepage), fai clic sul pulsante __( ingranaggio) e infine fai clic su Credenziale.

#### `ERR_IOT_HTTPS_LOAD_REQUEST_EXCEPTION`¶

Si è verificato un errore inaspettato quando il sistema IoT ha cercato di raggiungere [https://www.odoo.com](https://www.odoo.com/). Il problema sembra essere collegato a problemi di rete come:

  * il sistema IoT non ha accesso a Internet

  * sono presenti restrizioni di rete (ad es. firewall o VPN) che impediscono la comunicazione con [https://www.odoo.com](https://www.odoo.com/).




Nota

  * Per accedere ai dettagli completi dell’eccezione di richiesta con informazioni sull’errore, [attiva la modalità sviluppatore](../../developer_mode.html#developer-mode), fai clic sulla scheda del sistema Iot nell’app IoT e fai clic su Scarica registri sul [modulo del sistema IoT](../connect.html#iot-connect-iot-form). Per definire i livelli di log registrati nel file di log del sistema IoT, [accedi alla pagina principale della box IoT](../windows_iot.html#iot-windows-iot-homepage) o a quella del [Windows virtual IoT](../iot_box.html#iot-iot-box-homepage), fai clic sul pulsante __( ingranaggio) e poi Livello log in fondo alla pagina.

  * Per risolvere i problemi relativi alla rete, contatta l’amministratore di sistema o di rete. Questi problemi esulano dall’ambito dei servizi di assistenza di Odoo.




#### `ERR_IOT_HTTPS_LOAD_REQUEST_STATUS`¶

Il sistema IoT ha raggiunto [https://www.odoo.com](https://www.odoo.com/) con successo ma ha ricevuto una [risposta HTTP (codici stato)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) insolita.

Questo codice di errore include lo stato dell’HTTP. Ad esempio, `ERR_IOT_HTTPS_LOAD_REQUEST_STATUS 404` significa che il server ha restituito la risposta «Page Not Found».

Per risolvere il problema:

  1. apri [https://www.odoo.com](https://www.odoo.com/) in una pagina web per verificare che il sito web sia temporaneamente fuori uso per la manutenzione

  2. se [https://www.odoo.com](https://www.odoo.com/) è in down per la manutenzione, aspetta che torni disponibile

se il sito web è operativo, apri un [ticket di supporto](https://www.odoo.com/help) e assicurati di includere il codice di stato HTTPS a 3 cifre nel ticket.




#### `ERR_IOT_HTTPS_LOAD_REQUEST_NO_RESULT`¶

Il sistema IoT è stato collegato con successo a [https://www.odoo.com](https://www.odoo.com/) ma il server si è rifiutato di fornire il certificato HTTPS.

Verifica che il sistem IoT e il database rispettino i requisiti di ammissibilità per un certificato HTTPS.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/iot_advanced/https_certificate_iot.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](updating_iot.html "Aggiornamenti sistema IoT") |
  * [precedente](../iot_advanced.html "Avanzato") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Certificato HTTPS (IoT)


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
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier