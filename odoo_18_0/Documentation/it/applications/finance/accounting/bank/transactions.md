# Transazioni — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reconciliation.html "Riconciliazione bancaria") |
  * [precedente](bank_synchronization/enablebanking.html "Abilitare la Banca") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Transazioni



# Transazioni¶

L’importazione delle transazioni dagli estratti conto bancari consente di tenere traccia delle transazioni dei conti corrente e di riconciliarle con quelle registrate per la contabilità.

La [sincronizzazione bancaria](bank_synchronization.html) automatizza il processo. Tuttavia, se non vuoi utilizzarla o se la tua banca non è ancora supportata, sono disponibili altre opzioni:

  * Importare transazioni bancarie eseguite dalla tua banca;

  * Registrare transazioni bancarie manualmente.




Nota

Il raggruppamento delle transazioni per estratto conto è facoltativo.

## Importare transazioni¶

Odoo supporta più formati file per importare transazioni:

  * il formato Cash Management (CAMT.053) consigliato da SEPA;

  * valori separati da virgole (CSV);

  * Open Financial Exchange (OFX);

  * Quicken Interchange Format (QIF);

  * Belgio: Coded Statement of Account (CODA).




Per importare un file, accedi alla dashboard Contabilità e nel registro Banca fai clic su Importa file.

Suggerimento

In alternativa, puoi anche:

  * fare clic sull’icona __(ellissi) nel registro Banca e selezionare Importa file;

  * oppure accedere all’elenco di transazioni facendo clic sull’icona __(ellissi) nel registro Banca per poi selezionare Transazioni, successivamente fare clic sull’icona __(ingranaggio) e selezionare Importa record.




In seguito, scegli il file e caricalo.

Dopo aver configurato le opzioni di formattazione necessarie e aver mappato le colonne del file con i campi Odoo correlati, puoi eseguire un Test e Importare le tue transazioni bancarie.

Vedi anche

[Esportare e importare dati](../../../essentials/export_import_data.html)

## Registrare transazioni bancarie manualmente¶

È possibile registrare le transazioni bancarie anche manualmente. Per farlo, accedi alla dashboard Contabilità, fai clic sul registro Banca e poi su Nuova. Assicurati di compilare i campi Partner ed Etichetta per facilitare il processo di riconciliazione.

## Estratti conto¶

Un **estratto conto bancario** è un documento fornito da una banca o da un istituto finanziario che elenca le transazioni avvenute su un determinato conto bancario in un determinato periodo di tempo.

In Odoo Contabilità, raggruppare le transazioni in base al relativo estratto conto è facoltativo, ma a seconda del flusso aziendale, si potrebbe volerle registrare a scopo di controllo.

Importante

Se vuoi confrontare i saldi finali degli estratti conto bancari con i saldi finali dei record finanziari, _non dimenticare di creare una transazione di apertura_ per registrare il saldo del conto bancario alla data di inizio della sincronizzazione o dell’importazione delle transazioni. Quest’operazione è necessaria per garantire l’accuratezza della contabilità.

Per accedere agli estratti conto esistenti, apri la dashboard relativa alla contabilità, fai clic sull’icona __(ellissi) accanto al registro di banca o di cassa che vuoi controllare e poi fai clic su Estratti conto.

### Creare estratti conto dalla vista kanban¶

Apri la vista della riconciliazione bancaria (kanban) dalla dashboard della contabilità facendo clic sul nome del registro bancario e individua la transazione corrispondente all’ultima (più recente) transazione dell’estratto conto bancario. Fai clic sul pulsante Estratto conto quando si passa il mouse sulla riga di separazione superiore per creare un estratto conto da quella transazione fino alla transazione più vecchia che non fa ancora parte di un estratto conto.

Nella finestra Crea estratto conto, riempi il campo Riferimento dell’estratto conto, verificane il Saldo iniziale e il Saldo finale, per poi fare clic su Salva.

### Creare estratti conto dalla vista elenco¶

Apri l’elenco di transazioni facendo clic sul nome del registro bancario e passando alla vista elenco. Seleziona tutte le transazioni che corrispondono all’estratto conto bancario e nella colonna Estratto conto, seleziona un estratto conto esistente oppure creane uno nuovo digitandone il riferimento, facendo clic su Crea e modifica…, riempiendo i dettagli e terminare salvando.

### Visualizzare, modificare e stampare gli estratti conto¶

Per visualizzare un estratto conto esistente, fai clic sull’importo dell’estratto conto nella vista riconciliazione (kanban) o fai clic sul nome dell’estratto conto nella vista elenco delle transazioni bancarie. Da qui, puoi modificare il Riferimento, il Saldo iniziale oppure il Saldo finale.

Nota

L’aggiornamento manuale del Saldo iniziale comporta l’aggiornamento automatico del Saldo finale basato sul nuovo valore del Saldo iniziale e sul valore delle transazioni dell’estratto conto.

Avvertimento

Se il Saldo iniziale non corrisponde al Saldo finale dell’estratto conto precedente, oppure se il Saldo finale non corrisponde al saldo in corso (Sslfo iniziale più le transazioni dell’estratto conto), apparirà un avviso che spiega il problema. Per mantenere la flessibilità, è ancora possibile salvare senza prima risolvere il problema.

Per allegare una copia digitale (ad es., JPEG, PNG, o PDF) dell’estratto conto bancario per una migliore conservazione dei dati, fai clic sul pulsante __ Allegati e seleziona il file da allegare.

Per generare e stampare un PDF dell’estratto conto bancario, fai clic sul pulsante Stampa (se accedi tramite la vista della riconciliazione) oppure fai clic sull’icona __(ingranaggio) e poi su __Estratto conto (se accedi tramite la vista elenco).

Nota

Quando generi un estratto conto per la stampa, quest’ultimo viene aggiunto automaticamente agli Allegati.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/bank/transactions.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](reconciliation.html "Riconciliazione bancaria") |
  * [precedente](bank_synchronization/enablebanking.html "Abilitare la Banca") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Transazioni


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