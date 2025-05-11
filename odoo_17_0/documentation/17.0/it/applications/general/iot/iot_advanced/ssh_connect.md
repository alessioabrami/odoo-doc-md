# Connessione SSH box IoT — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../devices.html "Dispositivi") |
  * [precedente](updating_iot.html "Aggiornamenti sistema IoT") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Connessione SSH box IoT



# Connessione SSH box IoT¶

Nota

Le connessioni SSH sono disponibili solamente per [box IoT](../iot_box.html) e non per la [Windows virtual IoT](../windows_iot.html).

Avvertimento

  * Questa funzionalità dovrebbe essere utilizzata **solamente** con parti fidate, in quanto fornisce accessi amministrativi alla box IoT che possono causare problemi relativi alla sicurezza.

  * La gestione di una connessione SSH **non** è compresa tra le mansioni standard del supporto Odoo. Visita la pagina [supporto Odoo](https://www.odoo.com/help) per ulteriori informazioni.




Per fornire una connessione SSH a una box IOT, è necessario generare una password:

  1. Accedi alla pagina principale della box IoT aprendo l’applicazione IoT e facendo clic sull’indirizzo IP visualizzato sulla scheda della box IoT.

  2. Fai clic sul pulsante __( ingranaggio) in alto a destra e poi su Debug remoto.

  3. Nel pop-up Debug remoto che appare, fai clic su Genera e salva la password. Una volta chiuso il pop-up, la password non sarà più disponibile.

  4. Inserisci il Token di autenticazione fornito dall’utente che sta cercando di collegare la box IoT.

  5. Fai clic su Attiva modalità debugging.




Vedi anche

  * [Box IoT](../iot_box.html)

  * [Conessione sistema IoT a Odoo](../connect.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/iot_advanced/ssh_connect.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../devices.html "Dispositivi") |
  * [precedente](updating_iot.html "Aggiornamenti sistema IoT") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Avanzato](../iot_advanced.html) »
  * Connessione SSH box IoT


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