# Fatturazione elettronica (EDI) — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sequence.html "Sequenza fattura") |
  * [precedente](deferred_revenues.html "Risconti passivi") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Fatturazione elettronica (EDI)



# Fatturazione elettronica (EDI)¶

Per EDI, o scambio elettronico di dati, si intende lo scambio tra aziende di documenti commerciali, come ordini di acquisto e fatture, in un formato standard. L’invio di documenti secondo uno standard EDI garantisce che il sistema che riceve il messaggio possa interpretare correttamente le informazioni. Esistono diversi formati di file EDI, disponibili a seconda del Paese dell’azienda.

La funzione EDI consente di automatizzare l’amministrazione tra aziende e può essere richiesta anche da alcuni governi per il controllo fiscale o per facilitare l’amministrazione.

La fatturazione elettronica di documenti come fatture clienti, note di credito o fatture fornitori rappresenta uno dei campi di applicazione dell’EDI.

Odoo supporta la fatturazione elettronica in molti Paesi. Per maggiori dettagli, consulta la pagina relativa Paese che ti interessa:

  * [Argentina](electronic_invoicing/argentina.html)

  * [Austria](electronic_invoicing/austria.html)

  * [Belgio](electronic_invoicing/belgium.html)

  * [Brasile](electronic_invoicing/brazil.html)

  * [Cile](electronic_invoicing/chile.html)

  * [Colombia](electronic_invoicing/colombia.html)

  * [Croazia](electronic_invoicing/croatia.html)

  * [Danimarca](electronic_invoicing/denmark.html)

  * [Ecuador](electronic_invoicing/ecuador.html)

  * [Estonia](electronic_invoicing/estonia.html)

  * [Finlandia](electronic_invoicing/finland.html)

  * [Francia](electronic_invoicing/france.html)

  * [Germania](electronic_invoicing/germany.html)

  * [Ungheria](electronic_invoicing/hungary.html)

  * [Irlanda](electronic_invoicing/ireland.html)

  * [Italia](electronic_invoicing/italy.html)

  * [Lettonia](electronic_invoicing/latvia.html)

  * [Lituania](electronic_invoicing/lithuania.html)

  * [Lussemburgo](electronic_invoicing/luxembourg.html)

  * [Messico](electronic_invoicing/mexico.html)

  * [Paesi Bassi](electronic_invoicing/netherlands.html)

  * [Norvegia](electronic_invoicing/norway.html)

  * [Perù](electronic_invoicing/peru.html)

  * [Polonia](electronic_invoicing/poland.html)

  * [Portogallo](electronic_invoicing/portugal.html)

  * [Romania](electronic_invoicing/romania.html)

  * [Slovenia](electronic_invoicing/slovenia.html)

  * [Spagna](electronic_invoicing/spain.html)

  * [Spagna - Paese Basco](electronic_invoicing/basque_country.html)

  * [Uruguay](electronic_invoicing/uruguay.html)




Vedi anche

[Documentazione sulla localizzazione fiscale](../../fiscal_localizations.html)

## Configurazione¶

Per impostazione predefinita, il formato disponibile nella finestra di invio dipende dal Paese del cliente.

È possibile indicare un formato di fatturazione elettronica specifico per ogni cliente. Per farlo, vai su Contabilità ‣ Clienti ‣ Clienti, apri il modulo cliente, apri la scheda Contabilità e scegli il formato appropriato.

### Fatturazione elettronica nazionale¶

In base al Paese dell’azienda (ad es., [Italia](../../fiscal_localizations/italy.html), [Spagna](../../fiscal_localizations/spain.html), [Messico](../../fiscal_localizations/mexico.html), ecc.), potrebbe essere necessario emettere documenti per la fatturazione elettronica in un formato specifico per tutte le fatture. In questo caso, puoi indicare un formato predefinito per i registri relativi alle vendite.

Per farlo, vai su Contabilità ‣ Configurazione ‣ Registri, apri il registro vendite, apri la scheda Impostazioni avanzate e attiva i formati di cui hai bisogno per il registro.

## Generazione di fatture elettroniche¶

Da una fattura confermata, fare clic su Invia e stampa per aprire la finestra di invio. Selezionare l’opzione di fatturazione elettronica per generare e allegare il file della fattura elettronica.

## Peppol¶

La rete [Peppol](https://peppol.org/about/) assicura lo scambio di documenti e informazioni tra imprese e autorità governative. È utilizzata principalmente per la fatturazione elettronica e i suoi punti di accesso (connettori alla rete Peppol) consentono alle imprese di scambiare documenti elettronici.

Odoo è un **punto di accesso** e un SMP, che consente di effettuare transazioni di fatturazione elettronica senza la necessità di inviare fatture e bollette per e-mail o per posta

Se non è ancora stato fatto, [installare](../../../general/apps_modules.html#general-install) il modulo Peppol (`account_peppol`).

Importante

  * La registrazione di Peppol è **gratuita** e disponibile nella Comunità Odoo.

  * È possibile inviare **fatture clienti** e **note di credito** e ricevere **fatture fornitori** e **rimborsi** tramite Peppol.

  * È possibile inviare e ricevere documenti in uno dei seguenti formati supportati: **BIS Billing 3.0, XRechnung CIUS, NLCIUS**.

  * I seguenti **paesi** sono idonei per la **registrazione di Peppol in Odoo** :

Andorra, Albania, Austria, Bosnia-Erzegovina, Belgio, Bulgaria, Svizzera, Cipro, Repubblica Ceca, Germania, Danimarca, Estonia, Spagna, Finlandia, Francia, Regno Unito, Grecia, Croazia, Ungheria, Irlanda, Islanda, Italia, Liechtenstein, Lituania, Lussemburgo, Lettonia, Monaco, Montenegro, Macedonia del Nord, Malta, Paesi Bassi, Norvegia, Polonia, Portogallo, Romania, Serbia, Svezia, Slovenia, Slovacchia, San Marino, Turchia, Santa Sede (Stato della Città del Vaticano)




### Registrazione¶

Vai su Contabilità ‣ Configurazione ‣ Impostazioni. Se non hai installato il modulo Peppol, spunta la casella Attiva PEPPOL e poi **salva manualmente**. Fai clic su Inizia a inviare con Peppol per aprire il modulo di registrazione.

Nota

Il modulo di registrazione appare anche se scegli di Inviare e stampare una fattura via Peppol senza completare il processo di registrazione.

Puoi registrarti come mittente o come destinatario. In Odoo, un mittente può solo inviare fatture e note di credito su tramite Peppol, senza registrarsi come partecipante Peppol su Odoo SMP. Se sei già registrato su Peppol altrove e vuoi mantenere la registrazione ma vuoi comunque inviare fatture dal database Odoo e ricevere altri documenti in un altro software, registrati come **mittente**.

Suggerimento

  * È sempre possibile registrarsi prima come mittente e poi come destinatario dei documenti.

  * Al momento della registrazione, è possibile specificare se si desidera ricevere anche i documenti.




Compila le seguenti informazioni.

  * Seleziona la casella del destinatario se desideri registrarti su Odoo SMP. Se stai effettuando la migrazione da un altro fornitore di servizi, inserisci la Chiave di migrazione del fornitore precedente (il campo diventa visibile dopo aver spuntato la casella).

  * Schema indirizzo elettronico: Lo schema dell’indirizzo elettronico di Peppol dipende solitamente dal Paese dell’azienda. Odoo spesso lo precompila con il codice EAS usato più comunemente nel Paese. Ad esempio, il codice EAS preferito per la maggior parte delle aziende in Belgio è `0208`.

  * Endpoint: si tratta del numero di registrazione o di Partita IVA dell’azienda.

  * Telefono: numero di telefono che comprende il codice Paese (ad es., `+32` in Belgio).

  * E-mail: e-mail che Odoo può utilizzare per inviarti comunicazioni riguardo la registrazione Peppol.




Se vuoi esplorare Peppol oppure ottenere una dimostrazione tecnica, puoi scegliere la modalità Demo. In caso contrario, scegli Live.

Suggerimento

  * Se scegli la modalità Demo, tutto verrà simulato in Odoo. Non sarà effettuato nessun invio, ricezione o verifica del partner.

  * **Solo per utenti avanzati** , è possibile effettuare test sulla rete di prova di Peppol. Il server permette di registrarsi su Peppol e inviare/ricevere fatture di prova da/ad altri partecipanti. Per farlo, attiva la modalità sviluppatore, apri l’app **Impostazioni** , vai su Funzioni tecniche ‣ Parametri di sistema e cerca `account_peppol.edi.mode`. Fai clic sul parametro e modificalo da Valore a `test`. Torna al menu di configurazione Peppol nell’app **Impostazioni**. Noterai che ora è disponibile l’opzione Test.




Vedi anche

  * [Peppol EAS - Commissione europea](https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/Code+lists/)

  * [Peppol Endpoint - OpenPeppol eDEC Code Lists](https://docs.peppol.eu/edelivery/codelists/) (apri il «Participant Identifier Schemes» come pagina HTML)




Una volta effettuata la configurazione, richiedi l’invio di un codice di verifica per fare clic su Invia codice di registrazione via SMS. Al numero di telefono fornito verrà inviato un messaggio di testo con un codice per finalizzare il processo di verifica.

Una volta inserito il codice e fatto clic su Registrati, il tuo stato partecipante Peppol verrà aggiornato. Se scegli solo di inviare documenti, lo stato passerà a Può inviare ma non ricevere. Se hai scelto anche di ricevere documenti, lo stato cambierà in Può inviare, registrazione in sospeso da ricevere. In quel caso, dovrebbe attivarsi automaticamente in un giorno.

In seguito, seleziona il registro predefinito per la ricezione di fatture fornitore nel Registro fatture in entrata.

Suggerimento

Per attivare manualmente il cron che verifica lo stato della registrazione, attiva la modalità sviluppatore, poi vai su Impostazioni ‣ Funzioni tecniche ‣ Azioni pianificate e cerca l’azione PEPPOL: aggiorna stato partecipante.

Lo stato di applicazione del destinatario dovrebbe essere aggiornato subito dopo la registrazione nella rete Peppol.

Tutte le fatture clienti e fornitori possono ora essere inviate direttamente tramite la rete Peppol.

Importante

Per aggiornare l’indirizzo e-mail che Odoo può utilizzare per contattarti, modifica l’e-mail e fai clic su Aggiorna dettagli contatto.

### Configurare i servizi Peppol¶

Una volta effettuata la registrazione su Odoo SMP, il pulsante Configura servizi Peppol diventa visibile per permetterti di attivare o disattivare i formati documento che gli altri partecipanti possono inviarti tramite Peppol. Per impostazione predefinita, vengono attivati tutti i formati documento supportati da Odoo (in base ai moduli installati).

### Verificare un contatto¶

Prima di inviare una fattura a un contatto che utilizza la rete Peppol, è necessario verificare che anch’esso sia registrato come partecipante su Peppol.

Per farlo, vai su Contabilità ‣ Clienti ‣ Clienti e apri il modulo cliente. In seguito, apri la scheda Contabilità ‣ Fatturazione elettronica, seleziona il formato corretto e assicurati che i campi codice Peppol EAS e Endpoint siano riempiti. In seguito, fai clic Verifica. Se il contatto esiste nella rete, la validità dell’endpoint Peppol è impostata su Valido.

Importante

Sebbene Odoo precompili il codice EAS e il numero di endpoint in base alle informazioni disponibili per un contatto, è meglio confermare questi dettagli direttamente con il contatto.

È possibile verificare lo stato partecipante Peppol di più clienti insieme. Per farlo, vai su Contabilità ‣ Clienti ‣ Clienti e passa alla vista elenco. Scegli i clienti che vuoi verificare e poi fai clic su Azioni ‣ Verifica Peppol.

Se il partecipante è registrato sulla rete Peppol ma non può ricevere il formato che hai scelto per loro, l’etichetta Validità endpoint Peppol cambierà in Non può ricevere questo formato.

### Inviare fatture¶

Quando sei pronto a inviare una fattura tramite Peppol, fai clic sul pulsante Salva e stampa presente sul modulo della fattura. Per mettere in coda più fatture, selezionale dalla vista elenco e fai clic su Azioni ‣ Invia e stampa. Le fatture verranno inviate in gruppo più tardi. È necessario selezionare sia la casella BIS Billing 3.0 che la casella Invia tramite PEPPOL.

Le fatture registrate che possono essere inviate tramite Peppol sono contrassegnate come Peppol pronto. Per visualizzarle, usa il filtro Peppol pronto oppure accedi alla dashboard Contabilità e fai clic su Fatture pronte Peppol sul registro vendite corrispondente.

Una volta inviate tramite Peppol, lo stato delle fatture passa a In elaborazione. Lo stato passa a `Completata` dopo che le fatture sono state consegnate con successo al punto di accesso del contatto.

Suggerimento

Per impostazione predefinita, la colonna stato di Peppol è nascosta nella vista elenco delle fatture. È possibile scegliere di visualizzarla selezionandola dalle colonne opzionali, accessibili dall’angolo in alto a destra della vista elenco delle fatture.

Un cron viene eseguito regolarmente per verificare lo stato di queste fatture. È possibile verificare lo stato prima che il cron venga eseguito facendo clic su Recupera stato fattura Peppol nel giornale vendite corrispondente sulla dashboard Contabilità.

### Ricevere fatture fornitore¶

Una volta al giorno, un cron controlla se sono stati inviati nuovi documenti attraverso la rete Peppol. Questi documenti vengono importati e le fatture fornitori corrispondenti vengono create automaticamente come bozze.

Se vuoi recuperare i documenti Peppol in entrata prima che venga eseguito il cron, puoi farlo dalla dashboard dell’app Contabilità sul registro acquisti Peppol principale configurato nelle impostazioni. È sufficiente fare clic su Recupera da Peppol.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/customer_invoices/electronic_invoicing.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sequence.html "Sequenza fattura") |
  * [precedente](deferred_revenues.html "Risconti passivi") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Fatturazione elettronica (EDI)


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