# Note di credito e rimborsi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](cash_discounts.html "Sconti di cassa e riduzioni fiscali") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Note di credito e rimborsi



# Note di credito e rimborsi¶

Una nota di credito/debito è un documento inviato a un cliente per informarlo che gli è stato _accreditato/addebitato_ un determinato importo.

Diversi sono i casi d’uso che possono portare alla creazione di una nota di credito:

>   * un errore in una fattura
> 
>   * un reso di beni o un rifiuto dei servizi
> 
>   * i beni consegnati sono danneggiati.
> 
> 


Le note di debito sono meno comuni, ma sono utilizzate con maggior frequenza per tenere traccia dei debiti dovuti dai clienti o dai fornitori a causa di modifiche alle fatture confermate dei clienti o alle fatture dei fornitori.

Nota

L’emissione di una nota di credito/debito è l’unico metodo legale per annullare, rimborsare o modificare una fattura convalidata. Assicurati di **registrare il pagamento** se il cliente ha rimborsato il venditore e/o convalida il [reso](../../../sales/sales/products_prices/returns.html) se si tratta di un prodotto stoccabile.

## Creare una nota di credito cliente¶

Nella maggior parte dei casi, le note di credito vengono create direttamente dalle fatture corrispondenti. Per farlo, apri l’app Contabilità ‣ Clienti ‣ Fatture, apri la Fattura corrispondente e fai clic su Nota di credito.

Nella finestra Nota di credito, inserisci il Ragione visualizzata nella nota di credito e aggiorna il Registro e la Data di storno se necessario. Esistono due opzioni:

  * fai clic su Storna per aprire una bozza di nota di credito con i dettagli esatti della fattura originale. Aggiorna il Prodotto e la Quantità e fai clic su Conferma. Quest’opzione ti permette di effettuare rimborsi parziali o modificare la nota di credito.

  * Fai clic su Storna e crea fattura per creare una nota di credito, convalidarla automaticamente e riconciliarla con la fattura correlata per poi aprire una nuova bozza di fattura precompilata con i dettagli esatti della fattura originale.




Per creare una nota di credito da zero, apri il modulo Contabilità ‣ Clienti ‣ Note di credito e fai clic su Nuova. Completare una nota di credito è come completare una [fattura](../customer_invoices.html#accounting-invoice-creation).

Nota

La sequenza di una nota di credito inizia con `R` ed è seguita dal relativo numero di documento (ad es., RINV/2025/0004 è associato alla fattura INV/2025/0004).

## Creare una nota di debito cliente¶

Per creare una nota di debito, vai su Contabilità ‣ Clienti ‣ Fatture e segui questi step:

  1. Seleziona le fatture desiderate, fai clic su __ Azioni e seleziona Crea nota di debito.

  2. Nella finestra Crea nota di debito, inserisci la Ragione e aggiorna i campi Usa registro specifico e Data nota di debito se necessario.

  3. Attiva l’opzione Copia righe per copiare le righe della fattura e fai clic su Crea nota di debito.

  4. Nella nota di debito, aggiorna il Prodotto e la Quantità e fai clic su Conferma.




Suggerimento

Per creare una nota di debito dalla vista modulo della fattura, fai clic sull’icona __(ingranaggio) e seleziona Nota di debito.

## Registrare un rimborso fornitore¶

I rimborsi dei fornitori o le note di credito dei fornitori vengono registrate allo stesso modo delle note di credito:

Per registrare un rimborso fornitore o una nota di credito fornitore direttamente dalla fattura fornitore corrispondente, vai su Contabilità ‣ Fornitori ‣ Fatture fornitore, apri la fattura corrispondente e fai clic su Nota di credito.

Per registrarla da zero, vai su Contabilità ‣ Fornitori ‣ Rimborso e fai clic su Nuovo.

## Registrare una nota di debito fornitore¶

Le note di debito dei fornitori vengono registrate allo stesso modo delle note di debito emesse per i clienti.

Per registrare una nota di debito, vai su Contabilità ‣ Fornitori ‣ Fatture fornitore e seleziona le fatture desiderate. Fai clic su __ Azioni e seleziona Crea nota di debito.

Suggerimento

Per creare una nota di debito dalla vista modulo della fattura fornitore, fai clic sull’icona __(ingranaggio) e seleziona Nota di debito.

## Registrazioni contabili¶

La creazione di una nota di credito/debito da una fattura cliente/fornitore genera uno **storno** che annulla i movimenti contabili dalla fattura originale.

Example

La registrazione contabile di una fattura:

La registrazione contabile della nota di credito generata per stornare la fattura originale di cui sopra:

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/customer_invoices/credit_notes.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](cash_rounding.html "Arrotondamento di cassa") |
  * [precedente](cash_discounts.html "Sconti di cassa e riduzioni fiscali") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Note di credito e rimborsi


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record