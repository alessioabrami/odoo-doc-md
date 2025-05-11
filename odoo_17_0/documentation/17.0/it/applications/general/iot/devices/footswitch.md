# Collegare un sensore a pedale — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](printer.html "Collegare una stampante") |
  * [precedente](camera.html "Collegare una fotocamenra") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare un sensore a pedale



# Collegare un sensore a pedale¶

Quando si lavora in un ambiente di produzione, è sempre meglio per un operatore avere entrambe le mani a disposizione, in ogni momento. La box IoT di Odoo lo rende possibile quando si utilizza un interruttore a pedale.

Infatti, con un interruttore a pedale, l’operatore può passare da una schermata all’altra ed eseguire azioni con il piede. Questo può essere configurato in pochi passaggi sul centro di lavoro nell’applicazione _Produzione_.

## Connessione¶

Per collegare un interruttore a pedale alla box IoT, collega entrambi i dispositivi tramite cavo. Spesso l’operazione viene realizzata tramite cavo USB.

Se il sensore a pedali è un [dispositivo supportato](https://www.odoo.com/page/iot-hardware), non c’è bisogno di fare altro perché il dispositivo viene riconosciuto automaticamente al momento del collegamento.

## Collegare un sensore a pedale a un centro di lavoro nell’app Produzione di Odoo¶

Per collegare un interruttore a pedale a un’azione, è necessario prima configurarlo in un centro di lavoro. Apri l’app Produzione ‣ Configurazione ‣ Centri di lavoro. Da qui, accedi al Centro di lavoro desiderato in cui verrà utilizzato l’interruttore a pedale e aggiungi il dispositivo nella scheda Attivazioni IoT, sotto la colonna Dispositivo, selezionando Aggiungi riga. In questo modo, l’interruttore a pedale può essere collegato a un’opzione nella colonna Azioni e, facoltativamente, si può aggiungere un tasto per attivarlo. Un esempio di Azione nell’applicazione _Produzione_ potrebbe essere il pulsante Convalida o Segna come completato di un ordine di lavoro di produzione.

Importante

Nota che il primo trigger elencato viene scelto per primo. Quindi, l’ordine è importante e questi trigger possono essere trascinati in qualsiasi ordine. Nell’immagine qui sopra, l’uso dell’interruttore a pedale salta automaticamente la parte del processo su cui si sta lavorando.

Nota

Nella schermata Ordini di lavoro, una grafica di stato indica se il database è stato collegato correttamente all’interruttore a pedale.

Vedi anche

[Integrate IoT devices](../../../inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.html#workcenter-iot)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/footswitch.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](printer.html "Collegare una stampante") |
  * [precedente](camera.html "Collegare una fotocamenra") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare un sensore a pedale


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