# Aggiornamenti sistema IoT — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ssh_connect.html "Connessione SSH box IoT") |
  * [precedente](https_certificate_iot.html "Certificato HTTPS \(IoT\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Aggiornamenti sistema IoT



# Aggiornamenti sistema IoT¶

Per via della complessità dei sistemi IoT, il termine _aggiornamento_ può fare riferimento a vari processi tra cui:

  * aggiornare l’immagine del sistema IoT e/o il codice core;

  * aggiornare i gestori che includono interfacce e driver.




## Aggiornamento immagine e codice principale¶

IoT boxWindows virtual IoT

> Per verificare se la box IoT è aggiornata (e aggiornarla se necessario), [accedi alla pagina principale della box IoT](../iot_box.html#iot-iot-box-homepage), fai clic sul pulsante __( ingranaggio) in alto a destra, poi Aggiorna nella sezione Versione.
> 
> Suggerimento
> 
> [Attiva la modalità sviluppatore](../../developer_mode.html#developer-mode) per visualizzare le versioni attuali dell’immagine e del codice principale della box IoT.

**Aggiornamento immagine**

> Per aggiornare l’immagine della box IoT, installa la scheda SD. L’installazione può essere eseguita utilizzando [balenaEtcher](https://etcher.balena.io/), uno strumento gratuito e open source per scrivere immagini del disco sulla scheda SD.
> 
> Nota
> 
>   * L’aggiornamento dell’immagine del sistema IoT è spesso necessario dopo l’aggiornamento del database Odoo a una versione più recente.
> 
>   * Al fine di installare la scheda micro SD, è richiesto un computer con un lettore/adattatore di schede micro SD.
> 
>   * Un software alternativo per l’installazione della scheda micro SD è `Raspberry Pi Imager <https://www.raspberrypi.com/software/>`.
> 
> 

> 
>   1. [Scarica balenaEtcher.](https://etcher.balena.io/#download-etcher)
> 
>   2. inserisci la scheda micro SD della box IoT nel computer o nell’adattatore
> 
>   3. apri balenaEtcher, fai clic su Flash from URL e inserisci l’URL che segue: `http://nightly.odoo.com/master/iotbox/iotbox-latest.zip`
> 
>   4. fai clic su Select target e seleziona la scheda SD
> 
>   5. fai clic su Flash e aspetta la fine del processo.
> 
> 


**Aggiornamento codice principale**

> Per aggiornare il codice principale della box IoT, fai clic su Aggiorna nella sezione Aggiorna box IoT nel pop-up Aggiornamento.
> 
> Pericolo
> 
> Il processo potrebbe richiedere più di 30 minuti. **Non spegnere o scollegare la box IoT** perché potrebbe lasciare il dispositivo in uno stato incoerente che richiederebbe l’installazione di una nuova immagine per la box IoT.

Per aggiornare l’immagine e il codice del Windows virtual IoT [disinstalla il programma](../windows_iot.html#iot-windows-iot-uninstall) e [reinstalla](../windows_iot.html#iot-windows-iot-installation) il pacchetto più recente.

## Aggiornamento gestore (driver)¶

Per aggiornare i gestori del sistema IoT (ad es. driver e interfacce) e sincronizzarli con il codice del gestore server configurato, per risolvere, ad esempio, problemi relativi al mal funzionamento di [dispositivi](../devices.html) con il sistema IoT, procedi come segue:

  1. accedi alla pagina principale della [box IoT](../iot_box.html#iot-iot-box-homepage) o del [Windows virtual IoT](../windows_iot.html#iot-windows-iot-homepage) e fai clic sul pulsante __( ingranaggio) in alto a destra.

  2. fai clic su Aggiorna nella sezione Versione

  3. nel pop-up Aggiornamento che si apre, fai clic su Forza aggiornamento driver.




Importante

Se hai un database [on-premise](../../../../administration/on_premise.html) oppure [Odoo.sh](../../../../administration/odoo_sh/overview/introduction.html), il server configurato deve essere aggiornato per garantire che il codice del gestore includa le ultime correzioni e patch.

Nota

L’aggiornamento del gestore viene eseguito automaticamente ogni volta che il sistema IoT viene riavviato a meno che non venga disattivata l’opzione Aggiornamento driver automatico nella scheda Informazioni tecniche nel [modulo del sistema IoT](../connect.html#iot-connect-iot-form) in Odoo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/iot_advanced/updating_iot.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ssh_connect.html "Connessione SSH box IoT") |
  * [precedente](https_certificate_iot.html "Certificato HTTPS \(IoT\)") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Aggiornamenti sistema IoT


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