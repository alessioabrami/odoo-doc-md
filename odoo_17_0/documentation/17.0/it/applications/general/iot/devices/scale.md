# Collegare una bilancia — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [precedente](printer.html "Collegare una stampante") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una bilancia



# Collegare una bilancia¶

Importante

  * Negli stati membri dell’UE, per utilizzare una bilancia come dispositivo integrato [è richiesta una certificazione legale](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv%3AOJ.L_.2014.096.01.0107.01.ENG).

  * Odoo non è certificato in diversi Paesi, tra cui Francia, Germania e Svizzera. Se risiedi in uno di questi Paesi, puoi comunque utilizzare una bilancia, ma senza integrazione con il database Odoo. In alternativa, puoi utilizzare una stampante certificata _non integrata_ che stampa etichette certificate che possono essere scansionate in seguito nel database Odoo.




Per collegare una stampante al sistema IoT, usa un cavo USB. In alcuni casi, potresti aver bisogno di un adattatore serial-to-US per completare il collegamento. Se la bilancia è [compatibile con un sistema IoT](https://www.odoo.com/page/iot-hardware), non è richiesta nessuna configurazione aggiuntiva. La bilancia viene individuata automaticamente appena viene collegata. Se la bilancia non viene individuata, riavvia la box IoT oppure [riavvia il servizio Windows virtual IoT](../windows_iot.html#iot-windows-iot-restart) e [aggiorna i driver della bilancia](../iot_advanced/updating_iot.html#iot-updating-iot-handlers).

Nota

Se la bilancia ancora non funziona dopo aver aggiornato i driver, potrebbe non essere [compatibile con il sistema IoT di Odoo](https://www.odoo.com/page/iot-hardware). In casi del genere, è necessario utilizzare una bilancia diversa.

Una volta che la bilancia è stata collegata al sistema IoT, segui gli step descritti di seguito per configurarla nelle impostazioni del Punto vendita:

  1. [accedi alle impostazioni del Punto vendita](../../../sales/point_of_sale/configuration.html#configuration-settings) e seleziona il POS che desideri oppure fai clic sul pulsante a forma di ellissi verticale (⋮) sulla scheda di un POS e fai clic su Modifica.

  2. scorri in basso verso la sezione Dispositivi connessi e abilita la box IoT

  3. seleziona la bilancia nel campo Bilancia elettronica

  4. fai clic su Salva.




Vedi anche

[Collegare un sistema IoT a un Punto vendita](../../../sales/point_of_sale/configuration/pos_iot.html)

In seguito, la bilancia sarà disponibile in tutte le [sessioni :abbr:`POS](../../../sales/point_of_sale.html). Se un prodotto ha un prezzo per peso, cliccando su di esso nella schermata POS si apre la schermata della bilancia. Il cassiere può pesare il prodotto per aggiungere automaticamente il prezzo corretto al carrello.

## Bilance Ariva S¶

Per far si che le bilance della serie Ariva S (prodotte da Mettler-Toledo, LLC.) funzionino con i sistemi IoT, è necessario modificare un’impostazione specifica ed è richiesto un cavo Mettler RJ45 USB-to-proprietary.

Importante

Bisogna utilizzare il cavo Mettler USB-to-RJ45 ufficiale (numerto parte Mettler 72256236). Contatta Mettler o un partner per acquistare un cavo originale. Con questa configurazione, **non** funzionerà nessun altro cavo.

Per configurare la bilancia Ariva S per il riconoscimento di un sistema IoT, fai riferimento alla pagina 17 del documento Mettler’s Setup Guide for Ariva S series scales <<https://www.mt.com/dam/RET_DOCS/Ariv.pdf>>`_ e segui questi passaggi:

  1. tieni premuto il pulsante **> T<** per otto secondi oppure fino alla comparsa di CONF

  2. premi **> T<** fino alla comparsa di GRP 3 e poi premi **> 0<** per confermare

  3. nel passaggio 3.1, assicurati che il valore sia impostato su 1 (porte USB Virtual COM) e premi **> T<** per sfogliare le opzioni.

  4. Premi **> 0<** fino a 3.6 (se disponibile, altrimenti passa alla fase successiva).

  5. Nella fase 3.6, assicurati che il valore sia impostato su 3 (8217 Mettler-Toledo (WO)) premendo **> T<** per sfogliare le opzioni.

  6. Premi **> 0<** (più volte se necessario) fino all’apparizione di GRP 4.

  7. premi **> T<** fino alla comparsa di EXIT

Importante

**Non** apportare ulteriori modifiche se non sono necessarie.

  8. premi **> 0<**

  9. premi di nuovo **> 0<** per SALVARE e la bilancia si riavvierà

  10. riavvia la box IoT o il [servizio Windows virtual IoT](../windows_iot.html#iot-windows-iot-restart). La bilancia in seguito apparirà come `Toledo 8217`, al contrario della schermata precedente dove appariva come `Adam Equipment Serial`.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/scale.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [precedente](printer.html "Collegare una stampante") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una bilancia


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
  *[POS]: Punto vendita