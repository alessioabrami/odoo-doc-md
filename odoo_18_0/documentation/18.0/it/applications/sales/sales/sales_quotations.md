# Preventivi di vendita — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales_quotations/create_quotations.html "Creare preventivi") |
  * [precedente](../sales.html "Vendite") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Preventivi di vendita



# Preventivi di vendita¶

Un _preventivo di vendita_ o preventivo è un documento inviato a un cliente che delinea i costi e i termini stimati per beni e servizi. Una volta accettato, un preventivo può essere convertito in un ordine di vendita, che serve come accordo finale prima della consegna e della fatturazione.

## Panoramica flusso di vendita¶

I preventivi fanno parte di un flusso di vendita più ampio che collega le diverse fasi di interazione con il cliente, dall’interesse iniziale al pagamento.

Un flusso tipico segue le fasi elencate di seguito:

  1. _Preventivo_ : una proposta inviata al cliente con dettagli relativi al prodotto e costi.

  2. _Ordine di vendita_ : viene creato automaticamente quando il cliente accetta il preventivo confermando la vendita.

  3. _Consegna_ (se applicabile): i prodotti vengono spediti o vengono erogati dei servizi.

  4. _Fattura_ : la fattura finale viene emessa in base all’ordine di vendita oppure ai prodotti/servizi consegnati.

  5. _Pagamento_ : il cliente salda la fattura così da completare il ciclo di vendita.




Questo flusso aiuta le azienda a monitorare l’intero ciclo di una vendita conservando le informazioni importanti nelle varie applicazioni.

In Odoo, i preventivi vengono configurati nell’app _Vendite_. Inoltre, possono essere creati da altre app come parte del flusso di vendita:

  * **CRM** : [converti opportunità](../crm/acquire_leads/send_quotes.html) in preventivi per effettuare il follow-up di potenziali affari.

  * **Helpdesk** : [genera preventivi dai ticket](../../services/helpdesk/advanced/after_sales.html) se offri servizi a pagamento o prodotti.

  * **Abbonamenti** : [offri servizi ricorrenti](../subscriptions.html) prima di avviare un ciclo di fatturazione automatica.




#### [Create quotationsCreate, configure, and send quotations to customers. ](sales_quotations/create_quotations.html)#### [Quotation templatesConfigure and use quotation templates to send tailor-fit quotations at a quicker pace. ](sales_quotations/quote_template.html)#### [Optional productsOffer useful and related products to customers to increase sales. ](sales_quotations/optional_products.html)#### [Online signatures for order confirmationsCustomers have the ability to confirm orders via online signatures, directly on sales orders. ](sales_quotations/get_signature_to_validate.html)#### [Online payment order confirmationCustomers have the ability to confirm orders via online payment, directly on sales orders. ](sales_quotations/get_paid_to_validate.html)#### [Quotation DeadlinesSet deadlines on quotations to encourage customers to act in a timely manner when closing business deals. ](sales_quotations/deadline.html)#### [Deliver orders and invoices to different addressesSpecify separate customer delivery and invoicing addresses on quotations. ](sales_quotations/different_addresses.html)#### [Product variants on quotations and sales ordersAdd product variants to sales orders to provide additional options for single products. ](sales_quotations/orders_and_variants.html)#### [PDF quote builderAdd custom PDF files to quotations to elevate the document’s headers and designs. ](sales_quotations/pdf_quote_builder.html)

## Preventivi di vendita nelle trattative commerciali¶

I preventivi di vendita rappresentano una fase fondamentale del processo di vendita, in quanto colmano il divario tra la richiesta iniziale di beni e servizi da parte del cliente e l’accordo contrattuale finale per il pagamento e la consegna. Il preventivo fornisce anche trasparenza sui prezzi, aiutando entrambe le parti a negoziare e finalizzare i termini prima di prendere un impegno.

I preventivi di vendita svolgono un ruolo cruciale nelle transazioni commerciali, in quanto definiscono l’entità e il costo di ciò che viene venduto al cliente finale, stabiliscono aspettative chiare su prezzi, consegna, tasse e termini di pagamento e forniscono una fase documentata in cui l’accordo commerciale può essere negoziato prima di essere concordato.

## Elementi principali di un preventivo di vendita¶

Un preventivo ben strutturato comprende:

  * numero e data del preventivo. Un identificativo unico per il monitoraggio e per avere un riferimento così come le [date di emissione e di scadenza](sales_quotations/deadline.html). Nell’app **Vendite** di Odoo, il numero di preventivo viene assegnato secondo una nomenclatura standard una volta confermato.

  * Informazioni cliente: il nome e le informazioni di contatto del cliente così come [l’indirizzo di fatturazione e consegna](sales_quotations/different_addresses.html).

  * Prodotti e servizi: elenco dettagliato degli articoli da acquistare, con quantità, specifiche (se necessario) e prezzo unitario.

  * Termini di pagamento e [listini prezzi](products_prices/prices/pricing.html): accordi e regole configurati per la determinazione dei prezzi e il pagamento di questo particolare preventivo di vendita.

  * Prezzo speciale: [sconti e prezzi promozionali](products_prices/prices/pricing.html) per aggiornare e/o modificare singole righe del prodotto.

  * Costo totale e valuta: totali riassuntivi dei prezzi dei prodotti o dei servizi e delle spedizioni, comprese le relative tasse.




Nell’app Odoo **Vendite** , i preventivi possono includere dettagli e configurazioni aggiuntive che forniscono più informazioni come [modelli di preventivo](sales_quotations/quote_template.html), [piani di abbonamento](../subscriptions.html) e [nome del referente del team di vendita](sales_quotations/create_quotations.html).

  * [Creare preventivi](sales_quotations/create_quotations.html)
  * [Modelli preventivo](sales_quotations/quote_template.html)
  * [Prodotti opzionali](sales_quotations/optional_products.html)
  * [Firme online per confermare gli ordini](sales_quotations/get_signature_to_validate.html)
  * [Conferma ordine tramite pagamento online](sales_quotations/get_paid_to_validate.html)
  * [Date di scadenza per i preventivi](sales_quotations/deadline.html)
  * [Consegne e fatture a indirizzi diversi](sales_quotations/different_addresses.html)
  * [Varianti prodotto su preventivi e ordini di vendita](sales_quotations/orders_and_variants.html)
  * [Creazione preventivi in PDF](sales_quotations/pdf_quote_builder.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/sales/sales_quotations.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales_quotations/create_quotations.html "Creare preventivi") |
  * [precedente](../sales.html "Vendite") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Vendite](../../sales.html) »
  * [Vendite](../sales.html) »
  * Preventivi di vendita


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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
  *[LIFO]: Last In, First Out
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