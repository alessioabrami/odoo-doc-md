# Fatture basate su quantità ordinate o consegnate — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](down_payment.html "Acconti") |
  * [precedente](../invoicing.html "Invoicing Method") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su quantità ordinate o consegnate



# Fatture basate su quantità ordinate o consegnate¶

Politiche aziendali diverse potrebbero richiedere opzioni di fatturazione differenti:

  * La regola _Fatturare ciò che viene ordinato_ viene usata come modalità predefinita in Odoo _Vendite_ , il che significa che i clienti vengono fatturati una volta confermato l’ordine di vendita.

  * Con la regola _Fatturare ciò che viene consegnato_ le fatture vengono emesse una volta effettuata la consegna. Questa regola viene spesso usata per aziende che vendono materiali, liquidi o cibo in grandi quantità. In questi casi, La quantità ordinata potrebbe differire leggermente dalla quantità consegnata così da preferire la fatturazione della quantità effettivamente consegnata.




Avere più opzioni di fatturazione permette di avere maggiore flessibilità.

## Funzionalità politica di fatturazione¶

Per attivare le funzionalità di cui hai bisogno, accedi al modulo Vendite ‣ Configurazione ‣ Impostazioni e sotto la sezione Fatturazione, selezione una regola per la politica di fatturazione: Fatturare ciò che viene ordinato oppure Fatturare ciò che viene consegnato.

Importante

Se scegli la regola Fatturare ciò che viene consegnato, **non** è possibile attivare la funzionalità Fattura automatica che genera fatture automaticamente al momento della conferma di un pagamento online.

## Politica di fatturazione su modulo prodotto¶

Su qualsiasi pagina prodotto, attraverso l’app Vendite ‣ Prodotti ‣ Dashboard prodotti, trova l’opzione Politica di fatturazione nella scheda Informazioni generali. È possibile modificarla manualmente usando il menu a discesa.

## Impatto sui flussi di vendita¶

Nel modulo Odoo _Vendite_ , un flusso di vendita di base inizia dalla creazione di un preventivo. In seguito, il preventivo viene inviato al cliente. Successivamente, deve essere confermato e il preventivo diventa un ordine di vendita. Infine, verrà creata una fattura.

Le regole per la politica di fatturazione impattano il flusso di vendita in due modi distinti:

  * Fatturare ciò che viene ordinato: nessun impatto sul flusso di vendita di base. Una fattura viene creata non appena viene confermata la vendita.

  * Fatturare ciò che viene consegnato: impatto minore sul flusso di vendita perché la quantità consegnata deve essere aggiunta manualmente all’ordine di vendita. In alternativa, è possibile installare l’app _Magazzino_ e utilizzarla per confermare la quantità consegnata prima di creare una fattura con l’app _Vendite_.




Avvertimento

Se un utente prova a creare una fattura senza convalidare la quantità consegnata, apparirà il seguente messaggio di errore: Nessuna riga fatturabile. Se un prodotto ha una politica di fatturazione basata sulla quantità consegnata, controllare che la quantità stessa sia stata consegnata.

Nota

Una volta confermato un preventivo e lo stato passa da Preventivo inviato a Ordine di vendita, le quantità consegnate e fatturate sono disponibili per la visualizzazione direttamente dall’ordine di vendita, indipendentemente dalla regola di fatturazione applicata.

Odoo aggiunge automaticamente le quantità alla fattura, sia quelle Consegnate che Fatturate, anche se si tratta di una consegna parziale, una volta confermato il preventivo.

Infine, esistono alcune opzioni per creare una fattura: Fattura regolare, Acconto (percentuale) o Acconto (importo fisso).

Vedi anche

Assicurati di consultare la documentazione che spiega come funzionano gli acconti per scoprire di più: [Acconti](down_payment.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/invoicing/invoicing_policy.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](down_payment.html "Acconti") |
  * [precedente](../invoicing.html "Invoicing Method") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Fatture basate su quantità ordinate o consegnate


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
  *[NSSL]: Non-Shopee Supported Logistics