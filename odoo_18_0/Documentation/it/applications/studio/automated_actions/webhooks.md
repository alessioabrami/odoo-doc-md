# Webhook — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../pdf_reports.html "Reportistica in PDF") |
  * [precedente](../automated_actions.html "Regole di automazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Studio](../../studio.html) »
  * [Regole di automazione](../automated_actions.html) »
  * Webhook



# Webhook¶

Avvertimento

È _altamente consigliato_ consultare uno sviluppatore, un architetto di soluzioni o un altro ruolo tecnico quando si decide di utilizzare i webhook nonché durante l’intero processo di implementazione. Se non configurati correttamente, i webhook possono disturbare il database di Odoo e possono richiedere tempo per essere ripristinati.

I webhook, che possono essere creati in **Studio** , sono regole di automazione attivate da eventi esterni tramite callback HTTP definiti dall’utente. Quando un sistema esterno invia dati a un URL di Odoo webhook (il “trigger”) con un file di dati (il “payload”), Odoo risponde con un’azione predefinita nel database.

A differenza delle azioni programmate o delle chiamate API manuali, i webhook consentono la comunicazione e l’automazione in tempo reale. Ad esempio, se un ordine di vendita viene confermato in un sistema POS esterno, un webhook può aggiornare istantaneamente il magazzino di Odoo, garantendo la sincronizzazione del sistema.

Nota

Questa sezione spiega come creare un webhook che _prende_ i dati da una fonte esterna. Tuttavia, è possibile creare anche un’azione automatizzata che [invia una chiamata API a un webhook esterno](../automated_actions.html#studio-automated-actions-action-webhook).

## Creare un webhook in Studio¶

I webhook possono essere configurati in **Studio** e la configurazione è divisa tra il trigger e le azioni.

Suggerimento

  * La configurazione di un webhook in Odoo non richiede coding al momento della connessione ai database Odoo ma il test richiede uno strumento esterno come [Postman](https://www.postman.com/). Record o azioni di destinazione personalizzati possono richiedere competenze di programmazione.

  * [Attiva la modalità sviluppatore](../../general/developer_mode.html#developer-mode) per modificare il modello di destinazione del webhook (ad es. ordini di vendita o informazioni di contatto) e per trovare il nome tecnico del modello (che potrebbe richiedere una configurazione accurata del payload).




### Configurare il trigger del webhook¶

Per creare un webhook con **Studio** , [apri Studio](../../studio.html#studio-access), fai clic su Webhook e poi su Nuovo. Da qui, dai un nome al webhook, modificane il modello (il tipo di voce del database di destinazione) se necessario e di stabilire se le chiamate effettuate all’URL del webhook debbano essere registrate (in modo da tracciare la cronologia delle chiamate del webhook per la risoluzione dei problemi).

L’URL del webhook viene generato automaticamente. Questo è l’URL da utilizzare per testare il webhook e collegarlo al sistema esterno che invierà gli aggiornamenti al database.

Pericolo

L’URL del webhook è **confidenziale** e deve essere trattato con cura. Condividerlo online o senza precauzioni può fornire un accesso indesiderato al database di Odoo. Fai clic su Ruota secret per modificare l’URL, se necessario.

Infine, se il sistema che invia il webhook non è Odoo, sistema le azioni del Record di destinazione per cercare il record JSON incluso nel payload della chiamata API quando la chiamata viene effettuata all’URL del webhook. Se il sistema che invia il webhook è un database Odoo, assicurati che `id` e `model` appaiano nel payload.

Suggerimento

Sebbene il Modello venga configurato in Odoo, è il nome tecnico del modello che deve essere incluso nel payload. Passa con il mouse sul nome del modello, fai clic sull’icona __(link interno) per trovare il nome tecnico nel campo Modello. Ad esempio, il webhook di un ordine di vendita usa il modello _Ordine di vendita_ ma il nome tecnico `sale.order` viene utilizzato nel payload.

Nota

Al momento della creazione di un record nel database Odoo, il formato predefinito del record target non dovrebbe essere utilizzato, usa invece `model.browse(i)` o `model.search(i)`.

### Configurare l’azione di un webhook¶

Per configurare un’azione webhook durante la configurazione di un webhook, fai clic su Aggiungi un’azione nella scheda Azioni da eseguire. Fai clic sul Tipo di azione e configura i campi.

### Testare il webhook¶

Nota

Per testare il webhook è necessario configurarlo, avere a disposizione un payload di prova da inviare al webhook e uno strumento o sistema esterno per inviare il payload tramite richiesta API `POST`. Puoi utilizzare uno strumento del tipo [Postman](https://www.postman.com/) che richiede meno competenze tecniche.

Se durante il test appare un messaggio che recita `200 OK` oppure `status: ok` significa che il webhook funziona lato Odoo. Da qui, puoi iniziare l’implementazione con altri strumenti per inviare automaticamente le chiamate webhook a Odoo utilizzando l’URL del webhook.

Se vengono restituite altre risposte, il numero inviato nella risposta aiuta a identificare il problema. Ad esempio, un `500 Internal Server Error` significa che Odoo non è riuscito a interpretare correttamente la chiamata. Se viene restituito, assicurati che i campi trovati nel file JSON siano mappati correttamente nella configurazione del webhook e nel sistema che invia la chiamata di prova. L’attivazione della registrazione delle chiamate nella configurazione del webhook fornisce un registro degli errori se il webhook non funziona come previsto.

### Implementare il webhook¶

Una volta che il webhook è completamente configurato, collegalo al sistema che invia i dati al database di Odoo attraverso questo webhook. Assicurati che le chiamate API siano inviate all’URL del webhook quando si configura il sistema.

## Casi d’uso webhook¶

Di seguito sono riportati due esempi di utilizzo dei webhook in Odoo. Questi webhook richiedono strumenti esterni (che sono elencati nell’esempio).

Avvertimento

Consulta uno sviluppatore, un architetto di soluzioni o un altro ruolo tecnico se decidi di implementare i webhook. Se non vengono configurati correttamente, i webhook possono disturbare il database di Odoo e possono richiedere tempo per essere ripristinati.

### Aggiornare la valuta di un ordine di vendita¶

Il presente webhook permette di aggiornare la valuta di un ordine di vendita nell’applicazione **Vendite** in USD. È utile per le filiali al di fuori degli Stati Uniti con una società madre situata negli Stati Uniti o durante le fusioni quando si consolidano i dati in un unico database Odoo.

#### Configurare il trigger del webhook¶

Per configurare il webhook, apri l’app **Vendite**. In seguito, configura il trigger e il Modello viene impostato su `Ordine di vendita`. Successivamente, imposta il Record target su `model.env[payload.get('model')].browse(int(payload.get('id')))`. La ripartizione è la seguente:

  * **model** : ciò che viene aggiornato in Odoo (in questo caso, gli ordini di vendita). Questo corrisponde al Modello configurato precedentemente.

  * **env** : dove ha luogo l’azione. In questo caso, si tratta di Odoo.

  * **payload** : ciò che viene inviato all’URL del webhook. Questo contiene le informazioni che aggiornano l’ordine di vendita.

  * **get(“model”)** : dice al webhook quale record del database guardare. In questo caso, il webhook recupera (`get`) i dati legati a un `model` specifico. In questo esempio, si tratta del modello Ordine di vendita.

  * **browse** : dice al webhook di controllare il `model` (Ordine di vendita) configurato dal payload per l’aggiornamento.

  * **int** : trasforma il target in un ``integer` (un numero intero). Questo è importante nel caso in cui alcune parole (una `stringa`) o un numero decimale siano inclusi nel record di destinazione del payload.

  * **get(“id”)** : identifica il numero dell’ordine di vendita che viene aggiornato in Odoo.




#### Configurare l’azione di un webhook¶

Dopo aver configurato il trigger, configura l’azione del webhook facendo clic su Aggiungi azione. Per scegliere il Tipo, fai clic su Aggiorna record. Successivamente, seleziona `Aggiorna`, scegli il campo `Valuta` e seleziona `USD` per aggiornare il campo. Infine, fai clic su Salva e chiudi.

#### Riassunto configurazione webhook¶

Per riassumere ciò che è stato configurato, il webhook si rivolge agli ordini di vendita, identificati dal loro numero di ordine di vendita, e aggiorna la loro valuta in `USD` quando viene inviata una richiesta POST all’URL del webhook che include il numero dell’ordine di vendita (che è identificato dal record `id` del payload).

#### Testare il webhook¶

Testa la configurazione del webhook per assicurarti che tutto sia corretto. Per inviare il trigger simulato, il processo utilizza uno strumento chiamato [Postman](https://www.postman.com/).

Questa sezione illustra i passaggi per testare il webhook in Postman, ma non offre assistenza in caso di problemi con lo strumento. Per ottenere assistenza specifica con Postman, contatta il loro team di supporto.

Una volta aperto Postman, crea una nuova richiesta HTTP e imposta il metodo su POST. Successivamente, copia l’URL del webhook da testare e incollalo nel campo URL di Postman. In seguito, fai clic sulla scheda Body e seleziona l’opzione raw. Imposta il tipo di file su JSON, quindi copia questo codice e incollalo nel file.
    
    
    {
        "model": "sale.order",
        "id": "SALES ORDER NUMBER"
    }
    

Da qui, scegli un ordine di vendita su cui testare il webhook. Se non è possibile eseguire il test in un database Odoo attivo, puoi creare un database demo con un ordine di vendita campione e il webhook configurato. Sostituisci `SALES ORDER NUMBER` con il numero dell’ordine di vendita senza la `S` o gli zeri prima del numero. Ad esempio, un ordine di vendita con il numero `S00007` deve essere inserito come `7` in Postman. Infine, fai clic su Invia in Postman.

Se viene restituito un messaggio che dice `200 OK` o `status: ok`, allora il webhook funziona correttamente dal lato di Odoo. La valuta dell’ordine di vendita di prova viene aggiornata. Da qui, si può iniziare l’implementazione con l’altro strumento per inviare automaticamente le chiamate webhook a Odoo utilizzando l’URL del webhook.

Se vengono restituite altre risposte, il numero a esse associato aiuta a identificare il problema. Ad esempio, un `500 Internal Server Error` significa che Odoo non è riuscito a interpretare correttamente la chiamata. Se questo viene restituito, assicurati che i campi `model` e `id` siano mappati correttamente nella configurazione del webhook e in Postman.

### Creare un nuovo contatto¶

Questo webhook utilizza un codice personalizzato per creare un nuovo contatto in un database Odoo. Potrebbe essere utile per creare automaticamente nuovi fornitori o clienti.

#### Configurare il trigger del webhook¶

Per configurare questo webhook, apri l’app **Contatti**. In seguito, configura il trigger e imposta il Modello su `Contatto`. Inoltre, imposta il Record target su `model.browse([2])`. La suddivisione è la seguente:

  * **model** : ciò che viene aggiornato in Odoo (in questo caso, contatto). Questo corrisponde al Modello configurato precedentemente.

  * **browse** : dice al webhook di controllare il `model` (i contatti) configurato dal payload per la creazione.




#### Configurare l’azione di un webhook¶

Dopo aver configurato il trigger, imposta l’azione del webhook facendo clic su Aggiungi azione. Per il Tipo, fai clic su Esegui codice, quindi configura il campo code con il codice di esempio qui sotto. Infine, fai clic su Salva e chiudi.
    
    
    # variables to retrieve and hold data from the payload
    contact_name = payload.get('name')
    contact_email = payload.get('email')
    contact_phone = payload.get('phone')
    
    # a Python function to turn the variables into a contact in Odoo
    if contact_name and contact_email:
        new_partner = env['res.partner'].create({
            'name': contact_name,
            'email': contact_email,
            'phone': contact_phone,
            'company_type':'person',
            'customer_rank': 1,
        })
    # an error message for missing required data in the payload
    else:
        raise ValueError("Missing required fields: 'name' and 'email'")
    

#### Riassunto configurazione webhook¶

Per riassumere ciò che è stato configurato, il webhook crea un contatto quando una chiamata API viene inviata all’URL del webhook che include le informazioni del contatto.

#### Testare il webhook¶

Testa la configurazione del webhook per assicurarti che tutto sia corretto. Per inviare il trigger simulato, il processo utilizza uno strumento chiamato [Postman](https://www.postman.com/).

Questa sezione illustra i passaggi per testare il webhook in Postman, ma non offre assistenza in caso di problemi con lo strumento. Per ottenere assistenza specifica con Postman, contatta il loro team di supporto.

Una volta aperto Postman, crea una nuova richiesta e imposta il metodo su POST. Successivamente, copia l’URL del webhook da testare e incollalo nel campo URL di Postman. In seguito, fai clic sulla scheda Body e poi du raw. Imposta il tipo di file su JSON, quindi copia questo codice e incollalo nel file.
    
    
    {
        "name": "CONTACT NAME",
        "email": "CONTACTEMAIL@EMAIL.COM",
        "phone": "CONTACT PHONE NUMBER"
    }
    

Sostituisci i campi precedenti con le informazioni di un nuovo contatto in Postman e poi fai clic su Invia.

Se viene restituito un messaggio che dice `200 OK` o `status: ok`, allora il webhook funziona correttamente dal lato di Odoo. Il nuovo contatto di prova appare nell’app **Contatti**. Da qui, si può iniziare l’implementazione con l’altro strumento per inviare automaticamente le chiamate webhook a Odoo utilizzando l’URL del webhook.

Se vengono restituite altre risposte, il numero a esse associato aiuta a identificare il problema. Ad esempio, un `500 Internal Server Error` significa che Odoo non è riuscito a interpretare correttamente la chiamata. Se questo viene restituito, assicurati che i campi nel file JSON sia mappati correttamente nella configurazione del webhook e in Postman.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/studio/automated_actions/webhooks.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../pdf_reports.html "Reportistica in PDF") |
  * [precedente](../automated_actions.html "Regole di automazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Studio](../../studio.html) »
  * [Regole di automazione](../automated_actions.html) »
  * Webhook


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