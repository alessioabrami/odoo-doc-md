# Tariffe B2B (imposte escluse) e B2C (imposte incluse) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../customer_invoices.html "Fatture cliente") |
  * [precedente](eu_distance_selling.html "Vendite a distanza intracomunitarie nell’UE") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Tariffe B2B (imposte escluse) e B2C (imposte incluse)



# Tariffe B2B (imposte escluse) e B2C (imposte incluse)¶

Quando si lavora con i consumatori, i prezzi sono solitamente espressi con le tasse incluse nel prezzo (ad esempio, nella maggior parte degli e-commerce). Tuttavia, quando si lavora in un ambiente B2B, le aziende di solito negoziano i prezzi escludendo le imposte.

Odoo gestisce facilmente entrambi i casi d’uso, purché si registrino i prezzi sul prodotto con imposte escluse o incluse, ma non entrambe le cose insieme. Se si gestiscono tutti i prezzi solo con imposte incluse (o escluse), si può comunque fare facilmente un ordine di vendita con un prezzo con imposte escluse (o incluse): è facile.

Questa documentazione riguarda solo il caso d’uso specifico in cui è necessario avere due riferimenti per il prezzo (imposte incluse o escluse), per lo stesso prodotto. La ragione della complessità è che non esiste una relazione simmetrica tra prezzi inclusi e prezzi esclusi, come mostrato in questo caso d’uso, in Belgio con un’imposta del 21%:

  * Il tuo e-commerce ha un prodotto a **10 € (imposte incluse)**

  * Ciò significherebbe **8,26 € (imposte escluse)** e una **imposta di 1,74 €**.




Ma per lo stesso caso d’uso, se si registra il prezzo senza imposte nella scheda prodotto (8,26 €), si ottiene un prezzo con tasse incluse di 9,99 €, perché:

  * **8,26 € * 1,21 = 9,99 €**




Quindi, a seconda di come si registrano i prezzi nel modulo del prodotto, si avranno risultati diversi per il prezzo imposte incluse e per il prezzo imposte escluse:

  * Imposte escluse: **8,26 € e 10,00 €**

  * Imposte incluse: **8,26 € e 9,99 €**




Nota

Se si acquistano 100 pezzi a 10 € imposte incluse, la situazione diventa ancora più complicata. Si otterrà: **1.000 € (imposte incluse) = 826,45 € (prezzo) + 173,55 € (imposte)** Che è molto diverso da un prezzo per pezzo di 8,26 € tasse escluse.

Questa documentazione spiega come gestire il caso d’uso molto specifico in cui è necessario gestire i due prezzi (imposte escluse e incluse) sul modulo del prodotto all’interno della stessa azienda.

Nota

In termini finanziari, non avrai più entrate vendendo il tuo prodotto a 10 € invece che a 9,99 € (con un’imposta del 21%), perché le entrate saranno esattamente le stesse a 9,99 €, solo che l’imposta è superiore di 0,01 €. Quindi, se gestisci un e-commerce in Belgio, fai un favore ai clienti e fissa il prezzo a 9,99 € invece che a 10 €. Nota che questo non si applica a 20 € o 30 €, o ad altre aliquote fiscali, o a una quantità >1\. Inoltre, farai un favore a te stesso, poiché potrai gestire tutto al netto delle imposte, il che è meno soggetto a errori e più facile per gli addetti alle vendite.

## Configurazione¶

### Introduzione¶

Il modo migliore per evitare questa complessità è scegliere un solo modo di gestire i prezzi e attenersi a esso: prezzo senza imposte o prezzo con imposte incluse. Definisci quale sia quello predefinito memorizzato nel modulo del prodotto (sulla tassa predefinita relativa al prodotto) e lascia che Odoo calcoli l’altro automaticamente, in base al listino prezzi e alla posizione fiscale. Negozia i contratti con i clienti di conseguenza. Questo funziona perfettamente e non è necessario effettuare alcuna configurazione specifica.

Se non puoi farlo e se davvero negozi alcuni prezzi con imposte escluse e, per altri clienti, altri prezzi con imposte incluse, devi:

  1. memorizzare sempre il prezzo predefinito **imposte escluse** sul modulo prodotto e applicare una tassa (prezzo escluso sul modulo prodotto)

  2. creare un listino prezzi con prezzi in **imposte incluse** , per clienti specifici

  3. creare una posizione di bilancio che commuta l’imposta esclusa in un’imposta inclusa

  4. assegnare sia il listino prezzi che la posizione fiscale ai clienti che desiderano beneficiare di tale listino e posizione fiscale.




Ai fini di questa documentazione, utilizzeremo il caso d’uso sopra descritto:

  * il prezzo di vendita predefinito del prodotto è di 8,26 € imposte escluse

  * ma vogliamo venderlo a 10 €, imposte incluse, nei nostri negozi o nell’e-commerce.




### E-commerce¶

Se si utilizzano solo prezzi B2C o B2B sul proprio sito web, è sufficiente selezionare l’impostazione appropriata nelle impostazioni dell’applicazione **Sito web**.

Se hai prezzi sia B2B che B2C su un unico sito web, segui queste istruzioni:

  1. Attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e accedi alle Impostazioni generali ‣ Utenti e aziende ‣ Gruppi.

  2. Apri `Funzioni tecniche/Visualizzazione imposte B2B` oppure `Funzioni tecniche/Visualizzazione imposte B2C`.

  3. Nella scheda Utenti, aggiungi gli utenti che richiedono accesso al tipo di prezzo. Aggiungi utenti B2C nel gruppo B2C e utenti B2B nel gruppo B2B.




### Configurare i prodotti¶

L’impostazione predefinita per la tua azienda dovrebbe essere imposte escluse. Si tratta della configurazione predefinita ma puoi controllare la **Imposta di vendita predefinita** dal menu Configurazione ‣ Impostazioni dell’applicazione Contabilità.

In seguito, puoi creare un listino prezzi **B2C**. Puoi attivare la funzionalità listino prezzi per cliente dal menu: Configurazione ‣ Impostazioni dell’applicazione Vendite. Scegli l’opzione **vari prezzi per segmento cliente**.

Una volta fatto, crea un listino prezzi B2C dal menu Configurazione ‣ Listini prezzi. Per evitare confusioni, è bene rinominare il listino prezzi predefinito in B2B.

Successivamente, crea un prodotto che costa 8,26 €, con un’imposta del 21% (che non è inclusa nel prezzo) e configura un prezzo di 10 € per il prodotto per clienti B2C dal menu Vendite ‣ Prodotti dell’applicazione Vendite:

### Configurare una posizione di bilancio B2C¶

Dall’applicazione Contabilità, crea una posizione di bilancio B2C dal menu Configurazione ‣ Posizioni di bilancio. Questa posizione di bilancio dovrebbe mappare l’IVA al 21% (imposta esclusa dal prezzo) con un’IVA pari al 21% (imposta inclusa nel prezzo).

## Fare un test creando un preventivo¶

Crea un preventivo dall’applicazione Vendite, utilizzando il menu Vendite ‣ Preventivi. Dovresti ottenere il seguente risultato: 8,26 € + 1,73 € = 9,99 €.

Successivamente, crea un preventivo ma **modifica il listino prezzi in B2C e la posizione fiscale in B2C** sul preventivo stesso, prima di aggiungere il prodotto. Dovresti ottenere il risultato atteso, ovvero un prezzo totale di 10 € per il cliente: 8,26 € + 1,74 € = 10,00 €.

Questo è il comportamento atteso per un cliente del tuo negozio.

## Evitare di modificare ogni singolo ordine di vendita¶

Se negozi un contratto con un cliente, sia che si tratti di imposte incluse che imposte escluse, è possibile configurare il listino prezzi e la posizione di bilancio nella scheda cliente in modo che venga applicata automaticamente a ogni vendita del cliente stesso.

Il listino prezzi si trova nella scheda **Vendite e acquisti** del modulo cliente, mentre la posizione di bilancio si trova nella scheda contabilità.

Nota che ciò è soggetto a errori: se imposti una posizione di bilancio con tasse incluse nei prezzi, ma utilizzi un listino prezzi che non è incluso, è possibile che vengano calcolati prezzi errati. Per questo motivo, di solito consigliamo alle aziende di lavorare con un solo riferimento di prezzo.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/taxes/B2B_B2C.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../customer_invoices.html "Fatture cliente") |
  * [precedente](eu_distance_selling.html "Vendite a distanza intracomunitarie nell’UE") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Tariffe B2B (imposte escluse) e B2C (imposte incluse)


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
  *[API]: application programming interface
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
  *[AVCO]: Average Cost Valuation
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