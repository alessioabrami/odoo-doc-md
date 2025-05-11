# Creare opportunità dai moduli di contatto online — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_manual.html "Creare lead \(da e-mail o manualmente\)") |
  * [precedente](convert.html "Convertire i Lead in opportunità") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare opportunità dai moduli di contatto online



# Creare opportunità dai moduli di contatto online¶

L’aggiunta di un modulo di contatto a un sito web facilita la conversione dei visitatori in lead e opportunità. Dopo che il visitatore ha inviato le proprie informazioni, è possibile creare automaticamente un’opportunità e assegnarla a un team di vendita e a un addetto vendite.

## Personalizzare i moduli di contatto¶

Per impostazione predefinita, la pagina _Contattaci_ di un sito web Odoo mostra un modulo di contatto preconfigurato. È possibile personalizzare il modulo per soddisfare le necessità di un team vendita specifico.

Apri l’app Sito web ‣ Contattaci poi fai clic su Modifica nell’angolo in alto a destra dello schermo per aprire l’editor. Fai clic sul blocco di costruzione del modulo nel corpo della pagina per aprire le impostazioni di configurazione del modulo nella barra laterale di destra. Per personalizzare il modulo di contatto dalla sezione Modulo della barra laterale sono disponibili le seguenti opzioni:

  * Azione: l’azione predefinita per un modulo di contatto è Invia e-mail. Seleziona Crea opportunità dal menu a tendina per acquisire le informazioni nell’app _CRM_.

  * Team vendite: scegli un team vendita dal menu a tendina a cui assegnare l’opportunità che deriva dal modulo. Il campo appare **solo** se il campo Azione viene impostato su Crea opportunità.

  * Addetto vendite: se le opportunità devono essere assegnate a un addetto vendite specifico, selezionalo dal menu a discesa. Se non viene effettuata alcuna selezione in questo campo, le opportunità vengono assegnate in base alle regole esistenti del team.

  * Campi contrassegnati: usa il campo per modificare la gestione dei campi contrassegnati nel modulo. L’impostazione predefinita e consigliata è Richiesti.

  * Testo contrassegnato: scegli in che modo individuare i Campi contrassegnati. Il carattere predefinito è un asterisco (`*`).

  * Larghezza etichette: utilizza questo campo per modificare la larghezza in pixel delle etichette, se lo desideri.

  * In caso di successo: scegli in che modo la pagina web reagisce quando un cliente invia un modulo. L’opzione Niente mantiene il cliente nella stessa schermata, con l’aggiunta di un messaggio di conferma che indica che il modulo è stato inviato correttamente. L’opzione Reindirizza porta il cliente su una nuova pagina in base all’indirizzo inserito nel campo URL in basso. L’opzione Mostra messaggio sostituisce il modulo con un messaggio preconfigurato che informa il cliente che qualcuno dovrà rispondergli il prima possibile.

  * URL: se selezioni l’opzione Reindirizza per il campo In caso di successo, inserisci l’URL della pagina web alla quale verranno reindirizzati i clienti dopo aver inviato correttamente il modulo.

  * Visibilità: utilizza il menu a discesa per aggiungere qualsiasi condizione di visibilità per questo campo, se necessario.




Importante

Se nelle impostazioni del _CRM_ viene attivata l’opzione _lead_ , selezionando Crea opportunità verrà generato un lead. Per attivare i lead, accedi all’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. In seguito, fai clic su Salva.

### Personalizzare i campi del modulo di contatto¶

Oltre alle impostazioni del modulo, è possibile personalizzare anche le impostazioni di ciascun campo. Con il menu dell’editor web ancora aperto, faI clic su un campo per aprire la sezione delle impostazioni di configurazione Campo nella barra laterale. Per personalizzare un campo sono disponibili le seguenti opzioni:

  * Tipo: scegli un’opzione di campo personalizzata o un tipo di campo esistente

  * Tipo inserimento: determina il tipo di informazioni che i clienti devono inserire. Le opzioni disponibili sono: Testo, E-mail, Telefono o Url. La selezione effettuata in questo campo limita il formato che i clienti possono utilizzare per inserire le informazioni.

  * Etichetta: inserisci il nome del campo.

  * Posizione: scegli il modo in cui l’etichetta è allineata con il resto del modulo. L’etichetta può essere nascosta, sopra, a sinistra del campo o a destra e più vicina allo stesso.

  * Descrizione: fai scorrere il cursore per aggiungere una descrizione al campo, che può fornire ulteriori istruzioni ai clienti. Fai clic sotto il campo del modulo per aggiungere la descrizione.

  * Segnaposto: inserisci un esempio per aiutare gli utenti a capire come inserire le informazioni in cui la formattazione è importante, come un numero di telefono o un indirizzo e-mail.

  * Valore predefinito: inserisci un valore da includere nel modulo, per impostazione predefinita, se il cliente non inserisce informazioni nel campo. _Non è consigliabile includere un valore predefinito per i campi obbligatori_.

  * Richiesto: se questo campo **deve** essere compilato per ogni invio, fai scorrere il cursore per contrassegnarlo come obbligatorio.

  * Visibilità: seleziona quando questo campo deve essere visibile. Usa il pulsante a sinistra per scegliere se mostrare o nascondere questo campo agli utenti desktop. Usa il pulsante a destra per scegliere se mostrare o nascondere questo campo agli utenti mobili.

  * Animazione: scegli se questo campo deve avere un’animazione.




## Visualizzare opportunità¶

Quando un cliente invia un modulo di contatto e viene creata un’opportunità, questa viene assegnata in base alle impostazioni del modulo. Per visualizzare le opportunità, apri l’app CRM ‣ Vendite ‣ La mia pipeline.

Nota

Se i lead sono attivati nel database, gli invii dei moduli di contatto vengono generati come lead e non come opportunità. Per attivare i contatti, accedi all’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. Successivamente, fai clic su Salva.

Accedi all’app CRM ‣ Lead per visualizzare i lead appena creati.

Sulla dashboard La mia pipeline, fai clic sulla scheda di un’opportunità nella vista kanban per aprire il record dell’opportunità. Le informazioni inviate dal cliente saranno visibili sul record dell’opportunità.

Nota

Poiché i campi del modulo di contatto sono personalizzabili, i campi del record dell’opportunità, in cui sono memorizzate le informazioni del modulo, variano di conseguenza.

Se il modulo di contatto preconfigurato viene utilizzato, il campo _Oggetto_ viene aggiunto al campo Titolo e il contenuto nel campo Note, etichettato come La tua domanda, viene aggiunto nella scheda Note interne.

Vedi anche

  * [Gestire i team vendite](../pipeline/manage_sales_teams.html)

  * [Convertire i Lead in opportunità](convert.html)

  * [Assegnare lead con calcolo previsionale](../track_leads/lead_scoring.html)

  * [Moduli sito web](../../../websites/website/web_design/building_blocks/dynamic_content.html#website-dynamic-content-form)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/crm/acquire_leads/opportunities_form.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_manual.html "Creare lead \(da e-mail o manualmente\)") |
  * [precedente](convert.html "Convertire i Lead in opportunità") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Creare opportunità dai moduli di contatto online


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
  *[NSSL]: Non-Shopee Supported Logistics