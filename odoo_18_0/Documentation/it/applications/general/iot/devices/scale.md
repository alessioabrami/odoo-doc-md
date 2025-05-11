# Collegare una bilancia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [precedente](printer.html "Collegare una stampante") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
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

  1. [accedi alle impostazioni del Punto vendita](../../../sales/point_of_sale/configuration.html#configuration-settings) e seleziona il POS che desideri oppure fai clic sul pulsante a forma di ellissi verticale (⋮) sulla scheda di un POS e fai clic su Modifica

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




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/general/iot/devices/scale.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../email_communication.html "Comunicazione in Odoo via e-mail") |
  * [precedente](printer.html "Collegare una stampante") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
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
  *[FBM]: Fulfilled by Merchant
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
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID