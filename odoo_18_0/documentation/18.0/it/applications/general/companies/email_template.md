# Modelli e-mail — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../multi_company.html "Multi-azienda") |
  * [precedente](digest_emails.html "E-mail di riepilogo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Aziende](../companies.html) »
  * Modelli e-mail



# Modelli e-mail¶

I modelli e-mail sono e-mail salvate utilizzate ripetutamente per inviare e-mail dal database. Ciò consente agli utenti di inviare comunicazioni di qualità senza dovere redigere continuamente lo stesso testo.

La creazione di modelli diversi realizzati su misura per situazioni specifiche permette agli utenti di scegliere il messaggio giusto per il pubblico giusto. Tutto questo permette di aumentare la qualità del messaggio e il tasso di coinvolgimento con il cliente.

Nota

In Odoo, i modelli e-mail utilizzano QWeb o XML per poter modificare la visualizzazione dell’e-mail e rendere le personalizzazioni più solide senza dover modificare il codice. Ciò significa che Odoo può utilizzare un’Interfaccia Visiva Grafica (GUI) per modificare e-mail dal codice del backend. Quando l’e-mail ricevuta viene letta dal programma dell’utente finale, nel modulo definitivo appariranno vari formati e grafiche.

Accedi ai modelli e-mail in [modalità sviluppatore](../developer_mode.html#developer-mode) aprendo l’app Impostazioni ‣ Menu tecnico ‣ E-mail ‣ Modelli e-mail.

## Modificare i modelli e-mail¶

La funzionalità _powerbox_ può essere utilizzata quando si lavora con i modelli e-mail e consente di modificare direttamente la formattazione e il testo di un modello e-mail così come aggiungere link, pulsanti, opzioni per appuntamenti o immagini.

In aggiunta, il codice XML/HTML del modello e-mail può essere modificato direttamente attraverso l’icona </>. I segnaposto dinamici (che fanno riferimento a campi in Odoo) sono disponibili per l’utilizzo nei modelli e-mail.

### Powerbox¶

La funzionalità _powerbox_ è un editor di testi arricchito con varie opzioni di formattazione, layout e testo. Può essere utilizzato anche per aggiungere funzionalità XML/HTML in un modello e-mail. Powerbox viene attivato digitando uno slash `/` nel corpo del modello e-mail.

Quando digiti uno slash `/` nel corpo di un modello e-mail apparirà un menu a discesa con le seguenti opzioni:

Struttura

  * Elenco puntato: crea un elenco puntato semplice.

  * Elenco numerato: crea un elenco numerato.

  * Elenco di controllo: traccia le attività con un elenco di controllo.

  * Tabella: inserisci una tabella.

  * Separatore: inserisci una linea orizzontale di divisione.

  * Citazione: aggiungi una sezione con una citazione.

  * Codice: aggiungi una sezione codice.

  * 2 colonne: aggiungi due colonne.

  * 3 colonne: aggiungi tre colonne.

  * 4 colonne: aggiungi quattro colonne.




Formato

  * TItolo 1: sezione titolo grande.

  * Titolo 2: sezione titolo media.

  * Titolo 3: sezione titolo piccola.

  * Cambiare direzione: cambia la direzione del testo.

  * Testo: blocco per un paragrafo.




Elementi multimediali

  * Immagine: inserisci un’immagine.

  * Articolo: link ad un articolo.




Navigazione

  * Link: aggiungi un link.

  * Pulsante: aggiungi un pulsante.

  * Appuntamento: aggiungi un appuntamento specifico.

  * Calendario: pianifica un appuntamento.




Widget

  * 3 stelle: inserisci una valutazione di tre stelle.

  * 5 stelle: inserisci una valutazione di cinque stelle.




Blocchi base

  * Firma: inserisci la tua firma.




Strumenti di marketing

  * Segnaposto dinamici: inserisci contenuti personalizzati.




Suggerimento

Per utilizzare una delle opzioni, fai clic sulla funzione desiderata nel menu powerbox a discesa. Per formattare del testo esistente usando una delle opzioni disponibili (ad es. Titolo 1, Cambiare direzione, ecc.), evidenzia il testo, inserisci la chiave di attivazione (slash) `/`, e seleziona l’opzione desiderata dal menu a discesa.

Vedi anche

Utilizzare segnaposto dinamici

### Editor di codice XML/HTML¶

Per accedere all’editor XML/HTML da un modello e-mail, accedi alla [modalità sviluppatore](../developer_mode.html#developer-mode). In seguito, fai clic sull’icona </> nell’angolo in alto a destra del modello e modifica il codice XML/HTML. Per tornare all’editor di testo standard, fai clic di nuovo sull’icona </>.

Avvertimento

L’editor XML/HTML dovrebbe essere utilizzato con cautela in quanto va a modificare il codice backend del modello. La modifica del codice può causare la rottura immediata del modello o durante l’aggiornamento.

### Segnaposto dinamici¶

I _segnaposto dinamici_ fanno riferimento ad alcuni campi nel database Odoo per produrre dati unici nel modello e-mail.

Example

Molte aziende adorano personalizzare le proprie e-mail con un blocco di informazioni personalizzato per attirare l’attenzione. In Odoo, è possibile farlo utilizzando un segnaposto dinamico per far riferimento al campo nel modello. Ad esempio, è possibile far riferimento al nome di un cliente in un’e-mail dal campo Cliente sul modello Ordine di vendita. Il segnaposto dinamico per questo campo è: `{{ object.partner_id }}`.

I segnaposto dinamici sono codificati per la visualizzazione di campi all’interno del database. È possibile utilizzarli nel Corpo (scheda Contenuto) del modello e-mail. Inoltre, possono essere utilizzati nei campi presenti nella scheda Configurazione e-mail, nell”Oggetto dell’e-mail e per la Lingua.

Per utilizzare i segnaposto dinamici nel Corpo di un’e-mail, apri la funzionalità **powerbox** digitando `/` nel corpo del modello e-mail, nella scheda Contenuto. Scorri fino in fondo all’elenco delle opzioni e scegli Strumenti marketing. In seguito, seleziona Segnaposto dinamico e scegline uno dall’elenco per poi seguire i comandi per configurarlo con il campo Odoo desiderato. Ogni segnaposto dinamico è diverso.

Nota

Ogni combinazione unica di Campi, Sottomodelli e Campi secondari crea un segnaposto dinamico diverso. Immaginala come una combinazione per il campo in fase di creazione.

Per cercare i campi disponibili, digita il nome nel frontend (nell’interfaccia utente) del campo. Come risultato otterrai tutti i campi disponibili per il modello per cui è stata creata l’e-mail.

Avvertimento

La personalizzazione dei modelli e-mail non è gestita dal team di supporto di Odoo.

### Editor di testi ricco di funzionalità¶

Se hai bisogno di modificare un titolo, le dimensioni o lo stile del carattere, il colore, aggiungere un elenco o un link, è possibile farlo accedendo alla barra degli strumenti dell’editor di testi ed evidenziando il testo nel modello e-mail.

### Ripristinare i modelli e-mail¶

Se il modello e-mail non funziona perché il codice è stato modificato, puoi ripristinarlo tornando alla versione originale. Fai clic sul pulsante Ripristina modello nella parte in alto a sinistra dello schermo e il modello verrà ripristinato.

### Risposte predefinite nei modelli e-mail¶

Nella scheda Configurazione e-mail di un modello puoi trovare il campo Rispondi a. In questo campo, aggiungi gli indirizzi e-mail a cui reindirizzare le risposte quando invii e-mail di massa utilizzando il modello.

Suggerimento

Aggiungi indirizzi e-mail multipli aggiungendo una virgola «,» tra gli indirizzi o i segnaposto dinamici.

Il campo Rispondi a viene utilizzato **solo** per e.mail di massa (invio di e-mail in gruppo). Le e-mail di massa possono essere inviate in quasi tutte le applicazioni Odoo che dispongono dell’opzione vista elenco.

Per inviare e-mail di massa, apri la vista elenco, spunta le caselle accanto agli indirizzi desiderati a cui inviare e-mail, fai clic sul pulsante Azione (rappresentato dall’icona ⚙️ (ingranaggio)) e seleziona l’opzione e-mail desiderata dal menu a discesa Azioni. Le opzioni e-mail possono variare in base all’applicazione e alla vista elenco specifica.

Nel caso in cui sia possibile inviare un’e-mail, apparirà una finestra pop-up con i valori che possono essere definiti e personalizzati. L’opzione sarà disponibile dal pulsante Azioni presente nelle pagine da cui le e-mail possono essere inviate in gruppo. Ad esempio, nella pagina Clienti dell’app CRM. L’azione viene eseguita dal database Odoo.

## E-mail transazionali e URL corrispondenti¶

In Odoo, più eventi possono attivare l’invio di e-mail automatiche. Tali e-mail sono conosciute come _e-mail transazionali_ e a volte contengono link di reindirizzamento al database Odoo.

Per impostazione predefinita, i link generati dal database utilizzano la chiave dinamica `web.base.url` definita nei parametri di sistema. Per maggiori informazioni, consulta la sezione [Parametri di sistema](../../websites/website/configuration/domain_names.html#domain-name-web-base-url).

Se l’applicazione _Sito web_ non è installata, la chiave `web.base.url` sarà sempre il parametro predefinito utilizzato per generare tutti i link.

Importante

La chiave `web.base.url` può avere un solo valore, il che significa che in un ambiente database con più aziende o siti web, anche se è stato stabilito un nome di dominio specifico per ogni sito web, i link generati per condividere un documento (o i link di un’e-mail transazionale) potrebbero essere gli stessi, indipendentemente dal sito web/azienda legata all’invio dell’e-mail/documento.

Example

Se il Valore del parametro di sistema web.base.url è uguale a `https://www.mycompany.com` e vi sono due aziende distinte in Odoo con URL diversi: `https://www.mycompany2.com` e `https://www.mycompany1.com`, i link creati da Odoo per condividere un documento o inviare un’e-mail transazionale derivano dal dominio: `https://www.mycompany.com`, indipendentemente dall’azienda che invia il documento o l’e-mail.

Non è sempre così in quanto alcune applicazioni Odoo (_E-commerce_ , ad esempio) hanno un link configurato nel database con l’applicazione _Sito web_. In questo caso, se viene definito un dominio specifico per il sito web, l’URL generato nel modello e-mail utilizza il dominio definito sul sito corrispondente dell’azienda.

Example

Quando un cliente effettua un acquisto su un sito web _e-commerce_ , l’ordine ha un link con il sito web. Di conseguenza, i link nell’e-mail di conferma inviata al cliente utilizzano il nome di dominio per il sito web specifico.

Nota

Un documento condiviso utilizzando l’app _Documenti_ utilizzerà **sempre** la chiave `web.base.url`, in quanto il documento condiviso non è associato a nessun sito web in particolare. Questo significa che l’URL sarà sempre lo stesso (valore chiave `web.base.url`), non importa da quale azienda sia condiviso. Si tratta di una limitazione di cui siamo al corrente.

Per maggiori informazioni su come configurare i domini, consulta la [documentazione relativa ai nomi di dominio](../../websites/website/configuration/domain_names.html).

### Aggiornare le traduzioni nei modelli e-mail¶

In Odoo, i modelli e-mail vengono tradotti automaticamente per tutti gli utenti nel database e in tutte le lingue installate. Non dovrebbe essere necessario modificare le traduzioni. Tuttavia, è possibile modificare le traduzioni se necessario.

Avvertimento

Come nel caso di qualsiasi cambiamento apportato al codice, se le modifiche non vengono effettuate correttamente (ad esempio, modifiche che provocano errori nella sintassi) il modello potrebbe smettere di funzionare e apparirà bianco.

Per modificare le traduzioni, accedi alla [modalità sviluppatore](../developer_mode.html#developer-mode). In seguito, sul modello e-mail, fai clic sul pulsante Modifica e poi sul pulsante relativo alla lingua rappresentato dalle iniziali della lingua in uso (ad es. EN per l’inglese).

Nota

Se non vi sono più lingue installate e attivate nel database o se l’utente non ha i diritti di accesso livello amministratore, il pulsante relativo alla lingua non apparirà.

Apparirà una finestra con le varie lingue installate sul database. Da qui sarà possibile modificare le traduzioni. Una volta apportate le modifiche desiderate, fai clic sul pulsante Salva per salvare le modifiche.

Nota

Durante la modifica delle traduzioni, la lingua predefinita configurata per il database appare in **grassetto**.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/general/companies/email_template.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../multi_company.html "Multi-azienda") |
  * [precedente](digest_emails.html "E-mail di riepilogo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Aziende](../companies.html) »
  * Modelli e-mail


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
  *[API]: application programming interfaces
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
  *[ISBN]: International Standard Book Number