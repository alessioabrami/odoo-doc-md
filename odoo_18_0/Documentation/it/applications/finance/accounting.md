# Contabilità e fatturazione — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](accounting/get_started.html "Per iniziare") |
  * [precedente](../finance.html "Finanza") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Contabilità e fatturazione



# Contabilità e fatturazione¶

**Odoo Fatturazione** è un’applicazione autonoma per creare fatture, inviarle ai clienti e gestire i pagamenti.

**Odoo Contabilità** è un’app contabile completa di tutte le funzionalità. La produttività del contabile è al centro del suo sviluppo, con funzionalità come il riconoscimento delle fatture basato sull’IA, la sincronizzazione con i conti bancari, suggerimenti intelligenti per la riconciliazione, ecc.

Vedi anche

[Odoo Tutorial: Contabilità](https://www.odoo.com/slides/accounting-19)

#### [Get startedBasic concepts of accounting and initial setup of your accounting ](accounting/get_started.html)#### [TaxesTaxes, fiscal positions, and integrations ](accounting/taxes.html)#### [Customer invoicesCustomer invoices, payment terms, and electronic invoicing ](accounting/customer_invoices.html)#### [Vendor billsVendor bills, assets, and invoice digitization (OCR) ](accounting/vendor_bills.html)#### [PaymentsInvoices and bills payments (online, checks, batches) and follow-up on invoices ](accounting/payments.html)#### [Bank and cash accountsBank synchronization, reconciliation, and cash registers ](accounting/bank.html)#### [ReportingReporting, declarations, and analytic accounting ](accounting/reporting.html)

## <br>Contabilità a partita doppia¶

Odoo crea automaticamente tutte le scritture contabili sottostanti per tutte le transazioni contabili (ad esempio, fatture clienti, fatture fornitori, ordini dei punti vendita, spese, valutazioni di inventario, ecc.).

Odoo utilizza il sistema di contabilità a doppia scrittura, in cui ogni registrazione richiede una controparte corrispondente e opposta in un altro conto, con un conto addebitato e l’altro accreditato. Questo garantisce che tutte le transazioni siano registrate in modo accurato e coerente, assicurando che i conti siano sempre in equilibrio.

Vedi anche

[Foglio informativo sulla contabilità](accounting/get_started/cheat_sheet.html)

## Base di competenza e base di cassa¶

Sia la contabilità per competenza che quella per cassa sono supportate in Odoo. Questo consente di riportare i ricavi e le spese sia quando si verifica la transazione (contabilità per competenza) che quando il pagamento è effettuato o ricevuto (contabilità per cassa).

Vedi anche

Base di cassa

## Multi-azienda¶

Several companies can be managed within the same database. Each company has its [chart of accounts](accounting/get_started/chart_of_accounts.html), but it is possible to share accounts between them for scenarios in which such a configuration would be required. Users can then access several companies but only work on a single company’s accounting at a time.

Vedi anche

  * [Shared Accounts Feature](accounting/get_started/chart_of_accounts.html#coa-shared-accounts)

  * [Consolidation](accounting/get_started/consolidation.html)




## Ambiente multi-valuta¶

Un ambiente :doc:multivaluta <accounting/get_started/multi_currency> con un tasso di cambio automatizzato per facilitare le transazioni internazionali è disponibile in Odoo. Ogni transazione viene registrata nella valuta predefinita dell’azienda; per le transazioni effettuate in un’altra valuta, Odoo memorizza sia il valore nella valuta dell’azienda sia il valore nella valuta della transazione. Odoo genera utili e perdite di cambio dopo la riconciliazione delle voci di giornale.

Vedi anche

Gestione di una banca in valuta estera

## Gestione delle filiali¶

È possibile gestire più filiali grazie alle gerarchie multiaziendali. Ciò consente di registrare le scritture contabili su ogni filiale e di impostare una data di chiusura comune gestita dalla società principale.

## Standard internazionali¶

Odoo Accounting supporta più di 70 Paesi. Fornisce gli standard e i meccanismi centrali comuni a tutte le nazioni e, grazie ai moduli specifici per paese, soddisfa i requisiti locali. Esistono posizioni fiscali per affrontare le specificità regionali come il piano dei conti, le imposte o qualsiasi altro requisito.

Vedi anche

:doc:`Pacchetti di localizzazione fiscale

## Conti attivi e passivi¶

Per impostazione predefinita, esiste un unico conto per le voci di credito e uno per le voci di debito. Poiché le transazioni sono collegate ai **contatti** , è possibile eseguire un report per cliente, venditore o fornitore.

Il report **Partner Ledger** visualizza il saldo dei clienti e dei fornitori. È disponibile accedendo a :menuselezione:`Contabilità --> Reporting --> Libro mastro dei partner`.

## Rendiconto¶

I seguenti rapporti finanziari sono disponibili e aggiornati in tempo reale:

Rapporti finanziari  
---  
Estratto conto | Stato patrimoniale  
Conto economico  
Rendiconto finanziario  
Resoconto FISCALE  
Elenco vendite ES  
Verifica | Contabilità generale  
Bilancio di verifica  
Rapporto del giornale  
Rapporto Intrastat  
Registro di controllo  
Partner | Libro mastro dei partner  
Crediti scaduti  
Debito invecchiato  
Amministrazione | Analisi delle fatture  
Utili/perdite in valuta non realizzati  
Piano di ammortamento  
Spese non ammesse  
Analisi del bilancio  
Margini di prodotto  
Rapporto 1099  
  
Suggerimento

[Creare e personalizzare i rapporti](accounting/reporting/customize.html) con il motore dei rapporti di Odoo.

### Resoconto FISCALE¶

Odoo calcola tutte le transazioni contabili per lo specifico periodo fiscale e utilizza questi totali per calcolare l’obbligo fiscale.

Importante

Una volta generato il rapporto fiscale per un periodo, Odoo lo blocca e impedisce la creazione di nuove registrazioni nel libro giornale che riguardano l’IVA. Qualsiasi correzione alle fatture dei clienti o dei fornitori deve essere registrata nel periodo successivo.

Nota

A seconda della localizzazione del Paese, è possibile generare una versione XML del rapporto fiscale da caricare sulla piattaforma IVA dell’autorità fiscale competente.

## Sincronizzazione bancaria¶

Il sistema di sincronizzazione bancaria si collega direttamente al vostro istituto bancario per importare automaticamente tutte le transazioni nel vostro database. In questo modo è possibile avere una visione d’insieme del flusso di cassa senza dover accedere a un sistema bancario online o attendere gli estratti conto cartacei.

Vedi anche

:doc:`Sincronizzazione bancaria <contabilità/banca/sincronizzazione bancaria>

## Valutazione dell’inventario¶

In Odoo sono supportate sia le valutazioni periodiche (manuali) che quelle perpetue (automatizzate) dell’inventario. I metodi disponibili sono: prezzo standard, prezzo medio, LIFO e FIFO (First-In, First-Out).

Vedi anche

[Automatic inventory valuation](../inventory_and_mrp/inventory/product_management/inventory_valuation/inventory_valuation_config.html)

## Utili a nuovo¶

Gli utili a nuovo sono la parte del reddito trattenuta da un’azienda. Odoo calcola gli utili dell’anno corrente in tempo reale, quindi non è necessario alcun registro di fine anno o rollover. Il saldo del profitto e della perdita viene automaticamente riportato nel bilancio.

Vedi anche

[Foglio informativo sulla contabilità](accounting/get_started/cheat_sheet.html)

## Fiduciari¶

La modalità Società di contabilità può essere attivata andando su Contabilità ‣ Configurazione ‣ Impostazioni ‣ Modalità società di contabilità. Quando è attivata:

  * La sequenza del documento diventa modificabile su tutti i documenti;

  * Il campo Totale (tasse incluse) sembra velocizzare e controllare la codifica automatizzando la creazione di righe con il conto e le tasse giuste;

  * Data fattura e Data fattura sono precompilati quando si codifica una transazione.

  * L’opzione Codifica rapida è disponibile per le fatture dei clienti e le fatture dei fornitori.




  * [Per iniziare](accounting/get_started.html)
    * [Promemoria contabile](accounting/get_started/cheat_sheet.html)
    * [Piano dei conti](accounting/get_started/chart_of_accounts.html)
    * [Consolidamento](accounting/get_started/consolidation.html)
    * [Sistema multi valuta](accounting/get_started/multi_currency.html)
    * [Prezzo medio sulla merce resa](accounting/get_started/avg_price_valuation.html)
    * [Unità fiscali](accounting/get_started/tax_units.html)
  * [Imposte](accounting/taxes.html)
    * [Imposte per cassa](accounting/taxes/cash_basis.html)
    * [Imposte alla fonte](accounting/taxes/retention.html)
    * [Verifica numero partita IVA (VIES)](accounting/taxes/vat_verification.html)
    * [Posizioni di bilancio (mappatura fiscale e contabile)](accounting/taxes/fiscal_positions.html)
    * [Integrazione AvaTax](accounting/taxes/avatax.html)
      * [Utilizzare AvaTax](accounting/taxes/avatax/avatax_use.html)
      * [Portale Avalara (Avatax)](accounting/taxes/avatax/avalara_portal.html)
    * [Vendite a distanza intracomunitarie nell’UE](accounting/taxes/eu_distance_selling.html)
    * [Tariffe B2B (imposte escluse) e B2C (imposte incluse)](accounting/taxes/B2B_B2C.html)
  * [Fatture cliente](accounting/customer_invoices.html)
    * [Processi di fatturazione](accounting/customer_invoices/overview.html)
    * [Indirizzi di consegna e di fatturazione](accounting/customer_invoices/customer_addresses.html)
    * [Termini di pagamento e piani di rateizzazione](accounting/customer_invoices/payment_terms.html)
    * [Termini e condizioni predefiniti](accounting/customer_invoices/terms_conditions.html)
    * [Sconti di cassa e riduzioni fiscali](accounting/customer_invoices/cash_discounts.html)
    * [Note di credito e rimborsi](accounting/customer_invoices/credit_notes.html)
    * [Arrotondamento di cassa](accounting/customer_invoices/cash_rounding.html)
    * [Risconti passivi](accounting/customer_invoices/deferred_revenues.html)
    * [Fatturazione elettronica (EDI)](accounting/customer_invoices/electronic_invoicing.html)
    * [Sequenza fattura](accounting/customer_invoices/sequence.html)
    * [Posta ordinaria](accounting/customer_invoices/snailmail.html)
    * [Codici QR EPC](accounting/customer_invoices/epc_qr_code.html)
    * [Termini di resa](accounting/customer_invoices/incoterms.html)
  * [Fatture fornitore](accounting/vendor_bills.html)
    * [AI-powered document digitization](accounting/vendor_bills/invoice_digitization.html)
    * [Non-current assets and fixed assets](accounting/vendor_bills/assets.html)
    * [Deferred expenses](accounting/vendor_bills/deferred_expenses.html)
    * [Vendor bill sequence](accounting/vendor_bills/sequence.html)
  * [Pagamenti](accounting/payments.html)
    * [Online payments](accounting/payments/online.html)
      * [Install the patch to disable online invoice payment](accounting/payments/online/install_portal_patch.html)
    * [Pagamenti raggruppati](accounting/payments/batch.html)
    * [SEPA Direct Debit (SDD) customer payments](accounting/payments/batch_sdd.html)
    * [Follow-up on invoices](accounting/payments/follow_up.html)
    * [Pay with SEPA](accounting/payments/pay_sepa.html)
    * [Pay by checks](accounting/payments/pay_checks.html)
    * [Forecast future bills to pay](accounting/payments/forecast.html)
    * [Trusted accounts (send money)](accounting/payments/trusted_accounts.html)
  * [Conti bancari e di cassa](accounting/bank.html)
    * [Sincronizzazione bancaria](accounting/bank/bank_synchronization.html)
      * [Salt Edge](accounting/bank/bank_synchronization/saltedge.html)
      * [Ponto](accounting/bank/bank_synchronization/ponto.html)
      * [Abilitare la Banca](accounting/bank/bank_synchronization/enablebanking.html)
    * [Transazioni](accounting/bank/transactions.html)
    * [Riconciliazione bancaria](accounting/bank/reconciliation.html)
    * [Modelli di riconciliazione](accounting/bank/reconciliation_models.html)
    * [Trasferimenti interni](accounting/bank/internal_transfers.html)
    * [Gestire un conto bancario in una valuta straniera](accounting/bank/foreign_currency.html)
    * [Gestione dei prestiti](accounting/bank/loans.html)
  * [Rendiconto](accounting/reporting.html)
    * [Tax return (VAT declaration)](accounting/reporting/tax_returns.html)
    * [Tax carryover](accounting/reporting/tax_carryover.html)
    * [Contabilità analitica](accounting/reporting/analytic_accounting.html)
    * [Budget](accounting/reporting/budget.html)
    * [Intrastat](accounting/reporting/intrastat.html)
    * [Data inalterability check report](accounting/reporting/data_inalterability.html)
    * [Silverfin integration](accounting/reporting/silverfin.html)
    * [Custom reports](accounting/reporting/customize.html)
    * [Year-end closing](accounting/reporting/year_end.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](accounting/get_started.html "Per iniziare") |
  * [precedente](../finance.html "Finanza") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Finanza](../finance.html) »
  * Contabilità e fatturazione


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