# Gestire un conto bancario in una valuta straniera — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](loans.html "Gestione dei prestiti") |
  * [precedente](internal_transfers.html "Trasferimenti interni") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Gestire un conto bancario in una valuta straniera



# Gestire un conto bancario in una valuta straniera¶

In Odoo, ogni transazione viene registrata nella valuta predefinita dell’azienda e i resoconti sono tutti basati su tale valuta predefinita. Quando si dispone di un conto bancario in una valuta estera, per ogni transazione Odoo memorizza due valori:

  * il debito/credito nella valuta della _azienda_

  * il debito/credito nella valuta del _conto bancario_.




I tassi di cambio vengono aggiornati automaticamente utilizzando i servizi web di un istituto bancario. Per impostazione predefinita, Odoo utilizza i servizi web della Banca Centrale Europea, ma sono disponibili altre opzioni.

## Configurazione¶

### Attivare più valute¶

Per lavorare con più valute, accedi al modulo Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute e spunta Multi valuta. Nella sezione Registra voce tasso di cambio in:, aggiungi un Registro, un Conto utili, un Conto perdite e poi fai clic su Salva.

### Configurare valute¶

Una volta completata la configurazione multi valuta in Odoo, tutte le valute vengono create per impostazione predefinita ma non attivate necessariamente. Per attivare nuove valute, fai clic su Attiva altre valute nella sezione Multi valuta o apri l’app Contabilità ‣ Configurazione ‣ Contabilità: Valute.

Una volta attivate le valute, puoi scegliere di **automatizzare** l’aggiornamento del tasso di cambio oppure continuare a farlo **manualmente**. Per configurare l’aggiornamento del tasso, torna al modulo Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute, seleziona Tassi di cambio automatici, imposta un Intervallo secondo la frequenza desiderata e fai clic su Salva. Puoi anche scegliere il Servizio da cui vuoi ottenere tassi di cambio.

Per aggiornare manualmente i tassi di cambio, fai clic sul pulsante Aggiorna ora (🗘) accanto al campo Prossima esecuzione.

### Crea un nuovo conto bancario¶

Apri l’applicazione Contabilità ‣ Configurazione ‣ Registri e creane uno nuovo. Aggiungi un Nome registro e imposta il Tipo su `Banca`. Nella scheda Registrazioni contabili, aggiungi un **codice breve** , una **valuta** e infine fai clic sul campo Conto bancario per creare un nuovo conto. Nella finestra pop-up per la creazione del conto, inserisci un nome, un codice (ad es.: 550007), imposta il tipo su `Banca e cassa`, configura un tipo di valuta e salva. Una volta tornato al **registro** , fai clic sul campo Numero conto e nella finestra pop-up riempi i campi Numero conto, Banca del tuo conto e salva.

Al momento della creazione del giornale, Odoo collega automaticamente il conto bancario al registro. Puoi trovarlo seguendo il percorso Contabilità ‣ Configurazione ‣ Contabilità: Piano dei conti.

## Fatture fornitore in valuta estera¶

Per pagare una fattura fornitore in una valuta straniera, è sufficiente selezionare la valuta accanto al campo Registro e registrare il pagamento. Odoo crea e registra automaticamente gli **utili/perdite sui cambi** esteri come nuova registrazione contabile.

Nota

È possibile pagare una fattura estera con un’altra valuta. In questo caso, Odoo converte automaticamente le due valute.

## Resoconto utili/perdite sui cambi non realizzati¶

Questo resoconto offre una panoramica di tutti gli importi non realizzati in una valuta estera nel tuo stato patrimoniale e ti permette di sistemare una registrazione o impostare manualmente un tasso di cambio. Per accedere al resoconto, accedi a Rendicontazione ‣ Gestione: Utili/perdite in valuta non realizzati. Da qui, avrai accesso a tutte le registrazioni aperte nel tuo **stato patrimoniale**.

Se desideri utilizzare una valuta diversa rispetto a quella configurata in Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute, fai clic sul pulsante Tassi di cambio e modifica il tasso delle valute estere nel resoconto.

Quando modifichi manualmente i **tassi di cambio** , appare un banner giallo che ti permette di reimpostare il tasso di Odoo. Per farlo, puoi fare semplicemente clic su Ripristina tasso Odoo.

Per aggiornare lo **stato patrimoniale** con l’importo della colonna rettifica, fai clic sul pulsante Registrazione di rettifica. Nella finestra pop-up, scegli un Registro, un Conto spese e un Conto di ricavo per calcolare ed elaborare gli **Utili/perdite non realizzati**.

Puoi impostare la data del resoconto tramite il campo Data. Odoo modifica automaticamente la data di registrazione applicando la data configurata nel campo Data di storno.

Una volta registrata, la colonna rettifica dovrebbe indicare `0.00`, il che significa che tutti **gli utili/perdite non realizzati** sono stati rettificati.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/bank/foreign_currency.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](loans.html "Gestione dei prestiti") |
  * [precedente](internal_transfers.html "Trasferimenti interni") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Gestire un conto bancario in una valuta straniera


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