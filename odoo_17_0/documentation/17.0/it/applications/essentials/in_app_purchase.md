# Acquisti in-app (IAP) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](keyboard_shortcuts.html "Scelte rapide da tastiera") |
  * [precedente](export_import_data.html "Esportare e importare dati") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Acquisti in-app (IAP)



# Acquisti in-app (IAP)¶

Gli acquisti in-app (IAP) sono servizi opzionali che potenziano i database Odoo. Ogni servizio fornisce le proprie caratteristiche e funzionalità specifiche. Nel catalogo [Odoo IAP](https://iap.odoo.com/iap/all-in-app-services) è disponibile un elenco completo di servizi.

Example

Il servizio SMS invia messaggi di testo ai contatti direttamente dal database e il servizio di Digitalizzazione dei documenti digitalizza le fatture fornitore scansionate o in formato PDF, le note spese e CV tramite il riconoscimento ottico dei caratteri (OCR) e l’intelligenza artificiale (IA).

I servizi IAP **non** devono essere configurati prima dell’utilizzo. Gli utenti di Odoo possono semplicemente fare clic sul servizio nell’app per attivarlo. Tuttavia, ogni servizio richiede dei crediti prepagati e quando finiscono gli utenti **devono** comprarne di più per continuare ad utilizzarlo.

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima di scegliere se acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un “app gratuita.

## Servizi IAP¶

I servizi IAP sono forniti da Odoo così come da terze parti e e hanno una vasta gamma d’impiego.

I seguenti servizi IAP sono offerti da Odoo:

  * Digitalizzazione dei documenti: digitalizza fatture fornitore scansionate o in formato PDF, note spese e CV grazie all’OCR e all’IA.

  * Autocompletamento partner: popola automaticamente i record dei contatti con dati aziendali.

  * SMS: invia messaggi di testo SMS ai contatti direttamente dal database.

  * Generazione lead: genera lead in base ad un insieme di criteri e converti i visitatori web in lead e opportunità di qualità.

  * Posta ordinaria: invia fatture cliente e rendiconti di follow-up via posta, in tutto il mondo.

  * Identificazione firma itsme®️: chiedi ai firmatari dei documenti in Odoo _Firma_ di fornire i propri dati utilizzando la piattaforma _itsme®_ disponibile in Belgio e Paesi Bassi.




Per maggiori informazioni su ogni servizio disponibile attualmente (offerti da vari sviluppatori) consulta il [Catalogo Odoo IAP](https://iap.odoo.com/iap/all-in-app-services).

### Utilizzare servizi IAP¶

I servizi IAP vengono integrati automaticamente con Odoo e **non** è necessario impostazioni. Per utilizzare un servizio, interagisci con esso nel database.

Example

Il seguente flusso si focalizza sul servizio IAP _SMS_ utilizzato dal record di un contatto.

Questo può essere fatto cliccando sull’icona :guilabel:`📱 SMS`all’interno del database.

Di seguito, viene illustrato uno dei modi per utilizzare il servizio IAP _SMS_ con Odoo:

Per prima cosa, apri l”Applicazione contatti e fai clic su un contatto che presenta un numero di telefono nel campo Telefono o Cellulare del modulo.

In seguito, trova l’icona 📱 SMS che appare alla destra dei campi Telefono o Cellulare. Fai clic sull’icona 📱 SMS e apaprirà la finestra pop-up Invia messaggio SMS

Digita un messaggio nel campo Messaggio della finestra pop-up. In seguito, fai clic sul pulsante Invia SMS. Odoo invia il messaggio, tramite SMS, al contatto e registra quello che è stato inviato nel _chatter_ del modulo contatto.

Una volta inviato il messaggio SMS, i crediti prepagati per il servizio IAP _SMS_ vengono dedotti automaticamente dai crediti esistenti. Se non ci sono abbastanza crediti per inviare il messaggio, Odoo invita l’utente a comprarne di più.

Vedi anche

Per maggiori informazioni su come usare i vari servizi IAP e per maggiori istruzioni dettagliate relative alla funzionalità SMS in Odoo, consulta la seguente documentazione:

  * [Estrazione lead](../sales/crm/acquire_leads/lead_mining.html)

  * [Arricchisci la tua base di contatti con l’Autocompletamento partner](../sales/crm/optimize/partner_autocomplete.html)

  * [SMS Marketing](../marketing/sms_marketing.html)




## Crediti IAP¶

Ogni volta che utilizzi un servizio IAP, i crediti prepagati per il servizio vengono consumati. Odoo suggerisce l’acquisto di più crediti quando non ve ne sono abbastanza per continuare ad utilizzare il servizio. È possibile configurare avvisi e-mail quando i crediti sono pochi.

I crediti vengono acquistati in _Pacchetti_ dal [Catalogo Odoo IAP](https://iap.odoo.com/iap/all-in-app-services) e il prezzo viene specificato per ogni servizio.

Example

Per il [servizio SMS](https://iap.odoo.com/iap/in-app-services/1) sono disponibili quattro pacchetti:

  * Starter Pack: 10 crediti

  * Standard Pack: 100 crediti

  * Advanced Pack: 500 crediti

  * Expert Pack: 1.000 crediti




Il numero di crediti spesi dipende dalla lunghezza dell’SMS e dal Paese di destinazione.

Per maggiori informazioni, fai riferimento alla documentazione [Tariffe SMS e FAQ](../marketing/sms_marketing/pricing_and_faq.html).

### Acquista crediti¶

Se non disponi di crediti a sufficienza per eseguire un’attività, il database ti suggerisce automaticamente di acquistare più crediti.

Gli utenti possono verificare il saldo corrente dei crediti per ogni servizio e comprarne di nuovi manualmente andando su App Impostazioni ‣ Sezione contatti e tra le impostazioni Odoo IAP troverai Visualizza servizi.

Avrai così accesso alla pagina Servizi IAP con l’elenco dei vari servizi IAP attivati per il databse. Da qui, fai clic su un servizio IAP per aprire la pagina Informazioni account correlata dalla quale potrai acquistare crediti aggiuntivi.

#### Acquistare crediti manualmente¶

Per acquistare crediti manualmente segui questi step:

Per prima cosa, apri l”applicazione Impostazioni e scrivi `IAP` nella barra Cerca…. In alternativa, gli utenti possono recarsi nella sezione Contatti, Odoo IAP e fare clic su Visualizza servizi.

Avrai così accesso alla pagina Account IAP con l’elenco dei vari servizi IAP attivati per il databse. Da qui, fai clic su un servizio IAP per aprire la pagina Informazioni account correlata dalla quale potrai acquistare crediti aggiuntivi.

Nella pagina Informazioni account, fai clic sul pulsante Acquista crediti. In seguito, avrai accesso alla pagina Acquista crediti per (Account IAP). Da qui, fai clic sul pulsante Compra sul pacchetto di crediti desiderato. Segui le istruzioni per inserire i dettagli di pagamento e conferma l’ordine.

Una volta che la transazione è avvenuta con successo, i crediti saranno disponibili nel database.

#### Notifica crediti rimanenti¶

p

Apri l”applicazione Impostazioni e scrivi `IAP` nella barra Cerca…. Nella sezione Contatti, alla dicitura Odoo IAP fai clic su Visualizza servizi.

Gli account IAP disponibili appaiono nella vista elenco nella pagina Account IAP. Da qui, fai clic sull’account IAP desiderato per visualizzare la pagina Informazioni account relativa al servizio.

Nella pagina Informazioni account , spunta la casella Avvisami per poi visualizzare due campi: Limite e E-mail di avviso.

Nel campo Limite inserisci l’importo di crediti che Odoo dovrebbe usare come la soglia minima per il servizio. Nel campo E-mail di avviso inserisci l’indirizzo e-mail che riceverà le notifiche.

Odoo invia un avviso quando i crediti sono pochi all”E-mail di avviso quando il saldo dei crediti scende al di sotto dell’importo indicato nel campo Limite.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/essentials/in_app_purchase.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](keyboard_shortcuts.html "Scelte rapide da tastiera") |
  * [precedente](export_import_data.html "Esportare e importare dati") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Concetti fondamentali](../essentials.html) »
  * Acquisti in-app (IAP)


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
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