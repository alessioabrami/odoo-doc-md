# Modelli di riconciliazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](internal_transfers.html "Trasferimenti interni") |
  * [precedente](reconciliation.html "Riconciliazione bancaria") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Modelli di riconciliazione



# Modelli di riconciliazione¶

I modelli di riconciliazione vengono utilizzati per automatizzare il processo di [riconciliazione bancaria](reconciliation.html), molto utile quando si ha a che fare con registrazioni ricorrenti come commissioni bancarie. I modelli di riconciliazione possono essere utili anche per gestire [sconti di cassa](../customer_invoices/cash_discounts.html).

Ogni modello viene creato in base a un tipo di modello e alle condizioni della transazione bancaria.

Vedi anche

  * [Sincronizzazione bancaria](bank_synchronization.html)

  * [Tutorial Odoo: Modelli di riconciliazione](https://www.odoo.com/slides/slide/reconciliation-models-1841?fullscreen=1)




## Tipi di modelli di riconciliazione¶

È possibile accedere ai modelli di riconciliazione dall’app Contabilità ‣ Configurazione ‣ Banca: Modelli di riconciliazione. Per ogni modello di riconciliazione, è necessario configurare un Tipo. Esistono tre tipi di modelli:

  * Pulsante per generare la voce di controparte: viene creato un pulsante nella sezione delle voci risultanti della vista di riconciliazione bancaria. Se fai clic su questo pulsante, si genera una voce di controparte da riconciliare con la transazione attiva in base alle regole impostate nel modello. Le regole specificate nel modello determinano i conti, gli importi, le etichette e la distribuzione analitica della voce di controparte.

  * Regola per suggerire la voce di controparte: utilizzata per le transazioni ricorrenti per abbinare la transazione a una nuova voce in base a condizioni che devono corrispondere alle informazioni della transazione

  * Regola per abbinare fatture cliente/fornitore: utilizzata per le transazioni ricorrenti per abbinare la transazione a fatture cliente e fornitore o pagamenti esistenti in base a condizioni che devono corrispondere alle informazioni della transazione.




## Modelli di riconciliazione predefiniti¶

In Odoo, sono disponibili vari modelli preconfigurati, in base alla localizzazione fiscale dell’azienda. È possibile aggiornarli se necessario. Gli utenti possono anche creare i propri modelli di riconciliazione facendo clic su Nuovo.

Importante

Se un record corrisponde a vari modelli di riconciliazione, verrà applicato il primo nella _sequenza_ dei modelli. Puoi riorganizzare l’ordine trascinando e rilasciando la maniglia accanto al nome.

### Corrispondenza perfetta fatture clienti/fornitori¶

Il modello dovrebbe essere il primo della _sequenza_ in quanto attiva la funzione di suggerimento dell’abbinamento di fatture cliente o fornitore esistenti con una transazione bancaria in base a determinate condizioni.

Odoo riconcilia automaticamente il pagamento quando viene selezionata l’opzione di Validazione automatica e le condizioni del modello vengono rispettate. In questo caso, il software si aspetta di trovare il riferimento della fattura o del pagamento sulla riga dell’estratto conto (una volta selezionata la voce Etichetta) e il nome del partner (se il campo Partner selezionato è stato selezionato) per suggerire la voce di controparte corretta e riconciliare il pagamento automaticamente.

### Corrispondenza parziale fatture clienti/fornitori se pagate parzialmente¶

Questo modello suggerisce una fattura cliente o fornitore che corrisponde parzialmente al pagamento quando l’importo ricevuto è leggermente inferiore all’importo della fattura, come nel caso di **sconti di cassa**. La differenza viene riconciliata con il conto indicato nella scheda voce della controparte.

Il Tipo del modello di riconciliazione è Regola per abbinare fatture ed è necessario impostare anche la Tolleranza di pagamento.

Nota

La Tolleranza di pagamento viene applicata solamente a pagamenti più piccoli. Non viene presa in considerazione quando si riceve un sovra pagamento.

Vedi anche

[Sconti di cassa e riduzioni fiscali](../customer_invoices/cash_discounts.html)

### Riga commissioni bancarie¶

Questo modello suggerisce una voce di controparte secondo le regole configurate per il modello. In questo caso, il Tipo del modello di riconciliazione è Regola per suggerire la voce della controparte e la Etichetta può essere utilizzata per identificare le informazioni che si riferiscono alle Commissioni bancarie nell’etichetta della transazione.

Nota

Le [espressioni regolari](https://regexone.com/), spesso abbreviate come **Regex** , possono essere utilizzate in Odoo in vari modi per cercare, convalidare e manipolare i dati nel sistema. Le regex possono essere potenti ma anche complicate quindi è necessario utilizzare saggiamente e con una buona conoscenza degli schemi con cui si lavora.

Per utilizzare le espressioni regolari nei modelli di riconciliazione, imposta il Tipo di transazione su Corrisponde a espressione regolare e aggiungi la tua espressione. Odoo recupera automaticamente le transazioni che corrispondono alla tua Regex e le condizioni specificate nel modello.

## Mappatura partner¶

La mappatura dei partner consente di stabilire regole per abbinare automaticamente le transazioni al conto partner corretto, risparmiando tempo e riducendo il rischio di errori che possono verificarsi durante la riconciliazione manuale. Ad esempio, è possibile creare una regola di mappatura dei partner per i pagamenti in entrata con numeri di riferimento specifici o parole chiave nella descrizione della transazione. Quando un pagamento in entrata soddisfa questi criteri, Odoo lo mappa automaticamente sul conto del cliente corrispondente.

Per creare una regola mappatura partner, apri la scheda Mappatura partner e riempi i campi Trova testo in etichetta, Trova testo nelle note e Partner.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/bank/reconciliation_models.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](internal_transfers.html "Trasferimenti interni") |
  * [precedente](reconciliation.html "Riconciliazione bancaria") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Modelli di riconciliazione


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