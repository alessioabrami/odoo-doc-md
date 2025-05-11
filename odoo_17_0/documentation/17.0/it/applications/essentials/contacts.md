# Contatti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](contacts/merge.html "Unisci contatti") |
  * [precedente](search.html "Cercare, filtrare e raggruppare i record") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Contatti



# Contatti¶

L’applicazione _Contatti_ viene installata su tutti i database Odoo. I contatti vengono creati per i clienti con cui l’azienda ha rapporti commerciali tramite Odoo. Un contatto è un archivio di informazioni aziendali vitali, in grado di facilitare la comunicazione e le transazioni commerciali.

## Modulo contatto¶

Per creare un nuovo contatto, naviga nella app Contatti e fai clic su Crea. Apparirà un nuovo modulo dove potrai aggiungere varie informazioni di contatto.

### Tipo di contatto¶

Odoo permette di creare contatti Persona e Aziendali. Seleziona Persona o Azienda, in base al tipo di contatto che stai aggiungendo.

### Nome¶

Per prima cosa, inserisci il nome della Persona o dell”Azienda. Il nome nel database apparirà in questo modo. Il campo è **obbligatorio**.

Suggerimento

I contatti Persona possono avere un contatto di tipo Azienda collegato. Dopo aver selezionato Persona, apparirà un nuovo campo Nome azienda… al di sotto del campo nome.

### Indirizzo¶

In seguito, inserisci l”indirizzo dell”Azienda o della Persona.

Suggerimento

Se l’opzione Persona viene scelta, in seguito il _tipo di indirizzo_ può essere scelto da un menu a discesa. Le opzioni per questo menu includono: Contatto, Indirizzo di fatturazione, Indirizzo di consegna, Altro indirizzo e Indirizzo privato.

### Campi aggiuntivi¶

I dettagli aggiuntivi sono inclusi nel modulo iniziale. Sono disponibili i seguenti campi:

  * IVA: numero di partita IVA.

  * Identificazione cittadino: numero di identificazione del cittadino o del governo (disponibile solo per contatti Persona).

  * Posizione lavorativa: indica la posizione lavorativa della Persona (disponibile solo per contatti Persona).

  * Telefono: indica il numero di telefono (con il codice Paese). Effettua una chiamata, invia un SMS o un messaggio WhatsApp passando con il mouse sul campo del modulo per poi fare clic sull’opzione desiderata.

  * Cellulare: indica il numero di cellulare (con il codice Paese). Effettua una chiamata, invia un SMS o un messaggio WhatsApp passando con il mouse sul campo del modulo per poi fare clic sull’opzione desiderata.

  * E-mail: inserisci l’indirizzo e-mail con il dominio.

  * Sito web: inserisci l’indirizzo completo del sito web, iniziando con `http` o `https`.

  * Titolo: seleziona Dottore, Signora, Signorina, Signore, Professore oppure crea un nuovo titolo direttamente dal campo.

  * Tag: inserisci tag preconfigurati digitandoli nel campo o facendo clic sul menu a discesa per poi selezionarne uno. Per crearne uno nuovo, digita un nuovo tag nel campo e fai clic su Crea dal menu a discesa che spunta.




### Scheda contatti e indirizzi¶

Nel parte inferiore del modulo contatto ci sono varie schede. Nella scheda Contatti e indirizzi, possono essere aggiunti i contatti associati ad un”Azienda e gli indirizzi collegati. Ad esempio, in questo campo è possibile aggiungere una persona di contatto specifica per l’azienda.

È possibile aggiungere indirizzi multipli sia per i contatti di tipo Persona che Azienda. Per farlo, fai clic su Aggiungi nella scheda Contatti e indirizzi. Facendolo, spunterà il modulo pop-up Crea contatto, dal quale puoi configurare indirizzi aggiuntivi.

Nel modulo a comparsa Crea contatto, comincia facendo clic sul campo in alto Altro indirizzo per visualizzare il menu a discesa con le opzioni legate all’indirizzo stesso.

Seleziona una delle seguenti opzioni:

  * Contatto: aggiunge un altro contatto al modulo esistente.

  * Indirizzo di fatturazione: aggiunge un indirizzo di fatturazione specifico al modulo contatto esistente.

  * Indirizzo di consegna: aggiunge un indirizzo di consegna specifico al modulo contatto esistente.

  * Altro indirizzo: aggiunge un indirizzo alternativo al modulo di contatto esistente.

  * Indirizzo privato: aggiunge un indirizzo privato al modulo di contatto esistente.




Una volta selezionata un’opzione, inserisci le informazioni di contatto corrispondenti che dovrebbero essere utilizzate per il tipo di indirizzo specificato.

Aggiungi Nome contatto, Indirizzo, E-mail, insieme a numero di Telefono e/o Cellulare in basso.

Imposta la Posizione lavorativa che appare se il tipo di indirizzo del Contatto è stato selezionato. Questo è simile al contatto Persona.

Per aggiungere una nota, fai clic sul campo testo accanto a Note e scrivi qualsiasi cosa adatta al cliente o contatto.

In seguito, fai clic su Salva e chiudi per salvare l’indirizzo e chiudi la finestra Crea contatto. Oppure, fai clic su Salva e nuovo per salvare l’indirizzo e inserirne uno nuovo.

### Scheda Vendite e acquisti¶

La scheda Vendite e acquisti appare solo se sono state installate le app _Vendite_ , _Acquisti_ **oppure** _Punto vendita_.

La Posizione di bilancio può essere configurata nella scheda Vendite e acquisti. Seleziona una Posizione fiscale dal menu a discesa.

#### Sezione vendite¶

Nella sezione Vendite, è possibile assegnare un Addetto vendite al contatto. Per farlo, fai clic sul campo a tendina Addetto vendite e selezionane uno. Crea un nuovo Addetto vendite digitando il nome utente e facendo la scelta giusta.

Se necessario, è possibile configurare alcuni Temini di pagamento o un determinato Listino prezzi. Fai clic sul menu a discesa accanto a Termini di pagamento e modifica il campo con uno dei Termini di pagamento preselezionati oppure fai clic su Crea. Seleziona il menu a discesa Listino prezzi per scegliere il Listino prezzi appropriato.

Fai clic sul campo Metodo di consegna per selezionare un’opzione dal menu a discesa.

#### Sezione Punto vendita¶

Sotto la voce Punto vendita, inserisci un Codice a barre che può essere utilizzato per individuare il contatto. Usa il campo Punti fedeltà per tracciare i punti che l’utente accumula come parte del _Programma fedeltà_.

#### Sezione Acquisti¶

Specifica informazioni relative a Termini di pagamento, 1099 Box e Metodo di pagamento preferito qui. È possibile configurare anche un Promemoria di ricezione da qui.

#### Sezione Varie¶

Sotto la voce Varie, usa il campo Riferimento per aggiungere qualsiasi informazione relativa al contatto. Se questo contatto deve essere accessibile solo per un’azienda in un database con più aziende, selezionalo nell’elenco a discesa del campo Azienda. Usa il menu a discesa Sito web per limitare la pubblicazione del contatto ad un solo sito web (se si lavora su un database con più siti web). Seleziona uno o più Tag sito web per aiutare il filtraggio dei clienti pubblicati nella pagina `/customers` del sito web. Seleziona un Settore per il contatto dal menu a discesa. Usa il campo Politiche SLA per assegnare una politica SLA di _Assistenza_ al contatto.

### Scheda Contabilità¶

La scheda Contabilità appare quando installi l’applicazione _Contabilità_. Qui, un utente può aggiungere qualsiasia Conto corrente correlato oppure configurare Registrazioni contabili predefinite.

Sotto la voce Varie, usa il campo LEI per inserire un identificativo della persona giuridica, se necessario.

### Scheda Note interne¶

Dopo la scheda Contabilità, c’è la scheda Note interne, dove è possibile lasciare note sul modulo contatto, proprio come nel modulo di contatto di cui sopra.

### Scheda Assegnazione partner¶

La scheda successiva è Assegnazione partner, che per impostazione predefinita include la sezione Geolocalizzazione e altre opzioni partner incluse Attivazione partner e Revisione partner. Queste sono visibili **solo** se è stato installato il modulo _Rivenditori_.

Vedi anche

Consulta la [documentazione relativa ai rivenditori](../sales/crm/track_leads/resellers.html) per maggiori informazioni sulla pubblicazione dei partner sul sito web.

### Scheda Iscrizione¶

Infine, nei moduli contatto c’è la scheda Iscrizione, che può aiutare gli utenti a gestire le iscrizioni offerte ad un contatto specifico. Nota che questa scheda appare **solo** a seguito dell’installazione dell’applicazione _Membri_.

#### Attivare l’iscrizione¶

Per attivare l’iscrizione di un contatto, fai clic su Aggiungi iscrizione nella scheda Iscrizione di un modulo contatto. Nella finestra che appare, seleziona un”Iscrizione dal menu a discesa. In seguito, configura un Prezzo socio. Fai clic su Fattura l’iscrizione quando entrambi i campi sono completati.

In alternativa, per offrire un’iscrizione gratuita, spunta la casella Iscritto non pagante nella scheda Iscrizione del modulo contatto.

Vedi anche

Consulta la [documentazione membri](../sales/members.html) per maggiori informazioni sulla pubblicazione dei membri sul sito web.

## Pulsanti smart¶

Nella parte alta del modulo contatto, ci sono alcune opzioni aggiuntive disponibili conosciute con il nome di _pulsanti smart_.

Qui, Odoo mostra un’ampia gamma di record, legati al contatto e creati da altre applicazioni, Odoo integra le informazioni da ogni singola app ed è per questo motivo che ci sono molti pulsanti smart.

Example

Ad esempio, il pulsante Opportunità consente di visualizzare tutte le opportunità legate al cliente presenti nell’app _CRM_.

Suggerimento

Se le applicazioni corrispondenti sono installate, i pulsanti smart correlati appariranno automaticamente sul modulo contatto.

Un utente può vedere qualsiasi Riunione, Vendita, Ordine POS, Abbonamento, Attività di progetto e il pulsante smart Altro rivela opzioni aggiuntive, tramite il menu a discesa. Un utente può accedere rapidamente ad Acquisti, attività Helpdesk, Tasso di puntualità per le consegne, informazioni di fatturazione, Fatture fornitore e a Partitari clienti/fornitori collegati al contatto.

Consegne, documenti, carte fedeltà e addebiti diretti sono _anche_ collegati ai pulsanti smart, come questo, se ci sono casi di contatto in sospeso o in corso di registrazione.

Se il contatto è un partner, l’utente può visitare la pagina del partner sul sito web realizzato con Odoo facendo clic sul pulsante Vai al sito web.

### Archiviare i contatti¶

Se un utente decide di non volere avere più un contatto attivo, il record può essere archiviato. Per farlo, vai sul menu __ Azioni nella parte superiore del modulo e fai clic su Archivia.

In seguito, fai clic su OK nella finestra a comparsa di Conferma.

Una volta che il contatto è stato archiviato, come indicato da un banner in alto, quest’ultimo non verrà mostrato nella pagina dei contatti principali ma è possibile cercarlo con il filtro Archiviati.

Suggerimento

Un contatto può essere _non archiviato_ , se l’utente decide di lavorare di nuovo con loro. Per farlo, fai clic sul menu __ Azioni nella parte superiore del modulo contatto archiviato per poi cliccare su Annulla archiviazione. Dopo averlo fatto, il banner Archiviato scompare e il contatto viene ripristinato.

Vedi anche

  * [Aggiungere vari indirizzi nel CRM](../sales/sales/send_quotations/different_addresses.html)

  * [Tutorial Contatti e-learning Odoo](https://www.odoo.com/slides/slide/contacts-2527?fullscreen=1)




  * [Unisci contatti](contacts/merge.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/essentials/contacts.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](contacts/merge.html "Unisci contatti") |
  * [precedente](search.html "Cercare, filtrare e raggruppare i record") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Contatti


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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