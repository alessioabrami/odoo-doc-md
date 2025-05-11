# Riconciliazione bancaria — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reconciliation_models.html "Modelli di riconciliazione") |
  * [precedente](transactions.html "Transazioni") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Riconciliazione bancaria



# Riconciliazione bancaria¶

La **riconciliazione bancaria** è il processo che consiste nell’abbinare le tue [transazioni bancarie](transactions.html) con i record aziendali, come [fatture clienti](../customer_invoices.html), [fatture fornitore](../vendor_bills.html) e [pagamenti](../payments.html). Non solo è obbligatorio per la maggior parte delle aziende, ma offre anche diversi vantaggi, come la riduzione del rischio di errori nei resoconti finanziari, l’individuazione di attività fraudolente e una migliore gestione dei flussi di cassa.

Grazie ai [modelli di riconciliazione](reconciliation_models.html) bancaria, Odoo preseleziona automaticamente le registrazioni corrispondenti.

Vedi anche

  * [Tutorial Odoo: Riconciliazione bancaria](https://www.odoo.com/slides/slide/bank-reconciliation-2724)

  * [Sincronizzazione bancaria](bank_synchronization.html)

  * transazioni




## Visualizzazione riconciliazione bancaria¶

Per accedere alla **vista della riconciliazione** di un giornale di banca, accedi alla dashboard relativa alla contabilità e:

  * fai clic sul nome del registro (ad es. Banca) per mostrare tutte le transazioni, comprese quelle riconciliate in precedenza oppure

  * fai clic sul pulsante Voci riconciliate per visualizzare tutte le transazioni preselezionate da Odoo per la riconciliazione. Puoi rimuovere il filtro Non abbinato dalla barra di ricerca per includere anche le transazioni riconciliate in precedenza.




La vista della riconciliazione bancaria è divisa in tre sezioni: transazioni, registrazioni controparte e registrazioni risultanti.

Transazioni
    

La sezione relativa alle transazioni sulla sinistra mostra tutte le operazioni bancarie, partendo dalle più nuove in alto. Fai clic su una transazione per selezionarla.

Voci controparte
    

La sezione relativa alle voci della controparte, in basso a destra, mostra le opzioni relative all’abbinamento della transazione selezionata. Sono disponibili più schede, tra cui: Abbinare registrazioni esistenti, Pagamenti raggruppati, Operazioni manuali e Comunicazioni, che contiene il chatter per la transazione selezionata.

Registrazione risultante
    

La sezione voce risultante in alto a destra mostra la transazione selezionata abbinata alle voci risultanti e include qualsiasi debito o credito rimanente. In questa sezione, puoi convalidare la riconciliazione o contrassegnarla come Da controllare. Nella sezione della voce risultante, è disponibile qualsiasi pulsante relativo a modelli di riconciliazione.

## Riconciliare le transazioni¶

È possibile abbinare automaticamente le transazioni grazie all’uso dei [modelli di riconciliazione](reconciliation_models.html), oppure è possibile abbinarle con registrazioni esistenti, pagamenti raggruppati, operazioni manuali e pulsanti relativi a modelli di riconciliazione.

  1. Seleziona una transazione tra transazioni non abbinate

  2. Indica la controparte. Esistono vari modi per definire una controparte, tra cui abbinare registrazioni esistenti, operazioni manuali, pagamenti raggruppati e pulsanti per i modelli di riconciliazione

  3. Se la voce risultante non è completamente bilanciata, esegui il bilanciamento aggiungendo un’altra voce di controparte esistente o cancellala tramite operazione manuale

  4. Fai clic sul pulsante Convalida per confermare la riconciliazione e passare alla transazione successiva.




Suggerimento

Se non sei sicuro sul come riconciliare una transazione in particolare e vorresti occupartene più tardi, usa il pulsante Da controllare. Tutte le transazioni contrassegnate come Da controllare possono essere visualizzate utilizzando il filtro Da controllare.

Nota

Le transazioni bancarie vengono registrate nel **conto provvisorio del registro** fino al momento della riconciliazione. A questo punto, la riconciliazione modifica la registrazione del registro della transazione sostituendo il conto provvisorio della banca con il conto debito, credito o provvisorio corrispondente.

### Abbinare registrazioni esistenti¶

La presente scheda contiene registrazioni abbinate preselezionate automaticamente da Odoo secondo i modelli di riconciliazione. L’ordine della registrazione si basa sui [modelli di riconciliazione](reconciliation_models.html) e le registrazioni suggerite appariranno per prime.

Suggerimento

La barra di ricerca nella scheda Abbinamento registrazioni esistenti permette di cercare movimenti contabili specifici.

### Pagamenti raggruppati¶

[Batch payments](../payments/batch.html) allow you to group different payments to ease reconciliation. Use the Batch Payments tab to find batch payments for customers and vendors. Similarly to the Match Existing Entries tab, the Batch Payments tab has a search bar that allows you to search for specific batch payments.

### Operazioni manuali¶

Se non c’è una registrazione esistente che corrisponde alla transazione selezionata, è possibile che tu voglia riconciliare la transazione manualmente scegliendo il conto e l’importo corretti per poi completare tutti i campi aggiuntivi rilevanti.

Suggerimento

Puoi utilizzare l’opzione pagato completamente per riconciliare un pagamento, anche in casi in cui viene ricevuto solo un pagamento parziale. Nella sezione della voce risultante, apparirà una nuova riga che mostra il saldo aperto registrato di default nel conto di credito. Puoi scegliere un altro conto facendo clic sulla nuova riga nella sezione della voce risultante e selezionando il Conto per registrare il saldo aperto.

Nota

Le righe vengono riconciliate in modo silenzioso, a meno che non sia richiesta una voce di storno, che lancia una procedura guidata di riconciliazione.

### Pulsanti modelli di riconciliazione¶

Utilizza un pulsante [modello di riconciliazione](reconciliation_models.html) per le operazioni manuali utilizzate di frequente. Questi pulsanti personalizzati ti consentono di riconciliare rapidamente e manualmente le transazioni bancarie anche in combinazione con registrazioni esistenti.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/bank/reconciliation.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reconciliation_models.html "Modelli di riconciliazione") |
  * [precedente](transactions.html "Transazioni") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Riconciliazione bancaria


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
  *[POS]: point of sale
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: Servicio de Rentas Internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Fornitura Immediata di Informazioni
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
  *[PAC]: fornitori autorizzati
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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda