# Box IoT — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](windows_iot.html "Windows virtual IoT") |
  * [precedente](../iot.html "Internet delle cose \(IoT\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Box IoT



# Box IoT¶

Per iniziare a utilizzare una box IoT:

  1. Assicurati di avere un [abbonamento alla box IoT valido](../iot.html#iot-iot-iot-subscription) oltre all’abbonamento Odoo.

  2. collega i tuoi [dispositivi](devices.html) alla box IoT

  3. collega la box IoT alla rete

  4. [collega la box IoT al database Odoo](connect.html).




Nota

I dispositivi possono essere collegati anche dopo che la box IoT è stata aggiunta alla rete e/o connessa al database. Tuttavia, potrebbe essere necessario riavviarla.

## Connessione alla rete¶

La box IoT può essere collegata alla rete tramite cavo Ethernet o Wi-Fi.

Importante

**Tutti** i dispositivi devono essere collegati alla **stessa rete** : la box IoT, il dispositivo collegato alla box IoT e il computer collegato a Odoo.

### Ethernet¶

Collega il cavo Ethernet alla porta Ethernet della box IoT e a una porta disponibile del router e poi collega la box IoT a una fonte di alimentazione.

### Wi-Fi¶

Assicurati che non ci siano cavi Ethernet collegati alla box IoT e segui questi step:

>   1. collega la box IoT a una fonte di alimentazione e aspetta pochi minuti per far sì che si accenda
> 
>   2. accedi alle impostazioni Wi-Fi del computer e seleziona la rete della box IoT. Il nome della rete è il formato `BoxIoT-xxxxxxxxxxxx` (dove `xxxxxxxxxxxx` è l’identificatore unico).
> 
>   3. collega la rete Wi-Fi della box IoT e accedi. Il browser dovrebbe aprirsi automaticamente e reindirizzarti alla pagina principale della box IoT.
> 
> Nota
> 
> In base al sistema operativo, il browser potrebbe non aprirsi e reindirizzarti alla pagina principale della box IoT. In questo caso, apri il browser manualmente e vai su `http://10.11.12.1`.
> 
>   4. nella pagina principale della box IoT, fai clic su Configura accanto alla sezione Stato internet
> 
>   5. aspetta alcuni minuti per la scansione delle reti disponibili, seleziona la rete, inserisci la password della Wi-Fi e fai clic su Connetti.
> 
> 


Nota

Una volta collegato alla rete Wi-Fi, la box IoT smette di emettere il proprio segnale Wi-Fi e il computer dovrebbe ricollegarsi automaticamente alla rete originale. Se così non fosse, effettua la connessione manualmente.

## Pagina principale box IoT¶

Per accedere alla pagina principale della box IoT, apri un browser web **sulla stessa rete della box IoT** e accedi all’indirizzo IP della box IoT.

L’indirizzo IP della box IoT può essere recuperato:

  * collegando la box IoT a un monitor esterno: l’indirizzo IP viene visualizzato sullo schermo

  * collegando la box IoT a una stampante: l’indirizzo IP viene stampato automaticamente

  * accedendo all’interfaccia dell’amministratore del router al quale è connessa la box IoT oppure utilizzando un software di terze parti per scansionare la rete.




Una volta [collegata la box IoT al database Odoo](connect.html), è possibile accedere alla pagina principale da Odoo aprendo l’app IoT e facendo clic sull’URL mostrato sulla scheda della box IoT.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/iot_box.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](windows_iot.html "Windows virtual IoT") |
  * [precedente](../iot.html "Internet delle cose \(IoT\)") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Box IoT


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