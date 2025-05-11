# Diritti di accesso — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](portal.html "Accedere al portale") |
  * [precedente](2fa.html "Autenticazione a due fattori") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Diritti di accesso



# Diritti di accesso¶

I _diritti di accesso_ sono autorizzazioni che determinano i contenuti e le applicazioni a cui gli utenti possono accedere e modificare. In Odoo, questi permessi possono essere impostati per singoli utenti o per gruppi di utenti. Limitando i permessi solo a chi ne ha bisogno, si garantisce che gli utenti non modifichino o cancellino qualcosa a cui non dovrebbero avere accesso.

**Solo** un _amministratore_ può modificare i diritti di accesso.

Pericolo

Le modifiche ai diritti di accesso possono avere un impatto negativo sul database. Questo include _admin impotente_ , il che significa che nessun utente del database può apportare modifiche ai diritti di accesso. Per questo motivo, Odoo ti consiglia di contattare un Business Analyst o il nostro team di assistenza prima di apportare modifiche.

Suggerimento

Per poter apportare modifiche alle impostazioni dei diritti di accesso di un altro utente, un utente **deve** avere i diritti di accesso di _Amministrazione_ specifici impostati sul proprio profilo.

Per accedere all’impostazione, apri l’app Impostazioni ‣ Gestisci utenti ‣ seleziona un utente ‣ scheda Diritti di accesso ‣ sezione Amministrazione ‣ campo Amministrazione.

Una volta aperta l’impostazione, un amministratore già esistente **deve** modificare l’impostazione nel campo Amministrazione in Diritti di accesso.

Una volta completata l’operazione, fai clic su Salva per salvare le modifiche e rendi l’utente amministratore.

## Utenti¶

I diritti di accesso per gli [utenti individuali](../users.html#users-add-individual) vengono impostati quando l’utente viene aggiunto al database ma possono essere sistemati in qualsiasi momento dal profilo dell’utente.

Per modificare i diritti di un utente, fai clic sull’utente desiderato per modificarne il profilo.

Sulla pagina del profilo dell’utente, nella scheda Diritti di accesso, scorri in basso per visualizzare i permessi attuali.

Per ogni applicazione, utilizza il menu a discesa per selezionare il livello di autorizzazione che l’utente deve avere. Le opzioni variano per ogni sezione, ma le più comuni sono: Vuoto/Nessuno, Utente: i propri documenti, Utente: tutti i documenti o Amministratore.

Il campo Amministrazione nella scheda Diritti di accesso ha le seguenti opzioni: Impostazioni o Diritti di accesso.

## Creare e modificare gruppi¶

*I gruppi sono insiemi di autorizzazioni specifiche per le applicazioni che vengono utilizzate per gestire i diritti di accesso comuni per un gran numero di utenti. Gli amministratori possono modificare i gruppi esistenti in Odoo o crearne di nuovi per definire regole per i modelli all’interno di un’applicazione.

Per accedere ai gruppi, attiva la [modalità sviluppatore](../developer_mode.html#developer-mode) e poi apri l’app Impostazioni ‣ Utenti e aziende ‣ Gruppi.

Per creare un nuovo gruppo dalla pagina Gruppi, fai clic su Crea. Successivamente, dal modulo del gruppo vuoto, seleziona una Applicazione e completa il modulo del gruppo (descritto di seguito).

Per modificare i gruppi esistenti, fai clic su un gruppo esistente nell’elenco visualizzato nella pagina Gruppi e modifica il contenuto del modulo.

Inserisci un Nome per il gruppo e spunta la casella accanto a Condividi gruppo, se il gruppo è stato creato per condividere dati con altri utenti.

Importante

Verifica sempre le impostazioni modificate per assicurarti che vengano applicate agli utenti corretti.

The group form contains multiple tabs for managing all elements of the group. In each tab, click Add a line to add a new row for users or rules, and click the __(cancel) icon to remove a row.

  * Scheda Utenti: elenca gli utenti nel gruppo. Gli utenti elencati in nero hanno diritti amministrativi. Gli utenti privi di questo tipo di accesso appaiono in blu. Fai clic su Aggiungi riga per aggiungere utenti a questo gruppo.

  * Scheda Ereditati: significa che gli utenti aggiunti a questo gruppo vengono aggiunti automaticamente ai gruppi elencati in questa scheda. Fai clic su Aggiungi riga per aggiungere gruppi ereditati.

Example

Ad esempio, se nel gruppo _Vendite/Amministratore_ viene elencato il gruppo _Sito web/Editor limitato_ nella rispettiva scheda Ereditati, qualsiasi utente aggiunto al gruppo _Vendite/Amministratore_ riceverà automaticamente l’accesso anche al gruppo _Sito web/Editor limitato_.

  * Scheda Menu: indica a quali modelli può avere accesso il gruppo. Fai clic su Aggiungi riga per aggiungere un menu specifico.

  * Scheda Viste: elenca a quali viste ha accesso il gruppo. Fai clic su Aggiungi riga per aggiungere una vista al gruppo.

  * Scheda Diritti di accesso: elenca il primo livello di diritti (modelli) che il gruppo possiede. La colonna Nome rappresenta il nome per l’accesso del gruppo corrente al modello selezionato nella colonna Modello.

To link a new access right to a group, click Add a line. Select the appropriate model from the Model drop-down, then enter a name for the access right in the Name column. For each model, enable the following options as appropriate:

    * Lettura: gli utenti possono vedere i valori esistenti dell’oggetto

    * Scrittura: gli utenti possono modificare i valori esistenti dell’oggetto

    * Creazione: gli utenti possono creare nuovi valori per l’oggetto

    * Eliminazione: gli utenti possono eliminare valori.

Suggerimento

While there are no conventions for naming access rights, it is advisable to choose a name that identifies its purpose.

Ad esempio, il tipo di accesso che i manager del reparto acquisti hanno per il modello Contatto potrebbe essere nominato `res.partner.purchase.manager`. Si tratta del nome tecnico del modello seguito da un nome che identifica il gruppo di utenti in questione.

Per trovare il nome tecnico del modello dalla vista attuale, inserisci un testo segnaposto nel campo Nome e poi fai clic sul nome del Modello e successivamente sull’icona __(collegamento interno).

  * Regole record: elenca il secondo livello di diritti di modifica e visibilità. Le Regole record sostituiscono or perfezionano i diritti di accesso del gruppo. Fai clic su Aggiungi riga per aggiungere una regola record al gruppo. Per ogni regola, scegli i valori delle seguenti opzioni:

    * Applica per lettura.

    * Applica per scrittura.

    * Applica per creazione.

    * Applica per eliminazione.

Importante

Le regole record sono scritte utilizzando un _dominio_ oppure condizioni che filtrano i dati. Un’espressione di dominio è un elenco di condizioni simili. Ad esempio:

`[('mrp_production_ids', 'in', user.partner_id.commercial_partner_id.production_ids.ids)]`

Questa regola record serve ad abilitare gli avvisi di consumo MRP per i subappaltatori.

Odoo dispone di una libreria di regole di record preconfigurate per facilitare l’uso. Gli utenti che non conoscono i domini (e le espressioni di dominio) dovrebbero consultare un Business Analyst di Odoo o il team di supporto di Odoo prima di apportare modifiche.




## Modalità superutente¶

_Superuser mode_ allows the user to bypass record rules and access rights. To activate _Superuser mode_ , first, activate [developer mode](../developer_mode.html#developer-mode). Then, navigate to the _debug_ menu, represented by a __(debug) icon, located in the top banner.

Infine, nella parte inferiore del menu, fai clic su Diventa superutente.

Importante

Solo gli utenti con accesso alle _Impostazioni_ della sezione _Amministrazione_ dei _Diritti di accesso_ (nel proprio profilo utente) possono accedere alla _modalità superutente_.

Pericolo

La _modalità superutente_ consente di eludere le regole record e i diritti di accesso e pertanto deve essere utilizzata con estrema cautela.

Una volta usciti dalla _modalità superutente_ , gli utenti potrebbero essere bloccati dal database a causa delle modifiche apportate. Questo può causare un _amministratore impotente_ , ovvero un amministratore senza la possibilità di modificare i diritti/impostazioni di accesso.

In questo caso, contatta il supporto Odoo qui: [nuovo ticket di supporto](https://www.odoo.com/help). Il team di supporto è in grado di recuperare l’accesso usando un accesso di supporto.

Per uscire dalla _modalità superutente_ , esci dall’account andando sull’angolo in alto a destra e facendo clic sul nome utente OdooBot. In seguito, seleziona l’opzione Esci.

Suggerimento

Una maniera alternativa per attivare la _modalità superutente_ è accedere come superutente. Per farlo, vai alla schermata di accesso e inserisci l’indirizzo e-mail e la Password appropriati.

Invece di fare clic su Accedi, fai clic su Accedi come superutente.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/general/users/access_rights.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](portal.html "Accedere al portale") |
  * [precedente](2fa.html "Autenticazione a due fattori") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Utenti](../users.html) »
  * Diritti di accesso


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
  *[ISBN]: International Standard Book Number