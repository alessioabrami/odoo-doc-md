# Acconti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](proforma.html "Fatture proforma") |
  * [precedente](invoicing_policy.html "Fatture basate su quantità ordinate o consegnate") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Acconti



# Acconti¶

Un acconto è un pagamento iniziale, anticipato, effettuato durante la conferma di una transazione di vendita. L’acconto riduce il rischio per entrambe le parti (venditore e acquirente) in quanto indica un impegno reciproco a portare a termine la transazione di vendita.

Con l’acconto, l’acquirente paga una parte dell’importo totale dovuto e si impegna a pagare l’importo rimanente in un secondo momento. A sua volta, il venditore fornisce beni o servizi all’acquirente dopo aver accettato l’acconto, confidando nel fatto che l’importo rimanente sarà pagato in seguito.

Nell’app Odoo **Vendite** , è possibile personalizzare gli acconti per soddisfare i bisogni di ogni transazione di vendita.

## Crea fatture¶

Quando un ordine di vendita viene confermato, è disponibile l’opzione per creare una fattura, tramite il pulsante Crea fattura. Quando fai clic su di esso, appare un pop-up Crea fattura(e).

Nota

Le fatture vengono create automaticamente come bozze, in modo da poter essere revisionate prima della convalida.

Nel pop-up Crea fattura(e) pop-up, ci sono 3 opzioni tra cui poter scegliere nel campo Crea fattura:

  * Fattura normale

  * Anticipo (percentuale)

  * Anticipo (importo fisso)




## Richiesta acconto iniziale¶

Nella finestra pop-up Crea fattura(e), troverai le seguenti opzioni di acconto:

  * Anticipo (percentuale)

  * Anticipo (importo fisso)




Scegli l’opzione che preferisci e poi inserisci l’importo sia in percentuale che come prezzo fisso nel campo Importo anticipo.

Una volta riempiti tutti i campi, fai clic sul pulsante Crea bozza. Dopo aver fatto clic sul pulsante, Odoo mostrerà la bozza fattura cliente.

Importante

Se appare l’errore Operazione non valida, assicurati che la [politica di fatturazione](invoicing_policy.html) sia configurata correttamente. In alcuni casi, ad esempio, la politica di fatturazione viene configurata per richiedere la consegna prima della fatturazione.

Nella scheda Righe fattura della Bozza fattura cliente, l’acconto che è stato appena configurato nel modulo pop-up Crea fatture appare come Prodotto.

## Esempio: richiesta anticipo 50%¶

Nota

L’esempio seguente prevede un anticipo del 50% su un prodotto (Armadio con ante) con Quantità ordinate come Politica di fatturazione.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

Per prima cosa, accedi all’app Vendite ‣ Nuovo e aggiungi un Cliente al preventivo.

Successivamente, fai clic su Aggiungi un prodotto nella scheda Righe ordine e seleziona il prodotto Armadio con ante.

Quando l’ordine viene confermato (tramite il pulsante Conferma), il preventivo si trasforma in un ordine di vendita. A questo punto, è possibile creare e visualizzare la fattura facendo clic su Crea fattura.

In seguito, nella finestra Crea fatture che appare, seleziona Anticipo (percentuale) e scrivi `50` nel campo Importo acconto.

Nota

Il Conto di ricavo collegato al prodotto per cui è stato configurato il Pagamento anticipato può essere modificato.

Per maggiori informazioni, consulta la documentazione sulla Modifica del conto di ricavo per gli acconti.

È anche possibile configurare un Conto di acconto su una categoria prodotto. Se configurato, questo conto avrà la priorità.

Infine, fai clic su Crea bozza fattura per creare e visualizzare la bozza della fattura.

Facendo clic su Crea bozza fattura, apparirà la bozza della fattura che include l’acconto come Prodotto nella scheda Righe fatture.

Da qui, la fattura può essere confermata e registrata facendo clic su Conferma. La conferma della fattura cambia lo stato da Bozza a Confermata. Inoltre, rivela una nuova serie di pulsanti nella parte superiore della pagina.

Usando i pulsanti è possibile registrare il pagamento facendo clic su Registra pagamento.

In questo modo si apre il modulo pop-up Registra pagamento, che viene popolato automaticamente con le informazioni necessarie. Conferma la correttezza delle informazioni fornite e apporta le modifiche. Una volta terminato, fai clic sul pulsante Crea pagamento.

Dopo aver fatto clic su Crea pagamento, Odoo mostra la fattura del cliente con il banner verde In pagamento nell’angolo superiore destro.

Ora, quando il cliente vuole pagare l’importo rimanente dell’ordine, è necessario creare un’altra fattura. A tal fine, è necessario tornare all’ordine di vendita, seguendo i link del percorso.

Tornando all’ordine di vendita, nella scheda Righe ordine apparirà una nuova sezione dal titolo Acconti, insieme all’acconto appena fatturato e registrato.

In seguito, fai clic sul pulsante Crea fattura.

Nella finestra pop-up Crea fatture che appare, ci sono due nuovi campi: Già fatturato e Importo da fatturare.

Se l’importo rimanente è pronto per essere pagato, seleziona l’opzione Fattura normale. Odoo creerà una fattura per l’importo esatto necessario a completare il pagamento totale, come indicato nel campo Importo da fatturare.

Una volta completata l’operazione, fai clic su Crea bozza fattura.

In questo modo, viene visualizzata un’altra pagina Bozza fattura cliente, che elenca _tutte_ le fatture per quello specifico ordine di vendita nella scheda Righe fattura. Ogni voce di fattura mostra tutte le informazioni necessarie relative a ciascuna fattura.

Per completare il flusso, fai clic su Conferma, e lo stato della fattura passa da Bozza a Confermata. Successivamente, fai clic su Registra pagamento.

Ancora una volta, apparirà la finestra Registra pagamento, con tutti i campi autopopolati con le informazioni necessarie, compreso l’importo rimanente da pagare per l’ordine.

Dopo aver confermato queste informazioni, fai clic su Crea pagamento. In questo modo viene visualizzata la Fattura cliente finale con il banner verde In pagamento nell’angolo superiore destro. Inoltre, entrambi gli acconti sono presenti nella scheda Righe fattura.

A questo punto, il flusso è stato completato.

Nota

Questo flusso è possibile anche con l’opzione Importo fisso.

Importante

Se si utilizza un acconto con un prodotto che ha una politica di fatturazione di tipo Quantità consegnate e il costo del prodotto _supera_ l’acconto del 50% (come nella maggior parte dei casi), viene creata una fattura normale.

Tuttavia, per i prodotti che costano _meno_ dell’acconto del 50%, gli acconti non potranno essere dedotti al momento della fatturazione al cliente.

Questo perché i prodotti dovrebbero essere consegnati _prima_ di creare la fattura finale, dato che Odoo non consente totali negativi per le fatture.

Se non è stato consegnato nulla, viene creata una Nota di credito, che annulla la bozza di fattura creata dopo il pagamento dell’acconto.

Per utilizzare l’opzione Nota di credito, è necessario installare l’applicazione _Magazzino_ , per confermare la consegna. Altrimenti, la quantità consegnata può essere inserita manualmente direttamente nell’ordine di vendita.

## Esempio: acconto 100% richiesto¶

Il processo di richiesta di un acconto pari al 100% è simile al processo di configurazione di un ref:`acconto del 50% <sales/invoicing/50-percent-down-payments>` ma con meno step.

Nota

Un acconto del 100% non equivale a un pagamento completo dell’ordine di vendita.

Un ordine di vendita pagato tramite il normale processo di fatturazione non consentirà di generare ulteriori fatture e **non** verrà mostrato il pulsante _Crea fattura_ sull’ordine di vendita.

Seguendo questo esempio, il pulsante _Crea fattura_ _verrà_ visualizzato sull’ordine di vendita. Questo perché Odoo si aspetta che venga creata un’altra fattura dopo l’acconto per completare il pagamento dell’ordine di vendita.

In questo esempio, viene utilizzato il prodotto _Installazione pannello solare_.

Per configurare un acconto del 100%, inizia accedendo al modulo Vendite ‣ Nuovo e aggiungi un Cliente al preventivo.

Successivamente, fai clic su Aggiungi un prodotto nella scheda Righe ordine e seleziona il prodotto `Installazione pannello solare`.

Dopo aver fatto clic sul pulsante Conferma, il preventivo si trasforma in ordine di vendita. A questo punto, è possibile creare una fattura facendo clic su Crea fattura nell’angolo in alto a sinistra.

Nella finestra Crea fatture che appare, seleziona Anticipo (percentuale) e scrivi `100` nel campo Importo acconto.

Successivamente, fai clic su Crea bozza fattura per creare una bozza di fattura. Ciò ti permette di visualizzare la bozza di fattura, che include l”acconto come Prodotto nella scheda Righe fattura.

La fattura ora può essere confermata e registrata facendo clic su Conferma. La conferma della fattura cambia lo stato da Bozza a Confermata. Inoltre, rivela una nuova serie di pulsanti nella parte superiore della pagina.

Il pagamento può essere registrato facendo clic sul pulsante Registra pagamento.

In questo modo si apre il modulo pop-up Registra pagamento, che viene popolato automaticamente con le informazioni necessarie. Conferma la correttezza delle informazioni fornite e apporta le modifiche. Una volta terminato, fai clic sul pulsante Crea pagamento.

Dopo aver fatto clic su Crea pagamento, Odoo mostra la fattura del cliente con il banner verde In pagamento nell’angolo superiore destro.

Il processo ora è completo e l’acconto del 100% è stato applicato con successo.

## Modifica conto di ricavo per acconti¶

Per modificare o sistemare il conto di ricavo collegato alla pagina del prodotto Acconto, è **necessario** installare l’applicazione _Contabilità_.

Accedi alla pagina Prodotti (app Vendite ‣ Prodotti ‣ Prodotti), cerca il prodotto `Anticipo` nella barra relativa e selezionalo per visualizzare la pagina con tutti i dettagli.

Dopo aver installato l’app _Contabilità_ , la scheda Contabilità diventa disponibile nella pagina prodotto.

Nella scheda Contabilità, è possibile modificare il conto di ricavo nel campo Conto di ricavo nella sezione Crediti.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/invoicing/down_payment.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](proforma.html "Fatture proforma") |
  * [precedente](invoicing_policy.html "Fatture basate su quantità ordinate o consegnate") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Acconti


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
  *[NSSL]: Non-Shopee Supported Logistics