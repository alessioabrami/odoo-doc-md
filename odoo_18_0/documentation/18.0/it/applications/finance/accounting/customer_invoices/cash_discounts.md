# Sconti di cassa e riduzioni fiscali — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](credit_notes.html "Note di credito e rimborsi") |
  * [precedente](terms_conditions.html "Termini e condizioni predefiniti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Sconti di cassa e riduzioni fiscali



# Sconti di cassa e riduzioni fiscali¶

**Gli sconti di cassa** sono riduzioni dell’importo che un cliente deve pagare per i beni o i servizi offerti come incentivo per il pagamento tempestivo della fattura. Questi sconti sono in genere una percentuale dell’importo totale della fattura e vengono applicati se il cliente paga entro un determinato periodo di tempo. Gli sconti possono aiutare un’azienda a mantenere un flusso di cassa costante.

Example

Il 1° gennaio emetti una fattura di 100 €. Il pagamento completo deve essere effettuato entro 30 giorni e offri uno sconto del 2% se il cliente paga entro sette giorni.

Il cliente può pagare 98 € fino all’8 gennaio. Dopo tale data, dovrà pagare 100 € entro il 31 gennaio.

È possibile applicare anche una riduzione fiscale in base al Paese o alla regione.

Vedi anche

  * [Termini di pagamento e piani di rateizzazione](payment_terms.html)

  * [Pagamenti](../payments.html)




## Configurazione¶

Per garantire sconti ai clienti, prima è necessario controllare i conti utili e perdite. Successivamente, configura i termini di pagamento e aggiungi uno sconto spuntando la casella Sconto anticipato e completa i campi relativi a percentuale di sconto, giorni di sconto e riduzione fiscale.

### Sconto di cassa conti utili e perdite¶

Con lo sconto di cassa, l’importo guadagnato dipende dal fatto che il cliente benefici o meno dello sconto di cassa. Questo comporta inevitabilmente guadagni e perdite, che vengono registrati nei conti predefiniti.

Per modificare i conti, apri l’app Contabilità ‣ Configurazione ‣ Impostazioni e nella sezione Conti predefiniti, scegli i conti che vuoi utilizzare per il Conto utili con sconto e per il Conto perdite con sconto.

### Termini di pagamento¶

Gli sconti di cassa vengono definiti nei [termini di pagamento](payment_terms.html). Configurali come preferisci dal menu Contabilità ‣ Configurazione ‣ Termini di pagamento e assicurati di inserire la percentuale di sconto, i giorni di sconto e la riduzione fiscale nei campi corrispondenti.

### Riduzioni fiscali¶

A seconda del Paese o della regione, l’importo di base utilizzato per calcolare l’imposta può variare, il che può portare a una **riduzione fiscale**. Poiché le riduzioni fiscali sono impostate su singoli termini di pagamento, ogni termine può utilizzare una riduzione fiscale specifica.

Per configurare le modalità di applicazione della riduzione fiscale, accedi a un termine di pagamento con la casella di controllo Sconto anticipato attivata e seleziona una delle tre opzioni seguenti:

  * Sempre (su fattura)
    

L’imposta viene sempre ridotta. L’importo base utilizzato per calcolare l’imposta è l’importo scontato, indipendentemente dal fatto che il cliente benefici o meno dello sconto.

  * Su pagamento anticipato
    

L’imposta viene ridotta solo se il cliente paga in anticipo. L’importo di base utilizzato per calcolare l’imposta è lo stesso della vendita: se il cliente beneficia della riduzione, allora l’imposta viene ridotta. Ciò significa che, a seconda del cliente, l’importo dell’imposta può variare dopo l’emissione della fattura.

  * Mai
    

L’imposta non viene mai ridotta. L’importo di base utilizzato per calcolare l’imposta è l’intero importo, indipendentemente dal fatto che il cliente benefici o meno dello sconto.




Example

Il 1° gennaio emetti una fattura di 100 € (imposte escluse), con un’aliquota fiscale del 21%. Il pagamento completo deve essere effettuato entro 30 giorni e offri uno sconto del 2% se il cliente paga entro sette giorni.

Always (upon invoice)On early paymentNever

Data di scadenza | Importo totale dovuto | Calcolo  
---|---|---  
8 gennaio | 118,58 € | 98 € + (21% di 98 €)  
31 gennaio | 120,58 € | 100 € + (21% di 98 €)  
  
Data di scadenza | Importo totale dovuto | Calcolo  
---|---|---  
8 gennaio | 118,58 € | 98 € + (21% di 98 €)  
31 gennaio | 121,00 € | 100 € + (21% di 100 €)  
  
Data di scadenza | Importo totale dovuto | Calcolo  
---|---|---  
8 gennaio | 119,00 € | 98 € + (21% di 100 €)  
31 gennaio | 121,00 € | 100 € + (21% di 100 €)  
  
Nota

  * Le [Griglie imposta](../reporting/tax_returns.html#tax-returns-tax-grids), utilizzate per il resoconto fiscale, vengono calcolate correttamente a seconda del tipo di riduzione fiscale configurato.

  * Il **tipo di sconto o riduzione fiscale** potrebbe già essere correttamente preconfigurato in base al [pacchetto di localizzazione fiscale](../../fiscal_localizations.html#fiscal-localizations-packages).




## Applicare uno sconto di cassa alla fattura di un cliente¶

È possibile applicare uno sconto alla fattura di un cliente selezionando i termini di pagamento creati. Odoo calcola automaticamente gli importi corretti, gli importi delle imposte, le date di scadenza e i record contabili.

Nella scheda Movimenti contabili, puoi visualizzare i dettagli dello sconto facendo clic sul pulsante «toggle» per poi aggiungere le colonne Data sconto e Importo sconto.

L’importo dello sconto e la data di scadenza vengono visualizzati anche nel resoconto della fattura generato e inviato al cliente se l’opzione Mostra date versamento è selezionata nei termini di pagamento.

### Riconciliazione pagamenti¶

Quando registri un [pagamento](../payments.html) o [riconcili delle transazioni bancarie](../bank/reconciliation.html), Odoo prende in considerazione la data del pagamento del cliente per determinare se il cliente può beneficiare o meno dello sconto di cassa.

Nota

Se il cliente paga l’importo dello sconto _dopo_ la data dello sconto, puoi sempre decidere di contrassegnare la fattura come completamente pagata con uno storno o come parzialmente pagata.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/customer_invoices/cash_discounts.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](credit_notes.html "Note di credito e rimborsi") |
  * [precedente](terms_conditions.html "Termini e condizioni predefiniti") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Sconti di cassa e riduzioni fiscali


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