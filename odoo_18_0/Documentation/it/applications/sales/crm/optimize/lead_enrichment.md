# Arricchimento lead — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sales.html "Vendite") |
  * [precedente](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchimento lead



# Arricchimento lead¶

_Il lead enrichment_ è un servizio che fornisce informazioni commerciali per un contatto collegato a un lead. Il lead enrichment è un acquisto in app (IAP) che richiede crediti per essere utilizzato ed è disponibile per i lead esistenti in un database Odoo.

Le informazioni fornite dal lead enrichment possono comprendere informazioni generali sull’azienda (compresi il nome completo e il logo della stessa), account dei social media, Tipo di azienda, informazioni sulla Fondazione, Settori, numero di Dipendenti, Entrate previste, numero di Telefono, Fuso orario e Tecnologie utilizzate.

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima di scegliere se acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un’app gratuita.

Importante

La funzionalità _lead_ **deve** essere attivata nelle impostazioni del _CRM_ così da poter usare il lead enrichment. Per accedere alle impostazioni del _CRM_ , apri l’app CRM ‣ Configurazione ‣ Impostazioni. Nella sezione CRM, attiva l’opzione Lead e fai clic su Salva.

## Configurare la funzione di lead enrichment¶

Per configurare il lead enrichment nell’applicazione _CRM_ , accedi al modulo CRM ‣ Configurazione ‣ Impostazioni. In seguito, nella sezione Generazione lead, spunta la casella accanto a Lead enrichment e scegli Arricchire i lead solo su richiesta oppure Arricchire automaticamente tutti i lead. Fai clic sul pulsante Salva per attivare le modifiche.

## Arricchire lead¶

L’arricchimento dei lead si basa sul dominio dell’indirizzo e-mail del cliente impostato sul lead. Esistono due modi diversi per arricchire un lead: _automaticamente_ o _manualmente_.

### Arricchire lead automaticamente¶

Durante la configurazione, se selezioni Arricchire automaticamente tutti i lead nella pagina Impostazioni del _CRM_ , non è necessario che l’utente compia alcuna azione per arricchire il lead. Un’azione programmata viene eseguita automaticamente, ogni sessanta minuti, e l’arricchimento avviene sui lead, dopo aver contattato un database remoto.

Suggerimento

Per accedere al cron che viene eseguito per effettuare l’arricchimento dei lead automaticamente, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e accedi all’app Impostazioni ‣ menu Funzioni tecniche ‣ sezione Automazione ‣ Azioni programmate. Nella barra Ricerca…, scrivi `CRM`. Fai clic sul risultato dal nome CRM: arricchisci lead (IAP) ed effettua le modifiche necessarie. Nel campo Eseguire ogni e inserisci un valore maggiore o pari a cinque minuti.

Example

Di seguito è riportato un esempio di dati di arricchimento del lead che sono stati autocompilati con successo:

### Arricchire lead manualmente¶

Se l’opzione Arricchire lead solo su richiesta è stata selezionata nella pagina Impostazioni del _CRM_ , quando si attiva Arricchimento lead, ogni lead che un utente desidera arricchire **deve** essere arricchito manualmente. Questo si ottiene facendo clic sul pulsante Arricchisci nel menu superiore del lead.

Le stesse informazioni saranno recuperate allo stesso costo di credito IAP (uno per arricchimento). Questo metodo di arricchimento è utile quando non è necessario arricchire ogni lead o quando il costo è un problema.

Suggerimento

Arricchisci manualmente lead in gruppo usando la vista _elenco_. Per prima cosa, accedi all’app CRM ‣ Lead e fai clic sul pulsante vista elenco (icona ☰ (tre righe orizzontali)). Successivamente, spunta le caselle dei lead che dovrebbero essere arricchiti manualmente. Infine, fai clic sull’icona ⚙️ Azione e seleziona Arricchisci dal menu a discesa risultante. L’azione può essere eseguita anche dalla pagina _La mia pipeline_. Per farlo, apri il modulo _CRM_ , oppure segui il percorso app CRM ‣ Vendite ‣ La mia pipeline. Entrambi i percorsi mostrano lead e opportunità nella pagina Pipeline.

## Tariffazione¶

L’arricchimento dei lead è una funzione In-App Purchase (IAP) e ogni lead arricchito costa un credito.

Nota

Scopri di più sulle tariffe consultando la pagina: [Generazione lead da Odoo IAP](https://iap.odoo.com/iap/in-app-services/273).

Per comprare crediti, apri l’app CRM ‣ Configurazione ‣ Impostazioni. Nella sezione Generazione lead, sotto la funzionalità Arricchimento lead, fai clic su Compra crediti.

Crediti e saldi possono essere acquistati anche accedendo all’applicazione Impostazioni. Nella sezione Contatti, sotto la funzione IAP Odoo, fai clic su Vedi i miei servizi.

Vedi anche

[Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

Importante

Quando raccogli le informazioni di contatto di un’azienda, assicurati di conoscere le norme europee più recenti. Per maggiori informazioni sul Regolamento generale sulla protezione dei dati, consulta la pagina [Odoo GDPR](http://odoo.com/gdpr).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/crm/optimize/lead_enrichment.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sales.html "Vendite") |
  * [precedente](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchimento lead


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Puchase
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