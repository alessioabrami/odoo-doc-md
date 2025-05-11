# Sincronizzazione bancaria — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank_synchronization/saltedge.html "Salt Edge") |
  * [precedente](../bank.html "Conti bancari e di cassa") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Sincronizzazione bancaria



# Sincronizzazione bancaria¶

Odoo può sincronizzarsi direttamente con il vostro istituto bancario per importare automaticamente tutti gli estratti conto nel vostro database.

Per verificare se la vostra banca è compatibile con Odoo, andate su [Caratteristiche della contabilità di Odoo](https://www.odoo.com/page/accounting-features), e cliccate su Vedi l’elenco delle istituzioni supportate.

Odoo supporta più di 26.000 istituti bancari in tutto il mondo.

Per collegarsi alle banche, Odoo utilizza diversi servizi web:

  * **Plaid** : Stati Uniti d’America e Canada

  * **Yodlee** : In tutto il mondo

  * [Salt Edge](bank_synchronization/saltedge.html): In tutto il mondo

  * [Ponto](bank_synchronization/ponto.html): Europa

  * doc:`Enable Banking <bank_synchronization/enablebanking>`: Paesi scandinavi




Vedi anche

transazioni

## Configurazione¶

### Utenti On-Premise¶

Per poter utilizzare questo servizio, è necessario avere un abbonamento valido a Odoo Enterprise. Assicuratevi quindi che il vostro database sia registrato con il vostro contratto Odoo Enterprise. Utilizziamo anche un proxy tra il vostro database e il provider di terze parti, quindi, in caso di errore di connessione, verificate di non avere un firewall o un proxy che blocca il seguente indirizzo:

  * <https://production.odoofin.com/>




### Prima sincronizzazione¶

È possibile avviare la sincronizzazione accedendo all’applicazione Contabilità e Contabilità ‣ Configurazione ‣ Aggiungi un conto bancario.

Ora è possibile cercare il proprio istituto bancario. Selezionatelo e seguite la procedura per sincronizzarlo.

Nota

Se si verificano problemi durante la prima sincronizzazione, verificare che il browser web non blocchi i pop-up e che l’ad-blocker sia disattivato.

Importante

Quando si imposta la sincronizzazione dell’estratto conto, Odoo inizia automaticamente a registrare le transazioni contabili a partire dalla data dell’ultima transazione +1 giorno (se l’ultimo giorno di transazione è il 31/12/2022, la registrazione inizia il 01/01/2023). Se il giornale non contiene alcuna transazione, Odoo recupera le transazioni il più indietro possibile. È possibile limitare la data di recupero delle transazioni da parte di Odoo aprendo l’applicazione Contabilità, andando su Contabilità ‣ Blocca date e impostando una data nel campo Data di blocco delle voci del giornale.

Durante la prima sincronizzazione è necessario fornire un numero di telefono per proteggere il proprio account. Chiediamo queste informazioni perché non vogliamo che i vostri dati finiscano nelle mani sbagliate. Pertanto, se rileviamo attività sospette sul vostro conto, blocchiamo tutte le richieste provenienti dal vostro conto e dovrete riattivarlo utilizzando quel numero di telefono.

Il fornitore di terze parti può richiedere ulteriori informazioni per connettersi con il vostro istituto bancario. Queste informazioni non vengono memorizzate sui server di Odoo.

Per impostazione predefinita, le transazioni recuperate da una fonte online vengono raggruppate nello stesso estratto conto e viene creato un estratto conto al mese. È possibile modificare la periodicità di creazione dell’estratto conto nelle impostazioni del giornale.

Per visualizzare tutte le sincronizzazioni, attivare la modalità developer e andare su :menuselection:`Accounting –> Configuration –> Online Synchronization.

### Sincronizzazione manuale¶

Dopo la prima sincronizzazione, i diari creati vengono sincronizzati per impostazione predefinita ogni 12 ore. Se lo si desidera, è possibile sincronizzarli manualmente facendo clic sul pulsante Sincronizza ora della dashboard.

In alternativa, attivare la modalità sviluppatore, andare su Contabilità ‣ Configurazione ‣ Sincronizzazione online, selezionare la propria istituzione e quindi fare clic sul pulsante Recupera transazioni.

Importante

Some institutions do not allow transactions to be fetched automatically. For such institutions, during the automatic synchronization of the account, you receive an error message asking you to disable the automatic synchronization. This message can be found in the chatter of your online synchronizations. In this case, make sure to perform manual synchronizations.

## Problemi¶

### Sincronizzazione errata¶

Per segnalare un errore di connessione al [Supporto Odoo](https://www.odoo.com/help), attivare la modalità developer`<developer-mode>, andare su :menuselection:`Accounting –> Configuration –> Online Synchronization, selezionare la connessione fallita e copiare la descrizione dell’errore e il riferimento.

### Sincronizzazione disconnessa¶

Se la connessione con il proxy è stata interrotta, è possibile riconnettersi con il proxy utilizzando il pulsante Recupera account.

Nota

Se non si riesce a riconnettersi utilizzando il pulsante Reconnect, si prega di contattare direttamente il [support](https://www.odoo.com/help) con il proprio id cliente o il riferimento dell’errore elencato nella chat.

## Processo di migrazione per gli utenti che hanno installato Odoo prima di dicembre 2020¶

Se siete in sede, assicuratevi innanzitutto che la vostra fonte sia aggiornata all’ultima versione di Odoo.

Gli utenti che hanno creato un database prima di dicembre 2020 devono installare manualmente il nuovo modulo per utilizzare le nuove funzionalità.

Per farlo, andare su Apps ‣ Update Apps List, rimuovere il filtro predefinito nella barra di ricerca e digitare `account_online_synchronization`. Potete quindi fare clic su Installa. Infine, assicuratevi che tutti gli utenti aggiornino la loro pagina di Odoo premendo CTRL+F5.

Nota

  * Tutte le sincronizzazioni precedenti sono state scollegate durante l’installazione e non funzioneranno più. Per visualizzarle, attivare la modalità developer mode 1 e andare su Accounting ‣ Configuration ‣ Online Synchronization). Non è possibile risincronizzare queste connessioni; è necessario crearne di nuove.

  * Non disinstallare il modulo `account_online_sync`, che è il modulo precedente per la sincronizzazione online. Il nuovo modulo lo sostituisce.

  * Per impostazione predefinita, il modulo `account_online_synchronization` è installato automaticamente con Accounting




## FAQ¶

### La sincronizzazione non funziona in tempo reale. È normale?¶

Il processo non è destinato a funzionare in tempo reale, poiché i fornitori di terze parti sincronizzano i conti a intervalli diversi. Per forzare la sincronizzazione e recuperare gli estratti conto, accedere alla Dashboard Contabilità e fare clic sul pulsante Sincronizza ora. Sincronizzare e recuperare le transazioni attivando la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e andando in Contabilità ‣ Configurazione ‣ Sincronizzazione online. Alcuni provider consentono un solo aggiornamento al giorno, per cui è possibile che cliccando su Sincronizza ora non si ottengano le ultime transazioni se si è già eseguita tale azione nel corso della giornata.

Una transazione può essere visibile sul conto bancario ma non essere recuperata se ha lo stato Pending. Verranno recuperate solo le transazioni con lo stato Posted. Se la transazione non è ancora **Posted** , si dovrà attendere che lo stato cambi.

### La funzione di sincronizzazione bancaria online è inclusa nel mio contratto?¶

  * **Community Edition** : No, questa funzione non è inclusa nella versione Community.

  * **Edizione online** : Sì, anche se si beneficia del contratto One App Free.

  * **Edizione aziendale** : Sì, se al database è collegato un contratto aziendale valido.




### Alcune banche hanno uno status “Beta”. Che cosa significa?¶

Ciò significa che gli istituti bancari non sono ancora pienamente supportati dal nostro fornitore di terze parti. Potrebbero verificarsi bug o altri problemi. Odoo non supporta i problemi tecnici che si verificano con le banche in fase Beta, ma l’utente può comunque scegliere di connettersi. La connessione con queste banche contribuisce al processo di sviluppo, poiché il Provider avrà a disposizione dati e feedback reali dalla connessione.

### Perché le mie transazioni si sincronizzano solo quando le aggiorno manualmente?¶

Alcune banche prevedono misure di sicurezza aggiuntive e richiedono ulteriori passaggi, come un codice di autenticazione via SMS/email o un altro tipo di MFA. Per questo motivo, l’integratore non può effettuare transazioni finché non viene fornito il codice di sicurezza.

### Non tutte le mie transazioni passate sono presenti in Odoo, perché?¶

Per alcuni istituti, le transazioni possono essere recuperate solo fino a 3 mesi prima.

### Perché non vedo alcuna transazione?¶

Durante la prima sincronizzazione, sono stati selezionati i conti bancari che si è deciso di sincronizzare con Odoo. Se non avete sincronizzato nessuno dei vostri conti, attivate la modalità sviluppatore 1, andate su Contabilità ‣ Configurazione ‣ Sincronizzazione online e fate clic sul pulsante Ricerca conto sulla connessione.

Potrebbero anche non esserci nuove transazioni.

Se il conto bancario è correttamente collegato a un giornale e le transazioni pubblicate non sono visibili nel database, si prega di [inviare un ticket di assistenza](https://www.odoo.com/help).

### Come posso aggiornare le mie credenziali bancarie?¶

Per aggiornare le credenziali, attivare la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e andare su Accounting ‣ Configuration ‣ Online Synchronization. Aprire la connessione di cui si vogliono aggiornare le credenziali e fare clic sul pulsante Aggiorna le credenziali.

  * [Salt Edge](bank_synchronization/saltedge.html)
  * [Ponto](bank_synchronization/ponto.html)
  * [Abilitare la Banca](bank_synchronization/enablebanking.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/bank/bank_synchronization.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](bank_synchronization/saltedge.html "Salt Edge") |
  * [precedente](../bank.html "Conti bancari e di cassa") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Conti bancari e di cassa](../bank.html) »
  * Sincronizzazione bancaria


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