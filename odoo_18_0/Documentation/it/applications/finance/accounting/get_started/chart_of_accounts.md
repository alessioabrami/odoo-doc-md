# Piano dei conti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](consolidation.html "Consolidamento") |
  * [precedente](cheat_sheet.html "Promemoria contabile") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Piano dei conti



# Piano dei conti¶

Il **piano dei conti** è l’elenco di tutti i conti utilizzati per registrare transazioni finanziarie nel libro mastro di un business. È possibile accedervi aprendo l’app Contabilità ‣ Configurazione ‣ Piano dei conti.

Quando carichi il tuo piano dei conti, è possibile ordinare i conti per Codice, Nome conto oppure per Tipo. Tuttavia, sono disponibili altre opzioni nel menu a discesa.

## Configurare un conto¶

Il Paese selezionato durante la creazione del database (o durante l’aggiunta di un’ulteriore azienda al database) determina quale [pacchetto di localizzazione fiscale](../../fiscal_localizations.html) verrà installato per impostazione predefinita. Questo pacchetto include un piano dei conti standard già configurato secondo le normative nazionali. È possibile utilizzarlo direttamente o impostarlo in base alle esigenze della propria azienda.

Per creare un nuovo conto, apri l’app Contabilità ‣ Configurazione ‣ Piano dei conti, fai clic su Crea e riempi (almeno) i campi richiesti (Codice, Nome conto, Tipo).

Avvertimento

Non è possibile modificare la **localizzazione fiscale** di un’azienda una volta aggiunta la prima registrazione contabile.

### Codice e nome¶

Ogni conto è identificato da un Codice e Nome, che indicano anche lo scopo del conto.

### Tipo¶

Configurare un **tipo di conto** in modo corretto è essenziale per vari motivi:

  * ottenere informazioni sulla portata del conto

  * generare rendiconti legali e finanziari specifici per ogni Paese

  * impostare regole per la chiusura di un anno fiscale

  * generare registrazioni di apertura.




Per configurare un tipo di conto, apri il selettore a tendina del campo Tipo e seleziona il tipo corrispondente dall’elenco:

Resoconto | Categoria | Tipi conto  
---|---|---  
Stato patrimoniale | Cespiti | Credito  
Banca e cassa  
Attività correnti  
Attività non correnti  
Risconti attivi  
Immobilizzazioni  
Passività | Debito  
Carta di credito  
Passività correnti  
Passività non correnti  
Patrimonio netto | Patrimonio netto  
Utili di esercizio  
Conto economico | Ricavi | Ricavi  
Altri ricavi  
Spesa | Spesa  
Ammortamenti  
Costo del venduto  
Altro | Altro | Fuori bilancio  
  
#### Cespiti¶

Alcuni **tipi di conto** possono **automatizzare** la creazione di registrazioni di [asset](../vendor_bills/assets.html#assets-automation). Per **automatizzare** le registrazioni, fai clic su Vista sulla riga di un conto e apri la scheda Automazione.

Nella scheda Automazione, puoi scegliere tra tre opzioni:

  1. No: valore predefinito, non accade nulla

  2. Crea in bozza: ogni volta che una transazione viene registrata sul conto, viene creata una bozza di registrazione, ma non viene convalidata. È necessario compilare il modulo corrispondente

  3. Crea e convalida: devi selezionare un modello di risconto attivo. Quando una transazione viene registrata sul conto, una registrazione viene creata e convalidata immediatamente




### Imposte predefinite¶

Nel menu Vista di un conto, scegli una **imposta predefinita** da applicare quando il conto viene scelto per la vendita o per l’acquisto di un prodotto.

### Etichette¶

Alcuni rendiconti contabili richiedono **tag** da configurare sui conti rilevanti. Per aggiungere un tag, nel menu Vista, fai clic sul campo Tag e selezionane uno esistente oppure Creane uno nuovo.

### Gruppi del conto¶

I **gruppi conto** sono utili per elencare più conti come _conti secondari_ di un conto più grande e quindi per consolidare rendiconti come il **BIlancio di verifica**. Per impostazione predefinita, i gruppi vengono gestiti automaticamente in base al codice del gruppo. Ad esempio, il nuovo conto `131200` sarà parte del gruppo `131000`. È possibile attribuire un gruppo specifico a un conto nel campo Gruppo appartenente alla sezione Vista.

#### Creare gruppi conto manualmente¶

Nota

Gli utenti regolari non dovrebbero avere bisogno di creare gruppi conto manualmente. La seguente sezione è destinata solo a casi d’uso particolari e avanzati.

Per creare un nuovo gruppo conto, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e apri l’app Contabilità ‣ Configurazione ‣ Gruppi conto. Qui, crea un nuovo gruppo e inserisci il nome, codice prefisso e l’azienda per cui questo gruppo conto dovrebbe essere disponibile. Nota che è necessario inserire lo stesso codice prefisso sia nel campo Da che nel campo a.

Per visualizzare il rendiconto **Bilancio di verifica** con i tuoi gruppi conto, vai su Contabilità ‣ Rendicontazione ‣ Bilancio di verifica, poi apri il menu Opzioni e seleziona Gerarchia e totali parziali.

### Consentire la riconciliazione¶

Alcuni conti, come quelli creati per registrare le transazioni di un metodo di pagamento, possono essere utilizzati per la riconciliazione delle registrazioni contabili.

Ad esempio, una fattura pagata con una carta di credito può essere contrassegnata come pagata se riconciliata con il proprio pagamento. Di conseguenza, il conto utilizzato per registrare i pagamenti tramite carta di credito deve essere abilitato per la **riconciliazione**.

Per farlo, seleziona la casella Consenti riconciliazione nelle impostazioni del conto stesso e Salva la modifica. Oppure attiva il pulsante dalla vista del piano dei conti.

### Shared Accounts¶

The **Shared Accounts** feature allows the creation of a single account for a specific purpose and sharing it between multiple companies. It is especially useful for multi-company environments where a similar account might be used across different companies.

### Non attivo¶

Non è possibile eliminare un conto una volta che una transazione è stata registrata in esso. Puoi disattivarne l’utilizzo utilizzando la funzionalità **Non attivo** : spunta la casella Non attivo nelle impostazioni del conto e Salva.

Vedi anche

  * [Promemoria contabile](cheat_sheet.html)

  * [Non-current assets and fixed assets](../vendor_bills/assets.html)

  * [Deferred expenses](../vendor_bills/deferred_expenses.html)

  * [Risconti passivi](../customer_invoices/deferred_revenues.html)

  * [Fiscal localizations](../../fiscal_localizations.html)

  * [Tutorial Odoo: Piano dei conti](https://www.odoo.com/slides/slide/chart-of-accounts-1630)

  * [Tutorial Odoo: Aggiornare il piano dei conti](https://www.odoo.com/slides/slide/update-your-chart-of-accounts-1658)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/get_started/chart_of_accounts.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](consolidation.html "Consolidamento") |
  * [precedente](cheat_sheet.html "Promemoria contabile") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Piano dei conti


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