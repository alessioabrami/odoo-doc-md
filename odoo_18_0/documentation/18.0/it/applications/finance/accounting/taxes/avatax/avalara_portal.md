# Portale Avalara (Avatax) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../eu_distance_selling.html "Vendite a distanza intracomunitarie nell’UE") |
  * [precedente](avatax_use.html "Utilizzare AvaTax") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Imposte](../../taxes.html) »
  * [Integrazione AvaTax](../avatax.html) »
  * Portale Avalara (Avatax)



# Portale Avalara (Avatax)¶

La console di gestione di Avalara (_AvaTax_) offre opzioni di gestione dell’account, tra cui: visualizzazione/modifica delle transazioni inviate da Odoo ad _AvaTax_ , dettagli sulle modalità di calcolo delle imposte, rendicontazione fiscale, gestione delle esenzioni fiscali e risorse per la dichiarazione dei redditi.

Suggerimento

Avalara è lo sviluppatore del software fiscale _AvaTax_.

Per accedere alla console, accedi al [sandbox](https://sandbox.admin.avalara.com/) o all’ambiente di [produzione](https://admin.avalara.com/) di Avalara. La scelta dipende dal tipo di account configurato nella [integrazione](../avatax.html). Quindi, accedi alla console.

Vedi anche

Per maggiori informazioni consulta la documentazione di Avalara: [Activate your Communications Customer Portal account](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=qvv1656594440497&topicId=Activate_your_Communications_Customer_Portal_account.html&_LANG=enus).

## Transazioni¶

Per accedere alle transazioni, fai clic sul link Transazioni nella dashboard principale dopo avere effettuato l’accesso al Portale Avalara (Avatax). Per accedere manualmente alla pagina _Transazioni_ , accedi alla console Avalara e poi Transazioni ‣ Transazioni.

### Modificare le transazioni¶

Fai clic su una transazione per avere più dettagli come le sezioni Dettagli fattura, Informazioni aggiuntive e Informazioni cliente. Fai clic sull’icona __ Modifica dettagli documento per apportare modifiche alla transazione.

È possibile aggiungere uno Sconto per sistemare la fattura. Questo è utile specialmente in casi in cui la transazione è già stata sincronizzata con Avalara/_AvaTax_ ed è necessario effettuare modifiche in seguito.

### Filtro¶

Per filtrare le transazioni sulla pagina Transazioni, configura i campi Da e A per poi configurare altri campi da utilizzare come filtri, compresi i seguenti:

  * Stato documenti: qualsiasi delle seguenti opzioni, Tutti, Vuoto, Impegnato, Non impegnato o Bloccato.

  * Codice documento: una delle seguenti opzioni, Corrispondenza esatta, Inizia con oppure Contiene.

  * Codice cliente/fornitore: il codice cliente/fornitore in Odoo (ad es. `Contact18`).

  * Paese: il Paese in cui è stata calcolata l’imposta. Si tratta di un campo testo.

  * Regione: la regione del Paese che varia in base al Paese scelto.




Fai clic su __ Filtri per accedere alle seguenti condizioni per i filtri stessi:

  * Tipo documento: una delle scelte seguenti, Tutti, Fattura vendita, Fattura acquisto, Fattura reso, Fattura in entrata trasferimento magazzino, Fattura in uscita trasferimento magazzino oppure Fattura clienti.

  * ID importazione: rappresenta l’ID di importazione del documento.




### Ordina per¶

Sulla pagina delle Transazioni, le transazioni verranno elencate secondo il Filtro configurato, situato nella metà superiore della pagina. Le seguenti colonne sono disponibili di default per ordinare in ordine crescente o decrescente:

  * Codice documento: una delle seguenti opzioni, Corrispondenza esatta, Inizia con oppure Contiene.

  * Stato documenti: qualsiasi delle seguenti opzioni, Tutti, Vuoto, Impegnato, Non impegnato o Bloccato.

  * Codice cliente/fornitore: il codice cliente/fornitore in Odoo (ad es. Contact18).

  * Regione: la regione del Paese che varia in base al Paese selezionato.

  * Importo: valore numerico dell’importo totale sul documento Odoo.

  * Imposta: valore numerico dell’imposta applicata al totale.




#### Personalizzare le colonne¶

È possibile aggiungere colonne extra facendo clic su __ Personalizza colonne. Nella finestra pop-up che si apre, fai clic sul menu a tendina della colonna da modificare.

Per fornire più informazioni su una transazione, è possibile aggiungere le seguenti colonne:

  * Calcolato da AvaTax: l’importo dell’imposta calcolato da _AvaTax_.

  * Paese: il Paese in cui è stata calcolata l’imposta. Si tratta di un campo testo.

  * Codice cliente/fornitore: il codice cliente/fornitore in Odoo (ad es. `Contact18`).

  * Valuta: l’abbreviazione standardizzata della valuta dell’importo totale.

  * Data documento: la data di creazione del documento.

  * Stato documento: qualsiasi delle seguenti opzioni, Tutti, Vuoto, Impegnato, Non impegnato o Bloccato.

  * Tipo documento: una delle scelte seguenti, Tutti, Fattura vendita, Fattura acquisto, Fattura reso, Fattura in entrata trasferimento magazzino, Fattura in uscita trasferimento magazzino oppure Fattura clienti.

  * ID importazione: rappresenta l’ID di importazione del documento.

  * Ultima modifica: orario dell’ultima volta in cui il documento è stato modificato.

  * Codice posizione: il codice posizione utilizzato per calcolare l’imposta, basato sull’indirizzo di spedizione.

  * Numero OdA: il numero dell’ordine di acquisto.

  * Codice di riferimento: il codice di riferimento Odoo (ad es. NV/2024/00003).

  * Regione: la regione del Paese che varia in base al Paese scelto.

  * Codice addetto vendite: l’ID numerico dell’utente assegnato all’ordine di vendita in Odoo.

  * Data imposta: il mese/giorno/anno del calcolo dell’imposta.

  * Tipo di esenzione: se non c’è nessuna esenzione, il campo si popola con Nessuna.




Per aggiungere una nuova colonna fai clic su __ Colonna.

Vedi anche

Per maggiori informazioni sulle transazioni _AvaTax_ , consulta la documentazione: [Transactions](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=qvv1656594440497&topicId=transactions.html&_LANG=enus).

### Importazione ed esportazione¶

Mentre sei sulla pagina Transazioni, fai clic su __ Importa transazioni o su __ Esporta transazioni per importare o esportare le transazioni.

### Report¶

Per accedere alla reportistica, fai clic sul link Report nel menu in alto della console di gestione di Avalara. In seguito, scegli una delle schede disponibili: Resoconti transazioni, Resoconti affidabilità e dichiarazioni dei redditi oppure Resoconti esenzioni.

Suggerimento

In aggiunta, troverai anche le schede Preferiti e Download. La scheda Preferiti contiene tutte le configurazioni preferite per i resoconti scelte dall’utente. La scheda Download è caratterizzata da una vista elenco da cui l’utente può scaricare i resoconti sulle transazioni ad alto volume creati negli ultimi 30 giorni.

Nella sezione Scegli resoconto, seleziona la Categoria resoconto e il Nome resoconto.

In seguito, riempi la sezione Seleziona dettagli resoconto. Queste opzioni variano in base alla scheda selezionata in precedenza.

A seconda delle dimensioni del resoconto, nella sezione Seleziona il numero approssimativo di transazioni per il resoconto sono disponibili due opzioni: Crea e scarica il resoconto all’istante (per i resoconti di piccole dimensioni) e Crea e scarica il resoconto in background (per i resoconti più grandi). Scegli una delle due opzioni a seconda del volume di transazioni presenti nel resoconto

Infine, nella sezione Anteprima ed esportazione resoconto, seleziona il tipo di file da scaricare. Puoi scegliere tra .PDF e .XLS. In alternativa, il file può essere visualizzato in anteprima selezionando l’opzione Anteprima.

Dopo aver selezionato tutte le impostazioni, fai clic su Crea resoconto per scaricare il resoconto. Fai clic su __ Resoconto preferito per salvare la configurazione tra i preferiti dell’utente.

Dopo aver creato il resoconto, fai clic su __ Download per scaricare il file sul dispositivo.

Suggerimento

Seleziona un resoconto preconfigurato dalla sezione Resoconti usati di frequente della dashboard relativa alla reportistica.

Accedi all’elenco facendo clic sull’opzione Resoconti nel menu in alto della console di gestione di Avalara e scorri fino in fondo alla pagina.

Vedi anche

[Consulta la documentazione di Avalara: Reports in AvaTax](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=rjq1671176624730&topicId=Reports_in_AvaTax.html&_LANG=enus).

## Aggiungere più giurisdizioni¶

È possibile aggiungere altre giurisdizioni (sedi fiscali) nella console di gestione di Avalara. Accedi alla [sandbox](https://sandbox.admin.avalara.com/) oppure all’ambiente di [produzione](https://admin.avalara.com/) di Avalara in base al tipo di account configurato nella [integrazione](../avatax.html).

Successivamente, apri le Impostazioni ‣ Dove riscuotere le imposte. Hai tre schede a disposizione, in base alle necessità del tuo business. La prima scheda è Imposte di vendita e uso, dove è possibile riscuotere le imposte per gli Stati Uniti. Fai clic su __:guilabel: `Aggiungi ` per aggiungere un altro luogo in cui l’azienda riscuote le imposte di vendita e uso.

La seconda opzioni, è la scheda IVA/GST dove puoi selezionare l’opzione __ Aggiungi Paese o territorio dove riscuoti l’IVA/GST per aggiungere un altro Paese o territorio dove l’azienda riscuote l’IVA/GST.

Infine, nell’estremità destra, trovi la scheda Dazi doganali, dove è possibile aggiungere un Paese dove l’azienda riscuote i dazi doganali. Fai clic sull’icona __ Aggiungi un Paese dove calcolare dazi doganali in basso alla scheda.

Vedi anche

[Consulta la documentazione Avalara: Add local jurisdiction taxes](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=bla1700809896571_bla1700809896571&topicId=nbw1698727575499.html&_LANG=enus).

## Certificato esenzione da imposta¶

I certificati di esenzione fiscale per i clienti possono essere aggiunti nella console di gestione di Avalara, in modo che _AvaTax_ sia a conoscenza di quali clienti possono essere esentati dal pagamento di determinate imposte. Per aggiungere un _certificato di esenzione_ , segui il percorso Esenzioni ‣ Certificati clienti. Da qui, fai clic su __ Aggiungi un certificato per configurare un’esenzione.

Avvertimento

Per allegare le immagini dei certificati ed essere pronti per una valutazione, è necessario un abbonamento Avalara a Exemption Certificate Management (ECM). Per maggiori informazioni sull’abbonamento al componente aggiuntivo, visita la pagina [Avalara](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=hff1682048150115_hff1682048150115&topicId=fol1682356576230.html&_LANG=enus).

## Operazioni di fine anno¶

I servizi di Avalara includono i servizi di dichiarazione dei redditi, per quando è il momento di presentare le tasse alla fine dell’anno. Per accedere ai servizi fiscali di Avalara, accedi al [portale di gestione](https://admin.avalara.com/). Quindi, dalla dashboard principale, fai clic su Dichiarazioni. Avalara chiederà all’utente di accedere per motivi di sicurezza e lo reindirizzerà al portale _Dichiarazioni_.

Fai clic su Inizia per avviare il processo di completamento della dichiarazione dei redditi. Per maggiori informazioni, consulta la documentazione di Avalara: [About Managed Returns](https://community.avalara.com/support/s/document-item?language=en_US&bundleId=hps1656397152776_hps1656397152776&topicId=Learn_about_Managed_Returns.html&_LANG=enus).

Suggerimento

In alternativa, fai clic sul pulsante Dichiarazioni nel menu in alto della console di gestione di Avalara.

Vedi anche

  * [Integrazione AvaTax](../avatax.html)

  * [Utilizzare AvaTax](avatax_use.html)

  * [Conformità imposte USA: video e-learning Avatax](https://www.odoo.com/slides/slide/us-tax-compliance-avatax-2858?fullscreen=1)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/taxes/avatax/avalara_portal.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../eu_distance_selling.html "Vendite a distanza intracomunitarie nell’UE") |
  * [precedente](avatax_use.html "Utilizzare AvaTax") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Finanza](../../../../finance.html) »
  * [Contabilità e fatturazione](../../../accounting.html) »
  * [Imposte](../../taxes.html) »
  * [Integrazione AvaTax](../avatax.html) »
  * Portale Avalara (Avatax)


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