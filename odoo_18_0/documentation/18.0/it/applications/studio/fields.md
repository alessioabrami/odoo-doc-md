# Campi e widget — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](views.html "Viste") |
  * [precedente](../studio.html "Studio") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Campi e widget



# Campi e widget¶

I campi caratterizzano la struttura dei modelli di un database. Se immagini un modello come tabella o foglio di calcolo, i campi sono le colonne i cui dati sono registrati nei record (ad es., le colonne). I campi definiscono anche il tipo di dati salvati. La modalità di presentazione dei dati e la rispettiva formattazione nell”IU viene definita dal widget.

Da un punto di vista tecnico, in Odoo esistono 15 tipi di campo. Tuttavia, puoi scegliere tra 20 campi in Studio, in quanto alcuni tipi di campo sono disponibili più di una volta con un widget predefinito diverso.

Suggerimento

I Nuovi campi possono essere aggiunti solamente alle viste [modulo](views.html#studio-views-general-form) ed [Elenco](views.html#studio-views-multiple-records-list). Per quanto riguarda le altre viste, puoi aggiungere solo Campi esistenti (campi già presenti nel modello).

## Campi semplici¶

I campi semplici contengono valori di base come testo, numeri, file, ecc.

Nota

Non-default widgets, when available, are presented as bullet points or sub-headings below.

### Testo (`char`)¶

Il campo Testo viene utilizzato per testi brevi contenenti qualsiasi carattere. Una riga di testo viene visualizzata quando viene riempito il campo.

  * Badge: visualizza il valore all’interno di una forma arrotondata, simile a un tag. Il valore non può essere modificato nell’interfaccia utente, ma è possibile impostare un valore predefinito

  * Copia negli appunti: gli utenti possono copiare il valore facendo clic su un pulsante

  * E-mail: il valore diventa un link _mailto_ cliccabile

  * Immagine: mostra un’immagine utilizzando un URL. Il valore non può essere modificato manualmente ma è possibile impostare un valore predefinito.

Nota

This works differently than selecting the Image field directly, as the image is not stored in Odoo when using a Text field with the Image widget. For example, it can be useful if you want to save disk space.

  * Telefono: il valore diventa un link _tel_ cliccabile.

Suggerimento

Spunta l’opzione Abilita SMS per aggiungere un’opzione per inviare un SMS direttamente da Odoo accanto al campo.

  * URL: il valore diventa un URL cliccabile.




Example

### Testo su più righe (`text`)¶

Il campo Testo multiriga viene utilizzato per testi più lunghi contenenti qualsiasi tipo di carattere. Due righe di testo vengono visualizzate nell’IU quando viene riempito il campo.

  * Copia negli appunti: gli utenti possono copiare il valore facendo clic su un pulsante




Example

### Intero (`integer`)¶

Il campo Intero viene utilizzato per tutti i numeri interi (positivo, negativo o zero, senza un decimale).

  * Torta percentuale: mostra il valore all’interno di un cerchio, di solito per un valore calcolato. Il valore non può essere modificato sull’IU ma è possibile impostare un valore predefinito.

  * Barra di avanzamento: mostra il valore accanto alla barra percentuale, di solito per un valore calcolato. Il campo non può essere modificato manualmente ma è possibile impostare un valore predefinito.

  * Maniglia: mostra un’icona a forma di maniglia per ordinare i record manualmente nella [vista elenco](views.html#studio-views-multiple-records-list).




Example

### Decimale (`float`)¶

Il campo Decimale viene utilizzato per tutti i numeri decimali (positivo, negativo o zero, con un decimale).

Nota

Nell’IU, i numeri decimali vengono visualizzati con due decimali dopo il punto ma vengono salvati nel database con più precisione.

  * Monetary: it is similar to using the Monetary field. It is recommended to use the latter as it offers more functionalities.

  * Percentuale: mostra il simbolo di percentuale `%` dopo il valore.

  * Torta percentuale: mostra il valore all’interno di un cerchio, di solito per un valore calcolato. Il campo non può essere modificato manualmente ma è possibile impostare un valore predefinito.

  * Barra di avanzamento: mostra il valore accanto alla barra percentuale, di solito per un valore calcolato. Il campo non può essere modificato manualmente ma è possibile impostare un valore predefinito.

  * Tempo: il valore deve rispettare il formato _hh:mm_ con un massimo di 59 minuti.




Example

### Monetario (`monetary`)¶

Il campo Monetario viene utilizzato per tutti i valori monetari.

Nota

Quando aggiungi un campo Monetario per la prima volta, ti verrà richiesto di aggiungere il campo Valuta se non esiste già nel modello. Odoo si offre di aggiungere il campo Valuta per te. Una volta aggiunto, riaggiungi il campo Monetario.

Example

### Html (`html`)¶

Il campo Html viene utilizzato per aggiungere del testo che può essere modificato utilizzando l’editor HTML di Odoo.

  * Testo multiriga: disabilita l’editor HTML di Odoo per consentire la modifica dell’HTML puro.




Example

### Data (`date`)¶

Il campo Data viene utilizzato per selezionare una data sul calendario.

  * Remaining Days: the remaining number of days before the selected date is displayed (e.g., _In 5 days_), based on the current date. This field should be set to Read only.




Example

### Data e ora (`datetime`)¶

Il campo Data e ora viene utilizzato per selezionare una data sul calendario e un orario per l’orologio. L’orario attuale dell’utente viene utilizzato automaticamente se non imposti un altro orario.

Suggerimento

As well as general properties, some specific properties are available for Date & Time fields that have the Date & Time or Date Range widget set.

#### Date Range (`daterange`)¶

The Date Range widget is used to display a period of time defined by a start date and an end date in a single line. A date range can have a mandatory start and end date, e.g., for a multi-day event, or allow an optional start or end date, e.g., for a field service intervention or a project task.

Adding a date range requires two fields: a Date & Time field with the Date Range widget set and another field that is selected as the start date _or_ end date. This underlying field can be an existing Date or Date & Time field, or one created specifically for this purpose.

To add a date range:

  1. Identify an existing Date or Date & Time field that can be used as the underlying start/end date field, or add a new one. If the date range:

     * has a mandatory start date and end date, this field can be either the start date or end date; the outcome is the same.

     * allows an optional start or end date, this field is the start date or end date, respectively.

Suggerimento

To avoid displaying the same information twice, the underlying start/end date field can be made invisible by enabling Invisible or removed from the view by clicking Remove from view.

  2. Add a Date & Time field and set the Widget field to Date Range.

  3. Enter an appropriate Label.

  4. Select the underlying start/end date field from the Start date field or End date field dropdown, as relevant.

  5. If the date range should have a mandatory start and end date, enable Always range.

  6. Update any other general properties or specific properties for Date & Time fields as needed, then click Close in the upper right corner of the screen.




Example

#### Remaining Days (`remaining_days`)¶

The Remaining Days widget displays the remaining number of days before the selected date (e.g., _In 5 days_), based on the current date and time. This field should be set to Read only.

### Casella (`boolean`)¶

Il campo Casella viene utilizzato quando un valore può essere solo vero o falso, indicato spuntando o meno la casella.

  * Pulsante: visualizza un pulsante rotondo. Il widget funziona senza dover passare alla modalità di modifica.

  * Interruttore: visualizza un pulsante a forma di interruttore. Il widget funziona senza dover passare alla modalità di modifica.




Example

### Selezione (`selection`)¶

Il campo Selezione viene utilizzato quando gli utenti devono scegliere un solo valore da un gruppo di valori predefiniti.

  * Badge: visualizza il valore all’interno di una forma arrotondata, simile a un tag. Il valore non può essere modificato nell’interfaccia utente, ma è possibile impostare un valore predefinito

  * Badge: mostra tutti i valori selezionabili contemporaneamente all’interno di forme rettangolari, organizzate orizzontalmente.

  * Priority: displays star symbols instead of values, which can be used to indicate an importance or satisfaction level, for example. This has the same effect as selecting the Priority field, although, for the latter, four priority values are already predefined.

  * Pulsante di selezione: mostra tutti i valori selezionabili allo stesso tempo come pulsanti di selezione.

Suggerimento

By default, radio buttons are organized vertically. Enable Display horizontally to switch the way they are displayed.

  * Status Bar: displays all selectable values at the same time as an arrow progress bar.

Suggerimento

By default, values on the status bar are selectable. Disable Clickable to prevent the value being edited on the UI.




Example

### Priorità (`selection`)¶

The Priority field is used to display a three-star rating system, which can be used to indicate importance or satisfaction level. This field type is a Selection field with the Priority widget selected by default and four priority values predefined. Consequently, the Badge, Badges, Radio, and Selection widgets have the same effects as described under Selection.

Suggerimento

Per modificare il numero di stelle disponibili aggiungendo o rimuovendo valori, fai clic su Modifica valori. Nota che il primo valore è pari a 0 stelle (ad es., quando non viene effettuata nessuna scelta) quindi quando si hanno quattro valori, il sistema di valutazione sarà caratterizzato da tre stelle.

Example

### File (`binary`)¶

Il campo File viene utilizzato per caricare qualsiasi tipo di file oppure per firmare un modulo (Sign widget).

  * Image: users can upload an image file, which is then displayed in [Form view](views.html#studio-views-general-form). This has the same effect as using the Image field.

  * Visualizzatore PDF: gli utenti possono caricare un file PDF che può essere consultato dalla [vista modulo](views.html#studio-views-general-form).

  * Sign: users can electronically sign the form. This has the same effect as selecting the Sign field.




Example

### Immagine (`binary`)¶

The Image field is used to upload an image and display it in [Form view](views.html#studio-views-general-form). This field type is a File field with the Image widget selected by default. Consequently, the File, PDF Viewer, and Sign widgets have the same effects as described under File.

Suggerimento

Per modificare la dimensione delle immagini caricate, scegli Piccola, Media o Grande nel campo Dimensione.

### Firma (`binary`)¶

The Sign field is used to sign the form electronically. This field type is a File field with the Sign widget selected by default. Consequently, the File, Image, and PDF Viewer widgets have the same effects as described under File.

Suggerimento

To give users the Auto option when having to draw their signature, select one of the available Auto-complete with fields (Text, Many2One, and Related Field on the model only). The signature is automatically generated using the data from the selected field.

## Campi di relazione¶

I campi di relazione sono utilizzati per collegare e visualizzare i dati dei record di un altro modello.

Nota

I widget non predefiniti, quando disponibili, vengono presentati in un elenco puntato come segue.

### Molti a uno (`many2one`)¶

Il campo Molti a uno viene utilizzato per collegare un record (di un altro modello) al record che si sta modificando. Il nome del record dell’altro modello viene poi visualizzato sul record che si sta modificando.

Example

Sul modello _Ordine di vendita_ , il campo Cliente è un campo Molti a uno che punta al modello _Contatto_. Questo permette di collegare **più** ordini di vendita a **un** solo contatto (cliente).

Suggerimento

  * Spunta l’opzione Disattiva creazione per impedire agli utenti di creare un nuovo record nel modello collegato.

  * Spunta l’opzione Disattiva apertura per impedire agli utenti di aprire record in una finestra pop-up.

  * Fai clic su Dominio per creare un filtro che aiuta gli utenti a selezionare solo il record giusto.




  * Badge: mostra il valore all’interno di una forma arrotondata, simile a un tag. Il valore non può essere modificato nell’interfaccia utente.

  * Pulsante di selezione: mostra tutti i valori selezionabili allo stesso tempo come pulsanti di selezione.




### Uno a molti (`one2many`)¶

Il campo Uno a molti viene utilizzato per mostrare le relazioni esistenti tra un record del modello attuale e altri record di un altro modello.

Example

È possibile aggiungere un campo Uno a molti al modello _Contatto_ per visualizzare **molti** ordini di vendita di **un solo** cliente.

Nota

To use a One2Many field, the two models must have been linked already using a Many2One field. One2Many relations do not exist independently: a reverse-search of existing Many2One relations is performed.

### Righe (`one2many`)¶

Il campo Righe viene utilizzato per creare una tabella con righe e colonne (ad es., le righe dei prodotti di un ordine di vendita).

Suggerimento

Per modificare le colonne, fai clic sul campo Righe e poi su Modifica vista elenco. Per modificare il modulo che appare quando un utente fa clic su Aggiungi riga, fai clic su Modifica vista modulo.

Example

### Molti a molti (`many2many`)¶

The Many2Many field is used to link multiple records from another model to multiple records on the current model. Many2Many fields can use Disable creation, Disable opening, Domain, just like Many2One fields.

Example

Nel modello _Lavoro_ , il campo Assegnatari è un campo Molti a molti che punta al modello _Contatto_. Questo permette a un singolo utente di essere assegnato a **più** lavori e **più** utenti possono essere assegnati a un solo lavoro.

  * Caselle di controllo: gli utenti possono selezionare vari valori utilizzando le caselle di controllo.

  * Tags: users can select several values appearing in rounded shapes, also known as _tags_. This has the same effect as selecting the Tags field.




### Tag (`many2many`)¶

The Tags field is used to display several values from another model appearing in rounded shapes, also known as _tags_. This field type is a Many2Many field with the Tags widget selected by default. Consequently, the Checkboxes and Many2Many widgets have the same effects as described under Many2Many.

Suggerimento

Per mostrare tag con vari colori di sfondo è necessario spuntare l’opzione Usa colori.

Example

### Campo correlato (`related`)¶

Un Campo correlato non è un campo di relazione a sé. Non viene stabilita nessuna relazione tra i modelli ma viene utilizzata una relazione esistente per recuperare e mostrare le informazioni da un altro record.

Example

Per mostrare l’indirizzo e-mail di un cliente sul modello _Ordine di vendita_ , usa il Campo correlato `partner_id.email` selezionando Cliente e poi E-mail.

## Proprietà¶

### General properties¶

  * Invisible: Enable this property when it is not necessary for users to view a field on the UI. This helps declutter the UI by only showing the essential fields depending on a specific situation.

The Invisible attribute also applies inside Studio. To view hidden fields in Studio, click on a view’s View tab and enable Show Invisible Elements.

  * Required: Enable this property if a field should always be completed by the user before being able to proceed.

  * Readonly: Enable this property if users should not be able to modify a field.




Nota

> You can choose to enable Invisible, Required and Readonly for specific records only by clicking on Conditional and creating a filter.

Example

Nella vista _Modulo_ del modello _Contatto_ , il campo Titolo appare solo quando selezioni Individuale in quanto quel campo non sarà utile per un contatto Azienda.

  * Label: the field’s name on the UI. This is not the name used in the PostgreSQL database. To view and change the latter, activate the [developer mode](../general/developer_mode.html#developer-mode) and edit the Technical Name.

  * Help Tooltip: To explain the purpose of a field, add a description. The text is displayed inside a tooltip box when hovering with your mouse over the question mark beside the field’s label.

  * Widget: per modificare l’aspetto predefinito o la funzionalità di un campo, seleziona uno o più widget disponibili.

  * Placeholder: To provide an example of how a field should be completed, add placeholder text. The text appears in light gray until a value is entered.

  * Default value: To display a default value in a field when a record is created, add a value.

  * Allow visibility to groups: To limit which users can view the field, select one or more user access [groups](../general/users/access_rights.html#access-rights-groups).

  * Forbid visibility to groups: To prevent certain users from seeing the field, select one or more user access [groups](../general/users/access_rights.html#access-rights-groups).




### Properties for Date & Time fields¶

For Date & Time fields that have the Date & Time or Date Range widget set, some specific properties are available:

  * Minimal precision: Determine the smallest date unit that must be selected in the date selector. The possible values are Day, Month, Year or Decade. If no value is selected, the user must select a day in the date selector.

  * Maximal precision: Determine the largest date unit that can be used to navigate the date selector. The possible values are Day, Month, Year or Decade. If no value is selected, the user can navigate the date selector by decade.

  * Warning for future dates: Enable this property to display a warning icon if a future date is selected.

  * Condensed display: Enable this property to show days, months and hours with no leading zeros, e.g., `4/2/2025 8:05:00` instead of `04/02/2025 08:05:00`.

  * Show time: This property is enabled by default for Date & Time fields. On a read-only field, disable the property to show only the date. This can keep a list view less cluttered, for example.

  * Show seconds: This property is enabled by default for Date & Time fields. Disable the property to show only hours and minutes.

  * Time interval: Enter a value to determine the minute intervals shown in the time selector. For example, enter 15 to allow quarter-hour intervals. The default value is set to 5 minutes.

  * Earliest accepted date: Enter the earliest date that can be selected in the date selector in ISO-format, i.e., `YYYY-MM-DD`. If the current date is always the earliest accepted date, enter `today`. On the date selector, dates prior to the earliest accepted date are grayed out.

  * Latest accepted date: Enter the latest date that can be selected in the date selector in ISO-format, i.e., `YYYY-MM-DD`. If the current date is always the latest accepted date, enter `today`. On the date selector, dates later than the latest accepted date are grayed out.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/studio/fields.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](views.html "Viste") |
  * [precedente](../studio.html "Studio") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Campi e widget


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