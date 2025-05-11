# Attività — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reporting.html "Rendiconto") |
  * [precedente](../essentials.html "Concetti fondamentali") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Attività



# Attività¶

Le _attività_ rappresentano operazioni di follow-up legate ad un record in un database Odoo.

L’icona utilizza per visualizzare le attività varia a seconda del tipo di attività:

  * __icona(orologio): icona predefinita per le attività.

  * __icona(telefono): chiamata programmata.

  * __icona(busta): e-mail programmata.

  * __icona(verifica): attività «to-do» programmata.

  * __icona(gente) icon: riunione programmata.

  * __icona(caricamento): caricamento documento programmato.

  * __icona :guilabel: `(richiesta di firma): richiesta di firma pianificata.




## Pianifica attività¶

Le attività possono essere programmate su qualsiasi pagina del database che contiene storico del chatter, vista Kanban, vista elenco oppure vista attività di un’applicazione.

### Chatter¶

Le attività possono essere create dal chatter di qualsiasi record.

Per programmare una nuova attività, fai clic sul pulsante Attività, posizionato nella parte alta del chatter. Nella finestra a comparsa Programmazione attività, :ref:` riempi il modulo corrispondente <activities/form>`.

### Vista kanban¶

Le attività possono essere create anche dalla vista __(Kanban).

Per farlo, fai clic sull” __(clock) icon situato nella parte alta di un record.

Fai clic su \+ Pianifica attività per poi completare il modulo corrispondente.

Nota

Se per un record esiste già un’attività pianificata, l” __(clock) icon viene sostituito dall’icona che rappresenta l’attività programmata esistente. Fai clic sull’icona relativa al tipo di attività per programmarne un’altra.

### Vista elenco¶

Le attività possono anche essere create dalla vista __(elenco).

Se la colonna Attività è nascosta, puoi renderla visibile utilizzando l’icona __(regolazione impostazioni) nella parte destra della fila in alto.

in seguito, fai clic sull” __(clock) icon per il record al quale è stata aggiunta un’attività per poi cliccare su \+ Pianifica attività. Prosegui con la compilazione del modulo corrispondente che appare.

Nota

Se per un record esiste già un’attività pianificata, l” __(clock) icon viene sostituito dall’icona che rappresenta l’attività programmata esistente. Fai clic sull’icona relativa al tipo di attività per programmarne un’altra.

### Vista attività¶

La maggior parte delle applicazioni in Odoo presentano una vista _Attività_ disponibile. Se disponibil, l” __(clock) icon è visibile nell’angolo in alto a destra della barra del menu principale, tra le altre icone relative alle viste.

Per aprire la vista dell’attività, fai clic sull” __(clock) icon.

In questa vista, sono elencate tutte le attività disponibili in colonne mentre le voci in orizzontale rappresentano i singoli record.

Le attività in verde presentano una data di scadenza futura mentre le attività in arancione scadono nella data odierna. Infine, le attività in rosso sono in ritardo.

In ogni colonna, le barre colorate rappresentano record per un tipo di attività specifico e mostrano un numero che indica quante attività sono programmate per quel tipo specifico.

Se per un record sono programmati vari tipi di attività, nella casella apparirà un numero che indica il numero totale di attività programmate.

Nota

I colori delle attività, e il collegamento alla data di scadenza, sono sempre gli stessi all’interno di Odoo, indipendentemente dal tipo di attività o dalla vista selezionata.

Per programmare un’attività per un record, passa con il mouse sul campo corrispondente. Fai clic sull’icona __(più) e poi completa il modulo corrispondente.

### Modulo pianificazione attività¶

Le attività possono essere programmate in vari modi, ad esempio dal chatter fi un record oppure da una delle varie viste di un’applicazione, se disponibili: :ref:` vista Kanban <activities/kanban>`, vista elenco o vista attività.

Inserisci le seguenti informazioni nel modulo:

  * Tipo di attività: seleziona il tipo di attività dal menu a discesa. Le opzioni predefinite sono: E-mail, Chiamata, Riunione oppure To-Do. IN base alle applicazioni installate potrebbero essere disponibili altre opzioni.

  * Riepilogo: inserisci un titolo breve per l’attività, come `Discussione proposta`.

  * Scadenza: seleziona la data di scadenza dell’attività utilizzando il popover del calendario.

  * Assegnato a: per impostazione predefinita, l’utente corrente popola il campo. Per assegnare l’attività ad un utente diverso, selezionalo dal menu a discesa.

  * Note: aggiungi qualsiasi informazione aggiuntiva relativa all’attività.




Quando la finestra pop-up Programma attività è completa, fai clic su uno dei seguenti pulsanti:

  * Apri calendario: apre il calendario dell’utente per aggiungere e pianificare l’attività.

Fai clic sulla data e l’orario desiderati per l’attività per far apparire la finestra a comparsa Nuovo evento. Il riepilogo inserito nella finestra _Pianifica attività_ popolerà il campo Titolo.

Inserisci le informazioni nella finestra Nuovo evento e poi fai clic su Salva e chiudi per programmarla. Una volta pianificata, l’attività viene aggiunta al chatter nella sezione Attività pianificate.

Importante

Il pulsante Apri calendario appare **solo** se il Tipo di attività configurato è una Chiamata o una Riunione.

  * Pianifica: pianifica l’attività aggiungendola al chatter nella sezione Attività pianificate.

  * Pianifica e segna come completata: aggiunge i dettagli dell’attività al chatter nella sezione Oggi. L’attività non viene programmata ma viene contrassegnata automaticamente come completata.

  * Completata - Pianifica la prossima: aggiunge i dettagli dell’attività al chatter corrispondente a Oggi. L’attività non viene programmata ma viene contrassegnata automaticamente come completata e apparirà una nuova finestra a comparsa Pianifica attività.

  * Annulla: elimina tutte le modifiche apportate alla finestra pop-up Pianifica attività.




## Tutte le attività pianificate¶

Per visualizzare un elenco consolidato di attività, organizzate per applicazione, fai clic sull” __(clock) icon nel menu di intestazione, situato nell’angolo in alto a destra.

Se sono presenti attività programmate, il numero di attività appare in una bolla rossa sull” __(clock) icon.

Per ogni applicazione, tutte le attività sono ulteriormente divise in sottosezioni che indicano in quale sezione dell’applicazione deve essere completata l’attività. Ogni sottosezione elenca il numero di attività programmate che sono In ritardo, da fare Oggi e programmate nel Futuro.

Example

Nell’applicazione _Ferie_ , un’attività viene programmata per essere svolta nella dashboard con tutte le richieste relative a _Tutte le ferie_ e sei attività sono programmate per essere svolte nella dashboard _Assegnazioni_.

Queste richieste appaiono in due elenchi separati nel menu a discesa con tutte le attività: uno dal nome `Ferie` e l’altro dal titolo `Assegnazione ferie`.

### Richiedere un documento¶

L’opzione Richiedi documento è disponibile in fondo all’elenco di tutte le attività programmate. Fai clic su Richiedi documento e vedrai apparire la finestra Richiedere un file.

Inserisci le seguenti informazioni nel modulo:

  * Nome documento: inserisci un nome per il documento richiesto.

  * Richiesta per: seleziona l’utente che ha richiesto il documento dal menu a discesa.

  * Data di scadenza tra: inserisci un valore numerico che indica per quando è dovuto il documento. Accanto al campo, sarà visibile il campo Giorni. Fai clic su Giorni, l’opzione predefinita, per far apparire il menu a discesa. Seleziona l’opzione temporale desiderata dall’elenco. Le opzioni sono: Giorni, Settimane, o Mesi.

  * Spazio di lavoro: seleziona lo [Spazio di lavoro](../productivity/documents.html#documents-workspaces) specifico nel quale stai caricando il documento.

  * Tag: seleziona i tag desiderati dal menu a discesa. I tag disponibili visualizzati si basano sui tag configurati per lo Spazio di lavoro selezionato.

  * Messaggio: inserisci un messaggio per chiarire la richiesta del documento nel campo.




Una volta che tutti i campi sono stati completati, fai clic su Richiedi per inviare la richiesta del documento.

## Tipi di attività¶

Per visualizzare i tipi di attività configurati in un database, vai su Impostazioni ‣ sezione Comunicazioni ‣ impostazioni Attività ‣ Tipi di attività.

In questo modo avrai accesso alla pagina Tipi di attività dove sono elencati i tipi di attività esistenti.

Suggerimento

Le singole applicazioni presentano un elenco di _Tipi di attività_ specifici. Ad esempio, per visualizzare e modificare le attività disponibili per l’applicazione _CRM_ vai sull’app CRM ‣ Configurazione ‣ Tipi di attività.

### Modificare i tipi di attività¶

Per modificare un tipo di attività esistente, fai clic sul tipo di attività per visualizzare il modulo relativo al tipo di attività.

Effettua tutte le modifiche desiderate nel modulo relativo al tipo di attività. Il modulo viene salvato automaticamente ma può essere salvato manualmente in qualsiasi momento facendo clic sull’opzione Salva manualmente rappresentato dall’icona __(nuvola caricamento) situata nell’angolo in alto a sinistra della pagina.

### Creare nuovi tipi di attività¶

Per creare un nuovo tipo di attività, fai clic su Nuovo nella pagina relativa ai Tipi di attività e spunterà un nuovo modulo.

Inserisci un Nome per il tipo di attività nella parte alta del modulo per poi aggiungere le altre informazioni.

#### Sezione impostazioni attività¶

  * Azione: seleziona un’azione associata al nuovo tipo di attività usando il menu a discesa. Alcune azioni attivano comportamenti specifici dopo la programmazione di un’attività come:

    * Carica documento: se selezionata, all’attività pianificata viene aggiunto automaticamente un link per caricare un documento nel chatter.

    * Chiamata o Riunione: se selezionata, gli utenti hanno l’opzione di aprire il calendario per selezionare data e orario dell’attività.

    * Richiesta firma: se selezionata, all’attività pianificata viene aggiunto un link per aprire una finestra a comparsa relativa alla richiesta di firma nel chatter. Per farlo, è necessario installare l’applicazione _Firma_.

Nota

Tipi di attività disponibili in base alle applicazioni installate nel database.

  * Cartella: seleziona una cartella [spazio di lavoro](../productivity/documents.html#documents-workspaces) specifica in cui salvare un documento. Il campo appare **solo** se selezioni Carica documento come Azione.

Dal menu a discesa, seleziona la Cartella in cui è salvato il documento.

  * Utente predefinito: seleziona un utente dal menu a discesa per assegnare automaticamente l’attività all’utente selezionato quando il tipo di attività viene programmato. Se il campo è vuoto, l’attività viene assegnata all’utente che crea l’attività.

  * Riepilogo predefinito: inserisci una nota per indicare quando il tipo di attività viene creato.

Nota

Le informazioni presenti nei campi Utente predefinito e Riepilogo predefinito vengono incluse al momento della creazione di un’attività. Tuttavia, possono essere modificate prima che l’attività venga programmata o salvata.

  * Conserva le attività svolte: spunta la casella per mantenere le attività che sono state contrassegnate come `Svolte` visibili nella vista attività.

  * Nota predefinita: inserisci qualsiasi nota da far apparire con l’attività.




#### Sezione prossima attività¶

È possibile avere un’altra attività tra le suggerite o da attivare. Per farlo, configura la sezione Prossima attività.

  * Tipo concatenamento: seleziona Suggerisci la prossima attività o Attiva attività successiva dal menu a discesa. A seconda dell’opzione selezionata sarà visualizzato il campo Suggerimento oppure Attivazione.

Nota

Il campo Tipo di concatenamento **non** appare se selezioni Carica documento come Azione.

  * Suggerimento/Attivazione: in base a cosa hai selezionato per Tipo di concatenamento, il campo mostra Suggerimento o Attivazione. Utilizzando il menu a discesa, seleziona l’attività da consigliare o programmare come attività di follow-up al tipo di attività.

  * Pianifica: stabilisci quando suggerire o attivare la prossima attività.

Per prima cosa, inserisci un valore numerico che indica quando l’attività viene suggerita o attivata.

Accanto al campo, sarà visibile il campo Giorni. Fai clic su Giorni, l’opzione predefinita, per far apparire il menu a discesa. Seleziona l’opzione temporale desiderata dall’elenco. Le opzioni sono: Giorni, Settimane, o Mesi.

Infine, dal menu a discesa, seleziona se l’attività è programmata o attivata dopo la scadenza dell’attività precedente o dopo la data di completamento.




Vedi anche

  * [Comunicazioni](../productivity/discuss.html)

  * [Utilizzare i canali per comunicare con il team](../productivity/discuss/team_communication.html)

  * [Utilizzare attività per i team di vendita](../sales/crm/optimize/utilize_activities.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/essentials/activities.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reporting.html "Rendiconto") |
  * [precedente](../essentials.html "Concetti fondamentali") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Attività


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