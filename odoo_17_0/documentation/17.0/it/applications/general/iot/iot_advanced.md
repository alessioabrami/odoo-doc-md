# Avanzato — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot_advanced/https_certificate_iot.html "Certificato HTTPS \(IoT\)") |
  * [precedente](connect.html "Conessione sistema IoT a Odoo") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Avanzato



# Avanzato¶

  * Certificato HTTPS (IoT)
    * [Creazione certificato HTTPS](iot_advanced/https_certificate_iot.html#https-certificate-generation)
    * Errori e problemi legati alla generazione del certificato HTTPS
      * [Certificato HTTPS non generato](iot_advanced/https_certificate_iot.html#the-https-certificate-does-not-generate)
      * [Accesso alla pagina principale del sistema IoT tramite indirizzo IP ma non via URL `xxx.odoo-iot.com`](iot_advanced/https_certificate_iot.html#the-iot-system-s-homepage-can-be-accessed-using-its-ip-address-but-not-the-xxx-odoo-iot-com-url)
      * Errori
        * [`ERR_IOT_HTTPS_CHECK_NO_SERVER`](iot_advanced/https_certificate_iot.html#err-iot-https-check-no-server)
        * [`ERR_IOT_HTTPS_CHECK_CERT_READ_EXCEPTION`](iot_advanced/https_certificate_iot.html#err-iot-https-check-cert-read-exception)
        * [`ERR_IOT_HTTPS_LOAD_NO_CREDENTIAL`](iot_advanced/https_certificate_iot.html#err-iot-https-load-no-credential)
        * [`ERR_IOT_HTTPS_LOAD_REQUEST_EXCEPTION`](iot_advanced/https_certificate_iot.html#err-iot-https-load-request-exception)
        * [`ERR_IOT_HTTPS_LOAD_REQUEST_STATUS`](iot_advanced/https_certificate_iot.html#err-iot-https-load-request-status)
        * [`ERR_IOT_HTTPS_LOAD_REQUEST_NO_RESULT`](iot_advanced/https_certificate_iot.html#err-iot-https-load-request-no-result)
  * Aggiornamenti sistema IoT
    * [Aggiornamento immagine e codice principale](iot_advanced/updating_iot.html#image-and-core-code-update)
    * [Aggiornamento gestore (driver)](iot_advanced/updating_iot.html#handler-driver-update)
  * [Connessione SSH box IoT](iot_advanced/ssh_connect.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/iot_advanced.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](iot_advanced/https_certificate_iot.html "Certificato HTTPS \(IoT\)") |
  * [precedente](connect.html "Conessione sistema IoT a Odoo") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Internet delle cose (IoT)](../iot.html) »
  * Avanzato


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