# Regole di approvazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../general.html "Impostazioni generali") |
  * [precedente](pdf_reports.html "Reportistica in PDF") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di approvazione



# Regole di approvazione¶

Le regole di approvazione vengono utilizzate per automatizzare i processi di approvazione delle azioni. Ti permettono di definire i criteri quando è richiesta un’approvazione prima che venga eseguita un’azione utilizzando un pulsante.

## Configurazione¶

Per aggiungere regole di approvazione con Studio, segui questi passaggi:

  1. [apri studio](../studio.html#studio-access) e passa alla [vista](views.html) richiesta

  2. scegli il pulsante a cui applicare la regola

  3. fai clic su __ Aggiungi fase di approvazione nella scheda __ Proprietà

  4. specifica quali utenti sono responsabili dell’approvazione dell’azione utilizzando uno dei seguenti campi o entrambi:

>      * Approvatori per specificare uno o più utenti
> 
>      * Gruppo approvatore per specificare un gruppo utente.
> 
> Nota
> 
> Verrà creata un’attività per tutti gli utenti impostati come Approvatori quando ne viene richiesta l’approvazione.

  5. (_facoltativo_) seleziona gli Utenti da notificare tramite nota interna quando l’azione viene approvata o rifiutata

  6. (_facoltativo_) aggiungi una Descrizione da visualizzare sul pulsante.




Suggerimento

Puoi specificare le condizioni da rispettare per applicare una fase di approvazione facendo clic sull’icona __( filtro) accanto al campo Approvatori.

Per aggiungere un’altra fase di approvazione, fai clic su __ Aggiungi fase di approvazione. In presenza di più fasi, puoi:

  * attivare un”Approvazione esclusiva su ogni fase in modo che l’utente che approva una fase non ne approverà un’altra dello stesso record

  * modificare l”Ordine di approvazione delle fasi selezionando un numero, `1` per la prima fase, `2` per la seconda e così via. Un utente responsabile di una fase più elevata può approvare/rifiutare le fasi precedenti a meno che non venga selezionata l”Approvazione esclusiva




fare clic sull’icona __( cestino) accanto al campo Approvatori per eliminare una fase di approvazione.

Suggerimento

Puoi creare [gruppi utente](../general/users/access_rights.html#access-rights-groups) specifici per le approvazioni.

## Utilizzo¶

Una volta definita una regola di approvazione per un pulsante, l’icona **avatar utente** apparirà accanto all’etichetta del pulsante per ogni fase di approvazione. Facendo clic sull’icona scoprirai la fase(i).

Nota

Se un utente non autorizzato fa clic sul pulsante, verrà visualizzato un messaggio di errore e verrà creata un’attività per gli utenti specificati nel campo Approvatori.

Gli utenti autorizzati possono:

  * eseguire direttamente l’azione facendo clic sul pulsante se si tratta dell’ultima/sola fase di approvazione

  * approvare l’azione e permettere a un altro utente di eseguirla o spostarla alla prossima fase di approvazione facendo clic sull’icona **avatar utente** accanto all’etichetta del pulsante per poi fare clic su __( approva)

  * rifiutare l’azione facendo clic sull’icona **avatar utente** accanto all’etichetta del pulsante e in seguito sul pulsante __( rifiuta)

  * (solo per gli utenti selezionati nel campo Approvatori) delegare i diritti di approvazione a uno o più utenti per **tutti i record** :

    * facendo clic sull’icona __( vista kanban) e in seguito Delega;

    * selezionando uno o più Approvatori, Fino a quando avranno i diritti di approvazione (per sempre se il campo è vuoto) e, in via facoltativa, l’utente o gli utenti che dovrebbero essere notificati tramite nota interna utilizzando il campo Notifica a.




Suggerimento

  * Un utente che approva/rifiuta un’azione può revocare la propria decisione facendo clic sull’icona **avatar utente** accanto all’etichetta del pulsante e in seguito sul pulsante __( revoca). Inoltre, possono revocare la decisione di altri utenti per fasi con un Ordine di approvazione più basso a meno che non sia attivata l’opzione Approvazione esclusiva.

  * Le approvazioni vengono tracciate nel chatter dei record. Una voce di approvazione viene creata ogni volta che viene seguita un’azione legata all’approvazione con Studio. Per accedere alle voci di approvazione, [attiva la modalità sviluppatore](../general/developer_mode.html) e vai su Impostazioni ‣ Funzioni tecniche ‣ Voci approvazione Studio.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/studio/approval_rules.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../general.html "Impostazioni generali") |
  * [precedente](pdf_reports.html "Reportistica in PDF") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Regole di approvazione


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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