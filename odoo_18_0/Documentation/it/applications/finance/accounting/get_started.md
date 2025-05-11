# Per iniziare — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_started/cheat_sheet.html "Promemoria contabile") |
  * [precedente](../accounting.html "Contabilità e fatturazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Per iniziare



# Per iniziare¶

Quando apri per la prima volta l’applicazione Contabilità di Odoo, verrai accolto dalla Dashboard e da un banner introduttivo che ti mostrerà passo dopo passo il funzionamento dell’applicazione. Il banner di onboarding viene visualizzato finché non scegli di chiuderlo.

Le impostazioni disponibili nel banner di onboarding possono essere modificate in seguito, seguendo il percorso Contabilità ‣ Configurazione ‣ Impostazioni.

Nota

A seguito dell’installazione dell’app Contabilità di Odoo, il **Pacchetto di localizzazione fiscale** appropriato per la tua azienda verrà installato automaticamente, secondo il Paese selezionato al momento della creazione del database. In questo modo, potrai subito iniziare a utilizzare piani contabili, resoconti e imposte. [Fai clic qui](../fiscal_localizations.html#fiscal-localizations-packages) per maggiori informazioni sui Pacchetti di localizzazione fiscale.

## Banner onboarding Contabilità¶

Il banner di onboarding dell’app Contabilità è composto da quattro step:

  1. Periodi contabili

  2. Conto bancario

  3. Imposte

  4. Piano dei conti




### Periodi contabili¶

Stabilisci le date di apertura e chiusura degli **Anni fiscali** , utilizzate per generare automaticamente i rendiconti, e imposta la **Periodicità dichiarazione fiscale** , insieme a un promemoria per non perdere mai una scadenza relativa alla dichiarazione.

Per impostazione predefinita, la data di apertura è fissata al 1° gennaio e la data di chiusura al 31 dicembre, in quanto si tratta della pratica più comune.

Nota

È possibile modificare le impostazioni tramite il percorso Contabilità ‣ Configurazione ‣ Impostazioni ‣ Periodi fiscali e aggiornare i valori.

### Conto bancario¶

Collega il tuo conto bancario al database per sincronizzare automaticamente tutti gli estratti conto. Per farlo, trova la tua banca nell’elenco, fai clic su Collega e segui le istruzioni sullo schermo.

Nota

[Fai clic qui](bank/bank_synchronization.html) per scoprire di più sulla funzionalità.

Se il tuo istituto bancario non può essere sincronizzato automaticamente, oppure se preferisci non sincronizzarlo con il tuo database, puoi anche configurare il tuo conto bancario manualmente digitandone il nome, facendo clic su Crea conto bancario, per poi riempire il modulo.

  * Nome: il nome del conto, come mostrato in Odoo

  * Numero conto: numero conto corrente (IBAN in Europa)

  * Banca: fai clic su Crea e modifica per configurare i dettagli della banca. Aggiungi il Nome e il Codice identificativo (BIC o SWIFT) dell’istituto bancario

  * Codice: questo codice è il Codice breve del tuo registro, come mostrato in Odoo. Per impostazione predefinita, Odoo crea un nuovo registro con questo codice breve

  * Registro: questo campo viene visualizzato se si dispone di un registro bancario esistente non ancora collegato a un conto bancario. In tal caso, seleziona il Registro che vuoi utilizzare per registrare le transazioni finanziarie collegate a questo conto bancario o creane uno nuovo facendo clic su Crea e modifica.




Nota

  * Grazie a questo strumento, è possibile aggiungere tutti i conti correnti di cui hai bisogno seguendo il percorso Contabilità ‣ Configurazione ‣ Aggiungi conto bancario.

  * [Fai clic qui](bank.html) per maggiori informazioni sui conti bancari.




### Imposte¶

Questo menu ti permette di creare nuove imposte, (dis)attivare o modificare quelle esistenti. A seconda del [pacchetto di localizzazione](../fiscal_localizations.html) installato nel database, le imposte richieste per il tuo Paese sono configurate automaticamente.

Nota

[Fai clic qui](taxes.html) per avere più informazioni sulla configurazione delle imposte.

### Piano dei conti¶

Grazie a questo menu, puoi aggiungere conti al tuo **Piano dei conti** e indicare i saldi di apertura iniziali.

Le impostazioni di base vengono visualizzate su questa pagina per aiutarti a verificare il tuo Piano dei conti. Per accedere a tutte le impostazioni di un conto, fai clic sul pulsante Visualizza alla fine della riga.

Nota

[Fai clic qui](get_started/chart_of_accounts.html) per scoprire di più su come configurare i Piani contabili.

## Banner onboarding Fatturazione¶

Esiste un altro banner di onboarding che ti aiuta a capire come utilizzare le app Fatturazione e Contabilità di Odoo. Il banner relativo all’app Fatturazione è quello che ti accoglie se scegli di utilizzare l’app correlata.

Se hai già installato l’app Contabilità sul tuo database, puoi accedervi seguendo il percorso Contabilità ‣ Clienti ‣ Fatture.

Il banner di onboarding dell’app Fatturazione è composto da quattro step:

  1. Dati azienda

  2. Struttura documenti

  3. Crea fattura

  4. Pagamenti online




### Dati azienda¶

Aggiungi i dati della tua azienda, come nome, indirizzo, logo, sito web, numero di telefono, indirizzo e-mail e codice fiscale o partita IVA. Questi dati vengono poi visualizzati sui documenti, come le fatture.

Nota

È anche possibile modificare i dettagli dell’azienda accedendo alle Impostazioni ‣ Impostazioni generali, per poi scorrere in basso fino alla sezione Aziende e infine Aggiorna informazioni.

### Struttura documenti¶

Personalizza la [struttura predefinita delle fatture](../../studio/pdf_reports.html#studio-pdf-reports-default-layout).

Nota

È possibile modificare la struttura della fattura tramite il percorso Impostazioni ‣ Impostazioni generali, scorrere in basso fino alla sezione Aziende per poi fare clic su Configura struttura documento.

### Crea fattura¶

Crea la prima fattura.

Suggerimento

Aggiungi il **numero di conto corrente** e un link ai **Termini e condizioni generali** nel piè di pagina. In questo modo, i tuoi contatti potranno trovare online il contenuto completo dei GT&C senza doverli stampare sulle fatture emesse.

### Pagamenti online¶

Inizia a lavorare con Stripe e attiva pagamenti sicuri integrati con carte di credito e di debito all’interno di Odoo.

Suggerimento

Per utilizzare altri servizi di pagamento, accedi all’applicazione Fatturazione –> Configurazione –> Fornitori di pagamenti e [attiva i fornitori desiderati](../payment_providers.html).

Vedi anche

  * [Conti bancari e di cassa](bank.html)

  * [Piano dei conti](get_started/chart_of_accounts.html)

  * [Consolidamento](get_started/consolidation.html)

  * :doc:banca/sincronizzazione_bancaria

  * [Fiscal localizations](../fiscal_localizations.html)

  * [Tutorial Odoo: Contabilità e Fatturazione - Per iniziare [video]](https://www.odoo.com/slides/slide/getting-started-1692)




  * [Promemoria contabile](get_started/cheat_sheet.html)
  * [Piano dei conti](get_started/chart_of_accounts.html)
  * [Consolidamento](get_started/consolidation.html)
  * [Sistema multi valuta](get_started/multi_currency.html)
  * [Prezzo medio sulla merce resa](get_started/avg_price_valuation.html)
  * [Unità fiscali](get_started/tax_units.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/accounting/get_started.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](get_started/cheat_sheet.html "Promemoria contabile") |
  * [precedente](../accounting.html "Contabilità e fatturazione") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Per iniziare


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
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record