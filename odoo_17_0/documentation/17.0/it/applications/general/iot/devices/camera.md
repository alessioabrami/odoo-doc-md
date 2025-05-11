# Collegare una fotocamenra — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](footswitch.html "Collegare un sensore a pedale") |
  * [precedente](measurement_tool.html "Collegare uno strumento di misura") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una fotocamenra



# Collegare una fotocamenra¶

È possibile collegare una telecamera a una box IoT con un database Odoo in pochi passaggi. Una volta che la fotocamera è stata collegata a una box IoT, può essere utilizzata in un processo di produzione o può essere collegata a un punto di controllo qualità. In questo modo è possibile scattare foto quando viene raggiunto un punto/controllo di qualità prescelto o quando viene premuto un tasto specifico durante la produzione.

## Connessione¶

Per collegare una fotocamera a una box IoT, collega entrambi via cavo. Di solito, l’operazione viene effettuata tramite un cavo USB di qualsiasi tipo.

Se la fotocamera è [supportata](https://www.odoo.com/page/iot-hardware), non c’è bisogno di configurare nulla in quanto verrà individuata appena collegata.

## Collegare la fotocamera a un punto di controllo qualità per il processo di produzione¶

Nell’app Qualità, è possibile impostare un dispositivo su un Punto di controllo qualità. A tale scopo, spostati nell’app Qualità ‣ Controllo qualità ‣ Punti di controllo e apri il Punto di controllo desiderato che sarà collegato alla telecamera.

Nel modulo del punto di controllo, modifica lo stesso selezionando il campo Tipo e fai clic su Scatta una foto dal menu a tendina. Apparirà un campo chiamato Dispositivo dove potrai selezionare il _dispositivo_ allegato. Salva le modifiche se necessario.

La fotocamera è ora utilizzabile con il punto di controllo qualità selezionato. Quando il punto di controllo qualità viene raggiunto durante il processo di produzione, il database chiede all’operatore di scattare una foto.

Nota

È possibile accedere ai punti di controllo qualità anche dall’app IoT ‣ Dispositivi. Da qui, seleziona il dispositivo. Dalla scheda Punti controllo qualità è possibile aggiungere punti e dispositivi.

Suggerimento

In un modulo di controllo qualità, il Tipo di controllo può anche essere specificato in Fotografia. Spostati nell’app Qualità ‣ Controllo qualità ‣ Controlli qualità ‣ Nuovo per creare un nuovo controllo qualità dalla pagina Controlli qualità.

Vedi anche

  * [Quality control points](../../../inventory_and_mrp/quality/quality_management/quality_control_points.html)

  * [Quality alerts](../../../inventory_and_mrp/quality/quality_management/quality_alerts.html)




## Collegare la fotocamera a un centro di lavoro nell’app Produzione¶

Per collegare una fotocamera a un’azione, è necessario prima configurarla in un centro di lavoro. Apri l’app Produzione ‣ Configurazione ‣ Centri di lavoro. Quindi, vai alla voce Centro di lavoro desiderata in cui verrà utilizzata una fotocamera per visualizzare il modulo con i dettagli di quel centro di lavoro specifico. Da qui, aggiungi il dispositivo nella scheda Attivazioni IoT, nella colonna Dispositivo, facendo clic su Aggiungi riga.

Ora, il dispositivo della fotocamera può essere collegato all’opzione Scatta foto presente nel menu a tendina Azioni. Si può anche aggiungere un tasto per attivare l’azione.

Importante

Il primo trigger elencato viene scelto per primo. L’ordine dei trigger è importante e possono essere trascinati in qualsiasi ordine desiderato.

Nota

Nella schermata Ordini di lavoro, una grafica di stato indica se il database è stato collegato correttamente alla fotocamera.

Vedi anche

[Integrate IoT devices](../../../inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.html#workcenter-iot)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/camera.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](footswitch.html "Collegare un sensore a pedale") |
  * [precedente](measurement_tool.html "Collegare uno strumento di misura") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una fotocamenra


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