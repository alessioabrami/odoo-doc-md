# Collegare uno strumento di misura — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](camera.html "Collegare una fotocamenra") |
  * [precedente](screen.html "Collegare uno schermo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare uno strumento di misura



# Collegare uno strumento di misura¶

Grazie alla box IoT è possibile collegare strumenti di misura al database Odoo per l’utilizzo nell’app _Qualità_ in un punto di controllo/verifica qualità oppure per l’utilizzo in un centro di lavoro durante il processo di produzione.

Trovi l’elenco di dispositivi supportati al seguente link: [Dispositivi supportati](https://www.odoo.com/page/iot-hardware).

## Collegamento USB¶

Per collegare un dispositivo via USB, collega il cavo USB alla box IoT e il dispositivo apparirà nel database Odoo.

## Collegamento via bluetooth¶

Attiva la funzionalità Bluetooth sul dispositivo (consulta il manuale del dispositivo per ulteriori spiegazioni) e la box IoT si connetterà automaticamente al dispositivo.

## Collegare uno strumento di misura a un punto di controllo qualità nel processo di produzione¶

Nell’app _Qualità_ , è possibile impostare un dispositivo su un punto di controllo qualità. Per farlo, apri l’app Qualità ‣ Controllo qualità ‣ Punti di controllo e apri il punto di controllo desiderato a cui collegare lo strumento di misura.

Da qui, modifica il punto di controllo selezionando il campo Tipo e fai clic su Misura dal menu a discesa. Apparirà un campo chiamato Dispositivo dove potrai selezionare il dispositivo desiderato.

In aggiunta, è possibile configurare i campi Norma e Tolleranza. Salva le modifiche se necessario.

A questo punto, lo strumento di misura è collegato al punto di controllo qualità scelto. Il valore, che di solito deve essere modificato manualmente, viene aggiornato automaticamente durante l’utilizzo dello strumento.

Suggerimento

È possibile accedere ai punti di controllo qualità anche dall’app IoT ‣ Dispositivi e poi seleziona il dispositivo. Dalla scheda Punti controllo qualità è possibile aggiungere punti e dispositivi.

Nota

Nel modulo con i dettagli del controllo qualità, è possibile specificare il Tipo di controllo come Misura. Accedi alla pagina di un nuovo controllo qualità aprendo l’app Qualità ‣ Controllo qualità ‣ Controlli qualità ‣ Nuovo.

Vedi anche

  * [Quality control points](../../../inventory_and_mrp/quality/quality_management/quality_control_points.html)

  * [Quality alerts](../../../inventory_and_mrp/quality/quality_management/quality_alerts.html)




## Collegare uno strumento di misura a un centro di lavoro nell’app Produzione¶

Per collegare uno strumento di misura a un’azione, prima è necessario configurarlo in un centro di lavoro, Per farlo, apri l’app Produzione ‣ Configurazione ‣ Centri di lavoro. In seguito, seleziona il centro di lavoro desiderato nel quale utilizzare lo strumento di misura.

Nella pagina del centro di lavoro, aggiungi il dispositivo nella scheda Attivazioni IoT, sotto la colonna Dispositivi e seleziona Aggiungi riga. Quindi, lo strumento di misura può essere collegato all’opzione del menu a discesa Azioni etichettata Misura. È possibile aggiungere un tasto per attivare l’azione.

Importante

Nota che il primo trigger elencato viene scelto per primo. L’ordine è importante e questi trigger possono essere trascinati in qualsiasi ordine.

Nota

Nella schermata Ordini di lavoro, una grafica di stato indica se il database è stato collegato correttamente allo strumento di misura.

Vedi anche

[Integrate IoT devices](../../../inventory_and_mrp/manufacturing/advanced_configuration/using_work_centers.html#workcenter-iot)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/measurement_tool.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](camera.html "Collegare una fotocamenra") |
  * [precedente](screen.html "Collegare uno schermo") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare uno strumento di misura


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