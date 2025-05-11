# Collegare uno schermo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](measurement_tool.html "Collegare uno strumento di misura") |
  * [precedente](../devices.html "Dispositivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare uno schermo



# Collegare uno schermo¶

In Odoo, è possibile collegare una box IoT a uno schermo. Dopo essere stato configurato, lo schermo può essere utilizzato per mostrare gli ordini del Punto vendita ai clienti.

Un esempio di ordine POS (Punto vendita) su uno schermo.¶

Accedi allo schermo del cliente andando sulla pagina principale della box IoT e fai clic sul pulsante Schermo POS. Per accedere alla pagina principale della box IoT, apri l’app IoT ‣ Box IoT e fai clic sul link corrispondente della pagina della box IoT.

## Connessione¶

La modalità di connessione dello schermo alla box IoT cambia a seconda del modello.

IoT Box model 4IoT Box model 3

Collega fino a due schermi con i cavi micro-HDMI sul lato della box IoT. Se sono collegati due schermi, è possibile visualizzare contenuti diversi (vedi sezione Uso dello schermo).

Collega lo schermo con un cavo HDMI in un lato della box IoT

Vedi anche

Schema Raspberry Pi.

Importante

Lo schermo o gli schermi devono essere collegati prima che la box IoT venga accesa. Se già accesa, collega lo schermo e poi riavvia la box IoT scollegandola per dieci secondi e ricollegandola alla fonte di corrente.

Avvertimento

L’uso di adattatori HDMI/micro-HDMI può causare problemi che si traducono in una schermata nera e vuota sullo schermo. Si consiglia di utilizzare il cavo specifico per il collegamento dello schermo.

Se la connessione è avvenuta con successo, lo schermo dovrebbe mostrare la schermata Schermo cliente POS.

Lo schermo appare anche nell’elenco di Schermi nella pagina principale della box IoT. In alternativa, è possibile visualizzare lo schermo aprendo l’app IoT ‣ Dispositivi.

Nota

Se non viene rilevato nessuno schermo, verrà visualizzato un schermo predefinito denominato Schermo distante. Questo indica che non c’è uno schermo hardware collegato.

> ## Utilizzo¶

### Mostrare gli ordini del Punto vendita ai clienti¶

Per utilizzare lo schermo nell’app _Punto vendita_ , vai su Punto vendita ‣ Configurazione ‣ Punto vendita, seleziona un POS, fai clic su Modifica se necessario e attiva la funzionalità Box IoT.

In seguito, seleziona lo schermo dal menu a discesa Display cliente. Poi fai clic su Salva, se richiesto.

Ora lo schermo è disponibile per le sessioni POS. Un’icona a forma di schermo apparirà nel menu nella parte alta dello schermo per indicare lo stato della connessione.

Lo schermo mostrerà automaticamente gli ordini del POS e si aggiornerà quando i cambiamenti vengono applicati agli ordini.

### Visualizzare un sito web sullo schermo¶

Apri la vista modulo dello schermo tramite l’app IoT ‣ Dispositivi ‣ Schermo cliente. Ciò consente all’utente di scegliere un URL specifico per il sito web da mostrare sullo schermo usando il campo Mostra URL.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/screen.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](measurement_tool.html "Collegare uno strumento di misura") |
  * [precedente](../devices.html "Dispositivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare uno schermo


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